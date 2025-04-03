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

```