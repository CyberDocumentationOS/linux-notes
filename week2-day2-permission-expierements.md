# Active Learning Day 2 — Linux Permissions & Experiments

## Warm-Up — 5 Minute Permission Drill

Translate these permissions mentally before checking your answer.

---

## chmod 755

```bash
chmod 755 script.sh
```

### Permission String
-rwxr-xr-x
__________________________________

### Meaning

Owner: read, write, and execute
__________________________________

Group:read and execute
__________________________________

Others:read and execute
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
This gave the owner of the script.sh file execute permissions.
_______________________________________________________________________

_______________________________________________________________________

---

## chmod go-rwx

```bash
chmod go-rwx private.txt
    #-rwx------
```

### What happened?
This removed the read, write, and execute priviledges for the group and others.
_______________________________________________________________________

_______________________________________________________________________

---

# Permission Translation Practice

## Translate This Permission String

```bash
rwxr-xr-x
```
755

Owner: read write and execute
__________________________________

Group: read and execute
__________________________________

Others: read and execute
__________________________________

---

## Translate This Permission String

```bash
rw-r--r--
```
644
Owner: read and write
__________________________________

Group: read
__________________________________

Others: read
__________________________________

---

## Translate This Permission String

```bash
rwx------
```
700
Owner: read, write, and execute
__________________________________

Group: none
__________________________________

Others: none
__________________________________

---

# Task 1 — TryHackMe Notes

# Linux Fundamentals Part 2

## Important Concepts Learned

### ssh
SSH (Secure Shell) is a protocol between devices in an encrypted form. It allows us to remotely enter linux systems and execute commands from another device. 
Note: SSH is an encrypted remote access protocol. (Graded)
Note: There are more concept with ssh that will be covered later on. 
_______________________________________________________________________

_______________________________________________________________________

---

### Basic navigation (Filesystem Interaction, common directories, flags and switches).
These concepts boiled down to basic navigation of the linux enviroment. 
_______________________________________________________________________

_______________________________________________________________________

---

### Permissions
This section focused on rwx permissions and how the numbering system works, along with the su command. 
_______________________________________________________________________

_______________________________________________________________________

---

# Commands I Practiced

```bash
ssh username@10.65.156.219
    #This command lets you login remotely to a linux system, allowing us to input commands on the system remotely.
    #The "username" signifies what user we want to login as, and "10.65.156.219" is the ip address of the system we want to login to.
Man
    #This command gives you a manual for said command.
Unassociated flags
    -h
        #This flag will give the contents in a human-readable format.
ls
    ls -a
        #Displays all the contents, including the hidden files.
    ls --help
        #This command lists the possible option the command accepts.
    ls -lh
        #This command lists the contents of the directory long ways and does so in human readable format.
touch
    #Creates file.
mkdir
    #Makes directory.
cp
    #Copy a file or folder.
mv
    #Move a file or folder.
rm
    #Remove a file or folder (for folders, use rm -r or rmdir).
file
    #This command determines the type of a file. 
    file note
        #This command tells else what type of file note is. 
su
    #Switches user (substitute user).
    su -l user
        #This command lets us go to the user's (user), home directory automatically.

```

---

# What command confused me the most?
The command that confused me the most was su -l, as I didn't understand it at first. However, after looking at it fully, I understand it now. 
_______________________________________________________________________

_______________________________________________________________________

---

# What command felt easiest?
Definitely all the system navigation commands, as since they were all already familiar, I had no trouble with them. 
_______________________________________________________________________

_______________________________________________________________________

---

# Task 2 — Permission Experiments

# Private Directories

## Commands Used

```bash
mkdir private-folder
chmod 700 private-folder
ls -ld private-folder
    #This command list the metadata of the directory itself long ways.
```

---

## What happened?
The first command made the directory private-folder, with the second command changing the permissions to have only the owner have read, write, and execute permissions, and the last command lets you see the permission string of the directory (along with the other metadata).
_______________________________________________________________________

_______________________________________________________________________

---

## What permissions did the directory have?
drwx------
Owner: Read, Write, and Execute.
Group: None
Other: None
__________________________________

---

## Who could access the directory?
Only the onwer of the directory could access it.
_______________________________________________________________________

_______________________________________________________________________

---

# Shared Directories

## Commands Used

```bash
mkdir shared-folder
chmod 770 shared-folder
ls -ld shared-folder
```

---

## What happened?
The first command made the shared-folder directory, with the second command changing the permissions of the directory to have both owner and group have read, write, and execute permissions while others had no permissions. The last command lets you see the permission string of the directory (along with the other metadata).
_______________________________________________________________________

