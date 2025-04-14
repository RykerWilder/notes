# Basic linux commands

## File navigation and management

#### pwd (Print Working Directory)
Displays the path of the current directory.

---

#### ls (list)
Lists the files and directories in the current location.

show details (permissions, owner, size):
```bash
ls -l
```

also show hidden files (starting with .):
```bash
ls -a 
```

---

#### cd (change directory)

go to the specified directory:
```bash
cd path/absolute 
```

go back to parent directory:
```bash
cd .. 
```

go back to home:
```bash
cd ~ 
```

---

#### mkdir (make directory)

create a new directory:
```bash
mkdir folder_name
```

---

#### rmdir (remove directory)

delete an **empty** directory:
```bash
rmdir empty_folder
```

---

#### rm (remove)
Deletes files or directories.

delete a specific file by name:
```bash
rm file.txt
```

delete a folder and its contents **recursively**:
```bash
rm -r folder_name
```

force delete without asking for confirmation:
```bash
rm -f folder_name
```

---

#### touch
Create a new empty file or update the modification date.

```bash
touch new_file.txt
```

---

#### cat (concatenate)
Displays the contents of a file.

```bash
cat file.txt
```

---

#### nano
Text editor in the terminal.

```bash
nano file.txt
```

---

## Permission management

#### chmod (change mod)
Changes the permissions of a file/directory.

adds execute permission to a file:
```bash
chmod +x script.sh
```

---

#### ps (process status)
Displays active processes.

displays all running processes:
```bash
ps aux
```