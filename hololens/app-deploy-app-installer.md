---
title: Come eseguire il side load e installare app tramite il programma di installazione app di HoloLens 2
description: Scopri come installare e risolvere i problemi delle app con il programma di installazione app e caricare e installare le app tramite l'interfaccia utente.
keywords: gestione delle app, app, hololens, programma di installazione app
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 89f48fab236fdaf58fb0bf8b29e5a3aacb3bdee3
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283737"
---
# <span data-ttu-id="3a4b7-104">Installare app in HoloLens 2 tramite il programma di installazione app</span><span class="sxs-lookup"><span data-stu-id="3a4b7-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="3a4b7-105">Questa funzionalità è stata resa disponibile in [Windows Holographic, versione 20H2 - Aggiornamento di dicembre 2020.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="3a4b7-106">Assicurati che il dispositivo [sia aggiornato per](hololens-update-hololens.md) usare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="3a4b7-107">Abbiamo aggiunto **una nuova funzionalità (programma** di installazione app) per consentirti di installare le applicazioni in modo più semplice nei dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="3a4b7-108">La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti.**</span><span class="sxs-lookup"><span data-stu-id="3a4b7-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="3a4b7-109">Per evitare interruzioni per le aziende, il programma di installazione app non sarà disponibile **per i dispositivi** gestiti in questo momento.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="3a4b7-110">Un dispositivo viene considerato "gestito" se **si** verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a4b7-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="3a4b7-111">MDM [registrato](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="3a4b7-112">Configurato con il [pacchetto di provisioning](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="3a4b7-113">[L'identità utente](hololens-identity.md) è Azure AD</span><span class="sxs-lookup"><span data-stu-id="3a4b7-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="3a4b7-114">Ora puoi installare app senza dover abilitare la modalità sviluppatore o usare Device Portal.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="3a4b7-115">Scarica (tramite USB o tramite Microsoft Edge) il bundle Appx nel dispositivo e passa al bundle Appx in Esplora file per chiedere di avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="3a4b7-116">In alternativa, [avviare un'installazione da una pagina Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="3a4b7-117">Proprio come le app installate da Microsoft Store o il sideload tramite la funzionalità di distribuzione [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) di app [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) LOB di MDM, le app devono essere firmate digitalmente con lo strumento di firma e il certificato usato per firmare deve essere considerato attendibile dal dispositivo HoloLens prima che l'app possa essere distribuita.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="3a4b7-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a4b7-118">Requirements</span></span>

### <span data-ttu-id="3a4b7-119">Per i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="3a4b7-119">For your devices:</span></span>

 <span data-ttu-id="3a4b7-120">è attualmente disponibile nelle build di Windows Holographic 20H2 per i dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-120">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="3a4b7-121">Assicurati che tutti i dispositivi che usano questo metodo siano [aggiornati.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="3a4b7-122">Per le tue app:</span><span class="sxs-lookup"><span data-stu-id="3a4b7-122">For your apps:</span></span> 
