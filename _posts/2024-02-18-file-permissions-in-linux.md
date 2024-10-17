---
layout: post
title: How to Manage File Permissions in Linux
---    
### Description
Examine existing permissions on the file system. Determine if the permissions match the authorization that should be given. If they do not match, modify the permissions to authorize the appropriate users and remove any unauthorized access. 

```bash
researcher2@dc84eabb7540:~/projects$ ls -al
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Feb 20 22:12 .
drwxr-xr-x 3 researcher2 research_team 4096 Feb 20 23:19 ..
-rw--w---- 1 researcher2 research_team   46 Feb 20 22:12 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Feb 20 22:12 drafts
-rw-rw-rw- 1 researcher2 research_team   46 Feb 20 22:12 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Feb 20 22:12 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Feb 20 22:12 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Feb 20 22:12 project_t.txt
```
**reseach_team** is the group that owns the files in the projects directory.

### Change file permissions
**project_k** grants other users write permissions. Let's change that:

```bash
researcher2@dc84eabb7540:~/projects$ sudo chmod o-w project_k.txt
researcher2@dc84eabb7540:~/projects$ ls -l
total 20
drwx--x--- 2 researcher2 research_team 4096 Feb 20 22:12 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Feb 20 22:12 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Feb 20 22:12 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Feb 20 22:12 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Feb 20 22:12 project_t.txt
```
Notice the w is now removed from the other section of the permission string for the project k file. 

### Change file permissions on a hidden file
Change the permissions of the file .project_x.txt so that both the user and the group can read, but not write to, the file.

```bash
researcher2@dc84eabb7540:~/projects$ sudo chmod u-w,g+r,g-w .project_x.txt 
researcher2@dc84eabb7540:~/projects$ ls -al
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Feb 20 22:12 .
drwxr-xr-x 3 researcher2 research_team 4096 Feb 20 23:19 ..
-r--r----- 1 researcher2 research_team   46 Feb 20 22:12 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Feb 20 22:12 drafts
-rw------- 1 researcher2 research_team   46 Feb 20 22:12 project_k.txt
-rw------- 1 researcher2 research_team   46 Feb 20 22:12 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Feb 20 22:12 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Feb 20 22:12 project_t.txt
```