# DirBuster

DirBuster è uno strumento di enumerazione di directory e file web sviluppato da OWASP. È progettato per individuare directory e file nascosti sui server web attraverso attacchi di brute force utilizzando wordlist predefinite o personalizzate.

## Come Funziona

DirBuster funziona inviando richieste HTTP a un server web per testare l'esistenza di directory e file basandosi su liste di nomi comuni. Il tool analizza le risposte del server per determinare se una risorsa esiste o meno.

## Installazione

DirBuster è incluso in molte distribuzioni di sicurezza come Kali Linux. Per installarlo manualmente:

```bash
apt-get install dirbuster
```

## Utilizzo Base

### Interfaccia Grafica
```bash
dirbuster
```

### Modalità Command Line
```bash
dirb http://target.com /usr/share/wordlists/dirb/common.txt
```

## Parametri Principali

### Target Configuration
- **Target URL**: L'URL del sito web da testare
- **Number of Threads**: Numero di thread simultanei (default: 10)
- **Go Faster**: Aumenta la velocità rimuovendo alcuni controlli

### File Extension Options
- **File extension**: Estensioni di file da testare (.php, .html, .txt, etc.)
- **Use Blank Extension**: Testa anche file senza estensione

### Advanced Options
- **Recursive**: Scansione ricorsiva delle directory trovate
- **Be Recursive**: Profondità della ricorsione
- **Fail Case String**: Stringa che indica una risposta negativa
- **HTTP Response Codes**: Codici di risposta da considerare come successo

### Authentication
- **Use Authentication**: Per siti protetti da autenticazione
- **Username/Password**: Credenziali per l'accesso
- **Realm**: Realm per l'autenticazione HTTP

## Wordlist Comuni

### Wordlist Predefinite (Kali Linux)
```
/usr/share/wordlists/dirb/common.txt
/usr/share/wordlists/dirb/big.txt
/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
/usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
```

### Selezione Wordlist
- **Small**: Per test rapidi (~1000 entry)
- **Medium**: Bilanciamento tra velocità e completezza (~220k entry)
- **Large**: Scansione completa (~1M+ entry)

## Esempi Pratici

### Scansione Base
1. Avviare DirBuster
2. Inserire l'URL target: `http://example.com`
3. Selezionare wordlist: `/usr/share/wordlists/dirb/common.txt`
4. Impostare thread: 10-20
5. Cliccare "Start"

### Scansione con Estensioni Specifiche
- Aggiungere estensioni: `.php`, `.html`, `.txt`
- Abilitare "Use Blank Extension"
- Avviare la scansione

### Scansione Ricorsiva
- Abilitare "Be Recursive" 
- Impostare profondità: 3-5 livelli
- Monitorare i risultati in tempo reale

## Interpretazione dei Risultati

### Codici di Risposta HTTP
- **200 OK**: Risorsa trovata e accessibile
- **301/302**: Redirect (potenzialmente interessante)
- **403 Forbidden**: Risorsa esiste ma accesso negato
- **404 Not Found**: Risorsa non trovata

### Analisi Output
- **Dir Found**: Directory scoperte
- **File Found**: File individuati
- **Response Size**: Dimensione delle risposte (utile per identificare pagine standard)

## Best Practices

### Performance
- Iniziare con wordlist piccole per test rapidi
- Aumentare gradualmente i thread in base alla risposta del server
- Utilizzare proxy per evitare rate limiting

### Stealth
- Ridurre il numero di thread per essere meno invasivi
- Aggiungere delay tra le richieste
- Utilizzare User-Agent personalizzati

### Efficienza
- Salvare i risultati per analisi successive
- Utilizzare filtri per escludere falsi positivi
- Combinare con altri tool di reconnaissance

## Limitazioni

- Dipende dalla qualità delle wordlist
- Può essere rilevato da WAF/IDS
- Efficacia limitata su applicazioni moderne con routing dinamico
- Tempo di esecuzione può essere lungo con wordlist estese

## Considerazioni Legali

Utilizzare DirBuster solo su sistemi di cui si possiede l'autorizzazione o in ambienti di test dedicati. L'uso non autorizzato può violare leggi sulla sicurezza informatica.

## Alternative Moderne

- **Gobuster**: Più veloce, scritto in Go
- **ffuf**: Fuzzer moderno e flessibile
- **wfuzz**: Tool di fuzzing web completo
- **feroxbuster**: Scanner ricorsivo ad alte prestazioni