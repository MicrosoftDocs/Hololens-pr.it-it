---
title: Come caricare e installare le app tramite il programma di installazione di HoloLens 2 app
description: Informazioni su come installare e risolvere i problemi delle app con il programma di installazione delle app e il caricamento laterale e l'installazione delle app tramite interfaccia utente.
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: af4e222a4f83ab82466a383099897986ddf6b8c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297291"
---
# <span data-ttu-id="ea052-104">Installare app in HoloLens 2 tramite il programma di installazione di app</span><span class="sxs-lookup"><span data-stu-id="ea052-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="ea052-105">Questa caratteristica è stata resa disponibile in [Windows olografico, versione 20H2-dicembre 2020 Update](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="ea052-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="ea052-106">Verificare che il dispositivo sia [aggiornato](hololens-update-hololens.md) per usare questa caratteristica.</span><span class="sxs-lookup"><span data-stu-id="ea052-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="ea052-107">È stata **aggiunta una nuova funzionalità (programma di installazione delle app) per consentire l'installazione di applicazioni più agevolmente** nei dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ea052-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="ea052-108">La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti**.</span><span class="sxs-lookup"><span data-stu-id="ea052-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="ea052-109">Per evitare interruzioni alle aziende, il programma di installazione **delle app non sarà disponibile per i dispositivi gestiti** in questo momento.</span><span class="sxs-lookup"><span data-stu-id="ea052-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="ea052-110">Un dispositivo viene considerato "gestito **" Se una delle opzioni** seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="ea052-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="ea052-111">MDM [registrato](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="ea052-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="ea052-112">Configurato con il [pacchetto di provisioning](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="ea052-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="ea052-113">L' [identità](hololens-identity.md) dell'utente è Azure ad</span><span class="sxs-lookup"><span data-stu-id="ea052-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="ea052-114">Ora è possibile installare le app senza dover abilitare la modalità sviluppatore o usando Device Portal.</span><span class="sxs-lookup"><span data-stu-id="ea052-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="ea052-115">Download (tramite USB o Microsoft Edge) il bundle appx nel dispositivo e passare al bundle appx in Esplora file per richiedere di avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="ea052-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="ea052-116">In alternativa, [avviare un'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="ea052-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="ea052-117">Proprio come le app installate da Microsoft Store o trasferire localmente usando la funzionalità di distribuzione dell'app LOB di MDM, le app devono essere firmate digitalmente con lo [strumento Sign](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e il [certificato usato per firmare deve essere considerato attendibile](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) dal dispositivo HoloLens prima che l'app possa essere distribuita.</span><span class="sxs-lookup"><span data-stu-id="ea052-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="ea052-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea052-118">Requirements</span></span>

### <span data-ttu-id="ea052-119">Per i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="ea052-119">For your devices:</span></span>

<span data-ttu-id="ea052-120">Questa caratteristica è attualmente disponibile nelle build 20H2 olografiche di Windows per dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ea052-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="ea052-121">Verificare che i dispositivi che usano questo metodo vengano [aggiornati](hololens-update-hololens.md).</span><span class="sxs-lookup"><span data-stu-id="ea052-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="ea052-122">Per le tue app:</span><span class="sxs-lookup"><span data-stu-id="ea052-122">For your apps:</span></span>

