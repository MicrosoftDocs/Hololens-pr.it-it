---
title: Come caricare e installare le app tramite il programma di installazione di HoloLens 2 app
description: Caricare le app e installarle tramite interfaccia utente
keywords: gestione app, app, hololens, app Installer
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 415733bb2809b7ae2808edc097423f8928910c57
ms.sourcegitcommit: c4fd9a87bb7c728c73418f95a1b15dd93b0af7c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "11150917"
---
# <span data-ttu-id="e5004-104">Installare app in HoloLens 2 tramite il programma di installazione di app</span><span class="sxs-lookup"><span data-stu-id="e5004-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5004-105">Questa caratteristica è attualmente solo avalible in Windows Insider Build 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="e5004-105">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="e5004-106">[Altre informazioni su come iscriversi alle build di Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="e5004-106">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

<span data-ttu-id="e5004-107">In Windows Insider Release aggiungiamo **una nuova funzionalità (programma di installazione delle app) per consentire l'installazione di applicazioni più agevolmente** nei dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e5004-107">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="e5004-108">La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti**.</span><span class="sxs-lookup"><span data-stu-id="e5004-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="e5004-109">Per evitare interruzioni alle aziende, il programma di installazione **delle app non sarà disponibile per i dispositivi gestiti** in questo momento.</span><span class="sxs-lookup"><span data-stu-id="e5004-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="e5004-110">Un dispositivo viene considerato "gestito **" Se una delle opzioni** seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="e5004-110">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="e5004-111">MDM [registrato](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="e5004-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="e5004-112">Configurato con il [pacchetto di provisioning](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="e5004-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="e5004-113">L' [identità](hololens-identity.md) dell'utente è AAD</span><span class="sxs-lookup"><span data-stu-id="e5004-113">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="e5004-114">Ora è possibile installare le app senza dover abilitare la modalità sviluppatore o usando Device Portal.</span><span class="sxs-lookup"><span data-stu-id="e5004-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="e5004-115">È sufficiente scaricare (tramite USB o Edge) il bundle appx nel dispositivo e passare al bundle appx in Esplora file per richiedere di avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="e5004-115">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="e5004-116">In alternativa, [avviare un'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="e5004-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="e5004-117">Proprio come le app installate da Microsoft Store o trasferire localmente usando la funzionalità di distribuzione dell'app LOB di MDM, le app devono essere firmate digitalmente con lo [strumento Sign](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e il [certificato usato per firmare deve essere considerato attendibile](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) dal dispositivo HoloLens prima che l'app possa essere distribuita.</span><span class="sxs-lookup"><span data-stu-id="e5004-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="e5004-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5004-118">Requirements</span></span>

