---
title: HoloLens 2 Risoluzione dei problemi relativi alla visualizzazione
description: Aspettative per i HoloLens 2 visualizzati. Indicazioni per la configurazione dei display per la migliore qualità delle immagini.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: visualizzazione, calibrazione, comfort, oggetti visivi, qualità, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 3567c1f33f10240a9cacbf258669a0e3274f4c6bb3c90fc1317a57a3a415fc7f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659914"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2 Risoluzione dei problemi relativi alla visualizzazione

## <a name="overview"></a>Panoramica
Il HoloLens 2 display è una combinazione di waveguide e proiettori leggeri. Gli utenti osservano le waveguide, ovvero le lenti all'interno della visiera, quando indossano il visore. I proiettori leggeri sono all'interno dell'enclosure sopra la fronte. HoloLens 2 usa la luce laser per illuminare il display.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Seguire questa procedura per garantire la massima qualità visiva degli ologrammi presentati nei display:

* **Aumentare la luminosità dello schermo.** Ologrammi migliore quando lo schermo è al livello più chiaro. Quando si indossa il HoloLens, i pulsanti di luminosità si trova sul lato sinistro della visiera vicino al tempio.
* **Avvicinare la visiera agli occhi.** Ruotare la visiera verso il basso fino alla posizione più vicina agli occhi.
* **Maiusc visore verso il basso.** Provare a spostare il rilievo della fronte verso il basso, che comporterà il movimento della visiera verso il basso verso il basso verso il naso.
* **[Eseguire la calibrazione oculare.](hololens-calibration.md#calibrating-your-hololens-2)** Lo schermo usa la distanza interpupillaria (IPD) e lo sguardo oculare per ottimizzare le immagini sullo schermo. Se non si esegue la calibrazione oculare, la qualità dell'immagine potrebbe peggiorare. Per eseguire la calibrazione oculare, passare **Impostazioni**  >  **calibrazione**  >    >  **oculare di System** Calibration Run .
* **Eseguire la calibrazione dei colori dello schermo.** Nella [Windows Holographic, versione 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e versioni  successiva, è possibile selezionare un profilo colori alternativo per il HoloLens 2 schermo. In questo modo i colori possono risultare più accurati, in particolare ai livelli di luminosità dello schermo inferiori. La calibrazione dei colori  dello schermo è disponibile nell'app Impostazioni, nella **pagina Calibrazione** > sistema.

    > [!NOTE]
    > Poiché questa impostazione salva un nuovo profilo colori nel firmware dello schermo, si tratta di un'impostazione per dispositivo e non univoca per ogni account utente.

### <a name="how-to-use-display-color-calibration"></a>Come usare la calibrazione dei colori dello schermo
1. Avviare **l Impostazioni app** e passare a **Calibrazione > sistema**.
1. In **Calibrazione colori visualizzazione** selezionare il pulsante Esegui **calibrazione** colori visualizzazione.
1. Verrà avviata l'esperienza di calibrazione del colore dello schermo e si consiglia di assicurarsi che la visiera sia nella posizione corretta.
1. Dopo aver proceduto con le finestre di dialogo delle istruzioni, la luminosità dello schermo verrà automaticamente ridotta al 30%.
    > [!TIP]
    > Se si verificano problemi con la visualizzazione della scena in grigio nell'ambiente, è possibile regolare manualmente il livello di luminosità di HoloLens 2 usando i pulsanti di luminosità sul lato sinistro del dispositivo.
1. Selezionare i pulsanti da 1 a 6 per provare immediatamente ogni profilo di colore e trovarne uno che sia più adatto agli occhi (questo in genere significa che il profilo che consente alla scena di apparire più neutro, con il modello in scala di grigi e i toni della pelle che sembrano come previsto).

    ![Visualizzare la scena di calibrazione dei colori](images/color-cal-ui.png)
    
6. Quando si è soddisfatti del profilo selezionato, selezionare il pulsante Salva & **Esci**
1. Se si preferisce non apportare modifiche, selezionare il pulsante **Annulla & Esci** e le modifiche verranno ripristinate

> [!TIP]
> Ecco alcuni suggerimenti utili da tenere presenti durante l'uso dell'impostazione di calibrazione del colore di visualizzazione:
> - È possibile eseguire di nuovo la calibrazione dei colori Impostazioni ogni volta che si desidera
> - Se qualcuno nel dispositivo ha usato in precedenza l'impostazione per modificare i profili colori, la data/ora della modifica più recente verrà riflessa nella pagina Impostazioni colori
> - Quando si esegue di nuovo la calibrazione dei colori dello schermo, il profilo colori salvato in precedenza verrà evidenziato e il profilo 0 non verrà visualizzato (poiché il profilo 0 rappresenta il profilo colori originale dello schermo)
> - Se si vuole ripristinare il profilo colori originale dello schermo, è possibile farlo dalla pagina Impostazioni (vedere come reimpostare il profilo [colori](#how-to-reset-color-profile))

### <a name="how-to-reset-color-profile"></a>Come reimpostare il profilo colori

Se non si è soddisfatti del profilo colori personalizzato salvato nel HoloLens 2, è possibile ripristinare il profilo colori originale del dispositivo:
1. Avviare **l Impostazioni app** e passare a **Calibrazione > sistema**.
1. In **Calibrazione colori visualizzazione** selezionare il pulsante Ripristina profilo **colori** predefinito.
1. Quando si apre la finestra di dialogo, selezionare **Riavvia** se si è pronti per riavviare il HoloLens 2 e applicare le modifiche.

### <a name="top-display-color-calibration-known-issues"></a>Problemi noti relativi alla calibrazione dei colori dello schermo superiore

- Nella pagina Impostazioni, la stringa di stato che indica quando è stata modificata l'ultima modifica del profilo colori non sarà aggiornata fino a quando non si ricarica la pagina di Impostazioni 
    - **Soluzione** alternativa: selezionare un'Impostazioni pagina e quindi selezionare nuovamente la pagina Calibrazione.
- Se il HoloLens 2 durante l'esecuzione della calibrazione del colore dello schermo, riprenderà in un secondo momento nel ambiente iniziale e il livello di luminosità dello schermo sarà ancora in grigio.
- Potrebbe essere necessario provare a premere i pulsanti di luminosità sul lato sinistro del dispositivo verso l'alto o verso il basso alcune volte prima che funzionino come previsto.
- La localizzazione non è completa per tutti i mercati

## <a name="faq"></a>Domande frequenti

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Quali sono i modelli che occasionalmente lampeggiano negli angoli inferiori dello schermo?

In alcuni casi, il HoloLens 2 mostra modelli diversi negli angoli inferiore sinistro e destro dello schermo. Di seguito sono riportati alcuni esempi (GIF animate). Questo modello fa parte del normale funzionamento del dispositivo HoloLens 2 per calibrare lo schermo per un'esperienza ottimale.

![Modello bifase](./images/DAT-Biphase-Fiducial.gif) ![Modello GEO](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Perché non è possibile scattare una fotografia accurata del mio HoloLens 2 display?

Il HoloLens 2 è progettato per essere visualizzato dall'occhio umano. Il dispositivo ha un sistema di correzione del colore attivo che si adatta agli occhi di un utente. Rispetto all'occhio umano, le fotocamere vedono gli ambienti in modo diverso e di seguito sono alcuni fattori che possono influire su qualsiasi incoerenza tra ciò che una fotocamera acquisisce e ciò che un utente vede.

* **Posizione dell'occhio.** Il HoloLens 2 è progettato specificamente per la posizione dell'occhio dell'utente. Il HoloLens 2 usa la tecnologia di tracciamento oculare per adattarsi alla posizione dell'occhio dell'utente. Una fotocamera non riposizionata di pochi millimetri può causare la distorsione dell'immagine. Il posizionamento accurato con una fotocamera è difficile e deve corrispondere alla posizione esatta e al rilievo oculare per cui il dispositivo sta eseguendo la correzione del colore.
* **Movimento oculare.** Lo schermo si adatta al movimento dell'occhio dell'utente per regolare i colori. Ciò che viene visualizzato sullo schermo può variare a seconda che l'utente controlli il centro, il bordo o l'angolo dello schermo. Una singola acquisizione di immagini può nel migliore dei modi mostrare solo l'aspetto dello schermo per l'asse che corrisponde alla direzione dello sguardo fisso.
* **Visualizzazione binocolare.** Il HoloLens 2 è progettato per essere visualizzato con entrambi gli occhi. Il cervello si adatta alla visualizzazione di due immagini e le unisce. Le immagini di una sola visualizzazione ignorano le informazioni dell'altra visualizzazione.
* **Tempo di esposizione della fotocamera.** Il tempo di esposizione della fotocamera deve essere un multiplo esatto di 1/120 di secondo. La HoloLens frame di visualizzazione è di 120 Hz. A causa del modo in cui HoloLens 2 le immagini, anche l'acquisizione di un singolo frame non è sufficiente per abbinare l'esperienza visiva di un essere umano. Allo stesso tempo, se il dispositivo si sposta affatto, anche i micromovimenti, il sistema riprogetta l'immagine sullo schermo per stabilizzare gli ologrammi. L'acquisizione di più fotogrammi, HoloLens lo spostamento, richiede in genere una configurazione di laboratorio.
* **Dimensioni dell'apertura della fotocamera.** Le dimensioni di apertura della fotocamera devono essere di almeno 3 mm per acquisire un'immagine accurata. Le fotocamere dei telefoni cellulari con piccole aperture integrano la luce di un'area più piccola rispetto all'occhio umano. Il dispositivo applica la correzione del colore per i modelli osservati da aperture più grandi. Con piccole aperture, i modelli di uniformità sono più affilati e rimangono visibili nonostante le correzioni di colore applicate dal sistema.
* **Studente di ingresso della fotocamera.** L'icona di ingresso della fotocamera deve avere un diametro di almeno 3 mm per acquisire un'immagine accurata. In caso contrario, la fotocamera acquisisce alcuni modelli ad alta frequenza non visibili all'occhio. La posizione dell'alunno di ingresso deve essere posizionata davanti alla fotocamera e posizionata alla distanza di rilievo dell'occhio per evitare di introdurre aberrazioni e altre variazioni all'immagine acquisita.
* **Posizione della fotocamera.** Le fotocamere che soddisfano i requisiti per visualizzare il display HoloLens 2 sono più grandi ed è difficile posizionare la fotocamera abbastanza vicino al display HoloLens 2 per osservare l'immagine corretta dal colore. Se la fotocamera si trova nella posizione errata, la correzione del colore può influire negativamente sull'acquisizione HoloLens 2 schermo.
* **Correzione dell'immagine.** Le fotocamere digitali tipiche e le fotocamere per smartphone applicano una curva di riproduzione del tono (TRC) che aumenta il contrasto e il colore per offrire un risultato più veloce. Se applicata a un HoloLens 2, questa curva del tono amplifica le non uniformità.

Detto questo, è comunque possibile che le fotocamere industriali specializzate acquisiscono immagini rappresentative HoloLens 2 display. Sfortunatamente, le fotocamere di smartphone, consumer e professionali non acquisiscono immagini che corrispondono a quanto visualizzato da un utente HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Cosa fa la calibrazione oculare per visualizzare la qualità dell'immagine?

La HoloLens 2 colore corregge attivamente le immagini in base alla posizione degli occhi dell'utente. [La calibrazione](hololens-calibration.md) oculare fornisce due input importanti: (1) la distanza interpupillare (IPD) dell'utente e (2) la direzione di ogni occhio. Senza calibrazione oculare, il sistema ha come impostazione predefinita una posizione oculare nominale senza movimento oculare. La differenza tra correzione del colore attiva e nessuna correzione dipende dalla fisiologia dell'utente stesso. Ad esempio, gli utenti che hanno lo stesso IPD dell'impostazione predefinita del sistema visualizzano meno miglioramenti della correzione del colore. Mentre gli utenti con un IPD molto più stretto o più ampio rispetto all'impostazione predefinita del sistema visualizzano più modifiche all'immagine di visualizzazione.

Si noti che una nuova funzionalità di [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) inizierà a rilevare automaticamente [la posizione dell'occhio.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Quali sono le differenze di visualizzazione tra HoloLens (prima generazione) e HoloLens 2?

Tra le richieste principali che i clienti hanno fornito a Microsoft dopo aver riscontrato HoloLens 1 è stato (1) aumentare il campo di visualizzazione e (2) aumentare la luminosità. Gli sviluppi tecnologici hanno consentito a Microsoft di produrre guidi d'onda che raddoppiano l'area del campo di visualizzazione e producono proiettori leggeri con un display fino a tre volte più chiaro. L'hardware imposta la linea di base per un gruppo di compromessi per la qualità dell'immagine di visualizzazione: (1) campo di visualizzazione, (2) luminosità e (3) uniformità dei colori. L'avanzamento continuo della tecnologia consente miglioramenti in tutte le aree senza sacrificare un'altra area. Nel frattempo, la tecnologia esistente imposta i limiti disponibili per questi compromessi.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Quali sono i miglioramenti in arrivo che miglioreranno HoloLens 2 qualità dell'immagine?

Anche se sono in corso numerose indagini per migliorare la qualità delle immagini, è previsto che le aree seguenti arrivino nei prossimi aggiornamenti:

* **Posizione automatica dell'occhio.** Questa funzionalità consentirà di eseguire le procedure di calibrazione oculare in background. Gli utenti non dovranno più eseguire la calibrazione oculare per il funzionamento della correzione del colore attiva. Funzionerà semplicemente.
* **Miglioramenti della calibrazione dei colori.** Questo aggiornamento si concentra sui valori di colore dei colori più scuri (ad esempio, grigio scuro). Al momento, i colori dimmer prelevano un tono rosso. Questo problema si verifica anche quando l'intero schermo è in grigio. L'intero schermo seleziona i colori rosso. Questo problema è il risultato di un'attività troppo grande nel canale dei colori rosso per questi colori più scuri. Sono state caratterizzate le curve di illuminazione del laser in questi colori dimmer e si sta lavorando per offrire una procedura di calibrazione dell'utente. Il risultato sarà una maggiore accuratezza del colore nello spettro della luminosità. Non cambierà l'aspetto degli sfondi bianchi con la massima luminosità. Si continua a consigliare l'uso di modelli di progettazione in modalità scura nelle app.
* **Modalità di lettura.** Gli sviluppatori di app possono scambiare il campo di visualizzazione dello schermo per ottenere una risoluzione angolare più elevata. Gli sviluppatori di app possono eseguire l'override della matrice di proiezione in modo che il rendering del contenuto sia eseguito alla risoluzione del disegno dello schermo. Questa funzionalità comporta una riduzione del 30% del campo di visualizzazione e un corrispondente aumento della risoluzione angolare. È in corso il lavoro per introdurre questa funzionalità alla realtà [mista Toolkit](https://github.com/Microsoft/MixedRealityToolkit-Unity). Se disponibile, la modalità di lettura funzionerà in HoloLens 2 sistema operativo e non dipende da un aggiornamento del sistema operativo.

Gli aggiornamenti del sistema operativo vengono recapitati automaticamente. È anche possibile testare le versioni iniziali del miglioramento del software tramite il programma insider preview.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Quali linee guida sono disponibili per gli sviluppatori per applicare i principi di progettazione in modalità scura?

Gli utenti avranno la migliore esperienza quando evitano gli sfondi vuoti. La modalità scura è un principio di progettazione usato dalle app per usare sfondi di colore nero o scuro. Per impostazione predefinita, le impostazioni di sistema sono in modalità scura e possono essere regolate Impostazioni  >  **Colore di**  >  **sistema**.

Si consiglia agli sviluppatori di seguire le linee guida per la progettazione in modalità scura:

* [Linee guida per la progettazione degli sviluppatori HoloLens display](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Dimensioni dei caratteri consigliate](/windows/mixed-reality/typography#recommended-font-size)

Quando un ologramma richiede uno sfondo bianco, mantenere le dimensioni dell'ologramma più piccole rispetto al campo di visualizzazione completo dello schermo. Queste dimensioni consentono agli utenti di posizionare l'ologramma al centro dello schermo.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Come si pulisce un HoloLens 2 schermo?

Usare un panno di microfibra per cancellare la visiera in modo graduale. Per disinfettare la visiera, usare il 70% di alcol isopropile per inumidire leggermente un panno e quindi cancellare la visiera. Leggere le linee guida complete nelle domande [frequenti HoloLens 2 pulizia dei dati.](hololens2-maintenance.md)
