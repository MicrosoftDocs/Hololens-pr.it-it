---
title: Riavviare, reimpostare o ripristinare HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857764"
---
# <span data-ttu-id="277f4-104">Riavviare, reimpostare o ripristinare HoloLens</span><span class="sxs-lookup"><span data-stu-id="277f4-104">Restart, reset, or recover HoloLens</span></span>

## <span data-ttu-id="277f4-105">Ricaricare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="277f4-105">Charging the device</span></span>

<span data-ttu-id="277f4-106">Prima di avviare una procedura di risoluzione dei problemi, se possibile, assicurati che il dispositivo sia caricato almeno tra il 20% e il 40%.</span><span class="sxs-lookup"><span data-stu-id="277f4-106">Before starting any troubleshooting procedure, if possible, ensure that your device is charged at least between 20% and 40%.</span></span>

<span data-ttu-id="277f4-107">Assicurati di usare il caricabatterie e i cavi USB di tipo C forniti insieme al dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="277f4-107">Please ensure you are using the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="277f4-108">Nel caso in cui non siano disponibili, assicurati che il caricabatterie disponibile possa supportare almeno 15 W di potenza.</span><span class="sxs-lookup"><span data-stu-id="277f4-108">In case they are not available ensure the charger available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="277f4-109">Se possibile, non usare un PC per caricare il dispositivo tramite USB, perché i tempi di ricarica sono molti lunghi.</span><span class="sxs-lookup"><span data-stu-id="277f4-109">If possible, do not use a PC to charge the device over USB as this will provide a very slow charge.</span></span>

<span data-ttu-id="277f4-110">Se il dispositivo viene avviato correttamente ed è in esecuzione, puoi controllare la ricarica della tua batteria in tre modi.</span><span class="sxs-lookup"><span data-stu-id="277f4-110">If the device is correctly booted and running there are three different ways of checking the charge of your battery.</span></span>

1. <span data-ttu-id="277f4-111">Andando nel menu principale dell’interfaccia utente di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="277f4-111">From the main menu of the HoloLens Device UI.</span></span>
2. <span data-ttu-id="277f4-112">Controllando il LED che si trova vicino al tasto di accensione (per il 40%, dovresti vedere almeno due LED fissi). </span><span class="sxs-lookup"><span data-stu-id="277f4-112">Using the LED close to the power button (for 40% you should see at least two solid LEDS).</span></span>
3. <span data-ttu-id="277f4-113">Aprendo Esplora file nel proprio PC host, e cercando il dispositivo HoloLens 2 a sinistra, sotto “Questo PC”.</span><span class="sxs-lookup"><span data-stu-id="277f4-113">On your Host PC open File Explorer window and look for your HoloLens 2 device on left side under “This PC”.</span></span>
    
      <span data-ttu-id="277f4-114">a.</span><span class="sxs-lookup"><span data-stu-id="277f4-114">a.</span></span> <span data-ttu-id="277f4-115">Fai clic con il pulsante destro del mouse sul nome del dispositivo e scegli Proprietà.</span><span class="sxs-lookup"><span data-stu-id="277f4-115">Right click on the name of the device and select properties.</span></span> <span data-ttu-id="277f4-116">Viene mostrata una finestra di dialogo che mostra il livello della batteria per il dispositivo in uso.</span><span class="sxs-lookup"><span data-stu-id="277f4-116">A dialog will appear showing the battery level for your device.</span></span>

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

