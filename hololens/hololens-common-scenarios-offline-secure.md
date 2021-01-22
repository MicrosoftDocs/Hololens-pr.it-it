---
title: Scenari comuni - HoloLens 2 protetto offline
description: Informazioni su come configurare uno scenario di distribuzione sicura offline e di distribuzione di app con il provisioning per i dispositivi HoloLens.
keywords: HoloLens, gestione, offline, offline sicuro
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283417"
---
# <span data-ttu-id="2042d-104">Scenari comuni - HoloLens 2 protetto offline</span><span class="sxs-lookup"><span data-stu-id="2042d-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="2042d-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="2042d-105">Overview</span></span>

<span data-ttu-id="2042d-106">Questa guida fornisce indicazioni per l'applicazione di un pacchetto di provisioning di esempio che blocchi holoLens 2 per l'uso in ambienti sicuri con le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2042d-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="2042d-107">Disabilitare il WiFi.</span><span class="sxs-lookup"><span data-stu-id="2042d-107">Disable WiFi.</span></span>
-   <span data-ttu-id="2042d-108">Disabilita BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="2042d-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="2042d-109">Disabilitare i microfoni.</span><span class="sxs-lookup"><span data-stu-id="2042d-109">Disable Microphones.</span></span>
-   <span data-ttu-id="2042d-110">Impedisce l'aggiunta o la rimozione di pacchetti di provisioning.</span><span class="sxs-lookup"><span data-stu-id="2042d-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="2042d-111">Nessun utente può abilitare uno dei componenti con restrizioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2042d-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="2042d-112">Preparazione</span><span class="sxs-lookup"><span data-stu-id="2042d-112">Prepare</span></span>

<span data-ttu-id="2042d-113">Configurazione PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="2042d-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="2042d-114">Scarica il file del sistema [operativo HoloLens 2 più](https://aka.ms/hololens2download) recente direttamente in un PC.</span><span class="sxs-lookup"><span data-stu-id="2042d-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="2042d-115">Il supporto per questa configurazione è incluso nella build 19041.1117 e successive.</span><span class="sxs-lookup"><span data-stu-id="2042d-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="2042d-116">Scaricare/installare lo strumento Advanced Recovery Companion(ARC) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al PC</span><span class="sxs-lookup"><span data-stu-id="2042d-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="2042d-117">Scarica/installa l'ultimo strumento Progettazione configurazione di [Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store al PC.</span><span class="sxs-lookup"><span data-stu-id="2042d-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="2042d-118">[Scarica la OfflineSecureHL2_Sample con i file di progetto](https://aka.ms/HoloLensDocs-SecureOfflineSample) per compilare il PPKG.</span><span class="sxs-lookup"><span data-stu-id="2042d-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="2042d-119">Preparare [l'applicazione line-of-business offline per la distribuzione PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="2042d-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="2042d-120">Configura</span><span class="sxs-lookup"><span data-stu-id="2042d-120">Configure</span></span>

<span data-ttu-id="2042d-121">Creare un pacchetto di provisioning di configurazione sicura</span><span class="sxs-lookup"><span data-stu-id="2042d-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="2042d-122">Avvia lo strumento WCD nel PC.</span><span class="sxs-lookup"><span data-stu-id="2042d-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="2042d-123">Selezionare **File -> Apri progetto.**</span><span class="sxs-lookup"><span data-stu-id="2042d-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="2042d-124">Passare al percorso della cartella di OfflineSecureHL2_Sample salvata in precedenza e selezionare: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="2042d-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="2042d-125">Il progetto dovrebbe aprirsi e ora dovrebbe essere disponibile un elenco delle personalizzazioni disponibili:</span><span class="sxs-lookup"><span data-stu-id="2042d-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pacchetto di configurazione aperto in WCD](images/offline-secure-sample-wcd.png)

