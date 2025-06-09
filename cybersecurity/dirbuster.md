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

## Parametri
| Parametro            | Descrizione          |      Valori di Esempio | ----------------------------------------------------------------------------------------------- |
| `-u` / `--url`       | URL del target da scansionare                                                   | `http://example.com`                   |
| `-l` / `--wordlist`  | Percorso del file wordlist contenente le directory/file da testare              | `/usr/share/wordlists/dirb/common.txt` |
| `-e` / `--ext`       | Estensioni dei file da testare (separate da virgola)                            | `php,html,asp`                         |
| `-t` / `--threads`   | Numero di thread da utilizzare (velocizza la scansione)                         | `20`                                   |
| `-r` / `--recursive` | Abilita la scansione ricorsiva delle directory                                  | Nessun valore (flag booleana)          |
| `-H` / `--header`    | Aggiunge un header HTTP personalizzato (es. per Cookie o User-Agent)            | `"Cookie: PHPSESSID=1234"`             |
| `-X` / `--method`    | Specifica il metodo HTTP da utilizzare (GET di default)                         | `POST`                                 |
| `-s` / `--status`    | Mostra solo i risultati con specifici codici di stato HTTP                      | `200,301,403`                          |
| `-o` / `--output`    | Salva i risultati in un file                                                    | `report.txt`                           |
| `-v` / `--verbose`   | Mostra output dettagliato durante la scansione                                  | Nessun valore (flag booleana)          |
| `-p` / `--proxy`     | Utilizza un proxy per le richieste (formato `host:porta`)                       | `127.0.0.1:8080`                       |
| `-a` / `--useragent` | Imposta uno User-Agent personalizzato                                           | `"Mozilla/5.0"`                        |
| `-c` / `--cookies`   | Aggiunge cookie alla richiesta (formato `nome=valore`)                          | `session=abcd1234`                     |
| `-z` / `--delay`     | Imposta un ritardo (in millisecondi) tra le richieste per evitare rate-limiting | `100`                                  |
| `-P` / `--postdata`  | Dati da inviare nel body per richieste POST                                     | `"user=admin&pass=test"`               |
| `-k` / `--insecure`  | Disabilita la verifica del certificato SSL (per HTTPS)                          | Nessun valore (flag booleana)          |

