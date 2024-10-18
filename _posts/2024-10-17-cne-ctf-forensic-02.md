---
layout: post
title: CnE CTF 2024 - Forensic 02 - WGet The Giant 1
---
QUESTION:
I found a sorcerer book (SorcererBook-1.pcapng). Can you find its secret?
What is the IP address and the port used by the web server?

File: 
SorcererBook-1.pcapng

Format: 
CnE{###.###.#.##:####}

Rewards:
* 50 Experience

---
Copilot:
Download Wireshark

Step-by-Step Guide
Open Wireshark: Launch Wireshark on your Windows machine

Load the pcapng file: Go to File > Open and select the pcapng file you downloaded

Filter HTTP Traffic: In the Wireshark filter bar, type http and press Enter. This will filter the packets to show only HTTP traffic.

Identify the Web Server: Look for packets with the GET or POST method. These packets will show the IP address and port of the web server.

Extract IP Address and Port: Click on one of the HTTP packets, and in the packet details pane, look for the Source and Destination fields. The Source IP address and port will be the client's information, while the Destination IP address and port will be the web server's information.

**Host: 192.168.1.21:8000\r\n**