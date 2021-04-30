---
title: Aggiornare HoloLens
description: Scopri come controllare il numero di build di HoloLens, rimanere aggiornati con gli aggiornamenti del dispositivo, partecipare al programma Insider ed eseguire il rollback degli aggiornamenti.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309514"
---
# <a name="update-hololens"></a><span data-ttu-id="5098b-104">Aggiornare HoloLens</span><span class="sxs-lookup"><span data-stu-id="5098b-104">Update HoloLens</span></span>

<span data-ttu-id="5098b-105">HoloLens usa Windows Update, proprio come altri Windows 10 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5098b-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="5098b-106">HoloLens scaricherà e installerà automaticamente gli aggiornamenti di sistema ogni volta che è collegato all'alimentazione e connesso a Internet, anche quando è in standby.</span><span class="sxs-lookup"><span data-stu-id="5098b-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="5098b-107">Questo articolo illustra gli strumenti di HoloLens per:</span><span class="sxs-lookup"><span data-stu-id="5098b-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="5098b-108">visualizzazione della versione corrente del sistema operativo (numero di build)</span><span class="sxs-lookup"><span data-stu-id="5098b-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="5098b-109">controllo della disponibilità di aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="5098b-109">checking for updates</span></span>
- <span data-ttu-id="5098b-110">aggiornamento manuale di HoloLens</span><span class="sxs-lookup"><span data-stu-id="5098b-110">manually updating HoloLens</span></span>
- <span data-ttu-id="5098b-111">rollback a un aggiornamento precedente</span><span class="sxs-lookup"><span data-stu-id="5098b-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="5098b-112">Controllare la versione del sistema operativo (numero di build)</span><span class="sxs-lookup"><span data-stu-id="5098b-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="5098b-113">È possibile verificare il numero di versione del sistema (numero di build) aprendo l'app Impostazioni e selezionando **Informazioni**  >  **sul sistema.**</span><span class="sxs-lookup"><span data-stu-id="5098b-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="5098b-114">Verificare la disponibilità di aggiornamenti e aggiornare manualmente</span><span class="sxs-lookup"><span data-stu-id="5098b-114">Check for updates and manually update</span></span>

<span data-ttu-id="5098b-115">È possibile verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5098b-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="5098b-116">Per visualizzare gli aggiornamenti disponibili e verificare la disponibilità di nuovi aggiornamenti:</span><span class="sxs-lookup"><span data-stu-id="5098b-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="5098b-117">Aprire l'app **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="5098b-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="5098b-118">Passare a **Aggiorna & sicurezza**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="5098b-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="5098b-119">Selezionare **Verifica disponibilità aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="5098b-119">Select **Check for updates**.</span></span>

