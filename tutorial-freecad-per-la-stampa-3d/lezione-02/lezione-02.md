FREECAD PER LA STAMPA 3D
Lezione 02: Tassellazione oggetti Cad, linee nascoste, le normali

Benvenuti a tutti, questa lezione la trovi su [YouTube]() e in PDF su [Gumroad]() .

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Con piccole donazioni puoi scaricare file da me ottimizzati.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente

Indice e argomenti della lezione:
    • La tassellazione degli oggetti CAD, come regolarla e le linee nascoste
    • Un piccolo esercizio con gli snap per comprendere la tassellazione sugli oggetti CAD.
    • Un accenno alle normali.

Per tassellazione, si intende ciò che hai visto nella lezione precedente durante la spiegazione della Mesh e della maglia poligonale che la definisce, infatti la Mesh è composta da una forma tassellata, ovvero la maglia poligonale!

Ora vediamo che la tassellazione riguarda anche gli oggetti CAD…


LA TASSELLAZIONE DEGLI OGGETTI CAD

Gli oggetti CAD sono matematicamente più affamati, la sola visualizzazione di essi nella finestra 3D porterebbe a lunghe attese, quindi serve qualcosa che alleggerisca i calcoli di visualizzazione degli oggetti CAD, che possa essere “regolata” in base alla capacità di calcolo del nostro computer e in base al progetto.

FreeCAD, con lo scopo di alleggerire i calcoli di visualizzazione degli oggetti CAD, usa la tassellazione! Quindi crea una maglia poligonale dell’oggetto CAD e la visualizza nella finestra 3D, non si nota molto perché ci sono delle linee nascoste che vediamo a breve. 
Comunque a differenza dell’oggetto mesh, l’oggetto CAD è matematicamente esatto, ma nella finestra 3D viene visualizzato approssimato!
Quando stai guardando un oggetto CAD nella finestra 3D, in realtà stai osservando una Mesh approssimata dell’oggetto CAD!

Attenzione a NON confondere la tassellazione degli oggetti CAD con quelli Mesh:
    • Gli oggetti Mesh nella finestra 3D sono visualizzati esattamente cosi come sono, tassellati per loro natura.
    • Gli oggetti CAD vengono tassellati al solo scopo di ottimizzare i calcoli di visualizzazione. In realtà la forma dell’oggetto CAD rimane matematicamente esatta anche nelle curve, presto sarà più chiaro.
FreeCAD intelligentemente e di predefinito, nasconde quasi completamente la maglia poligonale dell’oggetto CAD tassellato, normalmente visualizza solo le linee fondamentali della geometria anche se viene impostata una visualizzazione wireframe o flat lines.

Infatti, nell’immagine puoi notare che i due oggetti CAD a destra nascondono quasi completamente la maglia poligonale, più avanti vediamo come visualizzare l’intera maglia poligonale dell’oggetto CAD. 

Ora vediamo che la tassellazione degli oggetti CAD può essere cambiata.
In FreeCAD abbiamo dei valori per regolare la tassellazione degli oggetti CAD, nelle prossime lezioni vediamo un metodo che utilizza questi valori per esportare un oggetto CAD in Mesh!

Puoi cambiare ed applicare i valori di tassellazione a livello globale in menu Modifica → Preferenze → Part design → Visualizzazione della figura → Tassellazione, dove ci sono i parametri “massima deviazione” e “massima deflessione angolare” (Per avere la sezione Part design nelle preferenze, devi avviare almeno una volta l’ambiente Part o Part design).

Mentre se vuoi applicare una deviazione e/o deflessione su un singolo oggetto, devi selezionare l’oggetto ed andare su: pannello proprietà → scheda vista, e trovi gli stessi parametri.

Attenzione… anche se i parametri presenti in preferenze si trovano nella sezione “Part design”, i valori di tassellazione impostati vengono applicati a tutti gli oggetti CAD del documento, indipendentemente dall’ambiente dove sono stati creati o importati.
Con un valore/i di tassellazione alto, l’oggetto CAD è “visivamente” meno accurato e viene visualizzato più velocemente, mentre abbassando il valore/i di tassellazione dell’oggetto CAD, esso è “visivamente” più accurato, ma aumentano i tempi di calcolo di visualizzazione.

Ora un’altra immagine di tre oggetti CAD “cilindri”, sovrapposti e visti dall’alto, ognuno con diversa tassellazione… 

Osservando la circonferenza del cilindro grigio puoi notare la tassellatura come abbiamo visto nelle mesh, ma attenzione ricorda che stiamo parlando di tassellazione su oggetti CAD!

Anche se l’oggetto CAD viene visualizzato “approssimato” rimane matematicamente esatto!!  Presto facciamo un esercizio per dimostrarlo

Se provi a cambiare la deviazione o deflessione dell’oggetto CAD nella Scheda vista, la tassellazione nella finestra 3D si aggiorna solo se abbassi i parametri, se li aumenti no!
Per assicurarsi di avere l’oggetto con tassellazione aggiornata nella finestra 3D, ricalcola l’oggetto! Su FreeCAD 0.18 selezioni l’oggetto, vai nel pannello struttura e con tasto destro del mouse metti “segna da ricalcolare”, poi clicchi sulla freccia ricalcola. Su FreeCAD 0.19 stessa cosa, ma il menu a tendina nel pannello struttura ha direttamente “ricalcola l’oggetto”.

