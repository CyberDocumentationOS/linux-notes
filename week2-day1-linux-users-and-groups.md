# Active Learning Day 1 — Linux Users & Permissions

## Warm-Up (5–10 Minutes)

Complete these commands WITHOUT notes:

```bash
pwd
    #Prints working directory.
ls -la
    #List all contents long ways of a directory, including hidden files.
cd
    #Changes the current working directory to the one specified.
mkdir
    #Creates a directory.
touch
    #Creates a file.
    #Note: Creates an empty file if it doesn't exist OR updates timestamps if it does. (Graded)
rm
    #Removes a file.
        #rmdir removes a directory.
chmod
    #Changes the permissions on a file or directory.
whoami
    #Tells you who is currently logged in.
id
    #Tells you the ids of who is specified (the command by itself displays the ids of the current logged in user).
groups
    #Tells you the groups of who is specified (the command by itself displays the groups of the current logged in user).
    #Note: Displays the groups a user belongs to. (Graded)
```

## Goal
- speed
- confidence
- muscle memory

---

# Task 1 — Deep Dive Into Permissions

# What are Linux permissions?

Linux permissions control:
- who can read files
- who can write files
- who can execute files/programs

---

# Permission Categories

| Category | Meaning |
|---|---|
| User (u) | Owner of the file/directory.
| Group (g) | The group associated with the file/directory.
| Others (o) | Everyone else.

---

# rwx Permissions

| Permission | Meaning |
|---|---|
| r | Read
| w | Write
| x | Execute

---

# Numeric Permissions

| Number | Permission |
|---|---|
| 7 | rwx
| 6 | rw-
| 5 | r-x
| 4 | r--
| 0 | ---

---

# Symbolic Permissions

## Example

```bash
chmod u+x script.sh
```

What happened?
This gave the execute permission to the owner of the script.sh file. 
_______________________________________________________________________

_______________________________________________________________________

---

# Octal Permissions

## Example

```bash
chmod 755 script.sh
```

Breakdown:

| Number | Meaning |
|---|---|
| 7 | rwx
| 5 | r-x
| 5 | r-x

---

# Ownership

## What does ownership mean in Linux?
Ownership is the specific mechanism that assigns a specific user as the owner of every file or directory, determining the permissions of it as well. The owner is usually who created the file/directory (it can be changed with the chown command), and they possess the highest level of control over the item in question.
_______________________________________________________________________

_______________________________________________________________________

---

# File Permissions vs Directory Permissions

## File Permissions

What does execute (`x`) do on a file?
The execute permission lets someone run the file as a program, which is necessary for binary executables and scripts.
_______________________________________________________________________

_______________________________________________________________________

---

## Directory Permissions

What does execute (`x`) do on a directory?
The execute permission lets someone enter the directory and access the files within it. 
_______________________________________________________________________

_______________________________________________________________________

---

# umask
user file-creation mode mask
## What is umask?
Umask is a Linux setting that sets the default permissions for newly created files and directories. 
_______________________________________________________________________

_______________________________________________________________________

---

## Why is umask important?
Umask is important because it allows a secure set up to all newly created files and directories, making sure that only the creator/owner has full permissions to it at first. This allows for the owner of the file/directory to specify who they want to give permissions to or not to avoid incidents in the future.
_______________________________________________________________________

_______________________________________________________________________

---

# ls -l
List long
## What does this command do?

```bash
ls -l
```
The ls -l command lists the contents of a directory long ways, allowing for more infortmation about the contents to be seen such as the owner, permissions, and timestamps.
_______________________________________________________________________

_______________________________________________________________________

---

# Permission Practice

## Commands Used

```bash
touch notes.txt
    #Creates an empty file named notes.txt.
chmod 000 notes.txt
    #Changes the permissions of the file to ----------, meaning that no one has permissions.
chmod 644 notes.txt
    #Changes the permissions of the file to -rw-r--r--, meaning the owner only has read and write permissions while group and others only have read permissions.
chmod u+x notes.txt
    #Changes the permissions of the file to -rwxr--r--, which gives the owner of the file execute permissions.
ls -l
```

---

## What happened when permissions were removed?
When the permissions of the file were removed, I was not able to interact with the file, as when I used `cat notes.txt`, it said permission denied. 
_______________________________________________________________________

