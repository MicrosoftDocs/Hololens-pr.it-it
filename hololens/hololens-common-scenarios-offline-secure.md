---
title: Scenari comuni-offline Secure HoloLens 2
description: Una distribuzione sicura offline e la distribuzione di app tramite il provisioning.
keywords: HoloLens, gestione, offline, protezione offline
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080502"
---
# <span data-ttu-id="8f1e8-104">Scenari comuni-offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8f1e8-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="8f1e8-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8f1e8-105">Overview</span></span>
<span data-ttu-id="8f1e8-106">Questa guida fornisce indicazioni per l'applicazione di un pacchetto di provisioning di esempio che bloccherà un HoloLens 2 per l'uso in ambienti sicuri con le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f1e8-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="8f1e8-107">Disabilitare il WiFi.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-107">Disable WiFi.</span></span>
-   <span data-ttu-id="8f1e8-108">Disabilitare il BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="8f1e8-109">Disabilitare i microfoni.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-109">Disable Microphones.</span></span>
-   <span data-ttu-id="8f1e8-110">Impedisce l'aggiunta o la rimozione di pacchetti di provisioning.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="8f1e8-111">Nessun utente può abilitare nessuno dei componenti ristretti sopra.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="8f1e8-112">Preparare</span><span class="sxs-lookup"><span data-stu-id="8f1e8-112">Prepare</span></span> 
<span data-ttu-id="8f1e8-113">Configurazione di Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="8f1e8-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="8f1e8-114">[Scaricare il file più recente del sistema operativo HoloLens 2](https://aka.ms/hololens2download) direttamente in un PC.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="8f1e8-115">Il supporto per questa configurazione è incluso nella build 19041,1117 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="8f1e8-116">Scaricare/installare lo strumento ARC (Advanced Recovery Companion) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al PC</span><span class="sxs-lookup"><span data-stu-id="8f1e8-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="8f1e8-117">Scaricare/installare lo strumento più recente di [Windows Configuration designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store al PC.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="8f1e8-118">[Scaricare la cartella OfflineSecureHL2_Sample con i file di progetto](https://aka.ms/HoloLensDocs-SecureOfflineSample) per compilare il PPKG.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="8f1e8-119">Preparare l' [applicazione offline line of business per la distribuzione di PPKG](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="8f1e8-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="8f1e8-120">Configura</span><span class="sxs-lookup"><span data-stu-id="8f1e8-120">Configure</span></span>
<span data-ttu-id="8f1e8-121">Creare un pacchetto di provisioning della configurazione sicura</span><span class="sxs-lookup"><span data-stu-id="8f1e8-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="8f1e8-122">Avviare lo strumento WCD nel PC.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="8f1e8-123">Selezionare **file-> progetto aperto**.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="8f1e8-124">Passare al percorso della cartella OfflineSecureHL2_Sample salvata in precedenza e selezionare: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="8f1e8-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="8f1e8-125">Il progetto dovrebbe essere aperto ed è ora necessario un elenco delle personalizzazioni disponibili:</span><span class="sxs-lookup"><span data-stu-id="8f1e8-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pacchetto di configurazione aperto in WCD](images/offline-secure-sample-wcd.png)

<span data-ttu-id="8f1e8-127">Configurazioni impostate in questo pacchetto di provisioning:</span><span class="sxs-lookup"><span data-stu-id="8f1e8-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="8f1e8-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f1e8-128">Item</span></span>                                                |     <span data-ttu-id="8f1e8-129">Impostazione</span><span class="sxs-lookup"><span data-stu-id="8f1e8-129">Setting</span></span>                       |     <span data-ttu-id="8f1e8-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f1e8-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="8f1e8-131">Account/utenti</span><span class="sxs-lookup"><span data-stu-id="8f1e8-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="8f1e8-132">Nome utente locale & password</span><span class="sxs-lookup"><span data-stu-id="8f1e8-132">Local User Name & Password</span></span>    |     <span data-ttu-id="8f1e8-133">Per questi dispositivi offline, un nome utente e una password singoli dovranno essere impostati e condivisi da tutti gli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="8f1e8-134">First Experience/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="8f1e8-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="8f1e8-135">True</span><span class="sxs-lookup"><span data-stu-id="8f1e8-135">True</span></span>                          |     <span data-ttu-id="8f1e8-136">Salta la calibrazione solo durante la configurazione iniziale del dispositivo</span><span class="sxs-lookup"><span data-stu-id="8f1e8-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="8f1e8-137">First Experience/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="8f1e8-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="8f1e8-138">True</span><span class="sxs-lookup"><span data-stu-id="8f1e8-138">True</span></span>                          |     <span data-ttu-id="8f1e8-139">Ignora la formazione del dispositivo durante l'installazione del dispositivo iniziale</span><span class="sxs-lookup"><span data-stu-id="8f1e8-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="8f1e8-140">First Experience/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="8f1e8-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="8f1e8-141">True</span><span class="sxs-lookup"><span data-stu-id="8f1e8-141">True</span></span>                          |     <span data-ttu-id="8f1e8-142">Salta la configurazione Wi-Fi durante l'installazione del dispositivo iniziale</span><span class="sxs-lookup"><span data-stu-id="8f1e8-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="8f1e8-143">Criteri/connettività/AllowBluetooth consente</span><span class="sxs-lookup"><span data-stu-id="8f1e8-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="8f1e8-144">No</span><span class="sxs-lookup"><span data-stu-id="8f1e8-144">No</span></span>                            |     <span data-ttu-id="8f1e8-145">Disabilita il Bluetooth</span><span class="sxs-lookup"><span data-stu-id="8f1e8-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="8f1e8-146">Criteri/esperienza/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="8f1e8-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="8f1e8-147">No</span><span class="sxs-lookup"><span data-stu-id="8f1e8-147">No</span></span>                            |     <span data-ttu-id="8f1e8-148">Disattiva Cortana (per eliminare i potenziali problemi in quanto i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="8f1e8-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="8f1e8-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="8f1e8-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="8f1e8-150">Sì</span><span class="sxs-lookup"><span data-stu-id="8f1e8-150">Yes</span></span>                           |     <span data-ttu-id="8f1e8-151">Disattiva il microfono</span><span class="sxs-lookup"><span data-stu-id="8f1e8-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="8f1e8-152">Criteri/privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="8f1e8-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="8f1e8-153">Forza di negazione</span><span class="sxs-lookup"><span data-stu-id="8f1e8-153">Force deny</span></span>                    |     <span data-ttu-id="8f1e8-154">Impedisce alle app di provare ad accedere ai dati della posizione (per eliminare i potenziali problemi perché il rilevamento della posizione è disabilitato)</span><span class="sxs-lookup"><span data-stu-id="8f1e8-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="8f1e8-155">Criteri/privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="8f1e8-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="8f1e8-156">Forza di negazione</span><span class="sxs-lookup"><span data-stu-id="8f1e8-156">Force deny</span></span>                    |     <span data-ttu-id="8f1e8-157">Impedisce alle app di provare ad accedere ai microfoni (per eliminare i potenziali problemi in quanto i microfoni sono disabilitati)</span><span class="sxs-lookup"><span data-stu-id="8f1e8-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="8f1e8-158">Criteri/sicurezza/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="8f1e8-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="8f1e8-159">No</span><span class="sxs-lookup"><span data-stu-id="8f1e8-159">No</span></span>                            |     <span data-ttu-id="8f1e8-160">Impedisce ad altri utenti di aggiungere pacchetti di provisioning che potrebbero tentare di ignorare i criteri bloccati.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="8f1e8-161">Criteri/sicurezza/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="8f1e8-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="8f1e8-162">No</span><span class="sxs-lookup"><span data-stu-id="8f1e8-162">No</span></span>                            |     <span data-ttu-id="8f1e8-163">Impedisce a chiunque di rimuovere il pacchetto di provisioning bloccato.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="8f1e8-164">Criteri/sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="8f1e8-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="8f1e8-165">No</span><span class="sxs-lookup"><span data-stu-id="8f1e8-165">No</span></span>                            |     <span data-ttu-id="8f1e8-166">Impedisce al dispositivo di provare a tenere traccia dei dati sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="8f1e8-167">Criteri/WiFi/AllowWiFi consente</span><span class="sxs-lookup"><span data-stu-id="8f1e8-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="8f1e8-168">No</span><span class="sxs-lookup"><span data-stu-id="8f1e8-168">No</span></span>                            |     <span data-ttu-id="8f1e8-169">Disabilita la connessione Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="8f1e8-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="8f1e8-170">In impostazioni di Runtime selezionare **account/utenti/nomeutente: Holo/password**</span><span class="sxs-lookup"><span data-stu-id="8f1e8-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="8f1e8-171">Nota la password e Reimposta, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="8f1e8-172">Passare a UniversalAppInstall/UserContextApp e [configurare l'app line-of-business](app-deploy-provisioning-package.md) che verrà distribuita in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot della posizione in cui aggiungere la tua app in WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="8f1e8-174">Una volta completata la procedura, selezionare il pulsante "Esporta" e seguire tutte le istruzioni fino a quando non viene creato il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pulsante Esporta per il pacchetto in WCD.](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="8f1e8-176">Distribuisci</span><span class="sxs-lookup"><span data-stu-id="8f1e8-176">Deploy</span></span>
1. <span data-ttu-id="8f1e8-177">Connettere il HL2 al PC Windows 10 tramite cavo USB.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="8f1e8-178">Avviare lo strumento ARC e selezionare **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="8f1e8-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="8f1e8-179">Nella schermata successiva selezionare **Selezione pacchetto manuale**.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="8f1e8-180">Passare al file con estensione FFU scaricato in precedenza e selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="8f1e8-181">Nella pagina avviso selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="8f1e8-182">Attendere lo strumento ARC per completare l'installazione del sistema operativo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="8f1e8-183">Quando il dispositivo completa il backup di installazione e avvio, dal PC passare a Esplora file e copiare il file PPKG salvato in precedenza nella cartella del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![File di PPKG nel PC nella finestra Esplora file.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="8f1e8-185">Nella HoloLens 2 Premere il tasto seguente per eseguire il pacchetto di provisioning: toccare **volume giù** e pulsante di **accensione** contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="8f1e8-186">Verrà richiesto di applicare il pacchetto di provisioning, selezionare **conferma**</span><span class="sxs-lookup"><span data-stu-id="8f1e8-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="8f1e8-187">Dopo aver completato il pacchetto di provisioning, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="8f1e8-188">Viene quindi richiesto di accedere al dispositivo con l'account e la password locali condivisi.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="8f1e8-189">Gestione</span><span class="sxs-lookup"><span data-stu-id="8f1e8-189">Maintain</span></span>
<span data-ttu-id="8f1e8-190">Con questa configurazione, è consigliabile riavviare il processo sopra e reflashare il dispositivo con lo strumento ARC e applicare un nuovo PPKG per apportare gli aggiornamenti al sistema operativo e/o alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8f1e8-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

