#Sistemi 
Transmission Control Protocol è un protocollo di trasporto utilizzato in internet.
Il suo compito è quello di fornire un flusso di byte affidabile da sorgente a destinazione.
È orientato alla connessione, quindi stabilisce una connessione tra mittente e destinatario prima di trasmettere i dati.

Nel dettaglio si occupa di:
- Stabilire una connessione full-duplex
- Comporre il flusso di byte
- Consegnargli al livello rete
- Rendere affidabile la comunicazione
- Riordinare i segmenti ricevuti
- Controllare il flusso di dati spediti
- Gestire il multiplexing/demoplexing
- Chiudere la connessione

---
## Multiplexing/Demoplexing

Diverse applicazioni sugli host remoti generano messaggi che condividono una stessa connessione di rete. Per gestire flussi diversi su un'unica connessione fisica si usa il multiplexing e il demoplexing.

Il multiplexing gestirà i dati assegnando ad applicazioni diverse una porta e ne inserisce l'intestazione.

Il demoplexing ripeterà la stessa operazione al contrario, e utilizzerà la porta per individuare l'applicazione coinvolta.

La porta è identificata con un 16 bit, ed è inserita nell'intestazione del segmento TCP.

La combinazione di un IP e una porta è detto socket.

---
## Il preambolo

![[TCP.png]]
- **Source port** e **destination port**: porte del mittente e del destinatario
- **Sequence Number**: Permette di tenere traccia del numero di byte inviati e ricevuti
- **Acknowledgment Number**: è il numero complementare del sequence number, indica all'host remoto il numero di byte da aspettarsi.
- **Data Offset**: indica la lunghezza dell'intestazione in parola da 32 bit
- **Reserved**: campo predisposto per usi futuri
- **Flags**:
  - CWR: conferma ricezione di un segmento con ECE attivo
  - ECE: indica che l'host supporta ECN
  - URG: corrisponde a un interrupt (messaggio urgente)
  - ACK: se attivo indica che l'acknowledgment number è valido
  - PSH: indica di passare senza indugio i dati al livello applicazione
  - RST: utilizzato per inizializzare una nuova connessione TCP
  - SYN: utilizzato per indicare la richiesta di una nuova connessione
  - FIN: usato per chiudere la connessione
- **Window Size**: indica il numero di byte ancora liberi che il ricevente è in grado di accettare
- **Checksum**: controllo degli errori
- **Urgent Pointer**: puntatore ai dati urgenti, usato solo se URG è attivo
- **Options**: campo opzionale inserito tra la fine del preambolo e l'inizio dei dati per inserire eventuali opzioni
- **Payload**: contenuto del messaggio

---
## Connessione TCP

Quando due host utilizzano TCP devono prima di tutto creare una sessione utilizzando una procedura detta three-way handshake.

#### Per avviare una connessione due host detti A e B:

1. A invia un segmento con flag SYN=1 e ACK=0
2. B una volta accettata la connessione, invia un segmento con flag SYN=1 e ACK=1
3. A invia un altro segmento con ACK=1

#### Per chiudere una connessione tra 2 host detti A e B:

1. A invia un segmento con FIN=1
2. B invia un segmento con ACK=1

Anche se A non riceve il segmento con ACK attivo, dopo un certo periodo di tempo chiude la connessione.

---
## Problemi del protocollo

Il protocollo ha dei problemi di efficienza, che derivano da un processo di scrittura e lettura molto lento. Oltre ai 2 problemi menzionati un altro problema è la possibile congestione della rete.

Se si vuole tenere in maggior conto la velocità bisogna utilizzare [[UDP]]