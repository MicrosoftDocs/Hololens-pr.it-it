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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283527"
---
# Trovare, aprire e salvare file in HoloLens

I file creati in HoloLens, incluse le foto e i video, vengono salvati direttamente nel dispositivo HoloLens. Visualizzare e gestire le stesse modalità di gestione dei file in Windows 10:

- Uso dell'app Esplora file per accedere alle cartelle locali.
- All'interno dello spazio di archiviazione di un'app.
- In una cartella speciale, ad esempio il video o la raccolta di musica.
- Uso di un servizio di archiviazione che include un'app e una selezione file (ad esempio OneDrive).
- Usare un PC desktop collegato al proprio HoloLens usando un cavo USB usando il supporto MTP (Media Transfer Protocol).

## Visualizzare i file in HoloLens usando Esplora file

> Si applica a tutti i dispositivi HoloLens 2 e HoloLens (1a generazione) dell' [aggiornamento di Windows 10 aprile 2018 (RS4) per HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).

Usare Esplora file in HoloLens per visualizzare e gestire i file nel dispositivo, inclusi oggetti 3D, documenti e immagini. Vai a **avviare**   >  **tutte le app**   >  **file Explorer** per iniziare.

> [!TIP]
> Se non sono presenti file in Esplora file, selezionare **questo dispositivo** nel riquadro in alto a sinistra.

Se non sono presenti file in Esplora file, il filtro "recenti" potrebbe essere attivo (l'icona dell'orologio viene evidenziata nel riquadro sinistro). Per risolvere questo problema, selezionare l'icona del documento di **questo dispositivo** nel riquadro sinistro (sotto l'icona dell'orologio) oppure aprire il menu e selezionare **questo dispositivo**.

## Trovare e visualizzare le foto e i video

L' [acquisizione di realtà mista](holographic-photos-and-videos.md) consente di scattare foto e video di realtà mista in HoloLens.  Queste foto e video vengono salvati nella cartella del rotolo della fotocamera del dispositivo.

È possibile accedere a foto e video scattate con HoloLens da:

- accesso al rotolo della videocamera direttamente nell' [app Foto](holographic-photos-and-videos.md).
- caricamento di foto e video nello spazio di archiviazione nel cloud sincronizzando le foto e i video in OneDrive.
- uso della pagina di acquisizione di realtà mista di [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### App Foto

L'app foto è una delle app predefinite nel menu **Start** e viene incorporata con HoloLens. Leggi altre informazioni sull' [uso dell'app Foto per visualizzare il contenuto](holographic-photos-and-videos.md).

È anche possibile installare l' [app OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store per sincronizzare le foto con altri dispositivi.

### App OneDrive

[OneDrive](https://onedrive.live.com/) consente di accedere, gestire e condividere foto e video con qualsiasi dispositivo e con qualsiasi utente. Per accedere alle foto e ai video acquisiti in HoloLens, scaricare l' [app OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store in HoloLens. Una volta scaricato, Apri l'app OneDrive e seleziona **Impostazioni**  >  per il**caricamento**della videocamera e accendi il **caricamento della videocamera**.

### Connettersi a un PC

Se HoloLens è in corso l' [aggiornamento di Windows 10 aprile 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) o versione successiva, è possibile connettere HoloLens a un PC Windows 10 usando un cavo USB per sfogliare foto e video nel dispositivo usando MTP (Media Transfer Protocol). È necessario assicurarsi che il dispositivo sia sbloccato per esplorare i file se è stato configurato un PIN o una password nel dispositivo.  

Se è stato abilitato [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), è possibile usarlo per esplorare, recuperare e gestire le foto e i video archiviati nel dispositivo.

## Accedere ai file all'interno di un'app

Se un'applicazione salva i file nel dispositivo, è possibile usare tale applicazione per accedervi.

### Richiesta di file da un'altra app

Un'applicazione può richiedere di salvare un file o aprire un file da un'altra app usando [selezione file](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).

### Cartelle note

HoloLens supporta un numero di [cartelle note](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) che le app possono richiedere l'autorizzazione per l'accesso.

## Visualizzare i file di HoloLens nel PC

Analogamente ad altri dispositivi mobili, connettere HoloLens al PC desktop usando MTP (Media Transfer Protocol) e aprire Esplora file nel PC per accedere alle raccolte di HoloLens per facilitare il trasferimento.

Per visualizzare i file di HoloLens in Esplora file nel PC:

1. Accedere a HoloLens, quindi collegarlo al PC usando il cavo USB fornito con HoloLens.

1. Selezionare **Apri dispositivo per visualizzare i file con Esplora file**oppure aprire Esplora file nel PC e passare al dispositivo.

Per visualizzare le informazioni sul proprio HoloLens, fare clic con il pulsante destro del mouse sul nome del dispositivo in Esplora file nel PC e quindi scegliere **Proprietà**.

> [!NOTE]
> HoloLens (1st Gen) non supporta la connessione a dischi rigidi esterni o schede SD.

## Eseguire la sincronizzazione con il cloud

Per sincronizzare foto e altri file da HoloLens al cloud, installare e configurare OneDrive in HoloLens. Per ottenere OneDrive, cercalo in Microsoft Store in HoloLens.

HoloLens non consente di eseguire il backup di file e dati dell'app, quindi è consigliabile salvare il materiale importante in OneDrive. In questo modo, se reimposti il dispositivo o disinstalli un'app, le tue info verranno backup.
