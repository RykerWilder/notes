# Basic linux commands

### pwd (Print Working Directory)
mostra il percorso della directory corrente.

---

### ls (list)
elenca i file e le directory nella posizione corrente.

Mostra dettagli(permessi, proprietario, dimensione):
```bash
ls -l
```

Mostra anche i file nascosti (iniziano con .):
```bash
ls -a 
```

---

### cd (change directory)

Raggiungi la directory specificata:
```bash
cd percorso/assoluto 
```

Torna alla directory padre:
```bash
cd .. 
```

Torna alla home:
```bash
cd ~ 
```

---

### mkdir (make directory)

Crea una nuova directory:
```bash
mkdir folder_name
```

---

### rmdir (remove directory)

elimina una directory **vuota**:
```bash
rmdir empty_folder
```

---

### rm (remove)
elimina file o directory.

Elimina un file specifico tramite il nome:
```bash
rm file.txt 
```

Elimina una cartella e il suo contenuto **ricorsivamente**:
```bash
rm -r folder_name
```

Forza l'eliminazione senza chiedere conferma:
```bash
rm -f folder_name
```

--- 