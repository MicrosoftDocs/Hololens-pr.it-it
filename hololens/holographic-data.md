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
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636181"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="4558d-104">Trovare, aprire e salvare file in HoloLens</span><span class="sxs-lookup"><span data-stu-id="4558d-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="4558d-105">I file creati in HoloLens, inclusi foto e video, vengono salvati direttamente nel HoloLens dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4558d-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="4558d-106">È possibile visualizzarli e gestirli nello stesso modo in cui si gestiscono i file Windows 10:</span><span class="sxs-lookup"><span data-stu-id="4558d-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="4558d-107">Uso dell'Esplora file app per accedere alle cartelle locali.</span><span class="sxs-lookup"><span data-stu-id="4558d-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="4558d-108">All'interno dello spazio di archiviazione di un'app.</span><span class="sxs-lookup"><span data-stu-id="4558d-108">Within an app's storage.</span></span>
- <span data-ttu-id="4558d-109">In una cartella speciale, ad esempio il video o la raccolta musicale.</span><span class="sxs-lookup"><span data-stu-id="4558d-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="4558d-110">Uso di un servizio di archiviazione che include un'app e una selezione file, ad esempio OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4558d-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="4558d-111">Usando un PC desktop connesso al HoloLens tramite un cavo USB, usando il supporto MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="4558d-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="4558d-112">Visualizzare i file HoloLens usando Esplora file</span><span class="sxs-lookup"><span data-stu-id="4558d-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="4558d-113">Si applica a tutti HoloLens 2 e HoloLens (prima generazione) a partire dall'aggiornamento di Windows 10 aprile [2018 (RS4) per HoloLens](/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="4558d-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="4558d-114">Usare Esplora file in HoloLens visualizzare e gestire i file nel dispositivo, inclusi oggetti 3D, documenti e immagini.</span><span class="sxs-lookup"><span data-stu-id="4558d-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="4558d-115">Passare a **Start**   >  **All apps**   >  **(Avvia tutte Esplora file** app) per iniziare.</span><span class="sxs-lookup"><span data-stu-id="4558d-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="4558d-116">Se non sono elencati file in Esplora file, selezionare **Questo dispositivo** nel riquadro in alto a sinistra.</span><span class="sxs-lookup"><span data-stu-id="4558d-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="4558d-117">Se non viene visualizzato alcun file in Esplora file, il filtro "Recenti" potrebbe essere attivo (l'icona a forma di orologio è evidenziata nel riquadro sinistro).</span><span class="sxs-lookup"><span data-stu-id="4558d-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="4558d-118">Per risolvere il problema, selezionare l'icona del documento This **Device** (Questo dispositivo) nel riquadro sinistro (sotto l'icona dell'orologio) oppure aprire il menu e selezionare **This Device (Questo dispositivo).**</span><span class="sxs-lookup"><span data-stu-id="4558d-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="4558d-119">Trovare e visualizzare foto e video</span><span class="sxs-lookup"><span data-stu-id="4558d-119">Find and view your photos and videos</span></span>

