---
title: Linux Post-Installation Steps
author: andrew
date: 2022-11-19 08:15:00 -0500
categories: [Linux]
tags: [code, linux, raspberry pi, ubuntu, ssh, hostname, poe, fan, docker, portainer, ntp, time, root, static IP, firewall]
pin: true
---

# Linux Post-Installation Steps

This guide is a walkthrough of all the important steps for a new Linux installation. The steps below will be written for Ubuntu Server, however can mostly be applied to any Linux distro. The final section will cover any additional steps to take on a Raspberry Pi running Ubuntu Server.

## Passwordless SSH

### PuTTY
This section will cover how to configure PuTTY to sign into your machine via SSH without the need for a password. See the below sections for information on other methods (MacOS, Disable Password Login, etc.).

1. If you haven't already, download and install PuTTY. After installation completes, run PuTTYgen.
2. From the `Key` menu, select `SSH-2 RSA Key`. Under the Parameters section, make sure RSA is selected. Enter `2048` as the number of bits.
3. Click <kbd>Generate</kbd>.
4. After the keys are generated, add a descriptive Key comment to help you easily identify your key and Save both keys (Public and Private Keys) to a secure location. **Do NOT close the PuTTYgen window yet.**
> Pay extra attention to where you save the Private Key because if anyone steals this key it can perform logins to your server without the need to enter a password.
{: .prompt-warning }
5. Copy the text in the `Public key for pasting into authorized_keys file:` and paste it into a new text document. 
6. SSH into the Linux machine as the user you want to login as without a password, then edit the `authorized_keys` file. 
```sh
pwd                 ## Check to see if you are in the correct $HOME location
mkdir .ssh          ## Create the .ssh folder if it isn't already there
nano .ssh/authorized_keys
```
7. Paste in the contents of the SSH key from the text document. Exit and save the document using <kbd>Ctrl+X</kbd>, <kbd>Y</kbd>, <kbd>Enter</kbd>.
8. Double check that the key saved and secure the `.ssh` folder with `700` permissions:
```sh
cat .ssh/authorized_keys
chmod -R 700 .ssh/
exit
```
9. In order to automatically use this key in PuTTY, open Putty and enter or load the configuration for the Linux machine. In the `Connection > SSH > Auth` category, click <kbd>Browse</kbd> and select your private key (`.ppk` file). Return to the `Session` category and save the configuration. 

### MacOS

1. This section coming soon

### Disable Password Login

1. Once you have passwordless SSH login successfully configured, you can disable password logins by editing the `sshd_config` file using:
```sh
sudo nano /etc/ssh/sshd_config
```
2. Uncomment the line `PasswordAuthentication yes` and change the value to `no`, then add the line `ChallengeResponseAuthentication no`. Save the config using <kbd>Ctrl+X</kbd>, <kbd>Y</kbd>, <kbd>Enter</kbd>.
3. Restart the SSH server using:
```sh
sudo systemctl restart ssh
```

## Updates

Now that we're logged into the Linux machine without a password, we will update the machine and configure automatic updates.

1. Run an `apt-get update` and `apt-get upgrade`:
```sh
sudo apt-get update
sudo apt-get upgrade
```
2. Configure automatic updates using `unattended-upgrades`:
```sh
sudo apt-get install unattended-upgrades
```
3. If you get a response that looks like this: `0 upgraded, 0 newly installed,...` run the following to reconfigure the package:
```sh
sudo dpkg-reconfigure --priority=low unattended-upgrades
```
4. Select <kbd>Yes</kbd> to automatically download and install updates.

## Additional Accounts, Sudoers, Disable Root

### Add New User

For this section, "andrew" will be used as the new user's username. Usernames are case-sensitive.

1. Add a new user to the machine using the `adduser` command:
```sh
sudo adduser andrew
```
2. Enter a password and verify that password.
3. Add name and additional information, if pertinent, and verify the information. 

### Sudoers

