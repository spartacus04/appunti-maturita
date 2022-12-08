#Sistemi 
IPv4 è la versione più utilizzata di ip sulle reti private e pubbliche. Gli indirizzi di IPv4 sono composti da 32 bit, che si sono rivelati non abbastanza in quanto sono stati esauriti.

Fortunatamente il problema della mancanza di IP è stato risolto con l'utilizzo di tecnologie come NAT, che ha tamponato il problema nell'attesa di [[IPv6]].

Il preambolo Ipv4 è composto in questo modo:
![[IPv4.png]]
- **Version**: versione del protocollo
- **IHL**: lunghezza dell'intestazione in "parole" da 32 bit
- **Differentiated Services** (**DS**): qualità del servizio: suddiviso nei 2 sottocampi DSCP e ECN
- **Total Length**: indica la lunghezza del datagramma
- **Identification**: indica a quale datagramma appartiene il frammento
- **Flags**: 
   - Bit 2: Riservato
   - Bit 1: (DF) se vale 1 impone ai router di non frammentare il datagramma
   - Bit 0: (MF) se vale 1 il pacchetto fa parte di un datagramma, se vale 0 identifica l'ultimo pacchetto di un datagramma
- **Fragment offset**: Indica la posizione del frammento nel datagramma corrente
- **TTL**: Contatore utilizzato per limitare la vita del paccehtto. A ogni salto è decrementato e quando raggiuge 0 il pacchetto è scartato.
- **Protocol**: Indica il protocollo del livello 4 (TCP o UDP)
- **Header Checksum**: Contiene il valore del checksum
- **Source Address** e **Destination address**: ip del mittente e destinatario
- **Options**: campo opzionale inserito tra la fine del preambolo e l'inizio dei dati per inserire dati importanti al routing
- **Padding**: bit vuoti per arrivare a un multipo di 32
- **Payload**: contenuto del messaggio
---
## Indirizzo e subnet mask

Un indirizzo IPv4 è costituito da 32 bit, espressi in dotted decimal notation.
Esempio:
$$
10101100.00010000.01110000.00001010
$$
Gli indirizzi possono quindi assumere un valore compreso tra $0.0.0.0$ e $255.255.255.255$

Un indirizzo individua univocamente il dispositivo di rete ed è diviso in 2 parti: network prefix e host address.

Una subnet mask è un indirizzo necessario a capire quale parte di un IP è il network prefix, e quindi per capire se un indirizzo fa parte di una rete.

$$
	11111111.11111111.11111111.00000000
$$

> I bit a 1 nella subnet mask identificano la porzione di rete mentre quelli a 0 indicano quali sono i bit nell'indirizzo host.

Per farlo facciamo la messa in and dei due indirizzi.
Esempio:

| Indirizzo      | valore                                | operatore |
| -------------- | ------------------------------------- |:---------:|
| Indirizzo host | $10101100.00010000.01110000.00001010$ |    AND    |
| Subnet mask    | $11111111.11111111.11111111.00000000$ |     =     |
| Rete           | $10101100.00010000.01110000.00000000$ |           |

Per esprimere in modo più efficace e sintetico i bit si utilizza la notazione prefix length, indicata con una barra "/" seguita dal numero di bit associati alla maschera
Esempio:
$$
127.16.112.10/24
$$
---
## Classificazione

Gli ip si distinguono in base al loro valore nelle seguenti classi
| nome | da        | a               | Note                                                                       |
| ---- | --------- | --------------- | -------------------------------------------------------------------------- |
| A    | 0.0.0.0   | 127.255.255.255 | 7 bit per la rete                                                          |
| B    | 128.0.0.0 | 192.255.255.255 | 14 bit per la rete                                                         |
| C    | 192.0.0.0 | 223.255.255.255 | 21 bit per la rete                                                         |
| D    | 224.0.0.0 | 239.255.255.255 | Inizia con 1110 ed è utilizzato per indirizzare tutti gli host di una rete |
| E    | 240.0.0.0 | 254.255.255.255 | Inizia con 1111 ed è riservato per usi futuri                              | 

---
## Indirizzi speciali
| Nome                   |    indirizzo    | utilizzo                                    |
| ---------------------- |:---------------:| ------------------------------------------- |
| indirizzo di rete      |     0.0.0.0     | Individua la rete corrente                  |
| indirizzo di broadcast | 255.255.255.255 | Invia pacchetti a tutti gli host della rete |
| indirizzo di loopback  |    127.0.0.1    | Host stesso                                 |

---
## Reti pubbliche e private

Le reti pubbliche sono reti accessibili liberamente da tutti, collegate a internet e tra di loro.

Le reti private sono accessibili solo da un altri host che appartengono alla stessa rete privata.
Le reti private sono divise in classi:

| nome | da          | a               |
| ---- | ----------- | --------------- |
| A    | 10.0.0.0    | 10.255.255.255  |
| B    | 172.16.0.0  | 172.31.255.255  |
| C    | 192.168.0.0 | 192.168.255.255 | 

Per consentire a una rete privata di connettersi a internet è necessario svolgere il procedimento di NAT (Network Address Translation).

Gli IP privati sono utilizzati per fornire:
- maggiore sicurezza
- abbondanza di spazio di indirizzamento

---
## Subnetting

Il subnetting permette di non sprecare gli indirizzi inutilizzati dividento un ip in sottoreti.
La suddivisione in sottoreti non è visibile al di fuori della rete LAN.

Vedi Indirizzo IP e subnet mask.

Per vedere il numero massimo di host in una sottorete $2^h$ dove h è il numero di bit dedicato agli host.

Per assegnare gli indirizzi IP ai vari host di una rete l'amministratore trasferisce dei bit dal campo host al campo subnet.
Gli host appartenenti alla sottostessa rete comunicano direttamente.
Per permettere agli host di comunicare con le altre sottoreti o con altre LAN è necessario usare un gateway, che solitamente ha come indirizzo quello precedente a quello di broadcast.

Una rete può essere partizionata con FLSM o VLSM.