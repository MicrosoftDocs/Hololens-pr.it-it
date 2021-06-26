---
title: Riavviare, reimpostare o ripristinare HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Come usare lo strumento ripristino dispositivi di Windows per eseguire il flash di un'immagine in HoloLens di prima generazione.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923517"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="11bb9-104">Riavviare, reimpostare o ripristinare HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="11bb9-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="11bb9-105">Se si verificano problemi con HoloLens, è possibile provare a riavviare o reimpostare il dispositivo o persino a ripristinare il dispositivo usando il ripristino del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="11bb9-106">Questo articolo illustra i passaggi consigliati per il ripristino nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="11bb9-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="11bb9-107">Se si sta cercando di ripristinare un HoloLens 2, vedere [Ripristino](hololens-recovery.md)di un HoloLens 2 , perché il processo è diverso.</span><span class="sxs-lookup"><span data-stu-id="11bb9-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="11bb9-108">Questo articolo è in particolare sul dispositivo e sul software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11bb9-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="11bb9-109">Se l'aspetto degli ologrammi non è quello giusto, vedi Considerazioni sull'ambiente **[HoloLens](hololens-environment-considerations.md)** per informazioni sui fattori che migliorano la qualità degli ologrammi.</span><span class="sxs-lookup"><span data-stu-id="11bb9-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="11bb9-110">Riavvia</span><span class="sxs-lookup"><span data-stu-id="11bb9-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="11bb9-111">Eseguire un riavvio sicuro con Cortana</span><span class="sxs-lookup"><span data-stu-id="11bb9-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="11bb9-112">Il modo più sicuro per riavviare HoloLens è usare Cortana, che in genere è la prima cosa da provare quando si verifica un problema con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11bb9-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="11bb9-113">Cortana non è disponibile in tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="11bb9-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="11bb9-114">Cortana è disponibile in tutti i dispositivi HoloLens (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="11bb9-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="11bb9-115">Cortana è disponibile nei HoloLens 2 nelle build precedenti all'aggiornamento di Windows Holograpic versione 2004.</span><span class="sxs-lookup"><span data-stu-id="11bb9-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="11bb9-116">Attiva HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11bb9-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="11bb9-117">Assicurarsi che un utente sia connesso e che il dispositivo non sia in attesa di una password per sbloccarlo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="11bb9-118">Pronunciare "Hey Cortana, reboot" o "Hey Cortana, restart".</span><span class="sxs-lookup"><span data-stu-id="11bb9-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="11bb9-119">Cortana risponderà e chiederà di confermare.</span><span class="sxs-lookup"><span data-stu-id="11bb9-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="11bb9-120">Attendere la riproduzione di un suono dopo la domanda e quindi pronunciare "Sì".</span><span class="sxs-lookup"><span data-stu-id="11bb9-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="11bb9-121">Il dispositivo verrà riavviato.</span><span class="sxs-lookup"><span data-stu-id="11bb9-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="11bb9-122">Usare il pulsante di alimentazione per eseguire un riavvio sicuro</span><span class="sxs-lookup"><span data-stu-id="11bb9-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="11bb9-123">Se non è ancora possibile riavviare il dispositivo, provare a riavviarlo usando il **pulsante di** alimentazione:</span><span class="sxs-lookup"><span data-stu-id="11bb9-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="11bb9-124">Tenere premuto il **pulsante di** alimentazione per 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="11bb9-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="11bb9-125">Dopo 1 secondo, tutti e cinque i LED si illuminano e quindi si spegne lentamente uno alla volta da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="11bb9-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="11bb9-126">Dopo 5 secondi, tutti i LED saranno spenti, a indicare che l'arresto è riuscito.</span><span class="sxs-lookup"><span data-stu-id="11bb9-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="11bb9-127">Arrestare la pressione del pulsante immediatamente dopo che tutti i LED sono stati disattivati.</span><span class="sxs-lookup"><span data-stu-id="11bb9-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="11bb9-128">Attendere 1 minuto per il completamento dell'arresto.</span><span class="sxs-lookup"><span data-stu-id="11bb9-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="11bb9-129">L'arresto potrebbe essere ancora in corso anche dopo che gli schermi sono stati disattivati.</span><span class="sxs-lookup"><span data-stu-id="11bb9-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="11bb9-130">Accendere di nuovo il dispositivo premendo e tenendo premuto il **pulsante** di alimentazione per 1 secondo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="11bb9-131">Eseguire un riavvio sicuro usando Portale di dispositivi di Windows</span><span class="sxs-lookup"><span data-stu-id="11bb9-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="11bb9-132">Per questo processo, HoloLens deve essere configurato come dispositivo per sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="11bb9-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="11bb9-133">Per altre informazioni, [vedere Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="11bb9-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="11bb9-134">Se la procedura precedente non funziona, provare a riavviare il dispositivo usando [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="11bb9-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="11bb9-135">Nell'angolo in alto a destra trovare l'opzione per riavviare o arrestare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="11bb9-136">Eseguire un riavvio forzato non sicuro</span><span class="sxs-lookup"><span data-stu-id="11bb9-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="11bb9-137">Se i metodi precedenti non hanno riavviato HoloLens, forza un riavvio.</span><span class="sxs-lookup"><span data-stu-id="11bb9-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="11bb9-138">Questo metodo equivale a rimuovere e reinstallare la batteria.</span><span class="sxs-lookup"><span data-stu-id="11bb9-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="11bb9-139">È pericoloso perché potrebbe lasciare il dispositivo in uno stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="11bb9-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="11bb9-140">In questo caso, dovrai eseguire il flash di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11bb9-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="11bb9-141">Si tratta di un metodo potenzialmente dannoso e deve essere usato solo se i metodi citati in precedenza non funzionano.</span><span class="sxs-lookup"><span data-stu-id="11bb9-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="11bb9-142">Tenere premuto il **pulsante di** alimentazione per almeno 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="11bb9-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="11bb9-143">È possibile tenere premuto il pulsante per più di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="11bb9-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="11bb9-144">È possibile ignorare qualsiasi attività del LED.</span><span class="sxs-lookup"><span data-stu-id="11bb9-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="11bb9-145">Rilasciare il pulsante e attendere 2-3 secondi.</span><span class="sxs-lookup"><span data-stu-id="11bb9-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="11bb9-146">Tenere premuto il **pulsante di** alimentazione per 1 secondo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="11bb9-147">Se si verificano ancora  problemi, premere il pulsante di alimentazione per 4 secondi, fino a quando tutti gli indicatori della batteria non si dissolveranno e lo schermo smetterà di visualizzare gli ologrammi.</span><span class="sxs-lookup"><span data-stu-id="11bb9-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="11bb9-148">Attendere 1 minuto e quindi premere di nuovo il **pulsante** di alimentazione per accendere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="11bb9-149">Tornare a una versione precedente - HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="11bb9-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="11bb9-150">In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11bb9-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="11bb9-151">A tale scopo, puoi usare lo strumento ripristino dispositivi di Windows per ripristinare holoLens alla versione precedente.</span><span class="sxs-lookup"><span data-stu-id="11bb9-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="11bb9-152">Se si torna a una versione precedente, i file e le impostazioni personali vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="11bb9-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="11bb9-153">Per tornare a una versione precedente di HoloLens 1, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="11bb9-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="11bb9-154">Assicurarsi che non siano presenti telefoni o dispositivi Windows collegati al PC.</span><span class="sxs-lookup"><span data-stu-id="11bb9-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="11bb9-155">Nel PC scaricare Windows [Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="11bb9-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="11bb9-156">Scaricare il [pacchetto di ripristino dell'aggiornamento dell'anniversario di HoloLens.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="11bb9-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="11bb9-157">Al termine dei download, aprire **Download di Esplora**  >  **file.**</span><span class="sxs-lookup"><span data-stu-id="11bb9-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="11bb9-158">Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="11bb9-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="11bb9-159">Connetti HoloLens al PC usando il cavo micro USB fornito.</span><span class="sxs-lookup"><span data-stu-id="11bb9-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="11bb9-160">Anche se hai già utilizzato altri cavi per connettere HoloLens, questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="11bb9-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="11bb9-161">WdRT rileverà automaticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11bb9-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="11bb9-162">Selezionare il **Microsoft HoloLens** riquadro.</span><span class="sxs-lookup"><span data-stu-id="11bb9-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="11bb9-163">Nella schermata successiva selezionare Selezione manuale **del pacchetto** e scegliere il file di installazione contenuto nella cartella decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="11bb9-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="11bb9-164">Cercare un file con estensione ffu.</span><span class="sxs-lookup"><span data-stu-id="11bb9-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="11bb9-165">Selezionare **Installa software** e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="11bb9-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="11bb9-166">Se WDRT non rileva HoloLens, prova a riavviare il PC.</span><span class="sxs-lookup"><span data-stu-id="11bb9-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="11bb9-167">Se il problema non funziona, selezionare **Il dispositivo non** è stato rilevato, selezionare **Microsoft HoloLens** e quindi seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="11bb9-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="11bb9-168">Ripristinare le impostazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="11bb9-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="11bb9-169">Per la reimpostazione della batteria è necessario almeno il 40% di carica.</span><span class="sxs-lookup"><span data-stu-id="11bb9-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="11bb9-170">Se holoLens presenta ancora un problema, prova a ripristinarlo allo stato factory.</span><span class="sxs-lookup"><span data-stu-id="11bb9-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="11bb9-171">Questo passaggio mantiene la versione del software Windows Holographic installato e restituisce tutto il resto alle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="11bb9-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="11bb9-172">Se si reimposta il dispositivo, tutti i dati personali, le app e le impostazioni verranno cancellati, incluse le informazioni di reimpostazione del TPM.</span><span class="sxs-lookup"><span data-stu-id="11bb9-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="11bb9-173">La reimpostazione installerà solo la versione installata più recente di Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="11bb9-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="11bb9-174">Sarà necessario ripetere tutti i passaggi di inizializzazione ( calibrare, connettersi al Wi-Fi, creare un account utente, scaricare le app e così via).</span><span class="sxs-lookup"><span data-stu-id="11bb9-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="11bb9-175">Aprire l'app Impostazioni e quindi selezionare **Aggiorna**  >  **ripristino.**</span><span class="sxs-lookup"><span data-stu-id="11bb9-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="11bb9-176">Selezionare **l'opzione Reimposta** dispositivo e leggere il messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="11bb9-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="11bb9-177">Confermare la reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="11bb9-177">Confirm the reset.</span></span> <span data-ttu-id="11bb9-178">Il dispositivo verrà riavviato e verrà visualizzato un set di ingranaggi rotanti e un indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="11bb9-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="11bb9-179">Attendere circa 30 minuti per il completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="11bb9-180">Al termine, il dispositivo verrà riavviato nell'esperienza "predefinita".</span><span class="sxs-lookup"><span data-stu-id="11bb9-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="11bb9-181">Reinstallare il sistema operativo</span><span class="sxs-lookup"><span data-stu-id="11bb9-181">Reinstall the operating system</span></span>

