# Linux File System

![linux file system](../img/linux-file-system.png)

Il file system di Linux è organizzato in una struttura gerarchica ad albero, che inizia dalla **root** (indicata con `/`). Ogni elemento (file, directory, dispositivo) è accessibile partendo da questa radice. Ecco una spiegazione dettagliata delle directory principali e del loro funzionamento:

---

## **1. Struttura gerarchica del file system**
Ecco le directory principali e il loro scopo:

### **`/` (Root)**
- È la directory radice, da cui partono tutte le altre.
- Contiene tutti i file e le directory del sistema.

### **`/bin` (Binari essenziali)**
- Contiene i **comandi fondamentali** per il sistema (es. `ls`, `cp`, `mv`, `bash`).
- Sono eseguibili da tutti gli utenti.

### **`/sbin` (Binari di sistema)**
- Contiene programmi di **amministrazione del sistema** (es. `fdisk`, `ifconfig`, `iptables`).
- Richiede solitamente i permessi di **root**.

### **`/boot` (File di avvio)**
- Contiene il **kernel**, i file del bootloader (`grub`) e i file necessari per l'avvio.

### **`/dev` (Dispositivi)**
- Contiene i file speciali che rappresentano **dispositivi hardware** (es. `/dev/sda` per il disco, `/dev/tty` per le console).
- In Linux, tutto è un file, anche l'hardware.

### **`/etc` (Configurazioni di sistema)**
- Contiene i **file di configurazione** globali (es. `/etc/passwd`, `/etc/fstab`, `/etc/network/interfaces`).
- Modificare questi file richiede solitamente i permessi di root.

### **`/home` (Directory utente)**
- Ogni utente ha una propria directory (es. `/home/mario`) dove può salvare file personali.
- È la directory di lavoro predefinita per gli utenti non-root.

### **`/lib` e `/lib64` (Librerie essenziali)**
- Contengono le **librerie condivise** necessarie per i programmi in `/bin` e `/sbin`.
- `/lib64` è usato per le librerie a 64 bit.

### **`/media` e `/mnt` (Punti di mount)**
- `/media`: usato per il mount automatico di dispositivi rimovibili (es. USB, CD-ROM).
- `/mnt`: usato per il mount temporaneo manuale (es. partizioni di rete o dischi aggiuntivi).

### **`/opt` (Software aggiuntivi)**
- Usato per programmi di terze parti installati manualmente (es. Google Chrome, Oracle).

### **`/proc` (File system virtuale del kernel)**
- Contiene informazioni su **processi e sistema** in tempo reale (es. `/proc/cpuinfo`, `/proc/meminfo`).
- Non occupa spazio su disco, è generato dinamicamente dal kernel.

### **`/root` (Home dell'amministratore)**
- Directory home dell'utente **root** (diversa da `/home/root`).

### **`/run` (Dati temporanei di runtime)**
- Memorizza informazioni volatili sui processi in esecuzione (PID, socket, lock).
- Sostituisce in parte `/var/run` nei sistemi moderni.

### **`/srv` (Dati dei servizi)**
- Contiene dati relativi a servizi di rete (es. FTP, HTTP).

### **`/tmp` (File temporanei)**
- File temporanei cancellati al riavvio (a volte montato in RAM con `tmpfs`).

### **`/usr` (Programmi e librerie utente)**
- Contiene la maggior parte dei **programmi installati** e librerie.
  - `/usr/bin`: comandi utente.
  - `/usr/sbin`: comandi di amministrazione non essenziali.
  - `/usr/lib`: librerie per i programmi in `/usr`.
  - `/usr/local`: software compilato manualmente (non dal package manager).

### **`/var` (File variabili)**
- Contiene dati in continua modifica:
  - `/var/log`: file di log.
  - `/var/cache`: cache delle applicazioni.
  - `/var/spool`: code di stampa, email.
  - `/var/www`: file dei siti web (se si usa Apache/Nginx).

---

## **2. Come funziona il file system?**
- **Tutto è un file**: file, directory, dispositivi, socket sono rappresentati come file.
- **Case-sensitive**: `/home` è diverso da `/Home`.
- **Percorsi assoluti e relativi**:
  - Assoluto: inizia con `/` (es. `/home/mario/file.txt`).
  - Relativo: parte dalla directory corrente (es. `./script.sh` o `../altro/file`).
- **Mount point**: i dispositivi esterni (USB, dischi) vengono "montati" in una directory (es. `/media/usb`).

---

## **3. Permessi e proprietà**
Ogni file/directory ha:
- **Proprietario** (user) e **gruppo**.
- **Permessi** in 3 gruppi: proprietario, gruppo, altri (lettura/scrittura/esecuzione).

Esempio:
```bash
-rw-r--r-- 1 mario users 1024 Jun 10 10:00 file.txt
```
- `-`: tipo (file normale).
- `rw-`: proprietario può leggere/scrivere.
- `r--`: gruppo può solo leggere.
- `r--`: altri possono solo leggere.

---

## **4. File system più comuni in Linux**
- **ext4** (quello più usato, journaling).
- **XFS** (per grandi file, alta performance).
- **Btrfs** (con funzionalità avanzate come snapshot).
- **ZFS** (usato in server, supporta checksum e deduplica).

---

## **5. Comandi utili per esplorare il file system**
- `ls` - Lista file.
- `cd` - Cambia directory.
- `pwd` - Mostra la directory corrente.
- `df -h` - Spazio su disco.
- `mount` - Mostra i dispositivi montati.
- `tree` - Visualizza la struttura ad albero.

---

### **Conclusione**
Il file system Linux è progettato per essere **logico e organizzato**, con ogni directory che ha uno scopo preciso. Sapere come è strutturato aiuta a navigare, risolvere problemi e amministrare il sistema in modo efficiente. 🚀