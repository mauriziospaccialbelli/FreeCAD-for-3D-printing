FREECAD PER LA STAMPA 3D
Lezione 01: Oggetti Solido e Shell di tipo Cad e Mesh, Formati e modellatori 3D

Benvenuti a tutti, sono Maurizio Spaccialbelli, questa lezione la trovi anche su [YouTube](https://www.youtube.com/playlist?list=PLQNfSBT6MZGS1SGfFDtfCbMwSAmQj7fuA) o in PDF su [Gumroad]() .

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Con piccole donazioni puoi scaricare file da me ottimizzati.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente

Questa guida è mirata all’uso di FreeCAD per la stampa 3D, richiede un’ esperienza minima di FreeCAD, Stampa 3D e Slicing.

OGGETTO SOLIDO E SHELL

Normalmente un oggetto per definirsi Solido deve essere completamente pieno o avere uno spessore, o meglio un volume, infatti gli oggetti solidi possono essere riprodotti nella realtà grazie a tecnologie di produzione, come la Stampa 3D.

Gli oggetti Shell/Guscio sono composti da più facce/superfici connesse tra loro. Una shell può essere aperta o completamente chiusa detta anche “a stagno”.

Una Shell aperta Non può essere riprodotta o stampata in 3D, mentre una “Shell a stagno” si! 
Una Shell a stagno in alcune situazioni è considerata un solido e lo vediamo durante la lezione.

Nella Stampa 3D quando modelliamo dobbiamo sempre ottenere un “modello solido” o almeno una “Shell a stagno”, con FreeCAD generalmente si ottengono “solidi”, ma in diverse situazioni possiamo anche avere “shell” o “Shell a stagno”

Le Forme 2D/3D in computer grafica possono essere create con diversi tipi di modellatori, che a loro volta possono utilizzare diverse tipi di modellazione, e diversi tipi di oggetti nativi e/o supportati.

Per esempio FreeCAD è un modellatore CAD parametrico che utilizza la modellazione geometrica grazie al kernel OPEN CASCADE.
FreeCAD essendo principalmente un CAD (disegno tecnico assistito) è mirato alle realizzazioni di modelli tecnico/meccanici/ingegneristici ed altro riguardate sempre il CAD.
FreeCAD lavora nativamente con Oggetti CAD, ma può importare e lavorare anche con altri tipi di oggetti.


OGGETTI CAD
In FreeCAD gli oggetti creati negli ambienti Part, Draft, Sketcher, Part design, sono oggetti CAD. La loro forma è accurata, precisa e matematicamente esatta alle misure date (guardare anche il numero di cifre decimali scelto in Preferenze → Generale → Unità → Numero di cifre decimali), quindi adatti a scopi tecnico/meccanici/ingegneristici.
Sinceramente la terminologia Oggetti/Modelli CAD Non so se sia esatta, comunque è intuitiva e senza conflitti con altre terminologie usate spesso in queste lezioni, quindi la uso.

Ecco un’immagine di alcuni oggetti CAD, il primo oggetto nell’albero(il Cubo) nella finestra 3D corrisponde al primo oggetto in alto a sinistra e cosi via come l’ordine di lettura occidentale(da sinistra a destra riga dopo riga).

Puoi vedere che gli Oggetti CAD possono essere Solidi, Shell, Shell a stagno, linee, archi, ecc…

Ora vediamo gli oggetti fondamentali nella stampa 3D… Gli oggetti Mesh! Fondamentali perché nei nostri slicer preferiti(Slic3r, prusa slicer, cura ecc…) dobbiamo importare dei file Mesh!

L’oggetto Mesh è l’oggetto nativo dei modellatori poligonali, come esempio di modellatore poligonale prendiamo “blender” un’altro famoso e potentissimo modellatore 3D a licenze libere, nato per creare oggetti organici/artistici(animali, persone, piante, personaggi ecc…) e moltissime altre cose.

In alcune situazioni la modellazione poligonale può essere usata per modelli tecnici, ma con i suoi limiti. Blender grazie ai componenti aggiuntivi può aumentare la sua efficienza in alcuni contesti, un esempio è l’architettura, ma si possono fare molti altri esempi.


OGGETTI MESH
La forma dell’oggetto Mesh è approssimata nelle curve, il livello di approssimazione è in base al numero di elementi da cui è composta.
Ora per conoscere e rendere visibili gli elementi della mesh, immagina di importare una Mesh Cubo in FreeCAD, con la Mesh selezionata fai CTRL + D e in modalità di visualizzazione scegli Flat lines, ora possiamo conoscere i Vertici, Spigoli e Facce… 

I Vertici sono i punti iniziali e finali di ogni Spigolo.
Le Facce sono i poligoni generati dagli spigoli e vertici, in questo tipo di Mesh i poligoni sono triangoli, il motivo di questa “triangolazione” si comprende durante le lezioni, ora andiamo avanti…

L’insieme di poligoni che definiscono la forma della Mesh è detta: Maglia/Rete poligonale.
Per conoscere il numero di elementi delle nostre Mesh importate o convertite in FreeCAD, basta selezionare l’oggetto mesh e guardare in pannello proprietà → scheda dati → Mesh. 

Attenzione: Con una multi-selezione di oggetti mesh, nella Scheda dati viene restituita la somma di vertici, spigoli e facce di tutte le mesh selezionate.

Da notare anche l’icona che FreeCAD usa per indicare gli oggetti Mesh.

Ora vediamo come sono definite le curve negli oggetti Mesh, sotto un’altra immagine con tre oggetti forati, uno dei quali è di tipo CAD(sinistra) e due di tipo Mesh con diversa approssimazione, la mesh a destra è più accurata rispetto a quella centrale.

Tutti gli oggetti nell’immagine successiva sono della stessa forma e visualizzati in modalità Flat lines.

La maglia poligonale di un oggetto Mesh è approssimata nelle curve perché è tassellata e generata da un numero definito di vertici, spigoli e facce.

Puoi notare che l’approssimazione della circonferenza del foro degli oggetti mesh, migliora se gli elementi che la definiscono aumentano, infatti non è esattamente una circonferenza, possiamo considerarla un insieme di spigoli.

Un numero maggiore di vertici, spigoli e facce, aumenta l’accuratezza nelle curve delle Mesh, ma una maglia poligonale più fitta appesantisce il peso in Mb dell’oggetto e aumenta i calcoli nelle operazioni con le Mesh.

Ora gli stessi oggetti forati visti  precedentemente, invece di visualizzarli in flat lines, li vediamo in modalità wireframe che ci nasconde le facce.
Gli oggetti CAD hanno solo elementi geometrici fondamentali, grazie ai quali viene calcolata la forma matematicamente esatta, mentre negli oggetti mesh è la maglia poligonale a definire la forma e in base alla quantità degli elementi che definiscono la maglia, la mesh sarà più o meno accurata, dunque “approssimata!”.

A prima vista può sembrare che un oggetto Mesh sia più complesso di un oggetto CAD, in realtà l’oggetto Mesh è matematicamente più semplice rispetto all’equivalente oggetto CAD.

Nelle prossime lezioni approfondiamo meglio altri dettagli della Mesh, come analizzarla prima di importarla nello Slicer, ed altre cose, ma visto che in questa lezione abbiamo già parlato di oggetti solidi, vediamo subito di comprendere la differenza tra “Solido Mesh” e “Solido CAD”

Prima di tutto scopriamo che…

L’oggetto Mesh è SEMPRE una shell!

Quando un Oggetto Mesh è una Shell a Stagno, per convenzione viene considerata un Solido Mesh, ma in realtà all’interno è vuoto! Fatta questa piccola precisazione, va sempre tenuto in considerazione che la mesh da importare nello slicer dovrà essere un Solido Mesh!

Invece un oggetto CAD che è una Shell a stagno, viene considerato per quello che è, una Shell! Un oggetto CAD shell a stagno, può essere convertito facilmente in solido tramite due strumenti che vediamo nelle prossime lezioni.

In FreeCAD gli oggetti mesh possono essere importati o creati dalla conversione che vediamo in una lezione dedicata. 

Ora scopriamo un’ultimo software libero che durante le prossime lezioni andiamo ad integrarlo in FreeCAD, il programma in questione è OpenSCAD (da Non confondere con il kernel OPEN CASCADE).
OpenSCAD è un CAD, più precisamente un compilatore CAD e può restituire sia oggetti CAD e sia oggetti Mesh.

In FreeCAD ci sono ambienti come Mesh Design e OpenSCAD dove erroneamente possiamo pensare di utilizzare la modellazione poligonale generando mesh, la modellazione poligonale in FreeCAD è utilissima grazie ai diversi strumenti presenti nei suddetti ambienti, ma pensare di usarla per modellare da zero un oggetto organico/artistico è sconsigliato, per questo esistono modellatori più adatti, per esempio blender.

È inutile aspettarci stesse tempistiche e funzionalità per fare una modifica organica/artistica in FreeCAD su una mesh importata... o magari creare una  forma organica/artistica da zero direttamente in FreeCAD…
Magari possiamo farlo e riuscirci, ma questo non significa che è il software giusto per ottenere questo genere di risultato.

Un’ultima nota: Possiamo fare operazioni solo tra oggetti dello stesso tipo, per esempio tra due mesh o tra due modelli CAD solidi.

ALCUNI FORMATI CAD e MESH

In FreeCAD possiamo esportare o importare molti formati, alcuni formati possono sempre tornare utili ed è meglio conoscerli, per prima cosa li dividiamo in due categorie…
    1. Formati CAD
    2. Formati Mesh

FORMATI CAD: Una esportazione in formato CAD mantiene la geometria matematicamente esatta, utile per importala in modellatori diversi da quello utilizzato, quindi ottimi per condividere modelli CAD tra diversi modellatori 3D. Ovviamente si perde lo storico delle operazioni, ma questo è normale.
Due formati CAD degni di nota e molto conosciuti/supportati sono il .step (o .stp), e il .iges (o .igs), ci sono molti altri formati liberamente utilizzabili, alcuni hanno limitazioni perché sono proprietari... per approfondire più avanti trovi due link.

Il .iges è il più vecchio e largamente supportato, mentre il .step è il suo successore e comunque molto supportato, ma ora andiamo avanti e vediamo i formati Mesh…


FORMATI Mesh: Esistono diversi formati Mesh, vediamone alcuni liberamente utilizzabili, utili nella stampa 3D e largamente compatibili.

I file Mesh sono indispensabili nella stampa 3D e servono per importarli nel nostro software di Slicer preferito (slic3r, prusaslicer, cura ecc…). Quindi in FreeCAD, finita la modellazione a scopo stampa 3D, si esporta/converte il nostro modello CAD nel formato Mesh desiderato, nelle prossime lezioni  vediamo tutto nel dettaglio.

I formati Mesh che è bene conoscere sono: .stl .obj .amf .3mf
NOTA: I formati .amf e .3mf dovrebbero essere descritti maggiormente, ma per comodità li definisco semplicemente Formati Mesh.

Il formato .stl è tra i più vecchi, è largamente utilizzato e Non memorizza materiali e texture.
Il .obj memorizza i dati dei materiali in un’altro file dello stesso nome con estensione .mtl, tuttavia la maggior parte degli slicer non possono sfruttare questa capacità perché il materiale è memorizzato su superfici invece di volumi.
Il .amf e .3mf memorizzano i materiali in volumi e quindi adatti per stampe multi-materiali e altro, sopratutto il .amf che FreeCAD ad oggi può solo esportare… e non è poco! Mentre ad oggi in FreeCAD non c’è nessun supporto per il .3mf.

Ci sono molti altri formati Mesh, anche se meno utilizzati negli Slicer, possono comunque interessare al mondo 3D in generale e alla stampa 3D, un paio si esempi sono il formato collada (.dae) e il .ply nato e utilizzato per gli scanner 3D.

Stessa cosa per i formati CAD… se vuoi per approfondire la compatibilità dei formati in FreeCAD in inport ed export, il consiglio è di seguire questi due link
    • https://wiki.freecadweb.org/Manual:Import_and_export_to_other_filetypes/it
    • https://wiki.freecadweb.org/Import_Export/it

Per questa lezione abbiamo finito, spero ti sia piaciuta e ti ricordo che le lezioni di “FreeCAD per la Stampa 3D” le trovi su YouTube come video lezioni.

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Con piccole donazioni puoi scaricare file da me ottimizzati.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente

Un saluto, a presto… 
Maurizio Spaccialbelli(Maurino Web)
