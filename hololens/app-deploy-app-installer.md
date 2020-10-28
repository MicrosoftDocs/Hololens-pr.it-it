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
ms.openlocfilehash: 4e2256f1086c92cdf0e788ba9dddf5b74a733116
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135527"
---
# <span data-ttu-id="7b0ad-104">Installare app in HoloLens 2 tramite il programma di installazione di app</span><span class="sxs-lookup"><span data-stu-id="7b0ad-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="7b0ad-105">In Windows Insider Release aggiungiamo **una nuova funzionalità (programma di installazione delle app) per consentire l'installazione di applicazioni più agevolmente** nei dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-105">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span>  <span data-ttu-id="7b0ad-106">Ora è possibile installare le app senza dover abilitare la modalità sviluppatore o usando Device Portal.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-106">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="7b0ad-107">È sufficiente scaricare (tramite USB o Edge) il bundle appx nel dispositivo e passare al bundle appx in Esplora file per richiedere di avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-107">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="7b0ad-108">In alternativa, [avviare un'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="7b0ad-108">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="7b0ad-109">Proprio come le app installate da Microsoft Store o trasferire localmente usando la funzionalità di distribuzione dell'app LOB di MDM, le app devono essere firmate digitalmente con lo [strumento Sign](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e il [certificato usato per firmare deve essere considerato attendibile](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) dal dispositivo HoloLens prima che l'app possa essere distribuita.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-109">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

