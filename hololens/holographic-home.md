---
title: Usare i menu Start e Ambiente iniziale
description: Informazioni su come usare il menu Start, gestire e accedere alle app ed esplorare i ambiente iniziale nei HoloLens mobili.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f9a6f1692df05e5fd8faec3da07cc85f7c6a32c7
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189172"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Usare i menu Start e Ambiente iniziale

Proprio come l'Windows pc inizia con il desktop, Windows Holographic inizia con ambiente iniziale.  Usando il menu Start è possibile aprire e posizionare le finestre dell'app, le utilità di avvio delle app immersive e il contenuto 3D in ambiente iniziale e la loro posizione nello spazio fisico verrà memorizzata.

## <a name="use-the-start-menu"></a>Usare il menu Start

Il menu Start di HoloLens consente di aprire le app, visualizzare informazioni importanti sullo stato e accedere a strumenti come la camera.

Ovunque ci si trova in HoloLens, è sempre possibile aprire il menu Start usando il **movimento Start**.  Nella HoloLens (prima generazione) il movimento Start è [di tipo fiore.](https://support.microsoft.com/help/12644/hololens-use-gestures) Nella HoloLens 2, il [movimento Avvia](hololens2-basic-usage.md#start-gesture) è toccare l'icona Start visualizzata sul dito.  È anche possibile aprire il menu Start usando la voce pronunciando "Vai a Start".

> [!TIP]
> Quando la menu Start è aperta, usare il movimento Avvia per chiuderla oppure osservare il menu Start e pronunciare "Chiudi".

Nella parte superiore della menu Start, verranno visualizzati gli indicatori di stato per Wi-Fi, batteria, volume e orologio. In HoloLens 2 è presente anche un indicatore di ascolto che indica se il dispositivo è abilitato per la voce e se è in ascolto di comandi vocali. Nella parte inferiore sono disponibili i pulsanti **Foto** e **Video** che consentono di scattare foto e registrazioni video.  È anche disponibile **un pulsante Connessione** che consente di proiettare ciò che viene visualizzato in un altro dispositivo usando Miracast.

### <a name="find-apps-on-start-menu"></a>Trovare app in menu Start

Il menu Start ha un **elenco app aggiunte** e un elenco Tutte **le** app.

- **L'elenco App** aggiunte mostra le app aggiunte. È possibile aggiungere e rimuovere app dall'elenco **App** aggiunte usando il menu di scelta rapida visualizzato quando si seleziona e si tiene **premuto** un riquadro dell'app.

- **L'elenco** Tutte le app mostra tutte le app installate nel dispositivo.  Selezionare il **pulsante Tutte** le app sul lato destro del menu **Start** per visualizzare l'elenco.

In entrambi gli elenchi di app usare **i** pulsanti Pagina precedente e **Pagina successiva** sul lato destro del menu Start per scorrere tutte le app nell'elenco.  Entrambi gli elenchi di app si apriranno automaticamente alla pagina usata per l'ultima volta durante una sessione del dispositivo.

> [!TIP]
> Nella HoloLens 2 è possibile scorrere direttamente gli elenchi di app usando il dito indice. È sufficiente toccare l'elenco con la punta del dito e trascinare verso l'alto o verso il basso.

### <a name="open-apps-from-start-menu"></a>Aprire app da menu Start

Per aprire un'app dal menu Start, è sufficiente **selezionare un** riquadro **dell'app.** È anche possibile pronunciare il nome di un'app per aprirla.

Quando si apre un'app dal menu Start, si verifica una delle condizioni seguenti, a seconda di come è progettata l'app:

- Viene **inserita una finestra** dell'app. L'app viene quindi caricata nella finestra ed è possibile usarla come un touchscreen.
- Viene **inserita un'utilità di avvio di app 3D** per un'app immersiva. È quindi necessario selezionare **l'utilità** di avvio per aprire l'app immersiva.
- Viene inserita una finestra dell'app che funge da utilità **di** avvio per un'app immersiva. L'app immersive verrà avviata automaticamente.

Le finestre delle app e le utilità di avvio delle app ambiente iniziale rimangono in questa posizione finché non si decide di rimuoverle.  Offrono un pratico collegamento per usare le finestre delle app o avviare app immersive senza doverle aprire di nuovo dal menu Start. 

> [!NOTE]
>Come in un telefono, le risorse di sistema vengono gestite automaticamente HoloLens.  Ad esempio, quando si apre una nuova app immersiva, tutte le altre app in esecuzione diventano immediatamente inattive. Non è necessario rimuovere le finestre delle app e le utilità di avvio ambiente iniziale per liberare risorse di sistema. 

## <a name="using-apps-on-hololens"></a>Uso di app in HoloLens

Le app in HoloLens possono usare la visualizzazione finestra dell'app o la visualizzazione immersiva. Con la visualizzazione della finestra dell'app, l'app mostra semplicemente il contenuto all'interno di una finestra. Con la visualizzazione immersiva, un'app consente di allontanarsi dalla realtà mista, in cui può quindi visualizzare il contenuto nell'ambiente fisico intorno all'utente. Le app possono anche scegliere di usare entrambe le visualizzazioni.

### <a name="use-app-windows"></a>Usare le finestre delle app

Nelle HoloLens app di prima generazione vengono posizionate e usate in ambiente iniziale, dove è possibile [spostarle,](hololens1-basic-usage.md#move-resize-and-rotate-apps) ridimensionarle e ruotarle nel modo che si desidera. Oltre a usare le finestre dell'app con sguardo fisso e movimento, è anche possibile usarle con Bluetooth mouse e tastiera connessi.

In HoloLens 2, oltre a usare le finestre dell'app in ambiente iniziale, è anche possibile usare una finestra dell'app alla volta all'interno di un'app immersive. È anche possibile impostare una finestra dell'app in modalità Follow **me** (Seguimi) in cui verrà visualizzata durante la procedura. Quando si apre una finestra dell'app all'interno di un'app immersiva, questa verrà aperta automaticamente in modalità **Seguimi.** È possibile [spostare, ridimensionare e ruotare le](hololens2-basic-usage.md#move-resize-and-rotate-holograms) finestre dell'app direttamente usando le mani sia in ambiente iniziale che all'interno di un'app immersiva.

> [!NOTE]
>
> - Possono essere attive fino a tre finestre dell'app ambiente iniziale alla volta. È possibile aprire altri elementi, ma solo tre rimarranno attivi.
> - Quando una finestra dell'app non è attiva, verrà visualizzato contenuto con aspetto scuro rispetto a una finestra attiva.  Alcuni mostreranno semplicemente l'icona dell'app anziché qualsiasi contenuto.  Per attivare una finestra inattiva, **è sufficiente selezionarla.**
> - Ogni app aperta può avere una finestra attiva alla volta, ad Microsoft Edge, che può avere fino a tre.

### <a name="close-apps"></a>Chiudere le app

Per chiudere un'app che usa una finestra dell'app, è sufficiente chiudere la finestra dell'app con **il pulsante** Chiudi sulla barra del titolo.  È anche possibile esaminare la finestra e pronunciare "Chiudi".

Per uscire da un'app che usa la visualizzazione immersiva, usa il movimento Avvia per visualizzare il menu Start **e** quindi seleziona il pulsante Home **di Realtà** mista.

Se un'app immersiva è in uno stato danneggiato ed è necessario riavviarla, è possibile assicurarsi che l'app venga arrestata completamente chiudendo l'utilità di avvio in ambiente iniziale e quindi avviarla dal menu Start.

### <a name="default-app-picker"></a>Selezione app predefinita

Con [Windows Holographic versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)quando si attiva un collegamento ipertestuale o si apre un tipo di file con più di un'app installata che la supporta, viene visualizzata una nuova finestra che richiede di selezionare l'app installata che deve gestire il tipo di file o di collegamento. In questa finestra è anche possibile scegliere di fare in modo che l'app selezionata gestirà il file o il tipo di collegamento "Una sola volta" o "Sempre".

![Finestra di selezione app.](images/default-app-picker.png)

Se si sceglie "Sempre" ma in seguito si vuole modificare l'app che gestisce un determinato file o tipo di collegamento, è possibile reimpostare le impostazioni predefinite salvate in **Impostazioni > app**. Scorrere fino alla fine della  pagina e selezionare il pulsante Cancella in "App predefinite per i tipi di file" e/o "App predefinite per i tipi di collegamento". A differenza dell'impostazione simile nei PC desktop, non è possibile reimpostare le impostazioni predefinite dei singoli tipi di file.

### <a name="per-app-volume-control"></a>Controllo del volume per app

Con [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)gli utenti possono modificare manualmente il livello di volume di ogni app. Ciò consente agli utenti di concentrarsi meglio sulle app necessarie o di ascoltare meglio quando usano più app. Ad esempio, la necessità di disattivare il volume di un'app mentre chiama un'altra persona per assistenza remota in un'altra.

Per impostare il volume di una singola app, passare Impostazioni Audio del sistema e in Opzioni audio avanzate  ->    ->  selezionare **Volume dell'app e preferenze del dispositivo.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Informazioni correlate

[Trovare, installare e disinstallare applicazioni dal Microsoft Store](holographic-store-apps.md)
