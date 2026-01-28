---
layout: post
title: How to Connect to TryHackMe with OpenVPN
tags: tryhackme linux openvpn cybersecurity
---
It's a simple process. I followed the steps outline in the free room at TryHackMe called [OpenVPN](https://tryhackme.com/room/openvpn). Here is how I connected to TryHackMe's servers through Linux:

Go to TryHackMe's [access page](https://tryhackme.com/access). 

Download the configuration file from the server closest to you. E.g., I'm in Canada, so I picked the only US server available.

Install OpenVPN
```sh
sudo apt install openvpn
```

Run the config file that you downloaded
```sh
sudo openvpn [filename.ovpn]
```

Refresh the access page and confirm you're connected with a green checkmark under OpenVPN Access Details.

Then verify you're connected by starting a TryHackMe machine and punching the machine's IP address into your web browser. If successful, you'll get a happy response from OpenVPN.

---

To start the service again, just run that second bit of code.