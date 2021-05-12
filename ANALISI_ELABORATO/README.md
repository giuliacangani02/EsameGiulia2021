      ![image](https://user-images.githubusercontent.com/72736319/117984820-735dce00-b338-11eb-9faf-50c10e1faaef.png)

# prima analisi elaborato
I giorni successivi all’uscita dell’elaborato, ho preso informazioni su come funziona il trasporto dei container nei porti ed in particolare in quella di Civitavecchia.
Ho scoperto che la gestione delle banchine, nella maggior parte dei casi, è affidata ad una società che viene identificata con la parola “terminalista”.
Nel porto di Civitavecchia, questa è la Roma Terminal Container (RTC). I terminalisti hanno in gestione le banchine di loro competenza
e prendendo accordi con gli armatori (i proprietari dei container che traportano le merci), definiscono un calendario degli attracchi delle navi 
presso le loro banchine di competenza. Più il porto è attivo, come ad esempio quello di Venezia e Genova, e più il calendario è fitto permettendo una programmazione
già pronta per l’anno successivo. Stessa considerazione può essere fatta per la gestione dei container che devono essere scaricati da parte dei TIR.

Grazie a questa situazione, possiamo ipotizzare che il porto per il quale dovrò applicare il mio elaborato, porto che vorrei chiamare “Juliet’s port”,
ha un calendario già definito per tutti i giorni dell’anno per quanto riguarda l’arrivo e la partenza delle navi container e quindi dell’utilizzo delle banchine.
In altre parole, ogni giorno saprò a priori quali navi, quanti container e il tipo di merce che approda in ognuna delle due banchine del mio elaborato.
Inoltre, per semplificare la fase di stoccaggio, ipotizzerò di usare container della stessa misura cioè 40 piedi(la misura più grande che c’è )

Per quanto riguarda lo scarico dei container utilizzando dei carrelli a guida automatica, non ho trovato nessun porto italiano che usa questo approccio 
e verificato che nel porto di Civitavecchia, lo scarico/carico dei container dalle navi alla banchina (e viceversa) è fatto utilizzando delle gru con a bordo del personale.
Per il mio progetto ho pensato di usare dei carrelli che utilizzeranno la tecnologia a laser LGV (Laser Guided Vehicle) ossia veicoli a guida laser. 
Si tratta di trasportatori di merci rapidi ed estremamente precisi impiegati nell’ambito della logistica e automazione.
I sistemi LGV consentono di ottenere una grande velocità ed efficienza nelle operazioni di magazzino.

Sulla base di alcune ricerche che ho effettuato, ho trovato un progetto veramente interessante ed innovativo progetto “BOXBAY” di una joint
venture internazionale (DP World e SMS Group), il quale se messo in pratica potrebbe rivoluzionare il mondo dei container. 
L’idea di questo progetto mi piace e semplifica molto lo “stoccaggio” dei container, permettendomi di applicare un algoritmo più semplice 
per il prelievo o l’inserimento dei container nelle pile di stoccaggio. Infatti, questo sistema (di cui però non conosco i costi implementativi) 
prevede la movimentazione 24 ore su 24 di bobine metalliche che pesano fino a 50 tonnellate, ciascuna in scaffalature alte fino a 50 metri. 
Tutto ciò permette il 100% di accessibilità al container senza dover spostare gli altri sulla stessa pila. 

Quindi il sistema permette un’ottimizzazione sia dello spazio necessario per lo stoccaggio dei container sia del tempo di carico/scarico.
La figura successiva da un’idea di come funziona questo innovativo sistema:

![image](https://user-images.githubusercontent.com/72736319/117985372-ed8e5280-b338-11eb-8ae1-02c76f8b9505.png)

Basandomi su questo sistema, ho progettato le stacking area del mio elaborato con quattro file di container ognuna altra 10 e lunga 25,
quindi 250 container a fila per un totale di 1.000 a stacking area come richiesto. La capacità complessiva delle 10 aree sarà quindi di 10.000 container. 
La movimentazione all’interno di ogni singola area sarà garantita attraverso l’uso di due gru a ponte per ogni corridoio. 
Lo schema successivo rappresenta come vorrei che fosse realizzata la singola stacking area del mio porto:

![image](https://user-images.githubusercontent.com/72736319/117985885-65f51380-b339-11eb-9459-a45a77eecf8a.png)

Sulla base di questa implementazione, considerando container da 40 che hanno una larghezza pari a circa 2,5 mt e una lunghezza di 12 mt, ogni stacking area potrà occupare, includendo delle aree di manovra, uno spazio circa pari a 300 mt di lunghezza e 20 mt di larghezza. Aggiungendo aree cuscinetto di almeno 5mt fra una stacking area e l’altra, possiamo dedurre la necessità di un’area pari almeno a 355 mt fronte banchina. Dalla planimetria che sono riuscita a recuperare della società RTC, possiamo affermare che la mia idea potrebbe essere anche realizzata nell’area della banchina usata per il carico/scarico dei container nel porto di Civitavecchia.


