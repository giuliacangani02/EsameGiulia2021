# Juliet's port
In un grande porto commerciale si vuole automatizzare il ciclo di gestione dei container, dai TIR alla nave e viceversa.
Il porto ha 2 banchine e 10 stacking area.
Quando una nave arriva in banchina i container sono scaricati nel molo da un operatore umano in una torre di controllo che comanda in modo remoto le gru del molo.
Sul molo, stazionano sempre dei carrelli elettrici a guida automatica, con ruote di gomma, su cui l’operatore carica i container. 
I carrelli automaticamente spostano i container passando attraverso un’area a loro dedicata, interdetta agli esseri umani ed altri mezzi, detta Area Fronte Mare (in figura). Attraversando quest’area arrivano in un’area di posteggio temporaneo antistante la stacking area (area di impilaggio) che dovrà stoccare il container.
In quest’area il container verrà prelevato dal carrello da una gru a ponte detta ASC. Dopo aver prelevato il container dal carrello, l'ASC muovendosi su dei binari paralleli, impila il container sopra gli altri container già stoccati. Un software comanda automaticamente (senza intervento umano) la gru ASC in maniera tale che venga effettuata una distribuzione ottimale (sort) dei container nella stacking area. Il container rimane nella stacking area fino a che non verrà caricato su un TIR porta-container. Quando un container deve essere movimentato dalla stacking area al TIR, il posizionamento dalla stacking area alla verticale del TIR è automatica, mentre la delicata fase di posizionamento finale sul telaio del TIR è svolta da un operatore umano che dalla torre di controllo pilota l’operazione da remoto, con l’ausilio di joystick e schermi che visualizzano l’area di manovra. 
I TIR (guidati da un autista umano) arrivano su una piazzola di attesa da dove vengono smistati verso una determinata stacking area per il carico/scarico. 
Lo studente proponga le tecnologie che ritiene idonee a guidare e controllare il movimento dei carrelli elettrici lungo l’area di trasferimento fronte mare, il movimento delle ASC lungo la stacking area e la guida remota delle gru dalla torre di controllo. La banchina è di cemento e può eventualmente essere cablata o dotata di sensori. 
Lo studente progetti anche il sistema di prenotazione dell’accesso dei truck portacontainer al porto sia per l’operazione di scarico che per quella di carico. I camionisti possono prenotare l’appuntamento di carico/scarico via app, via sito, oppure, all’ultimo secondo, su un varco antistante il porto. La precisione dell’appuntamento è quella dell’ora, per cui deve essere prevista un’area dove tenere eventualmente in coda i camion su uno o più ingressi. 
Il SW di gestione deve tenere traccia degli appuntamenti con data e ora, dei dati riguardanti il container (dimensioni, categoria, codice ISO 6346 ed informazioni relative), della merce trasportata (tipo, peso, ecc), dei dati riguardanti l’autista (nome, cognome, ecc) e del TIR (modello, targa, ecc.), della nave da cui deve essere scaricato il container (nome, capacità in numero di container), dell’operatore che ha gestito lo scarico (con nome, cognome, matricola, etc.) e delle informazioni della durata dell’appuntamento ed eventuali problemi riscontrati. 
Il SW deve gestire anche il carico/scarico della nave memorizzando la rotta e il viaggio, indicando se è in arrivo o in partenza e il nome del porto di provenienza/destinazione, con le date e l’ora di arrivo/partenza e memorizzando il numero di container da scaricare/caricare e il nome del capitano della nave in quel viaggio.  
Le stacking area sono 10 e hanno una capacità di 1000 container ciascuno, per cui la prenotazione dell’attracco è subordinata alla previsione di un numero sufficiente di posti liberi. La prenotazione riserva banchina e stacking area. I container vengono automaticamente accatastati uno sopra l’altro nel primo posto libero. 
# TO DO
Il candidato analizzi la realtà di riferimento e, fatte le opportune ipotesi aggiuntive, individui una soluzione che a suo motivato giudizio sia la più idonea a sviluppare i seguenti punti:
- [ ]   il dimensionamento del progetto, con numero di utenti stimato e altre quantità significative
- [ ]   un modello grafico che rappresenti il sistema, ne ponga in evidenza i vari componenti e le loro interconnessioni, motivando le scelte effettuate
- [ ]   una descrizione, anche utilizzando uno schema grafico, con le funzionalità tecnologiche che dovranno possedere i dispositivi terminali utente e quelli aziendali dislocati nei punti strategici dei locali
- [ ]	l’individuazione dei protocolli di comunicazione da adottare per garantire la sicurezza da attacchi informatici e la resilienza a guasti e malfunzionamenti delle applicazioni e le relative tecnologie
- [ ]	la definizione del database del sistema, sotto forma di entità relazione e di schema logico 
- [ ]	il progetto dell’interfaccia grafica, sotto forma di rappresentazione grafica
- [ ]	l’implementazione di una parte significativa dell'interfaccia grafica dell’applicazione
- [ ]	l’implementazione del database e dell’applicazione su una macchina locale, on-premises o in cloud
- [ ]	una stima dei tempi per la realizzazione del progetto, evidenziando la correlazione fra le attività
- [ ]	Sviluppi in linguaggio SQL delle query che consentano di ottenere le seguenti informazioni:
    - [ ]	il numero dei posti attualmente liberi in una certa stacking area
    - [ ]	il	nome del camionista prenotato per il 5 agosto 2021 con le informazioni che riguardano TIR, carico, nave e viaggio
- [ ]	un “executive summary” del progetto redatto in lingua inglese, che presenti il progetto in un’ottica di business. 

