Questo progetto accademico nasce con l'obiettivo di sviluppare una pipeline bioinformatica integrata all'interno dell'ambiente di sviluppo MATLAB per l'elaborazione, la visualizzazione tridimensionale e la persistenza dei dati relativi al gene dell'insulina umana.
Il codice è strutturato in una sequenza di blocchi logici che collegano l'acquisizione remota dei dati biologici tramite architetture di rete alla manipolazione matriciale e all'ingegneria dei dati.

OBIETTIVI DEL PROGETTO:
Acquisizione Dinamica dei Dati -> Automatizzare il download della sequenza nucleotidica reale direttamente dai server dell'NCBI utilizzando protocolli di rete standard, superando la necessità di disporre di file locali statici.
 
Modellazione Molecolare e Geometrica -> Applicare i principi biologici della complementarità delle basi di Watson-Crick per generare e renderizzare nello spazio tridimensionale la struttura a doppia elica del DNA.
 
Ottimizzazione del Codice -> Implementare buone pratiche di programmazione scientifica, quali la pre-allocazione della memoria e il controllo del dynamic resizing dei vettori per garantire efficienza computazionale.
 
Persistenza e Integrazione Relazionale -> Sperimentare due diversi livelli di storage per i dati estratti: un archivio binario proprietario (.mat) e un database relazionale esterno basato su motore SQLite, interrogato tramite linguaggio SQL nativo.

STRUTTURA DEL CODICE
Il programma è implementato sotto forma di Live Script MATLAB ed è suddiviso in 8 sezioni funzionali:
 Blocco 1: Acquisizione API HTTP e Pre-processing -> Effettua una richiesta HTTP "client-server" all'endpoint NCBI tramite l'utility efetch e pulisce la stringa grezza rimuovendo l'header del file FASTA.

Blocco 2: Configurazione Geometrica -> Definisce l'ossatura matematica e le coordinate cilindriche necessarie alla successiva generazione della spirale tridimensionale.
 
Blocco 3: Analisi Statistica e Frequenze -> Calcola in modo dinamico la lunghezza del frammento, esegue la pre-allocazione dei vettori di memoria e calcola la frequenza assoluta e percentuale dei nucleotidi.

Blocco 4: Complementarità di Watson-Crick -> Genera il filamento inferiore accoppiando le basi azotate secondo la regola biologica (A-T, C-G) e mappa i legami nello spazio.
 
Blocco 5: Rendering Grafico 3D -> Utilizza funzioni di plottaggio tridimensionale (plot3) per visualizzare l'elica complessiva e i singoli pioli nucleotidici con una mappatura cromatica differenziata.

Blocco 6: Tabelle MATLAB e Persistenza Locale -> Organizza le coordinate spaziali e i dati biologici in un oggetto table e ne effettua il salvataggio in un file binario .mat.

Blocco 7: Data Filtering Interattivo-> Integrazione di un’interfaccia grafica (GUI) dove l’utente ha possibilità di interrogare in tempo reale il database.
Il filtraggio vero e proprio viene eseguito sfruttando la funzione nativa strcmp.
 
Blocco 8: Integrazione con Database SQLite -> Crea un file di database .db, esporta la tabella strutturata tramite mappatura relazionale e interroga l'archivio permanente utilizzando puro linguaggio SQL standard.

MODALITA' DI ESECUZIONE
Prerequisiti:
-MATLAB 
-Database Toolbox di MATLAB (necessario per le funzioni di interazione con SQLite nel Blocco 8).
-Una connessione internet attiva (per il download iniziale della sequenza dal server NCBI nel Blocco 1).

 -MATLAB 
 -Database Toolbox di MATLAB (necessario per le funzioni di interazione con SQLite nel Blocco 8).
-Una connessione internet attiva (per il download iniziale della sequenza dal server NCBI nel Blocco 1).
