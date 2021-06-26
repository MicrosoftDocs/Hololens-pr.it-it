---
title: HoloLens 2 di implementazione e risoluzione dei problemi dei dispositivi gestiti
description: Risoluzione HoloLens 2 dei dispositivi in un ambiente Enterprise
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: Risoluzione dei problemi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961639"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="9df34-104">Risoluzione dei problemi di implementazione e dispositivi gestiti</span><span class="sxs-lookup"><span data-stu-id="9df34-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="9df34-105">Questo articolo descrive come risolvere diversi problemi o rispondere a domande relative all'implementazione e alla gestione dei HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9df34-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="9df34-106">Prima di avviare qualsiasi procedura di risoluzione dei problemi, assicurarsi che il dispositivo venga addebitato al **20-40%** della capacità della batteria, se possibile.</span><span class="sxs-lookup"><span data-stu-id="9df34-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="9df34-107">Le [luci dell'indicatore della](hololens2-setup.md#lights-that-indicate-the-battery-level) batteria che si trovano sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9df34-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="9df34-108">Risoluzione dei problemi EAP</span><span class="sxs-lookup"><span data-stu-id="9df34-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="9df34-109">Risoluzione dei problemi wi-fi</span><span class="sxs-lookup"><span data-stu-id="9df34-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="9df34-110">Risoluzione dei problemi di rete</span><span class="sxs-lookup"><span data-stu-id="9df34-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="9df34-111">Non è possibile accedere a un dispositivo HoloLens precedentemente</span><span class="sxs-lookup"><span data-stu-id="9df34-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="9df34-112">Non è possibile accedere dopo l'aggiornamento a Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="9df34-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="9df34-113">Risoluzione dei problemi di Autopilot</span><span class="sxs-lookup"><span data-stu-id="9df34-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="9df34-114">Domande frequenti sui dispositivi HoloLens gestiti</span><span class="sxs-lookup"><span data-stu-id="9df34-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="9df34-115">Risoluzione dei problemi EAP</span><span class="sxs-lookup"><span data-stu-id="9df34-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="9df34-116">Verificare che Wi-Fi profilo abbia le impostazioni giuste:</span><span class="sxs-lookup"><span data-stu-id="9df34-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="9df34-117">Il tipo EAP è configurato correttamente, tipi EAP comuni: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="9df34-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="9df34-118">Wi-Fi il nome SSID è giusto e corrisponde alla stringa HEX.</span><span class="sxs-lookup"><span data-stu-id="9df34-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="9df34-119">Per EAP-TLS, TrustedRootCA contiene l'hash SHA-1 del certificato della CA radice attendibile del server.</span><span class="sxs-lookup"><span data-stu-id="9df34-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="9df34-120">Nel comando "certutil.exe -dump cert_file_name" del PC Windows verrà mostrata la stringa hash SHA-1 di un certificato.</span><span class="sxs-lookup"><span data-stu-id="9df34-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="9df34-121">Raccogliere l'acquisizione di pacchetti di rete nei log del punto di accesso o del controller o del server AAA per individuare il punto di errore della sessione EAP.</span><span class="sxs-lookup"><span data-stu-id="9df34-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="9df34-122">Se l'identità EAP fornita da HoloLens non è prevista, verificare se il provisioning dell'identità è stato eseguito correttamente tramite un profilo Wi-Fi o un certificato client.</span><span class="sxs-lookup"><span data-stu-id="9df34-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="9df34-123">Se il server rifiuta il certificato client HoloLens, verificare se è stato effettuato il provisioning del certificato client richiesto nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9df34-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="9df34-124">Se HoloLens rifiuta il certificato del server, verificare se è stato effettuato il provisioning del certificato della CA radice del server in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9df34-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="9df34-125">Se il provisioning del profilo aziendale viene eseguito Wi-Fi pacchetto di provisioning, è consigliabile applicare il pacchetto di provisioning in un PC Windows 10 locale.</span><span class="sxs-lookup"><span data-stu-id="9df34-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="9df34-126">Se si verifica un errore anche Windows 10 PC, seguire la guida alla risoluzione dei problemi di autenticazione 802.1X del client Windows.</span><span class="sxs-lookup"><span data-stu-id="9df34-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="9df34-127">Inviare commenti e suggerimenti tramite Hub di Feedback.</span><span class="sxs-lookup"><span data-stu-id="9df34-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="9df34-128">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="9df34-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="9df34-129">Wi-Fi risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9df34-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="9df34-130">Ecco alcuni aspetti da provare se non è possibile connettere HoloLens a una rete Wi-Fi rete:</span><span class="sxs-lookup"><span data-stu-id="9df34-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="9df34-131">Assicurarsi che la Wi-Fi sia attivata.</span><span class="sxs-lookup"><span data-stu-id="9df34-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="9df34-132">Per controllare, usare il movimento Avvia e quindi selezionare Impostazioni > rete & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="9df34-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="9df34-133">Se Wi-Fi è attivata, provare a disattivarla e quindi attivarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="9df34-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="9df34-134">Passare più vicino al router o al punto di accesso.</span><span class="sxs-lookup"><span data-stu-id="9df34-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="9df34-135">Riavviare il router Wi-Fi, quindi riavviare HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9df34-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="9df34-136">Provare a eseguire di nuovo la connessione.</span><span class="sxs-lookup"><span data-stu-id="9df34-136">Try connecting again.</span></span>
4. <span data-ttu-id="9df34-137">Se nessuna di queste operazioni funziona, verificare che il router utilizzi il firmware più recente.</span><span class="sxs-lookup"><span data-stu-id="9df34-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="9df34-138">Queste informazioni sono disponibili nel sito Web del produttore.</span><span class="sxs-lookup"><span data-stu-id="9df34-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="9df34-139">Quando si accede a un account aziendale o aziendale nel dispositivo, può anche applicare i criteri di gestione dei dispositivi mobili (MDM), se i criteri sono configurati dall'amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="9df34-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="9df34-140">Risoluzione dei problemi di rete</span><span class="sxs-lookup"><span data-stu-id="9df34-140">Network Troubleshooting</span></span>
<span data-ttu-id="9df34-141">Se i problemi di rete sono un ostacolo per la corretta distribuzione e l'uso di HoloLens 2 nell'organizzazione, vedere come due noti strumenti di diagnostica di rete, Fiddler e Wireshark, consentono di analizzare, diagnosticare e identificare i problemi.</span><span class="sxs-lookup"><span data-stu-id="9df34-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="9df34-142">Per altri [dettagli, vedere](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) questo blog.</span><span class="sxs-lookup"><span data-stu-id="9df34-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="9df34-143">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="9df34-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="9df34-144">Non è possibile accedere a un dispositivo HoloLens precedentemente</span><span class="sxs-lookup"><span data-stu-id="9df34-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="9df34-145">Se il dispositivo è stato configurato in precedenza per un altro utente, per un client o per un ex dipendente [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) e non si ha la password per sbloccare il dispositivo, è possibile usare Intune per cancellare in remoto il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9df34-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="9df34-146">Il dispositivo viene quindi nuovamente lampeggiato.</span><span class="sxs-lookup"><span data-stu-id="9df34-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="9df34-147">Quando si cancella il dispositivo, assicurarsi di lasciare deselezionato Mantieni lo stato **di registrazione e l'account** utente.</span><span class="sxs-lookup"><span data-stu-id="9df34-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="9df34-148">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="9df34-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="9df34-149">Non è possibile accedere dopo l'aggiornamento a Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="9df34-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="9df34-150">Sintomi</span><span class="sxs-lookup"><span data-stu-id="9df34-150">Symptoms</span></span>
- <span data-ttu-id="9df34-151">L'uso del PIN per l'accesso avrà esito negativo dopo l'immissione del PIN corretto.</span><span class="sxs-lookup"><span data-stu-id="9df34-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="9df34-152">L'uso del metodo di accesso Web avrà esito negativo dopo l'accesso nella pagina Web.</span><span class="sxs-lookup"><span data-stu-id="9df34-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="9df34-153">Il dispositivo non è elencato come "Azure AD aggiunto" [in](https://portal.azure.com/) portale di Azure -> Azure Active Directory -> Dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9df34-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="9df34-154">Causa</span><span class="sxs-lookup"><span data-stu-id="9df34-154">Cause</span></span>
<span data-ttu-id="9df34-155">È possibile che il dispositivo in oggetto sia stato eliminato dal tenant Azure AD destinazione.</span><span class="sxs-lookup"><span data-stu-id="9df34-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="9df34-156">Ad esempio, questa operazione può verificarsi per i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9df34-156">For example, this may happen because:</span></span>

- <span data-ttu-id="9df34-157">Un amministratore o un utente ha eliminato il dispositivo nel portale di Azure o usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9df34-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="9df34-158">Il dispositivo è stato rimosso dal tenant Azure AD a causa dell'inattività.</span><span class="sxs-lookup"><span data-stu-id="9df34-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="9df34-159">Per un ambiente gestito in modo efficiente, è in genere consigliabile che gli amministratori IT rimuovono i dispositivi [inattivi](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)non più Azure AD tenant .</span><span class="sxs-lookup"><span data-stu-id="9df34-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="9df34-160">Quando un dispositivo inciso tenta di contattare nuovamente il tenant Azure AD dopo l'eliminazione, non riuscirà a eseguire l'autenticazione con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9df34-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="9df34-161">Questo effetto è spesso invisibile all'utente del dispositivo, perché l'accesso memorizzato nella cache tramite PIN continuerà a consentire all'utente di accedere.</span><span class="sxs-lookup"><span data-stu-id="9df34-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="9df34-162">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="9df34-162">Mitigation</span></span>
<span data-ttu-id="9df34-163">Attualmente non è possibile aggiungere un dispositivo HoloLens eliminato in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9df34-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="9df34-164">I dispositivi interessati dovranno essere puliti seguendo le istruzioni per [il reflashing del dispositivo.](hololens-recovery.md#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="9df34-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="9df34-165">Risoluzione dei problemi di Autopilot</span><span class="sxs-lookup"><span data-stu-id="9df34-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="9df34-166">Gli articoli seguenti possono essere una risorsa utile per ottenere altre informazioni e risolvere i problemi di Autopilot, tuttavia tenere presente che questi articoli sono basati su Windows 10 Desktop e che non tutte le informazioni possono essere valide per HoloLens:</span><span class="sxs-lookup"><span data-stu-id="9df34-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="9df34-167">Windows Autopilot problemi noti</span><span class="sxs-lookup"><span data-stu-id="9df34-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="9df34-168">Risolvere i problemi di registrazione dei dispositivi Windows in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9df34-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="9df34-169">Windows Autopilot - Conflitti di criteri</span><span class="sxs-lookup"><span data-stu-id="9df34-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="9df34-170">Domande frequenti sui dispositivi HoloLens gestiti</span><span class="sxs-lookup"><span data-stu-id="9df34-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="9df34-171">È possibile usare System Center Gestione configurazione (SCCM) per gestire i dispositivi HoloLens?</span><span class="sxs-lookup"><span data-stu-id="9df34-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="9df34-172">No.</span><span class="sxs-lookup"><span data-stu-id="9df34-172">No.</span></span> <span data-ttu-id="9df34-173">È necessario usare un sistema MDM per gestire i dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9df34-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="9df34-174">È possibile usare Active Directory Domain Services (Ad DS) per gestire gli account utente di HoloLens?</span><span class="sxs-lookup"><span data-stu-id="9df34-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="9df34-175">No.</span><span class="sxs-lookup"><span data-stu-id="9df34-175">No.</span></span> <span data-ttu-id="9df34-176">È necessario usare Azure Active Directory (Azure AD) per gestire gli account utente per i dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9df34-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="9df34-177">HoloLens è in grado di eseguire la registrazione automatica di Automated Data Capture Systems (ADCS) ?</span><span class="sxs-lookup"><span data-stu-id="9df34-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="9df34-178">No.</span><span class="sxs-lookup"><span data-stu-id="9df34-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="9df34-179">HoloLens può partecipare a autenticazione integrata di Windows?</span><span class="sxs-lookup"><span data-stu-id="9df34-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="9df34-180">No.</span><span class="sxs-lookup"><span data-stu-id="9df34-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="9df34-181">HoloLens supporta la personalizzazione?</span><span class="sxs-lookup"><span data-stu-id="9df34-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="9df34-182">No.</span><span class="sxs-lookup"><span data-stu-id="9df34-182">No.</span></span> <span data-ttu-id="9df34-183">Tuttavia, è possibile risolvere questo problema usando uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="9df34-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="9df34-184">Creare un'app personalizzata e quindi abilitare [la modalità tutto schermo](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="9df34-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="9df34-185">L'app personalizzata può essere personalizzata e può avviare altre app, ad esempio Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="9df34-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="9df34-186">Modificare tutte le immagini del profilo utente in Azure AD al logo aziendale.</span><span class="sxs-lookup"><span data-stu-id="9df34-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="9df34-187">Tuttavia, potrebbe non essere consigliabile per tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="9df34-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="9df34-188">Quali funzionalità di registrazione HoloLens 2 offerte?</span><span class="sxs-lookup"><span data-stu-id="9df34-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="9df34-189">La registrazione è limitata alle tracce che possono essere acquisite negli scenari di sviluppo o risoluzione dei problemi o ai dati di telemetria inviati dai dispositivi ai server Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9df34-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="9df34-190">Domande sulla protezione dei dispositivi HoloLens</span><span class="sxs-lookup"><span data-stu-id="9df34-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="9df34-191">Vedere [le informazioni HoloLens 2 sicurezza.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9df34-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="9df34-192">Per i dispositivi HoloLens di prima generazione, vedere [queste domande frequenti.](hololens1-faq-security.md)</span><span class="sxs-lookup"><span data-stu-id="9df34-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="9df34-193">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="9df34-193">Back to list</span></span>](#list)
