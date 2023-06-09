#Informatica 
## Analisi del testo (problema, entità, associazioni)
- Indicare la realtà di interesse
- Indicare possibili attività del database
- Indicare dati più importanti
- Definire gli attributi (a quali entità/relazioni appartengono)
- Considerazioni riguardanti certi attributi
- Considerare eventuali dati aggiuntivi
- Indicare gerarchia e tipologia (Totale, Parziale, Sovrapposta, Esclusiva)
- Analisi delle associazioni (regole di lettura e molteplicità)

## Diagramma ER
- Motivare eventuali scelte di entità/attributi

## Ristrutturazione diagramma ER
- Analisi ridondanze
- Eliminazione generalizzazione (accorpamento nel padre, accorpamento nelle figlie, sostituzione generalizzazione con associazioni)
- Partizionamento/Accorpamento Entità e associazioni

## Normalizzazione
- 1FN: Valori atomici
- 2FN: Tutti gli attributi dipendono solo dalla chiave primaria completa
- 3FN: Rimuovere gli attributi che dipendono da altri attributi del descrittore

## Tabella con entità, attributi, tipo, domino e opzionalità
- Da fare solo se rimane abbastanza tempo

## Vincoli impliciti e espliciti
- Sintassi: $V<Numero>: (<Espressione>)$

<div style="page-break-after: always;"></div>

## Progettazione logica
- Ricordarsi Associazioni Binarie 1:1, 1:N, N:N
- Ricordarsi Associazioni Unarie 1:1 con opzionalità

## SQL cheatsheet
```sql
SELECT {DISTINCT} [dati] FROM [tabella]
	(INNER LEFT RIGHT FULL) JOIN [tabella2]	ON [condizione]
	WHERE [condizioni]
	LIKE [pattern]
	BETWEEN [valore1] AND [valore2]
	IN (valori)
	ORDER BY [colonne] (ASC DESC)
	LIMIT [numero]
```
