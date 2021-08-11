---
title: Usare i menu Start e Ambiente iniziale
description: Informazioni su come usare il menu Start, gestire e accedere alle app e spostarsi ambiente iniziale nei HoloLens dispositivi.
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
ms.openlocfilehash: c510738595e234b30395aafa309d42bd33affb7889a3174f2e708ba1aac56626
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664902"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Usare i menu Start e Ambiente iniziale

Proprio come l'esperienza Windows pc inizia con il desktop, Windows Holographic inizia con ambiente iniziale.  Usando il menu Start è possibile aprire e posizionare finestre dell'app, utilità di avvio delle app immersive e contenuto 3D in ambiente iniziale e la relativa posizione nello spazio fisico verrà memorizzata.

## <a name="use-the-start-menu"></a>Usare il menu Start

Il menu Start di HoloLens consente di aprire le app, visualizzare informazioni importanti sullo stato e accedere a strumenti come la camera.

Ovunque ci si trova in HoloLens, è sempre possibile aprire il menu Start usando **il movimento Start**.  Alla HoloLens (prima generazione) il movimento Start è [bloom](https://support.microsoft.com/help/12644/hololens-use-gestures). In HoloLens 2, il [movimento Start tocca](hololens2-basic-usage.md#start-gesture) l'icona Start visualizzata sul polso.  È anche possibile aprire il menu Start usando la voce pronunciando "Vai a Start".

> [!TIP]
> Quando il menu Start è aperto, usare il movimento Avvia per chiuderlo o esaminare il menu Start e pronunciare "Chiudi".

Nella parte superiore del menu Start vengono visualizzati gli indicatori di stato per Wi-Fi, batteria, volume e orologio. In HoloLens 2 è presente anche un indicatore di ascolto che indica se il dispositivo è abilitato per la voce e se è in ascolto di comandi vocali. Nella parte inferiore sono disponibili i pulsanti **Foto** e **Video** che consentono di scattare foto e registrazioni video.  È anche disponibile un **Connessione** che consente di proiettare ciò che si vede in un altro dispositivo usando Miracast.

### <a name="find-apps-on-start-menu"></a>Trovare app in menu Start

Il menu Start ha un **elenco di app aggiunte** e un elenco Tutte **le** app.

- **L'elenco App aggiunte** mostra le app aggiunte. È possibile aggiungere e rimuovere app dall'elenco **App** aggiunte usando il menu di scelta rapida visualizzato quando si seleziona e si tiene **premuto** il riquadro di un'app.

- **L'elenco** Tutte le app mostra tutte le app installate nel dispositivo.  Selezionare il **pulsante Tutte** le app sul lato destro del menu **Start** per visualizzare l'elenco.

In entrambi gli elenchi  di app usare i pulsanti Pagina precedente e **Pagina successiva** sul lato destro del menu Start per scorrere tutte le app nell'elenco.  Entrambi gli elenchi di app verranno aperti automaticamente alla pagina usata per l'ultima volta durante una sessione del dispositivo.

> [!TIP]
> In HoloLens 2, è possibile scorrere direttamente gli elenchi di app usando il dito indice. È sufficiente toccare l'elenco con la punta del dito e trascinare verso l'alto o verso il basso.

### <a name="open-apps-from-start-menu"></a>Aprire app da menu Start

Per aprire un'app dal menu Start, è sufficiente **selezionare un** riquadro **dell'app.** È anche possibile pronunciare il nome di un'app per aprirla.

Quando si apre un'app dal menu Start, si verifica una delle operazioni seguenti, a seconda della modalità di progettazione dell'app:

- Viene **posizionata una finestra** dell'app. L'app viene quindi caricata nella finestra ed è possibile usarla come un touch screen.
- Viene **inserita un'icona di avvio di app 3D** per un'app immersiva. È quindi necessario selezionare **l'utilità di avvio** per aprire l'app immersiva.
- Viene posizionata una finestra dell'app che funge da **utilità** di avvio per un'app immersiva. L'app immersiva procederà all'avvio automatico.

Le finestre delle app e le utilità di avvio delle app ambiente iniziale rimangono in giro fino a quando non si decide di rimuoverle.  Offrono un comodo collegamento al mondo per usare queste finestre dell'app o per avviare app immersive senza doverle aprire di nuovo dal menu Start. 

> [!NOTE]
>Come in un telefono, le risorse di sistema vengono gestite automaticamente HoloLens.  Ad esempio, quando si apre una nuova app immersiva, tutte le altre app in esecuzione diventano immediatamente inattive. Non è necessario rimuovere le finestre delle app e le utilità di avvio ambiente iniziale liberare risorse di sistema. 

## <a name="using-apps-on-hololens"></a>Uso di app in HoloLens

Le app in HoloLens possono usare la visualizzazione della finestra dell'app o la visualizzazione immersiva. Con la visualizzazione della finestra dell'app, l'app mostra semplicemente il contenuto all'interno di una finestra. Con la visualizzazione immersiva, un'app si allontana dalla casa della realtà mista in cui può quindi visualizzare il contenuto nell'ambiente fisico circostante. Le app possono anche scegliere di usare entrambe le visualizzazioni.

### <a name="use-app-windows"></a>Usare le finestre dell'app

Nelle HoloLens app di prima generazione vengono posizionate e usate in ambiente iniziale, dove è possibile [spostarle,](hololens1-basic-usage.md#move-resize-and-rotate-apps) ridimensionarle e ruotarle come si desidera. Oltre a usare le finestre dell'app con lo sguardo e i movimenti, è anche possibile usarle con Bluetooth mouse e tastiera connessi.

In HoloLens 2, oltre a usare le finestre dell'app in ambiente iniziale, è anche possibile usare una finestra dell'app alla volta all'interno di un'app immersiva. È anche possibile impostare una finestra dell'app in modalità **Seguimi** in cui rimarrà davanti all'utente mentre si va in giro. Quando si apre una finestra dell'app mentre si è all'interno di un'app immersiva, viene aperta automaticamente in modalità **Seguimi.** È possibile [spostare, ridimensionare e ruotare le](hololens2-basic-usage.md#move-resize-and-rotate-holograms) finestre dell'app direttamente usando le mani sia in ambiente iniziale che all'interno di un'app immersiva.

> [!NOTE]
>
> - Possono essere attive fino a tre finestre dell'app ambiente iniziale alla volta. È possibile aprire altre informazioni, ma solo tre rimarranno attive.
> - Quando una finestra dell'app non è attiva, il contenuto avrà un aspetto scuro rispetto a una finestra attiva.  Alcuni mostreranno semplicemente l'icona dell'app anziché qualsiasi contenuto.  Per attivare una finestra inattiva, **è sufficiente selezionarla.**
> - Ogni app aperta può avere una finestra attiva alla volta, ad Microsoft Edge, che può avere fino a tre.

### <a name="close-apps"></a>Chiudere le app

Per chiudere un'app che usa una finestra dell'app, è sufficiente chiudere la finestra dell'app con **il pulsante** Chiudi sulla barra del titolo.  È anche possibile esaminare la finestra e pronunciare "Chiudi".

Per uscire da un'app che usa la visualizzazione immersiva, usare il movimento Avvia per visualizzare il menu Start **e** quindi selezionare il pulsante Home della **realtà mista.**

Se un'app immersiva è in uno stato interrotto ed è necessario riavviarla, è possibile assicurarsi che l'app venga prima arrestata completamente chiudendo l'utilità di avvio in ambiente iniziale e quindi avviarla dal menu Start.

### <a name="default-app-picker"></a>Selezione app predefinita

Con [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)quando si attiva un collegamento ipertestuale o si apre un tipo di file con più di un'app installata che lo supporta, verrà visualizzata una nuova finestra che richiede di selezionare l'app installata che deve gestire il tipo di file o collegamento. In questa finestra è anche possibile scegliere di fare in modo che l'app selezionata gestirà il file o il tipo di collegamento "Una volta" o "Sempre".

![Finestra di selezione app](images/default-app-picker.png)

Se si sceglie "Sempre" ma in un secondo momento si vuole modificare l'app che gestisce un file o un tipo di collegamento specifico, è possibile reimpostare le impostazioni predefinite salvate in Impostazioni > **App**. Scorrere fino alla fine della  pagina e selezionare il pulsante Cancella in "App predefinite per i tipi di file" e/o "App predefinite per i tipi di collegamento". A differenza dell'impostazione simile nei PC desktop, non è possibile reimpostare le impostazioni predefinite dei singoli tipi di file.

### <a name="per-app-volume-control"></a>Controllo del volume per app

Con [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)gli utenti possono regolare manualmente il livello di volume di ogni app. Ciò consente agli utenti di concentrarsi meglio sulle app necessarie o di ascoltare meglio quando usano più app. Ad esempio, la necessità di disattivare il volume di un'app chiamando un'altra persona per assistenza remota in un'altra.

Per impostare il volume di una singola app, passare Impostazioni Suono di sistema e **in** Opzioni audio avanzate  ->    ->  selezionare Volume app **e preferenze del dispositivo.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Informazioni correlate

[Trovare, installare e disinstallare le applicazioni dal Microsoft Store](holographic-store-apps.md)