<span data-ttu-id="7b0ad-110">Questo aggiornamento è allineato al desktop [in cui sideload è abilitato per impostazione predefinita](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)</span><span class="sxs-lookup"><span data-stu-id="7b0ad-110">This update aligns with desktop where [Sideloading is Enabled by Default](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b0ad-111">Questa caratteristica è attualmente solo avalible in Windows Insider Build 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-111">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="7b0ad-112">[Altre informazioni su come iscriversi alle build di Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="7b0ad-112">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7b0ad-113">Per gli amministratori IT che desiderano disabilitare questa funzionalità, usare il nome della famiglia di pacchetti seguente come parte dei [criteri di WDAC](windows-defender-application-control-wdac.md).</span><span class="sxs-lookup"><span data-stu-id="7b0ad-113">For IT Admins who wish to disable this feature please use the following package family name as part of your [WDAC policy](windows-defender-application-control-wdac.md).</span></span> <span data-ttu-id="7b0ad-114">In questo modo si bloccherà solo l'app del programma di installazione delle app e non le app installate da altre origini, ad esempio Microsoft Store o dalla soluzione MDM.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-114">This will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>
```
Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```
> [!NOTE]
> <span data-ttu-id="7b0ad-115">È consigliabile usare i [criteri di WDAC](windows-defender-application-control-wdac.md) per controllare le app, ma se vuoi consentire solo alle app di Microsoft Store, i dispositivi configurati per impostare esplicitamente i criteri [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) su "non consentire" consentiranno l'installazione delle app solo da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-115">It is recommended to use [WDAC policy](windows-defender-application-control-wdac.md) to control apps, however if you only want to allow Microsoft Store apps, devices configured to set the [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) policy explicitly to “not allow” will only allow apps to be installed from the Microsoft Store.</span></span> 

## <span data-ttu-id="7b0ad-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b0ad-116">Requirements</span></span>

### <span data-ttu-id="7b0ad-117">Per i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="7b0ad-117">For your devices:</span></span> 
> [!NOTE]
> <span data-ttu-id="7b0ad-118">Questa caratteristica è attualmente solo avalible in Windows Insider Build 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-118">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="7b0ad-119">[Altre informazioni su come iscriversi alle build di Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="7b0ad-119">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

### <span data-ttu-id="7b0ad-120">Per le tue app:</span><span class="sxs-lookup"><span data-stu-id="7b0ad-120">For your apps:</span></span> 
<span data-ttu-id="7b0ad-121">La configurazione della soluzione della tua app deve essere **Master** o **Release** perché il programma di installazione dell'app userà le dipendenze dallo Store.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-121">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="7b0ad-122">Vedere altre informazioni sulla [creazione di pacchetti di app](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="7b0ad-122">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="7b0ad-123">Le app installate tramite questo metodo devono essere firmate digitalmente.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-123">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="7b0ad-124">È necessario usare un certificato per firmare l'app.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-124">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="7b0ad-125">Puoi ottenere un certificato dall' [elenco CA attendibile di MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in questo caso non dovrai eseguire altre azioni.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-125">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="7b0ad-126">In alternativa, è possibile firmare il proprio certificato, ma il certificato deve essere inserito nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-126">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="7b0ad-127">Come firmare le app [con lo strumento Sign.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="7b0ad-127">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="7b0ad-128">Opzioni certificato:</span><span class="sxs-lookup"><span data-stu-id="7b0ad-128">Certificate options:</span></span>** 
- [<span data-ttu-id="7b0ad-129">Elenco CA attendibile MS</span><span class="sxs-lookup"><span data-stu-id="7b0ad-129">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="7b0ad-130">Selezionare un metodo di distribuzione del certificato.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-130">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="7b0ad-131">I [pacchetti di provisioning](hololens-provisioning.md) possono essere applicati ai dispositivi locali.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-131">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="7b0ad-132">MDM può essere usato per [applicare certificati con configurazioni di dispositivi](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="7b0ad-132">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="7b0ad-133">Usare il [gestore certificati](hololens-insider.md#certificate-manager)per dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-133">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="7b0ad-134">Metodo di installazione</span><span class="sxs-lookup"><span data-stu-id="7b0ad-134">Installation method</span></span>

1.  <span data-ttu-id="7b0ad-135">Verificare che il dispositivo HoloLens 2 sia acceso e che sia stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-135">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="7b0ad-136">Nel PC passare all'app personalizzata e copiare YourApp. appxbundle in yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-136">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="7b0ad-137">Una volta completata la copia del file, è possibile scollegare il dispositivo e completare l'installazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-137">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="7b0ad-138">Dal dispositivo HoloLens 2 aprire il **menu Start**, selezionare **tutte le app** e avviare l'app **Esplora file** .</span><span class="sxs-lookup"><span data-stu-id="7b0ad-138">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="7b0ad-139">Passare alla cartella Downloads.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-139">Navigate to the Downloads folder.</span></span> <span data-ttu-id="7b0ad-140">Potrebbe essere necessario nel pannello sinistro dell'app selezionare prima **questo dispositivo** , quindi passare a download.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-140">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="7b0ad-141">Selezionare il file YourApp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-141">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="7b0ad-142">Verrà avviato il programma di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-142">The App Installer will launch.</span></span> <span data-ttu-id="7b0ad-143">Selezionare il pulsante **Installa** per installare la tua app.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-143">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="7b0ad-144">L'app installata verrà avviata automaticamente dopo il completamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-144">The installed app will automatically launch upon the completion of installing.</span></span> 

![Installazione di esempi di MRTK tramite il programma di installazione dell'app](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="7b0ad-146">Risoluzione dei problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="7b0ad-146">Troubleshooting Installs</span></span>
<span data-ttu-id="7b0ad-147">Se l'app non è stata installata, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7b0ad-147">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="7b0ad-148">La tua app è una build master o release.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-148">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="7b0ad-149">Il dispositivo viene aggiornato a una build in cui è disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-149">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="7b0ad-150">Si è [connessi a Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="7b0ad-150">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="7b0ad-151">Gli [endpoint per Microsoft Store](hololens-offline.md) sono configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-151">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="7b0ad-152">Web Installer</span><span class="sxs-lookup"><span data-stu-id="7b0ad-152">Web Installer</span></span>

<span data-ttu-id="7b0ad-153">Gli utenti possono installare un'app direttamente da un server Web.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-153">Users can install an app directly from a web server.</span></span> <span data-ttu-id="7b0ad-154">In questo modo si usa il programma di installazione dell'app in combinazione con un metodo di distribuzione facile da scaricare e installare.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-154">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="7b0ad-155">Come configurare l'installazione Web:</span><span class="sxs-lookup"><span data-stu-id="7b0ad-155">How to set up web install:</span></span>
1.  <span data-ttu-id="7b0ad-156">Verificare che l'app sia configurata correttamente per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-156">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="7b0ad-157">Seguire [questa procedura per abilitare questa operazione in una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="7b0ad-157">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="7b0ad-158">Esperienza utente finale:</span><span class="sxs-lookup"><span data-stu-id="7b0ad-158">End user experience:</span></span>
1. <span data-ttu-id="7b0ad-159">L'utente riceve e installa il certificato nel dispositivo usando un metodo precedentemente selezionato.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-159">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="7b0ad-160">L'utente visita l'URL creato dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-160">User visits the URL created from the step above.</span></span>

<span data-ttu-id="7b0ad-161">L'app verrà ora installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-161">The app will now install to the device.</span></span> <span data-ttu-id="7b0ad-162">Per trovare l'app, Apri il **menu Start** e seleziona il pulsante **tutte** le app per trovare la tua app.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-162">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="7b0ad-163">Per informazioni sulla risoluzione dei problemi di questo metodo di installazione, vedere [risoluzione di errori di installazione dell'app](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span><span class="sxs-lookup"><span data-stu-id="7b0ad-163">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="7b0ad-164">L'interfaccia utente durante il processo di aggiornamento non è supportata.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-164">UI during the update process is not supported.</span></span> <span data-ttu-id="7b0ad-165">Quindi l'opzione ShowPrompt in [Questa pagina](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e le opzioni correlate non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="7b0ad-165">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="7b0ad-166">App di esempio</span><span class="sxs-lookup"><span data-stu-id="7b0ad-166">Sample Apps</span></span>

<span data-ttu-id="7b0ad-167">Se si vuole provare questa soluzione con alcune app di esempio, vedere alcuni esempi disponibili:</span><span class="sxs-lookup"><span data-stu-id="7b0ad-167">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="7b0ad-168">Hub esempi di MRTK</span><span class="sxs-lookup"><span data-stu-id="7b0ad-168">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="7b0ad-169">Superfici</span><span class="sxs-lookup"><span data-stu-id="7b0ad-169">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="7b0ad-170">App di esempio UWP che possono essere usate per i test</span><span class="sxs-lookup"><span data-stu-id="7b0ad-170">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