<span data-ttu-id="2042d-127">Configurazioni impostate in questo pacchetto di provisioning:</span><span class="sxs-lookup"><span data-stu-id="2042d-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="2042d-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="2042d-128">Item</span></span>                                                |     <span data-ttu-id="2042d-129">Impostazione</span><span class="sxs-lookup"><span data-stu-id="2042d-129">Setting</span></span>                       |     <span data-ttu-id="2042d-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2042d-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="2042d-131">Account/Utenti</span><span class="sxs-lookup"><span data-stu-id="2042d-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="2042d-132">Nome utente locale & password</span><span class="sxs-lookup"><span data-stu-id="2042d-132">Local User Name & Password</span></span>    |     <span data-ttu-id="2042d-133">Per questi dispositivi offline, un singolo nome utente e una singola password dovranno essere impostati e condivisi da tutti gli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2042d-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="2042d-134">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="2042d-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="2042d-135">True</span><span class="sxs-lookup"><span data-stu-id="2042d-135">True</span></span>                          |     <span data-ttu-id="2042d-136">Ignora la calibrazione solo durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2042d-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="2042d-137">First Experience / HoloLens /SkipTraining</span><span class="sxs-lookup"><span data-stu-id="2042d-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="2042d-138">True</span><span class="sxs-lookup"><span data-stu-id="2042d-138">True</span></span>                          |     <span data-ttu-id="2042d-139">Ignora la formazione dei dispositivi durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2042d-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="2042d-140">First Experience / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="2042d-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="2042d-141">True</span><span class="sxs-lookup"><span data-stu-id="2042d-141">True</span></span>                          |     <span data-ttu-id="2042d-142">Ignora la Wi-Fi configurazione del dispositivo durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2042d-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="2042d-143">Criteri/Connettività/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="2042d-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="2042d-144">No</span><span class="sxs-lookup"><span data-stu-id="2042d-144">No</span></span>                            |     <span data-ttu-id="2042d-145">Disabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="2042d-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="2042d-146">Criteri/Esperienza/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="2042d-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="2042d-147">No</span><span class="sxs-lookup"><span data-stu-id="2042d-147">No</span></span>                            |     <span data-ttu-id="2042d-148">Disabilita Cortana (per eliminare potenziali problemi perché i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="2042d-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="2042d-149">Criteri/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="2042d-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="2042d-150">Sì</span><span class="sxs-lookup"><span data-stu-id="2042d-150">Yes</span></span>                           |     <span data-ttu-id="2042d-151">Disabilita il microfono</span><span class="sxs-lookup"><span data-stu-id="2042d-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="2042d-152">Criteri/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="2042d-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="2042d-153">Forza negazione</span><span class="sxs-lookup"><span data-stu-id="2042d-153">Force deny</span></span>                    |     <span data-ttu-id="2042d-154">Impedisce alle app di tentare di accedere ai dati sulla posizione (per eliminare potenziali problemi poiché il rilevamento della posizione è disabilitato)</span><span class="sxs-lookup"><span data-stu-id="2042d-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="2042d-155">Criteri/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="2042d-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="2042d-156">Forza negazione</span><span class="sxs-lookup"><span data-stu-id="2042d-156">Force deny</span></span>                    |     <span data-ttu-id="2042d-157">Impedisce alle app di accedere ai microfoni (per eliminare potenziali problemi perché i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="2042d-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="2042d-158">Criteri/Sicurezza/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="2042d-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="2042d-159">No</span><span class="sxs-lookup"><span data-stu-id="2042d-159">No</span></span>                            |     <span data-ttu-id="2042d-160">Impedisce a chiunque di aggiungere pacchetti di provisioning che potrebbero tentare di ignorare i criteri bloccati.</span><span class="sxs-lookup"><span data-stu-id="2042d-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="2042d-161">Criteri/Sicurezza/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="2042d-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="2042d-162">No</span><span class="sxs-lookup"><span data-stu-id="2042d-162">No</span></span>                            |     <span data-ttu-id="2042d-163">Impedisce a chiunque di rimuovere questo pacchetto di provisioning bloccato.</span><span class="sxs-lookup"><span data-stu-id="2042d-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="2042d-164">Criteri/Sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="2042d-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="2042d-165">No</span><span class="sxs-lookup"><span data-stu-id="2042d-165">No</span></span>                            |     <span data-ttu-id="2042d-166">Impedisce al dispositivo di provare a tenere traccia dei dati sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="2042d-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="2042d-167">Criteri/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="2042d-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="2042d-168">No</span><span class="sxs-lookup"><span data-stu-id="2042d-168">No</span></span>                            |     <span data-ttu-id="2042d-169">Disabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="2042d-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="2042d-170">In Impostazioni di runtime, selezionare **Account / Utenti / UserName: Holo / Password**</span><span class="sxs-lookup"><span data-stu-id="2042d-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="2042d-171">Prendere nota della password e reimpostarla, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="2042d-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="2042d-172">Passa a UniversalAppInstall/UserContextApp e [configura l'app LOB](app-deploy-provisioning-package.md) che distribuirai in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2042d-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot della posizione in cui aggiungere l'app in WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="2042d-174">Al termine, seleziona il pulsante "Esporta" e segui tutte le istruzioni finché non viene creato il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="2042d-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="2042d-176">Distribuisci</span><span class="sxs-lookup"><span data-stu-id="2042d-176">Deploy</span></span>

1. <span data-ttu-id="2042d-177">Connetti HL2 al PC Windows 10 tramite cavo USB.</span><span class="sxs-lookup"><span data-stu-id="2042d-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="2042d-178">Avviare lo strumento ARC e selezionare **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="2042d-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="2042d-179">Nella schermata successiva seleziona Selezione manuale **del pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="2042d-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="2042d-180">Passa al file ffu scaricato in precedenza e seleziona **Apri.**</span><span class="sxs-lookup"><span data-stu-id="2042d-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="2042d-181">Nella pagina Avviso selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="2042d-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="2042d-182">Attendere che lo strumento ARC completi l'installazione del sistema operativo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2042d-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="2042d-183">Una volta completata l'installazione e avviato il backup, dal PC passa a Esplora file e copia il file PPKG salvato in precedenza nella cartella del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2042d-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![File PPKG nel PC nella finestra Esplora file.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="2042d-185">In HoloLens 2 premi la combinazione di pulsanti seguenti per eseguire il pacchetto di provisioning: tocca **Volume giù** e **Il** pulsante di alimentazione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="2042d-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="2042d-186">Verrà richiesto di applicare il pacchetto di provisioning, selezionare **Conferma**</span><span class="sxs-lookup"><span data-stu-id="2042d-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="2042d-187">Al termine del pacchetto di provisioning, selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="2042d-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="2042d-188">Dovrebbe quindi essere richiesto di accedere al dispositivo con l'account locale e la password condivisi.</span><span class="sxs-lookup"><span data-stu-id="2042d-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="2042d-189">Gestione</span><span class="sxs-lookup"><span data-stu-id="2042d-189">Maintain</span></span>

<span data-ttu-id="2042d-190">Con questa configurazione, è consigliabile riavviare il processo precedente e ripartire il dispositivo con lo strumento ARC e applicare un nuovo PPKG per apportare eventuali aggiornamenti al sistema operativo e/o alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2042d-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

