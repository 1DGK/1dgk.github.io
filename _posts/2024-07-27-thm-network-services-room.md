---
layout: post
title: TryHackMe - Network Services Room
---
[Network Services](https://tryhackme.com/r/room/networkservices)
---
# My Notes
**FOR NMAP, ALWAYS USE THE `-vv-` option** It makes it readable.

Install SMBClient: ``sudo apt install smbclient``

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

### Task 9 - Enumerating FTP
**How many ports are open on the target machine?**
21

```sh
dgk@dgk-desktop:~$ sudo nmap -sS -O -vv 10.10.106.6
Starting Nmap 7.95 ( https://nmap.org ) at 2024-08-07 20:00 EDT
Initiating Ping Scan at 20:00
Scanning 10.10.106.6 [4 ports]
Completed Ping Scan at 20:00, 0.18s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 20:00
Completed Parallel DNS resolution of 1 host. at 20:00, 0.03s elapsed
Initiating SYN Stealth Scan at 20:00
Scanning 10.10.106.6 [1000 ports]
Discovered open port 21/tcp on 10.10.106.6
Completed SYN Stealth Scan at 20:00, 1.45s elapsed (1000 total ports)
Initiating OS detection (try #1) against 10.10.106.6
Retrying OS detection (try #2) against 10.10.106.6
Retrying OS detection (try #3) against 10.10.106.6
Retrying OS detection (try #4) against 10.10.106.6
Retrying OS detection (try #5) against 10.10.106.6
Nmap scan report for 10.10.106.6
Host is up, received reset ttl 61 (0.10s latency).
Scanned at 2024-08-07 20:00:37 EDT for 13s
Not shown: 999 closed tcp ports (reset)
PORT   STATE SERVICE REASON
21/tcp open  ftp     syn-ack ttl 61
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.95%E=4%D=8/7%OT=21%CT=1%CU=31182%PV=Y%DS=4%DC=I%G=Y%TM=66B40AB3
OS:%P=x86_64-unknown-linux-gnu)SEQ(SP=104%GCD=1%ISR=10A%TI=Z%CI=I%TS=A)SEQ(
OS:SP=106%GCD=1%ISR=10C%TI=Z%CI=I%II=I%TS=A)SEQ(SP=107%GCD=1%ISR=109%TI=Z%C
OS:I=I%II=I%TS=A)SEQ(SP=107%GCD=1%ISR=10C%TI=Z%CI=I%II=I%TS=A)SEQ(SP=108%GC
OS:D=1%ISR=10B%TI=Z%CI=I%II=I%TS=A)OPS(O1=M509ST11NW6%O2=M509ST11NW6%O3=M50
OS:9NNT11NW6%O4=M509ST11NW6%O5=M509ST11NW6%O6=M509ST11)WIN(W1=68DF%W2=68DF%
OS:W3=68DF%W4=68DF%W5=68DF%W6=68DF)ECN(R=Y%DF=Y%T=40%W=6903%O=M509NNSNW6%CC
OS:=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=AS%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T
OS:=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T5(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=
OS:0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=
OS:Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%DF=N%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=
OS:G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=40%CD=S)

Uptime guess: 4.578 days (since Sat Aug  3 06:07:56 2024)
Network Distance: 4 hops
TCP Sequence Prediction: Difficulty=262 (Good luck!)
IP ID Sequence Generation: All zeros

Read data files from: /snap/nmap/3514/usr/bin/../share/nmap
OS detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 14.25 seconds
           Raw packets sent: 1128 (54.468KB) | Rcvd: 1085 (47.720KB)
```

**What port is ftp running on?**
21

**What variant of FTP is running on it?**
vsftpd

```sh
nmap -sV -p 21 10.10.106.6
Starting Nmap 7.95 ( https://nmap.org ) at 2024-08-07 20:10 EDT
Nmap scan report for 10.10.106.6
Host is up (0.17s latency).

PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 2.0.8 or later
Service Info: Host: Welcome

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 12.22 seconds
```
**Great, now we know what type of FTP server we're dealing with we can check to see if we are able to login anonymously to the FTP server. We can do this using by typing "ftp [IP]" into the console, and entering "anonymous", and no password when prompted.**

**What is the name of the file in the anonymous FTP directory?**
PUBLIC_NOTICE.txt

**What do we think a possible username could be?**
Mike

Download the file using 
```sh
ftp> get PUBLIC_NOTICE.txt
local: PUBLIC_NOTICE.txt remote: PUBLIC_NOTICE.txt
229 Entering Extended Passive Mode (|||41992|)
150 Opening BINARY mode data connection for PUBLIC_NOTICE.txt (353 bytes).
100% |***************************************************************|   353      145.57 KiB/s    00:00 ETA
226 Transfer complete.
353 bytes received in 00:00 (2.26 KiB/s)
```
Then open the file, which was saved to the present working directory:
```sh
dgk@dgk-desktop:~$ pwd
/home/dgk
dgk@dgk-desktop:~$ ls
Downloads  PUBLIC_NOTICE.txt  snap
dgk@dgk-desktop:~$ cat PUBLIC_NOTICE.txt
===================================
MESSAGE FROM SYSTEM ADMINISTRATORS
===================================

Hello,

I hope everyone is aware that the
FTP server will not be available
over the weekend- we will be
carrying out routine system
maintenance. Backups will be
made to my account so I reccomend
encrypting any sensitive data.

Cheers,

Mike
```

Great! Now we've got details about the FTP server and, crucially, a possible username. Let's see what we can do with that...