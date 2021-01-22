---
title: Aggiornare HoloLens
description: Scopri come controllare il numero di build di HoloLens, mantenerti aggiornato con gli aggiornamenti dei dispositivi, partecipare al Programma Insider e eseguire il rollback degli aggiornamenti.
keywords: procedura, aggiornamento, rollback, HoloLens, controllare la compilazione, numero di build
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283937"
---
# <span data-ttu-id="c8a17-104">Aggiornare HoloLens</span><span class="sxs-lookup"><span data-stu-id="c8a17-104">Update HoloLens</span></span>

<span data-ttu-id="c8a17-105">HoloLens usa Windows Update, proprio come altri dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c8a17-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="c8a17-106">HoloLens scaricherà e installerà automaticamente gli aggiornamenti di sistema ogni volta che viene collegato all'alimentazione e connesso a Internet, anche quando è in standby.</span><span class="sxs-lookup"><span data-stu-id="c8a17-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="c8a17-107">Questo articolo illustra gli strumenti di HoloLens per:</span><span class="sxs-lookup"><span data-stu-id="c8a17-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="c8a17-108">visualizzazione della versione corrente del sistema operativo (numero di build)</span><span class="sxs-lookup"><span data-stu-id="c8a17-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="c8a17-109">verifica della disponibilità di aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="c8a17-109">checking for updates</span></span>
- <span data-ttu-id="c8a17-110">aggiornamento manuale di HoloLens</span><span class="sxs-lookup"><span data-stu-id="c8a17-110">manually updating HoloLens</span></span>
- <span data-ttu-id="c8a17-111">rollback a un aggiornamento precedente</span><span class="sxs-lookup"><span data-stu-id="c8a17-111">rolling back to an older update</span></span>

## <span data-ttu-id="c8a17-112">Controllare la versione del sistema operativo (numero di build)</span><span class="sxs-lookup"><span data-stu-id="c8a17-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="c8a17-113">Puoi verificare il numero di versione del sistema (numero di build) aprendo l'app Impostazioni e selezionando **Informazioni**  >  **sul sistema.**</span><span class="sxs-lookup"><span data-stu-id="c8a17-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="c8a17-114">Verificare la disponibilità di aggiornamenti e aggiornare manualmente</span><span class="sxs-lookup"><span data-stu-id="c8a17-114">Check for updates and manually update</span></span>

<span data-ttu-id="c8a17-115">Puoi verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c8a17-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="c8a17-116">Per visualizzare gli aggiornamenti disponibili e verificare la disponibilità di nuovi aggiornamenti:</span><span class="sxs-lookup"><span data-stu-id="c8a17-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="c8a17-117">Apri **l'app** Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c8a17-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="c8a17-118">Passare a **Aggiornamento & Sicurezza di**Windows  >  **Update.**</span><span class="sxs-lookup"><span data-stu-id="c8a17-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="c8a17-119">Selezionare **Verifica disponibilità aggiornamenti.**</span><span class="sxs-lookup"><span data-stu-id="c8a17-119">Select **Check for updates**.</span></span>

