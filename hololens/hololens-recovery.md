---
title: Riavviare, reimpostare o ripristinare HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Come usare Advanced Recovery Companion per installare un file immagine su HoloLens 2.
keywords: guida, riavvio, reset, ripristino, ripristino manuale, ripristino automatico, ciclo di alimentazione, HoloLens, spegnimento, arc, advanced recovery companion
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
ms.openlocfilehash: 872e9d3445df2601579ae81f4190458289fa2eea
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195599"
---
# <span data-ttu-id="5b6db-104">Riavviare, reimpostare o ripristinare HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5b6db-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="5b6db-105">Caricare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="5b6db-105">Charge the device</span></span>

<span data-ttu-id="5b6db-106">Prima di avviare una procedura di risoluzione dei problemi, accertarsi che il dispositivo sia caricato almeno dal 20 al 40% della capacità della batteria, se possibile.</span><span class="sxs-lookup"><span data-stu-id="5b6db-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="5b6db-107">Assicurarsi di usare il caricabatterie e i cavi USB di tipo C forniti insieme al dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b6db-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="5b6db-108">L'alimentatore e il cavo USB da C a C forniti con il dispositivo sono il modo migliore per ricaricare HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b6db-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="5b6db-109">Il caricabatterie fornisce 18 W di alimentazione (9V a 2A).</span><span class="sxs-lookup"><span data-stu-id="5b6db-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="5b6db-110">Ove questi non fossero disponibili, assicurarsi che il caricabatterie disponibile possa supportare almeno 15 W di potenza.</span><span class="sxs-lookup"><span data-stu-id="5b6db-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="5b6db-111">Se possibile, evitare di usare un PC per caricare il dispositivo tramite USB, visto che tale processo sarebbe lento.</span><span class="sxs-lookup"><span data-stu-id="5b6db-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="5b6db-112">Se il dispositivo viene avviato correttamente ed è in esecuzione, è possibile controllare il livello di carica della batteria in tre modi:</span><span class="sxs-lookup"><span data-stu-id="5b6db-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="5b6db-113">Dal menu principale dell’interfaccia utente di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5b6db-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="5b6db-114">Controllare il LED che si trova vicino al tasto di accensione (con il 40% di carica, si dovrebbero vedere almeno due LED fissi). </span><span class="sxs-lookup"><span data-stu-id="5b6db-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="5b6db-115">Quando il dispositivo è in carica, l'indicatore della batteria si illumina per indicare il livello di carica corrente.</span><span class="sxs-lookup"><span data-stu-id="5b6db-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="5b6db-116">L'ultima luce si accenderà e spegnerà per indicare che la ricarica è attiva.</span><span class="sxs-lookup"><span data-stu-id="5b6db-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="5b6db-117">Quando il dispositivo HoloLens è acceso, l'indicatore della batteria mostra il livello di batteria in cinque incrementi.</span><span class="sxs-lookup"><span data-stu-id="5b6db-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="5b6db-118">Quando solo una delle cinque luci è accesa, il livello della batteria è inferiore al 20%.</span><span class="sxs-lookup"><span data-stu-id="5b6db-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="5b6db-119">Se il livello della batteria è molto basso e tenti di accendere il dispositivo, una luce lampeggia per un breve periodo, quindi scompare.</span><span class="sxs-lookup"><span data-stu-id="5b6db-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="5b6db-120">Aprire **Esplora file** sul proprio PC host, e cercare il dispositivo HoloLens 2 a sinistra, sotto **Questo PC**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="5b6db-121">Fare clic con il pulsante destro del mouse sul dispositivo e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="5b6db-122">Una finestra di dialogo mostrerà il livello di carica della batteria.</span><span class="sxs-lookup"><span data-stu-id="5b6db-122">A dialog box will show the battery charge level.</span></span>

   ![Schermata delle proprietà di HoloLens 2 che mostra il livello di variazione della batteria](images/ResetRecovery2.png)

