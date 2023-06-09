#Informatica 
>La **progettazione logica relazionale** consiste nel "mapping", cioè nella conversione del diagramma ER in un insieme di tabelle detto **schema logico relazionale** e nella definizione delle operazioni da compiere si di esso.

## Relazioni

>Una **relazione** R di una sequenza di insiemi $D_1$, $D_2$, ..., $D_n$ (non necessariamente distinti) è un sottoinsieme finito del prodotto cartesiano che possiamo esprimere con $$D_1 \cdot D_2=\{(x,y)\mid x\in D_1, y\in D_2\}$$

Il numero di tuple in una relazione R è detto **grado** (corrente) della relazione e indicato con $Card(R)$

Il numero di elementi in una tuple è detto **cardinalità**

Un **istanza** di una relazione R è l'insieme delle sue tuple in un determinato istante di tempo.

## Chiavi, schemi e occorrenze

>Esattamente come per il Modello ER, si dice **chiave candidata** o **super chiave** di una relazione R un insieme non vuoto K di attributo di R attraverso i quali è possibile identificare univocamente una tuple per ogni possibile istanza della relazione R.

Solitamente la chiave primaria è identificata da un id o un codice univoco quanto non è possibile identificare delle chiavi candidate minimali.

>Si definisce **schema** di una base di dati relazionale l'insieme di tutti gli schemi di relazione. Si definisce **occorrenza** di una base di dati relazionale l'insieme delle istanze degli schemi di relazione.

## Vincoli di integrità

I vincoli di integrità possono essere classificati in:
- **Vincolo interno sul dominio degli attributi**: Esempio $0<eta<10$
- **Vincolo interno su più attributi**: Esempio: $Data\, nascita<Data\, attuale$
- **Vincolo interno su più tuple**: Esempio: $PK_1 \neq PK_2$
- **Vincolo esterno**: Esempio:  Una partecipazione diversa da 0 o una cardinalità diversa da N impone un vincolo esterno
---
# Regole di traduzione dal modello ER al modello logico

Un entità `E` con attributi $A_1$, $A_2$, ..., $A_n$ viene tradotto in E($\underline{A_1}$, $A_2$, ..., $A_n$).

## Rappresentare associazioni tipo 1:N

$R_B (<\underline{K_B} >, <Attributi\quad B>, <K_A>, <Attributi\quad R>)$

$K_B$ = Chiave primaria di B
$K_A$ = Chiave primaria di B
R = Relazione

## Rappresentare associazioni tipo 1:1
- Nel caso nessuna relazione sia facoltativa si accorpano in una sola relazione
- Nel caso una relazione sia facoltativa l'entità non facoltativa riceve la chiave esterna
- Nel caso entrambe le relazioni siano facoltative entrambe le entità ricevono la chiave esterna

## Rappresentare associazioni tipo N:N

$R_B(<\underline{K_B}, <Attributi B>)$
$R_S(<\underline{K_A}>, <K_B>, <AttributiS>)$
$R_A(<\underline{K_A}> <AttributiA>)$

## Rappresentare associazioni su una stessa entità

