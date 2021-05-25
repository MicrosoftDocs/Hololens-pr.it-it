---
title: Scenari comuni- Sicurezza offline HoloLens 2
description: Informazioni su come configurare uno scenario di distribuzione sicura e di distribuzione di app offline con il provisioning per i dispositivi HoloLens.
keywords: HoloLens, gestione, offline, offline sicura
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
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397882"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="e7285-104">Scenari comuni- Sicurezza offline HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e7285-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="e7285-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e7285-105">Overview</span></span>

<span data-ttu-id="e7285-106">Questa guida fornisce indicazioni per l'applicazione di un pacchetto di provisioning di esempio che blocca un HoloLens 2 per l'uso in ambienti sicuri con le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7285-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="e7285-107">Disabilitare il Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="e7285-107">Disable WiFi.</span></span>
-   <span data-ttu-id="e7285-108">Disabilitare BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="e7285-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="e7285-109">Disabilitare i microfoni.</span><span class="sxs-lookup"><span data-stu-id="e7285-109">Disable Microphones.</span></span>
-   <span data-ttu-id="e7285-110">Impedisce l'aggiunta o la rimozione di pacchetti di provisioning.</span><span class="sxs-lookup"><span data-stu-id="e7285-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="e7285-111">Nessun utente può abilitare uno dei componenti con restrizioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="e7285-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="e7285-112">[![Scenario di sicurezza offline ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e7285-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="e7285-113">Preparazione</span><span class="sxs-lookup"><span data-stu-id="e7285-113">Prepare</span></span>

