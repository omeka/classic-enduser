# Setting Directory Permissions

One of the steps in Omeka's [installation](Installing.md) process is setting the correct permissions on the `files` directory (`archive` in older versions of Omeka). The necessary process for setting permissions can differ significantly between different servers, so it's often best to get specific advice from your hosting provider. This page tries to provide some more general guidance.

The user running the Omeka web process needs **read**, **write**, and **execute** permissions for the file-storage directory and all its subdirectories. 

[File access](https://en.wikipedia.org/wiki/File-system_permissions#Notation_of_traditional_Unix_permissions){target=_blank} works this way:

- One setting for the file's owner
- Another setting for a group of users
- A third setting for every user (the world)

It is often expressed as a ten-letter code - using R, W, and X, for read, write, and execute - that looks like this in some programs or displays:

- `-rwxrwxrwx` (for a file: all three permissions for the user, the group, and the world)
- `drwxr-xr-x` (for a directory: all three permissions for the user, read & execute for the group, read & execute for the world)

It is also expressed as a three-number code that looks like this:

- `755` (all three permissions for the user, read & execute for the group, read & execute for the world)
- `775` (all three permissions for the user, all three permissions for the group, read & execute for the world)

There are three major ways to give the needed permissions. For each option, the names of the permissions needed are provided for use with graphical permissions editors and file transfer programs, and example shell commands are also given for use in SSH.

suExec
-----------------------------------------------------
For servers using **suExec** (your host will be able to tell you if they are using it), the server executes PHP files using your user account's permissions. This often means you don't need to make any changes at all, since you should already have the proper access to the Omeka files that you extracted.

Under suExec, you only need to grant write permissions for the **user**.

Though it's generally not necessary, you can grant these permissions with this shell command: 
```
chmod -R 755 files
```

Group Access
--------------------------------------------------------------

For many other servers, the best option is often to set the directories to a group that Apache belongs to, and then give the group write access to the directories. This option takes a few steps.

1.  Find the correct group to use. Groups vary from server to server, but some common correct groups are `www-data` (the default on Ubuntu and Debian) and `apache` (the default on CentOS). Your host (or distribution if you run your own server) can tell you the right group to use.
2.  Then, set the group for the files directory and all subdirectories. On the shell, you can use this command (where `group-name` is the correct group you just found): 
	```chgrp -R group-name files```
3.  Finally, grant read, write, and execute permissions to the **user** and **group** for the files directory and all subdirectories. On the shell, you can use this command:
	```chmod -R 775 files```

World Access
-----------------------------------------------------
**This is the least secure option. Especially if you are using shared hosting, ask your host for advice before choosing it.**

You can also simply give access to the directories to all users on the system. This option is easy, but be sure to ask your host for advice before you choose it. It can be dangerous to give access to all users, and your host should be able to suggest another option.

This option requires read, write, and execute permissions for the **user**, **group**, and **world**. On the shell, you can use this command:

```
chmod -R 777 files
```