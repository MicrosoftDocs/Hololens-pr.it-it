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
ms.openlocfilehash: afd782df1c68e8441b14823e0d961317914140e3
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397362"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="0bb25-104">Riavviare, reimpostare o ripristinare HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="0bb25-104">Restart, reset, or recover HoloLens 2</span></span>

## <a name="charge-the-device"></a><span data-ttu-id="0bb25-105">Caricare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="0bb25-105">Charge the device</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0bb25-106">Prima di avviare qualsiasi procedura di risoluzione dei problemi, assicurarsi che al dispositivo venga addebitato un addebito dal **20 al 40%** della capacità della batteria, se possibile.</span><span class="sxs-lookup"><span data-stu-id="0bb25-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="0bb25-107">Le [luci dell'indicatore](hololens2-setup.md#lights-that-indicate-the-battery-level) della batteria che si trovano sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bb25-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="0bb25-108">Usare il [caricabatterie](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) e il cavo USB Type-C fornito con il HoloLens 2 perché è il modo migliore per caricare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bb25-108">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="0bb25-109">Il caricabatterie fornisce 18W di alimentazione (9 V a 2A).</span><span class="sxs-lookup"><span data-stu-id="0bb25-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="0bb25-110">Usando il caricatore a parete fornito, HoloLens 2 i dispositivi possono ricaricare la batteria in meno di 65 minuti quando il dispositivo è in standby.</span><span class="sxs-lookup"><span data-stu-id="0bb25-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="0bb25-111">Se questi accessori non sono disponibili, assicurarsi che il caricabatterie disponibile supporti almeno 15W di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="0bb25-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="0bb25-112">Se possibile, evitare di usare un PC per caricare il dispositivo tramite USB, che è lento.</span><span class="sxs-lookup"><span data-stu-id="0bb25-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="0bb25-113">Se il dispositivo viene avviato e in esecuzione correttamente, è possibile controllare il livello di carica della batteria in tre modi:</span><span class="sxs-lookup"><span data-stu-id="0bb25-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="0bb25-114">Dal menu principale dell'interfaccia utente del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0bb25-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="0bb25-115">Visualizzare il LED vicino al pulsante di accensione (per un addebito del 40%, dovrebbero essere visualizzati almeno due LED solidi).</span><span class="sxs-lookup"><span data-stu-id="0bb25-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="0bb25-116">Quando il dispositivo è in carica, l'indicatore della batteria si accende per indicare il livello di carica corrente.</span><span class="sxs-lookup"><span data-stu-id="0bb25-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="0bb25-117">L'ultima luce si dissolverà in entrata e in uscita per indicare la ricarica attiva.</span><span class="sxs-lookup"><span data-stu-id="0bb25-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="0bb25-118">Quando HoloLens è on, l'indicatore della batteria visualizza il livello della batteria in cinque incrementi.</span><span class="sxs-lookup"><span data-stu-id="0bb25-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="0bb25-119">Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%.</span><span class="sxs-lookup"><span data-stu-id="0bb25-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="0bb25-120">Se il livello della batteria è criticamente basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente e quindi si spegne.</span><span class="sxs-lookup"><span data-stu-id="0bb25-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="0bb25-121">Nel PC host aprire **Esplora file** e cercare il dispositivo HoloLens 2 sul lato sinistro in Questo **PC.**</span><span class="sxs-lookup"><span data-stu-id="0bb25-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="0bb25-122">Fare clic con il pulsante destro del mouse sul dispositivo e **scegliere Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="0bb25-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="0bb25-123">Verrà visualizzata una finestra di dialogo con il livello di carica della batteria.</span><span class="sxs-lookup"><span data-stu-id="0bb25-123">A dialog box will show the battery charge level.</span></span>

   ![Una schermata HoloLens 2 proprietà mostra il livello di modifica della batteria](images/ResetRecovery2.png)

<span data-ttu-id="0bb25-125">Se il dispositivo non può essere avviato nel menu di avvio, prendere nota dell'aspetto del LED e dell'enumerazione del dispositivo nel PC host.</span><span class="sxs-lookup"><span data-stu-id="0bb25-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="0bb25-126">Seguire quindi la guida [alla risoluzione dei problemi](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="0bb25-126">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="0bb25-127">Se lo stato del dispositivo non corrisponde ad alcuno degli stati [](hololens-recovery.md#hard-reset-procedure) elencati nella guida alla risoluzione dei problemi, eseguire la procedura di ripristino con il dispositivo connesso all'alimentatore, non al PC host.</span><span class="sxs-lookup"><span data-stu-id="0bb25-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="0bb25-128">Attendere almeno un'ora per l'addebito del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bb25-128">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="0bb25-129">Reimpostare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="0bb25-129">Reset the device</span></span>

