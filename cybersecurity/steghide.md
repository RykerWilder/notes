# Steghide

# Steghide - Guida Completa

## Introduzione

Steghide è un tool di steganografia che permette di nascondere file all'interno di immagini e file audio senza alterarne visibilmente l'aspetto. È uno strumento open-source scritto in C++ che utilizza algoritmi di crittografia per proteggere i dati nascosti.

## Cos'è la Steganografia

La steganografia è l'arte di nascondere informazioni all'interno di altri dati in modo che la presenza delle informazioni nascoste non sia rilevabile. A differenza della crittografia, che rende i dati illeggibili, la steganografia rende i dati invisibili.

## A cosa serve Steghide

Steghide è utilizzato per:

- **Nascondere documenti sensibili** all'interno di immagini innocue
- **Comunicazioni segrete** attraverso canali apparentemente normali
- **Backup nascosti** di informazioni critiche
- **Sicurezza informatica** per nascondere prove digitali
- **Privacy** per proteggere dati personali
- **Ricerca forense** per individuare dati nascosti

## Formati Supportati

### File Cover (contenitori)
- **JPEG** (.jpg, .jpeg)
- **BMP** (.bmp)
- **WAV** (.wav)
- **AU** (.au)

### File da nascondere
- Qualsiasi tipo di file (testo, immagini, documenti, archivi, ecc.)

## Installazione

### Linux (Ubuntu/Debian)
```bash
sudo apt-get update
sudo apt-get install steghide
```

### Linux (CentOS/RHEL)
```bash
sudo yum install steghide
# oppure
sudo dnf install steghide
```

### macOS (con Homebrew)
```bash
brew install steghide
```

### Windows
Scaricare il binario precompilato dal sito ufficiale o compilare dai sorgenti.

## Sintassi Generale

```bash
steghide [comando] [opzioni] [file]
```

## Comandi Principali

### 1. embed - Nascondere un file
```bash
steghide embed -cf immagine_cover.jpg -ef file_segreto.txt
```

### 2. extract - Estrarre un file nascosto
```bash
steghide extract -sf immagine_con_dati.jpg
```

### 3. info - Ottenere informazioni
```bash
steghide info immagine.jpg
```

### 4. encinfo - Informazioni su algoritmi di cifratura
```bash
steghide encinfo
```

### 5. version - Versione del programma
```bash
steghide version
```

## Parametri e Opzioni Dettagliate

### Opzioni Generali

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `-cf, --coverfile` | Specifica il file cover (contenitore) | `-cf immagine.jpg` |
| `-ef, --embedfile` | File da nascondere | `-ef documento.pdf` |
| `-sf, --stegofile` | File steganografico (output) | `-sf output.jpg` |
| `-xf, --extractfile` | Nome del file estratto | `-xf estratto.txt` |

### Opzioni di Sicurezza

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `-p, --passphrase` | Password per proteggere i dati | `-p "miasecretpassword"` |
| `-P, --prompt` | Richiede password interattivamente | `-P` |
| `-e, --encryption` | Algoritmo di crittografia | `-e rijndael-128` |

### Opzioni di Compressione

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `-z, --compress` | Livello di compressione (1-9) | `-z 6` |
| `-Z, --dontcompress` | Disabilita la compressione | `-Z` |

### Opzioni di Output

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `-v, --verbose` | Output dettagliato | `-v` |
| `-q, --quiet` | Modalità silenziosa | `-q` |
| `-f, --force` | Forza sovrascrittura file esistenti | `-f` |

### Opzioni Avanzate

| Parametro | Descrizione | Esempio |
|-----------|-------------|---------|
| `-N, --dontembedname` | Non incorpora il nome del file | `-N` |
| `-w, --checksum` | Aggiunge checksum per verifica integrità | `-w` |

## Algoritmi di Crittografia Supportati

Steghide supporta diversi algoritmi di crittografia:

- **rijndael-128** (AES-128) - Predefinito
- **rijndael-192** (AES-192)
- **rijndael-256** (AES-256)
- **arcfour** (RC4)
- **blowfish**
- **xtea**
- **saferplus**
- **wake**
- **pc1**
- **serpent**
- **rijndael** (AES con chiave variabile)
- **sapphire**

## Esempi Pratici

### Esempio 1: Nascondere un file di testo in un'immagine
```bash
# Creare il file segreto
echo "Questo è un messaggio segreto!" > messaggio.txt

# Nascondere il file nell'immagine
steghide embed -cf foto.jpg -ef messaggio.txt -p "password123"

# Il file foto.jpg ora contiene il messaggio nascosto
```

### Esempio 2: Estrarre il file nascosto
```bash
# Estrarre il file dall'immagine
steghide extract -sf foto.jpg -p "password123"

# Il file originale verrà estratto con il nome originale
```

### Esempio 3: Uso avanzato con opzioni personalizzate
```bash
# Nascondere con crittografia specifica e compressione
steghide embed \
  -cf immagine_cover.jpg \
  -ef documento_segreto.pdf \
  -sf immagine_output.jpg \
  -e rijndael-256 \
  -z 9 \
  -p "passwordcomplessa" \
  -v
```

### Esempio 4: Nascondere senza nome file
```bash
# Nascondere file senza incorporare il nome
steghide embed -cf audio.wav -ef dati.zip -N -p "mypass"

# Durante l'estrazione, specificare il nome
steghide extract -sf audio.wav -xf dati_estratti.zip -p "mypass"
```

