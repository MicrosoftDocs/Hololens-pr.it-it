---
title: Riavviare, reimpostare o ripristinare HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Come usare Advanced Recovery Companion per eseguire il flash di un'immagine HoloLens 2.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923636"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="8da4f-104">Riavviare, reimpostare o ripristinare HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8da4f-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="8da4f-105">Prima di iniziare qualsiasi procedura di risoluzione dei problemi, assicurarsi che il dispositivo venga addebitato al **20-40%** della capacità della batteria, se possibile.</span><span class="sxs-lookup"><span data-stu-id="8da4f-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="8da4f-106">Le [luci indicatore della batteria](hololens2-setup.md#lights-that-indicate-the-battery-level) posizionate sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8da4f-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="8da4f-107">Usare il caricatore e il cavo [USB Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) fornito con il HoloLens 2 perché è il modo migliore per caricare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8da4f-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="8da4f-108">Il caricatore fornisce 18W di potenza (9 V a 2A).</span><span class="sxs-lookup"><span data-stu-id="8da4f-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="8da4f-109">Usando il caricatore a pareti fornito, i HoloLens 2 possono caricare la batteria fino a esaurimento in meno di 65 minuti quando il dispositivo è in standby.</span><span class="sxs-lookup"><span data-stu-id="8da4f-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="8da4f-110">Se questi accessori non sono disponibili, assicurarsi che il caricatore disponibile sia in grado di supportare almeno 15W di potenza.</span><span class="sxs-lookup"><span data-stu-id="8da4f-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="8da4f-111">Se possibile, evitare di usare un PC per caricare il dispositivo tramite USB, che è lento.</span><span class="sxs-lookup"><span data-stu-id="8da4f-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="8da4f-112">Se il dispositivo viene avviato correttamente e in esecuzione, esistono tre modi per controllare il livello di carica della batteria:</span><span class="sxs-lookup"><span data-stu-id="8da4f-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="8da4f-113">Dal menu principale dell'interfaccia utente del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8da4f-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="8da4f-114">Visualizzare il LED vicino al pulsante di alimentazione (per una carica del 40%, dovrebbero essere visualizzati almeno due LED solidi).</span><span class="sxs-lookup"><span data-stu-id="8da4f-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="8da4f-115">Quando il dispositivo è in carica, l'indicatore della batteria si accende per indicare il livello di carica corrente.</span><span class="sxs-lookup"><span data-stu-id="8da4f-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="8da4f-116">L'ultima luce si dissolve in entrata e in uscita per indicare l'addebito attivo.</span><span class="sxs-lookup"><span data-stu-id="8da4f-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="8da4f-117">Quando HoloLens è on, l'indicatore della batteria visualizza il livello della batteria in cinque incrementi.</span><span class="sxs-lookup"><span data-stu-id="8da4f-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="8da4f-118">Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%.</span><span class="sxs-lookup"><span data-stu-id="8da4f-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="8da4f-119">Se il livello della batteria è molto basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente, quindi si esce.</span><span class="sxs-lookup"><span data-stu-id="8da4f-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="8da4f-120">Nel PC host aprire **Esplora file** e cercare il dispositivo HoloLens 2 sul lato sinistro in Questo **PC.**</span><span class="sxs-lookup"><span data-stu-id="8da4f-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="8da4f-121">Fare clic con il pulsante destro del mouse sul dispositivo e **scegliere Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="8da4f-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="8da4f-122">Verrà visualizzata una finestra di dialogo con il livello di carica della batteria.</span><span class="sxs-lookup"><span data-stu-id="8da4f-122">A dialog box will show the battery charge level.</span></span>

   ![Una schermata HoloLens 2 proprietà mostra il livello di modifica della batteria](images/ResetRecovery2.png)