<span data-ttu-id="0bb25-130">In determinate circostanze potrebbe essere necessario reimpostare manualmente il dispositivo senza usare l'interfaccia utente del software.</span><span class="sxs-lookup"><span data-stu-id="0bb25-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="0bb25-131">Procedura standard</span><span class="sxs-lookup"><span data-stu-id="0bb25-131">Standard procedure</span></span>

1. <span data-ttu-id="0bb25-132">Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.</span><span class="sxs-lookup"><span data-stu-id="0bb25-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="0bb25-133">Tenere premuto il **pulsante di** alimentazione per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="0bb25-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="0bb25-134">Tutti i LED devono essere disattivati.</span><span class="sxs-lookup"><span data-stu-id="0bb25-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="0bb25-135">Attendere 2-3 secondi e quindi premere brevemente il **pulsante di** alimentazione.</span><span class="sxs-lookup"><span data-stu-id="0bb25-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="0bb25-136">I LED vicini al pulsante di alimentazione si accenderanno e il dispositivo inizierà ad avviarsi.</span><span class="sxs-lookup"><span data-stu-id="0bb25-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="0bb25-137">Connettere il dispositivo al PC host e quindi aprire Gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0bb25-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="0bb25-138">Ad Windows 10, premere **il tasto Windows** e quindi il tasto **X** e quindi selezionare **Gestione dispositivi.** Assicurarsi che il dispositivo enumeri correttamente *come Microsoft HoloLens* come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="0bb25-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 responsabile devivo MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="0bb25-140">Procedura di reimpostazione rigida</span><span class="sxs-lookup"><span data-stu-id="0bb25-140">Hard-reset procedure</span></span>

<span data-ttu-id="0bb25-141">Se la procedura di reimpostazione standard non ha funzionato, usare la procedura di reimpostazione rigida:</span><span class="sxs-lookup"><span data-stu-id="0bb25-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="0bb25-142">Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.</span><span class="sxs-lookup"><span data-stu-id="0bb25-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="0bb25-143">Tenere premuti **i pulsanti di risparmio**  +  **energia** del volume per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="0bb25-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="0bb25-144">Il dispositivo verrà riavviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0bb25-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="0bb25-145">Connettere il dispositivo al PC host.</span><span class="sxs-lookup"><span data-stu-id="0bb25-145">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="0bb25-146">Aprire Gestione dispositivi (per Windows 10 premere il **tasto Windows** e quindi il **tasto X** e quindi selezionare Gestione **dispositivi**).</span><span class="sxs-lookup"><span data-stu-id="0bb25-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="0bb25-147">Assicurarsi che il dispositivo venga enumerato correttamente *Microsoft HoloLens* come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="0bb25-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 dispositivo MicrosoftHoloLensRecovery maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="0bb25-149">Pulire il dispositivo</span><span class="sxs-lookup"><span data-stu-id="0bb25-149">Clean-reflash the device</span></span>

