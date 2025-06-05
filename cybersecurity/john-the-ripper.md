# John The Ripper

John The Ripper (often abbreviated as "John" or "Jtr") is one of the most popular and powerful tools for the password cracking and auditing of password safety. It is an open-source tool developed to test the robustness of passwords through Brute Force and Dictionary Attack attacks.

## What it is for

John The Ripper is mainly used for:

- **Safety auditing**: Testing the robustness of passwords in corporate systems
- **penetration testing**: evaluate safety during penetration tests
- **Password recovery**: recover forgotten passwords (on ownership systems)
- **Security training**: demonstrate the importance of robust passwords
- **Safety research**: analyze hashing and vulnerability algorithms


## Basic commands

### General syntax
```Bash
John [Options] [File_Password]
```

### Main commands

#### Basic Crack
```Bash
John Password_file # Crack with default dictionary
John - -Wordlist = Dictionary.txt Password_file # Crack with personalized dictionary
John - -Rules Password_file # Crack with mutation rules
```

#### specific mode
```Bash

John -Incremental password_file # incremental mode (Brute Force)
John - -Single Password_file # Single Crack mode
John -EXALERAL = Mode Password_file # external mode
```

## Parameters and main options

### Input/output options

| Parameter | Description | Example |
|--- |-------
| `-Show` | Show passwords already crap | `JOHN - -SHOW HASHES.TXT `|
| `-ESSERS = Login` | Cracca Only specific users | `JOHN -ESUS = Admin, Root Hashes.txt` |

### Attack mode

| Parameter | Description | Example |
|--- |-------
| `--Single` | Single Crack mode (Use User Info) | `John - -Single Passwd` |
| `--Wordlist` | Attack with dictionary | `John - -Wordlist = DicT.Txt Hashes.txt` |
| `--incretional`| Brute Force incremental | `John -Incremental: Alpha Passwd` |
| `---Exalal = Mode` | Use Personalized external mode | `JOHN -EXALERAL = FILTER_ALPHA PASSWD`|

### Rules and mutations

| Parameter | Description | Example |
|--- |-------
| `--Rules` | Apply mutation rules | `John - -Rules - -Wordlist = dict.txt passwd` |
| `--Rules = Sectionis` | Use specific rules| `John - -Rules = wordlist passwd` |

### format and hash

| Parameter | Description | Example |
|--- |-------
| `--Format = format` | Specifies the hash format | `John - -Format = MD5 Hashes.Txt` |
| `-List = formats` | List of all supported formats | `John -List = formats` |

### Sessions and restore

| Parameter | Description | Example |
|--- |-------
| `--Session = Name` | Appoint the session | `JOHN -SESSION = Test1 Passwd` |
| `- Restore a session` | `John -Verore = Test1` |
| `-Status = Name` | Exhibition of the session status | `John -Status = Test1` |

### Performance and optimization

| Parameter | Description | Example |
|--- |-------
| `--Fork = n`| USA n Parallel processes | `John - -Fork = 4 Passwd` |
| `-Node = m/n`| Distributed: node m of n | `John -Node = 1/4 Passwd` |