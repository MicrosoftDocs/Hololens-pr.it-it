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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309124"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="6bb2f-104">Scenari comuni- Sicurezza offline HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6bb2f-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="6bb2f-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="6bb2f-105">Overview</span></span>

<span data-ttu-id="6bb2f-106">Questa guida fornisce indicazioni per l'applicazione di un pacchetto di provisioning di esempio che blocca un HoloLens 2 per l'uso in ambienti sicuri con le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6bb2f-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="6bb2f-107">Disabilitare il Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-107">Disable WiFi.</span></span>
-   <span data-ttu-id="6bb2f-108">Disabilitare BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="6bb2f-109">Disabilitare i microfoni.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-109">Disable Microphones.</span></span>
-   <span data-ttu-id="6bb2f-110">Impedisce l'aggiunta o la rimozione di pacchetti di provisioning.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="6bb2f-111">Nessun utente può abilitare uno dei componenti con restrizioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="6bb2f-112">Preparare</span><span class="sxs-lookup"><span data-stu-id="6bb2f-112">Prepare</span></span>

<span data-ttu-id="6bb2f-113">Windows 10 PC Setup</span><span class="sxs-lookup"><span data-stu-id="6bb2f-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="6bb2f-114">[Scaricare il file HoloLens 2 del sistema operativo](https://aka.ms/hololens2download) più recente direttamente in un PC.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="6bb2f-115">Il supporto per questa configurazione è incluso nella build 19041.1117 e successive.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="6bb2f-116">Scaricare/installare lo strumento Advanced Recovery Companion (ARC) dal [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al PC</span><span class="sxs-lookup"><span data-stu-id="6bb2f-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="6bb2f-117">Scaricare/installare lo strumento [WCD (Windows Configuration Designer)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) più recente dal Microsoft Store al PC.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="6bb2f-118">[Scaricare la OfflineSecureHL2_Sample file di progetto con i](https://aka.ms/HoloLensDocs-SecureOfflineSample) file di progetto per compilare il file PPKG.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="6bb2f-119">Preparare [l'applicazione Line of Business offline per la distribuzione PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="6bb2f-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="6bb2f-120">Configurare</span><span class="sxs-lookup"><span data-stu-id="6bb2f-120">Configure</span></span>

<span data-ttu-id="6bb2f-121">Creare un pacchetto di provisioning della configurazione sicura</span><span class="sxs-lookup"><span data-stu-id="6bb2f-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="6bb2f-122">Avviare lo strumento WCD nel PC.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="6bb2f-123">Selezionare **File -> Apri progetto**.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="6bb2f-124">Passare al percorso della cartella di OfflineSecureHL2_Sample salvata in precedenza e selezionare: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="6bb2f-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="6bb2f-125">Il progetto dovrebbe essere aperto e dovrebbe essere ora disponibile un elenco di personalizzazioni disponibili:</span><span class="sxs-lookup"><span data-stu-id="6bb2f-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6bb2f-126">![Screenshot del pacchetto di configurazione aperto in WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="6bb2f-126">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="6bb2f-127">Configurazioni impostate in questo pacchetto di provisioning:</span><span class="sxs-lookup"><span data-stu-id="6bb2f-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="6bb2f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="6bb2f-128">Item</span></span>                                                |     <span data-ttu-id="6bb2f-129">Impostazione</span><span class="sxs-lookup"><span data-stu-id="6bb2f-129">Setting</span></span>                       |     <span data-ttu-id="6bb2f-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bb2f-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="6bb2f-131">Account/Utenti</span><span class="sxs-lookup"><span data-stu-id="6bb2f-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="6bb2f-132">Nome utente locale & password</span><span class="sxs-lookup"><span data-stu-id="6bb2f-132">Local User Name & Password</span></span>    |     <span data-ttu-id="6bb2f-133">Per questi dispositivi offline, un singolo nome utente e una sola password dovranno essere impostati e condivisi da tutti gli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="6bb2f-134">Prima esperienza/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="6bb2f-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="6bb2f-135">Vero</span><span class="sxs-lookup"><span data-stu-id="6bb2f-135">True</span></span>                          |     <span data-ttu-id="6bb2f-136">Ignora la calibrazione solo durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="6bb2f-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="6bb2f-137">Prima esperienza/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="6bb2f-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="6bb2f-138">Vero</span><span class="sxs-lookup"><span data-stu-id="6bb2f-138">True</span></span>                          |     <span data-ttu-id="6bb2f-139">Ignora il training del dispositivo durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="6bb2f-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="6bb2f-140">Prima esperienza/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="6bb2f-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="6bb2f-141">Vero</span><span class="sxs-lookup"><span data-stu-id="6bb2f-141">True</span></span>                          |     <span data-ttu-id="6bb2f-142">Ignora la Wi-Fi durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="6bb2f-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="6bb2f-143">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="6bb2f-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="6bb2f-144">No</span><span class="sxs-lookup"><span data-stu-id="6bb2f-144">No</span></span>                            |     <span data-ttu-id="6bb2f-145">Disabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="6bb2f-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="6bb2f-146">Criteri/Esperienza/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="6bb2f-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="6bb2f-147">No</span><span class="sxs-lookup"><span data-stu-id="6bb2f-147">No</span></span>                            |     <span data-ttu-id="6bb2f-148">Disabilita Cortana (per eliminare potenziali problemi perché i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="6bb2f-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="6bb2f-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="6bb2f-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="6bb2f-150">Sì</span><span class="sxs-lookup"><span data-stu-id="6bb2f-150">Yes</span></span>                           |     <span data-ttu-id="6bb2f-151">Disabilita il microfono</span><span class="sxs-lookup"><span data-stu-id="6bb2f-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="6bb2f-152">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="6bb2f-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="6bb2f-153">Forza negazione</span><span class="sxs-lookup"><span data-stu-id="6bb2f-153">Force deny</span></span>                    |     <span data-ttu-id="6bb2f-154">Impedisce alle app di tentare di accedere ai dati sulla posizione (per eliminare potenziali problemi perché il rilevamento della posizione è disabilitato)</span><span class="sxs-lookup"><span data-stu-id="6bb2f-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="6bb2f-155">Criteri/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="6bb2f-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="6bb2f-156">Forza negazione</span><span class="sxs-lookup"><span data-stu-id="6bb2f-156">Force deny</span></span>                    |     <span data-ttu-id="6bb2f-157">Impedisce alle app di accedere ai microfoni (per eliminare potenziali problemi perché i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="6bb2f-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="6bb2f-158">Criteri/Sicurezza/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="6bb2f-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="6bb2f-159">No</span><span class="sxs-lookup"><span data-stu-id="6bb2f-159">No</span></span>                            |     <span data-ttu-id="6bb2f-160">Impedisce a chiunque di aggiungere pacchetti di provisioning che potrebbero tentare di eseguire l'override dei criteri bloccati.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="6bb2f-161">Criteri/Sicurezza/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="6bb2f-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="6bb2f-162">No</span><span class="sxs-lookup"><span data-stu-id="6bb2f-162">No</span></span>                            |     <span data-ttu-id="6bb2f-163">Impedisce a chiunque di rimuovere questo pacchetto di provisioning bloccato.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="6bb2f-164">Criteri/Sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="6bb2f-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="6bb2f-165">No</span><span class="sxs-lookup"><span data-stu-id="6bb2f-165">No</span></span>                            |     <span data-ttu-id="6bb2f-166">Impedisce al dispositivo di provare a tenere traccia dei dati sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="6bb2f-167">Criteri/Wi-Fi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="6bb2f-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="6bb2f-168">No</span><span class="sxs-lookup"><span data-stu-id="6bb2f-168">No</span></span>                            |     <span data-ttu-id="6bb2f-169">Disabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6bb2f-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="6bb2f-170">In Impostazioni di runtime selezionare **Account/Utenti/UserName: Holo/Password.**</span><span class="sxs-lookup"><span data-stu-id="6bb2f-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="6bb2f-171">Prendere nota della password e reimpostarla, se necessario.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="6bb2f-172">Passare a UniversalAppInstall/UserContextApp e [configurare l'app LOB](app-deploy-provisioning-package.md) che verrà distribuita in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6bb2f-173">![Screenshot della posizione in cui aggiungere l'app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="6bb2f-173">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="6bb2f-174">Al termine, selezionare il pulsante "Esporta" e seguire tutte le richieste fino a quando non viene creato il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6bb2f-175">![Screenshot del pulsante Esporta per questo pacchetto in WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="6bb2f-175">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="6bb2f-176">Distribuisci</span><span class="sxs-lookup"><span data-stu-id="6bb2f-176">Deploy</span></span>

1. <span data-ttu-id="6bb2f-177">Connettere HL2 al PC Windows 10 tramite cavo USB.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="6bb2f-178">Avviare lo strumento ARC e selezionare **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="6bb2f-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 schermata iniziale della reflash pulita](images/ARC2.png)

1. <span data-ttu-id="6bb2f-180">Nella schermata successiva selezionare **Selezione manuale del pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="6bb2f-180">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 informazioni ARC](images/arc_device_info.png)

1. <span data-ttu-id="6bb2f-182">Passare al file con estensione ffu scaricato in precedenza e selezionare **Apri.**</span><span class="sxs-lookup"><span data-stu-id="6bb2f-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="6bb2f-183">Nella pagina Avviso selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="6bb2f-183">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 di avviso di ARC](images/arc_warning.png)

1. <span data-ttu-id="6bb2f-185">Attendere che lo strumento ARC completi l'installazione HoloLens 2 sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="6bb2f-186">Al termine dell'installazione e dell'avvio del dispositivo, dal PC passare a Esplora file e copiare il file PPKG salvato in precedenza nella cartella del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6bb2f-187">![File PPKG nel PC in Esplora file finestra.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="6bb2f-187">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="6bb2f-188">Nel HoloLens 2 premere la casella combinata di pulsanti seguenti per eseguire il pacchetto di provisioning: toccare **volume** in basso e **pulsante** di alimentazione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="6bb2f-189">Verrà richiesto di applicare il pacchetto di provisioning e selezionare **Conferma**</span><span class="sxs-lookup"><span data-stu-id="6bb2f-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="6bb2f-190">Al termine del pacchetto di provisioning, selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="6bb2f-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="6bb2f-191">Verrà quindi richiesto di accedere al dispositivo con l'account locale condiviso e la password.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="6bb2f-192">Effettuare la manutenzione</span><span class="sxs-lookup"><span data-stu-id="6bb2f-192">Maintain</span></span>

<span data-ttu-id="6bb2f-193">Con questa configurazione, è consigliabile riavviare il processo precedente e aggiornare il dispositivo con lo strumento ARC e applicare un nuovo PPKG per apportare eventuali aggiornamenti al sistema operativo e/o alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6bb2f-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
