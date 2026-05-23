# Task 1 — Learn apt

# What is package management?

Package management is the system Linux uses to:
- install software
- update software
- remove software
- manage dependencies

A package manager automatically downloads and configures software from repositories.

Ubuntu and Debian-based systems use:
```bash
apt
```

which stands for:
```text
Advanced Package Tool
```

---

# What are repositories?
A reporsitory is a centralized storage location (which is usually a remote server), that holds software packages, metadata, and digital signature. It is similar to an app store, as it allows you to install, update, and remove applications and components from a system. 

---

# sudo apt update

## What does it do?
The sudo apt update command is used in debian-based distros that refreshes the local package index files by downloading the latest info about available software from configured repos. Think of it as refreshing the meta data. 
Note: This command is recommended before using any other apt commands. 
Note: This does not install any software, it only updates the catalog of what is available. 

_______________________________________________________________________

---

## Example

```bash
sudo apt update
    #When this command is input, it refreshes the index of the system, updating the catalog of the system.
```

### What happened?
When I input this command, it updated the meta data and any new packages that were available. 
_______________________________________________________________________

_______________________________________________________________________

---

# sudo apt upgrade

## What does it do?
The sudo apt upgrade command allows you to download and install the latest versions of all currently installed software packages. 

_______________________________________________________________________

---

## Example

```bash
sudo apt upgrade
    #When this command is input, it updates all of the software packages on your system (if there is a new version available).
sudo apt dist-upgrade
    #When this command is input, it does the same thing as above, though it will not do any updates that install or remove additional packages.
    #Note: dist-upgrade can install or remove packages if needed to complete upgrades. (Graded)
```

### What happened?
When I input this command, it proceeded to update all of the software packages that could be updated. I did notice it got stuck at 98% for a little bit, but then it finished, so it wasn't anything to worry about. 
_______________________________________________________________________

_______________________________________________________________________

---
# apt search

# What does it do?
The apt search command lets you search for package name of a certain software you are looking for.

## Example

```bash
apt search vim
    #When this command is input, it shows you all of the packages that have the keyword vim in it, letting you find the one you want. 
```

### What happened?
When I input the command, it gave me a big list of packages I could install if I wanted to. Since vim seems like an advanced package, I won't install it right now.

---

# sudo apt install

## What does it do?
The sudo apt install command lets you download and install software packages from configure repos. It installs anything needed automatically, including other depended on packages (it may prompt you with this).

_______________________________________________________________________

---

# Installing Packages
 ```bash
sudo apt install
    #This is the basic command that lets you install packages.
sudo apt install tmux htop git
    #This command allows you to install three commands at once, the tmux command, the htop command, and the git command. 
 ```

# Removing Packages
```bash
sudo apt remove
    #This is the basic command that lets you remove packages.
```

# Source File
```bash
sudo nano /etc/apt/sources.list
    #This is the file that the apt commands pulls it's sources from.
    #Note: This will be covered more in depth later on.
```
## tree

### Command

```bash
sudo apt install tree
    #This command lets you install the tree command onto your system. 
    #Note: This command was cover in full detail in week1-day2-linux-filesystem.md.
```

### What does tree do?

The `tree` command displays the file hierarchy structure of directories.

### What happened?
I installed tree `tree` yesterday, but when I ran the command above, it let me install it without a problem.
_______________________________________________________________________

_______________________________________________________________________

---

## htop

### Command

```bash
sudo apt install htop
    #This command install the htop package, allowing you to use the htop command.
    sudo dnf install htop
        #This does the same as above, though it is for distros based on fedora.
    sudo dnf install epel-release
        #This repo might be needed to install htop on fedora based distros.
htop
    #This command opens the htop monitor on your system. 
```

### What does htop do?
Htop is a process viewer and system monitor for linux. It displays metrics for the CPU, memory, swap usage, along with other processes.

### What happened?
When I ran the install htop command, it installed the tool, and when I put just htop, it opened the monitor. 
Note: I am going to explore this tool later down the line, just not at the moment. 
_______________________________________________________________________

