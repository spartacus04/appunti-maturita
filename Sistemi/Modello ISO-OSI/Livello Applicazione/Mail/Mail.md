#Sistemi 
La posta elettronica è un mezzo di comunicazione asincrono. Un messaggio di posta elettronica è solitamente creato da uno User Agent e spedito da un Trasfer agent.

Un'User Agent è un client email, mentre un transfer agent trasferisce i messaggi tra i server di posta.

Quindi per l'invio di un messaggio email Lo User Agent del mittente comporrà un messaggio, sarà inviato tramite un transfer agent con [[SMTP]] a un server email. Lo user agent del mittente quindi recupererà dal server email il messaggio tramite protocolli come [[POP3]] e [[IMAP]].

---
## Struttura di un email

Una mail è composta da:
- **Envelope**: che contiene tutte le info necessarie al trasporto
- **Header**: che contiene informazioni utili gli user agent
- **Body**: che contiene il vero e proprio messaggio. Il body utilizza lo standard MIME, che permette di stabilire delle regole per la codifica e decodifica in ASCII di tipi di messaggi diversi.