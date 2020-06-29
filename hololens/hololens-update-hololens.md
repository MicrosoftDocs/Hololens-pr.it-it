---
title: Aggiornare HoloLens
description: Controllare il numero di build, l'aggiornamento e la rollback degli aggiornamenti di HoloLens.
keywords: procedura, aggiornamento, rollback, HoloLens, controllo Build, numero di Build
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828591"
---
# <span data-ttu-id="e91b5-104">Aggiornare HoloLens</span><span class="sxs-lookup"><span data-stu-id="e91b5-104">Update HoloLens</span></span>

<span data-ttu-id="e91b5-105">HoloLens usa Windows Update, proprio come gli altri dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e91b5-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="e91b5-106">Il HoloLens scaricherà e installerà automaticamente gli aggiornamenti di sistema ogni volta che viene collegato a Power e connesso a Internet, anche quando è in standby.</span><span class="sxs-lookup"><span data-stu-id="e91b5-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="e91b5-107">In questo articolo verranno illustrati gli strumenti di HoloLens per:</span><span class="sxs-lookup"><span data-stu-id="e91b5-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="e91b5-108">visualizzazione della versione del sistema operativo corrente (numero di Build)</span><span class="sxs-lookup"><span data-stu-id="e91b5-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="e91b5-109">Verifica della disponibilità di aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="e91b5-109">checking for updates</span></span>
- <span data-ttu-id="e91b5-110">aggiornamento manuale di HoloLens</span><span class="sxs-lookup"><span data-stu-id="e91b5-110">manually updating HoloLens</span></span>
- <span data-ttu-id="e91b5-111">rollback di un aggiornamento precedente</span><span class="sxs-lookup"><span data-stu-id="e91b5-111">rolling back to an older update</span></span>

## <span data-ttu-id="e91b5-112">Verificare la versione del sistema operativo (numero di Build)</span><span class="sxs-lookup"><span data-stu-id="e91b5-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="e91b5-113">Puoi verificare il numero di versione del sistema (numero di Build) aprendo l'app Impostazioni e selezionando **System**  >  **About**.</span><span class="sxs-lookup"><span data-stu-id="e91b5-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="e91b5-114">Verificare la disponibilità di aggiornamenti e aggiornare manualmente</span><span class="sxs-lookup"><span data-stu-id="e91b5-114">Check for updates and manually update</span></span>

<span data-ttu-id="e91b5-115">Puoi verificare la disponibilità di aggiornamenti in qualsiasi momento in impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e91b5-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="e91b5-116">Per visualizzare gli aggiornamenti disponibili e verificare la disponibilità di nuovi aggiornamenti:</span><span class="sxs-lookup"><span data-stu-id="e91b5-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="e91b5-117">Aprire l'app **Impostazioni** .</span><span class="sxs-lookup"><span data-stu-id="e91b5-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="e91b5-118">Passare alla pagina **Update & Security**  >  **Update di Windows**.</span><span class="sxs-lookup"><span data-stu-id="e91b5-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="e91b5-119">Selezionare **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="e91b5-119">Select **Check for updates**.</span></span>

