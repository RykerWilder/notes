# John The Ripper

# John the Ripper - Guida Completa

## Introduzione

John the Ripper (spesso abbreviato come "John" o "JtR") è uno dei più popolari e potenti strumenti per il password cracking e l'auditing della sicurezza delle password. È un tool open-source sviluppato per testare la robustezza delle password attraverso attacchi di tipo brute force e dictionary attack.

## A cosa serve

John the Ripper è utilizzato principalmente per:

- **Auditing della sicurezza**: Testare la robustezza delle password in sistemi aziendali
- **Penetration testing**: Valutare la sicurezza durante test di penetrazione
- **Recupero password**: Recuperare password dimenticate (su sistemi di proprietà)
- **Formazione sulla sicurezza**: Dimostrare l'importanza di password robuste
- **Ricerca sulla sicurezza**: Analizzare algoritmi di hashing e vulnerabilità

## Formati supportati

John supporta numerosi formati di hash, tra cui:
- Unix DES e MD5
- Windows LM e NTLM
- Kerberos AFS
- Hash MySQL, PostgreSQL
- PDF, ZIP, RAR protetti da password
- E molti altri...

## Installazione

### Linux (Ubuntu/Debian)
```bash
sudo apt-get update
sudo apt-get install john
```

### Linux (da sorgenti)
```bash
git clone https://github.com/openwall/john.git
cd john/src
make clean generic
```

### Windows
Scaricare la versione precompilata dal sito ufficiale di John the Ripper.

## Comandi Base

### Sintassi generale
```bash
john [opzioni] [file_password]
```

### Comandi principali

#### Crack di base
```bash
# Crack con dizionario predefinito
john password_file

# Crack con dizionario personalizzato
john --wordlist=dizionario.txt password_file

# Crack con regole di mutazione
john --rules password_file
```

#### Modalità specifiche
```bash
# Modalità incrementale (brute force)
john --incremental password_file

# Modalità single crack
john --single password_file

# Modalità esterna
john --external=MODE password_file
```

## Parametri e Opzioni Principali

### Opzioni di Input/Output

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `--wordlist=FILE` | Specifica un dizionario personalizzato | `john --wordlist=rockyou.txt hashes.txt` |
| `--stdin` | Legge le password da standard input | `cat wordlist.txt \| john --stdin hashes.txt` |
| `--show` | Mostra le password già craccate | `john --show hashes.txt` |
| `--users=LOGIN` | Cracca solo utenti specifici | `john --users=admin,root hashes.txt` |

### Modalità di Attacco

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `--single` | Modalità single crack (usa info utente) | `john --single passwd` |
| `--wordlist` | Attacco con dizionario | `john --wordlist=dict.txt hashes.txt` |
| `--incremental` | Brute force incrementale | `john --incremental:alpha passwd` |
| `--external=MODE` | Usa modalità esterna personalizzata | `john --external=Filter_Alpha passwd` |

### Regole e Mutazioni

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `--rules` | Applica regole di mutazione | `john --rules --wordlist=dict.txt passwd` |
| `--rules=SECTION` | Usa regole specifiche | `john --rules=Wordlist passwd` |

### Formato e Hash

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `--format=FORMAT` | Specifica il formato hash | `john --format=md5 hashes.txt` |
| `--list=formats` | Lista tutti i formati supportati | `john --list=formats` |

### Sessioni e Restore

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `--session=NAME` | Nomina la sessione | `john --session=test1 passwd` |
| `--restore=NAME` | Ripristina una sessione | `john --restore=test1` |
| `--status=NAME` | Mostra stato della sessione | `john --status=test1` |

### Performance e Ottimizzazione

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `--fork=N` | Usa N processi paralleli | `john --fork=4 passwd` |
| `--node=M/N` | Distribuito: nodo M di N | `john --node=1/4 passwd` |

## Esempi Pratici

