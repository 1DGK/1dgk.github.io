---
layout: post
title: TryHackme Intro to Offensive Security Room
tags: tryhackme linux openvpn cybersecurity tools
---
Here is a link to the room [TryHackme Intro to Offensive Security Room](https://tryhackme.com/room/introtooffensivesecurity)

Start the machine.

Grab the IP address of the machine. In my case, it's 10.10.194.153.

Log into that machine. I'm using OpenVPN to connect to it from my Linux machine. Remember to get the config file from TryHackMe's network access page. Then make the connection:
```sh
sudo openvpn [filename.ovpn]
```

Then take that IP address from above and enter it into your web browser. 

To get rid of the split-view, click the icon at the bottom-left of the machine's viewport.

This task requires a program called GoBuster. So let's go ahead and install that:
```sh
sudo apt install gobuster
```

I ran the command as instructed:
```sh
gobuster -u http://fakebank.com -w wordlist.txt dir
```

But ran into this error:
```sh
2024/01/14 15:25:20 [!] 1 error occurred:
	* Wordlist (-w): File does not exist: wordlist.txt
```

After a bit of searching, I learned that SecLists is a common package used in security testing. It's maintained by Daniel Miessler, among others. It's a large batch of files, so it takes a minute.
So I [installed that package](https://github.com/danielmiessler/SecLists) using snap in Ubuntu:
```sh
snap install seclists
```
I eventually found the seclist folder:
```sh
dgk@dgk-virtual-machine:/snap/seclists/current$ ls
Discovery  LICENSE        Passwords         SecLists.png  usr
Fuzzing    meta           Pattern-Matching  snap          Web-Shells
IOCs       Miscellaneous  Payloads          Usernames
```

I searched for a wordlist text file, to no avail.

I finally figured it out. I found a wordlist file in the SecList folder called wordlist-skipfish.fuzz.txt. From the directory of that file (/snap/seclists/current/Miscellaneous), I ran the original command and replaced the wordlist with my newfound list from SecLists:
```sh
gobuster -u http://fakebank.com -w wordlist-skipfish.fuzz.txt dir
```
And finally I got some results:
```sh
=====================================================
Gobuster v2.0.1              OJ Reeves (@TheColonial)
=====================================================
[+] Mode         : dir
[+] Url/Domain   : http://fakebank.com/
[+] Threads      : 10
[+] Wordlist     : wordlist-skipfish.fuzz.txt
[+] Status codes : 200,204,301,302,307,403
[+] Timeout      : 10s
=====================================================
2024/01/14 15:54:20 Starting gobuster
=====================================================
2024/01/14 15:54:21 [-] Wildcard response found: http://fakebank.com/a102c407-1074-42f5-ac96-ed9d9838b527 => 200
2024/01/14 15:54:21 [!] To force processing of Wildcard responses, specify the '-fw' switch.
=====================================================
2024/01/14 15:54:21 Finished
=====================================================
```

We got a hit (see status 200), but it's not the hidden page that TryHackMe wants us to find. 

In the end, the answer is partly given away by the instructions. I'm not sure exactly which wordlist TryHackMe used, but my wordlist from SecLists didn't line up. Not the end of the world. 

All that to say, GoBuster is a neat way to find any hidden pages within a sitemap.