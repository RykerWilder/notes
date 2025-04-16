# Basic linux commands

When working with Linux, the terminal is a powerful tool for interacting with the operating system. Unlike the graphical interface (where you use the mouse to navigate among folders), here you use text commands.

**Index**
- [File navigation and management](#file-navigation-and-management)
- [Permission management](#permission-management)
- [Process management](#process-management)
- [Searching and manipulating text](#searching-and-manipulating-text)
- [Networks e connections](#networks-and-connections)

## File navigation and management

### pwd (Print Working Directory)

```bash
pwd   # Displays the path of the current directory
```

---

### ls (list)

```bash
ls      # Lists the files and directories in the current location.
ls -l   # Show details (permissions, owner, size)
ls -a   # Also show hidden files (starting with .)
```

---

### cd (change directory)


```bash
cd path/absolute   # Go to the specified directory
cd ..              # Go back to parent directory
cd ~               # Go back to home
```

---

### mkdir (make directory)

```bash
mkdir folder_name # Create a new directory
```

---

### rmdir (remove directory)

```bash
rmdir empty_folder # Delete an empty directory
```

---

### rm (remove)

```bash
rm file.txt          # Delete a specific file by name
rm -r folder_name    # Delete a folder and its contents recursively
rm -f folder_name    # Force delete without asking for confirmation
```

---

### touch

```bash
touch new_file.txt  # Create a new empty file or update the modification date
```

---

### cat (concatenate)

```bash
cat file.txt  # Displays the contents of a file
```

---

### nano

```bash
nano file.txt  # Text editor in the terminal
```

---

## Permission management

### chmod (change mod)
Changes the permissions of a file/directory.

```bash
chmod +x script.sh  # Adds execute permission to a file
```

---

### chown (change owner)

```bash
chown owner:group file.txt  # Change owner/group of a file.
```

---

## Process management
A process is an activity that the computer is performing at a particular time.

### ps (process status)
Shows running processes.
```bash
ps             # Current user's processes
ps aux         # All running processes
ps -ef         # Full list of processes
ps -u [user]   # Processes of a specific user
```

---

### top/htop
Interactive process monitoring.
```bash
top     # Dynamic interface (press 'q' to exit)
htop    # Improved version (if not installed: `sudo apt install htop`)
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
kill [PID]       # Send SIGTERM (gentle termination)
kill -9 [PID]    # Force shutdown (SIGKILL)
```

---

### killall/pkill
Kill processes by name.
```bash
killall firefox   # Kill all Firefox processes
pkill -f "name"   # Kill processes matching name
```

---

### nice/renice
Change the priority of a process.
```bash
nice -n 10 ./script.sh   # Start with low priority (value -20 to 19)
renice -n 5 -p [PID]     # Change the priority of an existing process
```
---

## Searching and manipulating text

### grep
Search for text in a file.\

```bash
grep "error" file.txt
```

---

### find
Search for files or directories.

```bash
find /home -name "*.txt"
```

---

## Networks and connections

### ping
Tests the connectivity of a host.

```bash
ping google.com
```

---

### ifconfig
Displays information about network interfaces.

---

### ssh
Secure remote connection.

```bash
ssh user@server
```

---

### scp
Copy files via SSH.

```bash
scp file.txt user@server:/path
```

---

### wget/curl
Download files from the internet

```bash
wget https://example.com/file.zip
```