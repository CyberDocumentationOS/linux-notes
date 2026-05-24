# Task 1 — Linux Review Drill

# Goal of This Drill

The purpose of this drill is to:
- practice commands from memory
- get comfortable using Linux without notes
- build confidence
- identify weak areas

IMPORTANT:
Getting stuck is NORMAL.

If you forget:
1. Try first
2. Use `man`
3. Google it
4. Retry

That is REAL Linux workflow.

---

# pwd
Print Working Directory
## What does it do?
The pwd command prints what working directory you are currently in.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
pwd
    #Prints what working directory you are in.
```

### What happened?
When I inputted the pwd command, it printed what working directory I was in (/home/vboxuser).
_______________________________________________________________________

_______________________________________________________________________

---

# ls
List Storage
## What does it do?
The ls command lists the storage of a directory. It is a very commonly used command. 
Note: The ls command lists files and directories. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
ls
    #When this command is input, it lists all the storage in the directory.
ls -la
    #When this command is input, it lists all the storage in the directory long ways, including hidden files.
```

### What happened?
When I input the ls and ls -la command, it output the storage of the directory I was in.
_______________________________________________________________________

_______________________________________________________________________

---

# cd
Change Directory
## What does it do?
The cd command changes the working directory you are in to the one you specify
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
cd /home
    #This command changes you working directory to /home.
cd ..
    #This command changes your working directory to thr previous one you are in.
cd ~
    #This command change your working directory to the user's home directory.
```

### What happened?
When I input these commands, it would change my current working directory to the one I inpu.
_______________________________________________________________________

_______________________________________________________________________

---

# mkdir
Make directory
## What does it do?
The mkdir command allows you to create a directory. 
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
mkdir practice-folder
    #This command above creates a directory named practice-folder.
mkdir test
    #This command above creates a directory named test.
```

### What happened?
When I input the commands above, it added the directories listed to the directory I was working in.
_______________________________________________________________________

_______________________________________________________________________

---

# touch

## What does it do?
The touch command allows you to create files.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
touch notes.txt
    #When this command is input, it creates a file named notes.txt.
touch demo.log
    #When this command is input, it creates a file named demo.log.
```

### What happened?
When I input both commands, it created files with the names notes.txt and demo.log.
_______________________________________________________________________

_______________________________________________________________________

---

# rm
remove
## What does it do?
The rm command lets you remove files and directories.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
rm notes.txt
    #This command removes the specified file from the working directory you are in. 
rm -r testfolder
    #This command removes the specified directory that is stored in the current working directory you are in.
    #Note: Can also use rmdir. 
```

### What happened?
When I input both commands, it removed both the file and directory I specified from the current working directory I was in. 
_______________________________________________________________________

_______________________________________________________________________

---

# cp
copy
## What does it do?
The cp command allows you to copy outputs into other files.
Note: The cp command copies files and directories. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
cp notes.txt backup.txt
    #This command copies the output of notes.txt and puts it into backup.txt.
    #Note: If backup.txt is not yet created, the command will create it, then paste it into the file.
cp -r folder1 folder2
    #This command copies the folder1 directory and pastes it into the folder2 directory.
    #Note: Same rules apply as above, but with directories.
```

### What happened?
When I used both of the commands, they copied the output of the first item and pasted it into the second item.
_______________________________________________________________________

_______________________________________________________________________

---

# mv
move
## What does it do?
The mv command moves the output of files and directories into a new location, then deletes the old file. It is also used to rename items. 
Note: moves files and directories (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
mv notes.txt notes-old.txt
    #This command moves the output of notes.txt to notes-old.txt and then deletes the original file. 
    #Note: This can also be considered renaming.
mv notes.txt ~/Documents
    #This command moves the notes.txt file into the documents directory. 
```

### What happened?
When I used both of the commands, it either renamed what I wanted it to, or moved the file where I wanted it.
_______________________________________________________________________

_______________________________________________________________________

---

# chmod
change mode
## What does it do?
The chmod command allows you to change the permissions of both files and directories.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
chmod 755 script.sh
    #This command changes the permissions of the file script.sh to -rwxr-xr-x (owner gets read, write, and execute permissions while group and others get only read and execute permissions).
chmod u+x script.sh
    #This command gives the owner of the file execute permissions.
chmod 700 secret-folder
    #This command changes the permissions of the file to have only the owner have read, write, and execute privledges.
```

### What happened?
When I input the commands above, I was able to change the permissions of the files that I desired to do so with. 
_______________________________________________________________________

_______________________________________________________________________

---

# sudo
super user do
## What does it do?
The sudo command allows you to have super user priviledges for a short period of time. This is mainly used for installing software or packages onto your system, though sometimes it is used to access certain directories and files. 
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
sudo apt update
    #This command lets you update the metadata of all the currently installed packages and software on your system.
    #Note: Only refreshes package metadata. (Graded)
sudo mkdir testdir
    #This command lets you create a directory if you are not allowed to create a directory in a certain situation. 
```

