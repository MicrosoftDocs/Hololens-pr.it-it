---
title: Acquisire, registrare e condividere foto e video di realtà mista
description: Informazioni su come acquisire, registrare e visualizzare e visualizzare foto e video di realtà mista HoloLens dispositivi di realtà mista. Informazioni su come condividere tramite Miracast o file raccolti.
keywords: hololens, foto, video, acquisizione, mrc, acquisizione di realtà mista, foto, fotocamera, miracast, streaming, livestream, demo, record
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 54e9959c03b69db39ff2738e5d4f41f9740ae562b38e8d85998521a4733edad7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664860"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Creare foto e video di realtà mista

HoloLens offre agli utenti l'esperienza di combinare il mondo reale con il mondo digitale.  Mixed Reality Capture (MRC) consente di acquisire l'esperienza come foto o video o di condividere ciò che viene visualizzato con altri utenti in tempo reale.

L'acquisizione di realtà mista usa un punto di vista in prima persona in modo che altri utenti possano visualizzare gli ologrammi mentre vengono visualizzati. Per un punto di vista di terze parti, usare [la visualizzazione degli elementi .](/windows/mixed-reality/spectator-view) La visualizzazione degli elementi di lavoro è particolarmente utile per le demo.

Sebbene sia divertente condividere video tra amici e colleghi, i video possono essere utili anche per insegnare ad altri utenti a usare un'app o a comunicare problemi con app ed esperienze.

> [!NOTE]
> Se non è possibile avviare esperienze di acquisizione di realtà mista e il HoloLens è un dispositivo di lavoro, rivolgersi all'amministratore di sistema. L'accesso alla fotocamera può essere limitato tramite criteri aziendali.

## <a name="capture-a-mixed-reality-photo"></a>Acquisire una foto di realtà mista

Esistono diversi modi per scattare una foto della realtà mista in HoloLens; È possibile usare i pulsanti hardware, la voce o il menu Start.

### <a name="hardware-buttons-to-take-photos"></a>Pulsanti hardware per scattare foto

Per scattare una foto rapida della visualizzazione corrente, premere contemporaneamente i pulsanti per il volume verso l'alto e il volume verso il basso.  Si tratta di un po' come la HoloLens di una schermata o di una schermata di stampa.

