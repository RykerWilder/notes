# Nmap
Nmap is free software released under the GNU GPL license and was developed to perform port scanning activities, both locally and remotely, on single IP addresses – private or public – or on user-specified ranges in order to determine the presence of open ports.

---

### Scan single hosts or IP ranges:

```bash
nmap 192.168.1.1 # Scan a single IP
nmap 192.168.1.1-100 # Scan a range of IPs
nmap 192.168.1.0/24 # Scan a subnet 
nmap scanme.nmap.org # Scan a domain
```

---

### Port Scanning

```bash
nmap -p 80,443 192.168.1.1 # Scan specific ports
nmap -p- 192.168.1.1 # Scan ALL ports (1-65535)
nmap --top-ports 10 192.168.1.1 # Scan the 10 most common ports
```

---

### Scan Types (TCP/UDP)

```bash
nmap -sS 192.168.1.1 # SYN Scan (stealth, does not complete TCP connection)
nmap -sT 192.168.1.1 # TCP Connect Scan (slower, but more reliable)
nmap -sU 192.168.1.1 # UDP Scan (important for DNS, DHCP, SNMP)
nmap -sA 192.168.1.1 # ACK Scan (useful for bypassing firewalls)
```

---

### Operating System and Services Detection

```bash
nmap -O 192.168.1.1 # Detect OS
nmap -sV 192.168.1.1 # Detect service versions
nmap -A 192.168.1.1 # Aggressive scan (OS, services, scripts)
```

---

### Scripting with NSE (Nmap Scripting Engine)

```bash
nmap --script=http-title 192.168.1.1 # Read the title of the web page
nmap --script=vuln 192.168.1.1 # Search for common vulnerabilities
nmap --script=ssl-enum-ciphers 192.168.1.1 # Test SSL/TLS ciphers
```

---

### Optimization and Useful Options

```bash
nmap -T4 192.168.1.1 # Fast (aggressive) mode
nmap -Pn 192.168.1.1 # Ignore ping (useful if ICMP is blocked)
nmap -v 192.168.1.1 # Verbose output
nmap -oN scan.txt 192.168.1.1 # Save the result to a file
```

---

### Timing Template
| Template      | Options    | Speed ​          ​| Description
|---------------|------------|-----------------|-----------------------------------------------
| **Paranoid**  | `-T0`      | Very slow       | 1 pkt every 5 min (extreme IDS evasion)
| **Sneaky**    | `-T1`      | Slow            | 1 pkt every 15 sec (IDS evasion)
| **Polite**    | `-T2`      | Moderate        | 1 pkt every 0.4 sec (minimal noise)
| **Normal**    | `-T3`      | Default         | Balanced between speed and reliability
| **Aggressive**| `-T4`      | Fast            | Low timeouts, more parallelism
| **Insane**    | `-T5`      | Maximum         | Low timeouts, maximum parallelism

---

Only use Nmap on networks you have permission to scan (it may be illegal on other people's networks).