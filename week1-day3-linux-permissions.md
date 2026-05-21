# Task 1 — Learn Permissions

# What are Linux permissions?

Linux permissions control who can:
- read files
- write to files
- execute files/programs

Linux permissions are split into 3 categories:

| Category | Meaning |
|---|---|
| User (u) | The owner of the file |
| Group (g) | Users in the assigned group |
| Others (o) | Everyone else |

---

# rwx Permissions

| Permission | Meaning |
|---|---|
| r | read |
| w | write |
| x | execute |

---

## What does read (r) mean?
Read (r) allows users to view file contents and/or list the contents of a directory.
_______________________________________________________________________

---

## What does write (w) mean?
Write (w) allows users to modify/create files/file data. 
_______________________________________________________________________

---

## What does execute (x) mean?
Execute (x) allows users to run a program, script, and/or navigate through a folder with commands like cd.
_______________________________________________________________________

---

# Example Permission String

```bash
drwxrwxr-x
    d
        #The d in the beginning means that this is a directory. 
    rwx
        #This first rwx represents the owner of the directory, and it indicates that the owner has read, write, and execute priveledges. 
    rwx
        #This second rwx represents the users who belong to the directories assigned group, who have the same permissions as above.
        #Note: This only applies to the users in the directory's assigned group.
    r-x
        #This third clust represents everyone else on the os. Even though they have read and execute permissions, they don't have write permissions. This is shown with the -, as it indicates they don't have permission to write.
-rw-rw-r--
    #This example, the first - represents a file. The first rw- means that the owner only has read and write permissions, not execute permissions, which is the same for second rw-, who is the file's assigned group. The third cluster, r--, indicates that everyone else can only read the file.
```

## Break down the permissions

| Section | Meaning |
|---|---|
| rwx | All permissions, including read, write, and execute.
| r-x | Has permission to read and permission to execute.
| r-- | Only has the permission to read.

---

# Octal Permissions

| Number | Permission |
|---|---|
| 7 | rwx |
| 6 | rw- |
| 5 | r-x |
| 4 | r-- |
| 3 | -wx |
| 2 | -w- |
| 1 | --x |
| 0 | --- |

---

## Common Permission Examples

```bash
chmod 777 file.txt
```

Meaning:
This command line means that we are changing the file permissions to -rwxrwxrwx, which means the owner, group, and others all have read, write, and execute permissions.

---

```bash
chmod 755 script.sh
```

Meaning:
This command line means that we are changing the file permissions to -rwxr-xr-x, which means the owner has read, write, and execute permissions, but the group and others only have read and execute permissions.

---

```bash
chmod 644 notes.txt
```

Meaning:
This command changes the permissions of notes.txt to -rw-r--r--. This signifies that the owner has read and write permissions, while the group and others only have read permissions.
---

# chmod
Change Mode
## What does chmod do?
The chmod command allows you to change the permissions of the owner, group, and others on a file or directory.
_______________________________________________________________________

---

## Symbolic Example
Symbolic permissions let people change the permissions of a file or directory using symbols. They are as follows:

chmod [who][operator][what] file

Who: Specifies who the command targetted towards, u (user/owner), g (group), o (others) or a (all)
Operator: Defines the action wanted, with + for add permissions, - for remove permissions, and = for set exact permissions (overwrites previous settings).
What: Indicates the specified permissions, r for read, w for write, and x for execute.

```bash
chmod u+x script.sh
    #The u in u+x indicates the owner, the + indicates add permission, and the x indicates execute. So in tandem, u+x means add the execute permission for the owner. 
chmod a-w demo.txt
    #The a indicates all users, the - indicates remove permission, and the w indicates write. So in tandem, a-w means remove write permissions for all users.
chmod u=rwx,g=rx,o=r file.txt   
    #This means set the exact permissions to have the owner have read, write, and execute permissions, have the group have read and execute permissions, and others only have the read permission.
chmod ug+rw demo.txt
    #This means have both the owner and group get read and write permissions.
```

What happened?
When I used this command, it would change the permissions that I set for each of the files. One thing I noticed is that when I added the execute permission to a file, it would change from white to green, changing it to an executable or binary, so that is something to keep an eye on in the future.
Note: Adding execute permissions allows the file to be executed if it contains valid executable code or a script. (Graded)

