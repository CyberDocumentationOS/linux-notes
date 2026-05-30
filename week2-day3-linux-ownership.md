# Active Learning Day 3 — Ownership & sudo Notes

# Warm-Up — Ownership + Permission Drill

Translate these mentally before checking yourself.

---

## chmod 700

```bash
chmod 700 private-folder
```

### Permission String
drwx------
__________________________________

### Meaning

Owner: read, write, execute
__________________________________

Group: none
__________________________________

Others: none
__________________________________

---

## chmod 770

```bash
chmod 770 shared-folder
```

### Permission String
drwxrwx---
__________________________________

### Meaning

Owner: read, write, execute
__________________________________

Group: read, write, execute
__________________________________

Others: none
__________________________________

---

## chmod 644

```bash
chmod 644 notes.txt
```

### Permission String
-rw-r--r--
__________________________________

### Meaning

Owner: read and write
__________________________________

Group: read
__________________________________

Others: read
__________________________________

---

## chmod u+x

```bash
chmod u+x script.sh
```

### What happened?
The owner of the script.sh file was given execute permissions.
_______________________________________________________________________

_______________________________________________________________________

---

## chown

```bash
sudo chown user:user file.txt
```

### What happened?
The owner and group of file.txt were changed to user and user.
Note: The ownership of file.txt was changed so both the user owner and group owner became user. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

## chgrp

```bash
sudo chgrp sharedgroup folder
```

### What happened?
The group of the directory folder was changed to sharedgroup.
_______________________________________________________________________

_______________________________________________________________________

---

# Task 1 — Learn More About sudo

# sudo

## What does sudo do?
The sudo command allows you to gain elevated (root) permissions for a short period of time.
_______________________________________________________________________

_______________________________________________________________________

---

## Why is sudo important?
Many commands require root permissions to execute, and logging into root the long way is clunky, so being able to quickly get permissions for a short time to execute a command or two is much more convient (plus most debian systems only let you use sudo by default as it is the preferred way to get root priviledges).
_______________________________________________________________________

_______________________________________________________________________

---

# sudo -l

## What does this command do?

