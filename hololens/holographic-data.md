---
title: Trovare e salvare file in HoloLens
description: Usare Esplora file in HoloLens per visualizzare e gestire i file nel dispositivo
keywords: hololens
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
ms.openlocfilehash: 50a13e1634344bea66bb6b7ce90d9e3fc8c2a783
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828560"
---
# <span data-ttu-id="57f4a-104">Trovare, aprire e salvare file in HoloLens</span><span class="sxs-lookup"><span data-stu-id="57f4a-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="57f4a-105">I file creati in HoloLens, incluse le foto e i video, vengono salvati direttamente nel dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="57f4a-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="57f4a-106">Visualizzare e gestire le stesse modalità di gestione dei file in Windows 10:</span><span class="sxs-lookup"><span data-stu-id="57f4a-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="57f4a-107">Uso dell'app Esplora file per accedere alle cartelle locali.</span><span class="sxs-lookup"><span data-stu-id="57f4a-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="57f4a-108">All'interno dello spazio di archiviazione di un'app.</span><span class="sxs-lookup"><span data-stu-id="57f4a-108">Within an app's storage.</span></span>
- <span data-ttu-id="57f4a-109">In una cartella speciale, ad esempio il video o la raccolta di musica.</span><span class="sxs-lookup"><span data-stu-id="57f4a-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="57f4a-110">Uso di un servizio di archiviazione che include un'app e una selezione file (ad esempio OneDrive).</span><span class="sxs-lookup"><span data-stu-id="57f4a-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="57f4a-111">Usare un PC desktop collegato al proprio HoloLens usando un cavo USB usando il supporto MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="57f4a-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="57f4a-112">Visualizzare i file in HoloLens usando Esplora file</span><span class="sxs-lookup"><span data-stu-id="57f4a-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="57f4a-113">Si applica a tutti i dispositivi HoloLens 2 e HoloLens (1a generazione) dell' [aggiornamento di Windows 10 aprile 2018 (RS4) per HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="57f4a-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="57f4a-114">Usare Esplora file in HoloLens per visualizzare e gestire i file nel dispositivo, inclusi oggetti 3D, documenti e immagini.</span><span class="sxs-lookup"><span data-stu-id="57f4a-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="57f4a-115">Vai a **avviare**   >  **tutte le app**   >  **file Explorer** per iniziare.</span><span class="sxs-lookup"><span data-stu-id="57f4a-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="57f4a-116">Se non sono presenti file in Esplora file, selezionare **questo dispositivo** nel riquadro in alto a sinistra.</span><span class="sxs-lookup"><span data-stu-id="57f4a-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="57f4a-117">Se non sono presenti file in Esplora file, il filtro "recenti" potrebbe essere attivo (l'icona dell'orologio viene evidenziata nel riquadro sinistro).</span><span class="sxs-lookup"><span data-stu-id="57f4a-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="57f4a-118">Per risolvere questo problema, selezionare l'icona del documento di **questo dispositivo** nel riquadro sinistro (sotto l'icona dell'orologio) oppure aprire il menu e selezionare **questo dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="57f4a-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="57f4a-119">Trovare e visualizzare le foto e i video</span><span class="sxs-lookup"><span data-stu-id="57f4a-119">Find and view your photos and videos</span></span>

