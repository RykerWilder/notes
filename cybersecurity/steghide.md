# Steghide

Steghide is a steganography tool that allows you to hide files within images and audio files without visibly altering their appearance.

---

## What Steghide is for
Steghide is used for:
- **Hide sensitive documents** within harmless images
- **Secret communications** through apparently normal channels
- **Hidden backups** of critical information
- **IT security** to hide digital evidence
- **Privacy** to protect personal data
- **Forensic research** to identify hidden data

## Supported formats

### File Cover (containers)
- **JPEG** (.jpg, .jpeg)
- **BMP** (.bmp)
- **WAV** (.wav)
- **AU** (.au)

## Supported encryption algorithms
Steghide supports several encryption algorithms:
- **rijndael-128** (AES-128) - Default
- **rijndael-192** (AES-192)
- **rijndael-256** (AES-256)
- **arcfour** (RC4)
- **blowfish**
- **xtea**
- **saferplus**
- **wake**
- **pc1**
- **serpent**
- **rijndael** (AES with variable key)
- **sapphire**j

With Steghide you can hide any type of file (text, images, documents, archives, etc.)

---

## General syntax
```bash
steghide [command] [options] [file]
```

## Main commands
```bash
steghide embed -cf cover_image.jpg -ef secret_file.txt            # Hide a file
steghide embed -cf photo.jpg -ef segret_file.txt -p "mypassword"  # Hide a file with password
steghide extract -sf image_with_data.jpg                          # Extract a hidden file
steghide info image.jpg                                           # Get information
steghide encinfo                                                  # Information on encryption algorithms
```

---

## Parameters and detailed options

### General Options
| Parameter | Description | 
|-----------|-------------|
| `-cf, --coverfile` | Specifies the cover file (container) 
| `-ef, --embedfile` | File to hide 
| `-sf, --stegofile` | Steganographic file (output) 
| `-xf, --extractfile` | Name of extracted file
| `-p, --passphrase` | Password to protect data |
| `-P, --prompt` | Requires password interactively |
| `-e, --encryption` | Encryption algorithm |
| `-z, --compress` | Compression level (1-9) |
| `-Z, --dontcompress` | Disable compression |
| `-v, --verbose` | Detailed output |
| `-q, --quiet` | Silent mode |
| `-f, --force` | Force overwrite existing files |
| `-N, --dontembedname` | Does not incorporate the file name |
| `-w, --checksum` | Adds checksum for integrity verification |