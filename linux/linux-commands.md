# Basic linux commands

When working with Linux, the terminal is a powerful tool for interacting with the operating system. Unlike the graphical interface (where you use the mouse to navigate among folders), here you use text commands.

**Index**
- [Utils](#utils)
- [File navigation and management](#file-navigation-and-management)
- [Permission management](#permission-management)
- [Process management](#process-management)
- [Searching and manipulating text](#searching-and-manipulating-text)
- [Networks e connections](#networks-and-connections)

---
---
## Utils
---
---
### man
Command manual.
```bash
man command              # Show the official manual
man -k "keyword"         # Search the manuals (equivalent to `apropos`)
```

---

### whatis 
Short description of a command.
```bash
whatis ls            # Show "ls - list directory contents"
```

---

### --help
Quick guide of a command options.
```bash
ls --help            # Command options
```

---

### history
Show history of executed commands.
```bash
history       # Full list
history 10    # Last 10 commands
!42           # Execute command with ID 42 from history
!!            # Repeat last command
```

### whoami
Display the current user
```bash
whoami
```

---
---
## File navigation and management
---
---
### pwd (Print Working Directory)
Shows your current directory path.
```bash
pwd   # Displays the path of the current directory
```

---

### ls (list)
Lists directory contents.
```bash
ls      # Basic listing
ls -l   # Long format (permissions, owner, size, modification time)
ls -a   # Include hidden files (starting with '.')
ls -lh  # Human-readable sizes (KB, MB, GB)
```

---

### cd (change directory)
Navigates between directories.
```bash
cd /path/to/dir  # Absolute path
cd folder        # Relative path
cd ..            # Parent directory
cd ~ or cd       # Home directory
cd -             # Previous directory
```

---

### mkdir (make directory)
Creates new directories.
```bash
mkdir folder            # Single directory
mkdir -p parent/child   # Creates nested directories
```

---

### rmdir (remove directory)
Removes **empty** directories.
```bash
rmdir empty_folder # Delete an empty directory
```

---

### rm (remove)
Deletes files/directories.
```bash
rm file.txt          # Delete file
rm -r folder/        # Recursive delete (directories + contents)
rm -f file           # Force delete (no confirmation)
```

---

### touch
Creates empty files or updates timestamps.
```bash
touch file.txt       # Creates if doesn't exist
touch existing.txt   # Updates modification time
```

---

### cat (concatenate)
Displays or combines file contents.
```bash
cat file.txt                # Show content
cat file1 file2 > combined  # Combine files
```

---

### nano
Simple terminal text editor.
```bash
nano file.txt  # Text editor in the terminal
```

---
---
## Permission management
---
---

### chmod (change mod)
Changes the permissions of a file/directory.

```bash
chmod u+rwx file   # Add read (r), write (w), execute (x) permissions to user (u)
chmod g-rw file    # Remove read and write permissions from group (g)
chmod o=x file     # Set execute only for others (o)
chmod a+w file     # Add write permissions to everyone (a = all)
```

```bash
chmod 755 file   # rwxr-xr-x (7=rwx for user, 5=r-x for group and others)
chmod 644 file   # rw-r--r-- (6=rw- for user, 4=r-- for group and others)
```

---

### chown (change owner) / chgrp (change group)
Changes file ownership.
```bash
chown user:group file   # Change both user and group
chown user file         # Change only user
chgrp group file        # Change only the group
```

---

### umask
Set default permissions.
```bash
umask 022   # Set default permissions (e.g. 755 for directories, 644 for files)
umask       # Show the current value
```

---
### SUID (Set User ID)
Execute the file with owner permissions.
```bash
chmod u+s file     # Set SUID
chmod 4755 file    # Set SUID to numeric format (4xxx)
```

---

### SGID (Set Group ID)
Execute the file with group permissions.
```bash
chmod g+s file      # Set SGID
chmod 2755 file     # Set SGID to numeric format (2xxx)
```

---
---
## Process management
---
---
A process is an activity that the computer is performing at a particular time.

### ps (process status)
Shows running processes.
```bash
ps                 # Current user's processes
ps aux             # All running processes
ps -ef             # Full list of processes
ps -ef | grep ssh  # Filter processes
ps -u [user]       # Processes of a specific user
```

---

### top/htop
Interactive process monitoring.
```bash
top    # Built-in process monitor
htop   # Enhanced version (install with sudo apt install htop)
```

---

### &
Runs a command in the background.
```bash
firefox &    # Starts Firefox in the background
```

---

### kill
Ends a process.
```bash
kill 1234          # Graceful termination (SIGTERM)
kill -9 1234       # Force kill (SIGKILL)
```

---

### killall/pkill
Kill processes by name.
```bash
killall firefox    # All Firefox instances
pkill -f "pattern" # Processes matching pattern
```

---

### nice/renice
Change the priority of a process.
```bash
nice -n 10 command  # Start with low priority
renice 5 -p 1234    # Change running process priority
```
---
---
## Searching and manipulating text
---
---
### grep
Searches text patterns.
```bash
grep "text" file.txt             # Search for "text" in file.txt
grep -i "text" file.txt          # Ignore case
grep -r "text" /folder           # Recursive search
grep -v "text" file.txt          # Show lines that do NOT contain "text"
grep -c "text" file.txt          # Count occurrences
grep -A 3 -B 2 "text" file.txt   # Show 3 lines after and 2 before the match
```

---

### tr
Replaces or deletes characters.
```bash
tr 'a-z' 'A-Z' < file.txt     # Converti in maiuscolo
tr -d '\n' < file.txt         # Rimuovi a capo
```

---

### find
Searches for files.
```bash
find /home -name "*.txt"      # By name
find . -size +1M -type f      # Files >1MB
find /var/log -mtime -7       # Modified in last 7 days
```

---
---
## Networks and connections
---
---
### ping
Tests network connectivity.
```bash
ping example.com
ping -c 4 example.com  # Limit to 4 packets
```

---

### ifconfig
Network interface configuration.
```bash
ifconfig        # Legacy tool (deprecated on many systems)
ip addr show    # Modern replacement
```

---

### ssh
Remote secure login.
```bash
ssh user@host            # Basic connection
ssh -p 2222 user@host    # Custom port
```

---

### scp
Copies files over SSH.
```bash
scp file.txt user@host:/path/  # Upload
scp user@host:/file.txt ./     # Download
```

---

### wget/curl
Downloads files.
```bash
wget https://example.com/file.zip  # Simple download
curl -O https://example.com/file   # More flexible alternative
```