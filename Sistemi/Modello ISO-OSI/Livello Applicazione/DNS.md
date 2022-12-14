#Sistemi 
Il domain name system è un sistema che permette di convertire indirizzi ip in nomi semplici e riconoscibili detti domini.

Il sistema DNS fornisce:
- uno spazio di nomi, struttrato in modo gerarchico
- un servizio in cui molti sistemi collaborano in rete per rendere disponibile lo spazio dei nomi
- un servizio in cui ogni server dns è responsabile solo del suo sottoinsieme
- un protocollo a livello applicazione che si appoggia sulla porta 53 di UDP.
---
## Gerarchia di dominio

Il DNS assegna uno spazio gerarchico dei nomi. Ogni nome di dominio è costituito da una o più etichette separate da un punto.

Il dominio di primo livello (Top Level Domain) può essere:
- gTLD
  - sTLD: domini sponsorizzati
  - uTLD: domini non sponsorizzati
- ccTLD: domini nazionali

Possiamo pensare DNS come una gerarchia di distributori di nomi più che a una gerarchia di domini.


La radice dell'albero è detto root name server, e contiene un elenco di server responsabili con i domini di primo livello. Ogni ramo dell'albero dei domini è detto zona. Ogni zona può essere considerata come autorità responsabile dei suoi sottorami. Ogni zona mantiene informazioni organizzate in Record.

Ogni record è costituito dai seguenti campi:
- **Name**: nome fornito al DNS
- **Value**: valore restituito dal DNS
- **Type**: come value deve essere interpretato
| Type  | Description                                                           |
| ----- | --------------------------------------------------------------------- |
| A     | IPv4 del dispositivo                                                  |
| MX    | Nome del dominio del server di posta                                  |
| NS    | Nome per un calcolatore che sa risolvere nomi all'interno del dominio |
| CNAME | Nome alias di un calcolatore                                          |
| AAAA  | IPv6 del dispositivo                                                  | 

- **Class**: classe di appartenenza delle risorse
- **TTL**: indica per quanto tempo la struttura dati è valida.

Ogni zona ha una coppia di record NS e A, relativi al server del livello sottostante.

---
## Messaggi

Il protocollo DNS ha 2 tipi di messaggi:
- Query
- Response

Ogniuno dei messaggi ha un **header**, che contiene i campi e i flag, e un campo **Question**, che contiene il nome del server richiesto.

Inoltre la response ha i seguenti campi aggiuntivi:
- **Answer**: che contiene uno o più record con le risposte dal server al client
- **Authoritative**: che fornisce informazioni sui server autorevoli per la richiesta-risposta
- **Additional**: che fornisce informazioni aggiuntive