---
title: Insider Preview per Microsoft HoloLens
description: È semplice iniziare con le build Insider e dare un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162950"
---
# <span data-ttu-id="b6049-103">Insider Preview per Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="b6049-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="b6049-104">Benvenuti alle build di insider Preview più recenti per HoloLens!</span><span class="sxs-lookup"><span data-stu-id="b6049-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="b6049-105">È facile [iniziare e dare](hololens-insider.md#start-receiving-insider-builds) un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b6049-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="b6049-106">Note sulla versione di Windows Insider</span><span class="sxs-lookup"><span data-stu-id="b6049-106">Windows Insider Release Notes</span></span>

### <span data-ttu-id="b6049-107">Installare app in HoloLens 2 tramite il programma di installazione di app</span><span class="sxs-lookup"><span data-stu-id="b6049-107">Install Apps on HoloLens 2 via App Installer</span></span>
<span data-ttu-id="b6049-108">Spediremo la funzionalità di installazione dell'app subito dopo l'aggiornamento di Windows olografico, versione 20H2.</span><span class="sxs-lookup"><span data-stu-id="b6049-108">We will ship the app installer capability soon after our Windows Holographic, version 20H2 update.</span></span> <span data-ttu-id="b6049-109">Aggiungiamo **una nuova funzionalità (Installer delle app) per consentire l'installazione delle applicazioni in modo più trasparente** nei dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b6049-109">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="b6049-110">La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti**.</span><span class="sxs-lookup"><span data-stu-id="b6049-110">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="b6049-111">Per evitare interruzioni alle aziende, il programma di installazione **delle app non sarà disponibile per i dispositivi gestiti** in questo momento.</span><span class="sxs-lookup"><span data-stu-id="b6049-111">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="b6049-112">Un dispositivo viene considerato "gestito **" Se una delle opzioni** seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="b6049-112">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="b6049-113">MDM [registrato](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="b6049-113">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="b6049-114">Configurato con il [pacchetto di provisioning](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="b6049-114">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="b6049-115">L' [identità](hololens-identity.md) dell'utente è AAD</span><span class="sxs-lookup"><span data-stu-id="b6049-115">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="b6049-116">Ora è possibile installare le app senza dover abilitare la modalità sviluppatore o usando Device Portal.</span><span class="sxs-lookup"><span data-stu-id="b6049-116">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="b6049-117">È sufficiente scaricare (tramite USB o Edge) il bundle appx nel dispositivo e passare al bundle appx in Esplora file per richiedere di avviare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="b6049-117">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="b6049-118">In alternativa, [avviare un'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="b6049-118">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="b6049-119">Proprio come le app installate da Microsoft Store o trasferire localmente usando la funzionalità di distribuzione dell'app LOB di MDM, le app devono essere firmate digitalmente con lo [strumento Sign](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e il [certificato usato per firmare deve essere considerato attendibile](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) dal dispositivo HoloLens prima che l'app possa essere distribuita.</span><span class="sxs-lookup"><span data-stu-id="b6049-119">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

**<span data-ttu-id="b6049-120">Istruzioni per l'installazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b6049-120">Application install instructions.</span></span>**

1.  <span data-ttu-id="b6049-121">Verificare che il dispositivo non sia considerato gestito</span><span class="sxs-lookup"><span data-stu-id="b6049-121">Ensure that your device is not considered managed</span></span>
1.  <span data-ttu-id="b6049-122">Verificare che il dispositivo HoloLens 2 sia acceso e connesso al PC</span><span class="sxs-lookup"><span data-stu-id="b6049-122">Ensure that your HoloLens 2 device is powered on and connected to your PC</span></span>
1.  <span data-ttu-id="b6049-123">Verificare di avere effettuato l'accesso al dispositivo HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b6049-123">Ensure that you are signed into the HoloLens 2 device</span></span>
1.  <span data-ttu-id="b6049-124">Nel PC passare all'app personalizzata e copiare YourApp. appxbundle in yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="b6049-124">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>   <span data-ttu-id="b6049-125">Dopo aver completato la copia del file, è possibile disconnettere il dispositivo</span><span class="sxs-lookup"><span data-stu-id="b6049-125">After you’ve finished copying your file you can disconnect your device</span></span>
1.  <span data-ttu-id="b6049-126">Dal dispositivo HoloLens 2 aprire il menu Start, selezionare tutte le app e avviare l'app Esplora file.</span><span class="sxs-lookup"><span data-stu-id="b6049-126">From your HoloLens 2 device Open the Start Menu, select All apps and launch the File Explorer app.</span></span>
1.  <span data-ttu-id="b6049-127">Passare alla cartella Downloads.</span><span class="sxs-lookup"><span data-stu-id="b6049-127">Navigate to the Downloads folder.</span></span> <span data-ttu-id="b6049-128">Potrebbe essere necessario nel pannello sinistro dell'app selezionare prima questo dispositivo, quindi passare a download.</span><span class="sxs-lookup"><span data-stu-id="b6049-128">You may need to on the left panel of the app select This device first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="b6049-129">Selezionare il file YourApp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="b6049-129">Select the yourapp.appxbundle file.</span></span>
1.  <span data-ttu-id="b6049-130">Verrà avviato il programma di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="b6049-130">The App Installer will launch.</span></span> <span data-ttu-id="b6049-131">Selezionare il pulsante Installa per installare la tua app.</span><span class="sxs-lookup"><span data-stu-id="b6049-131">Select the Install button to install your app.</span></span>
<span data-ttu-id="b6049-132">L'app installata verrà avviata automaticamente al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="b6049-132">The installed app will automatically launch upon completion of installation.</span></span>