_______________________________________________________________________

---

## What happened when permissions were restored?
When permissions were changed to have some again, I was able to interact with the file, being able to use `cat note.txt` once more. 
_______________________________________________________________________

_______________________________________________________________________

---

## Which file became executable?
When the last command, `chmod u+x notes.txt`, was input, it turned the note.txt file into an executable one. 
Note: gave the file execute permissions (Graded)
_______________________________________________________________________

---

# Task 2 — User & Group Management

# useradd

## What does useradd do?
The useradd command adds a user to the system.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
sudo useradd testuser
    #This command adds the user testuser to the system. 
```

What happened?
When I input this command (after it prompted me for the password to use sudo), it added the user to the system.
_______________________________________________________________________

_______________________________________________________________________

---

# passwd

## What does passwd do?
The passwd command lets you change the password for the specified user.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
sudo passwd testuser
    #This command lets you change the password for the user testuser.
```

What happened?
When I inputed this command (after it prompted me for the password to use sudo), it asked me for the new password for the test user I created, then told me to input it again. 
_______________________________________________________________________

_______________________________________________________________________

---

# groupadd

## What does groupadd do?
The groupadd command lets you add a group to the system.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
sudo groupadd sharedgroup
    #This command adds a group named sharedgroup to the system. 
```

What happened?
When I inputted the command (after it prompted me for the password to use sudo), it created the group with the name I specified. 
_______________________________________________________________________

_______________________________________________________________________

---

# usermod

## What does usermod do?
The usermod command allows you to modify existing user attributes, such as what group they are in and home directories. 
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
sudo usermod -aG sharedgroup testuser
    #This command adds the user testuser to the supplementary group sharedgroup.
    -a
        #This flag means append, and adds the user to the group, and not replace their primary group.
    -G
        #This flag indicates that the group is a supplementary group, not primary.
```

What happened?
When I input this command (after sudo), it added the user I specified to the supplementary group I specified. 
_______________________________________________________________________

_______________________________________________________________________

---

# groups

## What does groups do?
The groups command allows you to see what groups a user belongs to.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
groups
    #This command shows the groups that the current user is in.
groups testuser
    #This command shows the groups that the user testuser is in. 
```

Result:
When I input this command, it showed me the groups the users I specified are in. 
_______________________________________________________________________

_______________________________________________________________________

---

# id

## What does id do?
The id command shows the id(s) of the specified user. 
Note: Displays UID, GID, and group memberships. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
id
    #This command shows the id(s) of the current logged in user.
id testuser
    #This command shows the id(s) of the specified user (testuser).
```

Result:
When I input this command, it gave me the id(s) of the user that I specified. 
_______________________________________________________________________

_______________________________________________________________________

---

# su

## What does su do?
The su command lets you switch to another user account or execute commands with another user's priviledges.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
su testuser
    #This command switches the user account to testuser, allowing you to execute commands under this account.
su
    #This command switches to the root user, requiring authentication to use.
```

What happened?
When I input the first command, it prompted me for the specified account's password, and I was able to use their account. When I input the second command, it prompted me for the password once again, but I was unable to get root permissions. After some research, this is because it was asking for the root user's password, which I never set, so it won't let me in. When asked, the internet suggest just using sudo for now, so I will try to figure out a way around it later. 
_______________________________________________________________________

_______________________________________________________________________

---

# Mini Lab — Shared Group Access

# Step 1 — Create Two Users

```bash
sudo useradd user1
sudo useradd user2
```

What happened?
These two commands added the user accounts user1 and user2.
_______________________________________________________________________

_______________________________________________________________________

---

# Step 2 — Create Shared Group

```bash
sudo groupadd projectgroup
```

What happened?
This command added the group projectgroup. 
_______________________________________________________________________

_______________________________________________________________________

---

# Step 3 — Add User To Group

```bash
sudo usermod -aG projectgroup user1
```

What happened?
This command added user1 to the supplementary group projectgroup. 
_______________________________________________________________________

_______________________________________________________________________

---

# Step 4 — Create Shared Folder

```bash
mkdir shared-folder
```

What happened?
This command made the directory shared-folder.
_______________________________________________________________________

_______________________________________________________________________

---

# Step 5 — Change Group Ownership

```bash
sudo chgrp projectgroup shared-folder
    #This command allows someone to assign a specific group, projectgroup, to a file or directory, shared-folder.
