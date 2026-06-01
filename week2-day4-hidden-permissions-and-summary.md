# Active Learning Day 4 — Linux Permissions, Processes & Mini Project

## Goal

Practice:
- processes
- permissions
- ownership
- logs
- monitoring
- hidden Linux permission concepts
- verification/testing

**Estimated Time:** 45–75 minutes

---

# Warm-Up — Command Recall

Complete WITHOUT notes.

---

## ps aux

### What does this command do?
This command shows every running process on the system. 
_______________________________________________________________________

_______________________________________________________________________

---

## top

### What does this command do?
This command brings up a real time system monitoring tool that displays running processes and system resource usage.
_______________________________________________________________________

_______________________________________________________________________

---

## kill

### What does this command do?
This command terminates a process. 
_______________________________________________________________________

_______________________________________________________________________

---

## killall

### What does this command do?
This command terminates all processes with the name specified. 
_______________________________________________________________________

_______________________________________________________________________

---

## chmod 700

### Permission String
rwx------
__________________________________

### Meaning

Owner: read, write, and execute
_______________________________________________________________________

Group: none
_______________________________________________________________________

Others: none
_______________________________________________________________________

---

## chmod 770

### Permission String
rwxrwx---
__________________________________

### Meaning

Owner: read, write, and execute
_______________________________________________________________________

Group: read, write, and execute
_______________________________________________________________________

Others: none
_______________________________________________________________________

---

## chmod 644

### Permission String
rw-r--r--
__________________________________

### Meaning

Owner: read and write
_______________________________________________________________________

Group: read
_______________________________________________________________________

Others: read
_______________________________________________________________________

---

## chown
change owner
### What does this command do?
This command changes the owner of a file/directory (can also change the assigned group) to the one specified.
_______________________________________________________________________

_______________________________________________________________________

---

## chgrp

### What does this command do?
This command changes the assigned group of a file/directory to the one specified.
_______________________________________________________________________

_______________________________________________________________________

---

## groups

### What does this command do?
This command list the groups of the user specified.
_______________________________________________________________________

_______________________________________________________________________

---

## id

### What does this command do?
This command lists the UID (User id) GIDs (Group ids) the user specified has.
_______________________________________________________________________

_______________________________________________________________________

---

# Task 1 — Hidden Permission Concepts

## Sticky Bit

### What is the Sticky Bit?
The sticky bit is a special permissions flag that is specific to directories that restrict file deletion or renaming. 
_______________________________________________________________________

_______________________________________________________________________

---

### Why does it exist?
The sticky bit exists to prevent specific actions from happening in directories, without having to restrict access to it completely. 
_______________________________________________________________________

_______________________________________________________________________

---

### Example Command

```bash
chmod +t sharedfolder
    #When this command is input, it prevents file deletion and renaming on the specifc directory.
    #Permission String is drwxrwxr-t.
    #Note: It prevents users from deleting or renaming files they do not own. (Graded)
```

### What happened?
When I input this command, it made it so I couldn't remove or rename files in the directory I specified. When I did su and tried to remove the file, it said permission denied, not allowing me to. 
_______________________________________________________________________

_______________________________________________________________________

---

## SUID (Set User ID)

### What is SUID?
SUID is a permission that allow executable files to run with priviledges of the owner of the file.
_______________________________________________________________________

_______________________________________________________________________

---

### Why does it exist?
SUID exists because some executables require temporary elevated priviledges to run. 
_______________________________________________________________________

_______________________________________________________________________

---

### Example Command

```bash
chmod u+s file
    #When this command is input, it gives the file "file" the SUID permission, which allows the file to run with the priviledges as the file owner. 
    #Permission string is -rwSrw-r--.
    #Note: SUID only matters on executable files. S if it is not executable, s if it is. (Graded)
```

### What happened?
When I input this command, it added the SUID permission to the file I specified. 
_______________________________________________________________________

_______________________________________________________________________

---

### Why can SUID be dangerous?
Because the owner's permissions are usually different than the permissions of others, which this permission allows others to run as. If a file had the owner as the root user, that mean everyone running it would temporarily gain root priviledges, which is not ideal. 
_______________________________________________________________________

_______________________________________________________________________

---

## SGID (Set Group ID)

### What is SGID?
SGID is a permission that allow executable files to run with priviledges of the group assigned to a file, and allows directories to have anything created in it automatically gain the group ownership that the directory has as well. 
_______________________________________________________________________

_______________________________________________________________________