```bash
sudo -l
```
This command lists all the commands the current user is allowed or not allowed to do with these root priviledges.
Note: lists which commands the current user is allowed to run via sudo (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

## What information did it show?
The information shown is as such: 
User vboxuser may run the following commands on Ubuntu:
(ALL : ALL) ALL
_______________________________________________________________________

_______________________________________________________________________

---

# visudo

## What does visudo do?
The visudo command allows you to safely edit the /etc/sudoers file, which determines who can execute commands with elevated permissions.
_______________________________________________________________________

_______________________________________________________________________

---

## Why is visudo safer than editing sudoers directly?
Visudo is safer that editing the file directly because the command validates syntax and permforms sanity check before saving any changes, which prevents configuration errors that lock people out of sudo access.
_______________________________________________________________________

_______________________________________________________________________

---

# /etc/sudoers

## What is the sudoers file?
The sudoers file is a configuration file that determines what users/groups can execute commands with elevated permissions (root/sudo users).
_______________________________________________________________________

_______________________________________________________________________

---

## Why is sudoers important in cybersecurity?
This file in important in cybersecurity because it determines who has access to sudo permissions and who doesn't, locking people from using certain commands that are system altering. 
_______________________________________________________________________

_______________________________________________________________________

---

## Why can bad sudo configuration become dangerous?
Bad sudo configuration is dangerous because not only could it let bad actors gain power on the system/server, it can also cause configuration errors, leading to admins locked out of sudo priviledges.
_______________________________________________________________________

_______________________________________________________________________

---

# Practice Commands

## Commands Used

```bash
sudo -l
    #This command lists all the commands the current user is allowed or not allowed to do with these root priviledges.
    #Note: lists which commands the current user is allowed to run via sudo (Graded)
sudo visudo
    #This command lets you safely edit the /etc/sudoers file.
cat /etc/sudoers
    #This command lets you view the contents of the /etc/sudoers file, which shows what users/groups can execute commands with elevated permissions (root/sudo users).
    #Note: You need sudo to run this command.
```

---

## What happened?
When I input the first command, it said I had all of the sudo permissions for the user I was logged in as, and when I input the second command, it entered the visudo editor, which allows you to edit the /etc/sudoers file. When I input the third command (after using sudo of course), it showed me the contents of the /etc/sudoers file.
_______________________________________________________________________

_______________________________________________________________________

---

# Task 2 — Ownership Practice

# chown
Change owner
## What does chown do?
The chown command changes the owner of the file/directory to the specified user.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
sudo chown user:user file.txt
```

### What happened?
This command changes the owner and the assigned group of file.txt to the owner user and the group user.
_______________________________________________________________________

_______________________________________________________________________

---

# chgrp
Change group
## What does chgrp do?
The chgrp command changes the assigned group of a file/directory to the one specified. 
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
sudo chgrp sharedgroup file.txt
```

### What happened?
When this command is input, it changes the assigned group of file.txt to sharedgroup.
_______________________________________________________________________

_______________________________________________________________________

---

# Ownership Practice Lab

## Commands Used

```bash
mkdir ownershiplab
cd ownershiplab

touch notes.txt
touch script.sh
touch private.log

ls -l
```

---

## What happened?
What this set of commands does is create a directory named ownershiplab, make that the current working directory, and create the files notes.txt, script.sh, and private.log. The last command lists the contents of the directory long ways.
_______________________________________________________________________

_______________________________________________________________________

---

# Reading Ownership

## Example Output

```bash
-rw-r--r-- 1 user sharedgroup 0 May 28 12:00 notes.txt
```

### Owner
User
__________________________________

### Group
sharedgroup
__________________________________

### Permissions
Read and write for owner, read for group, and read for others.
__________________________________

---

# Recursive Ownership Changes

## Example

```bash
sudo chown -R user:user ownershiplab
```

### What does `-R` mean?
The -R option means to not only change the owner of this directory, but every file and subdirectory within it.
_______________________________________________________________________

_______________________________________________________________________

---

## What happened?
The owner of the whole directory and the assigned group of the whole directory were changed to the owner user and the group user. This means every file and subdirectory within the directory are owned by user and the assigned group to all of them is user.
_______________________________________________________________________

_______________________________________________________________________

---

# Task 3 — Mini Ownership Challenge

# Private Folder

## Commands Used

```bash
mkdir private-folder
chmod 700 private-folder
```

---

## What permissions did it have?
drwx------
Owner: Read, Write, and Execute
Group: None
Others: None
__________________________________

---

## Who could access it?
Only the owner of private-folder could access it.
_______________________________________________________________________

_______________________________________________________________________

---

# Shared Folder

## Commands Used

```bash
mkdir shared-folder
chmod 770 shared-folder
```

---

## What permissions did it have?
drwxrwx---
Owner: Read, Write, and Execute
Group: Read, Write, and Execute
Others: None
__________________________________

---

## Who could access it?
The owner and assigned group have access to the directory, and only them. 
_______________________________________________________________________

_______________________________________________________________________

---

# Read-Only File

## Commands Used

```bash
touch readonly.txt
chmod 444 readonly.txt
```

---

## What permissions did it have?
-r--r--r--
Owner: Read
Group: Read
Others: Read
__________________________________

---

## Could the file be modified?

Why or why not?
With the current permissions set, no it can not be modifed, because the file for everyone only has read permissions. If the permisions were changed to allow write permissions, then yes it could be modified, but only under those conditions. 
_______________________________________________________________________

_______________________________________________________________________

---

# Verification Commands

## Commands Used

```bash
ls -l
ls -ld
```

---

## What is the difference between `ls -l` and `ls -ld`?
The ls -l command lists the contents of the directory long ways, while the ls -ld command list the directory itself long ways. 
_______________________________________________________________________

_______________________________________________________________________

---

# Important Ownership Concepts

# What is the difference between ownership and permissions?
Ownership is who has access to the file/directory in question, while permissions determines the actions people are allowed to do. This is important because the owner may have certain priviledges that others don't, so being able to specify this is important. 
_______________________________________________________________________

_______________________________________________________________________

---

# Why are ownership and permissions important in cybersecurity?
Ownership and permissions are important in cybersecurity because it determines who has access to the object in question and who can modify the object in question. There are certain people how are allowed to modify existing files and directories, while others are not, which is something that should be specified to the system. 
_______________________________________________________________________

_______________________________________________________________________

---

# Why should users avoid using sudo carelessly?
Using sudo carelessly could lead to incidents on the system, like configuration malfuctions and other such errors.
_______________________________________________________________________

_______________________________________________________________________

---

# End Of Day Reflection

## What concept felt easiest today?
The ownership concept was the easiest, as it is something that is pretty simple at the end of the day. 
_______________________________________________________________________

_______________________________________________________________________

---

## What concept confused me the most today?
Definitly visudo, as when I was using the tool, it was difficult to understand how to use it (I couldn't even figure out how to exit it). It is something that I for sure need to practice.
_______________________________________________________________________

_______________________________________________________________________

---

## What is one important thing I learned today?
The most important thing I learned today was the sudo concpets, as it is something that adminstators use often. I think learning more about how to use sudo would help greatly with administration tasks in the future.
_______________________________________________________________________

_______________________________________________________________________

---

## How comfortable do I feel reading Linux ownership and permissions? (1–10)

Ownership and permissions: 7/10
Linux in general: 4/10

Why?
I think from a conceptional standpoint, I understand permissions and ownership farely well now, as it no longer feels like I need to learn the basic essentials of permissions, and that everything else that is new is just an option or a minor detail. From a practical standpoint, I still need work, yes, as there are plently of commands and tools I need to learn in order to be fully confident with it. This is even more true for linux as a whole, as there are whole sectors that I haven't even touched yet, but I with time, I will definitly learn more.
_______________________________________________________________________

_______________________________________________________________________
