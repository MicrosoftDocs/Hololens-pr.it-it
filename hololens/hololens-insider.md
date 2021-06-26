---
title: Insider Preview per Microsoft HoloLens
description: Informazioni su come iniziare a usare le build Insider e fornire feedback preziosi per il prossimo aggiornamento principale del sistema operativo per HoloLens.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924367"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="62cbc-103">Insider Preview per Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="62cbc-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="62cbc-104">Benvenuti nelle build insider preview più recenti per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="62cbc-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="62cbc-105">È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="62cbc-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="62cbc-106">partecipante al Programma Windows Insider sulla versione</span><span class="sxs-lookup"><span data-stu-id="62cbc-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="62cbc-107">Siamo molto contenti di iniziare a eseguire nuovamente il volo di nuove funzionalità per Windows Insiders.</span><span class="sxs-lookup"><span data-stu-id="62cbc-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="62cbc-108">Le nuove build verranno aggiornate ai canali Dev e Beta per gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="62cbc-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="62cbc-109">Questa pagina continuerà ad essere aggiornata quando si aggiungono altre funzionalità e aggiornamenti alle partecipante al Programma Windows Insider build.</span><span class="sxs-lookup"><span data-stu-id="62cbc-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="62cbc-110">Prepararsi a combinare questi aggiornamenti nella realtà.</span><span class="sxs-lookup"><span data-stu-id="62cbc-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="62cbc-111">Modifiche di CSP in HoloLens</span><span class="sxs-lookup"><span data-stu-id="62cbc-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="62cbc-112">Introduzione alla partecipante al Programma Windows Insider build 20348.1403</span><span class="sxs-lookup"><span data-stu-id="62cbc-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="62cbc-113">DevDetail</span><span class="sxs-lookup"><span data-stu-id="62cbc-113">DevDetail CSP</span></span>

<span data-ttu-id="62cbc-114">DevDetail CSP ora segnala anche lo spazio di archiviazione disponibile nel dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="62cbc-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="62cbc-115">Dovrebbe corrispondere approssimativamente al valore visualizzato nella pagina Archiviazione dell'app impostazioni.</span><span class="sxs-lookup"><span data-stu-id="62cbc-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="62cbc-116">Di seguito è riportato il nodo specifico contenente queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="62cbc-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="62cbc-117">./DevDetail/Ext/Microsoft/FreeStorage (solo operazione GET)</span><span class="sxs-lookup"><span data-stu-id="62cbc-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="62cbc-118">DeviceStatus</span><span class="sxs-lookup"><span data-stu-id="62cbc-118">DeviceStatus CSP</span></span>

<span data-ttu-id="62cbc-119">DeviceStatus CSP ora segnala anche SSID e BSSID della rete Wi-Fi con cui HoloLens è attivamente connesso.</span><span class="sxs-lookup"><span data-stu-id="62cbc-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="62cbc-120">Di seguito sono riportati i nodi specifici contenenti queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="62cbc-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="62cbc-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address of Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="62cbc-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="62cbc-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="62cbc-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="62cbc-123">BLOB syncml di esempio (per i fornitori MDM) per eseguire query per NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="62cbc-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="62cbc-124">Correzioni e miglioramenti:</span><span class="sxs-lookup"><span data-stu-id="62cbc-124">Fixes and improvements:</span></span>

