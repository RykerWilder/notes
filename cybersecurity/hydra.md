# Hydra

Hydra è uno strumento di penetration testing open-source utilizzato per eseguire attacchi di brute-force contro servizi di autenticazione remoti. È uno dei tool più veloci e flessibili per testare la robustezza delle password su diversi protocolli di rete.

## A cosa serve Hydra

- **Password Auditing**: Testare la robustezza delle password aziendali
- **Penetration Testing**: Valutare la sicurezza durante test di penetrazione
- **Security Assessment**: Identificare credenziali deboli nei sistemi
- **Brute Force Attacks**: Attacchi automatizzati contro servizi di login
- **Dictionary Attacks**: Utilizzo di wordlist per craccare password
- **Compliance Testing**: Verificare conformità alle policy di sicurezza
- **Red Team Operations**: Simulazioni di attacchi reali

## Protocolli Supportati

Hydra supporta oltre 50 protocolli, tra cui:

- **Web**: HTTP, HTTPS, HTTP-FORM, HTTP-GET, HTTP-POST
- **Database**: MySQL, PostgreSQL, Microsoft SQL, Oracle, MongoDB
- **Remote Access**: SSH, Telnet, RDP, VNC
- **Mail**: POP3, IMAP, SMTP
- **File Transfer**: FTP, FTPS, SFTP
- **Directory Services**: LDAP, SMB, Kerberos
- **Altri**: SNMP, Cisco, RouterOS, Redis, ecc.


## Sintassi Generale

```bash
hydra [opzioni] [target] [protocollo]
```

### Struttura comando base
```bash
hydra -l username -p password target_ip protocol
hydra -L userlist.txt -P passlist.txt target_ip protocol
```

## Opzioni Principali

| Parametro | Descrizione |
|-----------|-------------|
| `target` | IP o hostname del target |
| `-M file` | Lista di target multipli |
| `-s port` | Porta specifica |
| `-l login` | Username singolo |
| `-L file` | Lista di username |
| `-p pass` | Password singola |
| `-P file` | Lista di password |
| `-C file` | Combinazioni login:pass |
| `-e nsr` | Prova username come password |
| `-t tasks` | Numero di thread paralleli |
| `-T tasks` | Numero di connessioni simultanee |
| `-w timeout` | Timeout di risposta (secondi) |
| `-c timeout` | Timeout di connessione |
| `-W waittime` | Tempo di attesa tra connessioni |
| `-o file` | File di output |
| `-b format` | Formato output (text/json/jsonv1) |
| `-v` | Modalità verbose |
| `-V` | Mostra ogni tentativo |
| `-q` | Modalità quiet |
| `-f` | Ferma dopo prima password trovata |
| `-F` | Ferma dopo prima password per host |
| `-x` | Brute force pattern |
| `-y` | Disabilita uso di proxy |
| `-S` | Connessione SSL |
| `-O` | Usa vecchio SSL v2 e v3 |
| `-K` | Non verificare certificati SSL |


### SSH Brute Force
```bash
hydra -l root -P passwords.txt 192.168.1.100 ssh # Attacco base SSH
hydra -l admin -P rockyou.txt -s 2222 192.168.1.100 ssh # SSH con porta personalizzata
hydra -L users.txt -P passwords.txt 192.168.1.100 ssh # SSH con lista di utenti

# SSH con threading ottimizzato
hydra -l root -P passwords.txt -t 4 192.168.1.100 ssh
```




### HTTP Basic Authentication
```bash
# HTTP Basic Auth
hydra -l admin -P passwords.txt 192.168.1.100 http-get /admin/

# HTTPS Basic Auth
hydra -l admin -P passwords.txt -S 192.168.1.100 https-get /secure/
```

### Database Attacks
```bash
# MySQL brute force
hydra -l root -P passwords.txt 192.168.1.100 mysql

# PostgreSQL
hydra -l postgres -P passwords.txt 192.168.1.100 postgres

# Microsoft SQL Server
hydra -l sa -P passwords.txt 192.168.1.100 mssql

# MongoDB
hydra -l admin -P passwords.txt 192.168.1.100 mongodb
```








## Ottimizzazione Performance

### Threading e parallelismo
```bash
# Threading ottimizzato per SSH
hydra -l root -P passwords.txt -t 4 target ssh

# Max parallelismo per HTTP
hydra -l admin -P passwords.txt -t 10 -T 64 target http-post-form

# Bilanciamento carico/velocità
hydra -l admin -P passwords.txt -t 1 -W 2 target ssh
```

### Gestione timeout
```bash
# Timeout lunghi per connessioni lente
hydra -l admin -P passwords.txt -w 60 -c 10 target ssh

# Timeout corti per scan veloci
hydra -l admin -P passwords.txt -w 5 -c 2 target ftp
```


### Best practices di sicurezza
```bash
# Limitare rate per evitare detection
hydra -l admin -P passwords.txt -W 10 target ssh

# Usare liste utenti realistiche
hydra -L common_users.txt -P passwords.txt target ssh

# Output sicuro
hydra -l admin -P passwords.txt -o /tmp/results.txt target ssh
chmod 600 /tmp/results.txt
```




### Comandi essenziali
```bash
# SSH brute force base
hydra -l root -P passwords.txt target ssh

# HTTP form attack
hydra -l admin -P passwords.txt target http-post-form "/login:user=^USER^&pass=^PASS^:Failed"

# FTP brute force
hydra -l ftp -P passwords.txt target ftp

# Multiple targets
hydra -L users.txt -P passwords.txt -M targets.txt ssh

# Con output file
hydra -l admin -P passwords.txt -o results.txt target ssh

# Fast attack
hydra -l admin -P passwords.txt -t 16 -f target ssh
```


