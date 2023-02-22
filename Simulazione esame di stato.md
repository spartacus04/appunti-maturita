# Discussione Tecnologie di pagamento

Personalmente non conosco molte tecnologie per implementare il pagamento online, tuttavia un framework che può agevolarci nella creazione di pagamenti online è Shopify, che ci permette tramite il suo API di Php e Node di creare il nostro negozio online con tanto di pagamento.

# Progettazione concettuale

## Descrizione del progetto
In questo testo riconosciamo come entità: donatori, donazione, ricompensa e finanziamento. 

I donatori hanno come attributi i loro dati anagrafici, la loro email e come chiave primaria un identificatore numerico univoco.

Un donatore può fare una o più donazioni a diversi progetti, che hanno anche esse come chiave primaria un identificatore numerico univoco. Come attributi una donazione ha l'importo, un messaggio opzionale, la modalità di pagamento, la data di donazione e una booleana che indica se la donazione è stata rimborsata, che è ridondante nei confronti dei progetti, dove inseriremo un attributo che ci permetterà di controllare se un progetto è stato cancellato, ma ci permette un accesso più veloce. 


Un donatore per la sua donazione può eventualmente ricevere una ricompensa fisica. Ad esse associamo sempre un identificatore numerico univoco come chiave primaria, e come attributi inseriremo tipo, che indica il tipo di ricompensa, e approfondimenti, che ci permetterà di inserire dei dettagli. Per esempio nel testo avremo una ricompensa di tipo biglietto con approfondimento "biglietto per inaugurazione della restaurazione".


Ogni donazione è rivolta a un progetto. Come per le altre entità assoceremo come chiave primaria un identificatore numerico univoco. Come attributi inseriremo il nome del progetto, l'importo richiesto, la data di scadenza, lo stato della cancellazione, un link a un video, la descrizione degli obiettivi, e degli approfondimenti.

Ogni progetto è organizzato da una ONLUS che avrà come chiave primaria un numero univoco e come attributi il nome dell'azienda, l'indirizzo della sede e il nominativo del CEO.

A ogni progetto sono associati uno o più ambiti che hanno come chiave primaria il loro ambito stesso.

## Relazioni

$Donatore_{(1,N)}\to Donazione_{(1,1)}$
$Donazione_{(0,1)}\to Ricompensa_{(1, N)}$
$Donazione_{(1,1)}\to Progetto_{(0,N)}$
$Progetto_{(1,1)}\to Onlus_{(1,N)}$
$Progetto_{(1,N)}\to Ambito_{(1,N)}$

## Vincoli

$Donazione.importo \geq importominimo$
$Progetto.importorichiesto \geq 0$

## Diagramma ER

![[ER.png]]
# Progettazione logica

$Donatore(ID, nome, cognome, indirizzo, codiceFiscale, email)$
$Donazione(ID,importo,messaggio,data,rimborsata,modalita,ID_{Donatore},ID_{Ricompensa},ID_{Progetto})$
$Ricompensa(ID,tipo,approfondimenti)$
$Progetto(ID,nome,descrizione,importoRichiesto,dataScadenza,cancellato,video,approfondimenti,ID_{Onlus},ID_{AssociazioneAmbito})$
$AssociazioneAmbito(ID_{Ambito},ID_{Progetto})$
$Ambito(Ambito)$
$Onlus(ID,nome,indirizzo,nomeCeo)$