- [Posizioni dei pulsanti HoloLens 2](hololens2-hardware.md)
- [Posizioni dei pulsanti HoloLens (prima generazione)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Tenendo premuto **il volume e** i pulsanti **per** tre secondi, verrà avviata la registrazione di un video invece di scattare una foto. Per arrestare la registrazione, toccare contemporaneamente i pulsanti volume **up** **e volume** down.

### <a name="voice-commands-to-take-photos"></a>Comandi vocali per scattare foto

Nella HoloLens 2 versione 2004 (e successive) pronunciare: "Take a picture".

Nella HoloLens (prima generazione) o HoloLens 2 versione 1903, ad esempio: "Hey Cortana, take a picture".

### <a name="start-menu-to-take-photos"></a>menu Start di scattare foto

Usare il movimento Start per passare a **Start** e quindi selezionare l'icona **Fotocamera.**

Puntare la testa nella direzione di ciò che si vuole acquisire, quindi [fare un tocco per](hololens2-basic-usage.md#touch-holograms-near-you) scattare una foto. È possibile continuare a eseguire il tocco e acquisire foto aggiuntive. Tutte le foto acquisite verranno salvate nel dispositivo.

Usare di nuovo il movimento Start per terminare l'acquisizione di foto.  

## <a name="capture-a-mixed-reality-video"></a>Acquisire un video di realtà mista

Esistono diversi modi per registrare un video di realtà mista in HoloLens; È possibile usare i pulsanti hardware, la voce o il menu Start.

### <a name="hardware-buttons-to-record-videos"></a>Pulsanti hardware per registrare video

Il modo più rapido per registrare un video è tenere premuti i pulsanti di **volume** su e **volume** giù contemporaneamente fino all'inizio di un conto alla rovescia di tre secondi. Per arrestare la registrazione, toccare entrambi i pulsanti contemporaneamente.

> [!NOTE]
> Premendo rapidamente i **pulsanti di volume su** e **volume** giù nello stesso momento, verrà scattata una foto anziché registrare un video.

### <a name="voice-to-record-videos"></a>Voce per registrare video

Nella HoloLens 2 versione 2004 (e successive) pronunciare: "Avvia registrazione". Per arrestare la registrazione, pronunciare "Arresta registrazione".

Nella HoloLens (prima generazione) o HoloLens 2 versione 1903, ad esempio: "Hey Cortana, start recording". Per arrestare la registrazione, pronunciare "Hey Cortana, stop recording".

### <a name="start-menu-to-record-videos"></a>menu Start registrare video

Usare il movimento Avvia per passare a **Start** e quindi selezionare l'icona **Video.** Puntare la testa nella direzione di ciò che si vuole acquisire, quindi premere [il tocco per](hololens2-basic-usage.md#touch-holograms-near-you) avviare la registrazione. Verrà visualizzato un conto alla rovescia di tre secondi e verrà avviata la registrazione.

Per arrestare la registrazione, usare il movimento Avvia e selezionare l'icona **Video** evidenziata. Il video verrà salvato nel dispositivo.

> [!NOTE]
> **Si applica HoloLens (prima generazione)**  
> Il [Aggiornamento di Windows 10 (ottobre 2018)](/windows/mixed-reality/release-notes-october-2018) modifica il comportamento del movimento Start e Windows del pulsante HoloLens (prima generazione). Prima dell'aggiornamento, il movimento Start o il Windows arresta una registrazione video. Dopo l'aggiornamento, tuttavia, il movimento Start o il pulsante Windows apre il menu **Start** (o il **menu** azioni rapide se si è in un'app immersiva), da cui è possibile selezionare l'icona **video** evidenziata per arrestare la registrazione.

## <a name="share-what-you-see-in-real-time"></a>Condividere ciò che viene visualizzato in tempo reale

È possibile condividere ciò che si vede in HoloLens con amici e colleghi in tempo reale. Sono disponibili alcuni metodi:

1. Connessione a un Miracast o a un adattatore abilitato per l'uso per guardare un TV.
1. Uso [Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal) per guardare in un PC
1. Uso [dell Microsoft HoloLens app complementare](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) da guardare in un PC.
1. Distribuzione [dell'app Microsoft Dynamics 365 Remote Assist,](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) che consente ai dipendenti in prima linea di trasmettere ciò che vedono a un esperto remoto. L'esperto remoto può quindi guidare il lavoro in prima linea verbalmente o annotando nel proprio mondo.

> [!NOTE]
> La condivisione di ciò che viene visualizzato tramite Windows Portale di dispositivi o Microsoft HoloLens'app complementare richiede HoloLens essere in [modalità sviluppatore.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Streaming di video con Miracast

Usare il movimento Avvia per passare a **Start** e quindi selezionare **l'Connessione** avvio. Nella selezione visualizzata selezionare il dispositivo o l'Miracast a cui si vuole connettersi.

Per interrompere la condivisione, usare il movimento Avvia e selezionare l'icona **Connessione** evidenziata. Poiché si è in streaming, non verrà salvato nulla nel dispositivo.

> [!NOTE]
> Miracast è stato abilitato il supporto HoloLens (prima generazione) a partire [dal Aggiornamento di Windows 10 (ottobre 2018)](/windows/mixed-reality/release-notes-october-2018).

### <a name="real-time-video-with-windows-device-portal"></a>Video in tempo reale con Windows Portale di dispositivi

Poiché la condivisione tramite Windows Portale di dispositivi richiede che la modalità sviluppatore sia abilitata in HoloLens, seguire le istruzioni nella documentazione per sviluppatori per configurare la modalità sviluppatore e passare [Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal).

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens app complementare

Poiché la condivisione tramite l Microsoft HoloLens app complementare richiede che la modalità sviluppatore sia abilitata in HoloLens, seguire le istruzioni nella documentazione per sviluppatori per configurare [la modalità sviluppatore.](/windows/mixed-reality/using-the-windows-device-portal) Scaricare quindi [l'Microsoft HoloLens app complementare](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) e seguire le istruzioni all'interno dell'app per connettersi al HoloLens.

Dopo aver configurato l'app con il HoloLens, selezionare **l'opzione Streaming** live dal menu principale dell'app.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Visualizzare foto e video di realtà mista

Le foto e i video di realtà mista vengono salvati nel "Rullino" del dispositivo. È possibile esplorare il contenuto di questa cartella nel HoloLens con l'app Esplora file (passare a **Immagini > Rullino).**

È anche possibile visualizzare foto e video di realtà mista nell'app Foto, preinstallata in HoloLens. Per aggiungere una foto nel mondo, selezionarla nell'app Foto e scegliere Place in mixed world (Inserisci **nel mondo misto).** È possibile spostare la foto in tutto il mondo dopo che è stata posizionata.

Per visualizzare e/o salvare foto e video di realtà mista in un PC connesso a HoloLens, è possibile usare [Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) o il Esplora file del [PC tramite MTP.](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Usare Esplora file per ottenere immagini, video e file

Analogamente ad altri dispositivi mobili, connettere il HoloLens al PC per visualizzare Esplora file per accedere alle librerie di HoloLens (foto, video, documenti) per un trasferimento semplice. Questo metodo è facile da usare e non richiede l'uso del portale di dispositivi o del Wi-Fi.

1. Sbloccare il dispositivo.
1. Connessione il dispositivo a un PC tramite USB.
1. Esplora file si aprirà nel PC.
1. Passare a: This PC \\ *yourhololensname*\Internal Archiviazione\Pictures\Camera Roll
1. Copiare i file necessari nel PC.

Suggerimenti:
- Se non viene visualizzato alcun file, assicurarsi di accedere al HoloLens per abilitare l'accesso ai dati.
- È possibile ottenere altri file in altre cartelle, ad esempio i file [di diagnostica](hololens-diagnostic-logs.md#offline-diagnostics) dalla cartella Documenti.
- Da Esplora file sul PC Windows, è possibile selezionare Proprietà del dispositivo per visualizzare il numero di versione del sistema operativo olografico (versione del firmware), il numero di serie del dispositivo e la percentuale della batteria.
- Se l'organizzazione ha usato MDM per [disabilitare Connectivity/AllowUSBConnection,](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) non sarà possibile connettersi al dispositivo.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Condividere foto e video di realtà mista

Prima di [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)dopo aver acquisito una foto o un video di realtà mista, verrà visualizzata un'anteprima. Selezionare **l'icona** Condividi sopra l'anteprima per visualizzare l'assistente alla condivisione. Da qui è possibile selezionare l'end point in cui si desidera condividere la foto o il video.

Con Windows Holographic, versione 21H1, dopo aver acquisito una foto o un video di realtà mista, verrà visualizzata un'anteprima. Selezionare **l'icona** Condividi sopra l'anteprima per visualizzare l'assistente alla condivisione. Da qui è possibile selezionare l'end point (Posta elettronica, OneDrive e così via) con cui si desidera condividere la foto o il video. È anche possibile abilitare il HoloLens condividere con i dispositivi vicini Impostazioni **-> -> Shared Experiences**. Per altre informazioni, vedere [Condividere elementi con i dispositivi vicini in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

> [!TIP] 
> È anche possibile condividere foto e video di realtà mista OneDrive caricando automaticamente foto e video di realtà mista. Aprire l OneDrive app HoloLens e accedere con un account Microsoft **personale, [](https://account.microsoft.com)** se non è già stato fatto. Selezionare **l'Impostazioni** e scegliere **Caricamento fotocamera**. Attivare Il caricamento della fotocamera. Le foto e i video di realtà mista verranno ora caricati in OneDrive ogni volta che si avvia l'app HoloLens.

> [!NOTE]
> È possibile abilitare il caricamento della fotocamera solo OneDrive se si è effettuato l'accesso OneDrive con un account account Microsoft. Se si configura un HoloLens con un account aziendale o dell'istituto di istruzione, è possibile aggiungere un account Microsoft personale nell'app OneDrive per abilitare questa funzionalità.

## <a name="limitations-of-mixed-reality-capture"></a>Limitazioni dell'acquisizione di realtà mista

- Quando si usa l'acquisizione di realtà mista, la frequenza dei fotogrammi HoloLens sarà dimezzata a 30 Hz.
- La risoluzione di foto e video può essere ridotta se la fotocamera è già in uso da un'altra applicazione, durante lo streaming live o quando le risorse di sistema sono scarse.

### <a name="maximum-recording-length"></a>Lunghezza massima registrazione

Nei HoloLens 2 precedenti Windows Holographic, versione 20H2, i video registrati nel dispositivo erano limitati alla durata massima di cinque minuti.

Grazie ai commenti e suggerimenti dei clienti, è stata aumentata la lunghezza di registrazione delle acquisizioni [di realtà mista.](holographic-photos-and-videos.md) Le acquisizioni di realtà mista non saranno più limitate a 5 minuti per impostazione predefinita, ma calcoleranno invece la lunghezza massima della registrazione in base allo spazio disponibile su disco. Il dispositivo stima la durata massima della registrazione video in base allo spazio disponibile su disco fino all'80% dello spazio totale su disco.

> [!NOTE]
> Il HoloLens usa la durata predefinita della registrazione video (5 minuti) se si verifica una delle condizioni seguenti:
> - La durata massima stimata per la registrazione è inferiore ai 5 minuti predefiniti.
> - Lo spazio su disco disponibile è inferiore al 20% dello spazio totale su disco.

## <a name="default-file-format-and-resolution"></a>Formato di file e risoluzione predefiniti

### <a name="default-photo-format-and-resolution"></a>Formato e risoluzione predefiniti della foto

|  Dispositivo  |  Formato  |  Estensione  |  Risoluzione  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | jpg | 3904x2196px |
| HoloLens (prima generazione) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>Formato e risoluzione video registrati

| Dispositivo | Formato | Estensione | Risoluzione | speed | Audio |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | Stereo a 48 kHz |
| HoloLens (prima generazione) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | Stereo a 48 kHz |