### What happened?
When I input the first command, it prompted me for my password first. Once I did, it updated all the packages on the system. When I input the second command, it let me create a directory in a location I normally wouldn't be able to (root).
_______________________________________________________________________

_______________________________________________________________________

---

# ps
processes
## What does it do?
The ps command allows you to see all current processes running on your system.
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
ps
    #This command lets you see what current processes are running on your current terminal session.
ps aux
    #This command lets you see what current processes are running system wide, including hidden ones.

```

### What happened?
When I input both of these commands, I was able to see what processes were running both on my terminal session and system wide.
_______________________________________________________________________

_______________________________________________________________________

---

# kill

## What does it do?
The kill command allows you to terminate processes you wish. 
_______________________________________________________________________

_______________________________________________________________________

---

## Example

```bash
kill PID
    #This command lets you gracefully terminate the process you desire (the PID indicates what process you want to terminate).
kill -9 PID
    #This command lets you forcefully terminate the process you desire. 
    #Note: This is usually a last resort, as it is very rough, and just wants you to straight terminate the process, no matter what. 
killall firefox
    #This command lets you terminate a process without having to use a PID (process id). It also lets you terminate any background processes associated with it. 
    #Note: killall firefox terminates all processes named firefox (Graded)
```

### What happened?
When I used these commands, they terminated the processes I desired (firefox). 
_______________________________________________________________________

_______________________________________________________________________

---

# Reflection

## Which commands did I remember easily?
Pretty much all of them, as I have been using them for multiple days straight now, so they are easy to remember now. 
_______________________________________________________________________

_______________________________________________________________________

---

## Which commands did I struggle with?
I didn't really struggle with any commands, as they were all self explanatory. There were some that I forgot the name of eariler on (like I forgot the mv command when I was using the cp command), but then I saw it later and was like "Oh that's the command that lets me do that.". Other than that, no problems really. 
_______________________________________________________________________

_______________________________________________________________________

---

## What commands do I need more practice with?
I think I need more experience with the ps commands, mainly when it comes to reading the information, as I can tell it is going to be an important tool moving forward. I also need to remember what command lets me input stuff into files, as being able to input stuff into files is pretty important! Overall, I mainly need to practice with stuff that is going to be used in my career field a lot, but I believe this will come with more practice and time. 
_______________________________________________________________________

_______________________________________________________________________

---

# Task 2 — Build a Small Linux Project

# Goal of This Project

This project is meant to:
- practice Linux navigation
- organize directories
- manage files
- practice permissions
- build confidence using the terminal

---

# Step 1 — Create Main Directory

## Command Used

```bash
mkdir ~/cyberlab
```

### What happened?
When I input this command, the directory "cyberlab" was made.
_______________________________________________________________________

_______________________________________________________________________

---

# Step 2 — Create Subdirectories

## Commands Used

```bash
mkdir ~/cyberlab/notes
mkdir ~/cyberlab/scripts
mkdir ~/cyberlab/logs
```

### What happened?
When I input these commands, I made the subdirectories notes, scripts, and logs. 
Note: Instead of doing it the way presented, I decided to just cd to the cyberlab directory and make them there, since it is more efficient for this instance.
_______________________________________________________________________

_______________________________________________________________________

---

# Step 3 — Create Files

## Commands Used

```bash
touch ~/cyberlab/notes/linux-notes.txt
touch ~/cyberlab/scripts/backup.sh
touch ~/cyberlab/logs/system.log
```

### What happened?
When I input the commands, I was able to create the specified files for the specified subdirectories. 
_______________________________________________________________________

_______________________________________________________________________

---

# Step 4 — Practice Moving Files

## Commands Used

```bash
mv linux-notes.txt notes-backup.txt
mv system.log ~/cyberlab/notes
```

### What happened?
When I input the first command, it created a file named notes-backup.txt, moved the contents of linux-notes.txt to it, then deleted linux-notes.txt (basically renamed it). When I input the second command, it moved system.log from the log subdirectory to the notes subdirectory.
Note: The command renamed linux-notes.txt to notes-backup.txt. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

# Step 5 — Practice Copying Files

## Commands Used

```bash
cp notes-backup.txt second-copy.txt
cp backup.sh backup2.sh
```

### What happened?
When I inputted the commands (in their respective subdirectories of course), I was able to make copies of both of the files easily.
_______________________________________________________________________

_______________________________________________________________________

---

# Step 6 — Practice Permissions

## Commands Used

```bash
chmod 700 ~/cyberlab/logs
    #Permission string drwx------
        #Only the owner has read, write, and execute priviledges.
