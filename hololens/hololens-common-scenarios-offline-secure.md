---
title: 'Scenari comuni: protezione offline di HoloLens 2'
description: Scopri come configurare uno scenario di distribuzione sicura e di distribuzione delle app offline con provisioning per i dispositivi HoloLens.
keywords: HoloLens, gestione, offline, offline secure
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407586"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="4ec9f-104">Scenari comuni: protezione offline di HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4ec9f-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="4ec9f-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="4ec9f-105">Overview</span></span>

<span data-ttu-id="4ec9f-106">Questa guida fornisce indicazioni per l'applicazione di un pacchetto di provisioning di esempio che blocchi un HoloLens 2 per l'uso in ambienti sicuri con le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ec9f-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="4ec9f-107">Disabilita WiFi.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-107">Disable WiFi.</span></span>
-   <span data-ttu-id="4ec9f-108">Disabilitare BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="4ec9f-109">Disabilita microfoni.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-109">Disable Microphones.</span></span>
-   <span data-ttu-id="4ec9f-110">Impedisce l'aggiunta o la rimozione di pacchetti di provisioning.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="4ec9f-111">Nessun utente può abilitare uno dei componenti con restrizioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="4ec9f-112">Preparazione</span><span class="sxs-lookup"><span data-stu-id="4ec9f-112">Prepare</span></span>

