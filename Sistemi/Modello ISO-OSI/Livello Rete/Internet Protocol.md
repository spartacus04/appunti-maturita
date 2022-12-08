#Sistemi
> IP (Internet protocol) ha la funzione fondamentale di far transitare in rete i pacchetti (datagrammi) che contengono i dati provenienti dal livello trasporto.

Non è orientato alla connessione, questo significa che non determina nessuna connessione logica tra le estremità comunicative.
Fa del suo meglio (best effort) per inviare i pacchetti in modo corretto e ordinato, ma non controlla eventuali perdite e alterazioni dei dati.

IP quindi è affiancato al protocollo TCP per il recupero di errori o di dati persi.

Ci sono due versioni di IP: [[IPv4]] e [[IPv6]].

---
IP ha le seguenti funzioni:
- **encapsulation**: imbusta i dati che arrivano dal livello di trasporto lato mittente
- **addressing**: fornisce l'indirizzamento ai pacchetti
- **routing:** garantisce l'instradamento dei pacchetti
- **de-capsulation**: permette lo spacchettamento dei pacchetti ricevuti, togle la busta di livello 3 e passa i dati al livello di trasporto, lato ricevente.

---
Ip è indipendente dal mezzo trasmissivo, ma la dimensione del pacchetto non può tener conto della grandezza del frame di livello 2 (MTU). Quindi in alcuni casi il router è costretto a suddividere il pacchetto in frammenti più piccoli prima di inviarli