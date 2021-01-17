
FREECAD PER LA STAMPA 3D
Lezione 04: Metodo 1: Esportazione da CAD a Mesh

Benvenuti a tutti, questa lezione la trovi su [YouTube](https://www.youtube.com/playlist?list=PLQNfSBT6MZGS1SGfFDtfCbMwSAmQj7fuA) e in PDF su [Gumroad](https://gum.co/freecad-per-la-stampa-3d-03) .

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Con piccole donazioni puoi scaricare file da me ottimizzati.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente

Indice e argomenti della lezione:
    • Metodo 1: Esportazione da CAD a Mesh.
    • Cosa influisce sulla maglia poligonale da esportare con i due possibili CASI.
    • CASO 1 e linee nascoste per avere un’anteprima della Mesh prima dell’esportazione.
    • Note per Part design.
    • Valori minimi di tassellazione.
    • PRO e CONTRO del Metodo 1.

Oggi vediamo come esportare in mesh i nostri modelli CAD, abbiamo Due Metodi per farlo e per ogni Metodo c’è una lezione dedicata dove descrivo PRO e CONTRO.

Ricorda che prima di creare la mesh e con qualsiasi Metodo, è consigliato affinare e convertire in solido l’oggetto CAD, da controllare anche che sia un solido valido come visto nella lezione 03.

Ricordo che nella lezione 02 abbiamo visto la tassellazione sugli oggetti CAD e le linee nascoste, in questa lezione uso il termine “BREP” che nei modellatori CAD spesso indica la maglia poligonale generata per visualizzare l’oggeto/i CAD.


METODO 1: ESPORTAZIONE da CAD a Mesh

Crea una primitiva “cilindro” da ambiente Part e imposta il diametro a 10mm.
Ora seleziona il cilindro e in scheda dati → deviation metti 0,5 e ricalcoli il modello per assicurarti di aggiornare la tassellazione appena cambiata, ora vai nel menu File → Esporta.

In File di tipo: Scegli STL Mesh(*.stl *.ast).


In nome del file: Scrivi cilindro-mesh.stl (anche senza estensione FreeCAD dovrebbe aggiungerla in automatico in base al Tipo di file Scelto, in caso contrario aggiungi anche l’estensione .stl).

Ora cliccando su “Salva” il modello CAD viene “Esportato in mesh” nella posizione e con il nome scelto, a breve vediamo come impostare e controllare la tassellazione della maglia poligonale esportata.

Per vedere la mesh esportata bisogna importarla, quindi da File → Importa scegli cilindro-mesh.stl, questo viene importato ed aggiunto nel pannello struttura con il nome di “cilindro-mesh”, normalmente le mesh importate vengono visualizzate in shaded, come sempre con CTRL + D puoi scegliere flat lines o wireframe per vedere la maglia poligonale della mesh.

Nell’immagine seguente ho duplicato cilindro-mesh, quindi vedi tre oggetti…  il cilindro CAD, e due cilindri-mesh, uno visualizzato in shaded e uno in Flat lines.

Vediamo che la circonferenza della mesh è poco definita/tassellata, pochi spigoli definiscono la circonferenza cosi da far notare i vertici su di essa, quindi bisogna cambiare la tassellazione per far aumentare gli spigoli sulla circonferenza ed ottenere una Mesh migliore, per far ciò dobbiamo abbassare i parametri di tassellazione ed esportare nuovamente l’oggetto CAD, ma aspetta e continua a leggere… 
COSA INFLUISCE SULLA MAGLIA POLIGONALE DA ESPORTARE

Ci sono due parametri di tassellazione che influiscono sulla maglia poligonale generata  dall’esportazione da CAD a Mesh utilizzando il Medodo 1, FreeCAD sceglie solo uno di essi per creare la Mesh! Vediamoli… 

    1. Tassellazione oggetti CAD / Tassellazione in scheda vista: È la tassellazione già vista nelle lezioni precedenti usata per visualizzare gli oggetti CAD nella finestra 3D, presente in Modifica → Preferenze → Part design → Visualizzazione della figura, ed anche nel pannello proprietà →  scheda vista con oggetto CAD selezionato. In questa lezione cambiamo sempre in Tassellazione in scheda vista.

    2. Massima deviazione della maglia: È la tassellazione  presente in Modifica → Preferenze → Importa/Esporta → Formati mesh… Per visualizzare la sezione “Formati mesh”, devi avviare almeno una volta l’ambiente “Mesh design” o avere una mesh nel pannello struttura.

Importante: Come accennato…  Tra i due parametri di tassellazione appena descritti, solo uno verrà scelto da FreeCAD per generare la maglia poligonale durante l’esportazione, quindi abbiamo due CASI che dobbiamo comprendere e saper controllare.

CASO 1 : Se “Tassellazione in scheda vista” genera una mesh più accurata di “massima deviazione della maglia”, allora la maglia poligonale viene generata utilizzando i valori di “Tassellazione in scheda vista” ovvero deviazione e deflessione presenti in scheda vista.

CASO 2 : Se “Tassellazione in scheda vista” genera una mesh meno accurata di “massima deviazione della maglia”, allora la maglia poligonale viene generata utilizzando il valore di “massima deviazione della maglia”.

Quindi “Massima deviazione della maglia” stabilisce l’errore massimo che può avere la Mesh generata dall’ esportazione. Per errore massimo intendo la precisione della mesh rispetto al modello CAD, infatti con il Metodo 1 è impossibile esportare una maglia poligonale peggiore di quella che produrrebbe “massima deviazione della maglia”.
CASO 1 e  LINEE NASCOSTE


Il “Metodo 1: Esportazione da CAD a Mesh” può essere utilizzato lasciando tutto al caso, ma a breve vediamo che per aumentare il controllo delle esportazioni, si può forzare il CASO 1 (consigliato) o il CASO 2.

Non si può prevedere esattamente quale CASO verrà utilizzato, ma si può forzare più o meno esageratamente uno o l’altro.

Per esempio abbassando il valore di “massima deviazione della maglia” si forza il CASO 2, di conseguenza una nuova esportazione dell’oggetto produrrà una mesh più accurata. Ovviamente più abbassi “massima deviazione della maglia” e più ti assicuri di rientrare nel CASO 2, ma a mio avviso è un po' scomodo… Per cambiare la maglia poligonale della mesh da esportare bisogna andare ogni volta nelle preferenze.

Forzando il CASO 1 non serve aprire le preferenze ogni volta, ma il grande vantaggio è che si può avere un’anteprima della maglia poligonale prima dell’esportazione!

Per forzare il CASO 1 puoi lasciare il valore di “Massima deviazione della maglia” a 0,10mm(predefinito) o aumentarlo a 1 o 2mm per forzare il CASO 1 nella maggior parte delle esportazioni da CAD a Mesh con il Metodo 1(file → esporta).

Il valore di “deviazione” nella “tassellazione in scheda vista” è espresso in percentuale e calcolato in base alla grandezza del modello (riquadro del modello), quindi una tassellazione in scheda vista con deviation di 0,5 (%) su oggetti della stessa forma ma con diversa grandezza, produrrà tassellazioni diverse per ognuno di essi, questo cambia anche le condizioni per rientrare nel CASO 1, ecco perché aumentando in modo esagerato il valore di “massima deviazione della maglia” si aumenta la possibilità di rientrare nel CASO 1.

PROMEMORIA: Come abbiamo visto nelle lezioni precedenti, nelle preferenze digitando “ok” o “applica”, i valori inseriti sui singoli oggetti in “tassellazione in scheda vista” vengono soprascritti dai suoi valori equivalenti presenti nelle preferenze “Tassellazione oggetti CAD”(preferenze → part design → visualizzazione della figura).

Sappiamo che la Tassellazione oggetti CAD e l’equivalente tassellazione in scheda vista è utilizzata per ottimizzare la visualizzazione degli oggetti CAD nella finetra 3D (lezione 02), quindi rientrando nel CASO 1 la maglia poligonale della Mesh esportata sarà identica alla Mesh generata per visualizzare l’oggetto CAD!

Ora se ricordi lo “stile di disegno --> linee nascoste” (Lezione 02), si intuisce che forzando il CASO 1 puoi vedere un’anteprima della Mesh prima di esportarla! In pratica, con questo metodo esporti solo dopo aver raggiunto la maglia poligonale desiderata.

Nell’esportazione precedente i valori di “Tassellazione in scheda vista” erano con deviation a 0,5 (%) e angular deflection a 28,5°, mentre il valore di “massima deviazione della maglia” a 0.1mm (predefinito).  Nell’esportazione siamo rientrati nel CASO 1, infatti attivando le linee nascoste possiamo notare che la mesh cilindro.stl è identica alla mesh dell’oggetto CAD visualizzata grazie alle linee nascoste.


Puoi sopraporre gli oggetti per verificare che hanno la stessa tassellazione.
Da notare che lo “stile di disegno → linee nascoste” viene applicato su tutti gli oggetti, mesh comprese, ma l’effetto sulle mesh è come la visualizzazione “wireframe”.

Ora sempre con le linee nascoste attive, seleziona il cilindro CAD usato precedentemente nell’esportazione e abbassa la deviazione a 0,05 (%) infine ricalcola il modello!
A sinistra abbiamo il valore precedente (deviation 0,5), mentre a destra deviation a 0,05.

Ora selezioni ed esporti nuovamente il cilindro esattamente come prima(file → esporta), ma in “nome de file:” scrivi “cilindro-mesh-2.stl” ed esporti! Poi lo importi da file → importa.
Puoi notare che la maglia poligonale del cilindro-mesh-2.stl importato è migliorata rispetto all’esportazione precedente, ed è identica alla maglia poligonale dell’oggetto CAD con il valore di deviazione a 0,05. Quindi si è rientrati nel CASO 1, che abbinato all’uso delle linee nascoste diventa un modo interessante per esportare con il Metodo 1: esportazione da CAD a Mesh.

Se la mesh esportata, è diversa dalla mesh dell’oggetto CAD visualizzata grazie alle linee nascoste, significa che si è rientrati nel CASO 2, quindi o abbassi i valori di “Tassellazione nella scheda vista” o aumenti il valore di “Massima deviazione della maglia”… se qualcosa ti sfugge, riguarda i due CASI che ho scritto precedentemente.


Un’altra caratteristica “naturale” ma da prendere in considerazione… Con l’esportazione di una multi-selezione di oggetti CAD, tutti gli oggetti selezionati vengono esportati in un singolo oggetto Mesh, questo vale anche sulle funzioni in un corpo/body, quindi attenzione! Le multi-selezioni/esportazioni sono trattate nelle prossime lezioni.

NOTE PER L’AMBIENTE PART DESIGN

Per esportare i corpi di part design la selezione da fare è il corpo o l’entità finale(normalmente l’ultima funzione), non fa differenza, volendo puoi selezionare una qualsiasi funzione che desideri esportare, l’importante è fare solo una selezione, la multi-selezione è trattata in un’altra lezione.

Per cambiare la “tassellazione in scheda dati” devi selezionare il corpo e ricalcolare, se dopo il ricalcolo c’è ancora qualche funzione con il pallino blu ti consiglio di selezionare il corpo e tutte le sue funzioni, quindi sulla tastiera tieni premuto il tasto “shift” mentre selezioni il corpo e l’ultima funzione, ora rilasci il tasto “shift” e ricalcoli tutta la selezione effettuata, un ricalcolo con le selezioni appena descritta funzionerà in tutte le situazioni.

VALORI MINIMI DI TASSELLAZIONE

Nessun consiglio sui valori di deviazione e deflessione perchè può dipendere da diversi fattori come grandezza, forma, relazione tra deviazione lineare e deflessione angolare, e dallo scopo d’utilizzo del modello stesso, ma ora conosci il primo metodo per ottenere la maglia poligonale che desideri.

Ecco i Valori MINIMI possibili delle tassellazioni usate con il Metodo 1: esportazione da CAD a Mesh

Tassellazione oggetti CAD/Tassellazione scheda vista:
    • Deviazione lineare: Puoi scendere fino a 0,05% raggiungendo la massima accuratezza
    • Deflessione angolare: Arriva fino a 1° raggiungendo la massima accuratezza, spesso più fine della deviazione lineare.

Massima deviazione della maglia:
    • Massima deviazione della maglia: Con questo parametro puoi scendere moltissimo ed è espresso in mm. Volendo puoi abbassarlo fino ad ottenere maglie super fine (rientrando nel CASO 2), ma nella stampa 3D spesso è inutile esagerare e i valori minimi della “Tassellazione nella scheda vista” nella maggior parte dei casi sono più comodi e sufficienti.

Ecco un link per approfondire la deviazione lineare e deflessione angolare:
https://wiki.freecadweb.org/Mesh_FromPartShape/it


PRO E CONTRO DEL METODO 1

Ora vediamo i PRO e i CONTRO del Metodo 1: Esportazione da CAD a Mesh

PRO:  
    • Forzando il CASO 1 puoi avere un’anteprima della Mesh prima di esportarla.
    • Forzando il CASO 2 si possono ottenere mesh finissime, ma nella stampa 3D spesso inutile.
    • Puoi esportare una multi-selezione di oggetti CAD in Mesh mantenendo la Tassellazione di ogni singolo oggetto(anche diversa tra loro) ma attenzione…  tutti gli oggetti selezionati vengono esportati in un solo file, ed ogni selezione avrà la sua maglia poligonale. Questa tecnica può essere sfruttata a nostro vantaggio, o viceversa, avere maglie poligonali con elementi inutili, ci sarà una lezione dedicata per le multi-selezioni.


CONTRO: 
    • Bisogna importare la mesh per analizzarla ed eventualmente ripararla.
    • Abbassando i valori in “Tassellazione in scheda vista” degli oggetti CAD si aumentano i calcoli di visualizzazione dell’oggetto e di apertura del documento… Per evitarlo(se lo ritieni necessario), dopo l’esportazione bisogna ripristinare i parametri di tassellazione in scheda vista, una soluzione veloce è aprire le preferenze e cliccare su “ok” o “applica”, questo riscrive i parametri di “tassellazione oggetti CAD” sui parametri equivalenti presenti in scheda vista.
    • Avendo trattato l’esportazione da CAD a Mesh, sconsiglio di esportare in .amf .
      FreeCAD ad oggi non può importare il .amf, utilile per analizzare e riparare la mesh che vediamo nelle prossime lezioni.

Per questa lezione abbiamo finito, spero ti sia piaciuta e ti ricordo che le lezioni di “FreeCAD per la Stampa 3D” le trovi su YouTube come video lezioni.

Tutti i miei progetti e tutorial sono rilasciati sotto licenza libera, il tuo aiuto è fondamentale! Supporta i miei lavori sul canale che preferisci… Grazie Mille!
* [Gumroad](https://gumroad.com/mauriziospacciabelli/follow): Con piccole donazioni puoi scaricare file da me ottimizzati.
* [Patreon](https://www.patreon.com/mauriziospaccialbelli): Per supportarmi ed avere sconti da usare in Gumroad(anche del 100%).
* [Liberapay](https://liberapay.com/MaurizioSpaccialbelli): Ami l’open source? Ecco un canale open source per effettuare donazioni.
* [Paypal](https://www.paypal.me/mauriziospacciabelli): Non ha bisogno di presentazioni, se lo preferisci usalo tranquillamente

Un saluto, a presto… 
Maurizio Spaccialbelli(Maurino Web)