<span data-ttu-id="8da4f-124">Se il dispositivo non può essere avviato nel menu di avvio, prendere nota dell'aspetto del LED e dell'enumerazione del dispositivo nel PC host.</span><span class="sxs-lookup"><span data-stu-id="8da4f-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="8da4f-125">Seguire quindi la guida [alla risoluzione dei problemi](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="8da4f-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="8da4f-126">Se lo stato del dispositivo non corrisponde ad alcuno degli stati [](hololens-recovery.md#hard-reset-procedure) elencati nella guida alla risoluzione dei problemi, eseguire la procedura di ripristino con il dispositivo connesso all'alimentatore, non al PC host.</span><span class="sxs-lookup"><span data-stu-id="8da4f-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="8da4f-127">Attendere almeno un'ora per l'addebito del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8da4f-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="8da4f-128">Reimpostare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="8da4f-128">Reset the device</span></span>

<span data-ttu-id="8da4f-129">In determinate circostanze potrebbe essere necessario reimpostare manualmente il dispositivo senza usare l'interfaccia utente del software.</span><span class="sxs-lookup"><span data-stu-id="8da4f-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="8da4f-130">Procedura standard</span><span class="sxs-lookup"><span data-stu-id="8da4f-130">Standard procedure</span></span>

1. <span data-ttu-id="8da4f-131">Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.</span><span class="sxs-lookup"><span data-stu-id="8da4f-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="8da4f-132">Tenere premuto il **pulsante di** alimentazione per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="8da4f-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="8da4f-133">Tutti i LED devono essere disattivati.</span><span class="sxs-lookup"><span data-stu-id="8da4f-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="8da4f-134">Attendere 2-3 secondi e quindi premere brevemente il **pulsante di** alimentazione.</span><span class="sxs-lookup"><span data-stu-id="8da4f-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="8da4f-135">I LED vicini al pulsante di alimentazione si accenderanno e il dispositivo inizierà ad avviarsi.</span><span class="sxs-lookup"><span data-stu-id="8da4f-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="8da4f-136">Connettere il dispositivo al PC host e quindi aprire Gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8da4f-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="8da4f-137">Ad Windows 10, premere **il tasto Windows** e quindi il tasto **X** e quindi selezionare **Gestione dispositivi.** Assicurarsi che il dispositivo enumeri correttamente *come Microsoft HoloLens* come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="8da4f-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 responsabile devivo MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="8da4f-139">Procedura di reimpostazione rigida</span><span class="sxs-lookup"><span data-stu-id="8da4f-139">Hard-reset procedure</span></span>

<span data-ttu-id="8da4f-140">Se la procedura di reimpostazione standard non funziona, usare la procedura di reimpostazione forzata:</span><span class="sxs-lookup"><span data-stu-id="8da4f-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="8da4f-141">Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.</span><span class="sxs-lookup"><span data-stu-id="8da4f-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="8da4f-142">Tenere **premuti i pulsanti di alimentazione**  +  **del** volume per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="8da4f-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="8da4f-143">Il dispositivo verrà riavviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8da4f-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="8da4f-144">Connettere il dispositivo al PC host.</span><span class="sxs-lookup"><span data-stu-id="8da4f-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="8da4f-145">Aprire Gestione dispositivi (per Windows 10 premere **il tasto Windows** e quindi il tasto **X** e quindi selezionare **Gestione dispositivi**).</span><span class="sxs-lookup"><span data-stu-id="8da4f-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="8da4f-146">Assicurarsi che il dispositivo venga enumerato correttamente *Microsoft HoloLens* come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="8da4f-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery Device Manager 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="8da4f-148">Pulisci reflash del dispositivo</span><span class="sxs-lookup"><span data-stu-id="8da4f-148">Clean-reflash the device</span></span>

<span data-ttu-id="8da4f-149">In situazioni straordinarie potrebbe essere necessario eseguire il "clean flash" del HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8da4f-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="8da4f-150">Si noti che clean-reflash non dovrebbe influire sui problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8da4f-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="8da4f-151">Uniformità dei colori di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="8da4f-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="8da4f-152">Avvio con audio ma senza output di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="8da4f-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="8da4f-153">Modello a 1-3-5 LED</span><span class="sxs-lookup"><span data-stu-id="8da4f-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="8da4f-154">Surriscaldamento</span><span class="sxs-lookup"><span data-stu-id="8da4f-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="8da4f-155">Arresti anomali del sistema operativo (diversi dagli arresti anomali dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="8da4f-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="8da4f-156">Esistono due modi per eseguire il reflash del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8da4f-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="8da4f-157">Per entrambi, è prima necessario [installare Advanced Recovery Companion da Windows Store.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="8da4f-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="8da4f-158">Se si ripristina il dispositivo, tutti i dati personali, le app e le impostazioni verranno cancellati, incluse le informazioni sulla reimpostazione del TPM.</span><span class="sxs-lookup"><span data-stu-id="8da4f-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="8da4f-159">Per impostazione predefinita, Advanced Recovery Companion è impostato per scaricare la [](hololens-release-notes.md#) build di rilascio della funzionalità più recente. Vedere qui per leggere le note sulla versione per informazioni sulla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="8da4f-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="8da4f-160">Per ottenere la versione più recente HoloLens 2 pacchetto di aggiornamento flash completo (FFU) per il reflash del dispositivo tramite Advanced Recovery Companion, fare clic qui per scaricare l'immagine dell'aggiornamento HoloLens 2 [mensile più recente.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="8da4f-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="8da4f-161">Questa versione è l'ultima build disponibile a livello generale.</span><span class="sxs-lookup"><span data-stu-id="8da4f-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="8da4f-162">Prima di avviare la procedura reflash, verificare che l'app sia installata e in esecuzione nel PC Windows 10 e sia pronta per rilevare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8da4f-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="8da4f-163">Assicurati anche che l'addebito di HoloLens sia minimo del 40%.</span><span class="sxs-lookup"><span data-stu-id="8da4f-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 schermata clean reflash](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="8da4f-165">Procedura normale</span><span class="sxs-lookup"><span data-stu-id="8da4f-165">Normal procedure</span></span>

1. <span data-ttu-id="8da4f-166">Mentre il dispositivo HoloLens è in esecuzione, connetterlo al PC Windows 10 in cui è stata aperta in precedenza l'app Complementare per il ripristino avanzato.</span><span class="sxs-lookup"><span data-stu-id="8da4f-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="8da4f-167">Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="8da4f-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 iniziale della reflash pulita](images/ARC2.png)

3. <span data-ttu-id="8da4f-169">Selezionare il HoloLens 2 nell'interfaccia utente dell'app Complementare per il ripristino avanzato e seguire le istruzioni per completare la reflash.</span><span class="sxs-lookup"><span data-stu-id="8da4f-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="8da4f-170">Procedura manuale</span><span class="sxs-lookup"><span data-stu-id="8da4f-170">Manual procedure</span></span>

<span data-ttu-id="8da4f-171">Se il HoloLens 2 non viene avviato correttamente o se Advanced Recovery Companion non riesce a rilevare il dispositivo, potrebbe essere necessario impostare il dispositivo in modalità di ripristino:</span><span class="sxs-lookup"><span data-stu-id="8da4f-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="8da4f-172">Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.</span><span class="sxs-lookup"><span data-stu-id="8da4f-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="8da4f-173">Tenere premuto il **pulsante di** alimentazione per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="8da4f-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="8da4f-174">Tutti i LED devono essere disattivati.</span><span class="sxs-lookup"><span data-stu-id="8da4f-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="8da4f-175">Mentre si preme **il pulsante del volume** verso l'alto, premere e rilasciare il **pulsante** di alimentazione per avviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8da4f-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="8da4f-176">Attendere 15 secondi e quindi rilasciare il **pulsante di volume** in alto.</span><span class="sxs-lookup"><span data-stu-id="8da4f-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="8da4f-177">Solo il LED centrale dei cinque LED si accende.</span><span class="sxs-lookup"><span data-stu-id="8da4f-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="8da4f-178">Connettere il dispositivo al PC host e aprire Gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8da4f-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="8da4f-179">Ad esempio Windows 10 premere **il tasto Windows,** quindi **il tasto X** e quindi selezionare **Gestione** dispositivi. Assicurarsi che il dispositivo venga enumerato correttamente Microsoft HoloLens come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="8da4f-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="8da4f-181">Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="8da4f-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 della reflash pulita](images/ARC2.png)

6. <span data-ttu-id="8da4f-183">Selezionare il HoloLens 2 nell'interfaccia utente dell'app Advanced Recovery Companion e quindi seguire le istruzioni per completare la reflash.</span><span class="sxs-lookup"><span data-stu-id="8da4f-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="8da4f-184">Risolvere i problemi relativi ad Advanced Recovery Companion</span><span class="sxs-lookup"><span data-stu-id="8da4f-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="8da4f-185">Assicurarsi che il dispositivo venga addebitato al 40% o più prima di provare a eseguire il flashing.</span><span class="sxs-lookup"><span data-stu-id="8da4f-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="8da4f-186">Verificare che il dispositivo sia sbloccato.</span><span class="sxs-lookup"><span data-stu-id="8da4f-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="8da4f-187">Se ARC non rileva il dispositivo, assicurarsi di potersi connettere al dispositivo tramite Esplora file nel PC.</span><span class="sxs-lookup"><span data-stu-id="8da4f-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="8da4f-188">Se non è possibile;</span><span class="sxs-lookup"><span data-stu-id="8da4f-188">If you cannot;</span></span>

    1.  <span data-ttu-id="8da4f-189">È possibile che il dispositivo abbia criteri USB che disabilitano la connessione.</span><span class="sxs-lookup"><span data-stu-id="8da4f-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="8da4f-190">In tal caso, provare [la modalità flashing manuale.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="8da4f-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="8da4f-191">Se non sono presenti criteri, provare un cavo USB diverso.</span><span class="sxs-lookup"><span data-stu-id="8da4f-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="8da4f-192">Verificare che nel dispositivo non sia visualizzato un modello a [1-3-5 LED.](hololens2-setup.md#lights-to-indicate-problems)</span><span class="sxs-lookup"><span data-stu-id="8da4f-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="8da4f-193">Scaricare ARC senza usare l'App Store</span><span class="sxs-lookup"><span data-stu-id="8da4f-193">Download ARC without using the app store</span></span>

<span data-ttu-id="8da4f-194">Se l'ambiente IT impedisce l'uso dell'app di Windows Store o limita l'accesso al punto vendita al dettaglio, l'amministratore IT può rendere disponibile l'app tramite un percorso di distribuzione "offline".</span><span class="sxs-lookup"><span data-stu-id="8da4f-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="8da4f-195">Gli amministratori IT possono anche distribuire questa app tramite System Center Gestione configurazione (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="8da4f-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="8da4f-196">Questa guida è incentrata su Advanced Recovery Companion, ma il processo può essere usato anche per altre app "offline".</span><span class="sxs-lookup"><span data-stu-id="8da4f-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="8da4f-197">Seguire questa procedura per abilitare il percorso di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="8da4f-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="8da4f-198">Passare [all'Microsoft Store per le aziende](https://businessstore.microsoft.com) e accedere usando un'Azure Active Directory identità.</span><span class="sxs-lookup"><span data-stu-id="8da4f-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="8da4f-199">Passare a **Gestisci - Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="8da4f-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="8da4f-200">Attivare Mostra **app offline in** Esperienza di **acquisto.**</span><span class="sxs-lookup"><span data-stu-id="8da4f-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="8da4f-201">Passare al **negozio per il gruppo e** cercare Advanced Recovery [**_Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="8da4f-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="8da4f-202">Impostare **Tipo di licenza** su \**_offline_*_, quindi selezionare _\* Gestisci\*\*.</span><span class="sxs-lookup"><span data-stu-id="8da4f-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="8da4f-203">In **Scarica il pacchetto per l'uso offline** selezionare il secondo pulsante blu **Scarica.**</span><span class="sxs-lookup"><span data-stu-id="8da4f-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="8da4f-204">Assicurarsi che l'estensione del file *sia appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="8da4f-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="8da4f-205">In questa fase, se il PC desktop ha accesso a Internet, fare doppio clic sul pacchetto per installare l'app.</span><span class="sxs-lookup"><span data-stu-id="8da4f-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="8da4f-206">Se il PC di destinazione non ha connettività Internet, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="8da4f-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="8da4f-207">Selezionare la licenza non codificata e quindi selezionare **Genera licenza**.</span><span class="sxs-lookup"><span data-stu-id="8da4f-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="8da4f-208">In **Framework necessari** selezionare **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="8da4f-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="8da4f-209">Usare Gestione e manutenzione immagini distribuzione per applicare il pacchetto con la dipendenza e la licenza.</span><span class="sxs-lookup"><span data-stu-id="8da4f-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="8da4f-210">Da un prompt dei comandi amministratore eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8da4f-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="8da4f-211">Il numero di versione in questo esempio di codice potrebbe non corrispondere alla versione attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="8da4f-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="8da4f-212">È anche possibile che sia stato scelto un percorso di download diverso rispetto all'esempio.</span><span class="sxs-lookup"><span data-stu-id="8da4f-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="8da4f-213">Apportare eventuali modifiche al comando in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8da4f-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="8da4f-214">Quando si prevede di usare Advanced Recovery Companion per installare un FFU offline, può essere utile scaricare l'immagine flash.</span><span class="sxs-lookup"><span data-stu-id="8da4f-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="8da4f-215">[**Scaricare l'immagine corrente per HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="8da4f-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="8da4f-216">Altre risorse:</span><span class="sxs-lookup"><span data-stu-id="8da4f-216">Other resources:</span></span>
- [<span data-ttu-id="8da4f-217">Distribuire app offline</span><span class="sxs-lookup"><span data-stu-id="8da4f-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="8da4f-218">Opzioni della riga di comando per la manutenzione del pacchetto dell'app di Gestione e manutenzione immagini distribuzione (con estensione appx o appxbundle)</span><span class="sxs-lookup"><span data-stu-id="8da4f-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