<span data-ttu-id="277f4-118">Se non è possibile avviare il dispositivo nel menu di avvio, prendi nota dei LED e della numerazione del PC host, e segui la Guida alla risoluzione dei problemi (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="277f4-118">If the device cannot be booted to the Startup Menu, please take note of the LEDs and enumeration on the host PC and follow the troubleshooting guide (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="277f4-119">Se lo stato del dispositivo non rientra in uno degli stati elencati nella Guida alla risoluzione dei problemi, esegui la **procedura di reimpostazione** senza riconnettere il dispositivo al PC host, ma connetterlo all’alimentazione.</span><span class="sxs-lookup"><span data-stu-id="277f4-119">In case the state of the device does not fall in any of the states listed in the troubleshooting guide, execute the **hard reset procedure** without reconnecting the device to your host PC, but connect it instead to the power supply.</span></span> <span data-ttu-id="277f4-120">Attendere almeno un’ora che il dispositivo si ricarichi.</span><span class="sxs-lookup"><span data-stu-id="277f4-120">Wait for at least one hour for the device to charge.</span></span>

## <span data-ttu-id="277f4-121">Reimpostare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="277f4-121">Reset the device</span></span>

<span data-ttu-id="277f4-122">In alcuni casi, all’utente può essere richiesto di reimpostare manualmente il dispositivo, senza l’interfaccia utente del software.</span><span class="sxs-lookup"><span data-stu-id="277f4-122">Under certain circumstances the customer may be required to manually reset the device without using the SW UI.</span></span> 

### <span data-ttu-id="277f4-123">Procedura standard</span><span class="sxs-lookup"><span data-stu-id="277f4-123">Standard procedure</span></span>
1. <span data-ttu-id="277f4-124">Scollega il dispositivo dall’alimentatore o dal PC host scollegando il cavo di tipo C.</span><span class="sxs-lookup"><span data-stu-id="277f4-124">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="277f4-125">Tieni premuto il **tasto di accensione** per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="277f4-125">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="277f4-126">Tutti i LED devono essere spenti.</span><span class="sxs-lookup"><span data-stu-id="277f4-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="277f4-127">Attendi 2-3 secondi e premi brevemente il **pulsante di accensione**, i LED vicini al pulsante di accensione si accendono e il dispositivo inizia ad avviarsi.</span><span class="sxs-lookup"><span data-stu-id="277f4-127">Wait 2-3 seconds and Short press the **power button**, the LEDs close to the power button will light up and the device will start to boot.</span></span> 

4. <span data-ttu-id="277f4-128">Connetti il dispositivo al PC host aprendo Gestione dispositivi (su Windows 10, premi il tasto **“Windows”** e quindi **“x”**, e fai poi clic su “Gestione dispositivi”) verificando che il dispositivo sia correttamente indicato come Microsoft HoloLens, come mostrato nelle immagini seguenti:</span><span class="sxs-lookup"><span data-stu-id="277f4-128">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below:</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="277f4-130">Procedura di reimpostazione manuale</span><span class="sxs-lookup"><span data-stu-id="277f4-130">Hard-reset procedure</span></span>

<span data-ttu-id="277f4-131">Se la procedura di reimpostazione standard non funziona, è possibile usare la procedura di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="277f4-131">If the standard reset procedure does not work, you can use the hard-reset procedure.</span></span>

1. <span data-ttu-id="277f4-132">Scollega il dispositivo dall’alimentatore o dal PC host scollegando il cavo di tipo C.</span><span class="sxs-lookup"><span data-stu-id="277f4-132">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="277f4-133">Tieni premuto **volume giù + tasto di accensione** per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="277f4-133">Hold **volume down + power button** for 15 seconds.</span></span>

3. <span data-ttu-id="277f4-134">Il dispositivo viene riavviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="277f4-134">The device will automatically reboot.</span></span> 

4. <span data-ttu-id="277f4-135">Connetti il dispositivo al PC host aprendo Gestione dispositivi (su Windows 10, premi il tasto **“Windows”** e quindi **“x”**, e fai poi clic su “Gestione dispositivi”) verificando che il dispositivo sia correttamente indicato come Microsoft HoloLens, come mostrato nelle immagini seguenti.</span><span class="sxs-lookup"><span data-stu-id="277f4-135">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="277f4-137">Ripristino manuale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="277f4-137">Clean reflash the device</span></span>

<span data-ttu-id="277f4-138">In situazioni straordinarie potrebbe essere necessario ripristinare manualmente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="277f4-138">In extraordinary situations you may be required to clean flash the device.</span></span> <span data-ttu-id="277f4-139">Ci sono due modi per ripristinare un dispositivo HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="277f4-139">There are two ways to reflash a HoloLens2 device.</span></span> <span data-ttu-id="277f4-140">Per tutte le procedure di ripristino, ti verrà chiesto di [installare l’app Advanced Recovery Companion tramite Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="277f4-140">For all reflashing procedures you will be required to [install the Advanced Recovery Companion app from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> <span data-ttu-id="277f4-141">Se si ripristina il dispositivo, tutti i dati personali, le app e le impostazioni verranno eliminati, compreso il ripristino del TPM.</span><span class="sxs-lookup"><span data-stu-id="277f4-141">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span>

<span data-ttu-id="277f4-142">Advanced Recovery Companion scarica automaticamente la build di [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004). Se desideri scaricare il file FFU più recente di HoloLens 2 per ripristinare il dispositivo con Advanced Recovery Companion, lo puoi scaricare da [qui](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="277f4-142">Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), if you would like to download the latest HoloLens 2 FFU to flash your device via Advanced Recovery Companion then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="277f4-143">Il file FFU viene tenuto aggiornato, e corrisponde alla build più recente disponibile.</span><span class="sxs-lookup"><span data-stu-id="277f4-143">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="277f4-144">Prima di avviare la procedura di ripristino, verifica che l’app sia installata ed in esecuzione nel PC con Windows 10, e che sia pronta a rilevare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="277f4-144">Before starting the flashing procedure make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Ripristino manuale di HoloLens 2](images/ARC1.png)

### <span data-ttu-id="277f4-146">Procedura normale</span><span class="sxs-lookup"><span data-stu-id="277f4-146">Normal procedure</span></span>

1. <span data-ttu-id="277f4-147">Mentre il dispositivo HoloLens è acceso, connetterlo a un PC con Windows 10 su cui l’app Advanced Recovery Companion sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="277f4-147">While the HoloLens device is running, connect it to your Windows 10 PC where you previously launched the Advanced Recovery Companion App.</span></span>

2. <span data-ttu-id="277f4-148">Il dispositivo verrà rilevato automaticamente, e l’interfaccia utente dell'app Advanced Recovery Companion sarà aggiornata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="277f4-148">The device will automatically be detected and the Advanced Recovery Companion App UI will update as follows:</span></span>

![Ripristino manuale di HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="277f4-150">Seleziona il dispositivo HoloLens2 nell’interfaccia dell'app Advanced Recovery Companion, e segui le istruzioni per completare il ripristino.</span><span class="sxs-lookup"><span data-stu-id="277f4-150">Select the HoloLens2 device in the Advanced Recovery Companion App UI and follow the instructions to complete the flashing.</span></span>

### <span data-ttu-id="277f4-151">Procedura manuale</span><span class="sxs-lookup"><span data-stu-id="277f4-151">Manual procedure</span></span>

<span data-ttu-id="277f4-152">Se il dispositivo non si avvia correttamente, potrebbe essere necessario attivare la modalità di ripristino sull’HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="277f4-152">If the device does not boot correctly you may need to put the HoloLens 2 device in Recovery mode.</span></span>

1. <span data-ttu-id="277f4-153">Scollega il dispositivo dall’alimentatore o dal PC host scollegando il cavo di tipo C.</span><span class="sxs-lookup"><span data-stu-id="277f4-153">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span> 

2. <span data-ttu-id="277f4-154">Tieni premuto il **tasto di accensione** per 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="277f4-154">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="277f4-155">Tutti i LED devono spegnersi.</span><span class="sxs-lookup"><span data-stu-id="277f4-155">All LEDs should turn off.</span></span> 

3. <span data-ttu-id="277f4-156">Mentre premi il pulsante **Volume più**, premi e rilascia il **tasto di accensione** per avviare il boot sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="277f4-156">While pressing the **volume up button**, press and release the **power button** to boot the device.</span></span> <span data-ttu-id="277f4-157">Attendi 15 secondi prima di rilasciare il pulsante Volume più.</span><span class="sxs-lookup"><span data-stu-id="277f4-157">Wait 15 seconds before releasing the volume up button.</span></span> <span data-ttu-id="277f4-158">Dei 5 LED che si trovano sul dispositivo, si accende soltanto il LED centrale.</span><span class="sxs-lookup"><span data-stu-id="277f4-158">Out of the 5 LEDs on the device, only the middle LED will light up.</span></span>

4. <span data-ttu-id="277f4-159">Connetti il dispositivo al PC host aprendo Gestione dispositivi (su Windows 10, premi il tasto **“Windows”** e quindi **“x”**, e fai poi clic su “Gestione dispositivi”) verificando che il dispositivo sia correttamente indicato come Microsoft HoloLens, come mostrato nell’immagine sottostante.</span><span class="sxs-lookup"><span data-stu-id="277f4-159">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the image below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. <span data-ttu-id="277f4-161">Il dispositivo viene rilevato automaticamente, e l'interfaccia utente dell’app Advanced Recovery Companion viene aggiornata come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="277f4-161">The device will be automatically detected, and the Advanced Recovery Companion app UI will update as follows:</span></span>

![Ripristino manuale di HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="277f4-163">Seleziona il dispositivo HoloLens 2 nell’interfaccia dell’app Advanced Recovery Companion, e segui le istruzioni per completare il ripristino.</span><span class="sxs-lookup"><span data-stu-id="277f4-163">Select the HoloLens 2 device in the Advanced Recovery Companion app UI and follow the instructions to complete the flashing.</span></span>

## <span data-ttu-id="277f4-164">Download di ARC senza usare Windows Store</span><span class="sxs-lookup"><span data-stu-id="277f4-164">Downloading ARC without using the app store</span></span>

<span data-ttu-id="277f4-165">Se un ambiente IT impedisce l'uso dell’app Windows Store o limita l'accesso al negozio online, gli amministratori IT possono rendere disponibile l’app attraverso altri percorsi di distribuzione offline.</span><span class="sxs-lookup"><span data-stu-id="277f4-165">If an IT environment prevents the use of the Windows Store app or limits access to the retail store, IT administrators can make this app available through other ‘offline’ deployment paths.</span></span> 

- <span data-ttu-id="277f4-166">Questo processo può essere usato anche per altre app, come illustrato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="277f4-166">This process may also be used for other apps, as seen in step 2.</span></span> <span data-ttu-id="277f4-167">Questa guida si concentra sulle funzionalità avanzate di ripristino, ma è possibile modificarle per altre app offline.</span><span class="sxs-lookup"><span data-stu-id="277f4-167">This guide will focus on Advanced Recovery Companion, but my be modified for other offline apps.</span></span>  

<span data-ttu-id="277f4-168">Questo percorso di distribuzione può essere abilitato con la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="277f4-168">This deployment path can be enabled with the following steps:</span></span>
1.  <span data-ttu-id="277f4-169">Vai al sito web di [Store For Business](https://businessstore.microsoft.com) e accedi con un’identità di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="277f4-169">Go to the [Store For Business website](https://businessstore.microsoft.com) and sign-in with an Azure AD identity.</span></span>
1.  <span data-ttu-id="277f4-170">Vai a **Gestione – Impostazioni**, e attiva **Mostra app offline** in **Esperienza di shopping** come descritto in https://businessstore.microsoft.com/manage/settings/shop</span><span class="sxs-lookup"><span data-stu-id="277f4-170">Go to **Manage – Settings**, and turn on **Show offline apps** under **Shopping experience** as described at https://businessstore.microsoft.com/manage/settings/shop</span></span> 
1.  <span data-ttu-id="277f4-171">Vai **Compra per il gruppo** e cerca l’app [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="277f4-171">Go to **shop for my group** and search for the [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) app.</span></span>
1.  <span data-ttu-id="277f4-172">Cambia il valore della casella **Tipo licenza** su offline e fai clic su **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="277f4-172">Change the **License Type** box to offline and click **Manage**.</span></span>
1.  <span data-ttu-id="277f4-173">Nella sezione “Scarica il pacchetto per l’uso offline”, fai clic sul pulsante **“Scarica”**.</span><span class="sxs-lookup"><span data-stu-id="277f4-173">Under Download the package for offline use click the second blue **“Download”** button .</span></span> <span data-ttu-id="277f4-174">Verifica che l’estensione del file sia .appxbundle.</span><span class="sxs-lookup"><span data-stu-id="277f4-174">Ensure the file extension is .appxbundle.</span></span>
1.  <span data-ttu-id="277f4-175">In questa fase, se il PC desktop è connesso a internet, ti basta fare doppio clic e installarlo.</span><span class="sxs-lookup"><span data-stu-id="277f4-175">At this stage, if the Desktop PC has Internet access, simply double click and install.</span></span> 
1.  <span data-ttu-id="277f4-176">Gli amministratori IT possono anche distribuire l’app con System Center Configuration Manager (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="277f4-176">The IT administrator can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
1.  <span data-ttu-id="277f4-177">Se il PC di destinazione non può connettersi a internet, sono necessari alcuni passaggi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="277f4-177">If the target PC has no Internet connectivity, some additional steps are needed:</span></span> 
    1.  <span data-ttu-id="277f4-178">Seleziona la licenza non codificata e fai clic su **“Genera licenza”**, e clicca poi su **“Scarica”** in **“Framework necessari”**.</span><span class="sxs-lookup"><span data-stu-id="277f4-178">Select the unencoded license and click **“Generate license”** and under **“Required Frameworks”** click **“Download.”**</span></span> 
    1.  <span data-ttu-id="277f4-179">I PC senza accesso a internet dovranno usare DISM per applicare il pacchetto con i file e la licenza.</span><span class="sxs-lookup"><span data-stu-id="277f4-179">PCs without internet access will need to use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="277f4-180">In un prompt dei comandi con privilegi di amministrazione, scrivi:</span><span class="sxs-lookup"><span data-stu-id="277f4-180">In an administrator command prompt, type:</span></span>

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> <span data-ttu-id="277f4-181">Il numero della versione di questo codice d’esempio potrebbe non corrispondere alla versione effettiva.</span><span class="sxs-lookup"><span data-stu-id="277f4-181">The version number in this code example may not match the currently avalible version.</span></span> <span data-ttu-id="277f4-182">Puoi anche specificare un percorso di scaricamento diverso da quello mostrato nell’esempio.</span><span class="sxs-lookup"><span data-stu-id="277f4-182">You may have also choosen a different download location than in the example given.</span></span> <span data-ttu-id="277f4-183">Assicurati di apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="277f4-183">Please make sure to make any changes as needed.</span></span>

> [!TIP]
> <span data-ttu-id="277f4-184">Se pianifichi di usare Advanced Recovery Companion per installare un file FFU offline, può essere utile scaricare localmente l’immagine di ripristino: qui trovi [il file immagine più recente di HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="277f4-184">When planning to use Advanced Recovery Companion to install an ffu offline it may be useful to download your flashing image to be availible, here is the [current image for HoloLens 2](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="277f4-185">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="277f4-185">Other resources:</span></span>
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


