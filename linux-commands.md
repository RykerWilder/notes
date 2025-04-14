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