_______________________________________________________________________

---

## fastfetch
    #Note: Neofetch is a discontiued application, so I am using fastfetch instead.

### Command

```bash
sudo apt install fastfetch
    #This command lets you instell the fastfetch application on linux.
fastfetch
    #This command opens the fastfetch application for you.
    #Note: runs the fastfetch command (Graded)
```

### What does fastfetch do?
Fastfetch (successor to neofetch) is a performance oriented system information tool for linux that is filled with features and is very customizable.

### What happened?
When I initially tried to do sudo apt install neofetch, the output said unable to locate package neofetch. This is because the neofetch tool has been discontiued, so I tried using the fastfetch tool instead, which did work. When I input the second command, it displayed the fastfetch information, which was the intended affect. 
Note: I don't fully understand the customizible part of the tool (whether it is system wide or not), but that can be learned later down the line. 
_______________________________________________________________________

_______________________________________________________________________

---

# Important Concepts Learned

## Difference between update and upgrade

### update
The sudo apt update command simply updates the metadata of packages and makes sure they are all good. 
_______________________________________________________________________

### upgrade
The sudo apt upgrade command updates the software packages on the system, installing and removing packages when needed. 
_______________________________________________________________________

---

## Why is package management important?
Package management is important because it is how we install applications on linux, and without it, it would be very difficult to get what's needed on the system.
Note: Package managers help ensure software is securely distributed, updated, and dependency-compatible. (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

# Task 2 — Learn Processes

# What is a process?

A process is a running instance of a program.

Examples:
- Firefox running
- VS Code running
- Terminal sessions
- Background system services

Linux constantly runs many processes simultaneously.

---

# ps

## What does it do?
The ps command allows you to see what processes are running on your system in linux.

_______________________________________________________________________

---

## Example

```bash
ps
    #When this command is input, it shows all the processes that are running in this particular terminal session.
    #Note: shows processes attached to the current shell/session (Graded)
ps aux
    #When this command is input, it shows all the processes that are currently running on the system.
    a
        #Processes for all users.
    u
        #User oriented format with details on resource usage.
    x
        #Processes without a controlling terminal.
ps x
    #When this command is input, it shows every process that is running as the currently logged in user on the system.
ps -He
    #When this command is input, it displays the relationships between each of the processes.
    -H
        #Instructs ps to show the process hierarchy (Parent child relationship between the processes).
    -e
        #Ensures that all processes on the system are listed, regardless of what terminal they are associated with or who owns them.
ps -axjf
    #When this command is input, the same thing is displayed, though in an easier to read format.
    

```
# Labels for command outputs

```bash
ps
    PID (Process ID)
        #Identifies each process.
        #Each process on a linux will have a unique PID.
        #When a process runs, it is assigned a PID.
    TTY
        #The terminal the process is running inside of.
    Time
        #How much time the process has been utilizing the CPU.
    CMD
        #The command that is running as apart of the process.
ps aux
    USER
        #The user for each process.
    PID
        #Process ID.
    %CPU
        #The percent the process is using the CPU.
    %MEM
        #The percent the process is using memory.
    VSZ (Virtual Memory Size)
        #Total virtual address space allocated to the process.
    RSS (Resident Set Size)
        #Non-swapped physical memory currently used by the process.
    TTY
        #The terminal the process is running inside of.
    STAT
        #Current status and modifiers of the process using single letter codes.
    START
        #When process first started.
    TIME
        #How much time the process has been utilizing the CPU.
    COMMAND
        #The command that is running as apart of the process.
ps x
    PID
    TTY
    STAT
    TIME
    COMMAND
ps -He
    PID
    TTY
    TIME
    CMD
ps -axjf
    PPID
        #Parent process id.
    PID
    PGID
        #Process Group ID.
    SID
        #Session id, same as process that started the chain.
    TTY
    TPGID
        #Terminal session id in which the process is associated with.
    STAT
    UID
    TIME
    COMMAND
```
Note: A lot of the labels are confusing to me, but I will know them more later.
### What happened?
When I ran all the commands, it would show the process that were happening when I asked with the specific commands.
_______________________________________________________________________

_______________________________________________________________________

---

# top

## What does it do?
The top command is a real-time system monitoring tool that displays running processes and overall system resource usage. 

_______________________________________________________________________

---

## Example

```bash
top
    #When this command is input, it opens the top monitor on your system.
    #Labels
        Statistics
            Up time
                #How long the system has been up.
                #When it comes to server, up time of 5-6 minutes might be a problem.
            Load Average
                #Trending Perfomance.
            Tasks
                #Statistics about tasks your system is running.
            %Cpu(s)
                #The percentage of CPU time spent in various states.
            MiB Mem
                #Physical ram utilization.
            MiB Swap
                #Virtual memory usage.
        Task Area
            PID
                #Process ID
            USER
                #User account running the process.
            PR
                #Priority.
            NI
                #Nice value.
            VIRT
                #Virtual memory usage.
            RES
                #Resident memory (physical RAM).
            SHR
                #Shared memory.
            S
                #Process status.
            %CPU
                #CPU usage percentage.
            %MEM
                #Memory usage percentage.
            TIME+
                #Total CPU time consumed.
            COMMAND
                #Command name or line.
        
```
Note: I don't nearly have enough time to go in depth on this command, so I plan on exploring this on one of my actice rest days later.
### What happened?
When I put the top command in, it opened the top monitor, and I was able to interact with it a little bit. Definitely confusing, and I need time with it to fully understand it.
_______________________________________________________________________

_______________________________________________________________________

---

# htop

## What does it do?
Htop is a process viewer and system monitor for linux. It displays metrics for the CPU, memory, swap usage, along with other processes. (Copied from task 1).

_______________________________________________________________________

---

## Example

```bash
htop
    #This command opens the htop monitor on your system.
```

### What happened?
Note: Copied from task 1
When I ran the install htop command, it installed the tool, and when I put just htop, it opened the monitor. 
Note: I am going to explore this tool later down the line, just not at the moment.
_______________________________________________________________________

_______________________________________________________________________

---

# kill

## What does it do?
The kill command allows users to terminate certain processes on their system.

_______________________________________________________________________

---

## Example

```bash
kill PID
    #When this command is input, it terminates the process that is specified, the PID.
    pidof firefox
        #When this command is input, it retreives the PID of the application requested, in this case, firefox.
        #Note: Only returns something if it is running.
    kill PID1 PID2
        #Same as first one but kills multiple at once.
kill -9 PID
    #When this command is input, it sends signal 9 to a particular process, which is it's PID, and kills the process without clean up.
    #Note: Usually used as a last resort.
kill -L
    #When this command is input, it lists all the types of kill commands.
kill -3 PID
    #When this command is input, it essentially quits the application (has a core dump).
    #Note: sends SIGQUIT, which terminates the process and may create a core dump (Graded)
killall processname
    #When this command is input, it terminates the process using the process name instead of its PID.
    #Note: terminates ALL matching processes with that name (Graded)
```

## Signals (Only important ones listed for now)
1: HUP: Hangup (often used before logging out)
2: INT: Interupt (same as pressing Control+C in a terminal session)
9: KILL: Kill (terminates without cleanup). Only works if issued by process owner or super user (root). The program cannot respond to the signal; it must terminate.
15: TERM: Kill (terminates gracefully after cleanup). Only works if issued by process owner or super user (root). (Default)
### What is the difference?

`kill PID`
This command will terminate the process cleanly if it can.
_______________________________________________________________________

`kill -9 PID`
This command will terminate the process no matter what, without cleanup of any kind, and will forcibly terminate the process. This should only be used in last case scenario situations.
_______________________________________________________________________

---

### What happened?
When I did the kill commands, it would terminate the process I chose for it (fire fox). When I used the killall command, it would terminate the process I chose without me having to provide a PID for it, which is nice.
_______________________________________________________________________

_______________________________________________________________________

---

# Process Practice

# Open Programs

## What programs did I open?
I opened firefox and the app store on there to test the water with the commands. 
_______________________________________________________________________

_______________________________________________________________________

---

# Finding Processes

## Commands I used

```bash
ps aux
htop
top
```

### What did I notice?
I noticed that it was difficult to find the processes with all the commands used. I had to use the pidof command to find the PID for firefox, and the grep command to even find the app center.
_______________________________________________________________________

_______________________________________________________________________

---

# Killing Processes

## What process did I terminate?
I was able to terminate firefox, as I had the PID for it, but I wasn't able to terminate the app center, even with the killall command.
_______________________________________________________________________

---

## What happened after terminating it?
After I terminated firefox, it imediately went away. No windows animation for exiting it or anything, just gone.
_______________________________________________________________________

_______________________________________________________________________

---

# Important Process Concepts

## What is a PID?
A PID is a process id, which is given to every process that is running.


### Why are PIDs important?
PIDs are important because they allow us to easily find processes and deal with them appropiately, be that let them run or terminate them. It also helps us avoid confusion, as even though some things have the same name, all PIDs are different, no exceptions.
_______________________________________________________________________

_______________________________________________________________________

---

## Difference between foreground and background processes
Note: I definitely need to explore this concept further.
### Foreground Process
A foreground process is a process that runs in the actice terminal directly, blocking further input until the process is complete or moved to the background. Simple commands like ls fall into this category.
_______________________________________________________________________

### Background Process
A background process is a process that runs independently of the terminal, allowing the user to issue other commands while the task is being completed. 
_______________________________________________________________________

---

# Task 3 — Explore Logs

# What are logs?

Logs are files that record:
- system activity
- errors
- authentication attempts
- software events
- process activity

Logs are extremely important in:
- cybersecurity
- troubleshooting
- system administration
- incident response

---

# Exploring /var/log

## What is /var/log?
The /var/log directory is where all the logs and information regarding logs are kept. The reason it is in the /var directory is because logs are always increasing, so being in the variable directory makes sense.
Note: /var/log stores system, application, and service log files. (Graded)
_______________________________________________________________________

---

## Commands I used

```bash
cd /var/log
    #This command changes directory to the log directory, allowing you to view log files.
    #Note: Some log files may not be accessible for base users, and may require sudo to be accessed.
    #Note: Some log files end in .log, while others end in log. Some people miss this.
        #Note: many logs have no extentsion at all. (Graded)
ls -la
    #This command lists all the contents of the current directory (in this case, /var/log), lists them long ways, and includes hidden files.
```

### What did I notice?
When I opened the directory and did the ls command, a lot of the items within the directory had log in the name somewhere, or were related to them in someway.
_______________________________________________________________________

_______________________________________________________________________

---

# cat

## What does it do?
The cat command (short for concatenate) lists the contents of a file. This is important when it comes to logs, as we generally want to look at them to find certain things.
Note: cat outputs/displays file contents to standard output (Graded)
_______________________________________________________________________

---

## Example

```bash
cat filename.log
    #The command above lists out the contents of "filename.log".
    cat filename.log | grep wordyouwanttolookup
        #The command above is a way to search for specific values in a file. For this example, we are search the log for the value wordyouwanttolookup, and it will output any line with that as a value.
```

### What happened?
When I did these commands, they listed the contents of the log files, and when I did the grep command, it gave me back all the lines that had the specific value I searched for in the log file. One thing I noticed is that the log files I used the command on had such output that I had to clear the terminal and do ls again in order to view the rest of the log names.
_______________________________________________________________________

_______________________________________________________________________

---

# less

## What does it do?
The less command lets you display the contents of a output one page at a time. This is helpful when it comes to logs and other such files.
Note: display the contents of a file or command output (Graded)
_______________________________________________________________________

---

## Example

```bash
less filename.log
    #When this command is input, it shows the content of a file (in this case the log), and displays it one page at a time, allowing you to view the contents more easily. 
    #Note: To exit the pages, just press q.
ps aux | less
    #When this command is input, it shows the content of the ps aux command one page at a time. 
less [option] filename
    #When this command is input, it does the same as the other commands, though it uses the flag that is input. 
    -N
        #Shows line numbers in output.
    -X
        #Leaves file contents on the screen after you exit.
    +F
        #Tells less to watch the file contents for changes. This is more useful when it comes to logs.
```

### What happened?
When I inputted the commands, I was able to view the log files I desired, but in a much more convient way. I am most likely going to be using this when it comes to viewing log files.
Note: tail displays the last lines of a file (Graded)
_______________________________________________________________________

_______________________________________________________________________

---

## How do I exit less?
To exit the less, just press q, and it quits out of the command.
_______________________________________________________________________

---

# tail

## What does it do?
The tail command lets you display the last part of one or multiple files, printing the last 10 lines (though it can be adjusted if needed).

_______________________________________________________________________

---

## Example

```bash
tail filename.log
    #When this command is input, it displays the last 10 lines of the file in question (usually a log).
tail [option] filename.log
    -n
        #When this command is input, it outputs the specific number of lines reqested. For example, tail -3 filename.log outputs the last 3 lines of the file, not last 10.
    -c
        #When this command is input, it outputs the last bytes of a file.
        #Note: Must specify a number of bites when using commands.
    -q
        #Displays the last 10 lines of the file in quiet mode, which surpress the filename header.
    -f 
        #Same as default, but is monitors the output in real time and updates if new lines are added.
```

### What is the difference?

`tail filename.log`
This command just displays the last 10 lines of the file/log in question.
_______________________________________________________________________

`tail -f filename.log`
This command does the same as above, but monitors the output in real time, and updates if any new lines are added.
_______________________________________________________________________

---

### What happened?
When I input these commands, they worked as intended, except for -c at first, because I didn't specify a number of bytes, but once I did it worked. I still need to try these commands out more, as I know these are going to be important in the future, so having a good understanding of them will help out a lot.
_______________________________________________________________________

_______________________________________________________________________

---

# Important Log Concepts

## Why are logs important in cybersecurity?
Logs are important in cybersecurity because they are how we monitor incidents and address them if needed. They are essential for soc analyst and other related positions, as if you don't understand them, how can you help prevent similar attacks in the future? 
_______________________________________________________________________

_______________________________________________________________________

---

## What kinds of information can logs contain?
Logs can contain information about standard processes, but also about incidents that have happened, irregularities, and other such answers.
_______________________________________________________________________

_______________________________________________________________________

---

# End of Day Reflection

## What command was easiest today?
This was the cat command, as I already knew of it before hand, so it was simple to use.
_______________________________________________________________________

---

## What command was hardest today?
Definitely the top and htop commands. Like yeah, using them is easy (just type the name of it), but understanding those tools where fairly difficult to understand.
_______________________________________________________________________

---

## What concept confused me the most?
The topic that confused me the most was the -c flag in the tail command, as I don't really understand when it says 'bytes'. I guess I need more practice with it to understand it.
_______________________________________________________________________

---

## What is one important thing I learned today?
The most important thing I learned today was definitely apt, as it is an essential part of the linux enviroment and is how packages are managed.
_______________________________________________________________________

---

## Which tool did I like the most?
Probably the kill command, because it is fun to terminate processes and such. Another one would be the top tool, as although I am still confused by it, I can see how important it is going to be for adminstration tasks. I am probably going to make some labs in the future when it comes to top and htop to learn how to use it in a professional enviroment. 
_______________________________________________________________________

---

## How comfortable do I feel with processes and package management? (1–10)

Score: 3/10

Why?
Am I much better at linux than I started, yes, but that doesn't mean I'm at all an expert. I want this stuff to become muscle memory for me by the end of the summer, which means I still have a long way to go. 
_______________________________________________________________________