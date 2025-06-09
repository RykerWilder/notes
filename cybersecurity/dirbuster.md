# DirBuster

DirBuster is a web directory and file enumeration tool developed by OWASP. It is designed to find hidden directories and files on web servers through brute force attacks using predefined or custom wordlists.

## How Dirbuster Works

DirBuster works by sending HTTP requests to a web server to test the existence of directories and files based on lists of common names. The tool analyzes the server's responses to determine whether a resource exists or not.

## Basic Commands

```bash
dirb http://target.com                                         # Scan with default wordlist
dirb http://target.com /usr/share/wordlists/dirb/common.txt    # Scan with custom wordlist
dirb http://target.com /usr/share/wordlists/dirb/common.txt -X .php,.html,.txt # Scan with specific extensions
dirb http://target.com -u username:password                    # HTTP Basic Authentication
dirb http://target.com -c "SESSIONID=abc123"                   # Use cookies
dirb http://target.com -H "User-Agent: Mozilla/5.0"            # Custom headers
dirb http://target.com -R                                      # Recursive scanning
dirb http://target.com -p http://127.0.0.1:8080                # Use proxy
```

## Parameters
| Parameter | Description | Values ​​|
|--------------------|-------------------------------------------------------------------------------------------------|---------------------------------------|
| `-u` / `--url` | URL of the target to scan | `http://example.com` |
| `-l` / `--wordlist` | Path to the wordlist file containing the directories/files to test | `/usr/share/wordlists/dirb/common.txt`|
| `-e` / `--ext` | Extensions of the files to test (separated by commas) | `php,html,asp` |
| `-t` / `--threads` | Number of threads to use (speeds up scanning) | `20` |
| `-r` / `--recursive`| Enable recursive scanning of directories | No value (boolean flag) |
| `-H` / `--header` | Adds a custom HTTP header (e.g. for Cookies or User-Agent) | `"Cookie: PHPSESSID=1234"` |
| `-X` / `--method` | Specifies the HTTP method to use (default is GET) | `POST` |
| `-s` / `--status` | Show only results with specific HTTP status codes | `200,301,403` |
| `-o` / `--output` | Save results to a file | `report.txt` |
| `-v` / `--verbose` | Show verbose output during scan | No value (boolean flag) |
| `-p` / `--proxy` | Use a proxy for requests (format `host:port`) | `127.0.0.1:8080` |
| `-a` / `--useragent`| Set a custom User-Agent | `"Mozilla/5.0"` |
| `-c` / `--cookies` | Add cookies to the request (format `name=value`) | `session=abcd1234` |
| `-z` / `--delay` | Set a delay (in milliseconds) between requests to avoid rate-limiting | `100` |
| `-P` / `--postdata` | Data to send in the body for POST requests | `"user=admin&pass=test"` |
| `-k` / `--insecure` | Disable SSL certificate verification (for HTTPS) | No value (boolean flag) |