---

### Why does it exist?
SGID mainly exists to have everything within a directory automatically be owned by the assigned group, rather than having to manually input the permissions by hand. 
_______________________________________________________________________

_______________________________________________________________________

---

### Example Command

```bash
chmod g+s sharedfolder
    #When this command is input, it gives the sharedfolder directory the SGID permission, which allows the assigned group that owns the directory to own everything within it as well. 
    #Permission string is drwxrwsr-t.
```

### What happened?
When I input the command above, it gave the directory that I specified the SGID permissions. 
_______________________________________________________________________

_______________________________________________________________________

---

### What does SGID do on directories?
SGID permissions allow the assigned group that owns the directory to own everything within it as well.
_______________________________________________________________________

_______________________________________________________________________

---

# Viewing Special Permissions

## Command Used

```bash
ls -l
```

### What did you notice?
I noticed that the permission strings for the files modified had special permissions I hadn't seen before this task, like s and t. 
Note: Out of curiosity, I gave the owner and others on the directory I modified SUID permissions as well, which it did add to them. I also tried the same with SGID on the file I used, but it didn't work, so I guess it's SUID on files only. 
_______________________________________________________________________

_______________________________________________________________________


---

# Task 2 - Week 2 Reflection

# Permissions

## What permission concept do I understand best?
When it comes to permissions, the rwx permissions are what I understand the best, as I have had so much practice with them, it is second nature to me now. 
_______________________________________________________________________

_______________________________________________________________________

---

## What permission concept still needs work?
The permission concept I still need practice with is SUID and SGID, as I need to learn to intergrate them naturally into my learning rather than just practicing the commands. 
_______________________________________________________________________

_______________________________________________________________________

---

# Ownership

## What did I learn about ownership?
I've learned what ownership really means and why it is so important when it comes to cybersecurity (it determines who should have access to certain objects and who shouldn't).
_______________________________________________________________________

_______________________________________________________________________

---

# Users & Groups

## What did I learn about users and groups?
I learned more about how users and groups are utilized, and how ids work on a practical level. 
_______________________________________________________________________

_______________________________________________________________________

---

# sudo

## What did I learn about sudo?
I leared that sudo is not only important when performing certain tasks, but it is actually preferred by the distros themselves.
_______________________________________________________________________

_______________________________________________________________________

---

# Logs

## Why are logs important?
Logs are important because they track what has happened on the system, and they can help with problem solving things like system crashes and misconfigurations. 
_______________________________________________________________________

_______________________________________________________________________

---

# Cybersecurity Connection

## Why are permissions important in cybersecurity?
Permissions determine the extent of what can happen to a file/directory, and who is allowed to interact with said file/directory. It is imperative that certain people has access to certain things, and permissions is how that is moderated.
_______________________________________________________________________

_______________________________________________________________________

---

## Why can bad sudo configurations be dangerous?
Bad sudo configuration can be dangerous because it can mess with system configurations, leading to system errors and potentionally locking administrators out of important areas.
_______________________________________________________________________

_______________________________________________________________________

---

## Why can SUID become a security risk?
SUID can be a security risk because it essentially allows everyone to run the specified executable with elevated priviledges, which people can take advantage of if they like. 
_______________________________________________________________________

_______________________________________________________________________

---

# End of Day Reflection

## What command was easiest today?
The ls -l command was the easiest today, as it is one I am quite comfortable with at this point. 
_______________________________________________________________________

---

## What command was hardest today?
The SUID and SGID commands were so much as "hard", but more so conceptally complex, as they are commands that I am going to need later down the line when I start writing scripts and such, but it isn't something that I am going to use all that often as of now.
_______________________________________________________________________

---

## What concept confused me the most?
The SGID concept was a little confusing, as I thought it was pecuilar that it runs executables with group permissions and lets every file created in a directory automatically be owned by the group of the directory, those are two completely different things. 
_______________________________________________________________________

_______________________________________________________________________

---

## What is one important thing I learned today?
I learned about hidden permissions, which is very important, as it finally breaks away from normal rwx permissions and onto other specific permissions. 
_______________________________________________________________________

_______________________________________________________________________

---

## Confidence Score (1–10)

Score: 4/10

### Why?
While I have improved a lot, there are still lots of stuff I haven't even touched upon, and I am going to need to know a lot more complex concepts before I can call myself confident with linux. But with that said, I still have a long ways to go. 
_______________________________________________________________________

_______________________________________________________________________

---