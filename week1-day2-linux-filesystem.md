# Task 1 — Learn Linux Filesystem

## What is the Linux filesystem?

The Linux filesystem is the way Linux organizes and stores files and directories.

Directories are folders that contain files and other directories.

Linux uses a hierarchical structure that starts at the root directory:
/bin: The most basic binaries and functions are stored here.
    /sbin: The system binaries that a sys admin would used are stored here. Both of these directories have all the functions that are used in single user mode (basically adminstrator privledges or root user). Networking is disabled in this mode because of security issues.
/boot: This folder contains all the things necessary to boot the system. It is best not to mess with it.
/cdrom: Meant for mounting cdrom stuff (not necessary nowadays).
/dev: This is where all of your devices are. This is usually a place where drivers go.
    Note: contains device files that represent hardware and virtual devices. (Graded)
/etc: This is where all your system wide configurations are.
/home: This is where you store your personal files and documents. 
/lib folders: This where all the libraries are stored. 
    Note: Libraries are files that applications can use to perform various functions.
/media: This is were you find any other mounted drives (usb stick, hard drives, etc).
/mnt: This is the same as above, though most of them automatically configured in /media nowadays. For manually mounted stuff, use this directory, and use the /media directory for os stuff.
/opt: The optional folder where manually installed software from venders reside. You can also store programs you have written yourself here as well.
    Note: Some software packages from the repo can also find their way here.
/proc: Where you find pseudo files, that contain information about system processes and resources. 
    Note: Pfiles are actually files on the system, this is the kernal translating other information to appear as files.
/root: The root user's home folder. Unlike normal users, the root user does not contain the normal directories inside. You need to have root permissions in order to access and put files in it.
    Note: This is the specific /root directory, not the simple / that is the root of everything. There is a difference.
/run: Tempfs folder that is usually run in ram. This means that if it shutdown or reboot, everything in it is gone. It is used for processes that start early in the boot procedure to store runtime information that they use to function.
/snap: This is where snap packages are stored and are mainly used by ubuntu. Snap packages are self contained applications that run differently than other packages. Will be something covered in the future.
/srv: The service directory where server stuff is stored. The files by external users will be stored here. 
/sys: It is a way to interact with the kernel. Is similar to the run directory and that it isn't written to the disk and is created every time it is boot up. Don't store anything here.
/tmp: Temporary directory where temporary documents go. Folder is usually emptied when system is rebooted.
/usr: The user application space where apps will be installed that will be used by the user. Any apps installed here are considered non essential for system operation. 
/var: The variable directory, that contains files and directories that are expected to grow in size. 
```bash
/
```

---

# Important Directories

## /home

### What is /home used for?
The home directory is where all your personal documents and files are stored. It also has all the user's directories in it as well. 
_______________________________________________________________________

### What did I find inside /home?
When I inputted the command cd /home, it brought me to the specific directory, and when I did ls, it only listed the vboxuser directory. Once I entered that, I then did the ls command once again, and it listed a bunch of directories I had before, such as documents, images, and all the practice folders I made yesterday. 
_______________________________________________________________________

### Why is /home important?
The home directory is important because it is where all of your personal files and documents are, and is where each user can access any of their personal stuff.
_______________________________________________________________________

---

## /etc

### What is /etc used for?
The etc directory is used to contain the configuration files for the whole system.
_______________________________________________________________________

### What did I find inside /etc?
When I did the ls command in the etc directory, I found a bunch of configuration files and other directories required for the system to operate. I quickly left the folder afterwards, as it would not be good if I messed with it. 
_______________________________________________________________________

### Why is /etc important?
The etc directory is important because it is where all the configuration files are that let the os operate the way it is. Without it, all the files would be scattered around the os, and could cause a lot of accidental deletions.
_______________________________________________________________________

---

## /var

### What is /var used for?
The /var directory is used for files and directories that are expected to grow in size.
_______________________________________________________________________

### What did I find inside /var?
When I did ls /var, I saw a lot of directories like crash, cache, or mail. These are usually things that get filled with things other time, so it makes sense that they are here.
_______________________________________________________________________

### Why is /var important?
The /var directory is important because there needs to be a place for files and directories like this to go, as it would cause a lot of clutter and confusion if they weren't there. 
_______________________________________________________________________

---

## /bin

### What is /bin used for?
The /bin directory is where all of the system binaries are stored (commands such as ls and rm).This is where basic executibles go.

_______________________________________________________________________

### What did I find inside /bin?
When I did ls /bin, I found a bunch of directories and binaries, as this is where all of those files are stored. 
Note: Usually contains executable files rather than directories. (Graded)
_______________________________________________________________________

### Why is /bin important?
The /bin directory is important because it is where all the executibles for the commands are. If you were to mess around and delete them, then the system functionality could break.
_______________________________________________________________________

---

## /root

### What is /root used for?
The /root directory is the root user's home folder (who is the super user of the computer). This is where the root user's personal files and directories are.
_______________________________________________________________________

### What did I find inside /root?
When I did ls /root, it wouldn't let me in, saying "permission denied". My guess is that it has a bunch of files and directories that the root user has access too. 
_______________________________________________________________________