<span data-ttu-id="5b6db-124">Se il dispositivo non riesce a eseguire il boot al menu di avvio, prendere nota dell'aspetto del LED e dell'elenco dei dispositivi sul PC host.</span><span class="sxs-lookup"><span data-stu-id="5b6db-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="5b6db-125">Seguire quindi le [istruzioni per la risoluzione dei problemi](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="5b6db-125">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="5b6db-126">Se lo stato del dispositivo non rientra tra quelli elencati nella guida alla risoluzione dei problemi, eseguire la [procedura di reimpostazione forzata](hololens-recovery.md#hard-reset-procedure) connettendo il dispositivo all’alimentazione anziché al PC host.</span><span class="sxs-lookup"><span data-stu-id="5b6db-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="5b6db-127">Attendere almeno un’ora che il dispositivo si ricarichi.</span><span class="sxs-lookup"><span data-stu-id="5b6db-127">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="5b6db-128">Reimpostare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="5b6db-128">Reset the device</span></span>

<span data-ttu-id="5b6db-129">In alcuni casi, all’utente può essere richiesto di reimpostare manualmente il dispositivo, senza l’utilizzo dell’interfaccia utente del software.</span><span class="sxs-lookup"><span data-stu-id="5b6db-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="5b6db-130">Procedura standard</span><span class="sxs-lookup"><span data-stu-id="5b6db-130">Standard procedure</span></span>
1. <span data-ttu-id="5b6db-131">Scollegare il dispositivo dall’alimentatore o dal PC host scollegando il cavo di Tipo C.</span><span class="sxs-lookup"><span data-stu-id="5b6db-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="5b6db-132">Tenere premuto il pulsante di **accensione** per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="5b6db-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="5b6db-133">Tutti i LED devono essere spenti.</span><span class="sxs-lookup"><span data-stu-id="5b6db-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="5b6db-134">Attendere 2-3 secondi, quindi premere brevemente il pulsante di **accensione**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="5b6db-135">I LED vicini al pulsante di accensione si accenderanno e il dispositivo inizierà ad avviarsi.</span><span class="sxs-lookup"><span data-stu-id="5b6db-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="5b6db-136">Connettere il dispositivo al PC host e quindi aprire Gestione Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b6db-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="5b6db-137">(Per Windows 10, premere il tasto **Windows** e quindi il tasto **X**, selezionando successivamente **Gestione Dispositivo**.) Verificare che il dispositivo sia correttamente indicato come *Microsoft HoloLens* come mostrato nell’immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="5b6db-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery device manager](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="5b6db-139">Procedura di reimpostazione manuale</span><span class="sxs-lookup"><span data-stu-id="5b6db-139">Hard-reset procedure</span></span>

<span data-ttu-id="5b6db-140">Se la procedura di reimpostazione standard non funziona, è possibile usare la procedura di reimpostazione forzata:</span><span class="sxs-lookup"><span data-stu-id="5b6db-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="5b6db-141">Scollegare il dispositivo dall’alimentatore o dal PC host scollegando il cavo di Tipo C.</span><span class="sxs-lookup"><span data-stu-id="5b6db-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="5b6db-142">Tenere premuti i pulsanti **volume verso il basso** + e**accensione** per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="5b6db-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="5b6db-143">Il dispositivo verrà riavviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5b6db-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="5b6db-144">Connettere il dispositivo al PC host.</span><span class="sxs-lookup"><span data-stu-id="5b6db-144">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="5b6db-145">Aprire Gestione Dispositivo (per Windows 10 premere il tasto **Windows** e quindi **X** e successivamente selezionare **Gestione Dispositivo**).</span><span class="sxs-lookup"><span data-stu-id="5b6db-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="5b6db-146">Verificare che il dispositivo sia correttamente indicato come *Microsoft HoloLens* come mostrato nell’immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="5b6db-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery device manager 2](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="5b6db-148">Riconfigurare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="5b6db-148">Clean-reflash the device</span></span>

