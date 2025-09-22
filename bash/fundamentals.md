# Bash fundamentals

Bash scripting is writing a series of Linux/Unix commands in a file to automate tasks. It saves times, reduces errors, and is used i cybersecurity. DevOps and system admin works.

### Variables

```bash
name="Ryker Wilder"
echo "Welcome, $name!"
```

### Conditional Statements (if-else)

```bash
age=18

if [$age -ge 18]; then
    echo "You are and adult."
else
    echo "You are underage"
fi
```

### Loops

```bash
for i in 1 2 3
do 
    echo "Number: $i"
done
```

To run a bash script insert in terminal **bash file.sh**.
To make a script executable you have to change file permission with **chmod +x file.sh**.
After you can run the script with **./file.sh**