---

## Octal Example

```bash
chmod 755 script.sh
    #The line presented changes the permissions of script.sh to -rwxr-xr-x, which means the owner has read, write, and execute permissions, while the group and others only has read and execute permissions.
chmod 400 demo.txt
    #The line presented changes the permissions of demo.txt to -r--------, which means the owner has permission to read the file, while the group and others have no permissions at all. 
```

What happened?
When I used this command, the same thing happened as before with the symbolic example. It seems this is a more efficent way of changing permissions.

---

# chown
change owner
## What does chown do?
The chown command changes the owner of the file in question to who the command specifies.
_______________________________________________________________________

---

## Example

```bash
sudo chown user file.txt
    #The sudo lets the command be run, the chown command indicates that we want to change the owner of the file, the user is the person we want to be the owner, and the file.txt is the file we want to apply this to.
sudo chown user:user file.txt
    #The user:user indicates that we want to change both the owner and group of the file presented.
```

What happened?
When I did the first example, it let me do it no problem. However, when I tried to execute the second command, it wouldn't let me, saying the group I wished to change didn't exist. This is mainly because there are no groups on my vm, so that is something I will learn later.

---

# sudo
Superuser do
## What does sudo do?
The sudo command allows the user to run programs and actions with the priveledges of the super user. It usually gives you root permissions for a short time, allowing for certain actions to be done to the system. 
_______________________________________________________________________

---

## Why is sudo important?
Sudo is important because it lets someone perform actions that requires the super user (root) without having to log into the super user's account. This can prevent system breaking problems for happening, as it is only in this super user mode for a short period of time.
_______________________________________________________________________

---

## Example

```bash
cd /etc
sudo mkdir newdir
    #When we change directory to the etc directory, we try to make a new directory, but are denied. This is because only the super user has permission to do this. So when we put sudo in front of mkdir newdir, it prompts us with a password, which once entered, allows us to have super user permissions for a short period of time.
    #Note: The cd /etc command is seperate from the sudo mkdir newdir command. 
sudo apt-get install gcc
    #The line presented lets us install applications (for this example gcc), and we need to use the sudo command in order to do this. 
sudo -s
    #The line presented grants you access to be the root user. 
    #Note: starts a shell with root privileges to be technically correct. (graded).
sudo apt update
    #The line presented lets us refresh the local package index by downloadin the latest metadata from software repos (basically, think of it as a soft update, stuff like bug fixes or security patches). 
```

What happened?
When I used the commands, it prompted me with a password first, which was the password to get into the machine to begin with. Once that was done, it would execute the command needed, updating or installing anything that was asked. I still need to learn more about this, as there is still a bunch about this commadn that I don't know. 
_______________________________________________________________________

---

# Task 2 — Practice

# File & Directory Creation

## Commands I used

```bash
mkdir practice
    #Creates a directory named practice.
touch notes.txt
    #Creates a file named notes.txt.
mkdir private-folder
    #Creates a directory named private-folder.
```

What happened?
The commands used created a direcotry named practice, created a file named notes.txt, and a subdirectory named private-folder.
_______________________________________________________________________

---

# User Commands

## whoami

### What does it do?
The whoami command tells you what user you are logged in as. 
_______________________________________________________________________

### Example

```bash
whoami
```

### Result
When inputed, the whoami command outputs what user is currently logged in. In my case, that was vboxuser.
_______________________________________________________________________

---

## id
identify
### What does it do?
The id command tells you the user identity of a specified user/logged in user. This includes their user id (UID), group id (GID), and group memberships.
_______________________________________________________________________

### Example

```bash
id
    #When this command is input with no arguments, it tells you the current user's UID, primary GID, and all group IDs.
id username
    #When this argument is input, it is the same output as above, though now for a specific user.
id -u john
    #When this argument is input, the -u specifies only the UID, and the username, john, is to specify only that user get an id lookup.
id -g johnston
    #When this argument is input, the -g specifies only the GID, and the group name, johnston, is to specify only that group gets an id lookup.
id -r -u john
    #When this argument is input, the -r specifies a real id, the -u specifies only the UID, and the username, john, is to specify only that user get an id lookup.
id -r -g johnston
    #When this argument is input, the -r specifies a real id, the -g specifies only the GID, and the group name, johnston, is to specify only that group gets an id lookup.
id -G
    #When this argument is input, it will display all of the group ids for the current logged in user.
    id -G username
        #Same as above but for a specific user.
id -nu
    #When this argument is input, it will display the current logged in user of your system.
id -ng
    #Same as above but for group name.
id -nG
    #When this argument is input, it will display all the avalible group names.
id -nGz
    #When this argument is input, it will dsiplay all the avalible group names without a space. This is because of the -z (zero), which seperates the output with the NUL character instead of whitespace.
```

