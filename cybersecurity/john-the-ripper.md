# John The Ripper

John the Ripper (spesso abbreviato come "John" o "JtR") è uno dei più popolari e potenti strumenti per il password cracking e l'auditing della sicurezza delle password. È un tool open-source sviluppato per testare la robustezza delle password attraverso attacchi di tipo brute force e dictionary attack.

## A cosa serve

John the Ripper è utilizzato principalmente per:

- **Auditing della sicurezza**: Testare la robustezza delle password in sistemi aziendali
- **Penetration testing**: Valutare la sicurezza durante test di penetrazione
- **Recupero password**: Recuperare password dimenticate (su sistemi di proprietà)
- **Formazione sulla sicurezza**: Dimostrare l'importanza di password robuste
- **Ricerca sulla sicurezza**: Analizzare algoritmi di hashing e vulnerabilità


## Comandi Base

### Sintassi generale
```bash
john [opzioni] [file_password]
```

### Comandi principali

#### Crack di base
```bash
john password_file                                  # Crack con dizionario predefinito
john --wordlist=dizionario.txt password_file        # Crack con dizionario personalizzato
john --rules password_file                          # Crack con regole di mutazione
```

#### Modalità specifiche
```bash

john --incremental password_file      # Modalità incrementale (brute force)
john --single password_file           # Modalità single crack
john --external=MODE password_file    # Modalità esterna
```

## Parametri e Opzioni Principali

### Opzioni di Input/Output

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
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