- <span data-ttu-id="62cbc-125">È stato risolto un problema noto per Portale di dispositivi il download dei file bloccati non era [richiesto.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="62cbc-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="62cbc-126">È stato risolto un problema noto per Portale di dispositivi timeout di caricamento e [download di file.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="62cbc-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="62cbc-127">Iniziare a ricevere build Insider</span><span class="sxs-lookup"><span data-stu-id="62cbc-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="62cbc-128">Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.</span><span class="sxs-lookup"><span data-stu-id="62cbc-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="62cbc-129">Il comando vocale "Riavvia il dispositivo" funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="62cbc-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="62cbc-130">È anche possibile scegliere il pulsante di riavvio in Impostazioni/Programma Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="62cbc-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="62cbc-131">Si è verificato un bug nel back-end che potrebbe essere stato rilevato e ciò consente di tornare in funzione.</span><span class="sxs-lookup"><span data-stu-id="62cbc-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="62cbc-132">In un dispositivo HoloLens 2 passare a **Impostazioni** Aggiornamento &  >  **sicurezza**  >  **Programma Windows Insider** e selezionare **Introduzione.**</span><span class="sxs-lookup"><span data-stu-id="62cbc-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="62cbc-133">Collegare l'account usato per la registrazione come partecipante al Programma Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="62cbc-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="62cbc-134">Windows Insider sta ora passando ai canali.</span><span class="sxs-lookup"><span data-stu-id="62cbc-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="62cbc-135">L'anello veloce diventerà dev  **channel,** l'anello  lento diventerà l'Canale beta e l'anello di anteprima della versione diventerà il canale di anteprima della **versione.**  </span><span class="sxs-lookup"><span data-stu-id="62cbc-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="62cbc-136">Ecco l'aspetto del mapping: spiegazione partecipante al Programma Windows Insider canali per altre informazioni, vedere ![ ](images/WindowsInsiderChannels.png) [Introducing partecipante al Programma Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introduzione partecipante al Programma Windows Insider canali nei blog di Windows).</span><span class="sxs-lookup"><span data-stu-id="62cbc-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="62cbc-137">Selezionare quindi **Sviluppo attivo di Windows,** scegliere se si  desidera ricevere dev **channel** o build Canale beta ed esaminare le condizioni del programma.</span><span class="sxs-lookup"><span data-stu-id="62cbc-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="62cbc-138">Selezionare **Conferma > riavvia ora** per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="62cbc-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="62cbc-139">Dopo il riavvio del dispositivo, passare a Impostazioni **> aggiornamento & sicurezza > verificare** la disponibilità di aggiornamenti per ottenere la build più recente.</span><span class="sxs-lookup"><span data-stu-id="62cbc-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="62cbc-140">Risolvere i 0x80070490 errore di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="62cbc-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="62cbc-141">Se si verifica un errore di aggiornamento 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema a breve termine seguente.</span><span class="sxs-lookup"><span data-stu-id="62cbc-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="62cbc-142">Comporta lo spostamento del canale Insider, la raccolta dell'aggiornamento e quindi il ritorno del canale Insider.</span><span class="sxs-lookup"><span data-stu-id="62cbc-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="62cbc-143">Fase 1 - Versione di anteprima</span><span class="sxs-lookup"><span data-stu-id="62cbc-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="62cbc-144">Impostazioni, Aggiorna & Sicurezza, Programma Windows Insider, selezionare **Canale di anteprima versione**.</span><span class="sxs-lookup"><span data-stu-id="62cbc-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="62cbc-145">Impostazioni, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="62cbc-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="62cbc-146">Dopo l'aggiornamento, passare alla fase 2.</span><span class="sxs-lookup"><span data-stu-id="62cbc-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="62cbc-147">Fase 2 - Dev Channel</span><span class="sxs-lookup"><span data-stu-id="62cbc-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="62cbc-148">Impostazioni, Aggiorna & Sicurezza, Programma Windows Insider, selezionare **Dev Channel**.</span><span class="sxs-lookup"><span data-stu-id="62cbc-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="62cbc-149">Impostazioni, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="62cbc-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="62cbc-150">Istruzioni flash e download FFU</span><span class="sxs-lookup"><span data-stu-id="62cbc-150">FFU download and flash directions</span></span>
<span data-ttu-id="62cbc-151">Per testare con un volo firmato ffu, è prima necessario sbloccare il dispositivo prima di lampeggiare il volo firmato ffu.</span><span class="sxs-lookup"><span data-stu-id="62cbc-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="62cbc-152">Nel PC:</span><span class="sxs-lookup"><span data-stu-id="62cbc-152">On PC:</span></span>
    1. <span data-ttu-id="62cbc-153">Scaricare ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="62cbc-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="62cbc-154">Installare ARC (Advanced Recovery Companion) dal Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="62cbc-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="62cbc-155">In HoloLens - Flight Unlock: **aprire** l'aggiornamento delle impostazioni & sicurezza Programma Windows Insider quindi iscriversi  >    >   e riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62cbc-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="62cbc-156">Flash FFU: ora è possibile eseguire il flash del volo firmato FFU usando ARC.</span><span class="sxs-lookup"><span data-stu-id="62cbc-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="62cbc-157">Inviare commenti e suggerimenti e segnalare i problemi</span><span class="sxs-lookup"><span data-stu-id="62cbc-157">Provide feedback and report issues</span></span>
<span data-ttu-id="62cbc-158">Usare [l'app Hub di Feedback app](hololens-feedback.md) in HoloLens per inviare commenti e suggerimenti e segnalare i problemi.</span><span class="sxs-lookup"><span data-stu-id="62cbc-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="62cbc-159">L Hub di Feedback garantisce che siano incluse tutte le informazioni di diagnostica necessarie per consentire ai tecnici di eseguire rapidamente il debug e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="62cbc-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="62cbc-160">I problemi relativi alla versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="62cbc-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="62cbc-161">Assicurarsi di accettare il prompt che chiede se si desidera Hub di Feedback accedere alla cartella Documenti (selezionare **Sì** quando richiesto).</span><span class="sxs-lookup"><span data-stu-id="62cbc-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="62cbc-162">Nota per gli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="62cbc-162">Note for developers</span></span>
<span data-ttu-id="62cbc-163">Si è invitati a provare a sviluppare applicazioni usando build Insider di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="62cbc-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="62cbc-164">Per iniziare, vedere la documentazione per sviluppatori di [HoloLens.](https://developer.microsoft.com/windows/mixed-reality/development)</span><span class="sxs-lookup"><span data-stu-id="62cbc-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="62cbc-165">Queste stesse istruzioni funzionano con le build Insider di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="62cbc-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="62cbc-166">È possibile usare le stesse build di Unity e Visual Studio già in uso per lo sviluppo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="62cbc-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="62cbc-167">Interrompere la ricezione di build Insider</span><span class="sxs-lookup"><span data-stu-id="62cbc-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="62cbc-168">Se non si vogliono più ricevere build Insider di Windows Holographic, è possibile rifiutare esplicitamente [](hololens-recovery.md) quando HoloLens esegue una build di produzione oppure è possibile ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo in una versione non Insider di Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="62cbc-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="62cbc-169">Esiste un problema noto in cui gli utenti che annullano la registrazione dalle build insider preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu.</span><span class="sxs-lookup"><span data-stu-id="62cbc-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="62cbc-170">Successivamente, devono ripristinare manualmente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62cbc-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="62cbc-171">Per informazioni dettagliate complete su se si sarebbe stati o meno influenzati, vedere altre informazioni su [questo problema noto.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="62cbc-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="62cbc-172">Per verificare che HoloLens sia in esecuzione una build di produzione:</span><span class="sxs-lookup"><span data-stu-id="62cbc-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="62cbc-173">Passare a **Impostazioni > sistema > Informazioni su** e trovare il numero di build.</span><span class="sxs-lookup"><span data-stu-id="62cbc-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="62cbc-174">[Vedere le note sulla versione per i numeri di build di produzione](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="62cbc-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="62cbc-175">Per rifiutare esplicitamente le build Insider:</span><span class="sxs-lookup"><span data-stu-id="62cbc-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="62cbc-176">In un'istanza di HoloLens che esegue una build di produzione passare a Impostazioni **> Aggiorna**& sicurezza > Programma Windows Insider e selezionare Arresta **compilazioni Insider**.</span><span class="sxs-lookup"><span data-stu-id="62cbc-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="62cbc-177">Seguire le istruzioni per rifiutare esplicitamente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62cbc-177">Follow the instructions to opt out your device.</span></span>
