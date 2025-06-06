# Hydra

Hydra is an open-source penetration testing tool used to perform brute-force attacks against remote authentication services. It's one of the fastest and most flexible tools for testing password strength across various network protocols.

---

## What Hydra is Used For

- **Password Auditing**: Testing the strength of corporate passwords  
- **Penetration Testing**: Evaluating security during penetration tests  
- **Security Assessment**: Identifying weak credentials in systems  
- **Brute Force Attacks**: Automated attacks against login services  
- **Dictionary Attacks**: Using wordlists to crack passwords  
- **Compliance Testing**: Verifying compliance with security policies  
- **Red Team Operations**: Simulating real-world attacks  


## Supported Protocols

Hydra supports over 50 protocols, including:

- **Web**: HTTP, HTTPS, HTTP-FORM, HTTP-GET, HTTP-POST
- **Database**: MySQL, PostgreSQL, Microsoft SQL, Oracle, MongoDB
- **Remote Access**: SSH, Telnet, RDP, VNC
- **Mail**: POP3, IMAP, SMTP
- **File Transfer**: FTP, FTPS, SFTP
- **Directory Services**: LDAP, SMB, Kerberos
- **Altri**: SNMP, Cisco, RouterOS, Redis, ecc.

---

## General Syntax

```bash
hydra [options] [target] [protocol]
```

### Basic Command Structure
```bash
hydra -l username -p password target_ip protocol
hydra -L userlist.txt -P passlist.txt target_ip protocol
```

### Basic commands

```bash
hydra -l admin -P passwords.txt ssh://192.168.1.1 -t 4 -V                  # SSH attack
hydra -L users.txt -P passwords.txt ftp://192.168.1.1 -o results.txt       # FTP attack with users list
hydra -l admin -P passwords.txt 192.168.1.1 http-post-form "/login.php:user=^USER^&pass=^PASS^:Invalid password" -V # HTTP POST attack
hydra -l root -P passwords.txt mysql://192.168.1.1 -V                      # MySQL attack
hydra -L users.txt -P passwords.txt rdp://192.168.1.1 -t 10 -V             # RDP attack
hydra -l admin -P passwords.txt 192.168.1.1 http-get -s 8080               # Custom port attack
hydra -L users.txt -P passwords.txt -M targets.txt ssh -V                  # Attack with multiple targets
```

---

## Parameters

| Command               | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| `-l <username>`       | 	Specifies a single username.                                              |
| `-L <user_list>`      | File containing a list of usernames.                                        |
| `-p <password>`       | 	Specifies a single password.                                              |
| `-P <password_list>`  | 	File containing a list of passwords.                                      |
| `-s <port>`           | 	Custom port (if different from default).                                  |
| `-t <threads>`        | 	Number of parallel threads (default: 16).                                 |
| `-v` / `-V`           | 	Verbose mode (-V shows each attempt).                                     |
| `-f`                  | 	Stop attack after first valid login.                                      |
| `-o <file>`           |	Save results to a file.                                                   |
| `-M <target_list>`    | 	File with a list of targets (for multiple targets).                       |
| `-u`                  | Try username as password (reverse attack).                                  |
| `-e nsr`              |Try empty password (n), username as password (s), reverse (r).               |
| `-C <credenziali_file>` | File with username:password pairs (column format).                        |