<span data-ttu-id="4ec9f-113">Configurazione PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="4ec9f-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="4ec9f-114">[Scarica il file del sistema operativo HoloLens 2 più](https://aka.ms/hololens2download) recente direttamente in un PC.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="4ec9f-115">Il supporto per questa configurazione è incluso nella Build 19041.1117 e successive.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="4ec9f-116">Scaricare/installare lo strumento Advanced Recovery Companion(ARC) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al PC</span><span class="sxs-lookup"><span data-stu-id="4ec9f-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="4ec9f-117">Scarica/installa lo strumento [WCD (Windows Configuration Designer)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) più recente da Microsoft Store al PC.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="4ec9f-118">[Scarica la OfflineSecureHL2_Sample file di progetto per](https://aka.ms/HoloLensDocs-SecureOfflineSample) compilare PPKG.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="4ec9f-119">Preparare [l'applicazione Line of Business offline per la distribuzione di PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="4ec9f-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="4ec9f-120">Configura</span><span class="sxs-lookup"><span data-stu-id="4ec9f-120">Configure</span></span>

<span data-ttu-id="4ec9f-121">Creare un pacchetto di provisioning della configurazione sicura</span><span class="sxs-lookup"><span data-stu-id="4ec9f-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="4ec9f-122">Avvia lo strumento WCD nel PC.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="4ec9f-123">Selezionare **File -> Apri progetto**.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="4ec9f-124">Passare al percorso della cartella di OfflineSecureHL2_Sample salvata in precedenza e selezionare: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="4ec9f-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="4ec9f-125">Il progetto dovrebbe aprirsi e ora dovrebbe essere disponibile un elenco di personalizzazioni disponibili:</span><span class="sxs-lookup"><span data-stu-id="4ec9f-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pacchetto di configurazione aperto in WCD](images/offline-secure-sample-wcd.png)

   <span data-ttu-id="4ec9f-127">Configurazioni impostate in questo pacchetto di provisioning:</span><span class="sxs-lookup"><span data-stu-id="4ec9f-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="4ec9f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ec9f-128">Item</span></span>                                                |     <span data-ttu-id="4ec9f-129">Impostazione</span><span class="sxs-lookup"><span data-stu-id="4ec9f-129">Setting</span></span>                       |     <span data-ttu-id="4ec9f-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ec9f-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="4ec9f-131">Account /Utenti</span><span class="sxs-lookup"><span data-stu-id="4ec9f-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="4ec9f-132">Nome utente locale & password</span><span class="sxs-lookup"><span data-stu-id="4ec9f-132">Local User Name & Password</span></span>    |     <span data-ttu-id="4ec9f-133">Per questi dispositivi offline, un singolo nome utente e password dovranno essere impostati e condivisi da tutti gli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="4ec9f-134">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="4ec9f-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="4ec9f-135">True</span><span class="sxs-lookup"><span data-stu-id="4ec9f-135">True</span></span>                          |     <span data-ttu-id="4ec9f-136">Ignora la calibrazione solo durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="4ec9f-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="4ec9f-137">First Experience / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="4ec9f-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="4ec9f-138">True</span><span class="sxs-lookup"><span data-stu-id="4ec9f-138">True</span></span>                          |     <span data-ttu-id="4ec9f-139">Ignora la formazione dei dispositivi durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="4ec9f-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="4ec9f-140">First Experience / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="4ec9f-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="4ec9f-141">True</span><span class="sxs-lookup"><span data-stu-id="4ec9f-141">True</span></span>                          |     <span data-ttu-id="4ec9f-142">Ignora la Wi-Fi configurazione durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="4ec9f-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="4ec9f-143">Criteri/Connettività/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="4ec9f-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="4ec9f-144">No</span><span class="sxs-lookup"><span data-stu-id="4ec9f-144">No</span></span>                            |     <span data-ttu-id="4ec9f-145">Disabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="4ec9f-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="4ec9f-146">Criteri/Esperienza/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="4ec9f-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="4ec9f-147">No</span><span class="sxs-lookup"><span data-stu-id="4ec9f-147">No</span></span>                            |     <span data-ttu-id="4ec9f-148">Disabilita Cortana (per eliminare potenziali problemi perché i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="4ec9f-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="4ec9f-149">Criteri/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="4ec9f-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="4ec9f-150">Sì</span><span class="sxs-lookup"><span data-stu-id="4ec9f-150">Yes</span></span>                           |     <span data-ttu-id="4ec9f-151">Disabilita microfono</span><span class="sxs-lookup"><span data-stu-id="4ec9f-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="4ec9f-152">Criteri/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="4ec9f-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="4ec9f-153">Forza negazione</span><span class="sxs-lookup"><span data-stu-id="4ec9f-153">Force deny</span></span>                    |     <span data-ttu-id="4ec9f-154">Impedisce alle app di tentare di accedere ai dati sulla posizione (per eliminare potenziali problemi poiché il rilevamento della posizione è disabilitato)</span><span class="sxs-lookup"><span data-stu-id="4ec9f-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="4ec9f-155">Criteri/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="4ec9f-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="4ec9f-156">Forza negazione</span><span class="sxs-lookup"><span data-stu-id="4ec9f-156">Force deny</span></span>                    |     <span data-ttu-id="4ec9f-157">Impedisce alle app di tentare di accedere ai microfoni (per eliminare potenziali problemi poiché i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="4ec9f-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="4ec9f-158">Criteri/Sicurezza/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="4ec9f-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="4ec9f-159">No</span><span class="sxs-lookup"><span data-stu-id="4ec9f-159">No</span></span>                            |     <span data-ttu-id="4ec9f-160">Impedisce a chiunque di aggiungere pacchetti di provisioning che potrebbero tentare di ignorare i criteri bloccati.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="4ec9f-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="4ec9f-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="4ec9f-162">No</span><span class="sxs-lookup"><span data-stu-id="4ec9f-162">No</span></span>                            |     <span data-ttu-id="4ec9f-163">Impedisce a chiunque di rimuovere questo pacchetto di provisioning bloccato.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="4ec9f-164">Criteri/Sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="4ec9f-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="4ec9f-165">No</span><span class="sxs-lookup"><span data-stu-id="4ec9f-165">No</span></span>                            |     <span data-ttu-id="4ec9f-166">Impedisce al dispositivo di provare a tenere traccia dei dati sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="4ec9f-167">Criteri/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="4ec9f-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="4ec9f-168">No</span><span class="sxs-lookup"><span data-stu-id="4ec9f-168">No</span></span>                            |     <span data-ttu-id="4ec9f-169">Disabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="4ec9f-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="4ec9f-170">In Impostazioni di runtime, selezionare **Account / Utenti / UserName: Holo / Password**.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="4ec9f-171">Annotare la password e reimpostarla, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="4ec9f-172">Passa a UniversalAppInstall / UserContextApp e [configura l'app LOB](app-deploy-provisioning-package.md) che verrà distribuita in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot della posizione in cui aggiungere l'app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. <span data-ttu-id="4ec9f-174">Al termine, seleziona il pulsante "Esporta" e segui tutte le istruzioni finché non viene creato il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pulsante Esporta per questo pacchetto in WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a><span data-ttu-id="4ec9f-176">Distribuisci</span><span class="sxs-lookup"><span data-stu-id="4ec9f-176">Deploy</span></span>

1. <span data-ttu-id="4ec9f-177">Connetti HL2 al PC Windows 10 tramite cavo USB.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="4ec9f-178">Avviare lo strumento ARC e selezionare **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="4ec9f-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Schermata iniziale di riconfigurazione di HoloLens 2](images/ARC2.png)

1. <span data-ttu-id="4ec9f-180">Nella schermata successiva seleziona **Selezione manuale del pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="4ec9f-180">On the next screen select **Manual package selection**.</span></span>

   ![Schermata info HoloLens 2 ARC](images/arc_device_info.png)

1. <span data-ttu-id="4ec9f-182">Passare al file ffu scaricato in precedenza e selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="4ec9f-183">Nella pagina Avviso selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="4ec9f-183">At the Warning page select **Continue**.</span></span>

   ![Schermata di avviso HoloLens 2 ARC](images/arc_warning.png)

1. <span data-ttu-id="4ec9f-185">Attendere che lo strumento ARC completi l'installazione del sistema operativo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="4ec9f-186">Una volta completata l'installazione e avviato il backup, dal PC passare a Esplora file e copiare il file PPKG salvato in precedenza nella cartella del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![File PPKG nel PC nella finestra Esplora file.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="4ec9f-188">In HoloLens 2 premi la combinazione di pulsanti seguente per eseguire il pacchetto di provisioning: tocca **Volume giù** e **Pulsante** di alimentazione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="4ec9f-189">Verrà richiesto di applicare il pacchetto di provisioning, selezionare **Conferma**</span><span class="sxs-lookup"><span data-stu-id="4ec9f-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="4ec9f-190">Al termine del pacchetto di provisioning, seleziona **OK.**</span><span class="sxs-lookup"><span data-stu-id="4ec9f-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="4ec9f-191">Verrà quindi richiesto di accedere al dispositivo con l'account locale condiviso e la password.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="4ec9f-192">Gestione</span><span class="sxs-lookup"><span data-stu-id="4ec9f-192">Maintain</span></span>

<span data-ttu-id="4ec9f-193">Con questa configurazione, è consigliabile riavviare il processo precedente e ripartire il dispositivo con lo strumento ARC e applicare un nuovo PPKG per apportare eventuali aggiornamenti al sistema operativo e/o alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4ec9f-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
