---
title: Acquisire, registrare e condividere foto e video di realtà mista
description: Informazioni su come acquisire, registrare e visualizzare e visualizzare foto e video di realtà mista usando dispositivi di realtà mista HoloLens. Informazioni su come condividere tramite Miracast o i file raccolti.
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
ms.openlocfilehash: 86ef4328869c15517732eedf3dfb9e2a8252e713
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309179"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Creare foto e video di realtà mista

HoloLens offre agli utenti l'esperienza di combinare il mondo reale con il mondo digitale.  Mixed Reality Capture (MRC) consente di acquisire l'esperienza come foto o video o di condividere ciò che viene visualizzato con altri utenti in tempo reale.

L'acquisizione di realtà mista usa un punto di vista in prima persona in modo che altri utenti possano visualizzare gli ologrammi mentre vengono visualizzati. Per un punto di vista di terze parti, usare [la visualizzazione degli elementi .](https://docs.microsoft.com/windows/mixed-reality/spectator-view) La visualizzazione degli elementi di lavoro è particolarmente utile per le demo.

Sebbene sia divertente condividere video tra amici e colleghi, i video possono essere utili anche per insegnare ad altri utenti a usare un'app o a comunicare problemi con app ed esperienze.

> [!NOTE]
> Se non è possibile avviare esperienze di acquisizione di realtà mista e HoloLens è un dispositivo di lavoro, rivolgersi all'amministratore di sistema. L'accesso alla fotocamera può essere limitato tramite criteri aziendali.

## <a name="capture-a-mixed-reality-photo"></a>Acquisire una foto di realtà mista

Esistono diversi modi per scattare una foto della realtà mista in HoloLens. È possibile usare i pulsanti hardware, la voce o il menu Start.

### <a name="hardware-buttons-to-take-photos"></a>Pulsanti hardware per scattare foto

Per scattare una foto rapida della visualizzazione corrente, premere contemporaneamente i pulsanti per il volume verso l'alto e il volume verso il basso.  Si tratta di un po' come la versione holoLens di uno screenshot o di una schermata di stampa.