<span data-ttu-id="11bb9-182">Se il dispositivo ha ancora un problema dopo il riavvio e la reimpostazione, puoi usare uno strumento di ripristino nel computer per reinstallare il sistema operativo e il firmware HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11bb9-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="11bb9-183">I dati che HoloLens necessita per la reimpostazione sono in pacchetto in un aggiornamento flash completo (FFU), simile a un file con estensione iso, wim o vhd.</span><span class="sxs-lookup"><span data-stu-id="11bb9-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="11bb9-184">Informazioni sui formati di file di immagine FFU.</span><span class="sxs-lookup"><span data-stu-id="11bb9-184">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="11bb9-185">Puoi installare un nuovo sistema operativo in HoloLens (prima generazione) usando lo strumento ripristino dispositivi di Windows.</span><span class="sxs-lookup"><span data-stu-id="11bb9-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="11bb9-186">Prima di usare questo strumento, verifica se il riavvio o la reimpostazione di HoloLens corregge il problema.</span><span class="sxs-lookup"><span data-stu-id="11bb9-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="11bb9-187">Il processo di ripristino può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-187">The recovery process may take a while.</span></span> <span data-ttu-id="11bb9-188">Al termine, verrà installata la versione più recente del software Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="11bb9-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="11bb9-189">Per usare lo strumento, è necessario un computer che Windows 10 o versione successiva con almeno 4 GB di spazio di archiviazione disponibile.</span><span class="sxs-lookup"><span data-stu-id="11bb9-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="11bb9-190">Non è possibile eseguire questo strumento in una macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="11bb9-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="11bb9-191">Ripristinare HoloLens</span><span class="sxs-lookup"><span data-stu-id="11bb9-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="11bb9-192">Scaricare e installare lo [strumento ripristino dispositivi di Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) nel computer.</span><span class="sxs-lookup"><span data-stu-id="11bb9-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="11bb9-193">Connetti HoloLens (prima generazione) al computer usando il cavo Micro USB fornito con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11bb9-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="11bb9-194">Aprire lo strumento Ripristino dispositivi di Windows e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="11bb9-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="11bb9-195">Se HoloLens (prima generazione) non viene rilevato automaticamente, seleziona **Il mio dispositivo non è stato rilevato.**</span><span class="sxs-lookup"><span data-stu-id="11bb9-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="11bb9-196">Seguire quindi le istruzioni per impostare la modalità di ripristino del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="11bb9-197">Modalità flashing manuale</span><span class="sxs-lookup"><span data-stu-id="11bb9-197">Manual flashing mode</span></span>

