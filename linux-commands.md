# Basic linux commands

### pwd (Print Working Directory)
displays the path of the current directory.

---

### ls (list)
lists the files and directories in the current location.

Show details (permissions, owner, size):
```bash
ls -l
```

Also show hidden files (starting with .):
```bash
ls -a 
```

---

### cd (change directory)

Go to the specified directory:
```bash
cd path/absolute 
```

Go back to parent directory:
```bash
cd .. 
```

Go back to home:
```bash
cd ~ 
```

---

### mkdir (make directory)

Create a new directory:
```bash
mkdir folder_name
```

---

### rmdir (remove directory)

delete an **empty** directory:
```bash
rmdir empty_folder
```

---

### rm (remove)
deletes files or directories.

Delete a specific file by name:
```bash
rm file.txt
```

Delete a folder and its contents **recursively**:
```bash
rm -r folder_name
```

Force delete without asking for confirmation:
```bash
rm -f folder_name
```

---

### touch
create a new empty file or update the modification date.

```bash
touch new_file.txt
```

---

### cat (concatenate)
displays the contents of a file.

```bash
cat file.txt
```

---

### nano
text editor in the terminal.

```bash
nano file.txt
```

---

### chmod (change mod)
changes the permissions of a file/directory.

adds execute permission to a file:
```bash
chmod +x script.sh
```

---

### ps (process status)
displays active processes.

displays all running processes:
```bash
ps aux
```