FREECAD PER LA STAMPA 3D
Lezione 03: Modellazione Stampa 3D, One e Two Side, Controllo, Affina e Converti solido

Benvenuti a tutti, questa lezione la trovi su [YouTube](https://www.youtube.com/playlist?list=PLQNfSBT6MZGS1SGfFDtfCbMwSAmQj7fuA) e in PDF su [Gumroad](https://gum.co/freecad-per-la-stampa-3d-03) .

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Con piccole donazioni puoi scaricare file da me ottimizzati.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente

Una piccola nota riguardo la lezione:
    • Anche se diverse cose trattate in questa lezione possono essere utili su diverse tecnologie di produzione, il focus rimane sulla tecnologia di stampa 3D FFF/FDM.

Ora, prima di vedere la diversa gestione delle colorazioni (one side e two side), vediamo come cambiare i colori agli oggetti o facce, ci sono due modi per farlo, ognuno con le sue funzionalità:

    • Cambiare colore all’oggetto CAD o Mesh: Selezioni l’oggetto → apri la finestra aspetto con tasto destro mouse(su finestra 3D o pannello struttura) → clicchi aspetto. Puoi aprire la finestra aspetto anche con la scorciatoia da tastiera CTRL + D (con oggetto selezionato).
      
    • Cambio colore a singole facce(solo su oggetti CAD):  Selezioni l’oggetto e vai in pannello struttura →  tasto destro mouse → Imposta colori. In FreeeCAD 0.19 c’è il pulsante dedicato in ambiente Part

Ti ricordo che FreeCAD è molto personalizzabile, per esempio uno strumento che trovi in un ambiente può essere inserito in tutti gli ambienti. Per aggiungere comandi/pulsanti/macro in barre degli strumenti personalizzate, vedere la seconda lezione del tutorial FreeCAD 0.18/0.19.

COLORAZIONE/RENDERING “ONE SIDE” E “TWO SIDE”

In FreeCAD puoi scegliere due modi diversi per gestire la colorazione degli oggetti:

    • One side: Colora/renderizza solo il lato esterno della facce e permette di capire il verso delle normali.
      
    • Two side: Colora/renderizza entrambi i lati delle facce, interno ed esterno. È la scelta predefinita, ma Non permette di capire il verso delle normali.



In qualsiasi oggetto Solido, che sia CAD o Mesh, deve essere visibile solo l’esterno e mai l’interno! L’uso di “One side” è consigliato se si vuole tenere sotto controllo il verso delle normali viste nella lezione precedente.

Una tecnica può essere: Evitare il colore nero come colorazione delle facce o modello, e usare “One side”. Cosi mentre modelli dei solidi la sola vista del nero diventa allarmante!

Infatti, usando la semplice tecnica sopra descritta, quando vedi del nero su un oggetto significa che hai una o più normali invertite(inverse rispetto la logica del modello), o il modello è una shell e riesci ad intravedere l’interno che in “one side” è nero! In questi casi, devi sistemare il modello altrimenti FreeCAD e il nostro Slicer possono comportarsi stranamente.


Ti invito a seguire le lezioni di FreeCAD 0.18/0.19 per imparare a creare modelli robusti sia con la modellazione Geometria Solido Costruttiva(Ambiente Part) e con la Modifica delle funzioni(Ambiente Part design).

One side e Two side in FreeCAD puoi applicarli globalmente(FreeCAD 0.19) o al singolo oggetto.

Per applicare one/two side sul singolo oggetto:
Seleziona un oggetto, vai in pannello proprietà → scheda vista → lighting… cosi la scelta viene applicata solo sull’ oggetto selezionato.

Per applicare one/two side su tutti i nuovi oggetti:
In FreeCAD 0.19 c’è la possibilità di disattivare il “Two side” nelle preferenze, disattivandolo verrà usato “One side” globalmente su tutti i nuovi oggetti.
Puoi disattivarlo da Modifica → Preferenze → Part Design → shape appearance → Two-side rendering.


CONSIDERAZIONI PER LA MODELLAZIONE A SCOPO STAMPA 3D

Prima di cominciare la modellazione a scopo stampa 3D, è bene avere le idee chiare e decidere alcune cose prima di cominciare a modellare, quindi bisogna prendere in considerazione alcuni fattori, grazie ai quali andiamo a decidere o mantenere altezze, spessori, rinforzi, supporti personalizzati, modificatori, assemblaggi ecc… Tutto sempre considerando lo scopo dell’oggetto ed il metodo di produzione che in questo caso è la Stampa 3D fff/fdm.

Non tutti i seguenti fattori sono indispensabili, tuttavia ognuno di essi se deciso prima della progettazione 3D, può tornare utile per aumentare il controllo nello Slicer e conseguentemente anche il risultato della Stampa.

    • Diametro ugello: Ti permette di sapere quale spessore minimo e massimo può avere un singolo perimetro, quindi puoi prevedere alcuni comportamenti dello Slicer, per esempio il numero di perimetri in determinate pareti. Utile per evitare di avere pareti più sottili rispetto allo spessore minimo stampabile dell’ugello scelto, ed anche per determinare l’altezza massima dello strato.
      
    • Orientamento del modello sul piatto di stampa: Ti permette di evitare supporti quando possibile con semplici raccordi o smussi, o altre scelte che evitano il supporto. Utile anche per decidere se e come rinforzare il modello, in base alle forze che devono essere esercitate sul pezzo stampato.
      
    • Altezza strato/layer: Prima devi decidere l’orientamento del modello sul piatto di stampa, ora grazie all’altezza strato puoi controllare tutte le altezze che ti interessano (supporti personalizzati, modificatori, ponti, tasche/incassi, agganci rapidi che richiedono precisione, ecc…). In determinati punti del modello è utile per avere altezze multiple dell’altezza strato, ovviamente misurando tali altezze dall’ipotetico piatto di stampa(o da un’altro strato), o per creare supporti personalizzati, o modelli da utilizzare come modificatori ecc… Quando usi l’altezza strato variabile, questa considerazione può perdere efficacia.
      
    • Grandezza area di stampa: Il più ovvio… utile per decidere come dividere e assemblare il pezzo quando supera la grandezza massima stampabile, o progettarlo in base alla grandezza dell’area di stampa.



Ora andiamo a vedere un semplice esempio di slicing immaginando di voler ottimizzare la velocità di stampa con un ugello da 0,4mm su un ipotetico modello 3D.
Non vuole essere una lezione di slicing e mancano informazioni per esserlo, magari faccio una serie dedicata allo slicing, comunque spero possa essere utile per comprendere meglio alcune considerazioni appena fatte… 

Utilizzando un ugello da 0,4 mm, la parete minima è di 0,84 mm circa, questo perché lo spessore minimo dei perimetri è 0,42/0,43 mm, mentre l’altezza strato massima è di 0,3 mm. Da notare che le misure delle altezze(blu) sono multipli dell’altezza strato scelta(0,3mm).



In verità queste sono misure “di sicurezza” che garantiscono la miglior precisione e fusione tra i perimetri, tuttavia in base allo scopo del modello si può dare più o meno importanza a tali considerazioni andando a utilizzare “misure non consigliabili”, per esempio spessore dei perimetri a 0,25/0,3 mm con ugello da 0,4 mm.

Questo orientamento del modello di esempio ha bisogno di supporti, in base al suo scopo possiamo fare modifiche per evitarli.
Anche l’orientamento del modello va deciso in base al suo scopo, un diverso orientamento di stampa cambierebbe/invertirebbe misure e considerazioni fatte nell’immagine precedente.

Per ottimizzare tempi di stampa, possiamo utilizzare una larghezza di estrusione massima sui riempimenti vari a discapito della stabilità del flusso(spesso inevitabile), ma andiamo avanti.


TRE STRUMENTI FONDAMENTALI

Ora vediamo tre strumenti presenti nell’ambiente Part da utilizzare sui nostri oggetti CAD, utili e funzionali anche in altri ambienti.

AFFINA UNA FORMA: Questo pulisce l’oggetto CAD dagli spigoli di troppo nati durante le operazioni, basta selezionare l’oggetto CAD e cliccare su “Affina una forma”.

Affina una Forma in FreeCAD 0.18 lo trovi in Ambiente Part → menu parte → Affina una forma.

Mentre in FreeCAD 0.19 affina una forma è parametrico, lo trovi in Ambiente Part → menù parte → Crea una copia → Affina una forma

Ecco un’immagine che mostra come affina una forma elimina le linee di troppo:


Per avviare “affina forma” automaticamente puoi spuntare la casella in…

Modifica → Preferenze → Part design → affina automaticamente il modello dopo un’operazione booleana.

Nella stessa posizione puoi automatizzare affina forma anche in part design… 

Modifica → Preferenze → Part design → Ridefinisci/affina automaticamente il modello dopo le operazioni basate sugli sketch.

CONVERTI IN SOLIDO: Questo strumento converte in solido l’oggetto CAD selezionato, ma è consigliabile affinarlo prima con “Affina una forma” e poi convertirlo in solido.

Per usarlo devi selezionare l’oggetto CAD e poi “Converti in solido”.
    • Se l’oggetto selezionato è già un solido, non succede nulla e nel pannello report viene segnalato che l’oggetto è già un solido, quindi il comando viene ignorato.
    • Se l’oggetto selezionato Non è un solido, viene creato un nuovo oggetto dello stesso nome con l’aggiunta di “solid” nel nome dell’oggetto.
    • Nel caso di errore nella conversione, nel pannello report viene segnalato l’errore.

Converti in solido lo trovi in ambiente Part → menu parte → Converti in solido 

C’è un comando simile che trovi in ambiente part, è un’opzione dello Strumento utilità avanzate per creare forme → Crea solido da Shell. Quest’ultimo però funziona solo se si seleziona un oggetto CAD shell a stagno, personalmente consiglio lo strumento “Converti in solido” visto precedentemente che va bene in tutte le situazioni

CONTROLLO GEOMETRIA: Grazie ad esso possiamo verificare se l’ oggetto CAD selezionato è un solido valido, quindi senza errori che possono compromettere il modello ed operazioni successive. Lo trovi in ambiente Part → menu parte → Controllo Geometria… lo trovi anche come pulsante nelle barre degli strumenti dell’ambiente Part.

Importante: Se hai solo una faccia selezionata il controllo geometria analizza solo la faccia. Consiglio di selezionare l’oggetto da analizzare dal pannello struttura, cosi ti assicuri la selezione dell’intero oggetto.

Ecco un’immagine dove a sinistra puoi vedere il pulsante “controllo geometria” nella barra degli strumenti e dal menu parte, mentre a destra c’è la finestra azioni a strumento attivato.


In FreeCAD 0.19 (come vedi nell’immagine a destra), ci sono diverse opzioni per l’analisi, quindi è richiesto il “Run check” ovvero l’avvio del controllo geometria! Mentre nella 0.18 viene fatto un controllo diretto appena fai click sullo strumento “controllo geometria”.

Su FreeCAD 0.19 consiglio di spuntare il Run BOP check prima di avviare Run check.

Quando usi il controllo geometria, il risultato viene mostrato nella finestra azioni, eventuali errori visualizzati puoi espanderli, poi selezionarli per farli evidenziare nella finestra 3D, utile per capire dov’è l’errore che a volte si nasconde benissimo!

Dopo il controllo geometria, e sempre nella finestra azioni, puoi espandere le informazioni della forma, in FreeCAD 0.19 ci sono molte info aggiuntive rispetto alla versione 0.18, per esempio c’è “Shape type” dove viene indicato se l’oggetto cad è una shell, compund, solido ecc…  (utile con le shell a stagno che esteticamente sono identiche ai solidi).


Ecco un’immagine con il controllo geometria effettuato ed errore selezionato, ho anche esteso le info della forma...


CONSIGLIO: Se il controllo geometria è senza errori, ma nelle info della forma “Shape type” è diverso da “Solid”(solido), converti in solido l’oggetto e rifai il controllo geometria.

Link dove puoi approfondire il controllo geometria: https://wiki.freecadweb.org/Part_CheckGeometry/it

Un automatismo riguardo il controllo geometria lo trovi in Modifica → Preferenze → Part design →Controlla automaticamente il modello dopo un’operazione booleana

CONCLUSIONI

Il nostro modello deve essere sempre affinato e un solido valido, quindi è consigliato usare il controllo geometria durante lo sviluppo del modello.

Prima pulisci il modello con “affina una forma” e successivamente lo converti in solido con “Converti in solido”

Alcune situazioni che possono rompere il modello sono, le facce complanari e il problema di denominazione topologica, per entrambi ti invito a seguire le lezioni della serie tutorial FreeCAD 0.18/0.19.


Per questa lezione abbiamo finito, spero ti sia piaciuta e ti ricordo che le lezioni di “FreeCAD per la Stampa 3D” le trovi su YouTube come video lezioni.

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Con piccole donazioni puoi scaricare file da me ottimizzati.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente

Un saluto, a presto… 
Maurizio Spaccialbelli(Maurino Web)
