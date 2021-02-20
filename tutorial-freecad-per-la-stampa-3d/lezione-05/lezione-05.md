FREECAD PER LA STAMPA 3D
Lezione 05: Metodo 2: Conversione con crea mesh da una forma

Benvenuti a tutti, questa lezione la trovi su [YouTube](https://www.youtube.com/playlist?list=PLQNfSBT6MZGS1SGfFDtfCbMwSAmQj7fuA) e in PDF su [Gumroad](https://gum.co/freecad-per-la-stampa-3d-05) .

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Puoi scaricare file da me ottimizzati e fare piccole donazioni.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente


Indice e argomenti della lezione:
    • Metodo 2: Conversione con crea mesh da una forma.
    • Perchè scegliere opzione mesh “standard”.
    • Un’occhiata a Crease angle.
    • Valori minimi ed altre opzioni utilizzando l’opzione mesh “standard” e link approfondimento
    • PRO e CONTRO di “crea mesh da una forma”.

Nella lezione precedente abbiamo visto il “Metodo 1: Esportazione da CAD a Mesh”, che usa i parametri di tassellazione degli oggetti CAD per convertire un oggetto CAD in Mesh durante l’esportazione.

Oggi vediamo il “Metodo 2: Conversione con crea mesh da una forma” dove utilizziamo lo strumento “Crea mesh da una forma” dell’ambiente Mesh design, esso converte l’oggetto CAD in Mesh direttamente nel pannello struttura, ha i propri valori per approssimare e creare la maglia poligonale.


	METODO 2:  CONVERSIONE CON CREA MESH DA UNA FORMA

Ora seleziona il tuo solido valido/affinato e vai in ambiente Mesh Design → menu Mesh → Crea mesh da una forma, o usa il pulsante dedicato… 

NOTA: Io nell’immagine ho utilizzato una fusione di tre primitive, un cubo, un cilindro ed una sfera, tutti con grandezze di default, la sfera l’ho spostata in Z di 14mm.

Cliccando su “Crea mesh da una forma” nella finestra azioni si apre la finestra dello strumento…

Nelle “opzioni di mesh” si possono scegliere diverse tipi di conversioni: Standard, Mefisto, Netgen, gmsh(FreeCAD 0.19), alcune di esse richiedono l’installazione nel sistema operativo  per funzionare.
Ogni opzione mesh ha i propri parametri per regolare l’approssimazione, e restituisce un suo tipo di maglia poligonale, più o meno adatto all’utilizzo che si deve fare della Mesh.
Ora scegliamo l’opzione mesh “standard” come nell’immagine precedente, più avanti vediamo il perché, per ora andiamo avanti…

Ci sono due parametri per regolare l’approssimazione in “standard”, sono molto simili a quelli già visti nella lezione precedente.
In “Deviazione di superficie” metti 0,1mm, in “Deviazione angolare” metti 30° e clicca sul pulsante “OK”.

Puoi notare che la mesh è comodamente nell’albero degli oggetti(pannello struttura), questo evita un’importazione aggiuntiva della mesh, per analizzarla ed eventualmente ripararla.

La mesh è sicuramente da migliorare, se la stampi cosi sarà troppo spigolosa, quindi rifai la conversione con la stessa procedura appena descritta, ma con “deviazione di superficie” a 0,01mm.

La mesh a 0,01mm è più definita, anche la cucitura della sfera è migliorata!
Rispetto al metodo 1 visto nella lezione precedente, qui la mesh risultante è sempre convertita utilizzando i parametri della “opzione mesh” scelta, in questo caso “standard”.
Tutti i parametri che riguardano la tassellazione degli  oggetti CAD e “massima deviazione della maglia” visti nel metodo 1, sono ignorati.

Per esportare la mesh puoi utilizzare la classica esportazione da file → esporta o utilizzare il pulsante specifico “esporta mesh” presente in ambiente mesh… 

Da notare che un’esportazione da Mesh a Mesh, esporta esattamente la stessa maglia poligonale senza utilizzare nessuna tassellazione su di essa, anche se ovvio ho ritenuto opportuno dirlo.

NOTA: La deviazione della superficie nella opzione “standard” è in mm.


PERCHÈ SCEGLIERE L’OPZIONE MESH “STANDARD”

Ecco un’immagine per vedere la differenza tra le opzioni mesh disponibili, utile per comprendere meglio il perché nella stampa 3D si utilizza l’opzione standard… 

L’opzione “Standard”, restituisce mesh leggere e sufficientemente accurate per la stampa 3D, perché ottimizza il numero degli elementi sulle superfici piane e nelle curve, non a caso è lo stesso tipo di triangolazione utilizzata per visualizzare gli oggetti CAD nella finestra 3D.

L’opzione standard nella stampa 3D è l’opzione più adatta nella maggior parte delle situazioni.
Le altre “opzioni Mesh” sono spesso utilizzate in diversi contesti come l’analisi elementi finiti, animazione e altri campi di applicazioni/simulazioni fisiche, ecc…


CREASE ANGLE

Crease angle è presente nella scheda vista con un oggetto Mesh selezionato, esso migliora solo visivamente la mesh, quindi geometricamente rimane dell’approssimazione data dalla sua maglia poligonale. Nella stampa 3D il  consiglio è di usare Crease angle “a zero”, cosi da ottenere una visualizzazione reale della maglia poligonale.

Se non vedi gli spigoli come nell’immagine, seleziona la mesh, vai in scheda vista e controlla che il valore di crease angle sia a zero.

VALORI MINIMI E OPZIONI DI “CREA MESH DA UNA FORMA”

Anche con il “Metodo 2: conversione con crea mesh da una forma” e l’utilizzo dell’opzione mesh “standard”, nessun consiglio sui valori da utilizzare, perchè dipende da diversi fattori specificati nella lezione precedente, esclusa la grandezza del modello per quel che riguarda la deviazione di superficie, che in “crea mesh da una forma” è in millimetri e NON in percentuale.

Ora vediamo i valori minimi possibili… 

    • Deviazione della superficie: Puoi iniziare da 0,1mm fino a scendere a 0,001mm raggiungendo la massima accuratezza.
    • Deviazione angolare: Puoi iniziare da 30° fino a scendere tra i 15°/10° o meno… si può arrivare fino a 1°.

Ci sono altre opzioni nella finestra azioni scegliendo l’opzione mesh “standard”, ma questo non è il contesto adatto per utilizzarli/approfondirli, comunque gli diamo un’occhiata veloce...

    • Deviazione relativa alle superfici: In questo caso puoi tralasciarla e non utilizzarla.
    • Applica i colori delle facce alla mesh: Utile per mantenere i colori delle facce anche sulla mesh esportata, ma devi esportarla con lo strumento “esporta mesh” dell’ambiente mesh design ed utilizzare il formato .obj, ma questo è fuori tema con la Stampa 3D.
    • Definisci i segmenti con i colori delle facce: sinceramente mai provato

Ecco due link per approfondire lo strumento “Crea mesh da una forma” 
    • https://wiki.freecadweb.org/Mesh_FromPartShape/it.
      
    • https://old.opencascade.com/doc/occt-7.3.0/overview/html/occt_user_guides__modeling_algos.html#occt_modalg_11_2

PRO E CONTRO

Vediamo i vantaggi e svantaggi del “Metodo 2: Conversione con crea mesh da una forma” utilizzando l’opzione mesh “standard”.

PRO: 
    • Le mesh generate vengono aggiunte direttamente nel pannello struttura, quindi si evitano importazioni per eventuali analisi e riparazioni.
    • Con una multi-selezione di oggetti CAD, ogni oggetto viene convertito singolarmente e aggiunto nell’albero, quindi viene creato un oggetto mesh per ogni oggetto CAD selezionato.

CONTRO: 
    • Nessuna anteprima della mesh prima della conversione.


Per questa lezione abbiamo finito, spero ti sia piaciuta e ti ricordo che le lezioni di “FreeCAD per la Stampa 3D” le trovi su [YouTube](https://www.youtube.com/playlist?list=PLQNfSBT6MZGS1SGfFDtfCbMwSAmQj7fuA).

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Puoi scaricare file da me ottimizzati e fare piccole donazioni.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente



Un saluto, a presto… 
Maurizio Spaccialbelli(Maurino Web)

