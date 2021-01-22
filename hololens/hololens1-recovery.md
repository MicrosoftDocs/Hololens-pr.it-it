---
title: Riavviare, ripristinare o recuperare HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Come usare lo strumento Windows Device Recovery Tool per reinstallare il file immagine di HoloLens (prima generazione).
keywords: guida, riavvio, reset, ripristino, recupero, ripristino automatico, ciclo di alimentazione, HoloLens, spegnimento, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0aa400be56d09a843a1b7c9bae78346551ad8af
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283917"
---
# <span data-ttu-id="7d1be-104">Riavviare, ripristinare o recuperare HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="7d1be-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="7d1be-105">Se si riscontrano problemi su HoloLens, è possibile provare a riavviare o ripristinare il dispositivo, o addirittura a riconfigurarlo utilizzando lo strumento di recupero.</span><span class="sxs-lookup"><span data-stu-id="7d1be-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="7d1be-106">Questo articolo illustra i passaggi consigliati ed il loro ordine di esecuzione per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="7d1be-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="7d1be-107">Se si vuole ripristinare un HoloLens 2, vedere [Ripristino di un HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), visto che i processi sono differenti.</span><span class="sxs-lookup"><span data-stu-id="7d1be-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="7d1be-108">Questo articolo è incentrato sul dispositivo ed il software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7d1be-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="7d1be-109">Se gli ologrammi non sembrano essere corretti, vedere **[considerazioni sull'ambiente HoloLens](hololens-environment-considerations.md)** per informazioni sui fattori che migliorano la qualità degli ologrammi.</span><span class="sxs-lookup"><span data-stu-id="7d1be-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <span data-ttu-id="7d1be-110">Riavviare</span><span class="sxs-lookup"><span data-stu-id="7d1be-110">Restart</span></span>

### <span data-ttu-id="7d1be-111">Riavviare in sicurezza usando Cortana</span><span class="sxs-lookup"><span data-stu-id="7d1be-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="7d1be-112">Il modo più sicuro per riavviare HoloLens consiste nell'usare Cortana, che in genere è la prima cosa da provare quando si verifica un problema con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7d1be-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="7d1be-113">Cortana non è disponibile su tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7d1be-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="7d1be-114">Cortana è disponibile su tutti i dispositivi HoloLens di 1 generazione.</span><span class="sxs-lookup"><span data-stu-id="7d1be-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="7d1be-115">Cortana è disponibile sui dispositivi HoloLens 2 con build precedenti a Windows Holographic, versione 2004 aggiornata.</span><span class="sxs-lookup"><span data-stu-id="7d1be-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="7d1be-116">Attivare HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7d1be-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="7d1be-117">Assicurarsi che l’utente abbia già effettuato l’accesso e che il dispositivo non richieda una password per sbloccarsi.</span><span class="sxs-lookup"><span data-stu-id="7d1be-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="7d1be-118">Pronuncia “Ciao Cortana, riavvia” o “Ciao Cortana, esegui il reboot”.</span><span class="sxs-lookup"><span data-stu-id="7d1be-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="7d1be-119">Cortana risponderà e chiederà di confermare.</span><span class="sxs-lookup"><span data-stu-id="7d1be-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="7d1be-120">Attendere la riproduzione di un suono dopo la domanda e successivamente dire “Sì".</span><span class="sxs-lookup"><span data-stu-id="7d1be-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="7d1be-121">Il dispositivo viene ora riavviato.</span><span class="sxs-lookup"><span data-stu-id="7d1be-121">The device will restart.</span></span>