<span data-ttu-id="0bb25-150">In situazioni straordinarie, potrebbe essere necessario "pulire flash" il HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0bb25-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="0bb25-151">Si noti che clean-reflash non dovrebbe influire sui problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0bb25-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="0bb25-152">Uniformità dei colori di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="0bb25-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="0bb25-153">Avvio con audio ma nessun output di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="0bb25-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="0bb25-154">Modello a 1-3-5 LED</span><span class="sxs-lookup"><span data-stu-id="0bb25-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="0bb25-155">Surriscaldamento</span><span class="sxs-lookup"><span data-stu-id="0bb25-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="0bb25-156">Arresti anomali del sistema operativo (diversi dagli arresti anomali dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="0bb25-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="0bb25-157">Esistono due modi per eseguire il reflash del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bb25-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="0bb25-158">Per entrambi, è prima [necessario installare Advanced Recovery Companion da Windows Store.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="0bb25-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="0bb25-159">Se si rifiuta il dispositivo, tutti i dati personali, le app e le impostazioni verranno cancellati, incluse le informazioni di reimpostazione TPM.</span><span class="sxs-lookup"><span data-stu-id="0bb25-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="0bb25-160">Per impostazione predefinita, Advanced Recovery Companion è impostato per scaricare la [](hololens-release-notes.md#) build di rilascio delle funzionalità più recente. Vedere qui per leggere le note sulla versione per informazioni sulla versione più recente delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0bb25-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="0bb25-161">Per ottenere il pacchetto HoloLens 2 Full Flash Update (FFU) più recente per il reflash del dispositivo tramite Advanced Recovery Companion, fare clic qui per scaricare l'immagine HoloLens 2 [mensile più recente.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="0bb25-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="0bb25-162">Questa versione è l'ultima build disponibile a livello generale.</span><span class="sxs-lookup"><span data-stu-id="0bb25-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="0bb25-163">Prima di avviare la procedura reflash, verificare che l'app sia installata e in esecuzione nel PC Windows 10 e sia pronta per rilevare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bb25-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="0bb25-164">Assicurati anche che l'addebito di HoloLens sia minimo del 40%.</span><span class="sxs-lookup"><span data-stu-id="0bb25-164">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 schermata clean reflash](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="0bb25-166">Procedura normale</span><span class="sxs-lookup"><span data-stu-id="0bb25-166">Normal procedure</span></span>

1. <span data-ttu-id="0bb25-167">Mentre il dispositivo HoloLens è in esecuzione, connetterlo al PC Windows 10 in cui è stata aperta in precedenza l'app Complementare per il ripristino avanzato.</span><span class="sxs-lookup"><span data-stu-id="0bb25-167">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="0bb25-168">Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="0bb25-168">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 iniziale della reflash pulita](images/ARC2.png)

3. <span data-ttu-id="0bb25-170">Selezionare il HoloLens 2 nell'interfaccia utente dell'app Advanced Recovery Companion e seguire le istruzioni per completare la reflash.</span><span class="sxs-lookup"><span data-stu-id="0bb25-170">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="0bb25-171">Procedura manuale</span><span class="sxs-lookup"><span data-stu-id="0bb25-171">Manual procedure</span></span>

<span data-ttu-id="0bb25-172">Se il HoloLens 2 non viene avviato correttamente o se Advanced Recovery Companion non riesce a rilevare il dispositivo, potrebbe essere necessario impostare il dispositivo in modalità di ripristino:</span><span class="sxs-lookup"><span data-stu-id="0bb25-172">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="0bb25-173">Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.</span><span class="sxs-lookup"><span data-stu-id="0bb25-173">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="0bb25-174">Tenere premuto il **pulsante di** alimentazione per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="0bb25-174">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="0bb25-175">Tutti i LED devono essere disattivati.</span><span class="sxs-lookup"><span data-stu-id="0bb25-175">All LEDs should turn off.</span></span>

3. <span data-ttu-id="0bb25-176">Mentre si preme **il pulsante del volume** verso l'alto, premere e rilasciare il **pulsante** di alimentazione per avviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bb25-176">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="0bb25-177">Attendere 15 secondi e quindi rilasciare il **pulsante di volume** in alto.</span><span class="sxs-lookup"><span data-stu-id="0bb25-177">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="0bb25-178">Solo il LED centrale dei cinque LED si accende.</span><span class="sxs-lookup"><span data-stu-id="0bb25-178">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="0bb25-179">Connettere il dispositivo al PC host e aprire Gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0bb25-179">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="0bb25-180">Ad esempio Windows 10 premere **il tasto Windows,** quindi **il tasto X** e quindi selezionare **Gestione** dispositivi. Assicurarsi che il dispositivo venga enumerato correttamente Microsoft HoloLens come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="0bb25-180">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="0bb25-182">Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="0bb25-182">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 schermata di reflash pulita](images/ARC2.png)

6. <span data-ttu-id="0bb25-184">Selezionare il dispositivo HoloLens 2 nell'interfaccia utente dell'app Advanced Recovery Companion e quindi seguire le istruzioni per completare il reflash.</span><span class="sxs-lookup"><span data-stu-id="0bb25-184">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="0bb25-185">Risolvere i problemi di Advanced Recovery Companion</span><span class="sxs-lookup"><span data-stu-id="0bb25-185">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="0bb25-186">Assicurarsi che al dispositivo venga addebitato un addebito del 40% o superiore prima di provare a eseguire il flashing.</span><span class="sxs-lookup"><span data-stu-id="0bb25-186">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="0bb25-187">Verificare che il dispositivo sia sbloccato.</span><span class="sxs-lookup"><span data-stu-id="0bb25-187">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="0bb25-188">Se ARC non rileva il dispositivo, assicurarsi di potersi connettere al dispositivo tramite Esplora file sul PC.</span><span class="sxs-lookup"><span data-stu-id="0bb25-188">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="0bb25-189">Se non è possibile;</span><span class="sxs-lookup"><span data-stu-id="0bb25-189">If you cannot;</span></span>

    1.  <span data-ttu-id="0bb25-190">È possibile che il dispositivo abbia criteri USB che disabilitano la connessione.</span><span class="sxs-lookup"><span data-stu-id="0bb25-190">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="0bb25-191">In tal caso, provare [la modalità Flashing manuale.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="0bb25-191">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="0bb25-192">Se non sono presenti criteri, provare un cavo USB diverso.</span><span class="sxs-lookup"><span data-stu-id="0bb25-192">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="0bb25-193">Verificare che nel dispositivo non sia visualizzato un modello a [1-3-5 LED.](hololens2-setup.md#lights-to-indicate-problems)</span><span class="sxs-lookup"><span data-stu-id="0bb25-193">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="0bb25-194">Scaricare ARC senza usare l'App Store</span><span class="sxs-lookup"><span data-stu-id="0bb25-194">Download ARC without using the app store</span></span>

<span data-ttu-id="0bb25-195">Se l'ambiente IT impedisce l'uso dell'app di Windows Store o limita l'accesso al negozio al dettaglio, l'amministratore IT può rendere disponibile l'app tramite un percorso di distribuzione "offline".</span><span class="sxs-lookup"><span data-stu-id="0bb25-195">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="0bb25-196">Gli amministratori IT possono anche distribuire questa app tramite System Center Gestione configurazione (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="0bb25-196">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="0bb25-197">Questa guida è incentrata su Advanced Recovery Companion, ma il processo può essere usato anche per altre app "offline".</span><span class="sxs-lookup"><span data-stu-id="0bb25-197">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="0bb25-198">Seguire questa procedura per abilitare il percorso di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="0bb25-198">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="0bb25-199">Passare al [Microsoft Store per le aziende](https://businessstore.microsoft.com) e accedere usando un'Azure Active Directory identità.</span><span class="sxs-lookup"><span data-stu-id="0bb25-199">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="0bb25-200">Passare a **Gestisci - Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="0bb25-200">Go to **Manage – Settings**.</span></span> <span data-ttu-id="0bb25-201">Attivare Mostra **app offline in** Esperienza di **acquisto**.</span><span class="sxs-lookup"><span data-stu-id="0bb25-201">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="0bb25-202">Passare a **Cercare il gruppo e** cercare Advanced Recovery [**_Companion._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="0bb25-202">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="0bb25-203">Impostare License **Type (Tipo di** ***licenza) su* _offline_ _ e selezionare _ Manage (Gestisci).**</span><span class="sxs-lookup"><span data-stu-id="0bb25-203">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="0bb25-204">In **Scarica il pacchetto per l'uso offline** selezionare il secondo pulsante blu **Scarica.**</span><span class="sxs-lookup"><span data-stu-id="0bb25-204">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="0bb25-205">Assicurarsi che l'estensione del file *sia appxbundle.*</span><span class="sxs-lookup"><span data-stu-id="0bb25-205">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="0bb25-206">In questa fase, se il PC desktop ha accesso a Internet, fare doppio clic sul pacchetto per installare l'app.</span><span class="sxs-lookup"><span data-stu-id="0bb25-206">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="0bb25-207">Se il PC di destinazione non ha connettività Internet, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="0bb25-207">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="0bb25-208">Selezionare la licenza non codificata e quindi selezionare **Genera licenza**.</span><span class="sxs-lookup"><span data-stu-id="0bb25-208">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="0bb25-209">In **Framework necessari selezionare** **Scarica.**</span><span class="sxs-lookup"><span data-stu-id="0bb25-209">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="0bb25-210">Usare Gestione e manutenzione immagini distribuzione per applicare il pacchetto con la dipendenza e la licenza.</span><span class="sxs-lookup"><span data-stu-id="0bb25-210">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="0bb25-211">Da un prompt dei comandi dell'amministratore eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0bb25-211">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="0bb25-212">Il numero di versione in questo esempio di codice potrebbe non corrispondere alla versione attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="0bb25-212">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="0bb25-213">È anche possibile che sia stato scelto un percorso di download diverso rispetto all'esempio.</span><span class="sxs-lookup"><span data-stu-id="0bb25-213">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="0bb25-214">Apportare eventuali modifiche al comando in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="0bb25-214">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="0bb25-215">Quando si prevede di usare Advanced Recovery Companion per installare un FFU offline, può essere utile scaricare l'immagine flash.</span><span class="sxs-lookup"><span data-stu-id="0bb25-215">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="0bb25-216">[**Scaricare l'immagine corrente per HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="0bb25-216">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="0bb25-217">Altre risorse:</span><span class="sxs-lookup"><span data-stu-id="0bb25-217">Other resources:</span></span>
- [<span data-ttu-id="0bb25-218">Distribuire app offline</span><span class="sxs-lookup"><span data-stu-id="0bb25-218">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="0bb25-219">Opzioni della riga di comando per la manutenzione del pacchetto dell'app Gestione e manutenzione immagini distribuzione (con estensione appx o appxbundle)</span><span class="sxs-lookup"><span data-stu-id="0bb25-219">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
