# Medusa

Medusa è un tool di penetration testing progettato per eseguire attacchi di brute force contro servizi di rete che richiedono autenticazione. Medusa utilizza un approccio modulare per testare sistematicamente combinazioni di username e password contro servizi target. Il tool è multi-threaded, permettendo di eseguire più tentativi di login simultaneamente per aumentare l'efficienza.

## General Syntax

```bash
medusa -h [target] -u [username] -p [password] -m [module]
```

### Basic Command
```bash
medusa -H targets.txt -U users.txt -P passwords.txt -M ssh -t 16 -e ns -v 5 -O ssh_results.txt # Attacco SSH con liste personalizzate

medusa -h 10.0.0.1 -u admin -P rockyou.txt -M http -m "DIR:/private" -v 3 # Attacco HTTP Basic Auth con verbosità
```
