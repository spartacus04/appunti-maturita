	#Sistemi 
IMAP, come [[POP3]] permetti di recuperare i messaggi di posta elettronica, senza però doverli scaricare in locale. Infatti i messaggi rimangono sul server fino alla loro cancellazione manuale.

IMAP permette anche di leggere solo l'intestazione o parti del messaggio senza scaricare del tutto il file.

Una connessione con IMAP prevede:
- LOGIN
- SELECT per selezionare la cartella di posta
- SEARCH per cercare i messaggi
- FETCH

La cancellazione dei messaggi avviene contrassegnando il messaggio con il flag DELETED.