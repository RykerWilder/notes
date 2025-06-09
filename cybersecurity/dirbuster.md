# DirBuster

DirBuster è uno strumento di enumerazione di directory e file web sviluppato da OWASP. È progettato per individuare directory e file nascosti sui server web attraverso attacchi di brute force utilizzando wordlist predefinite o personalizzate.

## Come Funziona

DirBuster funziona inviando richieste HTTP a un server web per testare l'esistenza di directory e file basandosi su liste di nomi comuni. Il tool analizza le risposte del server per determinare se una risorsa esiste o meno.

## Utilizzo Base

```bash
dirb http://target.com # Scansione con wordlist predefinita
dirb http://target.com /usr/share/wordlists/dirb/common.txt # Scansione con wordlist personalizzata
dirb http://target.com /usr/share/wordlists/dirb/common.txt -X .php,.html,.txt # Scansione con estensioni specifiche
dirb http://target.com -u username:password # Autenticazione HTTP Basic
dirb http://target.com -c "SESSIONID=abc123" # Utilizzare cookies
dirb http://target.com -H "User-Agent: Mozilla/5.0" # Header personalizzati
dirb http://target.com -R # Scansione ricorsiva
dirb http://target.com -p http://127.0.0.1:8080 # Utilizzare proxy
```


