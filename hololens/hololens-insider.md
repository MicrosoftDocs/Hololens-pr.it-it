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
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636094"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="ce86a-103">Insider Preview per Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="ce86a-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="ce86a-104">Benvenuti alle build insider preview più recenti per HoloLens!</span><span class="sxs-lookup"><span data-stu-id="ce86a-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="ce86a-105">È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ce86a-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="ce86a-106">Windows Note sulla versione insider</span><span class="sxs-lookup"><span data-stu-id="ce86a-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="ce86a-107">Siamo entusiasti di iniziare a eseguire il volo di nuove funzionalità per Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="ce86a-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="ce86a-108">Le nuove build verranno aggiornate ai canali Dev e Beta per gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="ce86a-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="ce86a-109">Questa pagina continuerà ad essere aggiornata quando si aggiungono altre funzionalità e aggiornamenti alle build Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="ce86a-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="ce86a-110">Prepararsi a combinare questi aggiornamenti nella realtà.</span><span class="sxs-lookup"><span data-stu-id="ce86a-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="ce86a-111">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="ce86a-111">Feature</span></span>                 | <span data-ttu-id="ce86a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce86a-112">Description</span></span>                | <span data-ttu-id="ce86a-113">Utente o scenario</span><span class="sxs-lookup"><span data-stu-id="ce86a-113">User or Scenario</span></span> | <span data-ttu-id="ce86a-114">Build introdotta</span><span class="sxs-lookup"><span data-stu-id="ce86a-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="ce86a-115">Modifiche di CSP per la creazione di report HoloLens dettagli</span><span class="sxs-lookup"><span data-stu-id="ce86a-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="ce86a-116">Nuovi CSP per eseguire query sui dati</span><span class="sxs-lookup"><span data-stu-id="ce86a-116">New CSPs for to query data</span></span> | <span data-ttu-id="ce86a-117">Amministratori IT</span><span class="sxs-lookup"><span data-stu-id="ce86a-117">IT Admins</span></span>    | <span data-ttu-id="ce86a-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="ce86a-118">20348.1403</span></span>                 |
| [<span data-ttu-id="ce86a-119">Criteri di accesso automatico controllati da CSP</span><span class="sxs-lookup"><span data-stu-id="ce86a-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="ce86a-120">Usato per accedere automaticamente a un account</span><span class="sxs-lookup"><span data-stu-id="ce86a-120">Used to log in an account automatically</span></span> | <span data-ttu-id="ce86a-121">Amministratori IT</span><span class="sxs-lookup"><span data-stu-id="ce86a-121">IT Admins</span></span> | <span data-ttu-id="ce86a-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="ce86a-122">20348.1405</span></span> |
| [<span data-ttu-id="ce86a-123">Supporto di file PFX per Gestione certificati</span><span class="sxs-lookup"><span data-stu-id="ce86a-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="ce86a-124">Aggiungere certificati PFX tramite l'interfaccia Impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="ce86a-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="ce86a-125">Utente finale</span><span class="sxs-lookup"><span data-stu-id="ce86a-125">End User</span></span> | <span data-ttu-id="ce86a-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="ce86a-126">20348.1405</span></span> |
| [<span data-ttu-id="ce86a-127">Visualizzare il report di diagnostica avanzato in Impostazioni in HoloLens</span><span class="sxs-lookup"><span data-stu-id="ce86a-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="ce86a-128">Visualizzare i log di diagnostica MDM nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="ce86a-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="ce86a-129">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="ce86a-129">Troubleshooting</span></span> | <span data-ttu-id="ce86a-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="ce86a-130">20348.1405</span></span> |
| [<span data-ttu-id="ce86a-131">Notifiche di diagnostica offline</span><span class="sxs-lookup"><span data-stu-id="ce86a-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="ce86a-132">Commenti e suggerimenti per l'audiovisual per la raccolta di log</span><span class="sxs-lookup"><span data-stu-id="ce86a-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="ce86a-133">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="ce86a-133">Troubleshooting</span></span> | <span data-ttu-id="ce86a-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="ce86a-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="ce86a-135">Modifiche di CSP per la creazione di report HoloLens dettagli</span><span class="sxs-lookup"><span data-stu-id="ce86a-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="ce86a-136">Introduzione alla Windows Insider, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="ce86a-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="ce86a-137">I CSP seguenti sono stati aggiornati con nuovi modi per segnalare le informazioni dai HoloLens dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ce86a-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="ce86a-138">DevDetail CSP - Versione Archiviazione</span><span class="sxs-lookup"><span data-stu-id="ce86a-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="ce86a-139">DevDetail CSP ora segnala anche lo spazio di archiviazione disponibile HoloLens dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce86a-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="ce86a-140">Dovrebbe corrispondere approssimativamente al valore visualizzato nella pagina Impostazioni'app Archiviazione app.</span><span class="sxs-lookup"><span data-stu-id="ce86a-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="ce86a-141">Di seguito è riportato il nodo specifico contenente queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="ce86a-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="ce86a-142">./DevDetail/Ext/Microsoft/FreeStorage (solo operazione GET)</span><span class="sxs-lookup"><span data-stu-id="ce86a-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="ce86a-143">CSP DeviceStatus - SSID e BSSID</span><span class="sxs-lookup"><span data-stu-id="ce86a-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="ce86a-144">DeviceStatus CSP ora segnala anche SSID e BSSID Wi-Fi rete con cui HoloLens è attivamente connesso.</span><span class="sxs-lookup"><span data-stu-id="ce86a-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="ce86a-145">Di seguito sono riportati i nodi specifici contenenti queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="ce86a-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="ce86a-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address of Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="ce86a-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="ce86a-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="ce86a-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="ce86a-148">BLOB syncml di esempio (per i fornitori MDM) per eseguire query per NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="ce86a-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="ce86a-149">Criteri di accesso automatico controllati da CSP</span><span class="sxs-lookup"><span data-stu-id="ce86a-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="ce86a-150">Questo nuovo criterio AutoLogonUser controlla se un utente verrà connesso automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ce86a-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="ce86a-151">Alcuni clienti vogliono configurare dispositivi associati a un'identità ma che non vogliono alcuna esperienza di accesso.</span><span class="sxs-lookup"><span data-stu-id="ce86a-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="ce86a-152">Imagine il ritiro di un dispositivo e l'uso immediato dell'assistenza remota.</span><span class="sxs-lookup"><span data-stu-id="ce86a-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="ce86a-153">Oppure avere il vantaggio di poter distribuire rapidamente i dispositivi HoloLens e consentire agli utenti finali di velocizzare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ce86a-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="ce86a-154">Quando il criterio è impostato su un valore non vuoto, specifica l'indirizzo di posta elettronica dell'utente con accesso automatico.</span><span class="sxs-lookup"><span data-stu-id="ce86a-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="ce86a-155">L'utente specificato deve accedere al dispositivo almeno una volta per abilitare l'accesso automatico.</span><span class="sxs-lookup"><span data-stu-id="ce86a-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="ce86a-156">URI OMA del nuovo valore string `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` dei criteri</span><span class="sxs-lookup"><span data-stu-id="ce86a-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="ce86a-157">L'utente con lo stesso indirizzo di posta elettronica avrà l'accesso automatico abilitato.</span><span class="sxs-lookup"><span data-stu-id="ce86a-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="ce86a-158">In un dispositivo in cui è configurato questo criterio, l'utente specificato nel criterio dovrà accedere almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="ce86a-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="ce86a-159">I successivi riavvii del dispositivo dopo il primo accesso avranno l'utente specificato connesso automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ce86a-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="ce86a-160">È supportato un solo utente di accesso automatico.</span><span class="sxs-lookup"><span data-stu-id="ce86a-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="ce86a-161">Una volta abilitato, l'utente connesso automaticamente non sarà in grado di disconnettersi manualmente.</span><span class="sxs-lookup"><span data-stu-id="ce86a-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="ce86a-162">Per eseguire l'accesso come utente diverso, è prima necessario che i criteri siano disabilitati.</span><span class="sxs-lookup"><span data-stu-id="ce86a-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="ce86a-163">Alcuni eventi, ad esempio gli aggiornamenti principali del sistema operativo, potrebbero richiedere all'utente specificato di accedere di nuovo al dispositivo per riprendere il comportamento di accesso automatico.</span><span class="sxs-lookup"><span data-stu-id="ce86a-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="ce86a-164">L'accesso automatico è supportato solo per gli utenti msa e AAD.</span><span class="sxs-lookup"><span data-stu-id="ce86a-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="ce86a-165">Supporto di file PFX per Gestione certificati</span><span class="sxs-lookup"><span data-stu-id="ce86a-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="ce86a-166">Introdotto in Windows Insider build 20348.1405.</span><span class="sxs-lookup"><span data-stu-id="ce86a-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="ce86a-167">È stato aggiunto il supporto a [Gestione certificati per](certificate-manager.md) l'uso dei certificati con estensione pfx.</span><span class="sxs-lookup"><span data-stu-id="ce86a-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="ce86a-168">Quando gli utenti passano **a Impostazioni** certificati di & di sicurezza e selezionare Installa un certificato l'interfaccia utente ora supporta il file di certificato con estensione  >    >  pfx. </span><span class="sxs-lookup"><span data-stu-id="ce86a-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="ce86a-169">Gli utenti possono importare il certificato con estensione pfx, con chiave privata, nell'archivio utenti o nell'archivio computer.</span><span class="sxs-lookup"><span data-stu-id="ce86a-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="ce86a-170">Visualizzare il report di diagnostica avanzato in Impostazioni in HoloLens</span><span class="sxs-lookup"><span data-stu-id="ce86a-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="ce86a-171">Per i dispositivi gestiti durante la risoluzione dei problemi, verificare che sia applicata una configurazione dei criteri prevista è un passaggio importante.</span><span class="sxs-lookup"><span data-stu-id="ce86a-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="ce86a-172">In precedenza questa nuova funzionalità doveva essere eseguita fuori dal dispositivo tramite MDM o vicino al dispositivo dopo l'esportazione dei log di diagnostica MDM raccolti tramite gli account **Impostazioni** Accesso aziendale o dell'istituto di istruzione e selezionare Esporta i log di gestione e visualizzati in un PC nelle  ->    >  vicinanze. </span><span class="sxs-lookup"><span data-stu-id="ce86a-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="ce86a-173">È ora possibile visualizzare la diagnostica MDM nel dispositivo usando il browser Edge.</span><span class="sxs-lookup"><span data-stu-id="ce86a-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="ce86a-174">Per visualizzare più facilmente il report di diagnostica MDM, passare alla pagina Accedi all'istituto di istruzione o all'istituto di istruzione e selezionare **Visualizza report di diagnostica avanzato.**</span><span class="sxs-lookup"><span data-stu-id="ce86a-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="ce86a-175">Verrà generato e aperto il report in una nuova finestra di Edge.</span><span class="sxs-lookup"><span data-stu-id="ce86a-175">This will generate and open the report in a new Edge window.</span></span>

![Visualizzare il report di diagnostica avanzato nell Impostazioni app.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="ce86a-177">Notifiche di diagnostica offline</span><span class="sxs-lookup"><span data-stu-id="ce86a-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="ce86a-178">Si tratta di un aggiornamento per una funzionalità esistente denominata [Diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics).</span><span class="sxs-lookup"><span data-stu-id="ce86a-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="ce86a-179">In precedenza, non era presente alcun indicatore chiaro per gli utenti che avevano attivato la raccolta diagnostica o che era stata completata.</span><span class="sxs-lookup"><span data-stu-id="ce86a-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="ce86a-180">A questo punto, Windows build insider, sono disponibili due forme di feedback visivo per la diagnostica offline.</span><span class="sxs-lookup"><span data-stu-id="ce86a-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="ce86a-181">Il primo è notifiche di tipo avviso popup visualizzate sia all'avvio che al completamento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="ce86a-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="ce86a-182">Verranno visualizzati quando l'utente è connesso e dispone di oggetti visivi.</span><span class="sxs-lookup"><span data-stu-id="ce86a-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Avviso popup per la raccolta di log.](./images/logcollection1.jpg)

![Avviso popup al termine della raccolta dei log.](./images/logcollection2.jpg)
 
<span data-ttu-id="ce86a-185">Poiché gli utenti usano spesso La diagnostica offline come meccanismo di raccolta dei log di fallback per quando non hanno accesso a una visualizzazione, non possono accedere o sono ancora in Configurazione guidata. Verrà inoltre riprodotto un segnale audio quando vengono raccolti i log.</span><span class="sxs-lookup"><span data-stu-id="ce86a-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="ce86a-186">Questo suono verrà riprodotto oltre alla notifica di tipo avviso popup.</span><span class="sxs-lookup"><span data-stu-id="ce86a-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="ce86a-187">Questa nuova funzionalità verrà abilitata quando il dispositivo viene aggiornato e non deve essere abilitata o gestita.</span><span class="sxs-lookup"><span data-stu-id="ce86a-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="ce86a-188">In qualsiasi caso in cui questo nuovo feedback non possa essere visualizzato o ascoltato, la diagnostica offline verrà comunque generata.</span><span class="sxs-lookup"><span data-stu-id="ce86a-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="ce86a-189">Con questa aggiunta più recente di commenti e suggerimenti per l'audio è più facile raccogliere dati di diagnostica e risolvere più rapidamente i problemi.</span><span class="sxs-lookup"><span data-stu-id="ce86a-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="ce86a-190">Correzioni e miglioramenti:</span><span class="sxs-lookup"><span data-stu-id="ce86a-190">Fixes and improvements:</span></span>

- <span data-ttu-id="ce86a-191">È stato risolto un problema noto per Portale di dispositivi il download dei file bloccati non era [richiesto.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="ce86a-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="ce86a-192">È stato risolto un problema noto per Portale di dispositivi timeout di caricamento e [download di file.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="ce86a-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="ce86a-193">Iniziare a ricevere build Insider</span><span class="sxs-lookup"><span data-stu-id="ce86a-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="ce86a-194">Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.</span><span class="sxs-lookup"><span data-stu-id="ce86a-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="ce86a-195">Il comando vocale "Riavvia il dispositivo" funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="ce86a-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="ce86a-196">È anche possibile scegliere il pulsante di riavvio in Impostazioni/Windows Programma Insider.</span><span class="sxs-lookup"><span data-stu-id="ce86a-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="ce86a-197">Si è verificato un bug nel back-end che potrebbe essere stato rilevato e ciò consente di tornare in funzione.</span><span class="sxs-lookup"><span data-stu-id="ce86a-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="ce86a-198">In un dispositivo HoloLens 2 passare **a** Impostazioni  >  **aggiornamento & sicurezza**  >  **Windows Programma Insider** selezionare **Introduzione.**</span><span class="sxs-lookup"><span data-stu-id="ce86a-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="ce86a-199">Collegare l'account usato per la registrazione come Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="ce86a-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="ce86a-200">Windows insider sta ora passando a Canali.</span><span class="sxs-lookup"><span data-stu-id="ce86a-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="ce86a-201">L'anello veloce diventerà dev  **channel,** l'anello  lento diventerà l'Canale beta e l'anello di anteprima della versione diventerà il canale di anteprima della **versione.**  </span><span class="sxs-lookup"><span data-stu-id="ce86a-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="ce86a-202">Ecco l'aspetto del mapping:</span><span class="sxs-lookup"><span data-stu-id="ce86a-202">Here is what that mapping looks like:</span></span>

![Windows Spiegazione dei canali insider](images/WindowsInsiderChannels.png)

<span data-ttu-id="ce86a-204">Per altre informazioni, vedere [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introduzione Windows Insider Channels in Windows Blog).</span><span class="sxs-lookup"><span data-stu-id="ce86a-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="ce86a-205">Selezionare quindi **Sviluppo attivo di** Windows, scegliere se si desidera  ricevere dev **channel** o build Canale beta ed esaminare le condizioni del programma.</span><span class="sxs-lookup"><span data-stu-id="ce86a-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="ce86a-206">Selezionare **Conferma > riavvia ora** per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ce86a-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="ce86a-207">Dopo il riavvio del dispositivo, passare Impostazioni > **aggiornamento & sicurezza** > verificare la disponibilità di aggiornamenti per ottenere la build più recente.</span><span class="sxs-lookup"><span data-stu-id="ce86a-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="ce86a-208">Risolvere i 0x80070490 di errore di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ce86a-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="ce86a-209">Se si verifica un errore di aggiornamento 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema a breve termine seguente.</span><span class="sxs-lookup"><span data-stu-id="ce86a-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="ce86a-210">Comporta lo spostamento del canale Insider, il ritiro dell'aggiornamento e quindi il ritorno del canale Insider.</span><span class="sxs-lookup"><span data-stu-id="ce86a-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="ce86a-211">Fase 1 - Versione di anteprima</span><span class="sxs-lookup"><span data-stu-id="ce86a-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="ce86a-212">Impostazioni, Update & Security, Windows Programma Insider, selezionare **Release Preview Channel (Canale di anteprima versione).**</span><span class="sxs-lookup"><span data-stu-id="ce86a-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="ce86a-213">Impostazioni, Update & Security, Windows Update, Check **for updates**.</span><span class="sxs-lookup"><span data-stu-id="ce86a-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="ce86a-214">Dopo l'aggiornamento, passare alla fase 2.</span><span class="sxs-lookup"><span data-stu-id="ce86a-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="ce86a-215">Fase 2 - Dev Channel</span><span class="sxs-lookup"><span data-stu-id="ce86a-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="ce86a-216">Impostazioni, Aggiornare & Security, Windows Programma Insider selezionare **Dev Channel**.</span><span class="sxs-lookup"><span data-stu-id="ce86a-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="ce86a-217">Impostazioni, Update & Security, Windows Update, Check **for updates**.</span><span class="sxs-lookup"><span data-stu-id="ce86a-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="ce86a-218">Istruzioni flash e download FFU</span><span class="sxs-lookup"><span data-stu-id="ce86a-218">FFU download and flash directions</span></span>

<span data-ttu-id="ce86a-219">Per testare con un volo firmato ffu, è prima necessario sbloccare il dispositivo prima di lampeggiare il volo firmato ffu.</span><span class="sxs-lookup"><span data-stu-id="ce86a-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="ce86a-220">Nel PC:</span><span class="sxs-lookup"><span data-stu-id="ce86a-220">On PC:</span></span>
    1. <span data-ttu-id="ce86a-221">Scaricare ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="ce86a-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="ce86a-222">Installare ARC (Advanced Recovery Companion) dal Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="ce86a-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="ce86a-223">In HoloLens - Flight Unlock: **aprire** Impostazioni  >  **Update & Security**  >  **Windows Programma Insider** quindi iscriversi e riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce86a-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="ce86a-224">Flash FFU: ora è possibile eseguire il flash del volo firmato FFU usando ARC.</span><span class="sxs-lookup"><span data-stu-id="ce86a-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="ce86a-225">Inviare commenti e suggerimenti e segnalare i problemi</span><span class="sxs-lookup"><span data-stu-id="ce86a-225">Provide feedback and report issues</span></span>

<span data-ttu-id="ce86a-226">Usare [l'app Hub di Feedback nel](hololens-feedback.md) HoloLens per inviare commenti e suggerimenti e segnalare i problemi.</span><span class="sxs-lookup"><span data-stu-id="ce86a-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="ce86a-227">L Hub di Feedback garantisce che siano incluse tutte le informazioni di diagnostica necessarie per consentire ai tecnici di eseguire rapidamente il debug e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="ce86a-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="ce86a-228">I problemi relativi alla versione cinese e giapponese HoloLens devono essere segnalati allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="ce86a-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="ce86a-229">Assicurarsi di accettare il prompt che chiede se si desidera Hub di Feedback accedere alla cartella Documenti (selezionare **Sì** quando richiesto).</span><span class="sxs-lookup"><span data-stu-id="ce86a-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="ce86a-230">Nota per gli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="ce86a-230">Note for developers</span></span>

<span data-ttu-id="ce86a-231">Si è invitati a provare a sviluppare applicazioni usando build Insider di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ce86a-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="ce86a-232">Per [iniziare, HoloLens per](https://developer.microsoft.com/windows/mixed-reality/development) sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="ce86a-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="ce86a-233">Queste stesse istruzioni funzionano con le build Insider di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ce86a-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="ce86a-234">È possibile usare le stesse build di Unity e Visual Studio già in uso per lo HoloLens sviluppo.</span><span class="sxs-lookup"><span data-stu-id="ce86a-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="ce86a-235">Interrompere la ricezione di build Insider</span><span class="sxs-lookup"><span data-stu-id="ce86a-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="ce86a-236">Se non si vogliono più ricevere build Insider di Windows Holographic, è possibile rifiutare esplicitamente quando il [](hololens-recovery.md) HoloLens esegue una build di produzione oppure è possibile ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo a una versione non Insider di Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="ce86a-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="ce86a-237">Esiste un problema noto in cui gli utenti che annullano la registrazione dalle build insider preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu.</span><span class="sxs-lookup"><span data-stu-id="ce86a-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="ce86a-238">Successivamente, devono ripristinare manualmente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce86a-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="ce86a-239">Per informazioni dettagliate complete su se si sarebbe o meno in grado di influire, vedere altre informazioni su [questo problema noto.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="ce86a-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="ce86a-240">Per verificare che il HoloLens sia in esecuzione una build di produzione:</span><span class="sxs-lookup"><span data-stu-id="ce86a-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="ce86a-241">Passare a **Impostazioni > sistema > Informazioni su** e trovare il numero di build.</span><span class="sxs-lookup"><span data-stu-id="ce86a-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="ce86a-242">[Vedere le note sulla versione per i numeri di build di produzione](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="ce86a-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="ce86a-243">Per rifiutare esplicitamente le build Insider:</span><span class="sxs-lookup"><span data-stu-id="ce86a-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="ce86a-244">In un HoloLens esecuzione di una build di produzione passare a Impostazioni > **Update & Security > Windows Programma Insider** e selezionare Stop Insider builds (Arresta **compilazioni Insider).**</span><span class="sxs-lookup"><span data-stu-id="ce86a-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="ce86a-245">Seguire le istruzioni per rifiutare esplicitamente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce86a-245">Follow the instructions to opt out your device.</span></span>