1. To add a user to the `sudoers` group, use the following:
```sh
sudo usermod -aG sudo andrew
```
2. Check the users sudo permissions:
```sh
sudo -l -U andrew
```
---
3. To manually edit the `sudoers` file and/or set `sudo` permissions to not require a password, use the following:
```sh
sudo visudo
```
4. In the editor that opens, you can change the `sudo` permissions for any user or group.
To add a `nopasswd` permission to a user, add the following under `# User privilege specification`:
```sh
andrew  ALL=(ALL) NOPASSWD:ALL
```
5. To add `nopasswd` permissions for the entire `sudo` group, add the following under `# Allow members of group sudo to execute any command`:
```sh
%sudo   ALL=(ALL) NOPASSWD: ALL
```

### Disable Root Login

> The `root` user is already disabled by default in Ubuntu, but this step may be useful in other distros.
{: .prompt-info }

1. Check to see if the `root` account is enabled:
```sh
grep root /etc/passwd
```
If you get a response of `root:x:0:0:root:/root:bin/sh`, then the `root` account is enabled.
2. Disable logins for the `root` account:
```sh
sudo passwd -l root
```

## Static IP Configuration

> This section applies to Ubuntu installations that use `netplan`.
{: .prompt-info }

__Ideally, use the "belt *and* suspenders" approach: reserve the IP in your DHCP scope as well as set the IP on the server itself.__

This section will suppose that you are assigning a static IP of `10.0.0.100` to a machine connected to a router at `10.0.0.1`, in the `255.255.255.0` subnet, using `1.1.1.1` and `1.0.0.1` as its DNS addresses.

1. You can check your machine's current IP configuration using `ip a`.
2. Edit the `netplan` configuration using:
```sh
cd /etc/netplan/
ls
##  Find your configuration .yaml file and edit it using nano
sudo nano 01-netcfg.yaml
```
3. Modify the `.yaml` file, following the [proper `netplan` formatting](https://netplan.io/examples):
```yaml
network:
    version: 2
    ethernets:
        eth0:
            dhcp4: no
            addresses:
                - 10.0.0.100/24
            nameservers:
                addresses: [1.1.1.1, 1.0.0.1]
            routes:
                - to: default
                    via: 10.0.0.1
```
4. Save and close the file using <kbd>Ctrl+X</kbd>, <kbd>Y</kbd>, <kbd>Enter</kbd>, then apply the new `netplan` using:
```sh
sudo netplan apply
```
*If you changed the IP address to something different than it previously was, it will disconnect your SSH session and you will have to reconnect to the __new__ IP address.*

## Fix LVM and Partitioning

> This section is specific to *non-Raspberry-Pi* Ubuntu installations.
{: .prompt-info }

Access the Logical Volume Manager (LVM) using `lvm` and the following commands:
```console
sudo lvm
lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
exit
```
Finally, use `resize2fs` to resize the volume:
```console
sudo resize2fs /dev/ubuntu-vg/ubuntu-lv
```

## Set / Change Hostname

Run `hostname` to see your current hostname, or use `hostnamectl` to get more information.   
To change your hostname, run the following, where `{host}` is your desired hostname.
```sh
sudo hostnamectl set-hostname {host}
```
Edit the `hosts` file:
```sh
sudo nano /etc/hosts
```
Replace the old hostname if it is present.

## Set Time Zone and NTP Server

1. Run `timedatectl` to see the currently configured time zone. If this is correct, skip to Step 3. Time zones must follow [tz database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List) format. You can view all time zones using `timedatectl list-timezones`.
2. If this is incorrect, set the correct time zone using:
```sh
sudo timedatectl set-timezone America/New_York
```
3. Check the current NTP configuration using `systemctl status systemd-timesyncd`. If you wish to change the NTP server, move on to the next step.
4. Edit the `timesyncd` configuration using `sudo nano /etc/systemd/timesyncd.conf`.
5. Set the content of the `[Time]` block to:
```
[Time]
NTP=
FallbackNTP=time.google.com
```
Leaving `NTP=` uncommented and assigned to an empty string resets the list of NTP servers. Configuring [Google Public NTP](https://developers.google.com/time/guides) as the fallback server will cause it to be selected as the only NTP server.

6. Restart `systemd-timesyncd` using `sudo systemctl restart systemd-timesyncd.service`.
7. Verify that your system is using Google Public NTP with `timedatectl show-timesync | grep ServerName`. If successfully configured, the output will show: 
```sh
ServerName=time.google.com
```

## Configuring UFW