<span data-ttu-id="57f4a-120">L' [acquisizione di realtà mista](holographic-photos-and-videos.md) consente di scattare foto e video di realtà mista in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="57f4a-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="57f4a-121">Queste foto e video vengono salvati nella cartella del rotolo della fotocamera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="57f4a-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="57f4a-122">È possibile accedere a foto e video scattate con HoloLens da:</span><span class="sxs-lookup"><span data-stu-id="57f4a-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="57f4a-123">accesso al rotolo della videocamera direttamente nell' [app Foto](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="57f4a-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="57f4a-124">caricamento di foto e video nello spazio di archiviazione nel cloud sincronizzando le foto e i video in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="57f4a-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="57f4a-125">uso della pagina di acquisizione di realtà mista di [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="57f4a-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="57f4a-126">App Foto</span><span class="sxs-lookup"><span data-stu-id="57f4a-126">Photos app</span></span>

<span data-ttu-id="57f4a-127">L'app foto è una delle app predefinite nel menu **Start** e viene incorporata con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="57f4a-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="57f4a-128">Leggi altre informazioni sull' [uso dell'app Foto per visualizzare il contenuto](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="57f4a-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="57f4a-129">È anche possibile installare l' [app OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store per sincronizzare le foto con altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="57f4a-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="57f4a-130">App OneDrive</span><span class="sxs-lookup"><span data-stu-id="57f4a-130">OneDrive app</span></span>

<span data-ttu-id="57f4a-131">[OneDrive](https://onedrive.live.com/) consente di accedere, gestire e condividere foto e video con qualsiasi dispositivo e con qualsiasi utente.</span><span class="sxs-lookup"><span data-stu-id="57f4a-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="57f4a-132">Per accedere alle foto e ai video acquisiti in HoloLens, scaricare l' [app OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="57f4a-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="57f4a-133">Una volta scaricato, Apri l'app OneDrive e seleziona **Impostazioni**  >  per il**caricamento**della videocamera e accendi il **caricamento della videocamera**.</span><span class="sxs-lookup"><span data-stu-id="57f4a-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="57f4a-134">Connettersi a un PC</span><span class="sxs-lookup"><span data-stu-id="57f4a-134">Connect to a PC</span></span>

<span data-ttu-id="57f4a-135">Se HoloLens è in corso l' [aggiornamento di Windows 10 aprile 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) o versione successiva, è possibile connettere HoloLens a un PC Windows 10 usando un cavo USB per sfogliare foto e video nel dispositivo usando MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="57f4a-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="57f4a-136">È necessario assicurarsi che il dispositivo sia sbloccato per esplorare i file se è stato configurato un PIN o una password nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="57f4a-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="57f4a-137">Se è stato abilitato [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), è possibile usarlo per esplorare, recuperare e gestire le foto e i video archiviati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="57f4a-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="57f4a-138">Accedere ai file all'interno di un'app</span><span class="sxs-lookup"><span data-stu-id="57f4a-138">Access files within an app</span></span>

<span data-ttu-id="57f4a-139">Se un'applicazione salva i file nel dispositivo, è possibile usare tale applicazione per accedervi.</span><span class="sxs-lookup"><span data-stu-id="57f4a-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="57f4a-140">Richiesta di file da un'altra app</span><span class="sxs-lookup"><span data-stu-id="57f4a-140">Requesting files from another app</span></span>

<span data-ttu-id="57f4a-141">Un'applicazione può richiedere di salvare un file o aprire un file da un'altra app usando [selezione file](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="57f4a-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="57f4a-142">Cartelle note</span><span class="sxs-lookup"><span data-stu-id="57f4a-142">Known folders</span></span>

<span data-ttu-id="57f4a-143">HoloLens supporta un numero di [cartelle note](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) che le app possono richiedere l'autorizzazione per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="57f4a-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="57f4a-144">Visualizzare i file di HoloLens nel PC</span><span class="sxs-lookup"><span data-stu-id="57f4a-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="57f4a-145">Analogamente ad altri dispositivi mobili, connettere HoloLens al PC desktop usando MTP (Media Transfer Protocol) e aprire Esplora file nel PC per accedere alle raccolte di HoloLens per facilitare il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="57f4a-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="57f4a-146">Per visualizzare i file di HoloLens in Esplora file nel PC:</span><span class="sxs-lookup"><span data-stu-id="57f4a-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="57f4a-147">Accedere a HoloLens, quindi collegarlo al PC usando il cavo USB fornito con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="57f4a-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="57f4a-148">Selezionare **Apri dispositivo per visualizzare i file con Esplora file**oppure aprire Esplora file nel PC e passare al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="57f4a-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="57f4a-149">Per visualizzare le informazioni sul proprio HoloLens, fare clic con il pulsante destro del mouse sul nome del dispositivo in Esplora file nel PC e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="57f4a-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="57f4a-150">HoloLens (1st Gen) non supporta la connessione a dischi rigidi esterni o schede SD.</span><span class="sxs-lookup"><span data-stu-id="57f4a-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="57f4a-151">Eseguire la sincronizzazione con il cloud</span><span class="sxs-lookup"><span data-stu-id="57f4a-151">Sync to the cloud</span></span>

<span data-ttu-id="57f4a-152">Per sincronizzare foto e altri file da HoloLens al cloud, installare e configurare OneDrive in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="57f4a-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="57f4a-153">Per ottenere OneDrive, cercalo in Microsoft Store in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="57f4a-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="57f4a-154">HoloLens non consente di eseguire il backup di file e dati dell'app, quindi è consigliabile salvare il materiale importante in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="57f4a-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="57f4a-155">In questo modo, se reimposti il dispositivo o disinstalli un'app, le tue info verranno backup.</span><span class="sxs-lookup"><span data-stu-id="57f4a-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
