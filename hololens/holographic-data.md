---
title: Trovare e salvare file in HoloLens
description: Informazioni su come usare Esplora file in HoloLens per aprire, visualizzare e gestire i file nel dispositivo di realtà mista.
keywords: procedura, selezione file, file, foto, video, immagini, OneDrive, archiviazione, Esplora file, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428354"
---
# <a name="find-open-and-save-files-on-hololens"></a>Trovare, aprire e salvare file in HoloLens

I file creati in HoloLens, inclusi foto e video, vengono salvati direttamente nel HoloLens dispositivo. È possibile visualizzarli e gestirli nello stesso modo in cui si gestiscono i file Windows 10:

- Uso dell Esplora file app per accedere alle cartelle locali.
- All'interno dello spazio di archiviazione di un'app.
- In una cartella speciale, ad esempio il video o la raccolta musicale.
- Uso di un servizio di archiviazione che include un'app e una selezione file, ad esempio OneDrive.
- Usando un PC desktop connesso al HoloLens tramite un cavo USB, usando il supporto MTP (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Visualizzare i file HoloLens usando Esplora file

> Si applica a tutti HoloLens 2 e HoloLens (prima generazione) a partire dall'aggiornamento di Windows 10 aprile [2018 (RS4) per HoloLens](/windows/mixed-reality/release-notes-april-2018).

Usare Esplora file in HoloLens per visualizzare e gestire i file nel dispositivo, inclusi oggetti 3D, documenti e immagini. Passare a **Start**   >  **All apps**   >  **(Avvia tutte Esplora file** app) per iniziare.

> [!TIP]
> Se non sono elencati file in Esplora file, selezionare **Questo dispositivo** nel riquadro in alto a sinistra.

Se non viene visualizzato alcun file in Esplora file, il filtro "Recenti" potrebbe essere attivo (l'icona dell'orologio è evidenziata nel riquadro sinistro). Per risolvere il problema, selezionare l'icona del documento This **Device** (Questo dispositivo) nel riquadro sinistro (sotto l'icona dell'orologio) oppure aprire il menu e selezionare **This Device (Questo dispositivo).**

## <a name="find-and-view-your-photos-and-videos"></a>Trovare e visualizzare foto e video

[L'acquisizione di realtà](holographic-photos-and-videos.md) mista consente di scattare foto e video di realtà mista HoloLens.  Queste foto e video vengono salvati nella cartella Camera Roll del dispositivo.

È possibile accedere a foto e video scattati con HoloLens da:

- l'accesso al rullo della fotocamera direttamente tramite [l Foto app](holographic-photos-and-videos.md).
- caricamento di foto e video nell'archiviazione cloud tramite la sincronizzazione di foto e video OneDrive.
- usando la Acquisizione realtà mista pagina del [Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>App Foto

L Foto app è una delle app predefinite nel menu **Start** ed è incorporata con HoloLens. Altre informazioni [sull'uso dell'app Foto per visualizzare il contenuto.](holographic-photos-and-videos.md)

È anche possibile installare [l'app OneDrive dal Microsoft Store](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) per sincronizzare le foto con altri dispositivi.

### <a name="onedrive-app"></a>OneDrive app

[OneDrive](https://onedrive.live.com/) consente di accedere, gestire e condividere foto e video con qualsiasi dispositivo e con qualsiasi utente. Per accedere alle foto e ai video acquisiti HoloLens, scaricare [l'app OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) dal Microsoft Store nel HoloLens. Dopo il download, aprire l'app OneDrive, **selezionare** Impostazioni Caricamento della fotocamera  >  e attivare Caricamento **della fotocamera.**

### <a name="connect-to-a-pc"></a>Connessione a un PC

Se il HoloLens esegue l'aggiornamento di Windows 10 aprile [2018](/windows/mixed-reality/release-notes-april-2018) o versione successiva, è possibile connettere il HoloLens a un PC Windows 10 usando un cavo USB per esplorare foto e video nel dispositivo usando MTP (Media Transfer Protocol). Se nel dispositivo è configurato un PIN o una password, è necessario assicurarsi che il dispositivo sia sbloccato per esplorare i file.  

Se è stato abilitato [il Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal), è possibile usarlo per esplorare, recuperare e gestire le foto e i video archiviati nel dispositivo.

## <a name="access-files-within-an-app"></a>Accedere ai file all'interno di un'app

Se un'applicazione salva i file nel dispositivo, è possibile usarla per accedervi.

### <a name="requesting-files-from-another-app"></a>Richiesta di file da un'altra app

Un'applicazione può richiedere di salvare un file o aprire un file da un'altra app usando [le selettori di file](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Cartelle note

HoloLens supporta una serie di cartelle note a [cui le](/windows/mixed-reality/app-model#known-folders) app possono richiedere l'autorizzazione di accesso.

## <a name="view-hololens-files-on-your-pc"></a>Visualizzare HoloLens file nel PC

Analogamente ad altri dispositivi mobili, connettersi HoloLens al PC desktop usando MTP (Media Transfer Protocol) e aprire Esplora file sul PC per accedere alle librerie HoloLens per facilitarlo.

Per visualizzare i file HoloLens in Esplora file nel PC:

1. Accedere al HoloLens, quindi collegarlo al PC usando il cavo USB fornito con il HoloLens.

1. Selezionare **Apri dispositivo per visualizzare i file Esplora file** o aprire Esplora file nel PC e passare al dispositivo.

Per visualizzare informazioni sull'HoloLens, fare clic con il pulsante destro del mouse sul nome del Esplora file nel PC e quindi **scegliere Proprietà.**

> [!NOTE]
> HoloLens (prima generazione) non supporta la connessione a dischi rigidi esterni o schede SD.

## <a name="sync-to-the-cloud"></a>Sincronizzare con il cloud

Per sincronizzare foto e altri file dal HoloLens al cloud, installare e OneDrive in HoloLens. Per ottenere OneDrive, cercarlo nel Microsoft Store nel HoloLens.

HoloLens non consente di eseguire il backup di file e dati dell'app, quindi è buona idea salvare le informazioni importanti per OneDrive. In questo modo, se si reimposta il dispositivo o si disinstalla un'app, verrà eseguito il backup delle informazioni.
