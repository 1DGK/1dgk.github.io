---
layout: post
title: How to Add Plex Libraries in Linux
---
Go to the parent folder or directory, in my case it's
```bash
dgk@dgk-desktop:/media$
```
Notice the permissions:
```bash
dgk@dgk-desktop:/media$ ls -al
total 12
drwxr-xr-x   3 root root 4096 May 12 10:54 .
drwxr-xr-x  23 root root 4096 May 12 10:40 ..
drwxr-x---+  3 root root 4096 May 12 11:48 dgk
```

Then use the chmod command to give access to others:
```bash
dgk@dgk-desktop:/media$ sudo chmod 755 dgk/
```
Notice how the permissions changed:
```bash
dgk@dgk-desktop:/media$ ls -al
total 12
drwxr-xr-x   3 root root 4096 May 12 10:54 .
drwxr-xr-x  23 root root 4096 May 12 10:40 ..
drwxr-xr-x+  3 root root 4096 May 12 11:48 dgk
```
That simple command opens up the folder so Plex can see it. Happy streaming!