_______________________________________________________________________

---

## What permissions did the directory have?
drwxrwx---
Owner: Read, write, execute
Group: Read, write, execute
Other: none
__________________________________

---

## Who could access the directory?
Only the owner and group assigned to the directory could access it's contents. 
_______________________________________________________________________

_______________________________________________________________________

---

# Executable Scripts

## Commands Used

```bash
touch script.sh
chmod u+x script.sh
ls -l script.sh
```

---

## What happened?
The first command created the file script.sh, and the second command gave execute permissions to the owner of the file. The last command lets you see the permission string of the directory (along with the other metadata).
_______________________________________________________________________

_______________________________________________________________________

---

## What permission was added?
The execute permission.
__________________________________

---

## Why are executable permissions important?
Executable permissions are important because sometimes a script/application isn't finished and needs further testing, so only allowing the owner to execute it can provide certain incidents from happening. 
_______________________________________________________________________

_______________________________________________________________________

---

# Read-Only Files

## Commands Used

```bash
touch notes.txt
chmod 444 notes.txt
ls -l notes.txt
```

---

## What happened?
The first command created the file notes.txt, with the second command giving the owner, group, and others just read permissions. The last command lets you see the permission string of the directory (along with the other metadata).
_______________________________________________________________________

_______________________________________________________________________

---

## What permissions did the file have?
-r--r--r--
Owner: Read
Group: Read
Others: Read
__________________________________

---

## Could the file be modified?

Why or why not?
With the current permissions, the file is not able to be modified. In order for the file to be modified, the write permission would be needed. 
_______________________________________________________________________

_______________________________________________________________________

---

# chmod 000 Experiment

## Commands Used

```bash
touch file.txt
chmod 000 file.txt
cat file.txt
ls -l file.txt
```

---

## What happened after removing all permissions?
After removing all the permissions from the file, it was unaccessible, not being able to be seen, modified, or executed. 
Note: The file became inaccessible. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

## What error message appeared?
The error message "permission denied" appeared when I tried to view the contents of the file. 
_______________________________________________________________________

_______________________________________________________________________

---

## What did the permission string become?
----------
__________________________________

---

## Why is chmod 000 important to understand?
It is important to understand because it shows what absolutely no permissions looks like, and how some files are best to have those permissions (at least for a short period of time). 
_______________________________________________________________________

_______________________________________________________________________

---

# Important Permission Concepts

# What is the difference between file permissions and directory permissions?
File permissions determine who can read, write, and execute a file, while directory permissions determine who can enter, modify, and view contents of a directory. 
_______________________________________________________________________

_______________________________________________________________________

---

# Why are Linux permissions important in cybersecurity?
Linux permissions are important in cybersecurity because some things need restricted access, while others can have anyone access. Permissions help decide who can see what on a system, which is something that is intertwined with cybersecurity as a whole.
_______________________________________________________________________

_______________________________________________________________________

---

# Why should users avoid giving 777 permissions to everything?
777 permissions mean that anyone can access the file/directory, meaning they can modify or even delete it if they want. There are some files that are best not tampered with, and having 777 permissions on files like that can lead to incidents happening on the system. 
_______________________________________________________________________

_______________________________________________________________________

---

# End of Day Reflection

## What concept made the most sense today?
The permissions concept made the most sense to me, as it makes sense to restrict the actions of certain people if needed (plus I have been practicing it these past few days, so I am getting pretty used to them at this point).
_______________________________________________________________________

_______________________________________________________________________

---

## What concept confused me the most today?
The concept that confused me the most was the theory part of ssh, as it seems like something that I won't be using at the moment, and something that I am gonna need to commit to muscle memory in the near future. I also had trouble understand the definition of the -ld flag, as although it is simple enough, the wording made me a little confused.
_______________________________________________________________________

_______________________________________________________________________

---

## What is one thing I improved at today?
One thing I improved on today is nailing down on permissions, as I am starting to easily be able to dicipher permission strings easily, and know the outcome of every chmod argument I see. 
_______________________________________________________________________

_______________________________________________________________________

---

## How comfortable do I feel translating permissions mentally? (1–10)

Permissions: 6.8/10
Linux: 4/10

Why?
Basic rwx permissions are becoming second nature to me at this point, as I don't need to dicipher some like 755 anymore using notes, and can read permission strings just fine. With that said, I am sure there are more complicated permission commands I am yet to learn, so saying I am 10/10 confident is a bit cocky. I am getting more familiar to linux by the day, but I have a long way to go before I can say I am not a beginner.
_______________________________________________________________________

_______________________________________________________________________
