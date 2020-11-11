---
title: I display HoloLens 2
description: Le aspettative per display HoloLens 2. Indicazioni per la configurazione dei display per una migliore qualità dell'immagine.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: display, calibrazione, comfort, indicatori visivi, qualità, distanza interpupillare
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 0001ff627b150a9ba79e76f8d995231186c46917
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163012"
---
# Display HoloLens 2

Il display HoloLens 2 è una combinazione di guide d’onda e proiettori di luce. Gli utenti guardano attraverso le guide d’onda, ossia le lenti all'interno della visiera, quando si indossa il visore. I proiettori di luce si trovano all'interno dell’enclosure sopra la fronte. HoloLens 2 usa la luce laser per illuminare lo schermo.

## Risoluzione dei problemi

Per HoloLens 2, eseguire le operazioni seguenti per garantire la massima qualità visiva degli ologrammi presentati sugli schermi:

* **Aumenta la luminosità dello schermo.** Gli ologrammi sono migliori quando lo schermo ha un livello di luminosità più elevato.
* **Avvicina la visiera ai tuoi occhi.** Sposta la visiera verso il basso fino alla posizione più vicina agli occhi.
* **Sposta la visiera verso il basso.** Prova a spostare il cuscinetto della fronte verso il basso, in modo che la visiera si sposti più vicino al naso.
* **Eseguire la calibrazione oculare.** Lo schermo usa la distanza interpupillare e lo sguardo fisso per ottimizzare le immagini sul display. Se non esegui la calibrazione oculare, la qualità dell'immagine potrebbe essere peggiore. Per eseguire la calibrazione oculare, vai a **Impostazioni** > **Sistema,** > **Calibrazione,** > **Eseguire la calibrazione oculare**.

## Domande frequenti

### Quali sono i pattern che a volte lampeggiano negli angoli inferiori del display?

In alcuni casi, HoloLens 2 mostrerà diversi pattern nell'angolo in basso a sinistra e a destra del display. Di seguito sono riportati alcuni esempi (GIF animate). Questo pattern fa parte del normale funzionamento del dispositivo HoloLens 2 per calibrare il display e darti un'esperienza ottimale.

![Pattern bifase](./images/DAT-Biphase-Fiducial.gif) ![GEO pattern](./images/DAT-GEO-Fiducial.gif)

### Perché non riesco a scattare con precisione una foto del display HoloLens 2?

Il display HoloLens 2 è stato progettato per essere visualizzato dall'occhio umano. Il dispositivo è dotato di un sistema di correzione del colore attivo che si adatta all’occhio dell’utente. Diversamente all’occhio umano, le fotocamere vedono gli ambienti in modo diverso e di seguito sono riportati alcuni fattori che potrebbero influire negativamente sulle acquisizioni di una fotocamera rispetto a ciò che vede l’utente.

