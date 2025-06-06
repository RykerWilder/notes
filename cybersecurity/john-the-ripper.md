# John The Ripper

John The Ripper (often abbreviated as "John" or "Jtr") is one of the most popular and powerful tools for the password cracking and auditing of password safety. It is an open-source tool developed to test the robustness of passwords through Brute Force and Dictionary Attack attacks.

## What John The Ripper is used for

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

#### Basic Crack
```Bash
John Password_file                                  # Crack with default dictionary
John - -Wordlist = Dictionary.txt Password_file     # Crack with personalized dictionary
John - -Rules Password_file                         # Crack with mutation rules
```

#### specific mode
```Bash
John -Incremental password_file         # incremental mode (Brute Force)
John - -Single Password_file            # Single Crack mode
John -EXALERAL = Mode Password_file     # external mode
```

## Parameters

| Parameter | Description |
|--- |-------
| `-Show` | Show passwords already crap |
| `-ESSERS = Login` | Cracca Only specific users |
| `--Single` | Single Crack mode (Use User Info) |
| `--Wordlist` | Attack with dictionary |
| `--incretional`| Brute Force incremental |
| `---Exalal = Mode` | Use Personalized external mode |
| `--Rules` | Apply mutation rules |
| `--Rules = Sectionis` | Use specific rules|
| `--Format = format` | Specifies the hash format |
| `-List = formats` | List of all supported formats |
| `--Session = Name` | Appoint the session |
| `- Restore a session` |
| `-Status = Name` | Exhibition of the session status |
| `--Fork = n`| USA n Parallel processes |
| `-Node = m/n`| Distributed: node m of n |