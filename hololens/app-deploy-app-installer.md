---
title: Come caricare e installare le app tramite il programma di installazione di HoloLens 2 app
description: Caricare le app e installarle tramite interfaccia utente
keywords: gestione app, app, hololens, app Installer
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
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253093"
---
# <span data-ttu-id="07242-104">Installare app in HoloLens 2 tramite il programma di installazione di app</span><span class="sxs-lookup"><span data-stu-id="07242-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="07242-105">Aggiungiamo **una nuova funzionalità (Installer delle app) per consentire l'installazione delle applicazioni in modo più trasparente** nei dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="07242-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="07242-106">La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti**.</span><span class="sxs-lookup"><span data-stu-id="07242-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="07242-107">Per evitare interruzioni alle aziende, il programma di installazione **delle app non sarà disponibile per i dispositivi gestiti** in questo momento.</span><span class="sxs-lookup"><span data-stu-id="07242-107">To prevent disruption to enterprises, app installer will **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="07242-108">Questa caratteristica è stata resa disponibile in [Windows olografico, versione 20H2-dicembre 2020 Update](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="07242-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="07242-109">Verificare che il dispositivo sia [aggiornato](hololens-update-hololens.md) per usare questa caratteristica.</span><span class="sxs-lookup"><span data-stu-id="07242-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="07242-110">È stata **aggiunta una nuova funzionalità (programma di installazione delle app) per consentire l'installazione di applicazioni più agevolmente** nei dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="07242-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="07242-111">La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti**.</span><span class="sxs-lookup"><span data-stu-id="07242-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="07242-112">Per evitare interruzioni alle aziende, il programma di installazione **delle app non sarà disponibile per i dispositivi gestiti** in questo momento.</span><span class="sxs-lookup"><span data-stu-id="07242-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="07242-113">Un dispositivo viene considerato "gestito **" Se una delle opzioni** seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="07242-113">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="07242-114">MDM [registrato](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="07242-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="07242-115">Configurato con il [pacchetto di provisioning](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="07242-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="07242-116">L' [identità](hololens-identity.md) dell'utente è Azure ad</span><span class="sxs-lookup"><span data-stu-id="07242-116">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="07242-117">Ora è possibile installare le app senza dover abilitare la modalità sviluppatore o usando Device Portal.</span><span class="sxs-lookup"><span data-stu-id="07242-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="07242-118">Download (tramite USB o Microsoft Edge) il bundle appx nel dispositivo e passare al bundle appx in Esplora file per richiedere di avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="07242-118">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="07242-119">In alternativa, [avviare un'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="07242-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="07242-120">Proprio come le app installate da Microsoft Store o trasferire localmente usando la funzionalità di distribuzione dell'app LOB di MDM, le app devono essere firmate digitalmente con lo [strumento Sign](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e il [certificato usato per firmare deve essere considerato attendibile](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) dal dispositivo HoloLens prima che l'app possa essere distribuita.</span><span class="sxs-lookup"><span data-stu-id="07242-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="07242-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07242-121">Requirements</span></span>

### <span data-ttu-id="07242-122">Per i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="07242-122">For your devices:</span></span>

 <span data-ttu-id="07242-123">la caratteristica è attualmente disponibile nelle build 20H2 olografiche di Windows per i dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="07242-123">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="07242-124">Verificare che i dispositivi che usano questo metodo vengano [aggiornati](hololens-update-hololens.md).</span><span class="sxs-lookup"><span data-stu-id="07242-124">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="07242-125">Per le tue app:</span><span class="sxs-lookup"><span data-stu-id="07242-125">For your apps:</span></span> 
