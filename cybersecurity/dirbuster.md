# DirBuster

DirBuster è uno strumento di enumerazione di directory e file web sviluppato da OWASP. È progettato per individuare directory e file nascosti sui server web attraverso attacchi di brute force utilizzando wordlist predefinite o personalizzate.

## Come Funziona

DirBuster funziona inviando richieste HTTP a un server web per testare l'esistenza di directory e file basandosi su liste di nomi comuni. Il tool analizza le risposte del server per determinare se una risorsa esiste o meno.

## Utilizzo Base

### Interfaccia Grafica
```bash
dirbuster
```

### Modalità Command Line
```bash
dirb http://target.com /usr/share/wordlists/dirb/common.txt
```