### <span data-ttu-id="7d1be-122">Usare il pulsante di accensione per riavviare in sicurezza</span><span class="sxs-lookup"><span data-stu-id="7d1be-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="7d1be-123">Se ancora risulta impossibile riavviare il dispositivo, ritentare utilizzando il pulsante di **accensione**:</span><span class="sxs-lookup"><span data-stu-id="7d1be-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="7d1be-124">Tenere premuto il pulsante di **accensione** per 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="7d1be-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="7d1be-125">Dopo 1 secondo, tutti e cinque i LED si accenderanno disattivandosi lentamente uno alla volta da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="7d1be-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="7d1be-126">Dopo 5 secondi, tutti i LED saranno spenti, segno di arresto avvenuto correttamente.</span><span class="sxs-lookup"><span data-stu-id="7d1be-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="7d1be-127">È necessario smettere di premere il pulsante subito dopo lo spegnimento di tutti i LED.</span><span class="sxs-lookup"><span data-stu-id="7d1be-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="7d1be-128">Attendere 1 minuto per il completamento della chiusura.</span><span class="sxs-lookup"><span data-stu-id="7d1be-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="7d1be-129">Lo spegnimento potrebbe ancora essere in corso nonostante lo spegnimento delle luci.</span><span class="sxs-lookup"><span data-stu-id="7d1be-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="7d1be-130">Riaccendere il dispositivo tenendo premuto il tasto di **accensione** per 1 secondo.</span><span class="sxs-lookup"><span data-stu-id="7d1be-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <span data-ttu-id="7d1be-131">Eseguire un riavvio sicuro usando il Portale di dispositivi di Windows</span><span class="sxs-lookup"><span data-stu-id="7d1be-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="7d1be-132">Per questo processo, HoloLens deve essere configurato come un dispositivo per sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="7d1be-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="7d1be-133">Maggiori informazioni sul [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="7d1be-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="7d1be-134">Se la procedura precedente non ha funzionato, è possibile provare a riavviare il dispositivo usando il [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="7d1be-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="7d1be-135">Nell’angolo in alto a destra si trova l’opzione per riavviare o spegnere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7d1be-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <span data-ttu-id="7d1be-136">Eseguire un riavvio forzato rischioso</span><span class="sxs-lookup"><span data-stu-id="7d1be-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="7d1be-137">Se i metodi precedenti non hanno riavviato HoloLens, forzarne il riavvio.</span><span class="sxs-lookup"><span data-stu-id="7d1be-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="7d1be-138">Questo metodo equivale a rimuovere e reinstallare la batteria.</span><span class="sxs-lookup"><span data-stu-id="7d1be-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="7d1be-139">Tale procedura rappresenta un rischio perché potrebbe danneggiare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7d1be-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="7d1be-140">Se si verifica, dovrai ripristinare manualmente il tuo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7d1be-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="7d1be-141">Questo è un metodo potenzialmente pericoloso e dovrebbe essere usato soltanto quando nessuno dei metodi precedenti ha funzionato.</span><span class="sxs-lookup"><span data-stu-id="7d1be-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="7d1be-142">Tenere premuto il tasto di **accensione** per almeno 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="7d1be-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="7d1be-143">Puoi anche tenere premuto il tasto per più di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="7d1be-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="7d1be-144">Puoi ignorare qualsiasi attività dei LED.</span><span class="sxs-lookup"><span data-stu-id="7d1be-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="7d1be-145">Rilasciare il pulsante e attendere 2 o 3 secondi.</span><span class="sxs-lookup"><span data-stu-id="7d1be-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="7d1be-146">Tenere premuto il pulsante di **accensione** per 1 secondo.</span><span class="sxs-lookup"><span data-stu-id="7d1be-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="7d1be-147">Se il problema persiste, tenere premuto il tasto di **accensione** per 4 secondi, finché tutti gli indicatori della batteria si spengono e gli ologrammi non sono più mostrati sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="7d1be-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="7d1be-148">Attendere 1 minuto, e premere poi il tasto di **accensione** di nuovo per accendere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7d1be-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <span data-ttu-id="7d1be-149">Ripristinare le impostazioni di fabbrica</span><span class="sxs-lookup"><span data-stu-id="7d1be-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="7d1be-150">Per eseguire il ripristino, la batteria deve essere carica almeno al 40%.</span><span class="sxs-lookup"><span data-stu-id="7d1be-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="7d1be-151">Se il problema persiste sul Microsoft HoloLens, provare a ripristinare le impostazioni di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="7d1be-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="7d1be-152">Questo processo mantiene inalterata la versione installata del software Windows Holographic e ripristina le impostazioni di fabbrica per tutto il resto.</span><span class="sxs-lookup"><span data-stu-id="7d1be-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="7d1be-153">Se si ripristina il dispositivo, tutti i dati personali, le app e le impostazioni verranno eliminati, incluse le informazioni sul ripristino del TPM.</span><span class="sxs-lookup"><span data-stu-id="7d1be-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="7d1be-154">Il ripristino installerà solo l’ultima versione installata di Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="7d1be-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="7d1be-155">È necessario ripetere tutti i passaggi di inizializzazione (calibratura, connessione al Wi-Fi, creazione dell’account utente, download delle app e così via).</span><span class="sxs-lookup"><span data-stu-id="7d1be-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="7d1be-156">Aprire l’app Impostazioni e seleziona **Aggiorna** > **Ripristino**.</span><span class="sxs-lookup"><span data-stu-id="7d1be-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="7d1be-157">Seleziona l’opzione **Ripristina dispositivo** e leggi il messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="7d1be-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="7d1be-158">Confermare il ripristino.</span><span class="sxs-lookup"><span data-stu-id="7d1be-158">Confirm the reset.</span></span> <span data-ttu-id="7d1be-159">Il dispositivo si riavvierà e mostrerà una serie di ingranaggi rotanti con un indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="7d1be-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="7d1be-160">Attendi circa 30 minuti per il completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="7d1be-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="7d1be-161">Al termine, il dispositivo si riavvierà in modalità “impatto fuori scatola”.</span><span class="sxs-lookup"><span data-stu-id="7d1be-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <span data-ttu-id="7d1be-162">Reinstallare il sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7d1be-162">Reinstall the operating system</span></span>