<span data-ttu-id="5b6db-149">In situazioni straordinarie potrebbe essere necessario riconfigurare HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b6db-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="5b6db-150">Tenere presente che la riconfigurazione non condiziona questi problemi:</span><span class="sxs-lookup"><span data-stu-id="5b6db-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="5b6db-151">Uniformità del colore dello schermo</span><span class="sxs-lookup"><span data-stu-id="5b6db-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="5b6db-152">Avvio con i suoni ma senza segnale video</span><span class="sxs-lookup"><span data-stu-id="5b6db-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="5b6db-153">Pattern LED 1-3-5</span><span class="sxs-lookup"><span data-stu-id="5b6db-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="5b6db-154">Surriscaldamento</span><span class="sxs-lookup"><span data-stu-id="5b6db-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="5b6db-155">Arresti anomali del sistema operativo (distinti dagli arresti delle applicazioni)</span><span class="sxs-lookup"><span data-stu-id="5b6db-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="5b6db-156">Ci sono due modi per riconfigurare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b6db-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="5b6db-157">Per entrambi,è necessario installare prima [Advanced Recovery Companion da Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="5b6db-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="5b6db-158">Se si riconfigura il dispositivo, tutti i dati personali, le app e le impostazioni verranno eliminate, comprese le informazioni sul ripristino del TPM.</span><span class="sxs-lookup"><span data-stu-id="5b6db-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="5b6db-159">Per impostazione predefinita, Advanced Recovery Companion è impostato per scaricare la build dell'ultimo release funzionale, controllare qui per leggere le [Note sulla versione](hololens-release-notes.md#) per informazioni sull'ultimo release funzionale.</span><span class="sxs-lookup"><span data-stu-id="5b6db-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="5b6db-160">Per ottenere il pacchetto più recente di HoloLens 2 Full Flash Update (FFU) per reflashare il dispositivo tramite Advanced Recovery Companion, [fare clic qui per scaricare l'ultima immagine mensile di HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="5b6db-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="5b6db-161">Questa versione è generalmente la build più recente disponibile.</span><span class="sxs-lookup"><span data-stu-id="5b6db-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="5b6db-162">Prima di avviare la procedura di riconfigurazione, assicurarsi che l’app sia installata ed in esecuzione su un PC dotato di Windows 10 e pronto a rilevare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b6db-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Schermata di riconfigurazione di HoloLens 2](images/ARC1.png)

### <span data-ttu-id="5b6db-164">Procedura normale</span><span class="sxs-lookup"><span data-stu-id="5b6db-164">Normal procedure</span></span>

1. <span data-ttu-id="5b6db-165">Mentre il dispositivo HoloLens è acceso, connetterlo a un PC dotato di Windows 10 su cui l’app Advanced Recovery Companion sia già in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5b6db-165">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="5b6db-166">Il dispositivo verrà rilevato automaticamente, e l'interfaccia utente dell’app Advanced Recovery Companion avvierà l’aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="5b6db-166">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Schermata iniziale di riconfigurazione di HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="5b6db-168">Seleziona il dispositivo HoloLens 2 nell’interfaccia dell’app Advanced Recovery Companion, e segui le istruzioni per completare la riconfigurazione.</span><span class="sxs-lookup"><span data-stu-id="5b6db-168">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="5b6db-169">Procedura manuale</span><span class="sxs-lookup"><span data-stu-id="5b6db-169">Manual procedure</span></span>

<span data-ttu-id="5b6db-170">Se HoloLens 2 non si avvia correttamente, potrebbe essere necessario attivare la modalità di ripristino:</span><span class="sxs-lookup"><span data-stu-id="5b6db-170">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="5b6db-171">Scollegare il dispositivo dall’alimentatore o dal PC host scollegando il cavo di Tipo C.</span><span class="sxs-lookup"><span data-stu-id="5b6db-171">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="5b6db-172">Tenere premuto il pulsante di **accensione** per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="5b6db-172">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="5b6db-173">Tutti i LED devono spegnersi.</span><span class="sxs-lookup"><span data-stu-id="5b6db-173">All LEDs should turn off.</span></span>

3. <span data-ttu-id="5b6db-174">Mentre si tiene premuto il pulsante **volume verso l’alto**, premere e rilasciare il tasto di **accensione** per avviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b6db-174">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="5b6db-175">Attendere 15 secondi e, successivamente, rilasciare il pulsante **volume verso l’alto**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-175">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="5b6db-176">Dei cinque LED, dovrebbe illuminarsi solo quello centrale.</span><span class="sxs-lookup"><span data-stu-id="5b6db-176">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="5b6db-177">Connettere il dispositivo al PC host e aprire Gestione Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b6db-177">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="5b6db-178">(Per Windows 10, premere il tasto **Windows** e quindi il tasto **X**, selezionando successivamente **Gestione Dispositivo**.) Verificare che il dispositivo sia correttamente indicato come Microsoft HoloLens come mostrato nell’immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="5b6db-178">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="5b6db-180">Il dispositivo verrà rilevato automaticamente, e l'interfaccia utente dell’app Advanced Recovery Companion avvierà l’aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="5b6db-180">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Schermo di riconfigurazione di HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="5b6db-182">Selezionare il dispositivo HoloLens 2 nell’interfaccia utente dell’app Advanced Recovery Companion e seguire le istruzioni per completare la riconfigurazione.</span><span class="sxs-lookup"><span data-stu-id="5b6db-182">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="5b6db-183">Download di ARC senza l’utilizzo dell’app store</span><span class="sxs-lookup"><span data-stu-id="5b6db-183">Download ARC without using the app store</span></span>

<span data-ttu-id="5b6db-184">Se l’ambiente IT impedisce l'uso dell’app Windows Store o limita l'accesso al negozio online, gli amministratori IT possono rendere disponibile l’app attraverso altri percorsi di distribuzione offline.</span><span class="sxs-lookup"><span data-stu-id="5b6db-184">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="5b6db-185">Gli amministratori IT possono anche distribuire l’app attraverso il System Center Configuration Manager (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="5b6db-185">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="5b6db-186">Questa guida si concentra sull’Advanced Recovery Companion, ma è possibile utilizzare lo stesso processo per altre app “offline”.</span><span class="sxs-lookup"><span data-stu-id="5b6db-186">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="5b6db-187">Per abilitare il percorso di distribuzione, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="5b6db-187">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="5b6db-188">Passare al [Microsoft Store per le aziende](https://businessstore.microsoft.com) ed accedere usando un'identità Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b6db-188">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="5b6db-189">Passare a **Gestione-impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-189">Go to **Manage – Settings**.</span></span> <span data-ttu-id="5b6db-190">Attivare **Mostra le app offline** **nell’esperienza Shopping**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-190">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="5b6db-191">Accedere a **Shop for My Group**e cercare [ \* *_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="5b6db-191">Go to **shop for my group**, and search for [\**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="5b6db-192">Cambiare il _ *tipo di licenza*\* in \**_offline_*_ e selezionare _ \* Manage \* \*.</span><span class="sxs-lookup"><span data-stu-id="5b6db-192">Change the _*License Type*\* to \**_offline_*_, and select _\*Manage\*\*.</span></span>
1. <span data-ttu-id="5b6db-193">In **Scarica il pacchetto per l’uso offline**, selezionare il pulsante **Download**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-193">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="5b6db-194">Verificare che l’estensione del file sia *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="5b6db-194">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="5b6db-195">A questo punto, se il PC è connesso a internet, un doppio clic sul pacchetto avvierà l’installazione dell’app.</span><span class="sxs-lookup"><span data-stu-id="5b6db-195">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="5b6db-196">Se il PC non è connesso a Internet, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="5b6db-196">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="5b6db-197">Selezionare la licenza decodificata e quindi selezionare **Crea licenza**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-197">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="5b6db-198">In **Framework Necessari**, selezionare **Download**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-198">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="5b6db-199">Usare DISM per applicare al pacchetto la dipendenza e la licenza.</span><span class="sxs-lookup"><span data-stu-id="5b6db-199">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="5b6db-200">Da un prompt dei comandi con privilegi di amministratore, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="5b6db-200">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="5b6db-201">Il numero della versione di questo codice d’esempio potrebbe non corrispondere alla versione attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="5b6db-201">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="5b6db-202">Si potrebbe aver scelto anche un percorso di download diverso da quello mostrato nell’esempio.</span><span class="sxs-lookup"><span data-stu-id="5b6db-202">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="5b6db-203">Modificare il comando in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="5b6db-203">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="5b6db-204">Se si prevede di usare l’Advanced Recovery Companion per installare una FFU offline, può essere utile scaricare l'immagine flash.</span><span class="sxs-lookup"><span data-stu-id="5b6db-204">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="5b6db-205">[**Scaricare l'immagine corrente per HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="5b6db-205">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="5b6db-206">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="5b6db-206">Other resources:</span></span>
- [<span data-ttu-id="5b6db-207">Distribuire app offline</span><span class="sxs-lookup"><span data-stu-id="5b6db-207">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="5b6db-208">Pacchetto di app DISM (appx o appxbundle) opzioni di manutenzione della riga di comando</span><span class="sxs-lookup"><span data-stu-id="5b6db-208">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