<span data-ttu-id="b6049-133">Puoi trovare app di esempio in [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) per testare questo flusso.</span><span class="sxs-lookup"><span data-stu-id="b6049-133">You can find sample apps on [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) to test this flow.</span></span>

<span data-ttu-id="b6049-134">Leggere il processo completo di [installazione delle app in HoloLens 2 con il programma di installazione dell'app](app-deploy-app-installer.md).</span><span class="sxs-lookup"><span data-stu-id="b6049-134">Read about the full process of [installing apps on HoloLens 2 with the App Installer](app-deploy-app-installer.md).</span></span>  

![Installazione di esempi di MRTK tramite il programma di installazione dell'app](images/hololens-app-installer-picture.jpg)

## <span data-ttu-id="b6049-136">Iniziare a ricevere compilazioni Insider</span><span class="sxs-lookup"><span data-stu-id="b6049-136">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="b6049-137">Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.</span><span class="sxs-lookup"><span data-stu-id="b6049-137">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="b6049-138">Il comando vocale "dispositivo di riavvio" funziona bene.</span><span class="sxs-lookup"><span data-stu-id="b6049-138">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="b6049-139">È anche possibile scegliere il pulsante Riavvia in Impostazioni/programma Insider di Windows.</span><span class="sxs-lookup"><span data-stu-id="b6049-139">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="b6049-140">Abbiamo avuto un bug sul back-end che potresti aver incontrato e questo ti riporterà in carreggiata.</span><span class="sxs-lookup"><span data-stu-id="b6049-140">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="b6049-141">In un dispositivo HoloLens 2 passa a **Impostazioni**di  >  **aggiornamento &**  >  **programma sicurezza Windows Insider** e selezionare per **iniziare**.</span><span class="sxs-lookup"><span data-stu-id="b6049-141">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="b6049-142">Collegare l'account usato per la registrazione come Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="b6049-142">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="b6049-143">Windows Insider ora sta passando ai canali.</span><span class="sxs-lookup"><span data-stu-id="b6049-143">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="b6049-144">L'anello **veloce** diventerà il canale **dev**, l'anello **lento** diventerà il **canale Beta**e l' **anteprima del rilascio** diventerà il canale di **anteprima del rilascio**.</span><span class="sxs-lookup"><span data-stu-id="b6049-144">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="b6049-145">Ecco come si presenta il mapping:</span><span class="sxs-lookup"><span data-stu-id="b6049-145">Here is what that mapping looks like:</span></span>

![Spiegazione di Windows Insider Channels](images/WindowsInsiderChannels.png)

<span data-ttu-id="b6049-147">Per altre informazioni, vedere [Introduzione ai canali Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nei Blog di Windows.</span><span class="sxs-lookup"><span data-stu-id="b6049-147">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="b6049-148">Selezionare quindi **lo sviluppo attivo di Windows**, scegliere se si vuole ricevere le build del canale **dev** o del canale **beta** e rivedere le condizioni del programma.</span><span class="sxs-lookup"><span data-stu-id="b6049-148">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="b6049-149">Selezionare **conferma > Riavvia ora** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="b6049-149">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="b6049-150">Dopo aver riavviato il dispositivo, accedere a **impostazioni > aggiorna & sicurezza > verificare la disponibilità di aggiornamenti** per ottenere la build più recente.</span><span class="sxs-lookup"><span data-stu-id="b6049-150">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="b6049-151">FFU download e istruzioni Flash</span><span class="sxs-lookup"><span data-stu-id="b6049-151">FFU download and flash directions</span></span>
<span data-ttu-id="b6049-152">Per eseguire il test con un FFU firmato per il volo, è necessario prima di tutto sbloccare il dispositivo prima di infiammare il volo firmato FFU.</span><span class="sxs-lookup"><span data-stu-id="b6049-152">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="b6049-153">Nel PC:</span><span class="sxs-lookup"><span data-stu-id="b6049-153">On PC:</span></span>

    1. <span data-ttu-id="b6049-154">Scaricare FFU dal PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="b6049-154">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="b6049-155">Installare ARC (Advanced Recovery Companion) da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="b6049-155">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="b6049-156">In HoloLens-Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Windows Insider Program** , quindi iscriviti, riavvia il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6049-156">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="b6049-157">Flash FFU-ora è possibile flashare il FFU firmato in anteprima con ARC.</span><span class="sxs-lookup"><span data-stu-id="b6049-157">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="b6049-158">Inviare feedback e segnalare i problemi</span><span class="sxs-lookup"><span data-stu-id="b6049-158">Provide feedback and report issues</span></span>

<span data-ttu-id="b6049-159">Usare [l'app hub di feedback](hololens-feedback.md) in HoloLens per inviare commenti e segnalazioni.</span><span class="sxs-lookup"><span data-stu-id="b6049-159">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="b6049-160">L'uso di hub di feedback assicura che vengano incluse tutte le informazioni di diagnostica necessarie per aiutare i nostri ingegneri a eseguire rapidamente il debug e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="b6049-160">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="b6049-161">I problemi con la versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="b6049-161">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="b6049-162">Assicurarsi di accettare il messaggio che chiede se si vuole che l'hub di feedback acceda alla cartella documenti (selezionare **Sì** quando richiesto).</span><span class="sxs-lookup"><span data-stu-id="b6049-162">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="b6049-163">Nota per gli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="b6049-163">Note for developers</span></span>

<span data-ttu-id="b6049-164">Sei il benvenuto e ti consigliamo di provare a sviluppare le tue applicazioni usando le build Insider di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b6049-164">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="b6049-165">Per iniziare, vedere la [documentazione di HoloLens per sviluppatori](https://developer.microsoft.com/windows/mixed-reality/development) .</span><span class="sxs-lookup"><span data-stu-id="b6049-165">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="b6049-166">Le stesse istruzioni funzionano con le build Insider di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b6049-166">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="b6049-167">Puoi usare le stesse build di Unity e Visual Studio che stai già usando per lo sviluppo di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b6049-167">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="b6049-168">Interrompere la ricezione delle build Insider</span><span class="sxs-lookup"><span data-stu-id="b6049-168">Stop receiving Insider builds</span></span>

<span data-ttu-id="b6049-169">Se non si vuole più ricevere Build Insider di Windows olografico, è possibile rifiutare la disattivazione quando HoloLens è in esecuzione una build di produzione oppure è possibile [recuperare il dispositivo](hololens-recovery.md) usando il compagno di ripristino avanzato per recuperare il dispositivo in una versione non Insider di Windows olografico.</span><span class="sxs-lookup"><span data-stu-id="b6049-169">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="b6049-170">Esiste un problema noto in cui gli utenti che non si iscrivono da insider Preview Builds dopo la reinstallazione manuale di una nuova versione di anteprima acquisiranno una schermata blu.</span><span class="sxs-lookup"><span data-stu-id="b6049-170">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="b6049-171">In seguito dovrà recuperare manualmente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6049-171">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="b6049-172">Per informazioni dettagliate su se si è interessati o meno, vedere altre informazioni su questo [problema noto](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span><span class="sxs-lookup"><span data-stu-id="b6049-172">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="b6049-173">Per verificare che HoloLens esegua una build di produzione:</span><span class="sxs-lookup"><span data-stu-id="b6049-173">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="b6049-174">Accedere a **impostazioni > sistema > informazioni**e trovare il numero di Build.</span><span class="sxs-lookup"><span data-stu-id="b6049-174">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="b6049-175">[Vedere le note sulla versione per i numeri di build della produzione](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="b6049-175">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="b6049-176">Per rifiutare le build Insider:</span><span class="sxs-lookup"><span data-stu-id="b6049-176">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="b6049-177">In un HoloLens in cui è in corso una build di produzione, passare a **impostazioni > aggiornare & sicurezza > programma Windows Insider**e selezionare **Interrompi Build Insider**.</span><span class="sxs-lookup"><span data-stu-id="b6049-177">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="b6049-178">Seguire le istruzioni per rifiutare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6049-178">Follow the instructions to opt out your device.</span></span>
