---
title: Homelab Ideas
author: andrew
date: 2022-11-21 00:18:00 -0500
categories: [Homelab]
tags: [docker, self host, selfhosted, containers, github, software, business, personal, accounting, invoicing, crm, erp, help desk, inventory, media, organization, smart home, passwords, wiki, backups, email, monitoring, networking, security, sysadmin, homelab]
pin: true
---

# Homelab Ideas

---
## Business

### Accounting / Invoicing
- [ ] [Invoice Ninja](https://www.invoiceninja.org/) ([GitHub](https://github.com/invoiceninja/invoiceninja))
  - Invoicing, Quotes, Expenses, Time-Tracking built with Laravel & Flutter
- [ ] 

### CRM / ERP
- [ ] [Dolibarr](https://www.dolibarr.org/) ([GitHub](https://github.com/dolibarr))
  - A modern software package that helps manage your organization's activity (contacts, suppliers, invoices, orders, stocks, agenda…). Use it as a standalone application or as a web application to access it from the Internet or a LAN.
- [ ] [Odoo](https://www.odoo.com/) ([GitHub](https://github.com/odoo/odoo))
  - A suite of web-based open-source business apps
- [ ] [SuiteCRM](https://suitecrm.com/) ([GitHub](https://github.com/salesagility/SuiteCRM))
- [ ] 

### Help Desk / Ticketing
- [ ] [Trudesk](http://trudesk.io/) ([GitHub](https://github.com/polonel/trudesk))
  - Open-source help desk/ticketing solution
- [ ] [OTOBO](https://otobo.de/en/) ([GitHub](https://github.com/RotherOSS/))
  - Web-based ticketing systems used for Customer Service, Help Desk, IT Service Management
- [ ] 

### Inventory/Asset Management
- [ ] [PartKeepr](https://www.partkeepr.org/) ([GitHub](https://github.com/partkeepr/PartKeepr))
  - Open source parts/inventory management ([Docker Compose file](https://github.com/partkeepr/PartKeepr/blob/master/docker/development/docker-compose.yml))
- [ ] [Snipe-IT](https://snipeitapp.com/product/open-source) ([GitHub](https://github.com/snipe/snipe-it))
  - A free, open-source IT asset/license management system
- [ ] [PyInventory (GitHub)](https://github.com/jedie/PyInventory)
  - Web based management to catalog things including state and location etc.
- [ ] 

---
## Personal

### Media
- [ ] [MeTube (GitHub)](https://github.com/alexta69/metube)
  - YouTube-DL web UI
- [ ] [AllTube](https://www.alltubedownload.net/) ([GitHub](https://github.com/Rudloff/alltube))
  - Web GUI for youtube-dl
- [ ] [Calibre](https://calibre-ebook.com/)
  - E-book library manager that can view, convert, and catalog e-books in most of the major e-book formats and provides a built-in Web server for remote clients
- [ ] [Calibre Web](https://github.com/janeczku/calibre-web)
  - Web app providing a clean interface for browsing, reading and downloading eBooks using an existing Calibre database
- [ ] 

### Organization
- [ ] [Paperless-ngx](https://paperless-ngx.readthedocs.io/en/latest/) ([GitHub](https://github.com/jonaswinkler/paperless-ng)
  - A community-supported supercharged version of paperless: scan, index and archive all your physical documents
- [ ] [Tandoor](https://tandoor.dev/)
  - Recipe collection manager
- [ ] [Koillection](https://koillection.github.io/) ([GitHub](https://github.com/koillection/koillection))
  - A self-hosted website to manage all your collections
- [ ] 

### Password & Bookmark Managers
- [ ] [LinkWarden (GitHub)](https://github.com/Daniel31x13/link-warden)
  - A self-hosted bookmark + archive manager to store your useful links.
- [ ] [Reminiscence (GitHub)](https://github.com/kanishka-linux/reminiscence)
  - Self-Hosted Bookmark And Archive Manager
- [ ] [PassCheck](https://passcheck.anhur.xyz/) ([GitHub](https://github.com/apacketofsweets/PassCheck))
  - A web application featuring some handy password tools, including a password generator, strength checker and HaveIBeenPwned breach checker
- [ ] 

### Smart Home
- [ ] 

### Social
- [ ] [Monica](https://github.com/monicahq/monica/blob/main/docs/installation/providers/docker.md)
  - Personal CRM. Remember everything about your friends, family and business relationships.
- [ ] [Webtrees](http://www.webtrees.net/) ([GitHub](https://github.com/fisharebest/webtrees)) [[Docker GitHub](https://github.com/H2CK/webtrees)]
  - The web's leading online collaborative genealogy application
- [ ] [Baïkal](https://sabre.io/baikal/)([GitHub](https://github.com/sabre-io/Baikal))
  - Lightweight CalDAV and CardDAV server
- [ ] 

### Wikis / Notes
- [ ] [BookStack](https://www.bookstackapp.com/) ([GitHub](https://github.com/BookStackApp/BookStack))
  - A simple, self-hosted, easy-to-use platform for organizing and storing information
- [ ] [Trilium (GitHub)](https://github.com/zadam/trilium)
  - A hierarchical note taking application with focus on building large personal knowledge bases
- [ ] 

---
## SysAdmin

### Backups & Updates
- [ ] [ArchiveBox](https://archivebox.io/)
  - Self-hosted internet archiving solution
- [ ] [Syncthing (GitHub)](https://github.com/syncthing/syncthing)
  - A continuous file synchronization program ([Documentation site](https://docs.syncthing.net/index.html))
- [x] [Watchtower](https://containrrr.dev/watchtower/) ([GitHub](https://github.com/containrrr/watchtower))
- [ ] 

### Docker
- [ ] [Dockprom (GitHub)](https://github.com/stefanprodan/dockprom)
  - Docker host and container monitoring with Prometheus, Grafana, cAdvisor, NodeExporter and AlertManager
- [ ] [cAdvisor (GitHub)](https://github.com/google/cadvisor)
  - Analyzes resource usage and performance characteristics of running containers
- [x] [Watchtower](https://containrrr.dev/watchtower/) ([GitHub](https://github.com/containrrr/watchtower))
- [ ] 

### Email
- [ ] [docker-mailserver](https://docker-mailserver.github.io/docker-mailserver/edge/) ([GitHub](https://github.com/docker-mailserver/docker-mailserver))
  - Production-ready fullstack but simple mail server (SMTP, IMAP, LDAP, Antispam, Antivirus, etc.) running inside a container
- [ ] [Mailcow](https://mailcow.email/) ([GitHub](https://github.com/mailcow/mailcow-dockerized))
  - Mail server suite based on Dovecot, Postfix and other open source software, that provides a modern Web UI for administration
- [ ] [Mailu](https://mailu.io/) ([GitHub](https://github.com/Mailu/Mailu))
- [ ] [SnappyMail](https://snappymail.eu/) ([GitHub](https://github.com/the-djmaze/snappymail))
  - Simple, modern, lightweight & fast web-based email client. (It is an actively developed fork of RainLoop)
- [ ] 

### Monitoring
- [ ] [Dockprom (GitHub)](https://github.com/stefanprodan/dockprom)
  - Docker host and container monitoring with Prometheus, Grafana, cAdvisor, NodeExporter and AlertManager
- [ ] [cAdvisor (GitHub)](https://github.com/google/cadvisor)
  - Analyzes resource usage and performance characteristics of running containers
- [ ] [Linux Dash (GitHub)](https://github.com/tariqbuilds/linux-dash)
  - A beautiful web dashboard for Linux
- [ ] [SWMP (GitHub)](https://github.com/fuzzymannerz/swmp)
  - A responsive, eye-pleasing Linux server statistics dashboard.
- [ ] [Cockpit](https://cockpit-project.org/) ([GitHub](https://github.com/cockpit-project/cockpit))
  - Easy-to-use, integrated, glanceable, and open web-based interface for your servers
- [ ] 

### Networking
- [ ] [Ralph](https://ralph.allegro.tech/) ([GitHub](https://github.com/allegro/ralph))
  - CMDB / Asset Management system for data center and back office hardware
- [ ] [WireShark](https://www.wireshark.org/)
  - Network protocol analyzer
- [ ] [Cacti](https://www.cacti.net/) ([GitHub](https://github.com/cacti/))
  - A complete network graphing solution
- [ ] 

### Remote Access
- [ ] [Apache Guacamole](https://guacamole.apache.org/) ([GitHub Repos](https://github.com/search?utf8=%E2%9C%93&q=repo%3Aapache%2Fguacamole-server+repo%3Aapache%2Fguacamole-client+repo%3Aapache%2Fguacamole-website&type=Repositories&ref=searchresults))
  - A browser-accessible, clientless remote desktop gateway. Supports protocols like VNC, RDP, and SSH.
- [ ] 


### Security
- [ ] [BounCA](https://bounca.org/index.html)
  - Web-GUI based X509.v3 certificates management tool
- [ ] 