```

What happened?
When this command was input, it assigned the group projectgroup to the directory shared-folder.
_______________________________________________________________________

_______________________________________________________________________

---

# Step 6 — Adjust Permissions

```bash
chmod 770 shared-folder
```

What happened?
When this command was input, it changed the permissions of the shared-folder directory to drwxrwx---, which gives the owner and assigned group (projectgroup) read, write, and execute permissions, while others have no permissions. 
_______________________________________________________________________

_______________________________________________________________________

---

# Access Questions

## Which user should have access?
User1 should have access to the shared-folder directory.
_______________________________________________________________________

---

## Which user should NOT have access?
User2 should not have access to the shared-folder directory.
_______________________________________________________________________

---

## Why?
This is because user1 was added to projectgroup and user2 wasn't, and since only the owner and projectgroup have permissions for shared-folder while others have no permissions, only user1 has access to the directory. 
_______________________________________________________________________

_______________________________________________________________________

---

# Task 3 — Notes Review

# users

## What are users in Linux?
Users are the seperate accounts that interact with the linux system. 
Root User: Super user that has full system control.
Regular User: Human accounts with limited permissions.
System User: Non login account used to run background processes.
_______________________________________________________________________

_______________________________________________________________________

---

# groups

## What are groups in Linux?
Groups are collections of users that share the same permissions to certain files and directories. 
_______________________________________________________________________

_______________________________________________________________________

---

# ownership

## Why is ownership important?
Ownership is important because it determines who has access to certain files and who doesn't. Critical system files should only be writable by trusted privileged users like root to avoid having an incident happen. For other files, maybe some people shouldn't be privy to them, so the owner can grant only themself permissions if needed. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

# chmod

## What does chmod do?
The chmod command allows you to change the permissions on a file or directory for the owner, assigned group, and others.
_______________________________________________________________________

_______________________________________________________________________

---

# chown

## What does chown do?
The chown command allows you to change the owner of a file or directory to who you specify. 
_______________________________________________________________________

_______________________________________________________________________

---

# sudo

## Why is sudo important?
Sudo is important because it lets you execute commands that you normally could not. This is because these commands often times require super user (root) priviledges due to their potential system wide nature (though this isn't the case sometimes), and going through the process of logging into the root user is a little much. Sudo allows you to access these priviledges for a short period of time, and allows you to run these commands that you otherwise couldn't.
_______________________________________________________________________

_______________________________________________________________________

---

# umask

## What does umask affect?
Umask affects everyone on the system to a degree, but mainly the owner of the files/directories being made, as setting the umask defaults as something deemed necessary can allow for an easier time setting up permissions.
Note: umask controls default permissions for newly created files and directories. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

# End of Day Reflection

## What command was easiest today?
The command that was the easiest was the groups command, as all you have to do say groups and it lists what groups a user belongs to (technically pwd was easiest but that was for warmup so it doesn't count).
_______________________________________________________________________

---

## What command was hardest today?
I would say the hardest was the chgrp command, as I hadn't used it before and had to look up it's meaning. Once I did, it became self explanatory, but the flags are something I needed to learn to understand their meaning.
_______________________________________________________________________

---

## What concept confused me the most?
I would say the su raw command confused me the most, as I didn't understand why it wasn't working. Once I did figure it out, I realized that it is better for me to use the sudo command instead. 
_______________________________________________________________________

_______________________________________________________________________

---

## What is one important thing I learned today?
I learned that the sudo command is the preferred command by Ubuntu for performing root permissions and such, as logging in as the root user is generally not preferred and can be troublesome overall. 
_______________________________________________________________________

_______________________________________________________________________

---

## How comfortable do I feel with Linux permissions and users/groups? (1–10)

Permissions and user/groups score: 6.7/10
Score: 4/10

Why?
I am getting to the point to where I rarely mess up on permissions and other commands like that, and the basic navigation commands are becoming much easier at this point. With that said, I am far from a linux master, as I am sure there a lot more permission commands and concept that are more advanced, so I need to learn all of those before I feel confident enough for a professional setting. I am hopeful I will improve with time, and become better because of it. 
_______________________________________________________________________

_______________________________________________________________________