<span data-ttu-id="07242-126">La configurazione della soluzione della tua app deve essere **Master** o **Release** perché il programma di installazione dell'app userà le dipendenze dallo Store.</span><span class="sxs-lookup"><span data-stu-id="07242-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="07242-127">Vedere altre informazioni sulla [creazione di pacchetti di app](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="07242-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="07242-128">Le app installate tramite questo metodo devono essere firmate digitalmente.</span><span class="sxs-lookup"><span data-stu-id="07242-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="07242-129">È necessario usare un certificato per firmare l'app.</span><span class="sxs-lookup"><span data-stu-id="07242-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="07242-130">Puoi ottenere un certificato dall' [elenco CA attendibile di MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in questo caso non dovrai eseguire altre azioni.</span><span class="sxs-lookup"><span data-stu-id="07242-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="07242-131">In alternativa, è possibile firmare il proprio certificato, ma il certificato deve essere inserito nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07242-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="07242-132">Come firmare le app [con lo strumento Sign.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="07242-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="07242-133">Opzioni certificato:</span><span class="sxs-lookup"><span data-stu-id="07242-133">Certificate options:</span></span>**

- [<span data-ttu-id="07242-134">Elenco CA attendibile MS</span><span class="sxs-lookup"><span data-stu-id="07242-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="07242-135">Selezionare un metodo di distribuzione del certificato.</span><span class="sxs-lookup"><span data-stu-id="07242-135">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="07242-136">I [pacchetti di provisioning](hololens-provisioning.md) possono essere applicati ai dispositivi locali.</span><span class="sxs-lookup"><span data-stu-id="07242-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="07242-137">MDM può essere usato per [applicare certificati con configurazioni di dispositivi](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="07242-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="07242-138">Usare il [gestore certificati](certificate-manager.md)per dispositivi.</span><span class="sxs-lookup"><span data-stu-id="07242-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="07242-139">Metodo di installazione</span><span class="sxs-lookup"><span data-stu-id="07242-139">Installation method</span></span>

1. <span data-ttu-id="07242-140">Verificare che il dispositivo non sia considerato gestito.</span><span class="sxs-lookup"><span data-stu-id="07242-140">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="07242-141">Verificare che il dispositivo HoloLens 2 sia acceso e che sia stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="07242-141">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="07242-142">Nel PC passare all'app personalizzata e copiare YourApp. appxbundle in yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="07242-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="07242-143">Dopo aver completato la copia del file, è possibile disconnettere il dispositivo e terminare l'installazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="07242-143">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="07242-144">Dal dispositivo HoloLens 2 aprire il **menu Start**, selezionare **tutte le app** e avviare l'app **Esplora file** .</span><span class="sxs-lookup"><span data-stu-id="07242-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="07242-145">Passare alla cartella Downloads.</span><span class="sxs-lookup"><span data-stu-id="07242-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="07242-146">Potrebbe essere necessario nel pannello sinistro dell'app selezionare prima **questo dispositivo** , quindi passare a download.</span><span class="sxs-lookup"><span data-stu-id="07242-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="07242-147">Selezionare il file YourApp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="07242-147">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="07242-148">Verrà avviato il programma di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="07242-148">The App Installer will launch.</span></span> <span data-ttu-id="07242-149">Selezionare il pulsante **Installa** per installare la tua app.</span><span class="sxs-lookup"><span data-stu-id="07242-149">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="07242-150">L'app installata verrà avviata automaticamente dopo il completamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="07242-150">The installed app will automatically launch upon the completion of installing.</span></span>

![Installazione di esempi di MRTK tramite il programma di installazione dell'app](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="07242-152">Risoluzione dei problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="07242-152">Troubleshooting Installs</span></span>

<span data-ttu-id="07242-153">Se la tua app non è riuscita a installare, controlla quanto segue per risolvere i problemi:</span><span class="sxs-lookup"><span data-stu-id="07242-153">If your app failed to install check the following to troubleshoot:</span></span>

- <span data-ttu-id="07242-154">La tua app è una build master o release.</span><span class="sxs-lookup"><span data-stu-id="07242-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="07242-155">Il dispositivo viene aggiornato a una build in cui è disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="07242-155">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="07242-156">Si è [connessi a Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="07242-156">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="07242-157">Gli [endpoint per Microsoft Store](hololens-offline.md) sono configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="07242-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="07242-158">Web Installer</span><span class="sxs-lookup"><span data-stu-id="07242-158">Web Installer</span></span>

<span data-ttu-id="07242-159">Gli utenti possono installare un'app direttamente da un server Web.</span><span class="sxs-lookup"><span data-stu-id="07242-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="07242-160">Questo flusso usa il programma di installazione dell'app in combinazione con un metodo di distribuzione facile da scaricare e installare.</span><span class="sxs-lookup"><span data-stu-id="07242-160">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="07242-161">Come configurare l'installazione Web:</span><span class="sxs-lookup"><span data-stu-id="07242-161">How to set up web install:</span></span>

1. <span data-ttu-id="07242-162">Verificare che l'app sia configurata correttamente per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="07242-162">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="07242-163">Seguire questa [procedura per abilitare l'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="07242-163">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="07242-164">Esperienza utente finale:</span><span class="sxs-lookup"><span data-stu-id="07242-164">End user experience:</span></span>

1. <span data-ttu-id="07242-165">L'utente riceve e installa il certificato nel dispositivo usando un metodo precedentemente selezionato.</span><span class="sxs-lookup"><span data-stu-id="07242-165">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="07242-166">L'utente visita l'URL creato dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="07242-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="07242-167">L'app verrà ora installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07242-167">The app will now install to the device.</span></span> <span data-ttu-id="07242-168">Per trovare l'app, Apri il **menu Start** e seleziona il pulsante **tutte le app** per trovare la tua app.</span><span class="sxs-lookup"><span data-stu-id="07242-168">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="07242-169">Per altre informazioni sulla risoluzione dei problemi relativi al metodo di installazione dell'app, vedere [risoluzione degli errori](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="07242-169">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="07242-170">L'interfaccia utente durante il processo di aggiornamento non è supportata.</span><span class="sxs-lookup"><span data-stu-id="07242-170">UI during the update process is not supported.</span></span> <span data-ttu-id="07242-171">Quindi l'opzione ShowPrompt in [Questa pagina](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e le opzioni correlate non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="07242-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="07242-172">App di esempio</span><span class="sxs-lookup"><span data-stu-id="07242-172">Sample Apps</span></span>

<span data-ttu-id="07242-173">Per provare il programma di installazione dell'app con alcune app di esempio, vedere alcuni esempi disponibili:</span><span class="sxs-lookup"><span data-stu-id="07242-173">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="07242-174">Hub esempi di MRTK</span><span class="sxs-lookup"><span data-stu-id="07242-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="07242-175">Superfici</span><span class="sxs-lookup"><span data-stu-id="07242-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="07242-176">App di esempio UWP che possono essere usate per i test</span><span class="sxs-lookup"><span data-stu-id="07242-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