Il valori di tassellazione predefiniti nelle preferenze vanno bene nella maggior parte dei PC e Notebook, questi valori sono: Deviazione: 0.5% / Deflessione: 28,5°
Puoi abbassare questi valori per visualizzare tutti gli oggetti CAD del documento più definiti, ma aumenti i calcoli dei tempi di visualizzazione e conseguentemente del documento.
Ti invito a fare dei test sul tuo computer con documenti almeno di media complessità, ricorda che la matematica dell’oggetto CAD è sempre esatta indipendentemente dai valori di tassellazione inseriti.
Una piccola nota: Ogni volta che apri il menù preferenze e clicchi su ok, ogni oggetto torna alla deviazione e deflessione inserite nelle preferenze, quindi perdi le modifiche di tassellazione “locali” fatte nella scheda vista, tuttavia in questo contesto, cambiare i valori di tassellazione sul singolo oggetto è utile temporaneamente in alcune situazioni, nelle prossime lezioni vediamo quando e perchè farlo!


LINEE NASCOSTE

Fino ad ora abbiamo visto che la maglia poligonale creata per visualizzare gli oggetti CAD è in parte nascosta, e che normalmente sugli oggetti CAD ci vengono mostrate solo le linee fondamentali della geometria, questo è giusto altrimenti nascerebbe confusione tra oggetti CAD e Mesh, ma in alcuni contesti, riuscire a visualizzare l’intera maglia poligonale nata dalla tassellazione di un oggetto CAD può tornare utile, grazie all’attivazione delle linee nascoste puoi vedere tutta la maglia poligonale degli oggetti CAD, proprio come un oggetto Mesh in modalità di visualizzazione Flat lines o Wireframe.

Nelle prossime lezioni vediamo come sfruttare le linee nascoste. 

Le linee nascoste si attivano da “stile di disegno” che trovi in due modi:
    1. Nella barra degli strumenti Vista → pulsante stile di disegno → linee nascoste.
    2. Tasto destro del mouse su finestra 3D → Stile di disegno → linee nascoste.
       
Piccola nota: Lo stile di disegno viene applicato globalmente su tutti gli oggetti, sovrascrive la modalità di visualizzazione scelta sul singolo oggetto nella finestra aspetto (CTRL + D). 
Di predefinito lo stile di disegno è su “Come è”, in questo stato non sovrascrive nulla e gli oggetti vengono visualizzati in base alla modalità di visualizzazione impostata nella finestra aspetto (CTRL + D).


ESERCIZIO TASSELLAZIONE OGGETTI CAD

Ora un piccolo esercizio dimostrativo per comprendere meglio una frase che ho scritto più volte…  

“Un oggetto CAD rimane matematicamente esatto, ma è visualizzato approssimato”

Vai in ambiente Draft, metti vista dall’alto, scegli il piano XY, disegna una arco con il suo centro a X0, Y0, Z0, con raggio a 10mm, angolo iniziale 0° con apertura di 90°.

Ora seleziona l’arco e nella scheda vista come valore di deviazione metti “2” e ricalcola l’oggetto... è una esagerazione, ma ottima a scopo illustrativo.

Ora disegna una linea, come primo punto scegli X0, Y0, Z0, come secondo punto attiva lo snap punto medio e agganciati al punto medio dell’arco.

Dall’immagine si nota subito che gli snap si agganciano alla forma matematicamente esatta e Non alla forma tassellata,  se hai fatto l’esercizio puoi notarlo anche con lo zoom dal pc.

Attenzione: con lo snap “vicino”, esso si  aggancia alla forma tassellata e Non a quella matematicamente esatta, quindi lo snap “vicino” è Sconsigliato se vuoi agganciarti alle curve.



LE NORMALI

I modellatori 3D, per capire il verso di una superficie/faccia (interno ed esterno), usa le normali, ovvero un vettore/i sulle facce. Semplicemente puoi immaginare una freccia per ogni faccia, questa freccia immaginala perpendicolare alla faccia, e nascosta all’utente.

FreeCAD come altri modellatori usa le normali per capire quale sia l’interno e l’esterno di una superficie e quindi dell’oggetto stesso.

Le normali sono usate sia negli oggetti CAD e su oggetti Mesh.
Il verso interno delle facce normalmente è di colore Nero(se usi one side che vediamo nella prossima lezione).

Aggiungo una nota importante che ho imparato nella comunità di FreeCAD, la quale ringrazio come sempre…

Delle volte quando disegni delle linee, archi, rettangoli ecc.. e li estrudi creando una shell, può succedere che il verso delle normali sia invertito rispetto a quello che ti aspetti, per esempio l’immagine precedente con interno ed esterno invertite rispetto a quello che vedi, in tal caso si potrebbe pensare di avere delle normali invertite(al contrario), invece è tutto ok!

Il verso delle normali durante la creazioni di oggetti come linee, archi, rettangoli ecc… è deciso in base al verso di costruzione(orario o antiorario) di suddetti oggetti. Comunque nel caso di una shell a stagno o di un solido, le normali prendono il verso che ci si aspetta.

Per questa lezione abbiamo finito, spero ti sia piaciuta e ti ricordo che le lezioni di “FreeCAD per la Stampa 3D” le trovi su YouTube come video lezioni.

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Con piccole donazioni puoi scaricare file da me ottimizzati.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente

Un saluto, a presto… 
Maurizio Spaccialbelli(Maurino Web)
