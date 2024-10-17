---
layout: post
title: TryHackMe Linux Fundamentals Part 3
tags: tryhackme linux openvpn cybersecurity tools
---
These are notes from [my journey through TryHackMe's free rooms](https://1dgk.github.io/2024/01/15/tryhackme-free-rooms.html). Here are my notes from the [Linux Fundamentals Part 3](https://tryhackme.com/room/linuxfundamentalspart3) room.

This room is more intense than the first two. 

Learn the ps command.

To kill a process cleanly, use the SIGTERM command.

Use the ```ps aux``` command to find the process that contains a flag. 

To stop an example service called 'myservice', use the following command: ```systemctl stop myservice```. 

To start the same service on the boot-up of the system, use the following command: ```systemctl enable myservice```.

To background a service, use ```Ctrl+Z``` or ```fg```.

---
Dig into cron and crontab.
- Tools like [Crontab Generator](https://crontab-generator.org/) and [crontab guru](https://crontab.guru/).

To check crons and edit them, use the following command: ```crontab -e```.
---
Look at access logs in the var/logs folder.

Cat one of the access log files and note the ip of the user who visited the site.

Also, check what file they accessed.