### Esempio 1: Crack di file /etc/shadow
```bash
# Preparazione del file
sudo unshadow /etc/passwd /etc/shadow > mypasswd

# Crack con dizionario
john --wordlist=/usr/share/wordlists/rockyou.txt mypasswd

# Visualizza risultati
john --show mypasswd
```

### Esempio 2: Crack di hash MD5
```bash
# File con hash MD5
echo "admin:5d41402abc4b2a76b9719d911017c592" > md5hashes.txt

# Crack con formato specificato
john --format=raw-md5 --wordlist=dict.txt md5hashes.txt
```

### Esempio 3: Brute force incrementale
```bash
# Brute force solo caratteri alfabetici
john --incremental:alpha passwd

# Brute force caratteri alfanumerici
john --incremental:alnum passwd
```

### Esempio 4: Utilizzo delle regole
```bash
# Crack con regole standard
john --rules --wordlist=common.txt passwd

# Crack con regole specifiche
john --rules=Single --wordlist=names.txt passwd
```

## File di Configurazione

Il file principale di configurazione è `john.conf`, che contiene:

### Sezioni principali
- `[Options]`: Opzioni generali
- `[List.Rules:Wordlist]`: Regole per mutazioni
- `[List.External:*]`: Modalità esterne personalizzate
- `[Incremental:*]`: Configurazioni per brute force

### Esempio di regola personalizzata
```
[List.Rules:MyRules]
# Aggiunge numeri alla fine
$[0-9]
# Capitalizza prima lettera
c
# Aggiunge anni comuni
$1 $9 $9 $0
$2 $0 $0 $0
```

## Gestione delle Sessioni

### Avvio con sessione nominata
```bash
john --session=lavoro1 --wordlist=dict.txt passwd
```

### Pausa e ripristino
```bash
# Pausa: Ctrl+C
# Ripristino
john --restore=lavoro1
```

### Controllo stato
```bash
john --status=lavoro1
```

## Ottimizzazione Performance

### Utilizzo multi-core
```bash
# 4 processi paralleli
john --fork=4 passwd
```

### Distribuzione su più macchine
```bash
# Macchina 1 (nodo 1 di 3)
john --node=1/3 passwd

# Macchina 2 (nodo 2 di 3)
john --node=2/3 passwd

# Macchina 3 (nodo 3 di 3)
john --node=3/3 passwd
```

## Dizionari Comuni

### Dizionari preinstallati
- `/usr/share/john/password.lst` - Dizionario base
- `/usr/share/wordlists/rockyou.txt` - Dizionario molto popolare
- `/usr/share/wordlists/` - Directory con vari dizionari

### Creazione dizionari personalizzati
```bash
# Estrazione parole da testo
john --wordlist=documento.txt --stdout > custom_dict.txt

# Combinazione dizionari
cat dict1.txt dict2.txt | sort -u > combined_dict.txt
```

## Considerazioni sulla Sicurezza e Legalità

### Uso legale
- Utilizzare SOLO su sistemi di propria proprietà
- Ottenere autorizzazione scritta per test di penetrazione
- Rispettare le leggi locali sulla cybersecurity

### Best practices
- Non condividere password craccate
- Documentare i test per migliorare la sicurezza
- Usare ambienti isolati per i test
- Implementare password policy robuste dopo i test

## Comandi Utili Aggiuntivi

### Informazioni e diagnostica
```bash
# Lista tutti i formati supportati
john --list=formats

# Mostra informazioni su un formato
john --list=format-details=md5

# Test benchmark
john --test

# Versione di John
john --version
```

### Pulizia e manutenzione
```bash
# Rimuove file temporanei
rm john.pot john.rec

# Reset completo
john --clean
```

## Conclusioni

John the Ripper è uno strumento potente per l'auditing della sicurezza delle password. La sua efficacia dipende dalla qualità dei dizionari utilizzati e dalla configurazione appropriata. Ricordare sempre di utilizzarlo in modo etico e legale, solo su sistemi di propria proprietà o con esplicita autorizzazione.

Per ulteriori informazioni, consultare la documentazione ufficiale e la community di John the Ripper.