<span data-ttu-id="5098b-120">Se è disponibile un aggiornamento, verrà avviato il download della nuova versione.</span><span class="sxs-lookup"><span data-stu-id="5098b-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="5098b-121">Al termine del download, selezionare il pulsante **Riavvia ora** per attivare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5098b-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="5098b-122">Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5098b-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="5098b-123">Durante l'installazione dell'aggiornamento, HoloLens visualizza ingranaggi rotanti e un indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="5098b-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="5098b-124">Non disattivare HoloLens durante questo periodo.</span><span class="sxs-lookup"><span data-stu-id="5098b-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="5098b-125">Verrà riavviato automaticamente al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="5098b-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="5098b-126">HoloLens applica un aggiornamento alla volta.</span><span class="sxs-lookup"><span data-stu-id="5098b-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="5098b-127">Se HoloLens è più di una versione rispetto alla versione più recente, potrebbe essere necessario eseguire più volte il processo di aggiornamento per aggiornarlo completamente.</span><span class="sxs-lookup"><span data-stu-id="5098b-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="5098b-128">Tornare a una versione precedente - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5098b-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="5098b-129">In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5098b-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="5098b-130">È possibile eseguire questa operazione usando Advanced Recovery Companion per reimpostare HoloLens alla versione precedente.</span><span class="sxs-lookup"><span data-stu-id="5098b-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="5098b-131">Tornando a una versione precedente, i file e le impostazioni personali vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="5098b-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="5098b-132">Per tornare a una versione precedente di HoloLens 2, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="5098b-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="5098b-133">Assicurarsi di non avere telefoni o dispositivi Windows collegati al PC.</span><span class="sxs-lookup"><span data-stu-id="5098b-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="5098b-134">Nel PC scaricare [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dal Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="5098b-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="5098b-135">Scaricare la [versione più recente HoloLens 2 .](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="5098b-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="5098b-136">Al termine di questi download, aprire **Esplora file**  >  **Download**.</span><span class="sxs-lookup"><span data-stu-id="5098b-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="5098b-137">Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="5098b-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="5098b-138">Connettere HoloLens al PC usando un cavo DA USB A a USB-C.</span><span class="sxs-lookup"><span data-stu-id="5098b-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="5098b-139">Anche se si usano altri cavi per connettere HoloLens, questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="5098b-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="5098b-140">Advanced Recovery Companion rileva automaticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5098b-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="5098b-141">Selezionare il **Microsoft HoloLens** riquadro.</span><span class="sxs-lookup"><span data-stu-id="5098b-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="5098b-142">Nella schermata successiva selezionare **Selezione** pacchetto manuale e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="5098b-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="5098b-143">Cercare un file con estensione ffu.</span><span class="sxs-lookup"><span data-stu-id="5098b-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="5098b-144">Selezionare **Installa software** e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="5098b-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="5098b-145">Tornare a una versione precedente - HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="5098b-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="5098b-146">In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5098b-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="5098b-147">A tale scopo, puoi usare lo strumento ripristino dispositivi di Windows per ripristinare holoLens alla versione precedente.</span><span class="sxs-lookup"><span data-stu-id="5098b-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="5098b-148">Se si torna a una versione precedente, i file e le impostazioni personali vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="5098b-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="5098b-149">Per tornare a una versione precedente di HoloLens 1, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="5098b-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="5098b-150">Assicurarsi che non siano presenti telefoni o dispositivi Windows collegati al PC.</span><span class="sxs-lookup"><span data-stu-id="5098b-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="5098b-151">Nel PC scaricare Windows [Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="5098b-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="5098b-152">Scaricare il [pacchetto di ripristino dell'aggiornamento dell'anniversario di HoloLens.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="5098b-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="5098b-153">Al termine dei download, aprire **Download di Esplora**  >  **file.**</span><span class="sxs-lookup"><span data-stu-id="5098b-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="5098b-154">Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="5098b-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="5098b-155">Connetti HoloLens al PC usando il cavo micro USB fornito.</span><span class="sxs-lookup"><span data-stu-id="5098b-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="5098b-156">Anche se hai già utilizzato altri cavi per connettere HoloLens, questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="5098b-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="5098b-157">WdRT rileverà automaticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5098b-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="5098b-158">Selezionare il **Microsoft HoloLens** riquadro.</span><span class="sxs-lookup"><span data-stu-id="5098b-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="5098b-159">Nella schermata successiva selezionare Selezione manuale **del pacchetto** e scegliere il file di installazione contenuto nella cartella decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="5098b-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="5098b-160">Cercare un file con estensione ffu.</span><span class="sxs-lookup"><span data-stu-id="5098b-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="5098b-161">Selezionare **Installa software** e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="5098b-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="5098b-162">Se WDRT non rileva HoloLens, prova a riavviare il PC.</span><span class="sxs-lookup"><span data-stu-id="5098b-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="5098b-163">Se non funziona, selezionare **Il** dispositivo non è stato rilevato, selezionare Microsoft HoloLens **e** quindi seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="5098b-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="5098b-164">Programma Windows Insider su HoloLens</span><span class="sxs-lookup"><span data-stu-id="5098b-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="5098b-165">Per visualizzare le funzionalità più recenti in HoloLens,</span><span class="sxs-lookup"><span data-stu-id="5098b-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="5098b-166">In tal caso, aggiungere il Programma Windows Insider; Si otterrà l'accesso alle build di anteprima degli aggiornamenti software HoloLens prima che siano disponibili per il pubblico generale.</span><span class="sxs-lookup"><span data-stu-id="5098b-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="5098b-167">[Ottenere partecipante al Programma Windows Insider anteprima per Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="5098b-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
