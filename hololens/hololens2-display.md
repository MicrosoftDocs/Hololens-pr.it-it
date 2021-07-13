---
title: HoloLens 2 Risoluzione dei problemi di visualizzazione
description: Vengono visualizzate le HoloLens 2 aspettative. Linee guida per la configurazione di schermi per la migliore qualità delle immagini.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: display, calibration, comfort, visuals, quality, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 548f484043f2b1cb62ce0e0cfb6450a956d412b3
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636929"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2 Risoluzione dei problemi di visualizzazione

## <a name="overview"></a>Panoramica
Il HoloLens 2 schermo è una combinazione di waveguide e proiettori leggeri. Gli utenti guardano attraverso le onde, ovvero le lenti all'interno del visore, quando si indossano i visori VR. I proiettori leggeri si trova all'interno dello chassis sopra la fronte. HoloLens 2 usa la luce blu per illuminare lo schermo.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Seguire questa procedura per garantire la massima qualità visiva degli ologrammi presentati nei display:

* **Aumentare la luminosità dello schermo.** Ologrammi migliore quando lo schermo è al livello più chiaro. Quando si indossa il HoloLens, i pulsanti di luminosità si trova sul lato sinistro del visore vicino al tempio.
* **Avvicinare il visore agli occhi.** Ruotare il visore verso il basso nella posizione più vicina agli occhi.
* **Maiusc visore verso il basso.** Provare a spostare il rilievo della testa verso il basso, in modo da avvicinare il visore al visore.
* **[Eseguire la calibrazione oculare.](hololens-calibration.md#calibrating-your-hololens-2)** Lo schermo usa la distanza interpuperiale (IPD) e lo sguardo fisso per ottimizzare le immagini sullo schermo. Se non si esegue la calibrazione oculare, la qualità dell'immagine potrebbe peggiorare. Per eseguire la calibrazione oculare, passare **a** Impostazioni  >    >  **Calibrazione** del sistema  >  **Eseguire la calibrazione oculare.**
* **Eseguire la calibrazione dei colori dello schermo.** Nella [Windows olografica, versione 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e versioni  successiva, è possibile selezionare un profilo colore alternativo per la HoloLens 2 schermo. In questo modo i colori possono risultare più accurati, in particolare a livelli di luminosità inferiori dello schermo. La calibrazione dei colori dello schermo è disponibile nell'app **Impostazioni,** nella pagina **Calibrazione** > sistema.

    > [!NOTE]
    > Poiché questa impostazione salva un nuovo profilo colori nel firmware di visualizzazione, si tratta di un'impostazione per dispositivo (e non univoca per ogni account utente).

### <a name="how-to-use-display-color-calibration"></a>Come usare la calibrazione dei colori di visualizzazione
1. Avviare **l'app Impostazioni** e passare a **System > Calibration (Calibrazione del > sistema).**
1. In **Calibrazione colori visualizzazione** selezionare il pulsante Run display color **calibration (Esegui calibrazione colori** schermo).
1. Verrà avviata l'esperienza di calibrazione del colore dello schermo e si consiglia di assicurarsi che il visore si trova nella posizione corretta.
1. Dopo aver seguito le finestre di dialogo delle istruzioni, la visualizzazione verrà automaticamente disattivata fino al 30% di luminosità.
    > [!TIP]
    > Se si verificano problemi di visualizzazione della scena in grigio nell'ambiente in uso, è possibile regolare manualmente il livello di luminosità di HoloLens 2 usando i pulsanti di luminosità sul lato sinistro del dispositivo.
1. Selezionare i pulsanti da 1 a 6 per provare immediatamente ogni profilo di colore e trovarne uno con l'aspetto migliore per gli occhi (in genere questo significa che il profilo che consente alla scena di apparire più neutro, con il modello in scala di grigi e i toni dell'interfaccia che sembrano come previsto).

    ![Visualizzare la scena di calibrazione dei colori](images/color-cal-ui.png)
    
6. Quando si è soddisfatti del profilo selezionato, selezionare il pulsante **Save & Exit (Salva e esci)**
1. Se si preferisce non apportare modifiche, selezionare & **pulsante Esci** per annullare le modifiche

> [!TIP]
> Ecco alcuni suggerimenti utili da tenere presenti quando si usa l'impostazione di calibrazione dei colori dello schermo:
> - È possibile eseguire nuovamente la calibrazione dei colori Impostazioni quando si desidera
> - Se qualcuno nel dispositivo ha usato in precedenza l'impostazione per modificare i profili colori, la data/ora della modifica più recente verrà riflessa nella Impostazioni colori
> - Quando si esegue nuovamente la calibrazione dei colori di visualizzazione, il profilo colori salvato in precedenza verrà evidenziato e il profilo 0 non verrà visualizzato (poiché il profilo 0 rappresenta il profilo colori originale dello schermo)
> - Se si vuole ripristinare il profilo colori originale dello schermo, è possibile farlo dalla pagina Impostazioni (vedere come reimpostare il profilo [colori)](#how-to-reset-color-profile)

### <a name="how-to-reset-color-profile"></a>Come reimpostare il profilo colori

Se non si è soddisfatti del profilo colori personalizzato salvato nel HoloLens 2, è possibile ripristinare il profilo colori originale del dispositivo:
1. Avviare **l'app Impostazioni** e passare a **System > Calibration (Calibrazione del > sistema).**
1. In **Calibrazione colori schermo** selezionare il pulsante Ripristina profilo **colori** predefinito.
1. Quando viene visualizzata la finestra di dialogo, selezionare **Riavvia** se si è pronti per riavviare HoloLens 2 e applicare le modifiche.

### <a name="top-display-color-calibration-known-issues"></a>Problemi noti di calibrazione del colore di visualizzazione superiore

- Nella pagina Impostazioni, la stringa di stato che indica quando è stata modificata l'ultima modifica del profilo colori non sarà aggiornata fino a quando non si ricarica la pagina di Impostazioni 
    - **Soluzione** alternativa: selezionare un'Impostazioni pagina di calibrazione e quindi selezionare nuovamente la pagina Calibrazione.
- Se il HoloLens 2 va in sospensione durante l'esecuzione della calibrazione dei colori dello schermo, riprenderà in un secondo momento nel ambiente iniziale e il livello di luminosità dello schermo sarà ancora in grigio.
- Potrebbe essere necessario provare a premere i pulsanti di luminosità sul lato sinistro del dispositivo verso l'alto o verso il basso alcune volte prima che funzionino come previsto.
- La localizzazione non è completa per tutti i mercati

## <a name="faq"></a>Domande frequenti

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Quali sono i modelli che occasionalmente lampeggiano negli angoli inferiori dello schermo?

In alcuni casi, HoloLens 2 mostra modelli diversi negli angoli inferiore sinistro e destro dello schermo. Di seguito sono riportati alcuni esempi (GIF animate). Questo modello fa parte del normale funzionamento del dispositivo HoloLens 2 per calibrare lo schermo per un'esperienza ottimale.

![Modello bifase](./images/DAT-Biphase-Fiducial.gif) ![Modello GEO](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Perché non è possibile scattare una fotografia accurata della HoloLens 2 schermo?

La HoloLens 2 è progettata per essere visualizzata dall'occhio umano. Il dispositivo ha un sistema di correzione del colore attivo che si adatta agli occhi dell'utente. Rispetto all'occhio umano, le fotocamere vedono gli ambienti in modo diverso e di seguito sono riportati alcuni fattori che possono influire su eventuali incoerenze tra ciò che una fotocamera acquisisce e ciò che vede un utente.

* **Posizione dell'occhio.** Il HoloLens 2 schermo è progettato in modo specifico per la posizione oculare dell'utente. Il HoloLens 2 usa la tecnologia di tracciamento oculare per adattarsi alla posizione oculare dell'utente. Una fotocamera con una posizione errata di pochi millimetri può causare la distorsione dell'immagine. Il posizionamento accurato con una fotocamera è difficile e deve corrispondere esattamente alla posizione e al rilievo oculare per cui il dispositivo sta eseguendo la correzione del colore.
* **Movimento oculare.** Lo schermo si adatta al movimento dell'occhio dell'utente per regolare i colori. Ciò che viene visualizzato sullo schermo può variare a seconda che l'utente cerchi il centro, il bordo o l'angolo dello schermo. Una singola acquisizione di immagini può nel migliore dei modi mostrare solo l'aspetto della visualizzazione per l'asse che corrisponde a una direzione dello sguardo fisso.
* **Visualizzazione binocolo.** Il HoloLens 2 è progettato per essere visualizzato con entrambi gli occhi. Il cervello si adatta alla visualizzazione di due immagini e le unisce insieme. Le immagini di una sola visualizzazione ignorano le informazioni dell'altra visualizzazione.
* **Tempo di esposizione della fotocamera.** Il tempo di esposizione della fotocamera deve essere un multiplo esatto di 1/120 di secondo. La HoloLens frame di visualizzazione è 120 Hz. A causa del modo in cui HoloLens 2 disegna immagini, anche l'acquisizione di un singolo fotogramma non è sufficiente per corrispondere all'esperienza visiva di un essere umano. Allo stesso tempo, se il dispositivo si sposta affatto, anche in micromovementi, il sistema riprogetta l'immagine sullo schermo per stabilizzare gli ologrammi. L'acquisizione di più fotogrammi senza HoloLens spostamento richiede in genere una configurazione di laboratorio.
* **Dimensioni dell'apertura della fotocamera.** Le dimensioni dell'apertura della fotocamera devono essere di almeno 3 mm per acquisire un'immagine accurata. Le fotocamere dei telefoni cellulari con piccole aperture integrano la luce di un'area più piccola rispetto all'occhio umano. Il dispositivo applica la correzione dei colori per i modelli osservati da aperture più grandi. Con piccole aperture, i modelli di uniformità sono più nitidi e rimangono visibili nonostante le correzioni dei colori applicate dal sistema.
* **Ingresso della fotocamera.** Il diametro dell'ingresso della fotocamera deve essere di almeno 3 mm di diametro per acquisire un'immagine accurata. In caso contrario, la fotocamera acquisisce alcuni modelli ad alta frequenza non visibili all'occhio. La posizione dell'attrito dell'ingresso deve essere davanti alla fotocamera e posizionata alla distanza di rilievo oculare per evitare l'introduzione di aberrazioni e altre variazioni all'immagine acquisita.
* **Posizione della fotocamera.** Le fotocamere che soddisfano i requisiti per visualizzare lo schermo HoloLens 2 sono più grandi ed è difficile posizionare la fotocamera abbastanza vicina al display HoloLens 2 per osservare l'immagine con correzione del colore. Se la fotocamera si trova nella posizione sbagliata, la correzione del colore può influire negativamente sull'acquisizione HoloLens 2 schermo.
* **Correzione dell'immagine.** Le fotocamere digitali tipiche e le fotocamere per smartphone applicano una curva di riproduzione del tono (TRC) che aumenta il contrasto e il colore per fornire un risultato di snappier. Se applicata a un HoloLens 2 schermo, questa curva tono amplifica le non uniformità.

Detto questo, è comunque possibile che le fotocamere industriali specializzate acquisiscono immagini rappresentative dal HoloLens 2 schermo. Sfortunatamente, smartphone, consumer e fotocamere professionali non acquisiscono immagini corrispondenti a quanto visualizzato da un utente HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Cosa fa la calibrazione oculare per visualizzare la qualità dell'immagine?

La HoloLens 2 colore corregge attivamente le immagini in base alla posizione degli occhi dell'utente. [La calibrazione](hololens-calibration.md) oculare fornisce due input importanti: (1) la distanza interpuperiale (IPD) dell'utente e (2) la direzione di ogni occhio. Senza calibrazione oculare, per impostazione predefinita il sistema ha una posizione oculare nominale senza movimento oculare. La differenza tra la correzione del colore attiva e nessuna correzione dipende dalla fisiologia dell'utente stesso. Ad esempio, gli utenti con lo stesso IPD dell'impostazione predefinita del sistema visualizzano un minor numero di miglioramenti per la correzione dei colori. Mentre gli utenti con un IPD molto più ristretto o più ampio rispetto all'impostazione predefinita del sistema visualizzano più modifiche all'immagine visualizzata.

Si noti che una nuova funzionalità di [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) inizierà a rilevare automaticamente [la posizione dell'occhio.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Quali sono le differenze di visualizzazione tra HoloLens (prima generazione) e HoloLens 2?

Tra le richieste principali che i clienti hanno dato HoloLens a Microsoft dopo aver riscontrato che 1 è stato (1) aumentare il campo di visualizzazione e (2) aumentare la luminosità. Gli sviluppi tecnologici hanno consentito a Microsoft di produrre waveguid che raddoppiano l'area del campo di visualizzazione e di produrre proiettori leggeri con uno schermo fino a tre volte più chiaro. L'hardware imposta la linea di base per un insieme di compromessi per la qualità dell'immagine di visualizzazione: (1) campo di visualizzazione, (2) luminosità e uniformità dei colori (3). Il continuo miglioramento della tecnologia consente miglioramenti in tutte le aree senza compromettere un'altra area. Nel frattempo, la tecnologia esistente imposta i limiti disponibili per questi compromessi.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Quali sono i miglioramenti in arrivo che miglioreranno la HoloLens 2 delle immagini?

Anche se sono in corso molte indagini per migliorare la qualità delle immagini, è previsto che gli aggiornamenti previsti per le aree seguenti siano i seguenti:

* **Posizione automatica degli occhi.** Questa funzionalità consentirà di eseguire le procedure di calibrazione oculare in background. Gli utenti non dovranno più eseguire la calibrazione oculare per il corretto funzionamento della correzione del colore attiva. Ma funzionerà.
* **Miglioramenti della calibrazione dei colori.** Questo aggiornamento è in particolare sui valori dei colori più scuri(ad esempio, grigio scuro). Al momento, i colori dei dizionari prelevano un tono rosso. Questo problema si verifica anche quando l'intero schermo è in grigio, ovvero l'intero schermo preleva i colori rosso. Questo problema è il risultato di un'attività troppo grande nel canale di colore rosso per questi colori più scuri. Sono state caratterizzate le curve di illuminazione illuminate a questi colori diversi e si sta lavorando per offrire una procedura di calibrazione dell'utente. Il risultato sarà una maggiore accuratezza del colore nello spettro della luminosità. Non cambierà l'aspetto degli sfondi bianchi con la luminosità completa. Si continua a consigliare l'uso di schemi progettuali in modalità scura nelle app.
* **Modalità di lettura.** Gli sviluppatori di app possono trovare un compromesso tra il campo di visualizzazione dello schermo e ottenere una risoluzione angolare superiore. Gli sviluppatori di app possono eseguire l'override della matrice di proiezione in modo che il rendering del contenuto sia eseguito alla risoluzione del disegno dello schermo. Questa funzionalità comporta una riduzione del 30% del campo di visualizzazione e un aumento corrispondente della risoluzione angolare. È in corso un lavoro per introdurre questa funzionalità alla realtà [mista Toolkit](https://github.com/Microsoft/MixedRealityToolkit-Unity). Quando disponibile, la modalità di lettura funzionerà in qualsiasi HoloLens 2 operativo, non dipende da un aggiornamento del sistema operativo.

Gli aggiornamenti del sistema operativo vengono recapitati automaticamente. È anche possibile testare le versioni iniziali del miglioramento del software tramite il programma Insider Preview.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Quali linee guida sono disponibili per gli sviluppatori per applicare i principi di progettazione della modalità scura?

Gli utenti avranno la migliore esperienza quando si evitano sfondi bianchi. La modalità scura è un principio di progettazione usato dalle app per usare sfondi di colore nero o scuro. Per impostazione predefinita, le impostazioni di sistema sono in modalità scura e possono essere modificate Impostazioni  >  **colore di**  >  **sistema.**

È consigliabile che gli sviluppatori seguano le linee guida per la progettazione in modalità scura:

* [Linee guida di progettazione per sviluppatori HoloLens display](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Dimensioni dei caratteri consigliate](/windows/mixed-reality/typography#recommended-font-size)

Quando un ologramma richiede uno sfondo bianco, mantenere le dimensioni dell'ologramma inferiori rispetto al campo di visualizzazione completo dello schermo. Questa dimensione consente agli utenti di inserire l'ologramma al centro dello schermo.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Come si pulisce un HoloLens 2 schermo?

Usare un microfibero per cancellare il visore. Per pulire il visore, usare il 70% di bevande isopropyl per inumidire leggermente un visore e quindi cancellare il visore. Leggere le linee guida complete nelle domande [frequenti HoloLens 2 pulizia dei dati.](hololens2-maintenance.md)
