# Immagini-Satellitari-e-Riduzione-dimensinalita
# Analisi di times series da immagini Sentinel-2 nell’ambito della LandSurface Phenology mediante maching learning



## Concetti Introduttivi
![Mappatura vegetazione sovrapposta ad una mappa topografica](/ma.png)


Alcune specie vegetali hanno distinti cicli di vita, determinati dalla caduta, dalla crescita del fogliame e da periodi di intensa attività di fotosintesi. In natura ogni elemento che viene "colpito" da radiazione elettromagnetica assorbe, trasmette e riflette. Nel caso in esame si è interessati alla porzione che viene riflessa in quanto i sensori montati a bordo di droni / aerei / satelliti per il tele-rilevamento sono progettati per misurare la riflettanza. Un modo oramai consolidato per mappare la vegetazione è quello di studiare la riflettanza nello spazio e nel tempo (time-series). In molti lavori come \cite{4} viene spiegato quali sono i sensori che permettono di misurare la riflettanza ad esempio il LAI-200-Plant-Canopy-Analyzer.

Lo studio di come la riflettanza varia nel tempo ricade nell'ambito della **Land Surface Phenology (LSP)**. In molti casi lo scopo è quello di produrre delle mappe tematiche derivanti dalla classificazione con tecniche di **machine learning** spesso con approcci supervisionati. Solitamente il monitoraggio della vegetazione viene fatto da operatori e tale aspetto è molto oneroso dal punto di vista del tempo e dei costi. Oltre ad avere problemi a raggiungere alcune zone, il rilevamento può essere soggetto anche a bias/errori da parte dell'utente. Una soluzione è quella dunque di automatizzare il processo di generazione di mappe fito-sociologiche. Tali mappe si sono dimostrate essere nel tempo uno strumento fondamentale per il monitoraggio degli habitat naturali e semi-naturali, poiché necessitano di poche risorse e il rilevamento ottenuto è migliore del precedente. Il lavoro effettuato su queste aree potrà poi essere applicato a diverse aree che necessitano lo stesso tipo di mappatura quindi offre massima flessibilità. Gli studi di seguito citati fanno riferimento al tele-rilevamento della vegetazione\cite{1} e alla mappatura degli habitat forestali\cite{2} molto utili per capire quali siano i parametri da analizzare. In \cite{3} gli autori definiscono una metodologia di analisi dei dati satellitari di tipo Sentinel-2.

Il progetto Copernicus Global Land Service \cite{5}  fornisce dati utili al nostro progetto. Viene fornito, ad esempio attraverso l'elaborazione dei dati è possibile calcolare indici vegetazionali come ad esempio l'NDVI che forniscono utili indicazioni circa lo stato della vegetazione.

![Sentinel 2 ](/Sentinel-2_pillars.jpg)

## Obiettivi Progetto

L'obiettivo del progetto è quello di processare un set di immagini satellitari di Sentinel-2 con lo scopo di classificare le specie vegetali a supporto della creazione di mappe fito-sociologiche. Le immagini sono acquisite nell'areale noto come Val Montagnana (provincia di Ancona). Le immagini scelte su diversi anni consentono di coprire il maggior numero di settimane possibili. A partire da tali immagini attraverso l'utilizzo di librerie R e di notebook JupyterLab vengono applicate diverse tecniche con lo scopo di sviluppare dei modelli atti a classificare ogni singola time-series. Viene utilizzato un approccio che consente di ridurre la dimensionalità; tale approccio è noto in letterature come **Functional Principal Component Analysis (FPCA)**; in seguito a partire dagli FPCA score si crea un modello di apprendimento supervisionato a supporto della classificazione. In \ref{fig:mission} si riporta l'area di studio.

![Riduzione dimensinalità](/domenica0.jpg)

Le immagini illustrano la stessa zona d'interesse con mappe geografiche diverse.  
A sinistra abbiamo un immagine satellitare di Google Earth. La seconda è una mappa 2D creata in Qgis. Nella terza immagine sono presenti le classi di vegetazione che sono state rilevate.


## Software Utilizzati:

- **R-linguaggio**: R è un linguaggio di programmazione open-source e un ambiente di sviluppo per l'analisi statistica e la visualizzazione dei dati. È ampiamente utilizzato nella statistica e nell'analisi dei dati.

- **JupyterNotebook**: Jupyter Notebook è un'applicazione web open-source che consente di creare e condividere documenti interattivi contenenti codice, testo narrativo, grafici e altro ancora. È spesso utilizzato per l'analisi dei dati e l'apprendimento automatico.

- **Anaconda**: Anaconda è una piattaforma open-source per la gestione di ambienti Python e R, che facilita l'installazione di pacchetti e librerie scientifiche. È ampiamente utilizzato nella scienza dei dati.

- **QGIS**: QGIS (Quantum Geographic Information System) è un sistema open-source di informazioni geografiche (GIS) che consente di visualizzare, modificare e analizzare dati geospaziali. È utilizzato per la cartografia e l'analisi geografica.

- **Overleaf**: Overleaf è una piattaforma online per la scrittura collaborativa di documenti scientifici e tecnici in LaTeX. È spesso utilizzato per scrivere documenti accademici, tesi e articoli di ricerca.

- **Sentinel-2A e Sentinel-2B**: Sentinel-2A e Sentinel-2B sono satelliti della missione Sentinel-2 dell'Agenzia Spaziale Europea (ESA). Questi satelliti forniscono dati ad alta risoluzione utilizzati per monitorare l'ambiente terrestre, tra cui l'uso del suolo, la copertura vegetale e altro ancora.

## Algoritmi Utilizzati:Riduzione della dimensionalità nel progetto

La riduzione della dimensionalità è un processo che consiste nel ridurre il numero di variabili in un set di dati, preservando al contempo le informazioni rilevanti. In questo progetto, sembra che siano stati utilizzati diversi algoritmi per la riduzione della dimensionalità.

- **PCA (Principal Component Analysis)**: PCA è una tecnica di riduzione della dimensionalità che cerca di trovare le componenti principali (le direzioni di massima variazione) nei dati. Viene spesso utilizzata per semplificare l'analisi dei dati e la visualizzazione.

- **FPCA (Functional Principal Component Analysis)**: FPCA è una variante di PCA che viene utilizzata quando si lavora con dati funzionali, ad esempio serie temporali o curve. Aiuta a identificare le principali tendenze o modalità di variazione nei dati funzionali.

- **MFPCA (Multilevel Functional Principal Component Analysis)**: MFPCA è una tecnica avanzata di analisi delle componenti principali che viene utilizzata quando si hanno dati funzionali a più livelli, ad esempio dati gerarchici o dati stratificati.