<span data-ttu-id="e7285-114">Windows 10 PC Setup</span><span class="sxs-lookup"><span data-stu-id="e7285-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="e7285-115">[Scaricare la versione HoloLens 2 file del sistema operativo](https://aka.ms/hololens2download) direttamente in un PC.</span><span class="sxs-lookup"><span data-stu-id="e7285-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="e7285-116">Il supporto per questa configurazione è incluso nella build 19041.1117 e successive.</span><span class="sxs-lookup"><span data-stu-id="e7285-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="e7285-117">Scaricare/installare lo strumento Advanced Recovery Companion (ARC) dal [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al PC</span><span class="sxs-lookup"><span data-stu-id="e7285-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="e7285-118">Scaricare/installare lo strumento [WCD (Windows Configuration Designer)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) più recente dal Microsoft Store al PC.</span><span class="sxs-lookup"><span data-stu-id="e7285-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="e7285-119">[Scaricare la OfflineSecureHL2_Sample con i file di progetto](https://aka.ms/HoloLensDocs-SecureOfflineSample) per compilare il file PPKG.</span><span class="sxs-lookup"><span data-stu-id="e7285-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="e7285-120">Preparare [l'applicazione Line of Business offline per la distribuzione PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="e7285-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="e7285-121">Configurare</span><span class="sxs-lookup"><span data-stu-id="e7285-121">Configure</span></span>

<span data-ttu-id="e7285-122">Creare un pacchetto di provisioning della configurazione sicura</span><span class="sxs-lookup"><span data-stu-id="e7285-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="e7285-123">Avviare lo strumento WCD nel PC.</span><span class="sxs-lookup"><span data-stu-id="e7285-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="e7285-124">Selezionare **File -> Apri progetto**.</span><span class="sxs-lookup"><span data-stu-id="e7285-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="e7285-125">Passare al percorso della cartella di OfflineSecureHL2_Sample salvata in precedenza e selezionare: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="e7285-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="e7285-126">Il progetto dovrebbe essere aperto e dovrebbe essere ora disponibile un elenco di personalizzazioni disponibili:</span><span class="sxs-lookup"><span data-stu-id="e7285-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7285-127">![Screenshot del pacchetto di configurazione aperto in WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="e7285-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="e7285-128">Configurazioni impostate in questo pacchetto di provisioning:</span><span class="sxs-lookup"><span data-stu-id="e7285-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="e7285-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7285-129">Item</span></span>                                                |     <span data-ttu-id="e7285-130">Impostazione</span><span class="sxs-lookup"><span data-stu-id="e7285-130">Setting</span></span>                       |     <span data-ttu-id="e7285-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7285-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="e7285-132">Account/Utenti</span><span class="sxs-lookup"><span data-stu-id="e7285-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="e7285-133">Nome utente locale & password</span><span class="sxs-lookup"><span data-stu-id="e7285-133">Local User Name & Password</span></span>    |     <span data-ttu-id="e7285-134">Per questi dispositivi offline, un singolo nome utente e una singola password dovranno essere impostati e condivisi da tutti gli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e7285-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="e7285-135">Prima esperienza/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="e7285-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="e7285-136">Vero</span><span class="sxs-lookup"><span data-stu-id="e7285-136">True</span></span>                          |     <span data-ttu-id="e7285-137">Ignora la calibrazione solo durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e7285-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="e7285-138">Prima esperienza/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="e7285-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="e7285-139">Vero</span><span class="sxs-lookup"><span data-stu-id="e7285-139">True</span></span>                          |     <span data-ttu-id="e7285-140">Ignora il training del dispositivo durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e7285-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="e7285-141">Prima esperienza/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="e7285-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="e7285-142">Vero</span><span class="sxs-lookup"><span data-stu-id="e7285-142">True</span></span>                          |     <span data-ttu-id="e7285-143">Ignora la Wi-Fi durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e7285-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="e7285-144">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="e7285-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="e7285-145">No</span><span class="sxs-lookup"><span data-stu-id="e7285-145">No</span></span>                            |     <span data-ttu-id="e7285-146">Disabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="e7285-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="e7285-147">Criteri/Esperienza/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="e7285-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="e7285-148">No</span><span class="sxs-lookup"><span data-stu-id="e7285-148">No</span></span>                            |     <span data-ttu-id="e7285-149">Disabilita Cortana (per eliminare potenziali problemi perché i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="e7285-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="e7285-150">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="e7285-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="e7285-151">Sì</span><span class="sxs-lookup"><span data-stu-id="e7285-151">Yes</span></span>                           |     <span data-ttu-id="e7285-152">Disabilita il microfono</span><span class="sxs-lookup"><span data-stu-id="e7285-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="e7285-153">Criteri/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="e7285-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="e7285-154">Forza negazione</span><span class="sxs-lookup"><span data-stu-id="e7285-154">Force deny</span></span>                    |     <span data-ttu-id="e7285-155">Impedisce alle app di tentare di accedere ai dati sulla posizione (per eliminare potenziali problemi perché il rilevamento della posizione è disabilitato)</span><span class="sxs-lookup"><span data-stu-id="e7285-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="e7285-156">Criteri/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="e7285-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="e7285-157">Forza negazione</span><span class="sxs-lookup"><span data-stu-id="e7285-157">Force deny</span></span>                    |     <span data-ttu-id="e7285-158">Impedisce alle app di accedere ai microfoni (per eliminare potenziali problemi perché i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="e7285-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="e7285-159">Criteri/Sicurezza/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="e7285-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="e7285-160">No</span><span class="sxs-lookup"><span data-stu-id="e7285-160">No</span></span>                            |     <span data-ttu-id="e7285-161">Impedisce a chiunque di aggiungere pacchetti di provisioning che potrebbero tentare di eseguire l'override dei criteri bloccati.</span><span class="sxs-lookup"><span data-stu-id="e7285-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="e7285-162">Criteri/Sicurezza/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="e7285-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="e7285-163">No</span><span class="sxs-lookup"><span data-stu-id="e7285-163">No</span></span>                            |     <span data-ttu-id="e7285-164">Impedisce a chiunque di rimuovere questo pacchetto di provisioning bloccato.</span><span class="sxs-lookup"><span data-stu-id="e7285-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="e7285-165">Criteri/Sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="e7285-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="e7285-166">No</span><span class="sxs-lookup"><span data-stu-id="e7285-166">No</span></span>                            |     <span data-ttu-id="e7285-167">Impedisce al dispositivo di provare a tenere traccia dei dati sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="e7285-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="e7285-168">Criteri/Wi-Fi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="e7285-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="e7285-169">No</span><span class="sxs-lookup"><span data-stu-id="e7285-169">No</span></span>                            |     <span data-ttu-id="e7285-170">Disabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e7285-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="e7285-171">In Impostazioni di runtime selezionare **Account/Utenti/UserName: Holo/Password.**</span><span class="sxs-lookup"><span data-stu-id="e7285-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="e7285-172">Prendere nota della password e reimpostarla, se necessario.</span><span class="sxs-lookup"><span data-stu-id="e7285-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="e7285-173">Passare a UniversalAppInstall/UserContextApp e [configurare l'app LOB](app-deploy-provisioning-package.md) che verrà distribuita in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e7285-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7285-174">![Screenshot della posizione in cui aggiungere l'app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="e7285-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="e7285-175">Al termine, selezionare il pulsante "Esporta" e seguire tutte le richieste fino a quando non viene creato il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="e7285-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7285-176">![Screenshot del pulsante Esporta per questo pacchetto in WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="e7285-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="e7285-177">Distribuisci</span><span class="sxs-lookup"><span data-stu-id="e7285-177">Deploy</span></span>

1. <span data-ttu-id="e7285-178">Connettere HL2 al PC Windows 10 tramite cavo USB.</span><span class="sxs-lookup"><span data-stu-id="e7285-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="e7285-179">Avviare lo strumento ARC e selezionare **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="e7285-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 iniziale della reflash pulita](images/ARC2.png)

1. <span data-ttu-id="e7285-181">Nella schermata successiva selezionare **Selezione manuale del pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="e7285-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 informazioni ARC](images/arc_device_info.png)

1. <span data-ttu-id="e7285-183">Passare al file con estensione ffu scaricato in precedenza e selezionare **Apri.**</span><span class="sxs-lookup"><span data-stu-id="e7285-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="e7285-184">Nella pagina Avviso selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="e7285-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 di avviso arc](images/arc_warning.png)

1. <span data-ttu-id="e7285-186">Attendere che lo strumento ARC completi l'installazione HoloLens 2 sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e7285-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="e7285-187">Dopo aver completato l'installazione e avviato il dispositivo, dal PC passare a Esplora file e copiare il file PPKG salvato in precedenza nella cartella del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e7285-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7285-188">![File PPKG nel PC in Esplora file finestra.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="e7285-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="e7285-189">Nel HoloLens 2 premere la casella combinata di pulsanti seguenti per eseguire il pacchetto di provisioning: toccare **volume** in basso e **pulsante** di alimentazione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e7285-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="e7285-190">Verrà richiesto di applicare il pacchetto di provisioning e selezionare **Conferma**</span><span class="sxs-lookup"><span data-stu-id="e7285-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="e7285-191">Al termine del pacchetto di provisioning, selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="e7285-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="e7285-192">Verrà quindi richiesto di accedere al dispositivo con l'account locale condiviso e la password.</span><span class="sxs-lookup"><span data-stu-id="e7285-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="e7285-193">Effettuare la manutenzione</span><span class="sxs-lookup"><span data-stu-id="e7285-193">Maintain</span></span>

<span data-ttu-id="e7285-194">Con questa configurazione, è consigliabile riavviare il processo precedente e aggiornare il dispositivo con lo strumento ARC e applicare un nuovo PPKG per apportare eventuali aggiornamenti al sistema operativo e/o alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e7285-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
