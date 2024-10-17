---
layout: post
title: How to Install Docker Desktop in Ubuntu Linux
---

```bash
sudo apt install gnome-terminal

sudo apt-get update

sudo apt-get install ca-certificates curl

sudo install -m 0755 -d /etc/apt/keyrings

sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc

sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
```
Download the latest deb package.

Install the package with:
```bash
sudo apt-get install ./docker-desktop-<version>-<arch>.deb
```
Then run docker desktop through the apps menu in Ubuntu, or with this command:
```bash
systemctl --user start docker-desktop
```