### Why is /root important?
The basic / directory (which is the root of everything) is important because it is where all other directories and files root from. The /root directory specifically is important because it is where the root user's files and documents are, basically the adminstration profile.
_______________________________________________________________________

---

# Task 2 — Practice Navigation

## cd
change directory
### What does it do?
The cd command changes the directory you are currently in. 
_______________________________________________________________________

### Example

```bash
cd /home
    #This changes your current directory to the home directory.
cd ..
    #This means we want to go to the parent directory of the current working directory.
cd my\ books
    #The \ in my books represents a space in the name. 
cd
    #Just using cd straight puts you in your home folder.
```

### What happened when I used it?
Everytime I used the cd command, it would take me to my directory of choice. 
_______________________________________________________________________

---

## ls -la

### What does it do?
The ls -la command list all the items in the directory long ways, including the dotfiles. The -l flag means longways while the -a flag means all files, including dotfiles (., ..). 
_______________________________________________________________________

### Example

```bash
ls -la
    #This lists all the items in the directory longways, including the . and .. files.
ls -la demo
    #This does the same thing as above, though now with the demo directory. 
```

### What happened when I used it?
When I used both of the examples, it listed all the items in both of the directories, including the dotfiles.
_______________________________________________________________________

### What do the flags mean?

```bash
-l
    #This flag means to list the file long ways (long listing format). It provides details for each file (like file type, permissions, owner, group, file size, and modification date).
    #Note: lists directory contents in long format. (Graded)
```

_______________________________________________________________________

```bash
-a (or -all)
    #This flag lists all of the files, directories, and anything else within the directory, including dotfiles.
```

_______________________________________________________________________

---

## tree

### What does it do?
The tree command lists the file structure/hiearchy of the current working directory.
_______________________________________________________________________

### Example

```bash
sudo apt install tree
    #This command argument installs the tree command onto your linux system.
tree
    #Displays the file structure/hierarchy of the current working directory.
tree demodir
    #Displays the file structure/hierarchy of the specified working directory.
tree demodir/demosubdir
    #Displays the file structure/hierarchy of the specified working subdirectory.
tree -s
    #Displays the file structure/hierarchy of the current working directory along with file sizes.
tree -h
    #Same thing as above but makes it easier to understand (use k and m insteading of the raw numbers).
tree -a
    #Displays the file structure/hierarchy of the current working directory along with hidden files.
tree -d
    #Displays the file structure/hierarchy of the current working directory but only the directories, not the files.
tree -hd
    #Displays the file structure/hierarchy of the current working directory but only the directories, and the files sizes in an easier to read manner (uses k and m).
tree -hd demo
    #Same thing as above though now it will do it with the specified directory.
tree -L 2 /etc
    #Displays the file structure/hierarchy of the specific working directory but it only goes a specific amount deep (for this instance, 2 levels).
tree -p /etc
    #Displays the file structure/hierarchy of the specified working directory but shows the permission strings as well.
tree -f /etc
    #Displays the file structure/hierarchy of the specified working directory but it shows the whole file path.
tree -x
    #Displays the file structure/hierarchy of the current working directory but avoids other file systems. Pretty much excludes mounted files systems.
```

### What happened when I used it?
When I used the tree command in all of the scenarios, it listed the file hierarchy of the directory I was in or specified. The only problem I had is that it wasn't installed at first, but the I used the argument sudo apt install tree, and I was able to install and use it.
_______________________________________________________________________

---

## history

### What does it do?
The history command is a command that shows the history of previously executed commands.
_______________________________________________________________________

### Example

```bash
history
    #Lists the last 1000 commands that were used in the terminal.
    #Note: history displays previously executed commands (graded)
!159
    #Executes the command that was typed in the specified number. 
        #For example, if the command tree -h was the command executed the 159th time, then when we put !159, it will execute the command tree -h again.
 cd
    #When a space is in front of a command, it will not track that in history. It is best to use this when you have sensitive data being put in.
    #Note: On some Linux systems, commands beginning with a space may not be stored in history depending on shell configuration.
```

### What happened when I used it?
When I put in the command, it listed the history of commands that were put in. When I put in the !159, it input the command that was executed the 159th time, which was tree -d. And when I put a space in front of the command, it didn't track it.
_______________________________________________________________________

---

## man ls

### What does it do?
The man command in general lists the manual and explains the command with it, in this case the ls command. 
_______________________________________________________________________

### Example

```bash
man ls
    #Display the manual for the ls command.
```

### What happened when I used it?
When I typed in man ls, it led me to the manual for the ls command.
_______________________________________________________________________

### How do I exit the manual page?
All you have to do to exit the manual page is press q, and it will automatically take you back to the terminal. 
_______________________________________________________________________

---

## man cd

### What does it do?
The man cd command takes you to the manual page for the cd command. 
_______________________________________________________________________

### Example

```bash
man cd
    #Displays the manual for the cd command. 
```

### What happened when I used it?
When I put in the command, it did not respond with a manual page, and it said there was no manual page for the cd command. After looking it up, this is because cd is a shell builtin command, and does not have an external binary. Beacause of this, it has no manual page. 
_______________________________________________________________________

