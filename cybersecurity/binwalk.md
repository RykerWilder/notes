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

### Scansione e Analisi
- `-B` - Scansiona solo signature principali
- `-E` - Mostra entropy dei dati (utile per trovare sezioni crittografate)
- `-H` - Output in formato esadecimale
- `-A` - Scansiona per opcodes e codice
- `-g <pattern>` - Cerca pattern specifici nel file

### Estrazione
- `-e` - Estrae automaticamente i file trovati
- `-M` - Scansione ricorsiva sui file estratti
- `-C <dir>` - Specifica directory di output
- `-Z` - Comprimi i file estratti

### Filtraggio
- `-t <types>` - Include solo tipi specifici (es: `-t filesystem`)
- `-x <types>` - Esclude tipi specifici (es: `-x jpeg,png`)
- `-y <types>` - Mostra solo tipi specifici

### Output e Debug
- `-v` - Output verbose (più dettagli)  
- `-q` - Output silenzioso
- `-f <file>` - Salva risultati su file
- `--log=<file>` - File di log dettagliato

## Esempi Pratici

```bash
# Analisi completa con estrazione ricorsiva
binwalk -Me firmware.bin

# Analisi entropy per trovare dati crittografati  
binwalk -E firmware.bin

# Estrazione in directory specifica con log
binwalk -e -C /tmp/extracted --log=scan.log firmware.bin

# Cerca solo filesystem
binwalk -t filesystem firmware.bin

# Cerca stringhe specifiche
binwalk -g "admin\|password" firmware.bin

# Combina entropy + estrazione + ricorsiva
binwalk -EMe firmware.bin
```

## Output Tipico

```
DECIMAL       HEXADECIMAL     DESCRIPTION
------------------------------------------------------------------------
0             0x0             JFFS2 filesystem, little endian
14680         0x3958          LZMA compressed data, dictionary size: 65536
1441116       0x15FE5C        Linux kernel version 2.6.21.7
1454296       0x1631D8        gzip compressed data, maximum compression
```

## Consigli Rapidi

- Usa sempre `-M` per scansioni ricorsive complete
- `-E` aiuta a identificare sezioni crittografate (alta entropy)
- Combina parametri: `-EMe` per analisi complete  
- Salva sempre log con `--log=` per analisi successive
- Usa `-C` per organizzare output in directory separate