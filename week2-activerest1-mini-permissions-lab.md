# Mini Linux Permission Lab

## Goal
Practice:
- directories
- files
- permissions
- ownership
- navigation

**Estimated Time:** 15–20 minutes

---

# Step 1 — Create Lab Structure

## Commands
```bash
mkdir ~/minilab
    #This command makes a new directory in the user's home directory called minilab.
cd ~/minilab
    #This command changes the current working directory the user is in to the minilab directory. 
mkdir notes scripts logs
    #This command makes multiple subdirectories called notes, scripts, and logs.
```

## Goal
Create a small directory structure for the lab.

---

# Step 2 — Create Files

## Commands
```bash
touch notes/info.txt
    #This command creates a file named info.txt in the notes subdirectory.
touch scripts/test.sh
    #This command creates a file named test.sh in the scripts subdirectory.
touch logs/system.log
    #This command creates a file named system.log in the log subdirectory.
```

## Goal
Create one file inside each subdirectory.
Note: Combined all the commands into one to make it easier to type.
---

# Step 3 — Change Permissions

## Commands
```bash
chmod 700 logs
    #Changes permissions of the logs directory to have it where only the owner has read, write, and execute permissions.
chmod 755 scripts
    #Changes permissions of the scripts directory to have it where the owner has all permissions while group and others only have read and execute permissions.
chmod 644 notes/info.txt
    #Changes permissions of the info.txt file to where the owner has read and write permissions, while the group and others have only read permissions.
chmod u+x scripts/test.sh
    #Changes permissions of the test.sh file to give the owner of the file execute permissions.
```

## Goal
Practice:
- numeric permissions
- symbolic permissions
- executable permissions

---

# Step 4 — Verify Permissions

## Commands
```bash
ls -la
    drwxrwxr-x 5 vboxuser vboxuser 4096 May 25 02:54 .
    drwxr-x--- 24 vboxuser vboxuser 4096 May 25 02:54 ..
    drwx------ 2 vboxuser vboxuser 4096 May 25 02:56 logs
    drwxrwxr-x 2 vboxuser vboxuser 4096 May 25 02:56 notes
    drwxr-xr-x 2 vboxuser vboxuser 4096 May 25 02:56 scripts
ls -la notes
    -rw-r--r-- 1 vboxuser vboxuser 0 May 25 02:56 info.tx
ls -la scripts
    -rwxrw-r-- 1 vboxuser vboxuser 0 May 25 02:56 test.sh
ls -la logs
    -rw-rw-r-- 1 vboxuser vboxuser 0 May 25 02:56 system.log
```

## Goal
Read and understand the permission strings.
Note: Did not copy the hidden files for the subdirectories, as adds nothing to the answer.
## Questions
- Which files are executable?
    The only file that is executable (execute permissions) is test.sh, but the directories are executible to some extent. 
- Which directories are private?
    The directory that is private completely is the logs directory.
- Which files are read-only for others?
    The info.txt, test.sh, and system.log are all technically read only for others. 
---

# Step 5 — Practice Moving & Copying

## Commands
```bash
cp notes/info.txt notes/info-backup.txt
    #This command copies the contents of info.txt and pastes them in a copy called info-backup.txt.
mv logs/system.log notes/
    #This command moves the system.log file from the logs directory to the notes directory.
mv notes/info-backup.txt logs/
    #This command moves the info-backup.txt file from the notes directory to the logs directory.
```

## Goal
Practice:
- copying files
- moving files
- reorganizing directories

---

# Reflection Questions

Answer these after finishing:

- What permission string did `chmod 700` create?
    drwx------ for the logs directory.
- What does `u+x` do?
    The u+x permissions give the owner execute permissions.
- Which file became executable?
    The test.sh file was the only file that had execute permissions, becoming executable.
- What is the difference between `cp` and `mv`?
    The cp command copies the contents of a file or directory and pastes them into the file or directory of choice, while the mv command moves the contents of a file or directory to the file or directory of choice.
- Which command helped verify permissions?
    The ls -la command helped verify permissions of files and directories.