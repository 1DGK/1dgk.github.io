---
layout: post
title: CNTP - Linux Command Line for Beginners
---
In this section of the Cyber Ninja Training Plan, it's a relatively short course that explains the basics of the Linux command line. 

Here is a link to the [Cyber Ninja Training Plan](https://1drv.ms/x/s!AvDXyd4cgfxegZRq8OELn7MEbxtkkg?e=Ocfhvq). 

Here is a link to the (free) Udemy course, [Linux Command Line for Beginners](https://www.udemy.com/course/linux-command-line-basics/).

---
### My Notes
**Understanding the File System Locations:**

/bin contains binaries (executable files)

/boot contains files required for starting system

/dev contains device files.

/etc/ contains everything to configure

/home contains user accounts personal directories

/lib is where libraries are containing code for applications

/media is where external storage would be mounted.

/mnt is where you would mount storage devices or partitions

/opt is where software usually compiles

/proc/ is information about your computer and CPU / linux kernel 

/root/ is the home directory of the superuser (admin account)

/run/ stores temporary data for other processes

/sbin contains applications for the superuser

/usr/ is a bunch of directories with information relative to applications

/srv is a data area for servers

/sys/ contains information from devices connected to the computer

/tmp/ contains temporary files usually placed by applications

/var/ is where log files typically exist

---
Play around with the following commands: `pwd` `cd` `ls` `file`

Use a wildcard at the end of a command to list everything, e.g.
```sh
$ ls /etc/cron*
```

**File Permissions**

d means it's a directory

`-` means it's a file

rwx: read, write, execute.

User - Group - All Other User Accounts