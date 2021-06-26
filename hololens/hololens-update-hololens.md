---
title: Aggiornare HoloLens 2
description: Informazioni su come controllare il numero di build di HoloLens, mantenersi aggiornati con gli aggiornamenti del dispositivo, partecipare al programma Insiders ed eseguire il rollback degli aggiornamenti.
keywords: procedura, aggiornamento, rollback, HoloLens, controllo della compilazione, numero di build
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924112"
---
# <a name="update-hololens-2"></a><span data-ttu-id="d9ae1-104">Aggiornare HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d9ae1-104">Update HoloLens 2</span></span>

<span data-ttu-id="d9ae1-105">HoloLens usa Windows Update, proprio come altri Windows 10 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="d9ae1-106">HoloLens scarica e installa automaticamente gli aggiornamenti di sistema ogni volta che è collegato all'alimentazione e connesso a Internet, anche quando è in standby.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="d9ae1-107">Questo articolo illustra gli strumenti di HoloLens per:</span><span class="sxs-lookup"><span data-stu-id="d9ae1-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="d9ae1-108">visualizzazione della versione corrente del sistema operativo (numero di build)</span><span class="sxs-lookup"><span data-stu-id="d9ae1-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="d9ae1-109">controllo della disponibilità di aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="d9ae1-109">checking for updates</span></span>
- <span data-ttu-id="d9ae1-110">aggiornamento manuale di HoloLens</span><span class="sxs-lookup"><span data-stu-id="d9ae1-110">manually updating HoloLens</span></span>
- <span data-ttu-id="d9ae1-111">rollback a un aggiornamento precedente</span><span class="sxs-lookup"><span data-stu-id="d9ae1-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="d9ae1-112">Controllare la versione del sistema operativo (numero di build)</span><span class="sxs-lookup"><span data-stu-id="d9ae1-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="d9ae1-113">È possibile verificare il numero di versione del sistema (numero di build) aprendo l'app Impostazioni e selezionando **Informazioni**  >  **sul sistema.**</span><span class="sxs-lookup"><span data-stu-id="d9ae1-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="d9ae1-114">Verificare la disponibilità di aggiornamenti e aggiornare manualmente</span><span class="sxs-lookup"><span data-stu-id="d9ae1-114">Check for updates and manually update</span></span>

<span data-ttu-id="d9ae1-115">È possibile verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="d9ae1-116">Per visualizzare gli aggiornamenti disponibili e verificare la presenza di nuovi aggiornamenti:</span><span class="sxs-lookup"><span data-stu-id="d9ae1-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="d9ae1-117">Aprire l'app **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="d9ae1-118">Passare a **Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="d9ae1-119">Selezionare **Verifica disponibilità aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-119">Select **Check for updates**.</span></span>

<span data-ttu-id="d9ae1-120">Se è disponibile un aggiornamento, inizierà a scaricare la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="d9ae1-121">Al termine del download, selezionare il pulsante **Riavvia** ora per attivare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="d9ae1-122">Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="d9ae1-123">Durante l'installazione dell'aggiornamento, HoloLens visualizza ingranaggi rotanti e un indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="d9ae1-124">Non disattivare HoloLens durante questo periodo.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="d9ae1-125">Verrà riavviato automaticamente al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="d9ae1-126">HoloLens applica un aggiornamento alla volta.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="d9ae1-127">Se HoloLens è più di una versione rispetto alla versione più recente, potrebbe essere necessario eseguire più volte il processo di aggiornamento per aggiornarlo completamente.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="d9ae1-128">Tornare a una versione precedente</span><span class="sxs-lookup"><span data-stu-id="d9ae1-128">Go back to a previous version</span></span>

<span data-ttu-id="d9ae1-129">In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="d9ae1-130">I passaggi consigliati sono:</span><span class="sxs-lookup"><span data-stu-id="d9ae1-130">The recommended steps are:</span></span>

1. <span data-ttu-id="d9ae1-131">Contattare il supporto tecnico per verificare se è possibile risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="d9ae1-132">Assicurarsi che **i dati di** **telemetria** facoltativi o completi siano abilitati, in modo da rendere il bug più gestibile e più semplice da diagnosticare per i tecnici.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="d9ae1-133">[Il feedback dei](hololens-feedback.md) file è il più descrittivo possibile.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="d9ae1-134">Prendere nota del titolo o usare la funzionalità di condivisione per condividere il bug con il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="d9ae1-135">Contattare [il supporto](https://aka.ms/hlsupport)tecnico .</span><span class="sxs-lookup"><span data-stu-id="d9ae1-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="d9ae1-136">Se il problema è quello che deve essere risolto tornando a una versione precedente, possono fornire l'FFU per eseguire il flashing del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="d9ae1-137">Se non funziona, reimpostare o convertire il HoloLens 2 [con Advanced Recovery Companion.](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="d9ae1-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="d9ae1-138">Nel PC scaricare [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dal Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="d9ae1-139">Assicurarsi di non avere telefoni o dispositivi Windows collegati al PC.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="d9ae1-140">Scegliere la versione in cui si vuole eseguire il flash:</span><span class="sxs-lookup"><span data-stu-id="d9ae1-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="d9ae1-141">È possibile scaricare la [versione più recente HoloLens 2 versione](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="d9ae1-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="d9ae1-142">È possibile usare la compilazione predefinita ospitata da ARC.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="d9ae1-143">Se si sceglie questa opzione, ignorare il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="d9ae1-144">È possibile usare un supporto di compilazione fornito con .</span><span class="sxs-lookup"><span data-stu-id="d9ae1-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="d9ae1-145">Al termine di questi download, **aprire** Esplora file  >  **Download**.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="d9ae1-146">Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="d9ae1-147">Connettere HoloLens al PC usando un cavo DA USB A a USB-C.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="d9ae1-148">Anche se si usano altri cavi per connettere HoloLens, questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="d9ae1-149">Advanced Recovery Companion rileva automaticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="d9ae1-150">Selezionare il **Microsoft HoloLens** riquadro.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="d9ae1-151">Nella schermata successiva selezionare **Selezione** pacchetto manuale e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="d9ae1-152">Cercare un file con estensione ffu.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="d9ae1-153">Selezionare **Installa software** e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="d9ae1-154">Tornando a una versione precedente, i file e le impostazioni personali vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="d9ae1-155">Inoltre, se si vuole rimanere nella versione attualmente installata, è anche possibile sospendere manualmente [gli aggiornamenti](hololens-updates.md#pause-updates-via-device).</span><span class="sxs-lookup"><span data-stu-id="d9ae1-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="d9ae1-156">In questo modo il team di progettazione avrà il tempo di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="d9ae1-157">Programma Windows Insider su HoloLens</span><span class="sxs-lookup"><span data-stu-id="d9ae1-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="d9ae1-158">Per visualizzare le funzionalità più recenti in HoloLens,</span><span class="sxs-lookup"><span data-stu-id="d9ae1-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="d9ae1-159">In tal caso, aggiungere il Programma Windows Insider; Si otterrà l'accesso alle build di anteprima degli aggiornamenti software HoloLens prima che siano disponibili per il pubblico generale.</span><span class="sxs-lookup"><span data-stu-id="d9ae1-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="d9ae1-160">[Ottenere partecipante al Programma Windows Insider anteprima per Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="d9ae1-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