* **Posizione degli occhi.** Il display HoloLens 2 è stato progettato specificamente per la posizione degli occhi dell'utente. HoloLens 2 impiega la tecnologia di tracciamento oculare per adattarsi alla posizione degli occhi dell'utente. Una fotocamera malposizionata anche di pochi millimetri può comportare una distorsione dell'immagine. In una fotocamera il posizionamento accurato è difficile da ottenere e deve corrispondere all'esatta posizione ed estrazione pupillare per i quali il dispositivo esegue la correzione del colore.
* **Movimenti oculari.** Il display si adatta ai movimenti oculari dell'utente per regolare i colori. Gli elementi visualizzati sullo schermo potrebbero variare a seconda che l'utente stia osservando il centro, il bordo o l'angolo del display. Una singola immagine acquisita può mostrare solo come appare il display sull'asse che corrisponde allo sguardo in quella precisa direzione.
* **Visione binoculare.** Il display HoloLens 2 è stato progettato per essere visualizzato con entrambi gli occhi. Il cervello si adatta alla visualizzazione di due immagini e le fonde tra loro. Le immagini di un solo display ignorano le informazioni provenienti dall'altro display.
* **Tempo di esposizione della fotocamera.** Il tempo di esposizione della fotocamera deve essere un multiplo esatto di 1/120 di un secondo. La frequenza del display HoloLens è 120 Hz. L'esperienza visiva umana non è comparabile all’acquisizione di un singolo fotogramma, grazie al modo in cui HoloLens 2 disegna immagini. Allo stesso tempo, se il dispositivo viene mosso, anche con micromovimenti, il sistema riproietta l'immagine sul display per stabilizzare gli ologrammi. L'acquisizione di più frame, evitando lo spostamento di HoloLens, in genere richiede una configurazione di laboratorio.
* **Dimensioni diaframma fotocamera.** Le dimensioni del diaframma della fotocamera devono essere di almeno 3 mm per acquisire un'immagine precisa. Le fotocamere dei cellulari con diaframmi di piccole dimensioni integrano la luce da un'area ridotta rispetto a quella dell’occhio umano. Il dispositivo applica la correzione del colore per i pattern osservati da diaframmi più grandi. Con diaframmi di piccole dimensioni, i pattern uniformi sono più nitidi e rimangono visibili nonostante la correzione del colore applicata dal sistema.
* **Pupilla d’entrata della fotocamera.** La pupilla d’entrata della fotocamera deve avere almeno 3 millimetri di diametro per acquisire un'immagine precisa. In caso contrario, la fotocamera acquisisce pattern ad alta frequenza non visibili all'occhio. La posizione della pupilla d’entrata deve essere nella parte anteriore della fotocamera e posizionata in corrispondenza dell’estrazione pupillare, per evitare l'introduzione di anomalie e altre varianti dell'immagine acquisita.
* **Posizione della fotocamera.** Le fotocamere che soddisfano i requisiti per visualizzare il display HoloLens 2 sono più grandi ed è difficile posizionare la fotocamera abbastanza vicino al display di HoloLens 2 per osservare l'immagine su cui è stata eseguita la correzione del colore. Se la fotocamera è malposizionata, la correzione del colore potrebbe influire negativamente sull'acquisizione del display HoloLens 2.
* **Correzione immagine.** Le tipiche fotocamere digitali e fotocamere di smartphone applicano una curva di riproduzione tonale (TRC) che aumenta contrasto e colore per fornire un risultato più preciso. Se applicato a un display HoloLens 2, questa curva tonale amplifica le irregolarità.

Detto ciò, è comunque possibile per le fotocamere industriali acquisire immagini indicative dal display HoloLens 2. Purtroppo, né le fotocamere di smartphone, né quelle a basso costo o professionali acquisiscono immagini che corrispondono a ciò che l’utente vede con HoloLens 2.

### Che effetto ha la calibrazione oculare sulla qualità dell'immagine del display?

Il display HoloLens 2 esegue attivamente la correzione del colore sulle immagini in base alla posizione degli occhi dell'utente. [La calibrazione oculare](hololens-calibration.md) fornisce due importanti input: (1) la distanza interpupillare dell’utente, e (2) la direzione in cui guardano gli occhi. Senza calibrazione oculare, il sistema usa automaticamente una posizione simbolica senza tenere conto dei movimenti oculari. La differenza tra la correzione del colore attiva e nessuna correzione dipende dalla fisiologia dell'utente stesso. Ad esempio, gli utenti che hanno la stessa distanza interpupillare del sistema predefinito vedranno meno miglioramenti legati alla correzione del colore. Mentre gli utenti che hanno una distanza interpupillare più ristretta o più ampia rispetto a quella predefinita del sistema vedranno più modifiche all'immagine sul display.