---

# Directory Exploration

## Exploring /home

### Commands I used

```bash
cd /home
    #Took me to the home directory.
ls -la
    #Displayed all the contents (including hidden files) long ways.
```

### What did I notice?
I noticed that the /home directory specifically really only has the directories for the indivdual users, and nothing else really. 
_______________________________________________________________________

_______________________________________________________________________

---

## Exploring /etc

### Commands I used

```bash
cd /etc
    #This took me to the /etc directory. 
ls -la
    #Displayed all the contents (including hidden files) long ways.
```

### What did I notice?
I noticed that there were tones of files and binaries in this directory. It makes sense, it does have a bunch of configuration files.
Note: Mostly config files, directories, scripts, and service configs. Not as many binaries as I thought. (Graded).
_______________________________________________________________________

_______________________________________________________________________

---

## Exploring /var/log

### Commands I used

```bash
cd /var/log
    #This took me to the /log subdirectory of the /var directory.
ls -la
    #Displayed all the contents (including hidden files) long ways.
```

### What did I notice?
I noticed a lot of files and directories that are meant for logging certain items and processes, which does make sense for a directory called /log. I do definitly need to learn more about this directory though, as I am still fairly confused here.
_______________________________________________________________________

_______________________________________________________________________

---

# Task 3 — TryHackMe Notes

## Room Completed
```text
Linux Fundamentals Part 1
```

---

## What was the most important thing I learned?
I think the most important thing I learned in this room is the find, grep, and cat commands, as they seem very helpful and important to use. Cat is one that I have used before when it comes to the tutorials I watched for other commands, but it is good to know what it actually does.
_______________________________________________________________________

_______________________________________________________________________

---

## What confused me?
I think the thing that confused me the most was the & operator, as I have yet to have a command that I have learned so far use that, but I guess time will tell when it comes to that. 
_______________________________________________________________________

_______________________________________________________________________

---

## Commands I used the most

```bash
echo
    #Display the text that we input into the terminal.
    echo "Hello, World!"
        #The use of " is necessary if there are spaces.
whoami
    #Displays who the current user logged in is.
ls
    #Displays the items in the current working directory.
cd
    #Changes the directory you are in.
cat
    #Lets you output the contents of files.
    cat demo.txt
        #This line lets you display the contents of this file, demo.txt.
pwd
    #Tells you what directory you are currently in.
find
    #Tells you where you can find a certain file.
    find -name demo.txt
        #Will tell you where the specific is in the system.
    find -name *.txt
        #* is called a wildcard that can help you find files with something at the end of them. For example, the *.txt will find files that have .txt at the end of them.   
        #Note: * is a wildcard representing any number of characters. So it really means any filename ending in .txt. (Graded)
        find . -name demo.txt
            #Note: find expects a starting directory. (Graded)

grep
    #Lets you search for the contents of files for specific values.
    grep "81.143.211.90" access.log
        #The line presented searches through the file, access.log, for the specific value presented, "81.143.211.90". It will show all the results that have this specific value.
    grep -R "PRETTY_NAME" /etc/
        #The line presented will search across all the files in the /etc/ directory, subdirectories included. It will then show where the variable, "PRETTY_NAME", shows up.
&
    #This is an operator that allows you to run commands in the background of the terminal.
        #Note: run processes in the background. (Graded)
    firefox &
        #The line presented tells the terminal to launch firefox then return control of the terminal immediately.
&&
    #This is an operator that allows you to combine multiple commands together into one line.
    mkdir testdir && cd testdir
        #The line presented creates a directory called testdir, then changes directory to be testdir. If the first part doesn't happen, then the line is not executed.
>
    #This is an operator redirects outputs of commands and directing it somewhere else.
        #Note: redirects standard output to a file. (Graded)
    echo hey > welcome
        #The line presented will create (or overwrite) a file named welcome and echo the output "hey" into that file.
>>
    #This is an operator that does the same thing as above, but doesn't overwrite anything.
    echo hello >> welcome
        #The line presented will add the output "hello" to the file welcome, regardless of what is in there.
```

---


---

# End of Day Reflection

## What directories seem most important so far?
The most important directories seem to be /root, /bin and /sbin, /etc, and /home, as they have the most important contents of the system. 
_______________________________________________________________________

---

## Which command was most useful?
Definitely the tree command, as it makes looking through all the directories and files so much easier than before. With that said, the ls -la command is also one that can be very helpful, as it will show me everything, including hidden files, so it is best to use that one more frequently as well. 
_______________________________________________________________________

---

## Which command was hardest to understand?
There was no command in particular that was difficult to understand as a whole, as the only contender, grep, became easier to understand the second time I read it. However, the & operator is still fairly confusing for me, as there is no command I know so far that uses that operator, so it seems like I may forget it in the future. 
_______________________________________________________________________

---

## How comfortable do I feel navigating Linux now? (1–10)

Score: 3/10

Why?
While yes, I feel more confident than yesterday's outing with linux, I am still a beginner, and I need more practice before I can fully say I am confident with it. But it is only day 2 of 365, so that is to be expected.
_______________________________________________________________________