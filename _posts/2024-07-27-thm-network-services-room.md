---
layout: post
title: TryHackMe - Network Services Room
---
[Network Services](https://tryhackme.com/r/room/networkservices)
---
# My Notes
I'm struggling with this one, especially Task 4: Exploiting SMB.

SMBClient isn't installed on my Ubuntu version, so I enter this command to install it: ``sudo apt install smbclient``

Usage: ``smbclient //[IP]/[SHARE]``

- Important flags:
    - -U [name]: to specify the user
    - -p [port]: to specify the port

- From the previous task (enumeration), I found:
    - The SMB share location: whatever IP that THM gives the target machine
    - Interesting share: **profiles**
    - SMB is running on ports **139/445**
