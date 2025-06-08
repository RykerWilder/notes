# Binwalk

Binwalk è uno strumento di analisi per file binari che permette di identificare, estrarre e analizzare firmware, immagini di sistema e altri file binari complessi. È molto utilizzato in sicurezza informatica, reverse engineering e analisi di dispositivi IoT.

## Come Funziona

Binwalk scansiona i file binari cercando:
- **Magic bytes** (signature) che identificano tipi di file incorporati
- **Entropy dei dati** per trovare sezioni compresse o crittografate
- **Filesystem** come JFFS2, SquashFS, YAFFS2
- **Bootloader** e kernel Linux embedded
- **Archivi** compressi (ZIP, GZIP, LZMA, etc.)

## Utilizzo Base

```bash
binwalk firmware.bin         # Scansione semplice
binwalk -e firmware.bin      # Estrazione automatica
binwalk -Me firmware.bin     # Scansione + estrazione ricorsiva
```

## Parametri Essenziali

| Parametro | Descrizione |
|-----------|-------------|
| `-B` | Scansiona solo signature principali |
| `-E` | Mostra entropy dei dati (utile per trovare sezioni crittografate) |
| `-H` | Output in formato esadecimale |
| `-A` | Scansiona per opcodes e codice |
| `-g <pattern>` | Cerca pattern specifici nel file |
| `-e` | Estrae automaticamente i file trovati |
| `-M` | Scansione ricorsiva sui file estratti |
| `-C <dir>` | Specifica directory di output |
| `-Z` | Comprimi i file estratti |
| `-t <types>` | Include solo tipi specifici (es: `-t filesystem`) |
| `-x <types>` | Esclude tipi specifici (es: `-x jpeg,png`) |
| `-y <types>` | Mostra solo tipi specifici |
| `-v` | Output verbose (più dettagli) |
| `-q` | Output silenzioso |
| `-f <file>` | Salva risultati su file |
| `--log=<file>` | File di log dettagliato |


```

### Output Tipico

```
DECIMAL       HEXADECIMAL     DESCRIPTION
------------------------------------------------------------------------
0             0x0             JFFS2 filesystem, little endian
14680         0x3958          LZMA compressed data, dictionary size: 65536
1441116       0x15FE5C        Linux kernel version 2.6.21.7
1454296       0x1631D8        gzip compressed data, maximum compression
```