---
title: Trovare e salvare i file in HoloLens
description: Informazioni su come usare Esplora file HoloLens per aprire, visualizzare e gestire i file nel dispositivo di realtà mista.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032549"
---
# <a name="find-open-and-save-files-on-hololens"></a>Trovare, aprire e salvare i file HoloLens

I file creati in HoloLens, incluse foto e video, vengono salvati direttamente nel dispositivo HoloLens dispositivo. Visualizzarli e gestirli nello stesso modo in cui si gestirebbero i file Windows 10:

- Uso dell Esplora file app per accedere alle cartelle locali.
- All'interno dell'archiviazione di un'app.
- In una cartella speciale, ad esempio il video o la libreria musicale.
- Uso di un servizio di archiviazione che include un'app e una selezione file (ad esempio OneDrive).
- Uso di un PC desktop connesso al HoloLens tramite un cavo USB, usando il supporto MTP (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Visualizzare i file HoloLens usando Esplora file

> Si applica a tutti HoloLens 2 e HoloLens (prima generazione) a partire dall'aggiornamento di [Windows 10 aprile 2018 (RS4)](/windows/mixed-reality/release-notes-april-2018)per HoloLens .

Usare Esplora file in HoloLens per visualizzare e gestire i file nel dispositivo, inclusi oggetti 3D, documenti e immagini. Passare a **Start**   >  **All apps**   >  **Esplora file** per iniziare.

> [!TIP]
> Se non sono presenti file elencati in Esplora file, selezionare **Questo** dispositivo nel riquadro superiore sinistro.

Se non viene visualizzato alcun file in Esplora file, il filtro "Recenti" potrebbe essere attivo (l'icona dell'orologio è evidenziata nel riquadro sinistro). Per risolvere questo problema, selezionare l'icona del documento This **Device** (Questo dispositivo) nel riquadro sinistro (sotto l'icona dell'orologio) oppure aprire il menu e selezionare **This Device (Questo dispositivo).**

## <a name="find-and-view-your-photos-and-videos"></a>Trovare e visualizzare foto e video

[L'acquisizione di realtà](holographic-photos-and-videos.md) mista consente di scattare foto e video di realtà mista HoloLens.  Queste foto e questi video vengono salvati nella cartella Rullino del dispositivo.

È possibile accedere a foto e video scattati con HoloLens:

- accesso al rullino direttamente tramite [l'app Foto .](holographic-photos-and-videos.md)
- caricamento di foto e video nell'archiviazione cloud sincronizzando foto e video OneDrive.
- usando la Acquisizione realtà mista pagina del Windows Portale di dispositivi [.](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)

### <a name="photos-app"></a>App Foto

L Foto app è una delle app predefinite nel menu **Start** ed è integrata con HoloLens. Altre informazioni [sull'uso dell'app Foto per visualizzare il contenuto.](holographic-photos-and-videos.md)

È anche possibile installare [l'app OneDrive dal Microsoft Store](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) per sincronizzare le foto con altri dispositivi.

### <a name="onedrive-app"></a>OneDrive app

[OneDrive](https://onedrive.live.com/) consente di accedere, gestire e condividere foto e video con qualsiasi dispositivo e con qualsiasi utente. Per accedere alle foto e ai video acquisiti HoloLens, scaricare [l'app OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) dal Microsoft Store nel HoloLens. Dopo il download, aprire l'app OneDrive e selezionare Impostazioni Caricamento fotocamera  >  e attivare **Caricamento fotocamera**.

### <a name="connect-to-a-pc"></a>Connessione a un PC

Se il HoloLens esegue l'aggiornamento di Windows 10 aprile [2018](/windows/mixed-reality/release-notes-april-2018) o versione successiva, è possibile connettere il HoloLens a un PC Windows 10 usando un cavo USB per esplorare foto e video nel dispositivo usando MTP (media transfer protocol). È necessario assicurarsi che il dispositivo sia sbloccato per esplorare i file se nel dispositivo è configurato un PIN o una password.  

Se è stato abilitato [il Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal), è possibile usarlo per esplorare, recuperare e gestire le foto e i video archiviati nel dispositivo.

## <a name="access-files-within-an-app"></a>Accedere ai file all'interno di un'app

Se un'applicazione salva i file nel dispositivo, è possibile usarla per accedervi.

### <a name="requesting-files-from-another-app"></a>Richiesta di file da un'altra app

Un'applicazione può richiedere di salvare un file o aprire un file da un'altra app usando i [selettori di file](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Cartelle note

HoloLens supporta una serie di cartelle note a [cui](/windows/mixed-reality/app-model#known-folders) le app possono richiedere l'autorizzazione di accesso.

## <a name="view-hololens-files-on-your-pc"></a>Visualizzare HoloLens file nel PC

Analogamente ad altri dispositivi mobili, connettersi HoloLens al PC desktop usando MTP (Media Transfer Protocol) e aprire Esplora file nel PC per accedere alle librerie HoloLens per un facile trasferimento.

Per visualizzare i HoloLens nel Esplora file nel PC:

1. Accedere a HoloLens quindi collegarlo al PC usando il cavo USB fornito con il HoloLens.

1. Selezionare **Apri dispositivo per visualizzare i file con Esplora file** o aprire Esplora file nel PC e passare al dispositivo.

Per visualizzare le informazioni sull'HoloLens, fare clic con il pulsante destro del mouse sul nome del dispositivo Esplora file nel PC e quindi scegliere **Proprietà**.

> [!NOTE]
> HoloLens (prima generazione) non supporta la connessione a dischi rigidi esterni o schede SD.

## <a name="sync-to-the-cloud"></a>Sincronizzare con il cloud

Per sincronizzare foto e altri file dal HoloLens al cloud, installare e configurare OneDrive in HoloLens. Per ottenere OneDrive, cercarlo nel Microsoft Store nel HoloLens.

HoloLens backup dei file e dei dati dell'app, è quindi buona idea salvare le informazioni importanti per OneDrive. In questo modo, se si reimposta il dispositivo o si disinstalla un'app, verrà eseguito il backup delle informazioni.