### <span data-ttu-id="e5004-119">Per i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="e5004-119">For your devices:</span></span> 
> [!NOTE]
> <span data-ttu-id="e5004-120">Questa caratteristica è attualmente solo avalible in Windows Insider Build 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="e5004-120">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="e5004-121">[Altre informazioni su come iscriversi alle build di Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="e5004-121">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

### <span data-ttu-id="e5004-122">Per le tue app:</span><span class="sxs-lookup"><span data-stu-id="e5004-122">For your apps:</span></span> 
<span data-ttu-id="e5004-123">La configurazione della soluzione della tua app deve essere **Master** o **Release** perché il programma di installazione dell'app userà le dipendenze dallo Store.</span><span class="sxs-lookup"><span data-stu-id="e5004-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="e5004-124">Vedere altre informazioni sulla [creazione di pacchetti di app](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="e5004-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="e5004-125">Le app installate tramite questo metodo devono essere firmate digitalmente.</span><span class="sxs-lookup"><span data-stu-id="e5004-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="e5004-126">È necessario usare un certificato per firmare l'app.</span><span class="sxs-lookup"><span data-stu-id="e5004-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="e5004-127">Puoi ottenere un certificato dall' [elenco CA attendibile di MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in questo caso non dovrai eseguire altre azioni.</span><span class="sxs-lookup"><span data-stu-id="e5004-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="e5004-128">In alternativa, è possibile firmare il proprio certificato, ma il certificato deve essere inserito nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5004-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="e5004-129">Come firmare le app [con lo strumento Sign.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="e5004-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="e5004-130">Opzioni certificato:</span><span class="sxs-lookup"><span data-stu-id="e5004-130">Certificate options:</span></span>** 
- [<span data-ttu-id="e5004-131">Elenco CA attendibile MS</span><span class="sxs-lookup"><span data-stu-id="e5004-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="e5004-132">Selezionare un metodo di distribuzione del certificato.</span><span class="sxs-lookup"><span data-stu-id="e5004-132">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="e5004-133">I [pacchetti di provisioning](hololens-provisioning.md) possono essere applicati ai dispositivi locali.</span><span class="sxs-lookup"><span data-stu-id="e5004-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="e5004-134">MDM può essere usato per [applicare certificati con configurazioni di dispositivi](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="e5004-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="e5004-135">Usare il [gestore certificati](hololens-insider.md#certificate-manager)per dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e5004-135">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="e5004-136">Metodo di installazione</span><span class="sxs-lookup"><span data-stu-id="e5004-136">Installation method</span></span>

1.  <span data-ttu-id="e5004-137">Verificare che il dispositivo non sia considerato gestito.</span><span class="sxs-lookup"><span data-stu-id="e5004-137">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="e5004-138">Verificare che il dispositivo HoloLens 2 sia acceso e che sia stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e5004-138">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="e5004-139">Nel PC passare all'app personalizzata e copiare YourApp. appxbundle in yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="e5004-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="e5004-140">Una volta completata la copia del file, è possibile scollegare il dispositivo e completare l'installazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e5004-140">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="e5004-141">Dal dispositivo HoloLens 2 aprire il **menu Start**, selezionare **tutte le app** e avviare l'app **Esplora file** .</span><span class="sxs-lookup"><span data-stu-id="e5004-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="e5004-142">Passare alla cartella Downloads.</span><span class="sxs-lookup"><span data-stu-id="e5004-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="e5004-143">Potrebbe essere necessario nel pannello sinistro dell'app selezionare prima **questo dispositivo** , quindi passare a download.</span><span class="sxs-lookup"><span data-stu-id="e5004-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="e5004-144">Selezionare il file YourApp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="e5004-144">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="e5004-145">Verrà avviato il programma di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="e5004-145">The App Installer will launch.</span></span> <span data-ttu-id="e5004-146">Selezionare il pulsante **Installa** per installare la tua app.</span><span class="sxs-lookup"><span data-stu-id="e5004-146">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="e5004-147">L'app installata verrà avviata automaticamente dopo il completamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="e5004-147">The installed app will automatically launch upon the completion of installing.</span></span> 

![Installazione di esempi di MRTK tramite il programma di installazione dell'app](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="e5004-149">Risoluzione dei problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="e5004-149">Troubleshooting Installs</span></span>
<span data-ttu-id="e5004-150">Se l'app non è stata installata, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e5004-150">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="e5004-151">La tua app è una build master o release.</span><span class="sxs-lookup"><span data-stu-id="e5004-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="e5004-152">Il dispositivo viene aggiornato a una build in cui è disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e5004-152">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="e5004-153">Si è [connessi a Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="e5004-153">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="e5004-154">Gli [endpoint per Microsoft Store](hololens-offline.md) sono configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="e5004-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="e5004-155">Web Installer</span><span class="sxs-lookup"><span data-stu-id="e5004-155">Web Installer</span></span>

<span data-ttu-id="e5004-156">Gli utenti possono installare un'app direttamente da un server Web.</span><span class="sxs-lookup"><span data-stu-id="e5004-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="e5004-157">In questo modo si usa il programma di installazione dell'app in combinazione con un metodo di distribuzione facile da scaricare e installare.</span><span class="sxs-lookup"><span data-stu-id="e5004-157">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="e5004-158">Come configurare l'installazione Web:</span><span class="sxs-lookup"><span data-stu-id="e5004-158">How to set up web install:</span></span>
1.  <span data-ttu-id="e5004-159">Verificare che l'app sia configurata correttamente per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="e5004-159">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="e5004-160">Seguire [questa procedura per abilitare questa operazione in una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="e5004-160">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="e5004-161">Esperienza utente finale:</span><span class="sxs-lookup"><span data-stu-id="e5004-161">End user experience:</span></span>
1. <span data-ttu-id="e5004-162">L'utente riceve e installa il certificato nel dispositivo usando un metodo precedentemente selezionato.</span><span class="sxs-lookup"><span data-stu-id="e5004-162">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="e5004-163">L'utente visita l'URL creato dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="e5004-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="e5004-164">L'app verrà ora installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5004-164">The app will now install to the device.</span></span> <span data-ttu-id="e5004-165">Per trovare l'app, Apri il **menu Start** e seleziona il pulsante **tutte** le app per trovare la tua app.</span><span class="sxs-lookup"><span data-stu-id="e5004-165">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="e5004-166">Per informazioni sulla risoluzione dei problemi di questo metodo di installazione, vedere [risoluzione di errori di installazione dell'app](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span><span class="sxs-lookup"><span data-stu-id="e5004-166">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="e5004-167">L'interfaccia utente durante il processo di aggiornamento non è supportata.</span><span class="sxs-lookup"><span data-stu-id="e5004-167">UI during the update process is not supported.</span></span> <span data-ttu-id="e5004-168">Quindi l'opzione ShowPrompt in [Questa pagina](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e le opzioni correlate non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="e5004-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="e5004-169">App di esempio</span><span class="sxs-lookup"><span data-stu-id="e5004-169">Sample Apps</span></span>

<span data-ttu-id="e5004-170">Se si vuole provare questa soluzione con alcune app di esempio, vedere alcuni esempi disponibili:</span><span class="sxs-lookup"><span data-stu-id="e5004-170">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="e5004-171">Hub esempi di MRTK</span><span class="sxs-lookup"><span data-stu-id="e5004-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="e5004-172">Superfici</span><span class="sxs-lookup"><span data-stu-id="e5004-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="e5004-173">App di esempio UWP che possono essere usate per i test</span><span class="sxs-lookup"><span data-stu-id="e5004-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
