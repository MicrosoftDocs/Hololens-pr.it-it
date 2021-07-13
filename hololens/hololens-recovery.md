---
title: Riavviare, reimpostare o ripristinare HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Come usare Advanced Recovery Companion per eseguire il flash di un'immagine per HoloLens 2.
keywords: procedura, riavvio, ripristino, ripristino, hard reset, soft reset, ciclo di alimentazione, HoloLens, arresto, arco, complementare per il ripristino avanzato
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
ms.openlocfilehash: 0124453ef9e3b21722acaf2c6b438ebdfbd65043
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635943"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="bacb3-104">Riavviare, reimpostare o ripristinare HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bacb3-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="bacb3-105">Prima di avviare qualsiasi procedura di risoluzione dei problemi, assicurarsi che al dispositivo venga addebitato un addebito dal **20 al 40%** della capacità della batteria, se possibile.</span><span class="sxs-lookup"><span data-stu-id="bacb3-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="bacb3-106">Le [luci dell'indicatore della](hololens2-setup.md#lights-that-indicate-the-battery-level) batteria che si trovano sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bacb3-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="bacb3-107">Usare il [caricabatterie](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) e il cavo USB Type-C fornito con il HoloLens 2 perché è il modo migliore per caricare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bacb3-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="bacb3-108">Il caricabatterie fornisce 18W di alimentazione (9 V a 2A).</span><span class="sxs-lookup"><span data-stu-id="bacb3-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="bacb3-109">Usando il caricabatterie a parete fornito, HoloLens 2 i dispositivi possono ricaricare la batteria in meno di 65 minuti quando il dispositivo è in standby.</span><span class="sxs-lookup"><span data-stu-id="bacb3-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="bacb3-110">Se questi accessori non sono disponibili, assicurarsi che il caricabatterie disponibile supporti almeno 15W di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="bacb3-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="bacb3-111">Se possibile, evitare di usare un PC per caricare il dispositivo tramite USB, che è lento.</span><span class="sxs-lookup"><span data-stu-id="bacb3-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="bacb3-112">Se il dispositivo viene avviato correttamente e in esecuzione, è possibile controllare il livello di carica della batteria in tre modi:</span><span class="sxs-lookup"><span data-stu-id="bacb3-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="bacb3-113">Dal menu principale dell'interfaccia utente HoloLens dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bacb3-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="bacb3-114">Visualizzare il LED vicino al pulsante di accensione (per un addebito del 40%, dovrebbero essere visualizzati almeno due LED solidi).</span><span class="sxs-lookup"><span data-stu-id="bacb3-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="bacb3-115">Quando il dispositivo è in carica, l'indicatore della batteria si accende per indicare il livello di carica corrente.</span><span class="sxs-lookup"><span data-stu-id="bacb3-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="bacb3-116">L'ultima luce si dissolverà in entrata e in uscita per indicare la ricarica attiva.</span><span class="sxs-lookup"><span data-stu-id="bacb3-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="bacb3-117">Quando il HoloLens è on, l'indicatore della batteria visualizza il livello della batteria in cinque incrementi.</span><span class="sxs-lookup"><span data-stu-id="bacb3-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="bacb3-118">Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%.</span><span class="sxs-lookup"><span data-stu-id="bacb3-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="bacb3-119">Se il livello della batteria è criticamente basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente e quindi si spegne.</span><span class="sxs-lookup"><span data-stu-id="bacb3-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="bacb3-120">Nel PC host aprire **Esplora file** e cercare il dispositivo HoloLens 2 sul lato sinistro in Questo **PC**.</span><span class="sxs-lookup"><span data-stu-id="bacb3-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="bacb3-121">Fare clic con il pulsante destro del mouse sul dispositivo e **scegliere Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bacb3-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="bacb3-122">Verrà visualizzata una finestra di dialogo con il livello di carica della batteria.</span><span class="sxs-lookup"><span data-stu-id="bacb3-122">A dialog box will show the battery charge level.</span></span>

   ![Una HoloLens 2 delle proprietà mostra il livello di modifica della batteria](images/ResetRecovery2.png)

<span data-ttu-id="bacb3-124">Se il dispositivo non è in grado di avviare il menu di avvio, prendere nota dell'aspetto del LED e dell'enumerazione del dispositivo nel PC host.</span><span class="sxs-lookup"><span data-stu-id="bacb3-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="bacb3-125">Seguire quindi la guida [alla risoluzione dei problemi](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="bacb3-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="bacb3-126">Se lo stato del dispositivo non corrisponde a uno degli stati [](hololens-recovery.md#hard-reset-procedure) elencati nella guida alla risoluzione dei problemi, eseguire la procedura di ripristino con il dispositivo connesso all'alimentatore e non con il PC host.</span><span class="sxs-lookup"><span data-stu-id="bacb3-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="bacb3-127">Attendere almeno un'ora per l'addebito del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bacb3-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="bacb3-128">Reimpostare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="bacb3-128">Reset the device</span></span>

<span data-ttu-id="bacb3-129">In determinate circostanze, potrebbe essere necessario reimpostare manualmente il dispositivo senza usare l'interfaccia utente del software.</span><span class="sxs-lookup"><span data-stu-id="bacb3-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="bacb3-130">Procedura standard</span><span class="sxs-lookup"><span data-stu-id="bacb3-130">Standard procedure</span></span>

1. <span data-ttu-id="bacb3-131">Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.</span><span class="sxs-lookup"><span data-stu-id="bacb3-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="bacb3-132">Tenere premuto il **pulsante** di alimentazione per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="bacb3-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="bacb3-133">Tutti i LED devono essere spenti.</span><span class="sxs-lookup"><span data-stu-id="bacb3-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="bacb3-134">Attendere 2-3 secondi e quindi premere brevemente il **pulsante di** alimentazione.</span><span class="sxs-lookup"><span data-stu-id="bacb3-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="bacb3-135">I LED vicini al pulsante di accensione si accenderanno e il dispositivo inizierà ad avviarsi.</span><span class="sxs-lookup"><span data-stu-id="bacb3-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="bacb3-136">Connessione il dispositivo nel PC host e quindi aprire Gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bacb3-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="bacb3-137">Per Windows 10, premere il Windows **e** quindi il tasto **X** e quindi selezionare **Gestione dispositivi.** Assicurarsi che il dispositivo venga enumerato correttamente *Microsoft HoloLens* come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="bacb3-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="bacb3-139">Procedura di reimpostazione rigida</span><span class="sxs-lookup"><span data-stu-id="bacb3-139">Hard-reset procedure</span></span>

<span data-ttu-id="bacb3-140">Se la procedura di reimpostazione standard non ha funzionato, usare la procedura di reimpostazione rigida:</span><span class="sxs-lookup"><span data-stu-id="bacb3-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="bacb3-141">Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.</span><span class="sxs-lookup"><span data-stu-id="bacb3-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="bacb3-142">Tenere premuti **i pulsanti di risparmio**  +  **energia** del volume per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="bacb3-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="bacb3-143">Il dispositivo verrà riavviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bacb3-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="bacb3-144">Connessione il dispositivo al PC host.</span><span class="sxs-lookup"><span data-stu-id="bacb3-144">Connect the device to the host PC.</span></span>


5. <span data-ttu-id="bacb3-145">Aprire Gestione dispositivi (per Windows 10 premere **Windows** e quindi **il tasto X** e quindi selezionare Gestione **dispositivi**).</span><span class="sxs-lookup"><span data-stu-id="bacb3-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="bacb3-146">Assicurarsi che il dispositivo venga enumerato correttamente *Microsoft HoloLens* come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="bacb3-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery Device Maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="bacb3-148">Pulire il dispositivo</span><span class="sxs-lookup"><span data-stu-id="bacb3-148">Clean-reflash the device</span></span>

<span data-ttu-id="bacb3-149">In situazioni straordinarie, potrebbe essere necessario "pulire flash" il HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bacb3-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="bacb3-150">Si noti che clean-reflash non dovrebbe influire sui problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bacb3-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="bacb3-151">Uniformità dei colori di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="bacb3-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="bacb3-152">Avvio con audio ma nessun output di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="bacb3-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="bacb3-153">Modello a 1-3-5 LED</span><span class="sxs-lookup"><span data-stu-id="bacb3-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="bacb3-154">Surriscaldamento</span><span class="sxs-lookup"><span data-stu-id="bacb3-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="bacb3-155">Arresti anomali del sistema operativo (diversi dagli arresti anomali dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="bacb3-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="bacb3-156">Esistono due modi per eseguire il reflash del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bacb3-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="bacb3-157">Per entrambi, è prima [necessario installare Advanced Recovery Companion da Windows Store.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="bacb3-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="bacb3-158">Se si rifiuta il dispositivo, tutti i dati personali, le app e le impostazioni verranno cancellati, incluse le informazioni di reimpostazione TPM.</span><span class="sxs-lookup"><span data-stu-id="bacb3-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="bacb3-159">Per impostazione predefinita, Advanced Recovery Companion è impostato per scaricare la [](hololens-release-notes.md#) build di rilascio delle funzionalità più recente. Vedere qui per leggere le note sulla versione per informazioni sulla versione più recente delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="bacb3-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="bacb3-160">Per ottenere il pacchetto HoloLens 2 Full Flash Update (FFU) più recente per il reflash del dispositivo tramite Advanced Recovery Companion, fare clic qui per scaricare l'immagine HoloLens 2 [mensile più recente.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="bacb3-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="bacb3-161">Questa versione è la build disponibile a livello generale più recente.</span><span class="sxs-lookup"><span data-stu-id="bacb3-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="bacb3-162">Prima di avviare la procedura di reflash, assicurarsi che l'app sia installata e in esecuzione nel PC Windows 10 e pronta per rilevare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bacb3-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="bacb3-163">Assicurarsi inoltre che al HoloLens sia addebitato un minimo del 40%.</span><span class="sxs-lookup"><span data-stu-id="bacb3-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 schermata del reflash pulito](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="bacb3-165">Procedura normale</span><span class="sxs-lookup"><span data-stu-id="bacb3-165">Normal procedure</span></span>

1. <span data-ttu-id="bacb3-166">Mentre il HoloLens è in esecuzione, connetterlo al PC Windows 10 in cui è stata aperta in precedenza l'app Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="bacb3-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="bacb3-167">Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="bacb3-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 schermata iniziale del reflash pulito](images/ARC2.png)

3. <span data-ttu-id="bacb3-169">Selezionare il dispositivo HoloLens 2 nell'interfaccia utente dell'app Advanced Recovery Companion e seguire le istruzioni per completare il reflash.</span><span class="sxs-lookup"><span data-stu-id="bacb3-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="bacb3-170">Procedura manuale</span><span class="sxs-lookup"><span data-stu-id="bacb3-170">Manual procedure</span></span>

<span data-ttu-id="bacb3-171">Se il HoloLens 2 non viene avviato correttamente o se Advanced Recovery Companion non riesce a rilevare il dispositivo, potrebbe essere necessario impostare il dispositivo in modalità di ripristino:</span><span class="sxs-lookup"><span data-stu-id="bacb3-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="bacb3-172">Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.</span><span class="sxs-lookup"><span data-stu-id="bacb3-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="bacb3-173">Tenere premuto il **pulsante** di alimentazione per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="bacb3-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="bacb3-174">Tutti i LED devono essere spenti.</span><span class="sxs-lookup"><span data-stu-id="bacb3-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="bacb3-175">Mentre si preme il **pulsante di** accensione del volume, premere e **rilasciare** il pulsante di accensione per avviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bacb3-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="bacb3-176">Attendere 15 secondi e quindi rilasciare il **pulsante volume up.**</span><span class="sxs-lookup"><span data-stu-id="bacb3-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="bacb3-177">Solo il LED centrale dei cinque LED si accende.</span><span class="sxs-lookup"><span data-stu-id="bacb3-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="bacb3-178">Connessione il dispositivo nel PC host e aprire Gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bacb3-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="bacb3-179">Ad esempio Windows 10 premere il **Windows** e quindi **il tasto X** e quindi selezionare **Gestione dispositivi.** Assicurarsi che il dispositivo venga enumerato correttamente Microsoft HoloLens come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="bacb3-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="bacb3-181">Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="bacb3-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 schermata di reflash pulita](images/ARC2.png)

6. <span data-ttu-id="bacb3-183">Selezionare il dispositivo HoloLens 2 nell'interfaccia utente dell'app Advanced Recovery Companion e quindi seguire le istruzioni per completare il reflash.</span><span class="sxs-lookup"><span data-stu-id="bacb3-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="bacb3-184">Risolvere i problemi di Advanced Recovery Companion</span><span class="sxs-lookup"><span data-stu-id="bacb3-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="bacb3-185">Assicurarsi che al dispositivo venga addebitato un addebito del 40% o superiore prima di provare a eseguire il flashing.</span><span class="sxs-lookup"><span data-stu-id="bacb3-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="bacb3-186">Controllare che il dispositivo sia sbloccato.</span><span class="sxs-lookup"><span data-stu-id="bacb3-186">Check your device is unlocked.</span></span>

1. <span data-ttu-id="bacb3-187">Verificare che il dispositivo sia collegato direttamente al PC host, non a un hub.</span><span class="sxs-lookup"><span data-stu-id="bacb3-187">Check your device is plugged directly into the host PC, not a hub.</span></span>

1. <span data-ttu-id="bacb3-188">Se il dispositivo non viene visualizzato come dispositivo di HoloLens/HoloLens in Driver bus seriali universali, controllare:</span><span class="sxs-lookup"><span data-stu-id="bacb3-188">If your device is not showing as a HoloLens/HoloLens Recovery device under Universal Serial Bus Drivers, check:</span></span>
    1. <span data-ttu-id="bacb3-189">**Porte**, come dispositivo Qualcomm HS-USB</span><span class="sxs-lookup"><span data-stu-id="bacb3-189">**Ports**, as a Qualcomm HS-USB device</span></span>
    1.   <span data-ttu-id="bacb3-190">**Altri dispositivi**, come QUSB_BULK dispositivo: nel PC host mancano i driver necessari per rilevare il HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bacb3-190">**Other Devices**, as a QUSB_BULK device - your host PC is missing the necessary drivers to detect your HoloLens.</span></span> <span data-ttu-id="bacb3-191">Fare clic con il pulsante destro del mouse e selezionare Aggiorna driver e cercare i driver online o selezionare Aggiornamenti facoltativi nelle impostazioni Windows [Aggiorna](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674).</span><span class="sxs-lookup"><span data-stu-id="bacb3-191">Right click and select Update Driver and search for drivers online or [check Optional Updates in your Windows Update settings](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674).</span></span> <span data-ttu-id="bacb3-192">Dopo aver scaricato il driver, ARC dovrebbe essere in grado di rilevarlo.</span><span class="sxs-lookup"><span data-stu-id="bacb3-192">After the driver is downloaded, ARC should be able to detect it.</span></span>
 
1. <span data-ttu-id="bacb3-193">Se ARC non rileva il dispositivo, assicurarsi di potersi connettere al dispositivo tramite Esplora file sul PC.</span><span class="sxs-lookup"><span data-stu-id="bacb3-193">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="bacb3-194">Se non è possibile;</span><span class="sxs-lookup"><span data-stu-id="bacb3-194">If you cannot;</span></span>

    1.  <span data-ttu-id="bacb3-195">È possibile che il dispositivo abbia criteri USB che disabilitano la connessione.</span><span class="sxs-lookup"><span data-stu-id="bacb3-195">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="bacb3-196">In tal caso, provare [la modalità Flashing manuale.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="bacb3-196">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="bacb3-197">Se non sono presenti criteri, provare un cavo USB diverso.</span><span class="sxs-lookup"><span data-stu-id="bacb3-197">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="bacb3-198">Verificare che nel dispositivo non sia visualizzato un modello a [1-3-5 LED.](hololens2-setup.md#lights-to-indicate-problems)</span><span class="sxs-lookup"><span data-stu-id="bacb3-198">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="bacb3-199">Scaricare ARC senza usare l'App Store</span><span class="sxs-lookup"><span data-stu-id="bacb3-199">Download ARC without using the app store</span></span>

<span data-ttu-id="bacb3-200">Se l'ambiente IT impedisce l'uso dell'app Windows Store o limita l'accesso al negozio al dettaglio, l'amministratore IT può rendere disponibile l'app tramite un percorso di distribuzione "offline".</span><span class="sxs-lookup"><span data-stu-id="bacb3-200">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="bacb3-201">Gli amministratori IT possono anche distribuire questa app tramite System Center Configuration Manager (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="bacb3-201">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="bacb3-202">Questa guida è incentrata su Advanced Recovery Companion, ma il processo può essere usato anche per altre app "offline".</span><span class="sxs-lookup"><span data-stu-id="bacb3-202">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="bacb3-203">Per abilitare il percorso di distribuzione, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bacb3-203">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="bacb3-204">Passare [all'Microsoft Store per le aziende](https://businessstore.microsoft.com) e accedere usando un'Azure Active Directory identità.</span><span class="sxs-lookup"><span data-stu-id="bacb3-204">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="bacb3-205">Passare a **Gestisci - Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="bacb3-205">Go to **Manage – Settings**.</span></span> <span data-ttu-id="bacb3-206">Attivare Mostra **app offline in** Esperienza di **acquisto.**</span><span class="sxs-lookup"><span data-stu-id="bacb3-206">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="bacb3-207">Passare a **Cercare il gruppo e** cercare Advanced Recovery [**_Companion._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="bacb3-207">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="bacb3-208">Impostare License **Type (Tipo di** ***licenza) su* _offline_ _ e selezionare _ Manage (Gestisci).**</span><span class="sxs-lookup"><span data-stu-id="bacb3-208">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="bacb3-209">In **Scarica il pacchetto per l'uso offline** selezionare il secondo pulsante blu **Scarica.**</span><span class="sxs-lookup"><span data-stu-id="bacb3-209">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="bacb3-210">Assicurarsi che l'estensione del file *sia appxbundle.*</span><span class="sxs-lookup"><span data-stu-id="bacb3-210">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="bacb3-211">In questa fase, se il PC desktop ha accesso a Internet, fare doppio clic sul pacchetto per installare l'app.</span><span class="sxs-lookup"><span data-stu-id="bacb3-211">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="bacb3-212">Se il PC di destinazione non ha connettività Internet, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bacb3-212">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="bacb3-213">Selezionare la licenza non codificata e quindi selezionare **Genera licenza.**</span><span class="sxs-lookup"><span data-stu-id="bacb3-213">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="bacb3-214">In **Framework necessari selezionare** **Scarica.**</span><span class="sxs-lookup"><span data-stu-id="bacb3-214">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="bacb3-215">Usare Gestione e manutenzione immagini distribuzione per applicare il pacchetto con la dipendenza e la licenza.</span><span class="sxs-lookup"><span data-stu-id="bacb3-215">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="bacb3-216">Da un prompt dei comandi dell'amministratore eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="bacb3-216">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="bacb3-217">Il numero di versione in questo esempio di codice potrebbe non corrispondere alla versione attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="bacb3-217">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="bacb3-218">È anche possibile che sia stato scelto un percorso di download diverso rispetto all'esempio.</span><span class="sxs-lookup"><span data-stu-id="bacb3-218">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="bacb3-219">Apportare eventuali modifiche al comando in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="bacb3-219">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="bacb3-220">Quando si prevede di usare Advanced Recovery Companion per installare un FFU offline, può essere utile scaricare l'immagine flash.</span><span class="sxs-lookup"><span data-stu-id="bacb3-220">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="bacb3-221">[**Scaricare l'immagine corrente per HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="bacb3-221">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="bacb3-222">Altre risorse:</span><span class="sxs-lookup"><span data-stu-id="bacb3-222">Other resources:</span></span>
- [<span data-ttu-id="bacb3-223">Distribuire app offline</span><span class="sxs-lookup"><span data-stu-id="bacb3-223">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="bacb3-224">Opzioni della riga di comando per la manutenzione del pacchetto dell'app Gestione e manutenzione immagini distribuzione (con estensione appx o appxbundle)</span><span class="sxs-lookup"><span data-stu-id="bacb3-224">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