<span data-ttu-id="ea052-123">La configurazione della soluzione della tua app deve essere **Master** o **Release** perché il programma di installazione dell'app userà le dipendenze dallo Store.</span><span class="sxs-lookup"><span data-stu-id="ea052-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="ea052-124">Vedere altre informazioni sulla [creazione di pacchetti di app](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="ea052-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="ea052-125">Le app installate tramite questo metodo devono essere firmate digitalmente.</span><span class="sxs-lookup"><span data-stu-id="ea052-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="ea052-126">È necessario usare un certificato per firmare l'app.</span><span class="sxs-lookup"><span data-stu-id="ea052-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="ea052-127">Puoi ottenere un certificato dall' [elenco CA attendibile di MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in questo caso non dovrai eseguire altre azioni.</span><span class="sxs-lookup"><span data-stu-id="ea052-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="ea052-128">In alternativa, è possibile firmare il proprio certificato, ma il certificato deve essere inserito nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ea052-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="ea052-129">Come firmare le app [con lo strumento Sign.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="ea052-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="ea052-130">Opzioni certificato:</span><span class="sxs-lookup"><span data-stu-id="ea052-130">Certificate options:</span></span>**

- [<span data-ttu-id="ea052-131">Elenco CA attendibile MS</span><span class="sxs-lookup"><span data-stu-id="ea052-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="ea052-132">Selezionare un metodo di distribuzione del certificato.</span><span class="sxs-lookup"><span data-stu-id="ea052-132">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="ea052-133">I [pacchetti di provisioning](hololens-provisioning.md) possono essere applicati ai dispositivi locali.</span><span class="sxs-lookup"><span data-stu-id="ea052-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="ea052-134">MDM può essere usato per [applicare certificati con configurazioni di dispositivi](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="ea052-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="ea052-135">Usare il [gestore certificati](certificate-manager.md)per dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ea052-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="ea052-136">Metodo di installazione</span><span class="sxs-lookup"><span data-stu-id="ea052-136">Installation method</span></span>

1. <span data-ttu-id="ea052-137">Verificare che il dispositivo non sia considerato gestito.</span><span class="sxs-lookup"><span data-stu-id="ea052-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="ea052-138">Verificare che il dispositivo HoloLens 2 sia acceso e che sia stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ea052-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="ea052-139">Nel PC passare all'app personalizzata e copiare YourApp. appxbundle in yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="ea052-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="ea052-140">Dopo aver completato la copia del file, è possibile disconnettere il dispositivo e terminare l'installazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="ea052-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="ea052-141">Dal dispositivo HoloLens 2 aprire il **menu Start**, selezionare **tutte le app** e avviare l'app **Esplora file** .</span><span class="sxs-lookup"><span data-stu-id="ea052-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="ea052-142">Passare alla cartella Downloads.</span><span class="sxs-lookup"><span data-stu-id="ea052-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="ea052-143">Potrebbe essere necessario nel pannello sinistro dell'app selezionare prima **questo dispositivo** , quindi passare a download.</span><span class="sxs-lookup"><span data-stu-id="ea052-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="ea052-144">Selezionare il file YourApp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="ea052-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="ea052-145">Verrà avviato il programma di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="ea052-145">The App Installer will launch.</span></span> <span data-ttu-id="ea052-146">Selezionare il pulsante **Installa** per installare la tua app.</span><span class="sxs-lookup"><span data-stu-id="ea052-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="ea052-147">L'app installata verrà avviata automaticamente dopo il completamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="ea052-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Installazione di esempi di MRTK tramite il programma di installazione dell'app](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="ea052-149">Risoluzione dei problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="ea052-149">Troubleshooting Installs</span></span>

<span data-ttu-id="ea052-150">Se l'app non è stata installata, controllare quanto segue per risolvere i problemi:</span><span class="sxs-lookup"><span data-stu-id="ea052-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="ea052-151">La tua app è una build master o release.</span><span class="sxs-lookup"><span data-stu-id="ea052-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="ea052-152">Il dispositivo viene aggiornato a una build in cui è disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ea052-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="ea052-153">Si è [connessi a Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="ea052-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="ea052-154">Gli [endpoint per Microsoft Store](hololens-offline.md) sono configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="ea052-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="ea052-155">Web Installer</span><span class="sxs-lookup"><span data-stu-id="ea052-155">Web Installer</span></span>

<span data-ttu-id="ea052-156">Gli utenti possono installare un'app direttamente da un server Web.</span><span class="sxs-lookup"><span data-stu-id="ea052-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="ea052-157">Questo flusso usa il programma di installazione dell'app in combinazione con un metodo di distribuzione facile da scaricare e installare.</span><span class="sxs-lookup"><span data-stu-id="ea052-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="ea052-158">Come configurare l'installazione Web:</span><span class="sxs-lookup"><span data-stu-id="ea052-158">How to set up web install:</span></span>

1. <span data-ttu-id="ea052-159">Verificare che l'app sia configurata correttamente per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="ea052-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="ea052-160">Seguire questa [procedura per abilitare l'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="ea052-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="ea052-161">Esperienza utente finale:</span><span class="sxs-lookup"><span data-stu-id="ea052-161">End user experience:</span></span>

1. <span data-ttu-id="ea052-162">L'utente riceve e installa il certificato nel dispositivo usando un metodo precedentemente selezionato.</span><span class="sxs-lookup"><span data-stu-id="ea052-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="ea052-163">L'utente visita l'URL creato dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="ea052-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="ea052-164">L'app verrà ora installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ea052-164">The app will now install to the device.</span></span> <span data-ttu-id="ea052-165">Per trovare l'app, Apri il **menu Start** e seleziona il pulsante **tutte le app** per trovare la tua app.</span><span class="sxs-lookup"><span data-stu-id="ea052-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="ea052-166">Per altre informazioni sulla risoluzione dei problemi relativi al metodo di installazione dell'app, vedere [risoluzione degli errori](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="ea052-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="ea052-167">L'interfaccia utente durante il processo di aggiornamento non è supportata.</span><span class="sxs-lookup"><span data-stu-id="ea052-167">UI during the update process is not supported.</span></span> <span data-ttu-id="ea052-168">Quindi l'opzione ShowPrompt in [Questa pagina](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e le opzioni correlate non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="ea052-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="ea052-169">App di esempio</span><span class="sxs-lookup"><span data-stu-id="ea052-169">Sample Apps</span></span>

<span data-ttu-id="ea052-170">Per provare il programma di installazione dell'app con alcune app di esempio, vedere alcuni esempi disponibili:</span><span class="sxs-lookup"><span data-stu-id="ea052-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="ea052-171">Hub esempi di MRTK</span><span class="sxs-lookup"><span data-stu-id="ea052-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="ea052-172">Superfici</span><span class="sxs-lookup"><span data-stu-id="ea052-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="ea052-173">App di esempio UWP che possono essere usate per i test</span><span class="sxs-lookup"><span data-stu-id="ea052-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
