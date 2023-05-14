---
title: Plex User Guide
author: andrew
date: 2023-05-13 20:00:00 -0500
categories: [Plex]
tags: [plex, user, homelab, media, new, guide, graphics, movies, tv, shows, tv shows, music, libraries, overseerr, requests, quality]
pin: true
---

# Plex User Guide

This guide is meant to walk you through what Plex is, what it can do, and a few first steps that are suggested before you stream or request any media. 

> Please keep in mind that I operate this Plex server as a hobby, and I have multiple friends and family members that use the server. The best way to get support is to reach out to me directly or on the 'Plex Users' group chat.
{: .prompt-info }

## What's Plex?

### So what is Plex anyway?

You can think of Plex as a streaming service like Netflix or Hulu that is operated by someone you know instead of a huge company. What this means is that they have complete control over what content is available, and can often obtain shows and movies that you're looking for (even if they aren't available on other streaming platforms).

### Is Plex Free?

Server owners typically provide access to close friends and family only and don't charge for it.

Many server operators do pay a monthly or yearly fee for some additional features known as Plex Pass from the company that makes the Plex software. This helps to support ongoing efforts to make the Plex software better.

Additionally, Plex servers are a significant investment for the owner. The server hardware and storage devices are expensive to obtain and operate.

As a viewer, you can connect to and watch content on Plex servers for free through the Plex.tv website. However, viewing on the website often requires that the server transcode the media for you (more on that later). By using a Plex player that's specific to your hardware and platform, you'll get a better playback experience.

### Is Plex legal?

Plex is just a collection of software encompassing servers and clients. Plex itself is perfectly legal.

You can use Plex to stream content anywhere without worrying about copyright notices or the need to use a VPN or other means to hide your traffic.

## Getting Started

If you're here, you were probably invited to join my Plex server. The first step is to send me the email address you will use to create your free Plex account. If you've already done this: excellent, continue reading!

Shortly after you'll receive an email inviting you to join my server. Click the link in the email to accept the invitation and create your account at Plex.

Please don't share the account you create with others. If you know someone who you think would enjoy having access to this server, have them contact me. In most cases I'll be happy to add them with their own account. 

> Additionally, if you decide to purchase a Plex Pass (unlocks some paid features within your Plex players), the people you add to your "Plex Home" will not have access to my libraries.
{: .prompt-warning }

Now's the time to connect your playback devices to your new account. Depending on what you're using, you may need download and install the Plex app your device, or one may have come pre-installed. (This includes the App Store on iOS devices, the Google Play Store on Android devices, and other similar stores and libraries on other platforms like Roku.)

Upon first use for most of these platforms, you will either have to log in with your username and password, or link the device with your account when prompted. To link your account, your Smart TV or streaming device will show you a code made of 4 letters or numbers. Simply visit [plex.tv/link](https://www.plex.tv/link/) and enter the code (you may have to sign in first if you're not already). This linking process saves you from having to enter your username and password on your TV which can be frustrating.

Once you've entered the code, your streaming device should sign in automatically after a few moments.

You can visit the [Plex downloads page](https://www.plex.tv/media-server-downloads/#plex-app) to see a list of platforms on which the Plex player is available and be directed on how to install it for your device.

For convenience, Plex provides an online web client you can use to watch content at [app.plex.tv](https://app.plex.tv/). This makes it easy to catch up on your favorite shows while traveling or away from your preferred devices. However, using the web client should be avoided when possible as it is inefficient and puts unnecessary strain on the Plex server hardware.

## Playback Quality

> You will have to set your Video Settings on **each** device that you will be using to watch Plex.
{: .prompt-info }

Plex playback quality is dynamic and tries to adjust to the capabilities of your player and to the available internet bandwidth. However, out of the box, the quality settings in most Plex players are very conservative.

To increase the quality of your playback experience, locate the Settings in your Plex app, and navigate to the Video Settings section. Typically, you should try to set **Local Quality** to *Original* and set **Remote Quality** to *Maximum*. If you then find playback stutters or pauses frequently, reduce the quality setting until you achieve smooth playback. This will ensure that media is played on your device at the highest quality possible and can help reduce strain on the Plex server.

> See [this post](https://docs.shaffer.network/posts/plex-video-settings/) for device-specific instructions on how to set up your Video Settings!
{: .prompt-warning }