Nota, una nuova funzionalità in [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) inizierà a [rilevare automaticamente la posizione degli occhi](hololens-calibration.md#auto-eye-position-support). 

### Che differenze hanno i display di HoloLens di prima generazione e HoloLens 2?

Le principali richieste degli utenti ricevute da Microsoft dopo aver utilizzato HoloLens 1 sono state (1) aumentare il campo visivo e (2) aumentare la luminosità. Gli sviluppi tecnologici hanno consentito a Microsoft di produrre guide d’onda che raddoppiano l'area del campo visivo e producono proiettori di luce con un display tre volte più luminoso. L'hardware imposta la linea di base per un trio di compromessi per la qualità dell'immagine sul display: (1) campo visivo, (2) luminosità e (3) uniformità dei colori. Il progresso tecnologico continuo consente miglioramenti in tutte le aree senza sacrificarne nessuna. Nel frattempo, la tecnologia esistente imposta i limiti per questi compromessi.

### Quali miglioramenti saranno apportati alla qualità dell'immagine di HoloLens 2?

Mentre sono in corso numerose indagini per migliorare la qualità dell'immagine, sono previsti aggiornamenti futuri nelle aree seguenti:

* **Posizione degli occhi automatica.** Questa funzionalità consente di eseguire le procedure di calibrazione oculare in background. Gli utenti non dovranno più eseguire la calibrazione oculare per il funzionamento della correzione del colore attiva. Funzionerà a prescindere.
* **Miglioramenti nella calibrazione del colore.** Questo aggiornamento è incentrato sui valori cromatici dei colori più scuri, ad esempio il grigio scuro. Al momento, i colori più tenui hanno un tono rosso. Questo problema si verifica anche quando viene diminuita la luminosità di tutto il display: il display mostra un colore rosso. Questo problema è il risultato di un'attività eccessiva nel canale di colore rosso per questi colori più scuri. Abbiamo definito le curve a illuminazione laser per uesti colori più tenui e stiamo lavorando per offrire una procedura di calibrazione utente. Il risultato sarà una maggiore precisione del colore nello spettro della luminosità. Non cambierà l'aspetto degli sfondi bianchi a luminosità massima. Continuiamo a consigliare l'uso dei modelli di progettazione in modalità scura nelle app.
* **Modalità di lettura.** Gli sviluppatori di app possono fare un compromesso sul campo di visivo del display in modo da ottenere una risoluzione angolare superiore. Gli sviluppatori di app possono ignorare la matrice di proiezione in modo che venga eseguito il rendering del contenuto alla risoluzione grafica del display. Questa funzionalità comporta una riduzione del 30% nel campo visivo e un corrispondente aumento della risoluzione angolare. Si sta lavorando per presentare questa funzionalità al Toolkit per realtà mista. Se disponibile, la modalità di lettura è compatibile con qualsiasi sistema operativo HoloLens 2, il quale non dipende da un aggiornamento del sistema operativo.

Gli aggiornamenti del sistema operativo vengono recapitati automaticamente. È anche possibile testare in anteprima i miglioramenti alle versioni del software tramite il programma Insider Preview.

### Quali indicazioni sono disponibili per gli sviluppatori che vogliono applicare principi di progettazione in modalità scura?

Gli utenti avranno l'esperienza migliore quando si evitano sfondi bianchi. La modalità scura è un principio di progettazione usato dalle app per usare sfondi neri o scuri. Le impostazioni di sistema predefinite per la modalità scura possono essere modificate passando a **Impostazioni** > **Sistema** > **Colore**.

Agli sviluppatori si consiglia di seguire le indicazioni per la progettazione in modalità scura:

* [Linee guida per sviluppatori per la progettazione di display HoloLens](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Dimensioni del carattere consigliate](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Se un ologramma richiede uno sfondo bianco, mantenere le dimensioni dell'ologramma inferiori al campo di visualizzazione completo del display. Questa dimensione consente agli utenti di posizionare l'ologramma al centro dello schermo.

### Come si pulisce il display di HoloLens 2?

Usare un panno in microfibra per pulire delicatamente la visiera. Per igienizzare la visiera, inumidisci un panno con dell’alcool isopropilico al 70% e quindi pulisci la visiera. Leggi la guida completa sulle [domande frequenti sulla pulizia di HoloLens 2](hololens2-maintenance.md).