<span data-ttu-id="3a4b7-123">La configurazione della soluzione dell'app deve essere **Master** o **Release** perché il programma di installazione app userà le dipendenze dallo Store.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="3a4b7-124">Vedi altre informazioni sulla [creazione di pacchetti dell'app.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="3a4b7-125">Le app installate tramite questo metodo devono essere firmate digitalmente.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="3a4b7-126">Dovrai usare un certificato per firmare l'app.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="3a4b7-127">È possibile ottenere un certificato dall'elenco delle CA attendibili [di Microsoft,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)nel qual caso non sarà necessario eseguire alcuna azione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="3a4b7-128">Oppure puoi firmare il tuo certificato, tuttavia tale certificato dovrà essere inserito nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="3a4b7-129">Come firmare le app [con lo strumento di firma.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="3a4b7-130">Opzioni certificato:</span><span class="sxs-lookup"><span data-stu-id="3a4b7-130">Certificate options:</span></span>**

- [<span data-ttu-id="3a4b7-131">MS Trusted CA List</span><span class="sxs-lookup"><span data-stu-id="3a4b7-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="3a4b7-132">Selezionare un metodo di distribuzione del certificato.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-132">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="3a4b7-133">[I pacchetti di](hololens-provisioning.md) provisioning possono essere applicati ai dispositivi locali.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="3a4b7-134">MDM può essere usato per [applicare certificati con configurazioni dei dispositivi.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="3a4b7-135">Utilizzare Gestione certificati [nel dispositivo.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="3a4b7-136">Metodo di installazione</span><span class="sxs-lookup"><span data-stu-id="3a4b7-136">Installation method</span></span>

1. <span data-ttu-id="3a4b7-137">Verifica che il dispositivo non sia considerato gestito.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="3a4b7-138">Verifica che il dispositivo HoloLens 2 sia acceso e che tu sia connesso.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="3a4b7-139">Nel PC passa alla tua app personalizzata e copia yourapp.appxbundle in yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="3a4b7-140">Dopo aver completato la copia del file, puoi disconnettere il dispositivo e completare l'installazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="3a4b7-141">Dal dispositivo HoloLens 2 apri il **menu Start,** seleziona **Tutte le app** e avvia l'app **Esplora** file.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="3a4b7-142">Passare alla cartella Download.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="3a4b7-143">Nel pannello sinistro dell'app potrebbe essere necessario selezionare prima questo **dispositivo,** quindi passare a Download.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="3a4b7-144">Seleziona il file yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="3a4b7-145">Verrà avviato il programma di installazione app.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-145">The App Installer will launch.</span></span> <span data-ttu-id="3a4b7-146">Seleziona il **pulsante Installa** per installare l'app.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="3a4b7-147">L'app installata verrà avviata automaticamente al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Installazione di esempi MRTK tramite il programma di installazione app](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="3a4b7-149">Risoluzione dei problemi relativi alle installazioni</span><span class="sxs-lookup"><span data-stu-id="3a4b7-149">Troubleshooting Installs</span></span>

<span data-ttu-id="3a4b7-150">Se l'installazione dell'app non è riuscita, controlla quanto segue per risolvere i problemi:</span><span class="sxs-lookup"><span data-stu-id="3a4b7-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="3a4b7-151">L'app è una build Master o Release.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="3a4b7-152">Il dispositivo viene aggiornato a una build in cui questa funzionalità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="3a4b7-153">Si è [connessi a Internet.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="3a4b7-154">Gli [endpoint per Microsoft Store sono](hololens-offline.md) configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="3a4b7-155">Programma di installazione Web</span><span class="sxs-lookup"><span data-stu-id="3a4b7-155">Web Installer</span></span>

<span data-ttu-id="3a4b7-156">Gli utenti possono installare un'app direttamente da un server Web.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="3a4b7-157">Questo flusso utilizza il programma di installazione app combinato con un metodo di distribuzione di download e installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="3a4b7-158">Come configurare l'installazione Web:</span><span class="sxs-lookup"><span data-stu-id="3a4b7-158">How to set up web install:</span></span>

1. <span data-ttu-id="3a4b7-159">Verifica che l'app sia configurata correttamente per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="3a4b7-160">Seguire questa [procedura per abilitare l'installazione da una pagina Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="3a4b7-161">Esperienza utente finale:</span><span class="sxs-lookup"><span data-stu-id="3a4b7-161">End user experience:</span></span>

1. <span data-ttu-id="3a4b7-162">L'utente riceve e installa il certificato nel dispositivo usando un metodo scelto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="3a4b7-163">L'utente visita l'URL creato dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="3a4b7-164">L'app verrà ora installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-164">The app will now install to the device.</span></span> <span data-ttu-id="3a4b7-165">Per trovare l'app, apri il **menu Start** e seleziona il pulsante Tutte le **app** per trovare l'app.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="3a4b7-166">Per altre informazioni sulla risoluzione dei problemi relativi al metodo di installazione del programma di installazione delle app, visita [la pagina relativa alla risoluzione dei problemi relativi al programma di installazione delle app.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="3a4b7-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="3a4b7-167">L'interfaccia utente durante il processo di aggiornamento non è supportata.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-167">UI during the update process is not supported.</span></span> <span data-ttu-id="3a4b7-168">Pertanto, l'opzione ShowPrompt in [questa pagina e](https://docs.microsoft.com/windows/msix/app-installer/update-settings) le opzioni correlate non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="3a4b7-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="3a4b7-169">App di esempio</span><span class="sxs-lookup"><span data-stu-id="3a4b7-169">Sample Apps</span></span>

<span data-ttu-id="3a4b7-170">Per provare il programma di installazione app con alcune app di esempio, vedere alcuni degli esempi disponibili:</span><span class="sxs-lookup"><span data-stu-id="3a4b7-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="3a4b7-171">Hub degli esempi MRTK</span><span class="sxs-lookup"><span data-stu-id="3a4b7-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="3a4b7-172">Superfici</span><span class="sxs-lookup"><span data-stu-id="3a4b7-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="3a4b7-173">App di esempio UWP che possono essere usate per i test</span><span class="sxs-lookup"><span data-stu-id="3a4b7-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
