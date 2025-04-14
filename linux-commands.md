# Basic linux commands

- ### pwd (Print Working Directory)
mostra il percorso della directory corrente.

- ### ls (list)
elenca i file e le directory nella posizione corrente.

Mostra dettagli(permessi, proprietario, dimensione):
```bash
ls -l
```

Mostra anche i file nascosti (iniziano con .):
```bash
ls -a 
```


- ### cd (change directory)
cambia directory.


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


- ### mkdir (make directory)
crea una nuova directory
opzioni comuni:
mkdir folder_name

- ### rmdir (remove directory)
elimina una directory vuota.
rmdir empty_folder

- ### rm (remove)
elimina file o directory.
opzioni comuni:
rm file.txt : elimina un file specifico tramite il nome.
rm -r folder_name : elimina una cartella e il suo contenuto ricorsivamente.
rm -f : forza l'eliminazione senza chiedere conferma.