<span data-ttu-id="c8a17-120">Se è disponibile un aggiornamento, inizierà a scaricare la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="c8a17-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="c8a17-121">Al termine del download, selezionare **il** pulsante Riavvia ora per attivare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="c8a17-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="c8a17-122">Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c8a17-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="c8a17-123">Durante l'installazione dell'aggiornamento, HoloLens visualizza ingranaggi rotanti e un indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="c8a17-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="c8a17-124">Non disattivare HoloLens durante questo periodo.</span><span class="sxs-lookup"><span data-stu-id="c8a17-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="c8a17-125">Verrà riavviato automaticamente una volta completata l'installazione.</span><span class="sxs-lookup"><span data-stu-id="c8a17-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="c8a17-126">HoloLens applica un aggiornamento alla volta.</span><span class="sxs-lookup"><span data-stu-id="c8a17-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="c8a17-127">Se holoLens è più di una versione rispetto alla versione più recente, potrebbe essere necessario eseguire il processo di aggiornamento più volte per aggiornarlo completamente.</span><span class="sxs-lookup"><span data-stu-id="c8a17-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="c8a17-128">Tornare a una versione precedente - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c8a17-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="c8a17-129">In alcuni casi, potresti voler tornare a una versione precedente del software di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c8a17-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="c8a17-130">A tale scopo, puoi usare Advanced Recovery Companion per ripristinare holoLens alla versione precedente.</span><span class="sxs-lookup"><span data-stu-id="c8a17-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="c8a17-131">Tornando a una versione precedente, vengono eliminati i file e le impostazioni personali.</span><span class="sxs-lookup"><span data-stu-id="c8a17-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="c8a17-132">Per tornare una versione precedente di HoloLens 2, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="c8a17-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="c8a17-133">Assicurati di non avere telefoni o dispositivi Windows collegati al PC.</span><span class="sxs-lookup"><span data-stu-id="c8a17-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="c8a17-134">Nel PC scarica [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="c8a17-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="c8a17-135">Scarica la [versione più recente di HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="c8a17-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="c8a17-136">Al termine di questi download, apri **Download di Esplora**  >  **file.**</span><span class="sxs-lookup"><span data-stu-id="c8a17-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="c8a17-137">Fai clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e seleziona **Estrai tutto** > **Estratti** per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="c8a17-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="c8a17-138">Connetti HoloLens al PC usando un cavo USB-A-USB-C.</span><span class="sxs-lookup"><span data-stu-id="c8a17-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="c8a17-139">Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="c8a17-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="c8a17-140">Advanced Recovery Companion rileva automaticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c8a17-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="c8a17-141">Seleziona il riquadro **Microsoft HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="c8a17-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="c8a17-142">Nella schermata successiva, selezionare Selezione manuale del **pacchetto** e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="c8a17-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="c8a17-143">Cercare un file con estensione ffu.</span><span class="sxs-lookup"><span data-stu-id="c8a17-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="c8a17-144">Selezionare **Installa software**e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8a17-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="c8a17-145">Tornare a una versione precedente - HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="c8a17-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="c8a17-146">In alcuni casi, potresti voler tornare a una versione precedente del software di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c8a17-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="c8a17-147">A tale scopo, puoi usare lo strumento ripristino dispositivi di Windows per ripristinare holoLens alla versione precedente.</span><span class="sxs-lookup"><span data-stu-id="c8a17-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="c8a17-148">Tornando a una versione precedente, vengono eliminati i file e le impostazioni personali.</span><span class="sxs-lookup"><span data-stu-id="c8a17-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="c8a17-149">Per tornare a una versione precedente di HoloLens 1, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="c8a17-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="c8a17-150">Assicurati di non avere telefoni o dispositivi Windows collegati al PC.</span><span class="sxs-lookup"><span data-stu-id="c8a17-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="c8a17-151">Scarica Windows Device [Recovery Tool (WDRT) nel](https://support.microsoft.com/help/12379)PC.</span><span class="sxs-lookup"><span data-stu-id="c8a17-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="c8a17-152">Scarica il pacchetto [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="c8a17-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="c8a17-153">Al termine dei download, apri **Download di Esplora**  >  **file.**</span><span class="sxs-lookup"><span data-stu-id="c8a17-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="c8a17-154">Fai clic con il pulsante destro del \*\*\*\* mouse sulla cartella compressa appena scaricata e scegli  >  **Estrai** tutto per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="c8a17-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="c8a17-155">Connetti HoloLens al PC usando il cavo micro USB con cui è stato fornito.</span><span class="sxs-lookup"><span data-stu-id="c8a17-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="c8a17-156">Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="c8a17-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="c8a17-157">WdRT rileverà automaticamente holoLens.</span><span class="sxs-lookup"><span data-stu-id="c8a17-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="c8a17-158">Seleziona il riquadro **Microsoft HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="c8a17-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="c8a17-159">Nella schermata successiva, selezionare Selezione manuale del **pacchetto** e scegliere il file di installazione contenuto nella cartella decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="c8a17-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="c8a17-160">Cercare un file con estensione ffu.</span><span class="sxs-lookup"><span data-stu-id="c8a17-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="c8a17-161">Selezionare **Installa software**e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8a17-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="c8a17-162">Se WDRT non rileva HoloLens, prova a riavviare il PC.</span><span class="sxs-lookup"><span data-stu-id="c8a17-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="c8a17-163">Se il rilevamento non funziona, seleziona **Il mio dispositivo non è stato rilevato**, seleziona poi **Microsoft HoloLens**, e segui le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8a17-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="c8a17-164">Programma Windows Insider in HoloLens</span><span class="sxs-lookup"><span data-stu-id="c8a17-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="c8a17-165">Vuoi vedere le funzionalità più recenti in HoloLens?</span><span class="sxs-lookup"><span data-stu-id="c8a17-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="c8a17-166">In tal caso, partecipa al Programma Windows Insider; si otterrà l'accesso alle build di anteprima degli aggiornamenti software di HoloLens prima che siano disponibili al pubblico.</span><span class="sxs-lookup"><span data-stu-id="c8a17-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="c8a17-167">[Ottenere Windows Insider Preview per Microsoft HoloLens.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="c8a17-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
