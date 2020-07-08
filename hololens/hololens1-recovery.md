---
title: Riavviare, ripristinare o recuperare HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 36192315e234db16c7747457e69d6d6281c31bfe
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857734"
---
# <span data-ttu-id="950bf-104">Riavviare, ripristinare o recuperare HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="950bf-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="950bf-105">Se riscontri problemi sul tuo HoloLens, puoi provare a riavviare o ripristinare il tuo dispositivo, o addirittura a reinstallare il file immagine con lo strumento di recupero.</span><span class="sxs-lookup"><span data-stu-id="950bf-105">If you're experiencing problems with your HoloLens you may want to try a restart, reset, or even re-flash with device recovery.</span></span>

<span data-ttu-id="950bf-106">Di seguito sono riportate alcune procedure che puoi provare se il tuo HoloLens non funziona.</span><span class="sxs-lookup"><span data-stu-id="950bf-106">Here are some things to try if your HoloLens isn't running well.</span></span>  <span data-ttu-id="950bf-107">Questo articolo ti guida attraverso i passaggi consecutivi consigliati per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="950bf-107">This article will guide you through the recommended recovery steps in succession.</span></span>

<span data-ttu-id="950bf-108">Se vuoi ripristinare un dispositivo HoloLens 2, consulta la pagina [Ripristinare un HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), perché la procedura è differente.</span><span class="sxs-lookup"><span data-stu-id="950bf-108">If you are looking to recover a HoloLens 2, please view the page for [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as there are differences in the processes.</span></span>

<span data-ttu-id="950bf-109">Questo articolo è incentrato sul dispositivo e il software HoloLens. Se gli ologrammi non sono corretti, [questo articolo](hololens-environment-considerations.md) descrive i fattori ambientali che migliorano la qualità degli ologrammi.</span><span class="sxs-lookup"><span data-stu-id="950bf-109">This article focuses on the HoloLens device and software, if your holograms don't look right, [this article](hololens-environment-considerations.md) talks about environmental factors that improve hologram quality.</span></span>

## <span data-ttu-id="950bf-110">Riavviare</span><span class="sxs-lookup"><span data-stu-id="950bf-110">Restart</span></span>

### <span data-ttu-id="950bf-111">Eseguire un riavvio sicuro con Cortana</span><span class="sxs-lookup"><span data-stu-id="950bf-111">Perform a safe restart by using Cortana</span></span>

<span data-ttu-id="950bf-112">L’uso di Cortana è il modo più sicuro per riavviare il visore HoloLens.</span><span class="sxs-lookup"><span data-stu-id="950bf-112">The safest way to restart the HoloLens is by using Cortana.</span></span> <span data-ttu-id="950bf-113">Si tratta, in genere, di un semplice primo passaggio quando si verifica un problema con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="950bf-113">This is generally an easy first-step when experiencing an issue with HoloLens.</span></span> 

> [!NOTE]
> <span data-ttu-id="950bf-114">Cortana non è disponibile in tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="950bf-114">Cortana is not avalible on all devices.</span></span> <span data-ttu-id="950bf-115">Cortana è disponibile in tutti i dispositivi HoloLens di prima generazione.</span><span class="sxs-lookup"><span data-stu-id="950bf-115">Cortana is avalible to all HoloLens (1st Gen) devices.</span></span>
> <span data-ttu-id="950bf-116">Cortana è disponibile nei dispositivi HoloLens 2 con una build precedente a Windows Holographic versione 2004.</span><span class="sxs-lookup"><span data-stu-id="950bf-116">Cortana is avalible on HoloLens 2 devices on a build prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="950bf-117">Indossa il tuo dispositivo</span><span class="sxs-lookup"><span data-stu-id="950bf-117">Put on your device</span></span>
1. <span data-ttu-id="950bf-118">Assicurati che sia alimentato, che un utente vi stia accedendo, e che il dispositivo non richieda una password per sbloccarsi.</span><span class="sxs-lookup"><span data-stu-id="950bf-118">Make sure it's powered on, a user is logged in, and the device is not waiting for a password to unlock it.</span></span>
1. <span data-ttu-id="950bf-119">Pronuncia “Ciao Cortana, riavvia” o “Ciao Cortana, esegui il reboot”.</span><span class="sxs-lookup"><span data-stu-id="950bf-119">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
1. <span data-ttu-id="950bf-120">Cortana ti chiederà delle informazioni quando avrà ricevuto la richiesta.</span><span class="sxs-lookup"><span data-stu-id="950bf-120">When she acknowledges she will ask you for confirmation.</span></span> <span data-ttu-id="950bf-121">Attendi un secondo che venga riprodotto un suono dopo che ti ha rivolto la sua domanda, indicando che ti sta ascoltando, e pronuncia “Sì”.</span><span class="sxs-lookup"><span data-stu-id="950bf-121">Wait a second for a sound to play after she has finished her question, indicating she is listening to you and then say "Yes."</span></span>
1. <span data-ttu-id="950bf-122">Il dispositivo viene ora riavviato.</span><span class="sxs-lookup"><span data-stu-id="950bf-122">The device will now restart.</span></span>

### <span data-ttu-id="950bf-123">Eseguire un riavvio sicuro con il pulsante di accensione</span><span class="sxs-lookup"><span data-stu-id="950bf-123">Perform a safe restart by using the power button</span></span>

<span data-ttu-id="950bf-124">Se non riesci a riavviare il dispositivo, puoi provare a riavviarlo usando il pulsante di accensione:</span><span class="sxs-lookup"><span data-stu-id="950bf-124">If you still can't restart your device, you can try to restart it by using the power button:</span></span>

1. <span data-ttu-id="950bf-125">Tieni premuto il tasto di accensione per 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="950bf-125">Press and hold the power button for five seconds.</span></span>
   1. <span data-ttu-id="950bf-126">Dopo un secondo, tutti i cinque LED si accenderanno, e si spegneranno poi in sequenza da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="950bf-126">After one second, you will see all five LEDs illuminate, then slowly turn off from right to left.</span></span>
   1. <span data-ttu-id="950bf-127">Dopo cinque secondi tutti i LED saranno spenti, per indicare che il comando di spegnimento è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="950bf-127">After five seconds, all LEDs will be off, indicating the shutdown command was issued successfully.</span></span>
   1. <span data-ttu-id="950bf-128">Nota che è importante smettere di premere il pulsante subito dopo che tutti i LED si sono spenti.</span><span class="sxs-lookup"><span data-stu-id="950bf-128">Note that it's important to stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="950bf-129">Attendi un minuto il completamento della procedura di spegnimento.</span><span class="sxs-lookup"><span data-stu-id="950bf-129">Wait one minute for the shutdown to cleanly succeed.</span></span> <span data-ttu-id="950bf-130">Nota che lo spegnimento potrebbe ancora essere in corso, anche se le luci sono spente.</span><span class="sxs-lookup"><span data-stu-id="950bf-130">Note that the shutdown may still be in progress even if the displays are turned off.</span></span>
1. <span data-ttu-id="950bf-131">Riaccendi il dispositivo tenendo premuto il tasto di accensione per un secondo.</span><span class="sxs-lookup"><span data-stu-id="950bf-131">Power on the device again by pressing and holding the power button for one second.</span></span>

### <span data-ttu-id="950bf-132">Eseguire un riavvio sicuro usando Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="950bf-132">Perform a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="950bf-133">Per eseguire l’operazione, HoloLens deve essere configurato come un dispositivo per sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="950bf-133">To do this, HoloLens has to be configured as a developer device.</span></span>  
> <span data-ttu-id="950bf-134">Maggiori informazioni su [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="950bf-134">Read more about [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="950bf-135">Se la procedura precedente non ha funzionato, puoi provare a riavviare il dispositivo usando [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="950bf-135">If the previous procedure doesn't work, you can try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="950bf-136">Nell’angolo in alto a destra trovi un’opzione per riavviare o spegnere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="950bf-136">In the upper right corner, there is an option to restart or shut down the device.</span></span>

### <span data-ttu-id="950bf-137">Eseguire un riavvio forzato rischioso</span><span class="sxs-lookup"><span data-stu-id="950bf-137">Perform an unsafe forced restart</span></span>

<span data-ttu-id="950bf-138">Se non sei riuscito a riavviare il dispositivo con i metodi precedenti, puoi provare con un riavvio forzato.</span><span class="sxs-lookup"><span data-stu-id="950bf-138">If none of the previous methods are able to successfully restart your device, you can force a restart.</span></span> <span data-ttu-id="950bf-139">Questo metodo equivale a rimuovere la batteria dall’HoloLens.</span><span class="sxs-lookup"><span data-stu-id="950bf-139">This method is equivalent to pulling the battery from the HoloLens.</span></span>  <span data-ttu-id="950bf-140">Si tratta di un’operazione pericolosa, che può danneggiare il tuo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="950bf-140">It is a dangerous operation which may leave your device in a corrupt state.</span></span>  <span data-ttu-id="950bf-141">Se si verifica, dovrai ripristinare manualmente il tuo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="950bf-141">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="950bf-142">È un metodo potenzialmente pericoloso, e deve essere usato soltanto quando nessuno dei metodi precedenti ha funzionato.</span><span class="sxs-lookup"><span data-stu-id="950bf-142">This is a potentially harmful method and should only be used in the event none of the above methods work.</span></span>

1. <span data-ttu-id="950bf-143">Tieni premuto il tasto di accensione per almeno 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="950bf-143">Press and hold the power button for at least 10 seconds.</span></span>
   - <span data-ttu-id="950bf-144">Puoi anche tenere premuto il tasto per più di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="950bf-144">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="950bf-145">Puoi ignorare qualsiasi attività dei LED.</span><span class="sxs-lookup"><span data-stu-id="950bf-145">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="950bf-146">Rilascia il pulsante e attendi due o tre secondi.</span><span class="sxs-lookup"><span data-stu-id="950bf-146">Release the button and wait for two or three seconds.</span></span>
1. <span data-ttu-id="950bf-147">Riaccendi il dispositivo tenendo premuto il tasto di accensione per un secondo.</span><span class="sxs-lookup"><span data-stu-id="950bf-147">Power on the device again by pressing and holding the power button for one second.</span></span>
<span data-ttu-id="950bf-148">Se i problemi non sono risolti, tieni premuto il tasto di accensione per 4 secondi, finché tutti gli indicatori della batteria si spengono e gli ologrammi non sono più mostrati sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="950bf-148">If you're still having problems, press the power button for 4 seconds, until all of the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="950bf-149">Attendi 1 minuto, e premi poi il tasto di accensione di nuovo per accendere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="950bf-149">Wait 1 minute, then press the power button again to turn on the device.</span></span>

## <span data-ttu-id="950bf-150">Ripristinare le impostazioni di fabbrica</span><span class="sxs-lookup"><span data-stu-id="950bf-150">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="950bf-151">Per eseguire il ripristino, la batteria deve essere carica almeno al 40%.</span><span class="sxs-lookup"><span data-stu-id="950bf-151">The battery needs at least 40 percent charge to reset.</span></span>

<span data-ttu-id="950bf-152">Se riscontri ancora problemi sul tuo HoloLens dopo il riavvio, prova a ripristinare le impostazioni di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="950bf-152">If your HoloLens is still experiencing issues after restarting, try resetting it to factory state.</span></span>  <span data-ttu-id="950bf-153">Il ripristino dell’HoloLens mantiene inalterata la versione installata del software Windows Holographic, e ripristina le impostazioni di fabbrica per tutto il resto.</span><span class="sxs-lookup"><span data-stu-id="950bf-153">Resetting your HoloLens keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

<span data-ttu-id="950bf-154">Se si ripristina il dispositivo, tutti i dati personali, le app e le impostazioni verranno eliminati, compreso il ripristino del TPM.</span><span class="sxs-lookup"><span data-stu-id="950bf-154">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span> <span data-ttu-id="950bf-155">Durante il ripristino viene soltanto installata l’ultima versione di Windows Holographic, e dovrai completare di nuovo tutte le operazioni di inizializzazione (calibrazione, connessione Wi-Fi, creazione di un account utente, scaricamento delle app, e così via).</span><span class="sxs-lookup"><span data-stu-id="950bf-155">Resetting will only install the latest installed version of Windows Holographic and you will have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so forth).</span></span>

1. <span data-ttu-id="950bf-156">Lancia l’app Impostazioni e seleziona **Aggiorna** > **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="950bf-156">Launch the Settings app, and then select **Update** > **Reset**.</span></span>
1. <span data-ttu-id="950bf-157">Seleziona l’opzione **Ripristina dispositivo** e leggi il messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="950bf-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="950bf-158">Se accetti di ripristinare il dispositivo, questo si riavvierà e mostrerà una serie di ingranaggi rotanti con un indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="950bf-158">If you agree to reset your device, the device will restart and display a set of spinning gears with a progress bar.</span></span>
1. <span data-ttu-id="950bf-159">Attendi circa 30 minuti per il completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="950bf-159">Wait about 30 minutes for this process to complete.</span></span>
1. <span data-ttu-id="950bf-160">Al termine, il ripristino è completato e il dispositivo si riavvia offrendo l’esperienza iniziale.</span><span class="sxs-lookup"><span data-stu-id="950bf-160">The reset will complete and the device will restart into the out-of-the-box experience.</span></span>

## <span data-ttu-id="950bf-161">Reinstallare il sistema operativo</span><span class="sxs-lookup"><span data-stu-id="950bf-161">Re-install the operating system</span></span>

<span data-ttu-id="950bf-162">Se il dispositivo ha ancora problemi dopo il riavvio e il ripristino, puoi usare uno strumento di recupero sul tuo computer per reinstallare il sistema operativo e il firmware di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="950bf-162">If the device is still having a problem after rebooting and resetting, you can use a recovery tool on your computer to reinstall the HoloLens' operating system and firmware.</span></span>  

<span data-ttu-id="950bf-163">Tutti i dati di cui HoloLens ha bisogno per il ripristino sono inclusi in un file FFU (Full Flash Update).</span><span class="sxs-lookup"><span data-stu-id="950bf-163">All of the data HoloLens needs to reset is packaged in a Full Flash Update (ffu).</span></span>  <span data-ttu-id="950bf-164">Questo è simile ai file ISO, WIM o VHD.</span><span class="sxs-lookup"><span data-stu-id="950bf-164">This is similar to an iso, wim, or vhd.</span></span>  [<span data-ttu-id="950bf-165">Scopri di più sulle immagini FFU.</span><span class="sxs-lookup"><span data-stu-id="950bf-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="950bf-166">Se necessario, puoi installare un sistema operativo completamente nuovo sul tuo HoloLens di prima generazione usando Windows Device Recovery Tool. </span><span class="sxs-lookup"><span data-stu-id="950bf-166">If necessary, you can install a completely new operating system on your HoloLens (1st gen) with the Windows Device Recovery Tool.</span></span>

<span data-ttu-id="950bf-167">Prima di usare lo strumento, stabilisci se il riavvio o il ripristino del tuo HoloLens possa risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="950bf-167">Before you use this tool, determine if restarting or resetting your HoloLens fixes the problem.</span></span> <span data-ttu-id="950bf-168">La procedura di recupero può richiedere più tempo.</span><span class="sxs-lookup"><span data-stu-id="950bf-168">The recovery process may take some time.</span></span>  <span data-ttu-id="950bf-169">Al termine, sul tuo HoloLens sarà installata l’ultima versione del software Windows Holographic approvata per il tuo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="950bf-169">When you're done, the latest version of the Windows Holographic software approved for your HoloLens will be installed.</span></span>

<span data-ttu-id="950bf-170">Per usare lo strumento, è necessario un computer che esegue Windows 10 o versione successiva con almeno 4 GB di spazio di archiviazione libero.</span><span class="sxs-lookup"><span data-stu-id="950bf-170">To use the tool, you'll need a computer running Windows 10 or later, with at least 4 GB of free storage space.</span></span>  <span data-ttu-id="950bf-171">Nota che non puoi eseguire questo strumento su una macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="950bf-171">Please note that you can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="950bf-172">Recuperare l’HoloLens:</span><span class="sxs-lookup"><span data-stu-id="950bf-172">Recover your HoloLens:</span></span>

1. <span data-ttu-id="950bf-173">Scarica e installa [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) sul tuo PC.</span><span class="sxs-lookup"><span data-stu-id="950bf-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="950bf-174">Connetti l’HoloLens di prima generazione al tuo computer usando il cavo micro USB fornito insieme all’HoloLens.</span><span class="sxs-lookup"><span data-stu-id="950bf-174">Connect the HoloLens (1st gen) to your computer using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="950bf-175">Esegui Windows Device Recovery Tool e segui le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="950bf-175">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="950bf-176">Se HoloLens (prima generazione) non viene rilevato automaticamente, seleziona **Il mio dispositivo non è stato rilevato** per attivare la modalità di recupero del tuo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="950bf-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

### <span data-ttu-id="950bf-177">Modalità di lampeggiamento manuale:</span><span class="sxs-lookup"><span data-stu-id="950bf-177">Manual Flashing Mode:</span></span>

<span data-ttu-id="950bf-178">Se il tuo dispositivo non viene rilevato, usa questo metodo per attivare manualmente la modalità di lampeggiamento manuale.</span><span class="sxs-lookup"><span data-stu-id="950bf-178">In the event that your device is not being detected please use the following method to manually place it into flashing mode.</span></span>

1. <span data-ttu-id="950bf-179">Scollega il dispositivo da tutte le fonti di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="950bf-179">Unplug the device from all power sources.</span></span>
1. <span data-ttu-id="950bf-180">Se il dispositivo è acceso, tieni premuto il tasto di accensione fino a quando è completamente spento.</span><span class="sxs-lookup"><span data-stu-id="950bf-180">If the device is on please hold down the power button until it is completely off.</span></span>
1. <span data-ttu-id="950bf-181">Tieni premuto il tasto **Volume su**, e tocca brevemente il tasto **Volume giù**.</span><span class="sxs-lookup"><span data-stu-id="950bf-181">Hold the **Volume Up** button, and breifly tap the **Power button**.</span></span> 
1. <span data-ttu-id="950bf-182">Il dispositivo dovrebbe avviare il ciclo di avvio, e solo il LED centrale dovrebbe essere acceso.</span><span class="sxs-lookup"><span data-stu-id="950bf-182">The device should boot and then display only the middle LED light.</span></span>
1. <span data-ttu-id="950bf-183">Collega il dispositivo al tuo PC.</span><span class="sxs-lookup"><span data-stu-id="950bf-183">Plug the device into your PC.</span></span>
1. <span data-ttu-id="950bf-184">Esegui Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="950bf-184">Launch Windows Device Recovery Tool.</span></span>
1. <span data-ttu-id="950bf-185">Devi selezionare \*Il mio dispositivo non è stato rilevato\*\*, e scegliere poi **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="950bf-185">You will need to select \*My device was not detected\*\*, and then select **HoloLens**.</span></span> 
1. <span data-ttu-id="950bf-186">Segui le istruzioni per recuperare il tuo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="950bf-186">Follow the instructions to recover your device.</span></span>
