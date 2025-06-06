# Nmap

Nmap (Network Mapper) is a free open-source tool for network discovery and security auditing. It is considered one of the most powerful and versatile tools for network exploration, host discovery, service detection, and security assessment.

## What Nmap is used For

- **Network Discovery**: Discovering active hosts in a network
- **Port Scanning**: Identifying open ports on specific targets
- **Service Detection**: Detecting services and versions running
- **OS Detection**: Identifying the operating system of targets
- **Vulnerability Assessment**: Detecting potential vulnerabilities
- **Network Mapping**: Creating topological maps of networks
- **Security Auditing**: Evaluating network and system security
- **Penetration Testing**: Information gathering during pentests

## General Syntax

```bash
nmap [Scan Type] [Options] {target specification}
```

## Target Specification

| Format | Description | Example |
|---------|-------------|---------|
| Single IP | A single IP address | `192.168.1.1` |
| IP Range | Range of IP addresses | `192.168.1.1-100` |
| CIDR Subnet | CIDR notation | `192.168.1.0/24` |
| Hostname | Domain name | `example.com` |
| IP List | Space-separated list | `192.168.1.1 192.168.1.5` |
| Input File | File with target list | `-iL targets.txt` |
| Random targets | Random targets | `-iR 100` |

### Target Exclusion

```bash
nmap 192.168.1.0/24 --exclude 192.168.1.1,192.168.1.5     # Exclude specific hosts
nmap 192.168.1.0/24 --excludefile exclude.txt             # Exclude from file
```

## Host Discovery

| Parameter | Description | Example |
|-----------|-------------|---------|
| `-sn` | Ping scan (no port scan) | 
| `-Pn` | Skip host discovery |
| `-PS` | TCP SYN ping | `nmap -PS22,80,443 192.168.1.1` |
| `-PA` | TCP ACK ping | `nmap -PA80 192.168.1.1` |
| `-PU` | UDP ping | `nmap -PU53 192.168.1.1` |
| `-PE` | ICMP echo ping | `nmap -PE 192.168.1.1` |
| `-PP` | ICMP timestamp ping |
| `-PM` | ICMP netmask ping |

## Port Scanning

| Parameter | Description |
|-----------|-------------|
| `-sS` | TCP SYN scan (stealth) |
| `-sT` | TCP connect scan |
| `-sU` | UDP scan |
| `-sA` | TCP ACK scan |
| `-sW` | TCP Window scan |
| `-sM` | TCP Maimon scan |
| `-sF` | FIN scan |
| `-sX` | Xmas scan |
| `-sN` | Null scan |

## Port Specification

| Parameter | Description | Example |
|-----------|-------------|---------|
| `-p` | Specific ports | `nmap -p 22,80,443 192.168.1.1` |
| `-p-` | All ports (1-65535) | `nmap -p- 192.168.1.1` |
| `-p1-1000` | Port range | `nmap -p1-1000 192.168.1.1` |
| `--top-ports` | Top N most common ports | `nmap --top-ports 100 192.168.1.1` |
| `-F` | Fast scan (100 common ports) | `nmap -F 192.168.1.1` |

## Service and Version Detection

| Parameter | Description |
|-----------|-------------|
| `-sV` | Version detection |
| `--version-intensity` | Detection intensity (0-9) |
| `--version-light` | Light detection |
| `--version-all` | Try all probes |

## OS Detection

| Parameter | Description |
|-----------|-------------|
| `-O` | OS detection |
| `--osscan-limit` | Limit OS scan to promising targets |
| `--osscan-guess` | Guess OS aggressively |

## Timing and Performance

| Parameter | Description |
|-----------|-------------|
| `-T0` | Paranoid (very slow) |
| `-T1` | Sneaky (slow) |
| `-T2` | Polite (slow) |
| `-T3` | Normal (default) |
| `-T4` | Aggressive (fast) |
| `-T5` | Insane (very fast) |

## Output Options

| Parameter | Description | Example |
|-----------|-------------|---------|
| `-oN` | Normal output | `nmap -oN scan.txt 192.168.1.1` |
| `-oX` | XML output | `nmap -oX scan.xml 192.168.1.1` |
| `-oG` | Grepable output | `nmap -oG scan.gnmap 192.168.1.1` |
| `-oA` | All formats | `nmap -oA scan 192.168.1.1` |

## Firewall/IDS Evasion

| Parameter | Description |
|-----------|-------------|
| `-f` | Fragment packets |
| `--mtu` | Set MTU size |
| `-D` | Decoy scan |
| `-S` | Spoof source address |
| `--source-port` | Spoof source port |
| `--data-length` | Append random data |