<span data-ttu-id="4558d-120">[L'acquisizione di realtà](holographic-photos-and-videos.md) mista consente di scattare foto e video di realtà mista HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4558d-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="4558d-121">Queste foto e video vengono salvati nella cartella Camera Roll del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4558d-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="4558d-122">È possibile accedere a foto e video scattati con HoloLens da:</span><span class="sxs-lookup"><span data-stu-id="4558d-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="4558d-123">accedendo al rullo della fotocamera direttamente tramite [l Foto app](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="4558d-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="4558d-124">caricamento di foto e video nell'archiviazione cloud tramite la sincronizzazione di foto e video OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4558d-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="4558d-125">usando la Acquisizione realtà mista pagina del [Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="4558d-125">using the Mixed Reality Capture page of the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="4558d-126">App Foto</span><span class="sxs-lookup"><span data-stu-id="4558d-126">Photos app</span></span>

<span data-ttu-id="4558d-127">L Foto app è una delle app predefinite nel menu **Start** ed è incorporata con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4558d-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="4558d-128">Altre informazioni [sull'uso dell'app Foto per visualizzare il contenuto.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="4558d-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="4558d-129">È anche possibile installare [l'app OneDrive dal Microsoft Store](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) per sincronizzare le foto con altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4558d-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="4558d-130">OneDrive app</span><span class="sxs-lookup"><span data-stu-id="4558d-130">OneDrive app</span></span>

<span data-ttu-id="4558d-131">[OneDrive](https://onedrive.live.com/) consente di accedere, gestire e condividere foto e video con qualsiasi dispositivo e con qualsiasi utente.</span><span class="sxs-lookup"><span data-stu-id="4558d-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="4558d-132">Per accedere alle foto e ai video acquisiti HoloLens, scaricare [l'app OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) dal Microsoft Store nel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4558d-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="4558d-133">Dopo il download, aprire l'app OneDrive, **selezionare** Impostazioni Caricamento della  >  **fotocamera** e attivare Caricamento **della fotocamera.**</span><span class="sxs-lookup"><span data-stu-id="4558d-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="4558d-134">Connessione a un PC</span><span class="sxs-lookup"><span data-stu-id="4558d-134">Connect to a PC</span></span>

<span data-ttu-id="4558d-135">Se il HoloLens esegue l'aggiornamento di Windows 10 aprile [2018](/windows/mixed-reality/release-notes-april-2018) o versione successiva, è possibile connettere il HoloLens a un PC Windows 10 usando un cavo USB per esplorare foto e video nel dispositivo usando MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="4558d-135">If your HoloLens is running the [Windows 10 April 2018 update](/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="4558d-136">Se nel dispositivo è configurato un PIN o una password, è necessario assicurarsi che il dispositivo sia sbloccato per esplorare i file.</span><span class="sxs-lookup"><span data-stu-id="4558d-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="4558d-137">Se è stato abilitato [il Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal), è possibile usarlo per esplorare, recuperare e gestire le foto e i video archiviati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4558d-137">If you have enabled the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="4558d-138">Accedere ai file all'interno di un'app</span><span class="sxs-lookup"><span data-stu-id="4558d-138">Access files within an app</span></span>

<span data-ttu-id="4558d-139">Se un'applicazione salva i file nel dispositivo, è possibile usarla per accedervi.</span><span class="sxs-lookup"><span data-stu-id="4558d-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="4558d-140">Richiesta di file da un'altra app</span><span class="sxs-lookup"><span data-stu-id="4558d-140">Requesting files from another app</span></span>

<span data-ttu-id="4558d-141">Un'applicazione può richiedere di salvare un file o aprire un file da un'altra app usando [le selettori di file](/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="4558d-141">An application can request to save a file or open a file from another app by using [file pickers](/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="4558d-142">Cartelle note</span><span class="sxs-lookup"><span data-stu-id="4558d-142">Known folders</span></span>

<span data-ttu-id="4558d-143">HoloLens supporta una serie di cartelle note a [cui le](/windows/mixed-reality/app-model#known-folders) app possono richiedere l'autorizzazione di accesso.</span><span class="sxs-lookup"><span data-stu-id="4558d-143">HoloLens supports a number of [known folders](/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="4558d-144">Visualizzare HoloLens file nel PC</span><span class="sxs-lookup"><span data-stu-id="4558d-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="4558d-145">Analogamente ad altri dispositivi mobili, connettersi HoloLens al PC desktop usando MTP (Media Transfer Protocol) e aprire Esplora file nel PC per accedere alle librerie HoloLens per facilitarlo.</span><span class="sxs-lookup"><span data-stu-id="4558d-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="4558d-146">Per visualizzare i file HoloLens in Esplora file nel PC:</span><span class="sxs-lookup"><span data-stu-id="4558d-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="4558d-147">Accedere al HoloLens, quindi collegarlo al PC usando il cavo USB fornito con il HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4558d-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="4558d-148">Selezionare **Apri dispositivo per visualizzare i file Esplora file** o aprire Esplora file nel PC e passare al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4558d-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="4558d-149">Per visualizzare informazioni sull'HoloLens, fare clic con il pulsante destro del mouse sul nome del Esplora file nel PC e quindi **scegliere Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="4558d-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="4558d-150">HoloLens (prima generazione) non supporta la connessione a dischi rigidi esterni o schede SD.</span><span class="sxs-lookup"><span data-stu-id="4558d-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="4558d-151">Eseguire la sincronizzazione nel cloud</span><span class="sxs-lookup"><span data-stu-id="4558d-151">Sync to the cloud</span></span>

<span data-ttu-id="4558d-152">Per sincronizzare foto e altri file dal HoloLens al cloud, installare e OneDrive in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4558d-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="4558d-153">Per ottenere OneDrive, cercarlo nel Microsoft Store nel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4558d-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="4558d-154">HoloLens non consente di eseguire il backup di file e dati dell'app, quindi è buona idea salvare le informazioni importanti per OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4558d-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="4558d-155">In questo modo, se si reimposta il dispositivo o si disinstalla un'app, verrà eseguito il backup delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="4558d-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
