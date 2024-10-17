---
layout: post
title: Fix for 'Bad Cipher' Error with OpenVPN and TryHackMe
tags: tryhackme linux openvpn cybersecurity tools
---
Download the OpenVPN config file from TryHackMe. Open it in a text editor.

Add the following line under ```cipher AES-256-CBC```:
```data-ciphers AES-256-CBC```.

Save the file and try again with OpenVPN.

Now I can start the machine in any TryHackMe room and ssh into it from Terminal on Windows. 
E.g., ```sudo ssh tryhackme@10.10.142.22```

Shout out to [u/Horror-Parsnip-4395](https://www.reddit.com/user/Horror-Parsnip-4395/) for posting the answer.
