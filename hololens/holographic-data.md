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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309186"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="9bf0b-104">Trovare, aprire e salvare file in HoloLens</span><span class="sxs-lookup"><span data-stu-id="9bf0b-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="9bf0b-105">I file creati in HoloLens, inclusi foto e video, vengono salvati direttamente nel dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="9bf0b-106">È possibile visualizzarli e gestirli nello stesso modo in cui si gestiscono i file Windows 10:</span><span class="sxs-lookup"><span data-stu-id="9bf0b-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="9bf0b-107">Uso dell'Esplora file app per accedere alle cartelle locali.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="9bf0b-108">All'interno dello spazio di archiviazione di un'app.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-108">Within an app's storage.</span></span>
- <span data-ttu-id="9bf0b-109">In una cartella speciale, ad esempio il video o la raccolta musicale.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="9bf0b-110">Uso di un servizio di archiviazione che include un'app e una selezione file (ad esempio OneDrive).</span><span class="sxs-lookup"><span data-stu-id="9bf0b-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="9bf0b-111">Uso di un PC desktop connesso a HoloLens tramite un cavo USB, con supporto MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="9bf0b-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="9bf0b-112">Visualizzare i file in HoloLens usando Esplora file</span><span class="sxs-lookup"><span data-stu-id="9bf0b-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="9bf0b-113">Si applica a tutti HoloLens 2 e HoloLens (prima generazione) a Aggiornamento di Windows 10 (aprile 2018) [(RS4) per HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)</span><span class="sxs-lookup"><span data-stu-id="9bf0b-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="9bf0b-114">Usa Esplora file in HoloLens per visualizzare e gestire i file nel dispositivo, inclusi oggetti 3D, documenti e immagini.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="9bf0b-115">Passare a **Start**   >  **All apps**   >  **(Avvia tutte Esplora file** app) per iniziare.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="9bf0b-116">Se non sono elencati file in Esplora file, selezionare **Questo dispositivo** nel riquadro in alto a sinistra.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="9bf0b-117">Se non viene visualizzato alcun file in Esplora file, il filtro "Recenti" potrebbe essere attivo (l'icona a forma di orologio è evidenziata nel riquadro sinistro).</span><span class="sxs-lookup"><span data-stu-id="9bf0b-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="9bf0b-118">Per risolvere il problema, selezionare l'icona del documento This **Device** (Questo dispositivo) nel riquadro sinistro (sotto l'icona dell'orologio) oppure aprire il menu e selezionare **This Device (Questo dispositivo).**</span><span class="sxs-lookup"><span data-stu-id="9bf0b-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="9bf0b-119">Trovare e visualizzare foto e video</span><span class="sxs-lookup"><span data-stu-id="9bf0b-119">Find and view your photos and videos</span></span>

<span data-ttu-id="9bf0b-120">[L'acquisizione di realtà](holographic-photos-and-videos.md) mista consente di scattare foto e video di realtà mista in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="9bf0b-121">Queste foto e questi video vengono salvati nella cartella Rullino del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="9bf0b-122">È possibile accedere a foto e video scattati con HoloLens:</span><span class="sxs-lookup"><span data-stu-id="9bf0b-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="9bf0b-123">accesso al rullino direttamente tramite [l'app Foto.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="9bf0b-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="9bf0b-124">caricamento di foto e video nell'archiviazione cloud sincronizzando foto e video in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="9bf0b-125">usando la Acquisizione realtà mista pagina del [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="9bf0b-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="9bf0b-126">App Foto</span><span class="sxs-lookup"><span data-stu-id="9bf0b-126">Photos app</span></span>

<span data-ttu-id="9bf0b-127">L'app Foto è una delle app predefinite nel menu **Start** ed è integrata con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="9bf0b-128">Altre informazioni [sull'uso dell'app Foto per visualizzare il contenuto.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="9bf0b-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="9bf0b-129">È anche possibile installare [l'app OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) dal Microsoft Store per sincronizzare le foto con altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="9bf0b-130">App OneDrive</span><span class="sxs-lookup"><span data-stu-id="9bf0b-130">OneDrive app</span></span>

