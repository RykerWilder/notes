# Medusa

Medusa is a penetration testing tool designed to perform brute force attacks against network services that require authentication. Medusa uses a modular approach to systematically test username and password combinations against target services. The tool is multi-threaded, allowing multiple login attempts to be performed simultaneously to increase efficiency.

## General Syntax

```bash
medusa -h [target] -u [username] -p [password] -m [module]
```

### BasicCommands
```bash
medusa -H targets.txt -U users.txt -P passwords.txt -M ssh -t 16 -e ns -v 5 -O ssh_results.txt   # SSH attack with custom lists
medusa -h 10.0.0.1 -u admin -P rockyou.txt -M http -m "DIR:/private" -v 3                        # HTTP Basic Auth attack with verbosity
```

## Parameters

| Command               | Description                                     |
|-----------------------|-------------------------------------------------|
| `-h <host>`           | Target (IP/hostname) or host list file (-H)     |
| `-H <file>`           | File with list of targets (1 per line)          |
| `-u <user>`           | Single username or file (-U)                    |
| `-U <file>`           | File with list of usernames                     |
| `-p <pass>`           | Single password or file (-P)                    |
| `-P <file>`           | File with list of passwords                     |
| `-M <module>`         | Module to use (e.g. ssh, ftp, http)             |
| `-t <threads>`        | Parallel threads (default: 8)                   |
| `-T <hosts>`          | Hosts tested in parallel (default: 1)           |
| `-f`                  | Stop on first valid login                       |
| `-F`                  | Stop on first compromised service               |
| `-r <sec>`            | Delay between retries (seconds)                 |
| `-R <n>`              | Reconnection attempts                           |