### Result
When I inputed these commands, the output that I was told was going to happen did indeed occur. I tried the -l operator out of curiosity, though it didn't work (it brought up an error). 
_______________________________________________________________________

---


## User Management

### What does it do?
The user commands let you create, modify, and delete user accounts.

### Example

```bash
#Important before info
    cat /etc/passwd
        #This file in particular lists all the users on the system.
        #Note: This file will be covered later down the line.
        #Note: stores user account information (Graded)
        cat /etc/passwd | grep username
            #This argument will find the specific user in the file.
        vboxuser : x : 1000 : 1000 : vboxuser : /home/vboxuser : /bin/bash
            #The 1000 after the x: is the user id for vboxuser.
            #Note: When you add a new user to a linux system, it is going to assign the next avalible id to that user. So after this would be 1001.
            #Note: Users that begin with 1000 are human accounts, and anything below 1000 are generally system accounts. 
users
    #This command lists all the users logged into the system. (Graded)
sudo useradd username
    #This command adds a user to your system.
    sudo useradd -m username
        #This command does the same thing as the one above but adds the user to the home directory as well. 
        #Note: Depending on the distro, you may have to use this command to add a directory to home.
    sudo useradd -r username
        #This command allows you to add a system user to your system. 
sudo userdel username
    #This command deletes a user from your system.
    sudo userdel -r username
        #This command does same thing as above though deletes the home directory for the user along with it.
passwd
    #This command lets you change the password for the user you are logged in as.
    sudo passwd username
        #This command lets you chaneg the password for a specific user. 
        #Note: It will not prompt you to enter the old password, as you are logged into the root account because of sudo.
sudo usermod
    #This command lets you modifiy users on your system.
```
### Result
When I input the commands, I was able to run them just as they were shown. When I was changing the password for one of the dummy accounts I created, I made the password just "k" (I obviously wouldn't use this as a real password), and it told me it was a bad password, which was interesting. 
---


## groups

### What does it do?

_______________________________________________________________________

### Example
Note: There are a such thing as group passwords, but it said that it isn't recommended to use them.
```bash
#Important before Info
    cat /etc/group
        #This file in particular lists all the groups in the system.
        demogroup:x:1000
            #The 1000 at the end of this line is the group id (GID).
        demouser:x:1000:1000
            #The final 1000 at the end is the GID of the primary group of the user.
            #Note: A group is only a primary group if it is assigned to a user.
groups
    #This command shows you all of the groups the current user is a member of.
    groups username
        #Does same thing as above, but for a specific user.
sudo groupadd groupname
    #This command adds a group to your system.
sudo groupdel groupname
    #This command deletes a group from your system.
sudo usermod -aG groupname username
    #This argument adds a user to a group. The usermod command modifies a user, the -a notes to append (add), the -G notes groups, the groupname is what group you want to add the user to, and the username is the user you want to add to the group.
    sudo usermod -g groupname username
        #This argument replaces the primary group of a user. It is best not to use this argument though.
sudo gpasswd -a username groupname
    #Does the same thing as the -aG command above.
sudo gpasswd -d username groupname
    #This argument removes a user from a group. This is because of the -d operator, which means delete.
```

### Result
When I input the commands, they worked as they said they would. The only one I had trouble with was the second to last command, as it said permission denied. However, I realized that I forgot to put sudo at the end of it, and it worked the second time I did, so yeah.
_______________________________________________________________________

---
# chmod Practice

## Remove permissions

### Example

```bash
chmod u-r notes.txt
```

What happened?
When this command is executed, the owner of the file lost the read permission.
Note: the owner lost read permission for that file (Graded)
_______________________________________________________________________

---

## Add permissions

### Example

```bash
chmod u+w notes.txt
```

What happened?
When this command is executed, the owner of the file is given the write permission.
_______________________________________________________________________

---

# Switching Users

## Command used

```bash
su username
    #This command allows you to switch to another user during a session. It is usually done to gain root privileges.
    #Note: The su command allows you to switch to another user account during a session. (Graded)
```

What happened?
When I did su zig (zig is the other user I created), it prompted me for it's password, and once entered, switched me to that account. I noticed that the stuff for the $ was gone, and it was just the $, and that once I exited, it went back to normal. 
_______________________________________________________________________

---

# Permission Experiments

## What happened when permissions were removed?
What I noticed is the rwx string had - a lot. I also noticed that when I tried to enter a file without the read permission, I was denied access.
_______________________________________________________________________

_______________________________________________________________________

---

## What happened when permissions were added back?
When I added the permissions back to the file I removed them from, I was able to access them once again. This was expected, as I would be concerned if this wasn't the case.
_______________________________________________________________________

_______________________________________________________________________

---

# Task 3 — Mini Challenge

# Private Folder Challenge

## Step 1 — Create Folder

```bash
mkdir secret-folder
```

Result:
When inputing the command, a directory named secret-folder was made.
_______________________________________________________________________

---

## Step 2 — Remove Other User Access

```bash
chmod 700 secret-folder
```

Result:
Once this command was input, the secret-folder directory had the string drwx------, which indicates that only the owner has access to the folder.

_______________________________________________________________________

---

## Step 3 — Test With Another User

### What happened?
I entered the zig user account I made with the su command, and I was not able to enter the file no matter what I did, but it wasn't in the way I thought it would be. I thought it would be a simple permission denied, but instead it was user /secret-folder does not exist or the user entry does not contain all the required fields. Granted, I tried the expierement first in my home directory (cause I forgot about it) and it didn't work, so I made the same folder in the root directory, in which I entered the zig account and tried to enter it, to only be met with that. I am not really sure if I succeded or not, but I guess I will know later.
Note: After inputting su zig, I should have inputted cd /home/vboxuser/secret-folder, then I would have gotten Permission denied. 
_______________________________________________________________________

_______________________________________________________________________

---

## Why did this happen?
If the way I thought it was supposed to work worked, it was because the owner of the file was the only person granted any permissions to the directory, and no one else was allowed. As for my mishap, this probably happened because I shouldn't really be adding directories or files to the root folder, and that is why the zig account was denied access, not because of the permissions I put on there. But then again, I may have done the permissions like I was supposed to anyway. 
Note: The issue wasn't where the folder was, it was how the directory was being accessed/tested. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

# Important Concepts Learned Today

## Difference between authentication and authorization

Authentication means:
Authentication is the process of proving that you have access to something that you are prevue to, like with a password or something else of the sort. 
_______________________________________________________________________

Authorization means:
Authorization is being allowed into certain files or areas that other people are not, like have permissions to a certain directory or file. 
_______________________________________________________________________

---

## Why are permissions important in cybersecurity?
Permissions are important when it comes to cybersecurity because hackers are always trying to get into places with sensitive information, and some people may not be as trust worthy as others, so only allowing certain people into certain places makes sense when it comes to system wide security. 
_______________________________________________________________________

_______________________________________________________________________

---

# End of Day Reflection

## What command was easiest today?
The command that was the easiest today was definitly whoami, as it was one command and very easy to memorize (it shows what user is logged in currently).
_______________________________________________________________________

---

## What command was hardest today?
I would say the hardest command was definitly some of the sudo commands, as they are meant as system wide commands that access the root user of the system. 
_______________________________________________________________________

---

## What concept confused me the most?
I think the concept that confused me the most was switch users, as it was needlessly complicated for me. It caused me trouble with the third task, and caused needless confusion. However, practice will help with that.
_______________________________________________________________________

---

## What is one important thing I learned today?
One important thing I learned today was users and groups, as it is something that is going to be very important moving forward. 
_______________________________________________________________________

---

## How comfortable do I feel with Linux permissions? (1–10)

Score: 3/10

Why?
I am learning more, yes, but I still have a long ways to go before I can confidently say I am good with linux. Ideally, I want linux to be pure muscle memory, to the point where I don't need to think about any of this stuff and can just use it without problem.
_______________________________________________________________________