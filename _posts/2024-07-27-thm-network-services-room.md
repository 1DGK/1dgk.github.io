---
layout: post
title: TryHackMe - Network Services Room
---
[Network Services](https://tryhackme.com/r/room/networkservices)
---
# My Notes
**FOR NMAP, ALWAYS USE THE `-vv-` option** It makes it very readable.


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

- Ports 445/tcp, 22/tcp, and 139/tcp are open

```sh
root@ip-10-10-223-119:~# smbclient //10.10.229.100/profiles -U Anonymous -p 445
WARNING: The "syslog" option is deprecated
Enter WORKGROUP\Anonymous's password: 
Try "help" to get a list of possible commands.
smb: \> ls -a
NT_STATUS_NO_SUCH_FILE listing \-a
smb: \> ls
  .                                   D        0  Tue Apr 21 12:08:23 2020
  ..                                  D        0  Tue Apr 21 11:49:56 2020
  .cache                             DH        0  Tue Apr 21 12:08:23 2020
  .profile                            H      807  Tue Apr 21 12:08:23 2020
  .sudo_as_admin_successful           H        0  Tue Apr 21 12:08:23 2020
  .bash_logout                        H      220  Tue Apr 21 12:08:23 2020
  .viminfo                            H      947  Tue Apr 21 12:08:23 2020
  Working From Home Information.txt      N      358  Tue Apr 21 12:08:23 2020
  .ssh                               DH        0  Tue Apr 21 12:08:23 2020
  .bashrc                             H     3771  Tue Apr 21 12:08:23 2020
  .gnupg                             DH        0  Tue Apr 21 12:08:23 2020
```

I had to look for help on this task, because I tried for several days and couldn't crack it. [Here is where I found help](https://medium.com/@danielhuynh_7529/tryhackme-network-services-ebc660996ac3). It's not the best idea, but after enough time I had to get some help.
---
### Task 6 - Enumerating Telnet
**How many ports are open on the target machine?**
```sh
dgk@dgk-ThinkPad-T540p:~$ nmap -p- -v -T4 10.10.198.176
```
This takes about 10 minutes.

**What port is this?**

**This port is unassigned, but still lists the protocol it's using, what protocol is this?**

**Now re-run the nmap scan, without the -p- tag, how many ports show up as open?**

**Here, we see that by assigning telnet to a non-standard port, it is not part of the common ports list, or top 1000 ports, that nmap scans. It's important to try every angle when enumerating, as the information you gather here will inform your exploitation stage.**

**Based on the title returned to us, what do we think this port could be used for?**

**Who could it belong to? Gathering possible usernames is an important step in enumeration.**

**Always keep a note of information you find during your enumeration stage, so you can refer back to it when you move on to try exploits.**