- [Posizioni dei pulsanti HoloLens 2](hololens2-hardware.md)
- [Posizioni dei pulsanti in HoloLens (prima generazione)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Tenendo premuto **il volume e** i pulsanti **per** tre secondi, si inizierà a registrare un video invece di scattare una foto. Per arrestare la registrazione, toccare **contemporaneamente** i pulsanti volume su e **volume** giù.

### <a name="voice-commands-to-take-photos"></a>Comandi vocali per scattare foto

Nella HoloLens 2 versione 2004 (e successive) pronunciare: "Fare una foto".

In HoloLens (prima generazione) o HoloLens 2 versione 1903, ad esempio: "Hey Cortana, scatta una foto".

### <a name="start-menu-to-take-photos"></a>menu Start per scattare foto

Usare il movimento Avvia per passare a **Start** e quindi selezionare l'icona **della fotocamera.**

Puntare la testa nella direzione di ciò che si vuole acquisire, quindi [toccare l'aria](hololens2-basic-usage.md#touch-holograms-near-you) per scattare una foto. È possibile continuare a usare il tocco e acquisire foto aggiuntive. Tutte le foto acquisite verranno salvate nel dispositivo.

Usare di nuovo il movimento Avvia per terminare l'acquisizione di foto.  

## <a name="capture-a-mixed-reality-video"></a>Acquisire un video di realtà mista

Esistono diversi modi per registrare un video di realtà mista in HoloLens; è possibile usare i pulsanti hardware, la voce o il menu Start.

### <a name="hardware-buttons-to-record-videos"></a>Pulsanti hardware per registrare video

Il modo più rapido per registrare un  video è tenere premuti i pulsanti volume su e **volume** giù contemporaneamente fino all'inizio di un conto alla rovescia di tre secondi. Per arrestare la registrazione, toccare entrambi i pulsanti contemporaneamente.

> [!NOTE]
> Premendo rapidamente i **pulsanti volume su** e **volume** giù contemporaneamente, verrà scattata una foto anziché registrare un video.

### <a name="voice-to-record-videos"></a>Voce per registrare video

In HoloLens 2 versione 2004 (e successive), pronunciare: "Avvia registrazione". Per arrestare la registrazione, pronunciare "Stop recording".

In HoloLens (prima generazione) o HoloLens 2 versione 1903, ad esempio: "Hey Cortana, start recording". Per arrestare la registrazione, pronunciare "Hey Cortana, stop recording".

### <a name="start-menu-to-record-videos"></a>menu Start registrare video

Usare il movimento Avvia per passare a **Start** e quindi selezionare l'icona **del video.** Puntare la testa nella direzione di ciò che si vuole acquisire, quindi premere [il tocco per](hololens2-basic-usage.md#touch-holograms-near-you) avviare la registrazione. Verrà visualizzato un conto alla rovescia di tre secondi e verrà avviata la registrazione.

Per arrestare la registrazione, usare il movimento Avvia e selezionare l'icona **del video** evidenziata. Il video verrà salvato nel dispositivo.

> [!NOTE]
> **Si applica solo a HoloLens (prima generazione)**  
> Il [Aggiornamento di Windows 10 (ottobre 2018)](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) modifica il comportamento del movimento Start e del pulsante Windows in HoloLens (prima generazione). Prima dell'aggiornamento, il movimento Start o il pulsante Windows interrompeva la registrazione di un video. Dopo l'aggiornamento, tuttavia, il movimento Start o il pulsante Windows apre il menu **Start** (o il **menu** azioni rapide se si è in un'app immersiva), da cui è possibile selezionare l'icona **video** evidenziata per arrestare la registrazione.

## <a name="share-what-you-see-in-real-time"></a>Condividere ciò che viene visualizzato in tempo reale

Puoi condividere ciò che vedi in HoloLens con amici e colleghi in tempo reale. Sono disponibili alcuni metodi:

1. Connessione a un dispositivo o a un adattatore abilitato per Miracast per guardare un TV.
1. Uso [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) guardare in un PC
1. Uso [dell Microsoft HoloLens app complementare](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) da guardare in un PC.
1. Distribuzione dell'app [Microsoft Dynamics 365 Remote Assist,](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) che consente ai dipendenti in prima linea di trasmettere ciò che vedono a un esperto remoto. L'esperto remoto può quindi guidare il lavoro in prima linea verbalmente o annotando nel proprio mondo.

> [!NOTE]
> La condivisione di ciò che viene visualizzato tramite Portale di dispositivi di Windows o Microsoft HoloLens'app complementare richiede che HoloLens sia in [modalità sviluppatore.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Trasmettere video con Miracast

Usare il movimento Avvia per passare a **Start** e quindi selezionare l'icona **di** connessione. Nel selettore visualizzato selezionare il dispositivo o l'adattatore abilitato per Miracast a cui si vuole connettersi.

Per interrompere la condivisione, usare il movimento Avvia e selezionare l'icona **di connessione** evidenziata. Poiché si è in streaming, non verrà salvato nulla nel dispositivo.

> [!NOTE]
> Il supporto Miracast è stato abilitato in HoloLens (prima generazione) a partire [dall'Aggiornamento di Windows 10 (ottobre 2018)](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).

### <a name="real-time-video-with-windows-device-portal"></a>Video in tempo reale con Portale di dispositivi di Windows

Poiché la condivisione tramite Portale di dispositivi di Windows richiede che la modalità sviluppatore sia abilitata in HoloLens, seguire le istruzioni nella documentazione per gli sviluppatori per configurare la modalità sviluppatore e passare Portale di dispositivi di Windows [.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens'app complementare

Poiché la condivisione tramite l Microsoft HoloLens app complementare richiede che la modalità sviluppatore sia abilitata in HoloLens, seguire le istruzioni nella documentazione per gli sviluppatori per configurare la [modalità sviluppatore](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). Scaricare quindi [l'app Microsoft HoloLens complementare](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) e seguire le istruzioni all'interno dell'app per connettersi a HoloLens.

Dopo aver configurato l'app con HoloLens, selezionare l'opzione **Streaming** live dal menu principale dell'app.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Visualizzare foto e video di realtà mista

Le foto e i video di realtà mista vengono salvati nel "Rullino" del dispositivo. È possibile esplorare il contenuto di questa cartella in HoloLens con l'app Esplora file (passare a Immagini > Rullino foto).

È anche possibile visualizzare foto e video di realtà mista nell'app Foto, preinstallata in HoloLens. Per aggiungere una foto nel mondo, selezionarla nell'app Foto e scegliere **Inserisci nel mondo misto.** È possibile spostare la foto in tutto il mondo dopo che è stata posizionata.

Per visualizzare e/o salvare foto e video di realtà mista in un PC connesso a HoloLens, puoi usare [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) o [l'Esplora file del PC tramite MTP.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Usare Esplora file per ottenere immagini, video e file

Analogamente ad altri dispositivi mobili, connetti HoloLens al PC per visualizzare Esplora file per accedere alle librerie di HoloLens (foto, video, documenti) per facilitane il trasferimento. Questo metodo è facile da usare e non richiede l'uso del portale di dispositivi o del Wi-Fi.

1. Sbloccare il dispositivo.
1. Connettere il dispositivo a un PC tramite USB.
1. Esplora file si aprirà nel PC.
1. Passare a: this PC \\ *yourhololensname*\Internal Storage\Pictures\Camera Roll
1. Copiare i file necessari nel PC.

Suggerimenti:
- Se non vengono visualizzati file, assicurati di accedere a HoloLens per abilitare l'accesso ai dati.
- È possibile ottenere altri file in altre cartelle, ad esempio i file [di diagnostica](hololens-diagnostic-logs.md#offline-diagnostics) dalla cartella Documenti.
- Da Esplora file sul PC, è possibile selezionare Proprietà del dispositivo per visualizzare il numero di versione del sistema operativo Windows Holographic (versione del firmware), il numero di serie del dispositivo e la percentuale della batteria.
- Se l'organizzazione ha usato MDM per [disabilitare Connectivity/AllowUSBConnection,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) non sarà possibile connettersi al dispositivo.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Condividere foto e video di realtà mista

Dopo aver acquisito una foto o un video di realtà mista, verrà visualizzata un'anteprima. Selezionare **l'icona di** condivisione sopra l'anteprima per visualizzare l'assistente alla condivisione. Da qui è possibile selezionare l'end point in cui si desidera condividere la foto o il video.

È anche possibile condividere foto e video di realtà mista da OneDrive caricando automaticamente foto e video di realtà mista. Aprire l'app OneDrive in HoloLens e accedere con un account Microsoft [personale,](https://account.microsoft.com) se non è già stato fatto. Selezionare **l'icona** delle impostazioni e scegliere **Camera upload (Caricamento fotocamera).** Attivare Caricamento fotocamera. Le foto e i video di realtà mista verranno ora caricati in OneDrive ogni volta che si avvia l'app in HoloLens.

> [!NOTE]
> È possibile abilitare il caricamento della fotocamera in OneDrive solo se si è connessi a OneDrive con un account account Microsoft. Se si configura HoloLens con un account aziendale o dell'istituto di istruzione, è possibile aggiungere un account Microsoft personale nell'app OneDrive per abilitare questa funzionalità.

## <a name="limitations-of-mixed-reality-capture"></a>Limitazioni dell'acquisizione di realtà mista

- Quando si usa l'acquisizione di realtà mista, il framerate di HoloLens verrà dimezzato a 30 Hz.
- La risoluzione di foto e video può essere ridotta se la fotocamera è già in uso da un'altra applicazione, durante lo streaming live o quando le risorse di sistema sono scarse.

### <a name="maximum-recording-length"></a>Lunghezza massima della registrazione

Nei HoloLens 2 precedenti a Windows Holographic, i video della versione 20H2 registrati nel dispositivo erano limitati alla durata massima di cinque minuti.

Grazie ai commenti e suggerimenti dei clienti, è stata aumentata la lunghezza di registrazione delle acquisizioni [di realtà mista.](holographic-photos-and-videos.md) Le acquisizioni di realtà mista non saranno più limitate a 5 minuti per impostazione predefinita, ma calcoleranno invece la lunghezza massima della registrazione in base allo spazio disponibile su disco. Il dispositivo stima la durata massima della registrazione video in base allo spazio disponibile su disco fino all'80% dello spazio totale su disco.

> [!NOTE]
> HoloLens userà la lunghezza di registrazione video predefinita (5 minuti) se si verifica una delle condizioni seguenti:
> - La durata massima stimata della registrazione è inferiore ai 5 minuti predefiniti.
> - Lo spazio su disco disponibile è inferiore al 20% dello spazio totale su disco.

## <a name="default-file-format-and-resolution"></a>Formato di file e risoluzione predefiniti

### <a name="default-photo-format-and-resolution"></a>Formato e risoluzione predefiniti della foto

|  Dispositivo  |  Formato  |  Estensione  |  Soluzione  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | jpg | 3904x2196px |
| HoloLens (prima generazione) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>Formato e risoluzione video registrati

| Dispositivo | Formato | Estensione | Soluzione | speed | Audio |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | Stereo a 48 kHz |
| HoloLens (prima generazione) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | Stereo a 48 kHz |
