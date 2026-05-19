# Linux Commands for Beginners Notes

## What is the terminal?

The terminal is the interface where you type commands in order to interact with the operating system. 

Another name for the terminal is command line.

Why is the terminal important in Linux/cybersecurity?

The terminal is important in linux/cybersecurity because it is how we execute commands and actions. It is the main way we interact with linux
---

# Command Notes

## pwd
print working directory
### What does it do?
The pwd tells you what working directory you are currently in.
_______________________________________________________________________

### Example

```bash
pwd
```
### What happened when I used it?
When I used the command, it told my the working directory I was in (/home/vboxuser).
_______________________________________________________________________

### My own explanation
The pwd command tells you where you currently are.
_______________________________________________________________________

---

## ls
list storage
### What does it do?

The ls command lists the folders in the current working directory

### Example

```bash
ls
    #lists things in the current directory
ls -l
    #lists things in the current directory long ways
ls /home
    #lists things in the specified directory
ls /
    #lists things in the entire file system
ls /home/vboxuser
    #lists things in the specified directory
ls -R
    #lists the directory structure
```
ls /
### What happened when I used it?
Normal ls listed all the files in the current working directory. 
    So if you are in a home directory and do ls, it will list everything in the home directory.
The ls / command list all of the files at the very beginning of the hard drive.
    If text is blue, it is a folder.
    If text is white, it is a file.
    If text is green, it is a program or binary. 
    Permission strings can tell what it is all the time.
        d is a directory
        Example:
            drwxr-xr-x would be a directory
        - is a file and/or program
        Example:
            -rwxr-xr-x would be a file/program
        l is a link
            lrwxrwxrwx would be a link
The ls /home command listed all the files in the home directory.
The ls -l / had every item on a line.
The ls -l /home listed every item in the home directory. 
When I did ls -l /home/vboxuser, it listed every item in the vboxuser directory in the home directory, basically starting a path. 
~ is your home directory.
The home directory has all the users in it, and from you can select what user.
List of all directories:
    bin: has runnable programs
    boot: has all the files required for booting the os
    dev:
    etc: configuration files
    home:
    lib:
    lib64:
    lost+found:
    media: media stuff
    mnt: mount manually stuff
    opt:
    proc:
    root: Is the most powerful user in a linux system.
    run:
    sbin:
    sys:
    tmp:
    usr:
    var:
### My own explanation
The ls command list all the files for a directory. / is the name of the filesystem.
If you do something like ls /home/vboxuser, it autonmatically goes to that file. And if you do something lile ls -l /home/vboxuser, then it will list all of it long ways.
---

## cd

### What does it do?
The command lets you go into a specific directory.
_______________________________________________________________________

### Example

```bash
cd Documents
cd /sys
cd a/b/
    #gets you to the specific directory
cd ..
    #gets you to the parent directory of the directory you were in
```

### What happened when I used it?
When I did cd /sys, it went into the sys directory, but when I did it without /, it said no such file or directory.
_______________________________________________________________________

### My own explanation
The cd command lets you go into a specific directory.
_______________________________________________________________________

---

## clear

### What does it do?
This command clears the terminal to the beginning. Can also use ctrl L.
_______________________________________________________________________

### Example

```bash
clear
```

### What happened when I used it?
It cleared all the lines there were on the terminal back to the beginning.
_______________________________________________________________________

### My own explanation
The clear command clears everything on screen and declutters the terminal.
_______________________________________________________________________

---

## mkdir
Make directory
### What does it do?
This command allows you to make a directory/sub directory when needed.
_______________________________________________________________________

### Example

```bash
mkdir practice-folder
    #creates directory
cd /home/vboxuser/practicefolder
mkdir /home/vboxuser/practicefolder/notes
    #creates subdirectory
mkdir -p practicefolder/names
    #creates directory and subdirectory
mkdir --parents practicefolder/names
    #full version of command from above
mkdir -p practicefolder/{item1,item2,item3}
    #creates directory and multiple subdirectories.
mkdir -p a/b/c/d/e
    #creates path of directories
```

### What happened when I used it?
When I used the command, I was able to create a directory in the said directory I want. I was also able to create multiple subdirectories as well. Using the the -p modifier (also known as --parents) lets you create a directory and a subdirectory at once. The command with the {} let me create a directory and a subdirectory as well, though it did list 2 of the subdirectories outside of the directory for some reason.
_______________________________________________________________________

### My own explanation
The mkdir command and modifiers lets you create directories and sub directories.
_______________________________________________________________________

---

## touch

### What does it do?
It is the easiest way to create empty files on linux.
_______________________________________________________________________

### Example

```bash
touch notes.txt
touch practicefile
    #created file
touch practicefile
    #command used again changed the timestamp of the file
cat > abc.txt
    #lets you type in the file you created.
```

### What happened when I used it?
When I used this command, it created an empty file in my directory. When I used it again, it changed the timestamp of the file. 
_______________________________________________________________________

### My own explanation
The touch command is used from creating files and changing the timestamp on those files.
_______________________________________________________________________

---

## rm

### What does it do?
The rm command lets you remove both files and directories.
_______________________________________________________________________

### Example

