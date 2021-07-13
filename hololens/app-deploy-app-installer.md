---
title: Come eseguire il side load e installare le app tramite HoloLens 2 Programma di installazione app
description: Informazioni su come installare e risolvere i problemi delle app con il programma di installazione delle app e il caricamento laterale e installare le app tramite l'interfaccia utente.
keywords: gestione delle app, app, hololens, programma di installazione delle app
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635586"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="72aeb-104">Installare app in HoloLens 2 tramite Programma di installazione app</span><span class="sxs-lookup"><span data-stu-id="72aeb-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="72aeb-105">Questa funzionalità è stata resa disponibile in [Windows Holographic, versione 20H2 - Aggiornamento di dicembre 2020](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="72aeb-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="72aeb-106">Assicurarsi che il dispositivo [sia aggiornato](hololens-update-hololens.md) per usare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="72aeb-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="72aeb-107">È stata aggiunta una nuova funzionalità **(Programma di installazione app)** per consentire di installare le applicazioni in modo più semplice nei HoloLens 2 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="72aeb-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="72aeb-108">La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti.**</span><span class="sxs-lookup"><span data-stu-id="72aeb-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="72aeb-109">Per evitare interruzioni per le aziende, il programma di installazione delle app non **sarà attualmente disponibile per** i dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="72aeb-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="72aeb-110">Un dispositivo viene considerato "gestito" **se si** verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="72aeb-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="72aeb-111">MDM [registrato](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="72aeb-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="72aeb-112">Configurato con il [pacchetto di provisioning](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="72aeb-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="72aeb-113">[L'identità utente](hololens-identity.md) Azure AD</span><span class="sxs-lookup"><span data-stu-id="72aeb-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="72aeb-114">È ora possibile installare le app senza dover abilitare la modalità sviluppatore o usare Portale di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="72aeb-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="72aeb-115">Scaricare (tramite USB o tramite Microsoft Edge) il bundle Appx nel dispositivo e passare al bundle Appx nel Esplora file per chiedere di avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="72aeb-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="72aeb-116">In alternativa, [avviare un'installazione da una pagina Web](/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="72aeb-116">Alternatively, [initiate an install from a web page](/windows/msix/app-installer/installing-windows10-apps-web).</span></span> <span data-ttu-id="72aeb-117">Proprio come le app installate dal Microsoft Store o il sideload usando la funzionalità di distribuzione di app [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) LOB [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) MDM, le app devono essere firmate digitalmente con lo strumento di firma e il certificato usato per firmare deve essere considerato attendibile dal dispositivo HoloLens prima che l'app possa essere distribuita.</span><span class="sxs-lookup"><span data-stu-id="72aeb-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="72aeb-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72aeb-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="72aeb-119">Per i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="72aeb-119">For your devices:</span></span>

<span data-ttu-id="72aeb-120">Questa funzionalità è attualmente disponibile nelle build Windows Holographic 20H2 per HoloLens 2 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="72aeb-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="72aeb-121">Assicurarsi che tutti i dispositivi che usano questo metodo siano [aggiornati.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="72aeb-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="72aeb-122">Per le app:</span><span class="sxs-lookup"><span data-stu-id="72aeb-122">For your apps:</span></span>

<span data-ttu-id="72aeb-123">La configurazione della soluzione dell'app deve essere **Master** o **Release** perché il Programma di installazione app userà le dipendenze dallo Store.</span><span class="sxs-lookup"><span data-stu-id="72aeb-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="72aeb-124">Vedere altre informazioni sulla [creazione di pacchetti di app.](/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="72aeb-124">See more about [creating app packages](/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="72aeb-125">Le app installate tramite questo metodo devono essere firmate digitalmente.</span><span class="sxs-lookup"><span data-stu-id="72aeb-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="72aeb-126">È necessario usare un certificato per firmare l'app.</span><span class="sxs-lookup"><span data-stu-id="72aeb-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="72aeb-127">È possibile ottenere un certificato dall'elenco di [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)attendibili ms , nel qual caso non sarà necessario eseguire alcuna azione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="72aeb-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="72aeb-128">Oppure è possibile firmare il proprio certificato, tuttavia tale certificato dovrà essere inserito nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72aeb-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="72aeb-129">Come firmare le [app usando lo strumento di firma.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="72aeb-129">How to sign apps [using the Sign Tool.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="72aeb-130">**Opzioni del certificato:**</span><span class="sxs-lookup"><span data-stu-id="72aeb-130">**Certificate options:**</span></span>

- [<span data-ttu-id="72aeb-131">Elenco di CA attendibili ms</span><span class="sxs-lookup"><span data-stu-id="72aeb-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="72aeb-132">**Selezionare un metodo di distribuzione del certificato.**</span><span class="sxs-lookup"><span data-stu-id="72aeb-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="72aeb-133">[I pacchetti di](hololens-provisioning.md) provisioning possono essere applicati ai dispositivi locali.</span><span class="sxs-lookup"><span data-stu-id="72aeb-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="72aeb-134">MDM può essere usato per [applicare i certificati con le configurazioni dei dispositivi.](/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="72aeb-134">MDM can be used to [apply certificates with device configurations](/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="72aeb-135">Usare gestione certificati [nel dispositivo](certificate-manager.md).</span><span class="sxs-lookup"><span data-stu-id="72aeb-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="72aeb-136">Metodo di installazione</span><span class="sxs-lookup"><span data-stu-id="72aeb-136">Installation method</span></span>

1. <span data-ttu-id="72aeb-137">Verificare che il dispositivo non sia considerato gestito.</span><span class="sxs-lookup"><span data-stu-id="72aeb-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="72aeb-138">Verificare che il HoloLens 2 sia acceso e che sia stato eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="72aeb-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="72aeb-139">Nel PC passare all'app personalizzata e copiare yourapp.appxbundle indevicename\Internal Archiviazione\Downloads.</span><span class="sxs-lookup"><span data-stu-id="72aeb-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="72aeb-140">Al termine della copia del file, è possibile disconnettere il dispositivo e completare l'installazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="72aeb-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="72aeb-141">Dal dispositivo HoloLens 2 aprire il **menu Start,** selezionare Tutte le **app** e avviare l'app **Esplora file** app.</span><span class="sxs-lookup"><span data-stu-id="72aeb-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="72aeb-142">Passare alla cartella Download.</span><span class="sxs-lookup"><span data-stu-id="72aeb-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="72aeb-143">Potrebbe essere necessario nel pannello sinistro dell'app selezionare **Prima questo dispositivo,** quindi passare a Download.</span><span class="sxs-lookup"><span data-stu-id="72aeb-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="72aeb-144">Selezionare il file yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="72aeb-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="72aeb-145">Il Programma di installazione app verrà avviato.</span><span class="sxs-lookup"><span data-stu-id="72aeb-145">The App Installer will launch.</span></span> <span data-ttu-id="72aeb-146">Selezionare il **pulsante Installa** per installare l'app.</span><span class="sxs-lookup"><span data-stu-id="72aeb-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="72aeb-147">L'app installata verrà avviata automaticamente al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="72aeb-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Installazione di esempi MRTK tramite Programma di installazione app](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="72aeb-149">Risoluzione dei problemi relativi alle installazioni</span><span class="sxs-lookup"><span data-stu-id="72aeb-149">Troubleshooting Installs</span></span>

<span data-ttu-id="72aeb-150">Se l'installazione dell'app non è riuscita, controllare quanto segue per risolvere i problemi:</span><span class="sxs-lookup"><span data-stu-id="72aeb-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="72aeb-151">L'app è una build master o di versione.</span><span class="sxs-lookup"><span data-stu-id="72aeb-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="72aeb-152">Il dispositivo viene aggiornato a una build in cui è disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="72aeb-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="72aeb-153">Si è [connessi a Internet.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="72aeb-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="72aeb-154">Gli [endpoint per l'Microsoft Store](hololens-offline.md) sono configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="72aeb-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="72aeb-155">Programma di installazione Web</span><span class="sxs-lookup"><span data-stu-id="72aeb-155">Web Installer</span></span>

<span data-ttu-id="72aeb-156">Gli utenti possono installare un'app direttamente da un server Web.</span><span class="sxs-lookup"><span data-stu-id="72aeb-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="72aeb-157">Questo flusso usa l'Programma di installazione app combinato con un metodo di distribuzione di download e installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="72aeb-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="72aeb-158">Come configurare l'installazione Web:</span><span class="sxs-lookup"><span data-stu-id="72aeb-158">How to set up web install:</span></span>

1. <span data-ttu-id="72aeb-159">Verificare che l'app sia configurata correttamente per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="72aeb-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="72aeb-160">Seguire questa [procedura per abilitare l'installazione da una pagina Web](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="72aeb-160">Follow these [steps to enable install from a web page](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="72aeb-161">Esperienza utente finale:</span><span class="sxs-lookup"><span data-stu-id="72aeb-161">End user experience:</span></span>

1. <span data-ttu-id="72aeb-162">L'utente riceve e installa il certificato nel dispositivo usando un metodo scelto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="72aeb-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="72aeb-163">L'utente visita l'URL creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="72aeb-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="72aeb-164">L'app verrà ora installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72aeb-164">The app will now install to the device.</span></span> <span data-ttu-id="72aeb-165">Per trovare l'app, aprire il **menu Start** e selezionare il pulsante **Tutte** le app per trovare l'app.</span><span class="sxs-lookup"><span data-stu-id="72aeb-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="72aeb-166">Per altre informazioni sulla risoluzione dei problemi relativi al metodo di installazione del programma di installazione dell'app, vedere [Risolvere i problemi del programma di installazione dell'app.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="72aeb-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="72aeb-167">L'interfaccia utente durante il processo di aggiornamento non è supportata.</span><span class="sxs-lookup"><span data-stu-id="72aeb-167">UI during the update process is not supported.</span></span> <span data-ttu-id="72aeb-168">L'opzione ShowPrompt in [questa pagina e](/windows/msix/app-installer/update-settings) le opzioni correlate non sono quindi supportate.</span><span class="sxs-lookup"><span data-stu-id="72aeb-168">So the ShowPrompt option on [this page](/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="72aeb-169">App di esempio</span><span class="sxs-lookup"><span data-stu-id="72aeb-169">Sample Apps</span></span>

<span data-ttu-id="72aeb-170">Provare il Programma di installazione app con una delle app di esempio disponibili.</span><span class="sxs-lookup"><span data-stu-id="72aeb-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="72aeb-171">App di esempio</span><span class="sxs-lookup"><span data-stu-id="72aeb-171">Sample apps</span></span>](/windows/mixed-reality/develop/features-and-samples)
