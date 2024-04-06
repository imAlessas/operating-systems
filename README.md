# Sistemi Operativi

Questa repo contiene il riassunto del corso _Sistemi Operativi_, tenuto dal docente N. Bellotto durante l'anno accademico 2022/2023 della facoltà di Ingegneria Informatica dell'Università degli Studi di Padova.

All'interno di questa repository, oltre al file del riassunto, [`sistemi-operativi.pdf`](sistemi-operativi.pdf), sono presenti tutti i file `.tex` e le immagini volti alla compilazione del documento.

## Indice

* [Risoluzione dei problemi](risoluzione-dei-problemi)

* [Contenuti trattati](#contenuti-trattati)

## Risoluzione dei problemi

Il documento presentato in questa repo ha alcune mancanze (in particolare nella seconda parte del terzo capitolo); inoltre è possibile che siano presenti errori di battitura o di altro tipo.

Se vuoi dare un contributo correggendo eventuali errori oppure aggiungere parti di documento mancanti, consiglio fortemente di rispettare le seguenti linee guida.

> [!IMPORTANT]
>
> 1. Utilizza la funzione `fork` per clonare la repo sul tuo account GitHub
>
> 2. Crea un nuovo `branch` ed effettua le __modifiche__ e le aggiunte al progetto
>
> 3. Fai una `pull request` e attendi che le modifiche vengano revisionate

Eventualmente, si possono utilizzare anche i GitHub `issues` per segnalare un errore banale.

Si osserva infine che tutti i `commit` di questo progetto, nonostante sia scritto in lingua italiana, sono in inglese, come il nome dei files e delle cartelle. Si prega quindi di mantenere valido questo invariante.

## Contenuti trattati

Il documento `.pdf` è suddiviso in diversi capitoli. In questa sezione cerchiamo di schematizzare il contenuto per apprendere gli argomenti principali che sono discussi all'interno di `sistemi-operativi.pdf`.

<details>
    <summary> <b> Processi </b> </summary>
    Il capitolo tratta dei processi, definendoli come istanze attive di programmi in esecuzione sulla CPU, con uno spazio dedicato in memoria e un blocco di controllo (PCB) che ne gestisce le informazioni. Esplora gli stati attraversati dai processi, come nuovo, pronto, in esecuzione, in attesa e terminato, con creazione e terminazione gestite dal genitore. Discute inoltre la comunicazione tra processi, sia tramite memoria condivisa, più veloce ma soggetta a errori di sincronizzazione, sia attraverso il passaggio di messaggi, più sicuro ma con maggiore overhead a causa del coinvolgimento del kernel.
</details>

<details>
    <summary> <b> Threads </b> </summary>
    Il capitolo tratta dei threads, definendoli come fili di esecuzione all'interno di un processo. Vengono evidenziati i vantaggi dei threads rispetto ai processi, come una maggiore reattività, una gestione semplificata delle risorse e una minor richiesta di risorse di sistema. Si discute inoltre il concetto di concorrenza e parallelismo, con l'illustrazione di esempi e la distinzione tra parallelismo di dati e di compiti. Viene presentata la legge di Amdahl e si analizza l'effetto del codice seriale sullo speedup. Infine, vengono esaminati vari modelli di multithreading, inclusi il modello many-to-one, one-to-one e many-to-many, insieme alle librerie di thread e agli approcci di threading implicito.
</details>

<details>
    <summary> <b> CPU scheduling </b> </summary>
    Nella gestione della CPU, lo scheduling dei processi determina quali processi vengono eseguiti nella ready queue, con concetti chiave quali burst CPU, preemption e dispatcher. Gli algoritmi non preemptive come FCFS e SJF, basato sulla stima dei tempi di burst CPU, sono efficaci ma limitati, mentre gli algoritmi preemptive come SRTF e RR migliorano la reattività ma possono causare starvation. Il priority scheduling e le code multilivello offrono alternative, assegnando priorità ai processi o suddividendoli in code con feedback, migliorando la gestione dei processi nei sistemi operativi.
</details>

<details>
    <summary> <b> Sincronizzazione </b> </summary>
    Il capitolo tratta principalmente di concetti legati alla sincronizzazione e alla gestione dei processi in un sistema informatico. Si discute l'utilizzo di semafori binari come il _mutex_ e il _read\_count_ per gestire l'accesso concorrente alle risorse. Viene esaminato il problema dei 5 filosofi, un classico esempio di sincronizzazione. Inoltre, si affronta il concetto di sezione critica e la necessità di cooperazione tra processi per evitare conflitti nella memoria condivisa.
</details>

<details>
    <summary> <b> Deadlocks </b> </summary>
    Il capitolo tratta i deadlocks, esaminando le condizioni che portano a un deadlock e gli algoritmi per gestirli. Si discute il modello di sistema con risorse singole e multiple, e si illustra una situazione classica di deadlock con due thread e semafori. Vengono elencate le 4 condizioni necessarie per un deadlock e si introduce il concetto di grafo risorsa-allocazione. Si menziona anche il concetto di livelock, una situazione simile al deadlock. Infine, si approfondiscono i metodi di prevenzione e di evitamento dei deadlock, inclusi l'algoritmo del banchiere e l'importanza dello stato sicuro.
</details>

<details>
    <summary> <b> Memoria principale </b> </summary>
    Il capitolo esplora la gestione della memoria principale in un sistema operativo, presentando la paginazione come soluzione alla frammentazione della memoria e spiegando la traduzione degli indirizzi. Si discute la frammentazione interna ed esterna e i problemi legati all'allocazione contigua e a partizioni fisse e variabili. Si affrontano concetti come il binding e l'MMU. In seguito, si esamina la tabella delle pagine, la TLB e le prestazioni correlate. Si analizzano tecniche di paginazione per sistemi a 64 bit e si discute il concetto di swapping, con diverse strategie e applicazioni nei dispositivi mobili. Infine, si introduce la segmentazione e si discute la sua combinazione con la paginazione in un modello ibrido.
</details>

<details>
    <summary> <b> Memoria virtuale </b> </summary>
    Il capitolo sulla memoria virtuale esplora come un sistema operativo gestisce la memoria utilizzando tecniche come il demand paging e il copy-on-write. Si discute l'introduzione dello spazio degli indirizzi virtuali e la possibilità di condividere la memoria tra processi. Il demand paging, che carica solo le pagine necessarie in memoria, viene esaminato insieme ai page fault e alle soluzioni per ottimizzare le prestazioni, come il prepaging e il copy-on-write. Inoltre, si analizzano gli algoritmi di rimpiazzo delle pagine, come FIFO e l'algoritmo ottimale, evidenziando le loro caratteristiche e l'effetto sull'efficienza complessiva del sistema. Il testo fornisce una panoramica completa delle strategie e delle tecniche utilizzate per gestire efficacemente la memoria virtuale in un sistema operativo, comprese le tecniche di allocazione dei frame e le modalità di allocazione della memoria del kernel.
</details>

<details>
    <summary> <b> Memoria di massa </b> </summary>
    Il capitolo sulla memoria di massa affronta la gestione e l'utilizzo ottimale della memoria secondaria, distinguendo tra HDD e NVM (NonVolatile Memory). Gli HDD sono più lenti ma hanno maggiore capacità di archiviazione, mentre le NVM, come gli SSD, sono più veloci ma meno durevoli. Si discute la gestione della scrittura e della cancellazione dei dati nelle NVM e si introduce il concetto di garbage collection. Vengono menzionati anche dispositivi come i RAM drives e i nastri magnetici per i backup. Si analizza l'indirizzamento della memoria secondaria e si esaminano gli algoritmi di scheduling per l'accesso ai dischi, come FCFS, SSTF, SCAN e C-SCAN, con una considerazione sulla scelta dell'algoritmo in base alle esigenze del sistema.
</details>

<details>
    <summary> <b> Sistema I/O </b> </summary>
    Il capitolo sul Sistema Input/Output (I/O) esplora l'importanza della gestione efficiente degli input e output nei computer, fondamentale per attività quotidiane come la scrittura di documenti e la connessione a Internet. Si discute dei componenti hardware coinvolti, come le porte di connessione e i bus di comunicazione, oltre ai controller che facilitano il collegamento tra periferiche e computer. Si esaminano le tecniche di comunicazione, inclusi il polling e gli interrupt, oltre al concetto di Direct Memory Access (DMA) per ottimizzare i trasferimenti di dati tra memoria e periferiche. La gestione software è trattata attraverso i device-drivers nel kernel, responsabili della comunicazione con le periferiche hardware, mentre i task del kernel includono la gestione delle code di richieste, degli errori e delle strutture dati necessarie per il controllo delle periferiche. Infine, si menzionano le pratiche per migliorare le performance del sistema I/O, come la riduzione dei context-switches e l'ottimizzazione dell'uso del DMA.
</details>

<details>
    <summary> <b> Interfaccia del file system </b> </summary>
    Il capitolo sull'Interfaccia del File System esplora il concetto e la gestione dei file all'interno dei sistemi operativi, delineando il concetto di file come uno spazio di indirizzi logici contigui per dati di vario tipo. Si discute anche delle estensioni dei file e dei loro attributi, come nome, identificatore, tipo, locazione, dimensione e protezione. Le operazioni sui file, come la creazione, la lettura, la scrittura, la cancellazione e il troncamento, sono presentate insieme alla gestione dei file aperti e al concetto di locking per l'accesso esclusivo ai file. La struttura della directory è analizzata attraverso diverse prospettive, tra cui la rappresentazione a uno e due livelli e la struttura ad albero, con considerazioni sulla gestione dei cicli e la protezione dei file e delle directory, come implementato nei sistemi Unix/Linux attraverso le liste di accesso. La sezione conclude con una panoramica sulla struttura del disco e delle partizioni.
</details>

<details>
    <summary> <b> Implementazione del file system </b> </summary>
    Il capitolo sull'implementazione del file system analizza dettagliatamente la struttura e le operazioni di questo sistema, esaminando anche i diversi metodi di allocazione dello spazio su disco e la gestione dello spazio libero. Attraverso un'analisi stratificata del file system, suddivisa in diversi livelli come il controllo I/O, il basic file system e il logical file system, il testo fornisce una panoramica completa delle funzionalità e delle sfide nell'implementazione di questa componente fondamentale dei sistemi operativi. Infine, vengono esplorati vari approcci per la gestione dello spazio libero, compresi il counting, il grouping e il metodo TRIM, che mirano a ottimizzare l'utilizzo dell'area disponibile su disco.
</details>

## Collaboratori

* Alessandro Trigolo (GitHub: [@imAlessas](https://github.com/imAlessas))

---

__Note__: This file has been mostly AI-generated.