<span data-ttu-id="7d1be-163">Se il dispositivo presenta ancora problemi dopo il riavvio e il ripristino, è possibile usare uno strumento di recupero sul computer per reinstallare il sistema operativo e il firmware di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7d1be-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="7d1be-164">I dati necessari per reimpostare HoloLens sono inclusi in un Full Flash Update (FFU), che è simile a un file con estensione ISO, WIM o VHD.</span><span class="sxs-lookup"><span data-stu-id="7d1be-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="7d1be-165">Scopri di più sulle immagini FFU.</span><span class="sxs-lookup"><span data-stu-id="7d1be-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="7d1be-166">Usando il Windows Device Recovery Tool è possibile installare un sistema operativo completamente nuovo su un HoloLens di 1 generazione. </span><span class="sxs-lookup"><span data-stu-id="7d1be-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="7d1be-167">Prima di usare tale strumento, è preferibile stabilire se il riavvio o il ripristino di HoloLens possano risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="7d1be-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="7d1be-168">La procedura di recupero può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="7d1be-168">The recovery process may take a while.</span></span> <span data-ttu-id="7d1be-169">Al termine, sarà installata l’ultima versione del software Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="7d1be-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="7d1be-170">Per usare lo strumento, è necessario un computer dotato di Windows 10 o versione successiva e di almeno 4 GB di spazio di archiviazione libero.</span><span class="sxs-lookup"><span data-stu-id="7d1be-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="7d1be-171">Non è possibile eseguire questo strumento su una macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="7d1be-171">You can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="7d1be-172">Recupero di HoloLens</span><span class="sxs-lookup"><span data-stu-id="7d1be-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="7d1be-173">Scarica e installa [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) sul tuo PC.</span><span class="sxs-lookup"><span data-stu-id="7d1be-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="7d1be-174">Connettere un HoloLens di 1 generazione al computer usando il cavo micro USB fornito in dotazione.</span><span class="sxs-lookup"><span data-stu-id="7d1be-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="7d1be-175">Eseguire Windows Device Recovery Tool e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="7d1be-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="7d1be-176">Se l'HoloLens di 1 generazione non viene rilevato automaticamente, selezionare **il mio dispositivo non è stato rilevato**.</span><span class="sxs-lookup"><span data-stu-id="7d1be-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="7d1be-177">Seguire quindi le istruzioni per far entrare il dispositivo in modalità di ripristino.</span><span class="sxs-lookup"><span data-stu-id="7d1be-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <span data-ttu-id="7d1be-178">Modalità di riconfigurazione manuale</span><span class="sxs-lookup"><span data-stu-id="7d1be-178">Manual flashing mode</span></span>

<span data-ttu-id="7d1be-179">Se il dispositivo non viene rilevato, eseguire le operazioni seguenti per farlo entrare in modalità di riconfigurazione:</span><span class="sxs-lookup"><span data-stu-id="7d1be-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="7d1be-180">Scollegare il dispositivo da tutte le fonti di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="7d1be-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="7d1be-181">Se il dispositivo è acceso, tenere premuto il tasto di **accensione** fino al suo completo spegnimento.</span><span class="sxs-lookup"><span data-stu-id="7d1be-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="7d1be-182">Tenere premuto il tasto **volume verso l’alto** e toccare brevemente il tasto di **accensione**.</span><span class="sxs-lookup"><span data-stu-id="7d1be-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="7d1be-183">Il dispositivo dovrebbe avviarsi e solo il LED centrale dovrebbe essere acceso.</span><span class="sxs-lookup"><span data-stu-id="7d1be-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="7d1be-184">Collega il dispositivo al tuo PC.</span><span class="sxs-lookup"><span data-stu-id="7d1be-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="7d1be-185">Eseguire Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="7d1be-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="7d1be-186">Selezionare**Il mio dispositivo non è stato rilevato** e quindi **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="7d1be-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="7d1be-187">Segui le istruzioni per recuperare il tuo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7d1be-187">Follow the instructions to recover your device.</span></span>