chmod 755 ~/cyberlab/scripts
    #Permission string drwxr-xr-x
        #The owner has read, write, and execute priviledges, while the group and others only have read and write.
        #Notes: The owner has read, write, and execute permissions, while group and others only have read and execute permissions. (I meant to write execute, but oh well) (Graded)
chmod 644 ~/cyberlab/notes/linux-notes.txt
    #Permission string -rw-r--r--
        #The owner has read and write permissions, while group and others only have read permissions.
```

### What happened?
When I input the commands presented, I was able to change the permissions of the files to the one that were requested. 
Note: Instead of doing the full arguments, I cd to cyberlab directory, and had it in the format of "chmod 700 logs" to make it more convient for myself. 
_______________________________________________________________________

_______________________________________________________________________

---

# Step 7 — Explore Project Structure

## Commands Used

```bash
tree ~/cyberlab
ls -la ~/cyberlab
```

### What happened?
When I input the first command, it gave me a tree like hierarchy of the directory cyberlab, and when I did the second command, it listed the contents of the directory long ways, including hidden files. 
_______________________________________________________________________

_______________________________________________________________________

---

# What Does My Final Project Look Like?

Paste your final `tree` output below:

```bash
vboxuser@Ubuntu :~ $ tree ~/cyberlab
    /home/vboxuser/cyberlab
        logs
        notes
            notes-backup.txt
            second-copy.txt
            system.log
        scripts
            backup2.sh
            backup.sh
4 directories, 5 files

```

---

# What did I learn from this project?
I learned how to configure a directory with subdirectories, files, and permissions. 
_______________________________________________________________________

_______________________________________________________________________

---

# What confused me?
This is going to sound a little over confident, but not really confused me on this lab, it was all pretty straight forward. 
_______________________________________________________________________

_______________________________________________________________________

---

# Task 3 — Weekly Reflection

# Week 1 Reflection

## What did I learn this week?
I learned the basics of manuevering through the linux terminal and filesystem, understanding permissions, and learning about processes and packages. 


---

## What topics confused me the most?
The topics that confused me the most were the ones that weren't touched apon that much, such as fastfetch and top, but those are more so the tools themselves, not the commands.

---

## What commands do I remember best?
The commands I remember the best are the ls and cd commands, as they were the ones I was using the most often throughout this entire week, and they are pretty natural to me at this point in time. 

---

## What commands do I still need practice with?
I need practice with the tools like top, htop, fastfetch, and others like that. I want to fully understand how to use them and what the specific elements mean in detail. I mainly want to learn how these tools are used in certain scenarios, as that would help me learn more about them. I also need to remember how to put stuff into files, that is a must.

---

## What Linux topic do I want to learn more about?
While I do want to learn more about the top and htop commands, I mainly want to learn more logs and understanding them better. It is going to be a recurring thing in cybersecurity, I know that, and I would like to understand how to use log specific tools in the future, so I understand the complexities of them and be able to use them with cyber specific labs. 

---

## What was the hardest thing this week?
The hardest thing this week wasn't understanding the material or anything like that, it was managing my time with it. I was fortunate enough to only have to work 1 day this week, but the day I did work, I was barely able to get a good amount done. I think managing my time with these is going to be something I need to address moving forward, as while yes, it is good I took extra time learning, I need to keep in mind that jobs don't like to wait, and being able to complete the tasks in a timely manner is important. But this is something that will solve itself over time, so it isn't something that is to be worried about. 

---

## What was the easiest thing this week?
The easiest thing to do this week was today actually, the practice day, as doing all the commands requested was quite easy, as I have been doing them for a solid week at this point. This is a good thing, as it means a lot of essential commands like ls, cd, and others like chmod are going to become muscle memory for me, and not something I have to worry about forgetting. 

---

## What am I most proud of this week?
The thing that I am most proud of this week is sticking to the plan and doing the practice I need. Without practice, I won't remember any of this, so the fact I am getting on a linux terminal everyday is something I am proud of doing. 

---

## How confident do I feel compared to Day 1?

(1–10)

```text
Confidence Level: 3/10
```

Why?
Yes, I do feel a little more confident about linux now, mainly when it comes to manuevering around the terminal, but this is not the end of it, far from it. I still have to learn things like scripts and networking, so I am far from being an expert in linux. But with that said, this is week 1 of 52, so it makes sense I am not the best in the world right now. 

---

# Final Thoughts

## How did Week 1 go overall?
I think week 1 went well for the most part. Minus some time management skills, I understand basic concepts of linux, and am much more confident around the terminal than I ever have been before. I hope to keep up the consistency I have right now in the future.

---