<span data-ttu-id="9bf0b-131">[OneDrive](https://onedrive.live.com/) consente di accedere, gestire e condividere foto e video con qualsiasi dispositivo e con qualsiasi utente.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="9bf0b-132">Per accedere alle foto e ai video acquisiti in HoloLens, scaricare [l'app OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) dal Microsoft Store in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="9bf0b-133">Dopo il download, aprire l'app OneDrive e selezionare **Impostazioni**  >  **Caricamento fotocamera** e attivare Caricamento **fotocamera**.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="9bf0b-134">Connettersi a un PC</span><span class="sxs-lookup"><span data-stu-id="9bf0b-134">Connect to a PC</span></span>

<span data-ttu-id="9bf0b-135">Se HoloLens esegue l'aggiornamento di Windows 10 aprile [2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) o versione successiva, è possibile connettere HoloLens a un PC Windows 10 usando un cavo USB per esplorare foto e video nel dispositivo usando MTP (media transfer protocol).</span><span class="sxs-lookup"><span data-stu-id="9bf0b-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="9bf0b-136">È necessario assicurarsi che il dispositivo sia sbloccato per esplorare i file se nel dispositivo è configurato un PIN o una password.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="9bf0b-137">Se è stato abilitato [il Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), è possibile usarlo per esplorare, recuperare e gestire le foto e i video archiviati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="9bf0b-138">Accedere ai file all'interno di un'app</span><span class="sxs-lookup"><span data-stu-id="9bf0b-138">Access files within an app</span></span>

<span data-ttu-id="9bf0b-139">Se un'applicazione salva i file nel dispositivo, è possibile usarla per accedervi.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="9bf0b-140">Richiesta di file da un'altra app</span><span class="sxs-lookup"><span data-stu-id="9bf0b-140">Requesting files from another app</span></span>

<span data-ttu-id="9bf0b-141">Un'applicazione può richiedere di salvare un file o aprire un file da un'altra app usando i [selettori di file](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="9bf0b-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="9bf0b-142">Cartelle note</span><span class="sxs-lookup"><span data-stu-id="9bf0b-142">Known folders</span></span>

<span data-ttu-id="9bf0b-143">HoloLens supporta una serie di cartelle note a cui [le](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) app possono richiedere l'autorizzazione di accesso.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="9bf0b-144">Visualizzare i file HoloLens nel PC</span><span class="sxs-lookup"><span data-stu-id="9bf0b-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="9bf0b-145">Analogamente ad altri dispositivi mobili, connetti HoloLens al PC desktop usando MTP (Media Transfer Protocol) e apri Esplora file nel PC per accedere alle librerie HoloLens per facilitane il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="9bf0b-146">Per visualizzare i file di HoloLens Esplora file nel PC:</span><span class="sxs-lookup"><span data-stu-id="9bf0b-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="9bf0b-147">Accedere a HoloLens e quindi collegarlo al PC usando il cavo USB fornito con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="9bf0b-148">Selezionare **Apri dispositivo per visualizzare i file Esplora file** o aprire Esplora file nel PC e passare al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="9bf0b-149">Per visualizzare informazioni su HoloLens, fai clic con il pulsante destro del mouse sul nome del Esplora file nel PC e quindi **scegli Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="9bf0b-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="9bf0b-150">HoloLens (prima generazione) non supporta la connessione a dischi rigidi esterni o schede SD.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="9bf0b-151">Eseguire la sincronizzazione nel cloud</span><span class="sxs-lookup"><span data-stu-id="9bf0b-151">Sync to the cloud</span></span>

<span data-ttu-id="9bf0b-152">Per sincronizzare foto e altri file da HoloLens al cloud, installare e configurare OneDrive in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="9bf0b-153">Per ottenere OneDrive, cercarlo nel Microsoft Store in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="9bf0b-154">HoloLens non consente di eseguire il backup di file e dati dell'app, quindi è buona idea salvare le informazioni importanti in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="9bf0b-155">In questo modo, se si reimposta il dispositivo o si disinstalla un'app, verrà eseguito il backup delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="9bf0b-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