```bash
rm notes.txt
    #lets you remove the specified file
rmdir {john,
    #lets you remove the specified directory
rmdir -p a/b/c/d/e
    #lets you remove the directory path all at once, as without the -p modifier, it will only remove the one at the end
rmdir -pv a/b/c/d/e
    #does same thing as above but tells you what is happening
rm -r a
    #removes both directories and files, starting with the parent directory.
        #Note: when trying to remove a directory contain files, always make sure to just put the first directory, as something like rm -r a/b will consider b to be the parent directory, therefore not deleting a with it.
rm -rv a
    #does same thing as above but tells you what is happening
```

### What happened when I used it?
The first four commands worked as intended, removing what I specified. The 5th command took some time to work, but that was because of things before that I incorrectly put in unrelated to the command, and when using it again it worked. 
_______________________________________________________________________

### My own explanation
The rm and rmdir commands let you remove both directories and files when needed. The -r modifier lets you delete the whole directory structure, not just one thing.
_______________________________________________________________________

---

## cp
copy
### What does it do?
The cp command is meant to copy files and directories in linux.
_______________________________________________________________________

### Example

```bash
cp practicefile practicecopy
    #The contents of practicefile were copied over the content of practicecopy.
cp options source destination
    #The cp command specifies that you want to copy the source, the options modifier specifies what option you want to do with the source, the source modifier is what you are copying, and the destination modifier is where you want it to go.
cp practicefile2 pics
    #The contents of practicefile2 were copied and a copy of the file was pasted into the pics directory.
cp practicecopy practicefile2 pics
    #Same thing as before, but with 2 files into the directory.
cp -i practicecopy practicefile2 pics
    #The -i options lets you decide if you want to overide something or not, prompting you with a y or n answer.
cp /home/vboxuser/specificdir/specificfile /home/vboxuser/specificdir/specificfile .
    #Pastes the files from a different directory into the one we are currently in.
cp -R specificdir specificdir2
    #Copies the contents of specificdir and pastes into specificdir2.
    #Note: cp -r specificdir specificdir2 copies the directory as well the contents into the directory chosen.
```

### What happened when I used it?
When I used the cp command, it let me copy files and paste them into other directories/files. When I did the 5th command argument, it prompted me if I wanted to overide the specific files or not. 
_______________________________________________________________________

### My own explanation
The cp command lets you copy files and directories into other files and directories.
_______________________________________________________________________

---

## mv
Move and rename
### What does it do?
The mv command lets you move and rename files in linux.
_______________________________________________________________________

### Example

```bash
mv options source destination
    #The options modifier lets you decide any specific options you want to do with the source, the source it what file/directory you are applying it to, and the destination file is where it is going.
mv demofile filedemo
    #This argument renamed the file "demofile" to "filedemo".
mv cat demofile
    #This argument transferred the content of cat into a new file called demofile.
mv demofile demodir
    #This argument trandferred the demofile into the demo directory.
    #Note: If there is a file in the directory you want to move the file to, then it will be overridden.
mv -i demofile demodir
    #Same thing as above except it will prompt you with a yes or no answer if you want to do it or not.
mv clap demo
    #Moves directory into another directory (files included).
mv currentdir newdir
    #Moves all contents of the currentdir into the newdir (basically renaming).
mv -v
    #Explains what the argument just did.
```

### What happened when I used it?
When I used the command, it would either moves the contents of the directories and files or the directories and files themselves to the specified location or would rename the source specified.
_______________________________________________________________________

### My own explanation
The mv command is used for moving and renaming files and directories.
_______________________________________________________________________

---

# Practice Commands Section

Try these commands yourself and write what happened.

## Practice 1

```bash
mkdir test-folder
```

Result:
The Command created a directory named test-folder in the vboxuser directory.
_______________________________________________________________________

---

## Practice 2

```bash
cd test-folder
```

Result:
The command changed the working directory to be test-folder instead of vboxuser.
_______________________________________________________________________

---

## Practice 3

```bash
touch practice.txt
```

Result:
The command created a file named practice.txt in the test-folder directory.
_______________________________________________________________________

---

## Practice 4

```bash
ls
```

Result:
The command listed the contents of the test-folder directory.
_______________________________________________________________________

---

## Practice 5

```bash
cp practice.txt copied.txt
```

Result:
The command copied the contents of practice.txt and pasted it into a new file called copied.txt
_______________________________________________________________________

---

## Practice 6

```bash
mv copied.txt moved.txt
```

Result:
The command moved the contents of the copied.txt file and placed them in a new file called moved.txt, deleting copied.txt in the process. This is also known as renaming.
_______________________________________________________________________

---

## Practice 7

```bash
rm moved.txt
```

Result:
The command removed the file moved.txt from the test-folder directory.
_______________________________________________________________________

---

# End of Day Reflection

## Which command was easiest?
The pwd was the easiest, as it had only one function, to print what working directory I was in.
_______________________________________________________________________

---

## Which command confused me the most?
Probably the mv command for the fact that the video explaining it worded some stuff confusingly, but it wasn't really that bad and is pretty understandable now that I know it.
_______________________________________________________________________

---

## What do I need more practice with?
I need more practice with understanding all the options, as they were implemented as much as I thought they were going to be, and I need to know them all sooner than later.
_______________________________________________________________________

---

## What is one thing I learned today?
I learned about all the commands that are necessary to navigate the terminal, which is very important. I am hoping this all becomes muscle memory soon enough.
_______________________________________________________________________

---

## How comfortable do I feel in Linux right now? (1–10)

Score: 3/10

Why?
While yes, I do feel comfortable navigating a linux terminal now, there is still far more I need to learn before I can confidently say I am fully comfortable with the os.
_______________________________________________________________________