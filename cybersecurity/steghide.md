# Steghide

## Introduction

Steghide is a steganography tool that allows you to hide files within images and audio files without visibly altering its appearance.

## What Steghide is for

Steghide is used for:

- ** Hide sensitive documents ** within harmless images
- ** secret communications ** through apparently normal channels
- ** hidden backups ** of critical information
- ** IT security ** to hide digital tests
- ** Privacy ** to protect personal data
- ** Forensic research ** to identify hidden data

## Supported formats

### File Cover (containers)
- ** jpeg ** (.jpg, .jpeg)
- ** BMP ** (.bmp)
- ** WAV ** (.wav)
- ** au ** (.au)

With Steghide you can hide any type of file (text, images, documents, archives ...)

## General syntax

`` `Bash
Steghide [Command] [Options] [File]
`` ``

## main commands

`` `Bash
Steghide Embed -CF Image_Cover.jpg -ef File_segreto.txt # Hide a file
Steghide Extract -Sf Image_con_dati.jpg # Extract a hidden file
Steghide Info Image.jpg # Get information
Steghide Encinfo # Information on encryption algorithms
`` ``


## parameters and detailed options

### General Options

| Parameter | Description | Example |
|--- |-------
| `` -CF,--Colli` | Specifies the Cover File (container) | `` -CF Image.jpg` |
| `-EF,--Embedfile` | Files to hide | `-EF document.pdf` |
| `` -SF,--STEGOFILE` | Steganographic files (output) | `` -SF Output.jpg` |
| `` -xf, ---Extractfile` | Extract file name | `` -xf extracted.txt` |

### Security options

| Parameter | Description | Example |
|--- |-------
| `` -P,--Passphrase` | Password to protect data | `-P" Miasecretpassword "` |
| `` -P, ---prompt '| Requires passwords interactively | `` -P` |
| ``-and,-encryptionis | Encryption algorithm | `-and Rijndael-128` |

### compression options

| Parameter | Description | Example |
|--- |-------
| `` -Z,--Compress` | Compression level (1-9) | `` -Z 6` |
| `` -Z,-Dontcompress` | Disable compression | `` -Z` |

### Output options

| Parameter | Description | Example |
|--- |-------
| `` -V,--verbose` | Detailed output | ``v` |
| `` -q,--provide | Silent mode | `` -q` |
| `` -F,--Force` | Force overwritten existing files | `` -F` |

### Advanced Options

| Parameter | Description | Example |
|--- |-------
| `` -N,--Dontembedname '| The file name does not incorporate | `` N '|
| `` -W,-CECKSUM '| Adds checksum for integrity verification | `` -W` |

## Supported encryption algorithms

Steghide supports several encryption algorithms:

- **Rijndael-128** (AES-128)- Default
- **Rijndael-192** (AES-192)
- **Rijndael-256** (AES-256)
- **Arcfour** (RC4)
- **Blowfish**
- **XTEA**
- **SAFFFLUS**
- **Wake**
- **PC1**
- **Serpent**
- **Rijndael** (AES with variable key)
- **SAPPHIRE**