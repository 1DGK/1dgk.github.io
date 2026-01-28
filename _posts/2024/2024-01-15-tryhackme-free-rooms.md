---
layout: post
title: My TryHackMe Free Room Journey
tags: tryhackme linux openvpn cybersecurity tools
---
Inspired by [this post](https://tryhackme.com/r/resources/blog/free_path), I'll work through each room and provide explanations along the way.

### Level 1 - Getting Started

Before getting started with challenges and CTFs (Capture the Flags), we recommend easing in with the following training:
- [x] Tutorial - Learn how to use a TryHackMe room to start your upskilling in cyber security
- [x] [Intro to Offensive Security](https://tryhackme.com/room/introtooffensivesecurity) - Hack your first website (legally in a safe environment) and experience an ethical hacker's job
    - [My notes](https://1dgk.github.io/2024/01/14/tryhackme-intro-offsec.html)
- [x] [Introduction to Offensive Pentesting](https://tryhackme.com/module/introduction-to-offensive-pentesting) - Understand what a penetration test involves, including testing techniques and methodologies every pentester should know
- [x] [Linux Fundamentals](https://tryhackme.com/module/linux-fundamentals) - Learn how to use the Linux operating system, a critical skill in cyber security
    - [My notes](https://1dgk.github.io/2024/01/17/thm-linux-pt3.html)
- [ ] [OhSINT](https://tryhackme.com/room/ohsint) - Use open-source intelligence to solve this challenge!

### Level 2 - Tooling

The most important thing in a pentester's toolbox is tooling. At this level, you’ll learn the absolute minimum of the necessary tools to become a better hacker!

- [ ] [Nmap Live Host Discovery](https://tryhackme.com/room/nmap01) - Learn how to use Nmap to discover live hosts using ARP scan, ICMP scan, and TCP/UDP ping scan
    - [ ] [Nmap](https://tryhackme.com/room/furthernmap) - this one might be a little more in-depth.
- [ ] Hydra - Learn about and use Hydra, a fast network logon cracker, to bruteforce and obtain a website's credentials
- [ ] Linux PrivEsc - Practice your Linux Privilege Escalation skills on an intentionally misconfigured Debian VM with multiple ways to get root!
- [ ] Burp Suite: The Basics - An introduction to using Burp Suite for Web Application pentesting
- [ ] Introduction to OWASP ZAP - Learn how to use OWASP ZAP from the ground up (an alternative to BurpSuite)
- [ ] Metasploit: Introduction - An introduction to the main components of the Metasploit Framework 

Again, here are some more introductory CTFs. These are a little more complex, but with your new knowledge of tools, you should smash them in no time! Don't worry if you can't, that's what hacking is all about – trying harder until you can no longer try and then learning from what you couldn't do.

- [ ] Vulnversity - Learn about active recon, web app attacks and privilege escalation
- [ ] Blue - Deploy & hack into a Windows machine, leveraging common misconfigurations issues
- [ ] Simple CTF - A beginner-friendly Capture the Flag
- [ ] Bounty Hacker - Prove that you’re the most elite hacker in the solar system, and claim your right to the status of Elite Bounty Hacker!
- [ ] Brute It - Learn how to brute, hash cracking and escalate privileges

### Level 3 - Crypto & Hashes with CTF Practice

Understanding cryptography is essential to any hacker. This section will teach you the basics and give you some CTF practice.

- [ ] Introduction to Cryptography - Learn about encryption algorithms such as AES, Diffie-Hellman key exchange, hashing, PKI, and TLS
- [ ] Crack the Hash - Cracking hashes challenges
- [ ] Agent Sudo - You found a secret server located under the deep sea. Your task is to hack inside the server and reveal the truth!
- [ ] The Cod Caper - A guided room taking you through infiltrating and exploiting a Linux system
- [ ] Lazy Admin - Have fun and practice your skills with Linux
- [ ] Encryption - Crypto 101 - An introduction to encryption, as part of a series on crypto

### Level 4 - Web

- [ ] Content Discovery - Learn the various ways of discovering hidden or private content on a webserver that could lead to new vulnerabilities
- [ ] Walking an Application - Manually review a web application for security issues using only your browsers developer tools
- [ ] SQL Injection - Learn how to detect and exploit SQL Injection vulnerabilities
- [ ] DNS in Detail - Learn how DNS works and how it helps you access internet services
- [ ] HTTP in Detail - Learn about how you request content from a web server using the HTTP protocol
- [ ] Burp Suite Basics - An introduction to using Burp Suite for Web Application pentesting
- [ ] OWASP Juice Shop - This free room uses the Juice Shop vulnerable web application to learn how to identify and exploit common web application vulnerabilities
- [ ] Overpass - What happens when some broke CompSci students make a password manager?
- [ ] Bolt - Get familiar with the Bolt CMS and how it can be exploited using Authenticated Remote Code Execution
- [ ] Takeover - This challenge revolves around subdomain enumeration
- [ ] Neighbour - Check out our new cloud service, Authentication Anywhere. Can you find other user's secrets
- [ ] Corridor - Can you escape the corridor?
- [ ] Epoch - Be honest, you have always wanted an online tool that could help you convert UNIX dates and timestamps!

### Level 5 - Reverse Engineering

Reverse engineering is the art of taking a compiled program and figuring out what it does. This section will teach you everything you need to know about it.

    Windows Reversing Intro - Introduction to reverse engineering x64 Windows software
    Basic Malware RE - This room aims towards helping everyone learn about the basics of Malware Reverse Engineering
    Reversing ELF - A room for beginner Reverse Engineering CTF players to capture the flags
    Dumping Router Firmware - Have you ever been curious about how your router works? What OS it runs? What makes it tick?
    Dissecting PE Headers - Learn about Portable Executable files and how their headers work

### Level 6 - Networking

    What is Networking? - Begin learning the fundamentals of computer networking in this bite-sized and interactive module
    Introduction to Networking - An introduction to networking theory and basic networking tools
    Introduction to LAN - Learn about some of the technologies and designs that power private networks
    Passive Reconnaissance - Learn about the essential tools for passive reconnaissance, such as whois, nslookup, and dig
    Active Reconnaissance - Learn how to use simple tools such as traceroute, ping, telnet, and a web browser to gather information
    Nmap - An in-depth look at scanning with Nmap, a powerful network scanning tool
    Traffic Analysis Essentials - Learn Network Security and Traffic Analysis foundations and take a step into probing network anomalies
    Snort - Learn how to use Snort to detect real-time threats, analyse recorded traffic files and identify anomalies
    Wireshark the Basics - Learn the basics of Wireshark and how to analyse protocols and PCAPs

### Level 7 - Privilege Escalation

Privilege Escalation is where you take a user account and get root/domain admin. It is essential to CTFs and hacking, so let's learn more about how to do it.

    Linux Privilege Escalation - Get hands-on with over 8 different privilege escalation techniques
    Windows PrivEsc - Practice your Windows Privilege Escalation skills on an intentionally misconfigured Windows VM
    Linux PrivEsc Arena - Learn how to escalate privileges using a very vulnerable Linux VM
    Windows Privesc Arena - Learn how to escalate privileges using a very vulnerable Windows 7 VM
    Sudo Security Bypass - A tutorial room exploring CVE-2019-14287 in the Unix Sudo Program. Room One in the SudoVulns Series!
    Sudo Buffer Overflow - A tutorial room exploring CVE-2019-18634 in the Unix Sudo Program. Room Two in the SudoVulns Series!
    Blaster - A blast from the past, let’s look at alternative modes of exploitation
    Ignite - A new start-up has a few issues with its web server
    Kenobi - Enumerate Samba for shares, manipulate a vulnerable version of ProFTPD and escalate your privileges with path variable manipulation
    C4ptur3-th3-Fl4g - A beginner-friendly CTF challenge
    Pickle Rick - A Rick and Morty CTF. Help turn Rick back into a human!

### Level 8 - CTF practice

Here's some CTF practice for you!

Hint: You are allowed to look at walkthroughs for challenge CTFs, however, try to only read what is necessary if you get stuck. And only read the walkthrough if you are really stuck. If you would like a hint without reading a walkthrough, you can ask on our Discord, Subreddit or Forum.

Easy

    Break Out The Cage - Help (Nicolas) Cage bring back his acting career and investigate the nefarious goings-on of his agent!
    Lian Yu - A beginner-friendly security challenge
    B3dr0ck - There’s server trouble in Bedrock
    Committed - One of our developers accidentally committed some sensitive code to our GitHub repository. Well, at least, that is what they told us...
    Cyber Heroes - Want to be a part of the elite club of CyberHeroes? Prove your merit by finding a way to log in!
    Startup - Abuse traditional vulnerabilities via untraditional means

Medium

    VulvNet: Active - VulnNet Entertainment have hired you as a core Penetration Tester. Get full access to the system and compromise the domain!
    Buffer Overflow Prep - Practice stack-based buffer overflows!
    Dogcat - Exploit a PHP application via LFI and break out of a docker container
    Eavesdropper - Listen closely, you might hear a password
    Surfer - Surf some internal webpages to find the flag!
    Ollie - Meet the world's most powerful hacker dog!

### Level 9 - Windows

And finally, Windows practice! Note that Windows machines physically cost more resources to run, so most of the Windows machines are locked behind a subscription.

    Windows Fundamentals 1 - In part 1 of the Windows Fundamentals module, we'll start our journey learning about the Windows desktop, the NTFS file system, UAC, the Control Panel, and more
    Windows Fundamentals 2 - In part 2 of the Windows Fundamentals module, discover more about System Configuration, UAC Settings, Resource Monitoring, the Windows Registry and more
    Windows Fundamentals 3 - In part 3 of the Windows Fundamentals module, learn about the built-in Microsoft tools that help keep the device secure, such as Windows Updates, Windows Security, BitLocker, and more
    Active Directory Basics - This room will introduce the basic concepts and functionality provided by Active Directory
    Blue - Deploy & hack into a Windows machine, leveraging common misconfigurations issues
    Attacktive Directory - 99% of Corporate networks run off of AD. But can you exploit a vulnerable Domain Controller?
    Retro - Can you achieve a new high score?
    Blueprint - Hack into this Windows machine and escalate your privileges to Administrator
    Anthem - Exploit a Windows machine in this beginner-level challenge
    Relevant - Conduct a penetration test on an environment due for release in seven days
    Windows Forensics 1 - Introduction to Windows Registry Forensics
    LocalPotato - Learn how to elevate your privileges on Windows using LocalPotato (CVE-2023-21746)
    PrintNightmare, Thrice! - Search the artifacts on the endpoint to determine if the employee used any of the Windows Printer Spooler vulnerabilities to elevate their privileges

Want More?

Now you will have a good understanding of hacking, all for free! You should now be able to do the easiest challenges quickly, and medium challenges are where you’ll gain the most amount of knowledge.

Completed the free cyber security training above? You can:

    Subscribe to TryHackMe to get paths featuring subscriber-only rooms and access unlimited content. (As Windows uses more resources than Linux, most Windows rooms are subscriber-only. If you want to learn more Windows pentesting, a subscription is a great route to go!)
    Create your own challenge rooms for TryHackMe (check out how to develop rooms)
    Check out our Twitter - new challenge rooms are released weekly!