<span data-ttu-id="e91b5-120">Se è disponibile un aggiornamento, inizierà a scaricare la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="e91b5-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="e91b5-121">Al termine del download, selezionare il pulsante **Riavvia ora** per attivare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="e91b5-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="e91b5-122">Se il dispositivo è inferiore a 40% e non è collegato, il riavvio non verrà avviato per l'installazione dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e91b5-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="e91b5-123">Durante l'installazione dell'aggiornamento, il HoloLens visualizzerà gli ingranaggi rotanti e un indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="e91b5-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="e91b5-124">Non disattivare il HoloLens durante questo periodo.</span><span class="sxs-lookup"><span data-stu-id="e91b5-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="e91b5-125">Verrà riavviato automaticamente dopo aver completato l'installazione.</span><span class="sxs-lookup"><span data-stu-id="e91b5-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="e91b5-126">HoloLens applica un aggiornamento alla volta.</span><span class="sxs-lookup"><span data-stu-id="e91b5-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="e91b5-127">Se il HoloLens è più di una versione dietro alla più recente, potrebbe essere necessario eseguire più volte il processo di aggiornamento per aggiornarlo completamente.</span><span class="sxs-lookup"><span data-stu-id="e91b5-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="e91b5-128">Tornare a una versione precedente-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e91b5-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="e91b5-129">In alcuni casi, potresti voler tornare a una versione precedente del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e91b5-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="e91b5-130">Puoi eseguire questa operazione usando il compagno di ripristino avanzato per reimpostare il HoloLens alla versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e91b5-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="e91b5-131">Tornando a una versione precedente vengono eliminati i file e le impostazioni personali.</span><span class="sxs-lookup"><span data-stu-id="e91b5-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="e91b5-132">Per tornare a una versione precedente di HoloLens 2, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e91b5-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="e91b5-133">Verificare che non siano presenti telefoni o dispositivi Windows collegati al PC.</span><span class="sxs-lookup"><span data-stu-id="e91b5-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="e91b5-134">Nel PC scaricare il compagno di [Ripristino avanzato](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e91b5-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="e91b5-135">Scaricare la [versione più recente di HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="e91b5-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="e91b5-136">Dopo aver completato questi download, aprire download di **Esplora file**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="e91b5-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="e91b5-137">Fai clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e seleziona **Estrai tutto** > **Estratti** per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="e91b5-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="e91b5-138">Connettere il HoloLens al PC usando un cavo USB-a-USB-C.</span><span class="sxs-lookup"><span data-stu-id="e91b5-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="e91b5-139">Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="e91b5-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="e91b5-140">Il compagno di recupero avanzato rileva automaticamente il HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e91b5-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="e91b5-141">Selezionare il riquadro **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="e91b5-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="e91b5-142">Nella schermata successiva selezionare **Selezione pacchetto manuale** e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="e91b5-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="e91b5-143">Cercare un file con estensione FFU.</span><span class="sxs-lookup"><span data-stu-id="e91b5-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="e91b5-144">Selezionare **Installa software**e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="e91b5-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="e91b5-145">Tornare a una versione precedente-HoloLens (1st Gen)</span><span class="sxs-lookup"><span data-stu-id="e91b5-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="e91b5-146">In alcuni casi, potresti voler tornare a una versione precedente del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e91b5-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="e91b5-147">Puoi eseguire questa operazione usando lo strumento ripristino dispositivi Windows per reimpostare il HoloLens alla versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e91b5-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="e91b5-148">Tornando a una versione precedente vengono eliminati i file e le impostazioni personali.</span><span class="sxs-lookup"><span data-stu-id="e91b5-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="e91b5-149">Per tornare a una versione precedente di HoloLens 1, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e91b5-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="e91b5-150">Verificare che non siano presenti telefoni o dispositivi Windows collegati al PC.</span><span class="sxs-lookup"><span data-stu-id="e91b5-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="e91b5-151">Nel PC scaricare lo [strumento Windows Device Recovery (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="e91b5-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="e91b5-152">Scaricare il [pacchetto di ripristino dell'aggiornamento di HoloLens anniversario](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="e91b5-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="e91b5-153">Al termine del download, aprire download di **Esplora file**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="e91b5-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="e91b5-154">Fai clic con il pulsante destro del mouse sulla cartella zippata appena scaricata e seleziona **Estrai tutti gli**  >  **estratti** per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="e91b5-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="e91b5-155">Connettere il HoloLens al PC usando il cavo micro-USB con cui è stato fornito.</span><span class="sxs-lookup"><span data-stu-id="e91b5-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="e91b5-156">Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="e91b5-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="e91b5-157">WDRT rileverà automaticamente la HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e91b5-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="e91b5-158">Selezionare il riquadro **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="e91b5-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="e91b5-159">Nella schermata successiva selezionare **Selezione pacchetto manuale** e scegliere il file di installazione contenuto nella cartella decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="e91b5-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="e91b5-160">Cercare un file con estensione FFU.</span><span class="sxs-lookup"><span data-stu-id="e91b5-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="e91b5-161">Selezionare **Installa software**e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="e91b5-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="e91b5-162">Se WDRT non rileva il HoloLens, provare a riavviare il PC.</span><span class="sxs-lookup"><span data-stu-id="e91b5-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="e91b5-163">Se non funziona, selezionare il **dispositivo non è stato rilevato**, selezionare **Microsoft HoloLens**e quindi seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="e91b5-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="e91b5-164">Programma Windows insider in HoloLens</span><span class="sxs-lookup"><span data-stu-id="e91b5-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="e91b5-165">Vuoi vedere le caratteristiche più recenti di HoloLens?</span><span class="sxs-lookup"><span data-stu-id="e91b5-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="e91b5-166">In questo caso, partecipa al programma Windows Insider; otterrai l'accesso alle build di anteprima degli aggiornamenti software di HoloLens prima che siano disponibili per il pubblico generale.</span><span class="sxs-lookup"><span data-stu-id="e91b5-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="e91b5-167">[Ottenere Windows Insider Preview per Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="e91b5-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