<span data-ttu-id="11bb9-198">Se il dispositivo non viene rilevato, seguire questa procedura per attivarla in modalità flashing:</span><span class="sxs-lookup"><span data-stu-id="11bb9-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="11bb9-199">Scollegare il dispositivo da qualsiasi fonte di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="11bb9-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="11bb9-200">Se il dispositivo è spento, tenere premuto il **pulsante** di alimentazione fino a quando non si spegne completamente.</span><span class="sxs-lookup"><span data-stu-id="11bb9-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="11bb9-201">Tenere premuto **il pulsante del volume** e toccare brevemente il pulsante **di** alimentazione.</span><span class="sxs-lookup"><span data-stu-id="11bb9-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="11bb9-202">Il dispositivo dovrebbe avviarsi e visualizzare solo il LED centrale.</span><span class="sxs-lookup"><span data-stu-id="11bb9-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="11bb9-203">Collegare il dispositivo al PC.</span><span class="sxs-lookup"><span data-stu-id="11bb9-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="11bb9-204">Aprire lo strumento ripristino dispositivi di Windows.</span><span class="sxs-lookup"><span data-stu-id="11bb9-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="11bb9-205">Selezionare **Il dispositivo non è stato rilevato** e quindi **HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="11bb9-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="11bb9-206">Seguire le istruzioni per ripristinare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11bb9-206">Follow the instructions to recover your device.</span></span>
