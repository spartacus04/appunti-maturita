#Sistemi 
Il trasferimento delle email si basa sul protocollo SMTP, che si occupa di trasferire un messaggio. Utilizza il protocollo [[TCP]], ed è quindi orientato alla connessione.

La comunicazione con SMTP si articola in:
- handshake
- trasferimento del messaggio
- chiusura della connessione

Le righe di comando e di risposta terminano in CRLF.

SMPT fu successivamente espanso per supportare il login con credenziali encrittate in base64.

I comandi per il login sono HELO (passwordless) e EHLO (with password).