### Esempio 5: Verifica presenza dati nascosti
```bash
# Controllare se un file contiene dati nascosti
steghide info possibile_stego.jpg

# Output mostrerà se ci sono dati incorporati
```

## Workflow Completo

### Preparazione
```bash
# 1. Preparare i file
ls -la
# foto_originale.jpg (file cover)
# documento_segreto.txt (file da nascondere)
```

### Nascondere i dati
```bash
# 2. Incorporare il file segreto
steghide embed \
  -cf foto_originale.jpg \
  -ef documento_segreto.txt \
  -sf foto_con_segreto.jpg \
  -p "passwordsicura" \
  -v

# Output: "embedding \"documento_segreto.txt\" in \"foto_originale.jpg\"... done"
```

### Verifica
```bash
# 3. Verificare l'incorporamento
steghide info foto_con_segreto.jpg
# Richiederà la password se i dati sono presenti
```

### Estrazione
```bash
# 4. Estrarre i dati (su un altro sistema)
steghide extract \
  -sf foto_con_segreto.jpg \
  -xf documento_recuperato.txt \
  -p "passwordsicura"
```

## Analisi Forense e Rilevamento

### Comandi per l'analisi
```bash
# Verificare se un file contiene dati steganografici
steghide info file_sospetto.jpg

# Tentativo di estrazione senza password (per test)
steghide extract -sf file_sospetto.jpg -p ""
```

### Strumenti complementari per il rilevamento
```bash
# Usare altri tool per analisi steganografica
stegsolve file.jpg    # Tool grafico per analisi
binwalk file.jpg      # Analisi struttura file
hexdump -C file.jpg | head -20    # Analisi esadecimale
```

## Sicurezza e Best Practices

### Password sicure
```bash
# Usare password complesse
steghide embed -cf cover.jpg -ef secret.txt -p "Tr0ub4dor&3"

# Evitare password semplici
# steghide embed -cf cover.jpg -ef secret.txt -p "123456"  # MAI!
```

### Selezione file cover appropriati
```bash
# Preferire immagini con molti dettagli e colori
# Evitare immagini troppo semplici o uniformi
# Verificare dimensioni adeguate per i dati da nascondere

# Controllare la capacità del file cover
steghide info -p "" cover_image.jpg
```

### Gestione sicura dei file
```bash
# Rimuovere file temporanei
rm file_originale_segreto.txt

# Usare shred per cancellazione sicura (Linux)
shred -vfz -n 3 file_sensibile.txt

# Verificare che non rimangano tracce
ls -la
```

## Limitazioni e Considerazioni

### Limitazioni tecniche
- **Dimensione dati**: I dati nascosti non possono superare la capacità del file cover
- **Formati supportati**: Solo JPEG, BMP, WAV, AU come contenitori
- **Qualità**: Possibile degradazione minima della qualità dell'immagine

### Rilevabilità
```bash
# Steghide può essere rilevato da:
# - Analisi statistica delle immagini
# - Tool specializzati di steganalisi
# - Confronto con originale se disponibile
```

### Considerazioni legali
- Utilizzare solo su file di propria proprietà
- Rispettare le leggi locali sulla privacy e crittografia
- Non utilizzare per attività illegali

## Scripting e Automazione

### Script bash per batch processing
```bash
#!/bin/bash
# Script per nascondere più file

PASSWORD="mysecretpass"
COVER_DIR="cover_images"
SECRET_DIR="secret_files"
OUTPUT_DIR="stego_output"

for secret_file in "$SECRET_DIR"/*; do
    filename=$(basename "$secret_file")
    cover_file="$COVER_DIR/cover_$(date +%s).jpg"
    output_file="$OUTPUT_DIR/stego_$filename.jpg"
    
    steghide embed \
        -cf "$cover_file" \
        -ef "$secret_file" \
        -sf "$output_file" \
        -p "$PASSWORD" \
        -q
        
    echo "Nascosto: $filename -> $output_file"
done
```

### Script per estrazione automatica
```bash
#!/bin/bash
# Script per estrarre file da immagini steganografiche

PASSWORD="mysecretpass"
STEGO_DIR="stego_files"
EXTRACT_DIR="extracted"

mkdir -p "$EXTRACT_DIR"

for stego_file in "$STEGO_DIR"/*.jpg; do
    filename=$(basename "$stego_file" .jpg)
    
    cd "$EXTRACT_DIR"
    steghide extract -sf "../$stego_file" -p "$PASSWORD" -q
    cd ..
    
    echo "Estratto da: $stego_file"
done
```

## Troubleshooting

### Errori comuni e soluzioni

#### "steghide: the cover file is too short to contain the embed file"
```bash
# Soluzione: Usare un file cover più grande o comprimere i dati
steghide embed -cf immagine_grande.jpg -ef file.txt -z 9
```

#### "steghide: could not extract any data with that passphrase"
```bash
# Verificare password corretta
# Verificare che il file contenga effettivamente dati nascosti
steghide info file.jpg
```

#### "steghide: can not get data from standard input"
```bash
# Specificare sempre i file esplicitamente
steghide embed -cf cover.jpg -ef data.txt  # Corretto
```

## Comandi di Riferimento Rapido

### Comandi essenziali
```bash
# Nascondere file
steghide embed -cf immagine.jpg -ef segreto.txt -p "pass"

# Estrarre file
steghide extract -sf immagine.jpg -p "pass"

# Informazioni file
steghide info immagine.jpg

# Lista algoritmi crittografia
steghide encinfo
