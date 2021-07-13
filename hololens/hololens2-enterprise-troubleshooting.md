---
title: HoloLens 2 implementazione e risoluzione dei problemi dei dispositivi gestiti
description: Risoluzione dei HoloLens 2 dispositivi in un Enterprise locale
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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636878"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="5e639-104">Risoluzione dei problemi di implementazione e dispositivi gestiti</span><span class="sxs-lookup"><span data-stu-id="5e639-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="5e639-105">Questo articolo descrive come risolvere diversi problemi o rispondere a domande relative all'implementazione e alla gestione HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5e639-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="5e639-106">Prima di iniziare qualsiasi procedura di risoluzione dei problemi, assicurarsi che il dispositivo venga addebitato al **20-40%** della capacità della batteria, se possibile.</span><span class="sxs-lookup"><span data-stu-id="5e639-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="5e639-107">Le [luci indicatore della batteria](hololens2-setup.md#lights-that-indicate-the-battery-level) posizionate sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5e639-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="5e639-108">Risoluzione dei problemi EAP</span><span class="sxs-lookup"><span data-stu-id="5e639-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="5e639-109">Risoluzione dei problemi relativi al Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="5e639-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="5e639-110">Risoluzione dei problemi di rete</span><span class="sxs-lookup"><span data-stu-id="5e639-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="5e639-111">Non è possibile accedere a un dispositivo di configurazione HoloLens precedente</span><span class="sxs-lookup"><span data-stu-id="5e639-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="5e639-112">Non è possibile accedere dopo l'aggiornamento Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="5e639-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="5e639-113">Risoluzione dei problemi di Autopilot</span><span class="sxs-lookup"><span data-stu-id="5e639-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="5e639-114">Domande frequenti HoloLens dispositivi gestiti</span><span class="sxs-lookup"><span data-stu-id="5e639-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="5e639-115">Risoluzione dei problemi EAP</span><span class="sxs-lookup"><span data-stu-id="5e639-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="5e639-116">Verificare che Wi-Fi profilo abbia le impostazioni giuste:</span><span class="sxs-lookup"><span data-stu-id="5e639-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="5e639-117">Il tipo EAP è configurato correttamente, tipi EAP comuni: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="5e639-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="5e639-118">Wi-Fi nome SSID è a destra e corrisponde alla stringa HEX.</span><span class="sxs-lookup"><span data-stu-id="5e639-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="5e639-119">Per EAP-TLS, TrustedRootCA contiene l'hash SHA-1 del certificato CA radice attendibile del server.</span><span class="sxs-lookup"><span data-stu-id="5e639-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="5e639-120">Nel Windows PC "certutil.exe -dump cert_file_name" visualizza la stringa hash SHA-1 di un certificato.</span><span class="sxs-lookup"><span data-stu-id="5e639-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="5e639-121">Raccogliere l'acquisizione di pacchetti di rete nel punto di accesso, nel controller o nei log del server AAA per individuare la posizione in cui la sessione EAP ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5e639-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="5e639-122">Se l'identità EAP fornita da HoloLens non è prevista, verificare se è stato eseguito correttamente il provisioning dell'identità tramite un profilo Wi-Fi o un certificato client.</span><span class="sxs-lookup"><span data-stu-id="5e639-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="5e639-123">Se il server rifiuta HoloLens certificato client, verificare se è stato effettuato il provisioning del certificato client richiesto nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5e639-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="5e639-124">Se HoloLens rifiuta il certificato del server, verificare se è stato effettuato il provisioning del certificato CA radice del server HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5e639-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="5e639-125">Se il provisioning del profilo aziendale viene effettuato tramite Wi-Fi di provisioning, è consigliabile applicare il pacchetto di provisioning in un PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5e639-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="5e639-126">Se si verifica un errore anche Windows 10 PC, seguire la guida alla risoluzione dei Windows di autenticazione 802.1X del client.</span><span class="sxs-lookup"><span data-stu-id="5e639-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="5e639-127">Inviare commenti e suggerimenti tramite Hub di Feedback.</span><span class="sxs-lookup"><span data-stu-id="5e639-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="5e639-128">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="5e639-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="5e639-129">Wi-Fi risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5e639-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="5e639-130">Di seguito sono riportati alcuni aspetti da provare se non è possibile connettere il HoloLens a una Wi-Fi rete:</span><span class="sxs-lookup"><span data-stu-id="5e639-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="5e639-131">Assicurarsi che la Wi-Fi sia attivata.</span><span class="sxs-lookup"><span data-stu-id="5e639-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="5e639-132">Per verificare, usare il movimento Avvia, quindi selezionare Impostazioni > rete & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="5e639-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="5e639-133">Se Wi-Fi è attivata, provare a disattivarla e quindi ad attivarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e639-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="5e639-134">Spostarsi più vicino al router o al punto di accesso.</span><span class="sxs-lookup"><span data-stu-id="5e639-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="5e639-135">Riavviare il router Wi-Fi, quindi riavviare HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5e639-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="5e639-136">Provare a eseguire di nuovo la connessione.</span><span class="sxs-lookup"><span data-stu-id="5e639-136">Try connecting again.</span></span>
4. <span data-ttu-id="5e639-137">Se nessuna di queste operazioni funziona, verificare che il router utilizzi il firmware più recente.</span><span class="sxs-lookup"><span data-stu-id="5e639-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="5e639-138">Queste informazioni sono disponibili nel sito Web del produttore.</span><span class="sxs-lookup"><span data-stu-id="5e639-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="5e639-139">Quando si accede a un account aziendale o aziendale nel dispositivo, può anche essere applicato un criterio di gestione dei dispositivi mobili (MDM), se il criterio è configurato dall'amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="5e639-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

[<span data-ttu-id="5e639-140">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="5e639-140">Back to list</span></span>](#list)

## <a name="network-troubleshooting"></a><span data-ttu-id="5e639-141">Risoluzione dei problemi di rete</span><span class="sxs-lookup"><span data-stu-id="5e639-141">Network Troubleshooting</span></span>
<span data-ttu-id="5e639-142">Se i problemi di rete sono un ostacolo alla distribuzione e all'uso di HoloLens 2 nell'organizzazione, configurare Fiddler e/o Wireshark per acquisire e analizzare il traffico HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5e639-142">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, configure Fiddler and/or Wireshark to capture and analyze HTTP/HTTPS traffic.</span></span> 

### <a name="configure-fiddler-to-capture-http-traffic"></a><span data-ttu-id="5e639-143">Configurare Fiddler per l'acquisizione del traffico HTTP</span><span class="sxs-lookup"><span data-stu-id="5e639-143">Configure Fiddler to capture HTTP traffic</span></span>
<span data-ttu-id="5e639-144">Fiddler è un proxy di debug Web e viene usato per risolvere i problemi relativi a HTTP(S).</span><span class="sxs-lookup"><span data-stu-id="5e639-144">Fiddler is a web debugging proxy and is used to troubleshoot HTTP(S) issues.</span></span> <span data-ttu-id="5e639-145">Acquisisce ogni richiesta HTTP che il computer effettua e registra tutti gli elementi associati.</span><span class="sxs-lookup"><span data-stu-id="5e639-145">It captures every HTTP request the computer makes and records everything associated with it.</span></span> <span data-ttu-id="5e639-146">La ricerca di problemi di autenticazione dell'utente finale per le app HTTPS migliora la produttività e l'efficienza per i casi d'uso HoloLens 2 destinazione.</span><span class="sxs-lookup"><span data-stu-id="5e639-146">Uncovering end-user authentication issues for your HTTPS apps drives better productivity and efficiency for your target HoloLens 2 use cases.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="5e639-147">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5e639-147">Prerequisites</span></span>
 
- <span data-ttu-id="5e639-148">HoloLens 2 dispositivi e il PC devono essere nella stessa rete</span><span class="sxs-lookup"><span data-stu-id="5e639-148">HoloLens 2 devices and your PC must be on the same network</span></span>
- <span data-ttu-id="5e639-149">Prendere nota dell'indirizzo IP del PC</span><span class="sxs-lookup"><span data-stu-id="5e639-149">Note the IP address of your PC</span></span>

#### <a name="install-and-configure-fiddler"></a><span data-ttu-id="5e639-150">Installare e configurare Fiddler</span><span class="sxs-lookup"><span data-stu-id="5e639-150">Install and Configure Fiddler</span></span>

1. <span data-ttu-id="5e639-151">Nel PC installare [e](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) avviare Fiddler.</span><span class="sxs-lookup"><span data-stu-id="5e639-151">On your PC - [install](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) and start Fiddler.</span></span>  
1. <span data-ttu-id="5e639-152">Nel PC configurare Fiddler per consentire ai computer remoti di connettersi.</span><span class="sxs-lookup"><span data-stu-id="5e639-152">On your PC - configure Fiddler to allow remote computers to connect.</span></span>
    1. <span data-ttu-id="5e639-153">Passare a Fiddler Impostazioni -> Connessioni</span><span class="sxs-lookup"><span data-stu-id="5e639-153">Go to Fiddler Settings -> Connections</span></span>
    1. <span data-ttu-id="5e639-154">Si noti la porta di ascolto per Fiddler (il valore predefinito è 8866)</span><span class="sxs-lookup"><span data-stu-id="5e639-154">Note the listening port for Fiddler (default is 8866)</span></span>
    1. <span data-ttu-id="5e639-155">Selezionare Consenti ai computer remoti di connettersi</span><span class="sxs-lookup"><span data-stu-id="5e639-155">Check Allow remote computers to connect</span></span>
    1. <span data-ttu-id="5e639-156">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5e639-156">Click Save</span></span>
3. <span data-ttu-id="5e639-157">Nel HoloLens 2 configurare Fiddler come server proxy<sup>1:</sup></span><span class="sxs-lookup"><span data-stu-id="5e639-157">On your HoloLens 2 – configure Fiddler as the proxy server<sup>1</sup>:</span></span>
    1. <span data-ttu-id="5e639-158">Aprire il menu Start e selezionare Impostazioni</span><span class="sxs-lookup"><span data-stu-id="5e639-158">Open the Start menu and select Settings</span></span>
    1. <span data-ttu-id="5e639-159">Selezionare Rete & Internet e quindi Proxy nel menu a sinistra</span><span class="sxs-lookup"><span data-stu-id="5e639-159">Select Network & Internet and then Proxy on the left menu</span></span>
    1. <span data-ttu-id="5e639-160">Scorrere verso il basso fino a Manual proxy setup (Configurazione manuale del proxy) e impostare Use a proxy server (Usa un server proxy) su On (Attiva)</span><span class="sxs-lookup"><span data-stu-id="5e639-160">Scroll down to Manual proxy setup and toggle Use a proxy server to On</span></span>
    1. <span data-ttu-id="5e639-161">Immettere l'indirizzo IP del PC in cui è installato Fiddler</span><span class="sxs-lookup"><span data-stu-id="5e639-161">Enter the IP address of the PC where Fiddler is installed</span></span>
    1. <span data-ttu-id="5e639-162">Immettere il numero di porta indicato in precedenza (il valore predefinito è 8866)</span><span class="sxs-lookup"><span data-stu-id="5e639-162">Enter the port number noted above (default is 8866)</span></span>
    1. <span data-ttu-id="5e639-163">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5e639-163">Click Save</span></span>

<span data-ttu-id="5e639-164"><sup>1</sup> Per le build 20279.1006+ (Insider e la versione futura), seguire questa procedura per configurare il proxy:</span><span class="sxs-lookup"><span data-stu-id="5e639-164"><sup>1</sup> For builds 20279.1006+ (Insiders and the upcoming release), use the following steps to configure proxy:</span></span>
1. <span data-ttu-id="5e639-165">Aprire il menu Start e passare alla pagina Wi-Fi proprietà della rete virtuale</span><span class="sxs-lookup"><span data-stu-id="5e639-165">Open the Start menu and go to your Wi-Fi Network’s Properties page</span></span> 
1. <span data-ttu-id="5e639-166">Scorrere verso il basso fino a Proxy</span><span class="sxs-lookup"><span data-stu-id="5e639-166">Scroll down to Proxy</span></span>
1. <span data-ttu-id="5e639-167">Passare all'installazione manuale</span><span class="sxs-lookup"><span data-stu-id="5e639-167">Change to Manual Setup</span></span>
1. <span data-ttu-id="5e639-168">Immettere l'indirizzo IP del PC in cui è installato Fiddler</span><span class="sxs-lookup"><span data-stu-id="5e639-168">Enter the IP address of the PC where Fiddler is installed</span></span>
1. <span data-ttu-id="5e639-169">Immettere il numero di porta indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5e639-169">Enter the port number noted above.</span></span> <span data-ttu-id="5e639-170">(il valore predefinito è 8866)</span><span class="sxs-lookup"><span data-stu-id="5e639-170">(default is 8866)</span></span>
1. <span data-ttu-id="5e639-171">Fare clic su Applica</span><span class="sxs-lookup"><span data-stu-id="5e639-171">Click Apply</span></span>
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a><span data-ttu-id="5e639-172">Decrittografare il traffico HTTPS HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5e639-172">Decrypt HTTPS traffic from HoloLens 2</span></span>

1. <span data-ttu-id="5e639-173">Nel PC esportare il certificato di Fiddler.</span><span class="sxs-lookup"><span data-stu-id="5e639-173">On your PC – export the Fiddler certificate.</span></span>
    1. <span data-ttu-id="5e639-174">Passare a Fiddler Impostazioni -> HTTPS ed espandere Impostazioni</span><span class="sxs-lookup"><span data-stu-id="5e639-174">Go to Fiddler Settings -> HTTPS and expand Advanced Settings</span></span>
    2. <span data-ttu-id="5e639-175">Fare clic su Export Fiddler certificate (Esporta certificato Fiddler).</span><span class="sxs-lookup"><span data-stu-id="5e639-175">Click Export Fiddler certificate.</span></span> <span data-ttu-id="5e639-176">Verrà salvato sul desktop</span><span class="sxs-lookup"><span data-stu-id="5e639-176">It will save to your desktop</span></span>
    3. <span data-ttu-id="5e639-177">Spostare il certificato nella cartella Download nel HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5e639-177">Move the certificate over to the Downloads folder on your HoloLens 2</span></span>

2.  <span data-ttu-id="5e639-178">Nel HoloLens 2 importare il certificato di Fiddler.</span><span class="sxs-lookup"><span data-stu-id="5e639-178">On your HoloLens 2 - import the Fiddler certificate.</span></span>
    1. <span data-ttu-id="5e639-179">Passare a Impostazioni -> aggiornamento e sicurezza -> certificati</span><span class="sxs-lookup"><span data-stu-id="5e639-179">Go to Settings -> Update and Security -> Certificates</span></span>
    2. <span data-ttu-id="5e639-180">Fare clic su Installa certificato, passare alla cartella Download e selezionare il certificato Fiddler</span><span class="sxs-lookup"><span data-stu-id="5e639-180">Click Install Certificate, browse to the Downloads folder and select the Fiddler certificate</span></span>
    3. <span data-ttu-id="5e639-181">Modificare il percorso dell'archivio in Computer locale</span><span class="sxs-lookup"><span data-stu-id="5e639-181">Change Store Location to Local Machine</span></span>
    4. <span data-ttu-id="5e639-182">Modificare l'archivio certificati nella radice</span><span class="sxs-lookup"><span data-stu-id="5e639-182">Change Certificate Store to root</span></span>
    5. <span data-ttu-id="5e639-183">Selezionare Installa</span><span class="sxs-lookup"><span data-stu-id="5e639-183">Select Install</span></span>
    6. <span data-ttu-id="5e639-184">Verificare che il certificato sia visualizzato nell'elenco dei certificati.</span><span class="sxs-lookup"><span data-stu-id="5e639-184">Confirm the certificate is showing in the list of certificates.</span></span> <span data-ttu-id="5e639-185">In caso contrario, ripetere i passaggi precedenti</span><span class="sxs-lookup"><span data-stu-id="5e639-185">If not, repeat the above steps</span></span>

#### <a name="inspect-https-sessions"></a><span data-ttu-id="5e639-186">Esaminare le sessioni HTTP(S)</span><span class="sxs-lookup"><span data-stu-id="5e639-186">Inspect HTTP(S) sessions</span></span>

<span data-ttu-id="5e639-187">Nel PC Fiddler mostrerà le HoloLens 2 HTTP(S) attive del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5e639-187">On your PC, Fiddler will show the HoloLens 2’s live HTTP(S) sessions.</span></span> <span data-ttu-id="5e639-188">Il pannello Inspectors (Controlli) in Fiddler può visualizzare la richiesta/risposta HTTP(S) in visualizzazioni diverse. Ad esempio, la visualizzazione "Raw" mostra la richiesta o la risposta non elaborata in testo normale.</span><span class="sxs-lookup"><span data-stu-id="5e639-188">The Inspectors panel in Fiddler can show HTTP(S) request/response in different views - for example, the “Raw” view shows the raw request or response in plain text.</span></span> 

### <a name="configure-wireshark-to-capture-network-traffic"></a><span data-ttu-id="5e639-189">Configurare Wireshark per l'acquisizione del traffico di rete</span><span class="sxs-lookup"><span data-stu-id="5e639-189">Configure Wireshark to capture network traffic</span></span>
<span data-ttu-id="5e639-190">Wireshark è un analizzatore di protocolli di rete e viene usato per controllare il traffico TCP/UDP da e verso i dispositivi HoloLens 2 rete.</span><span class="sxs-lookup"><span data-stu-id="5e639-190">Wireshark is a network protocol analyzer and is used to inspect TCP/UDP traffic from and to your HoloLens 2 devices.</span></span> <span data-ttu-id="5e639-191">In questo modo è facile identificare il traffico che attraversa la rete verso il HoloLens 2, la quantità, la frequenza, la latenza tra determinati hop e così via.</span><span class="sxs-lookup"><span data-stu-id="5e639-191">This makes it easy to identify what traffic is crossing your network to your HoloLens 2, how much of it, how frequently, how much latency there is between certain hops, and so forth.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="5e639-192">Prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="5e639-192">Prerequisites:</span></span>
- <span data-ttu-id="5e639-193">Il PC deve avere accesso a Internet e supportare la condivisione Internet su Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="5e639-193">PC must have internet access and support Internet sharing over Wi-Fi</span></span>

#### <a name="install-and-configure-wireshark"></a><span data-ttu-id="5e639-194">Installare e configurare Wireshark</span><span class="sxs-lookup"><span data-stu-id="5e639-194">Install and Configure Wireshark</span></span>
1. <span data-ttu-id="5e639-195">Nel PC installare [Wireshark](https://www.wireshark.org/#download)</span><span class="sxs-lookup"><span data-stu-id="5e639-195">On your PC - install [Wireshark](https://www.wireshark.org/#download)</span></span> 
1. <span data-ttu-id="5e639-196">Nel PC abilitare Hotspot per dispositivi mobili per condividere la connessione Internet dal Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="5e639-196">On your PC - enable Mobile hotspot to share your Internet connection from Wi-Fi.</span></span>
1. <span data-ttu-id="5e639-197">Nel PC avviare Wireshark e acquisire il traffico dall'interfaccia hotspot mobile.</span><span class="sxs-lookup"><span data-stu-id="5e639-197">On your PC - start Wireshark and capture traffic from the Mobile hotspot interface.</span></span> 
1. <span data-ttu-id="5e639-198">Nel HoloLens 2: modificare la Wi-Fi di rete nell'hotspot Mobile del PC.</span><span class="sxs-lookup"><span data-stu-id="5e639-198">On your HoloLens 2 – change its Wi-Fi network to the PC’s Mobile hotspot.</span></span> <span data-ttu-id="5e639-199">HoloLens 2 Il traffico IP verrà visualizzato in Wireshark.</span><span class="sxs-lookup"><span data-stu-id="5e639-199">HoloLens 2 IP traffic will show up in Wireshark.</span></span>

#### <a name="analyze-wireshark-logs"></a><span data-ttu-id="5e639-200">Analizzare i log di Wireshark</span><span class="sxs-lookup"><span data-stu-id="5e639-200">Analyze Wireshark logs</span></span>
<span data-ttu-id="5e639-201">I filtri Wireshark consentono di filtrare i pacchetti di interesse.</span><span class="sxs-lookup"><span data-stu-id="5e639-201">Wireshark filters can help filtering out the packets of interests.</span></span> 

<span data-ttu-id="5e639-202">Vedere il [blog originale.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)</span><span class="sxs-lookup"><span data-stu-id="5e639-202">Check out the original [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span></span>

[<span data-ttu-id="5e639-203">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="5e639-203">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="5e639-204">Non è possibile accedere a un dispositivo di configurazione HoloLens precedente</span><span class="sxs-lookup"><span data-stu-id="5e639-204">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="5e639-205">Se il dispositivo è stato configurato in precedenza per un altro utente, per un client o per un ex dipendente [](/intune/remote-actions/devices-wipe) e non si ha la password per sbloccare il dispositivo, è possibile usare Intune per cancellare in remoto il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5e639-205">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="5e639-206">Il dispositivo viene quindi nuovamente lampeggiato.</span><span class="sxs-lookup"><span data-stu-id="5e639-206">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="5e639-207">Quando si cancella il dispositivo, assicurarsi di lasciare deselezionato Mantieni lo stato **di registrazione e l'account** utente.</span><span class="sxs-lookup"><span data-stu-id="5e639-207">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>

[<span data-ttu-id="5e639-208">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="5e639-208">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="5e639-209">Non è possibile accedere dopo l'aggiornamento a Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="5e639-209">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="5e639-210">Sintomi</span><span class="sxs-lookup"><span data-stu-id="5e639-210">Symptoms</span></span>
- <span data-ttu-id="5e639-211">L'uso del PIN per l'accesso avrà esito negativo dopo l'immissione del PIN corretto.</span><span class="sxs-lookup"><span data-stu-id="5e639-211">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="5e639-212">L'uso del metodo di accesso Web avrà esito negativo dopo l'accesso nella pagina Web.</span><span class="sxs-lookup"><span data-stu-id="5e639-212">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="5e639-213">Il dispositivo non è elencato come "Azure AD aggiunto" [in](https://portal.azure.com/) portale di Azure -> Azure Active Directory -> Dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5e639-213">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="5e639-214">Causa</span><span class="sxs-lookup"><span data-stu-id="5e639-214">Cause</span></span>
<span data-ttu-id="5e639-215">Il dispositivo in oggetto potrebbe essere stato eliminato dal tenant Azure AD destinazione.</span><span class="sxs-lookup"><span data-stu-id="5e639-215">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="5e639-216">Ad esempio, ciò può verificarsi perché:</span><span class="sxs-lookup"><span data-stu-id="5e639-216">For example, this may happen because:</span></span>

- <span data-ttu-id="5e639-217">Un amministratore o un utente ha eliminato il dispositivo nel portale di Azure o usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e639-217">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="5e639-218">Il dispositivo è stato rimosso dal tenant Azure AD a causa dell'inattività.</span><span class="sxs-lookup"><span data-stu-id="5e639-218">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="5e639-219">Per un ambiente gestito in modo efficiente, è in genere consigliabile che gli amministratori IT rimuovono i dispositivi inattivi non più [Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span><span class="sxs-lookup"><span data-stu-id="5e639-219">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="5e639-220">Quando un dispositivo inciso tenta di contattare nuovamente il tenant Azure AD dopo l'eliminazione, non riuscirà a eseguire l'autenticazione con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5e639-220">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="5e639-221">Questo effetto è spesso invisibile all'utente del dispositivo, perché l'accesso memorizzato nella cache tramite PIN continuerà a consentire all'utente di accedere.</span><span class="sxs-lookup"><span data-stu-id="5e639-221">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="5e639-222">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="5e639-222">Mitigation</span></span>
<span data-ttu-id="5e639-223">Attualmente non è possibile aggiungere un dispositivo HoloLens eliminato in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5e639-223">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="5e639-224">I dispositivi interessati dovranno essere puliti seguendo le istruzioni per [il reflashing del dispositivo.](hololens-recovery.md#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="5e639-224">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

[<span data-ttu-id="5e639-225">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="5e639-225">Back to list</span></span>](#list)

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="5e639-226">Risoluzione dei problemi di Autopilot</span><span class="sxs-lookup"><span data-stu-id="5e639-226">Autopilot Troubleshooting</span></span>

<span data-ttu-id="5e639-227">Gli articoli seguenti possono essere una risorsa utile per ottenere altre informazioni e risolvere i problemi di Autopilot, tuttavia tenere presente che questi articoli sono basati su Windows 10 Desktop e che non tutte le informazioni possono essere applicabili a HoloLens:</span><span class="sxs-lookup"><span data-stu-id="5e639-227">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="5e639-228">Windows Autopilot - Problemi noti</span><span class="sxs-lookup"><span data-stu-id="5e639-228">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="5e639-229">Risolvere i problemi di registrazione dei dispositivi Windows in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5e639-229">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="5e639-230">Windows Autopilot - Conflitti di criteri</span><span class="sxs-lookup"><span data-stu-id="5e639-230">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

[<span data-ttu-id="5e639-231">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="5e639-231">Back to list</span></span>](#list)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="5e639-232">Domande frequenti HoloLens dispositivi gestiti</span><span class="sxs-lookup"><span data-stu-id="5e639-232">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="5e639-233">È possibile usare System Center Configuration Manager (SCCM) per gestire HoloLens dispositivi?</span><span class="sxs-lookup"><span data-stu-id="5e639-233">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="5e639-234">No.</span><span class="sxs-lookup"><span data-stu-id="5e639-234">No.</span></span> <span data-ttu-id="5e639-235">È necessario usare un sistema MDM per gestire i HoloLens mobili.</span><span class="sxs-lookup"><span data-stu-id="5e639-235">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="5e639-236">È possibile usare Active Directory Domain Services (Ad DS) per gestire HoloLens account utente?</span><span class="sxs-lookup"><span data-stu-id="5e639-236">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="5e639-237">No.</span><span class="sxs-lookup"><span data-stu-id="5e639-237">No.</span></span> <span data-ttu-id="5e639-238">È necessario usare Azure Active Directory (Azure AD) per gestire gli account utente per HoloLens dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5e639-238">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="5e639-239">È HoloLens la registrazione automatica di Automated Data Capture Systems (ADCS) ?</span><span class="sxs-lookup"><span data-stu-id="5e639-239">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="5e639-240">No.</span><span class="sxs-lookup"><span data-stu-id="5e639-240">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="5e639-241">È HoloLens partecipare all'autenticazione Windows integrata?</span><span class="sxs-lookup"><span data-stu-id="5e639-241">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="5e639-242">No.</span><span class="sxs-lookup"><span data-stu-id="5e639-242">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="5e639-243">La HoloLens supporta la personalizzazione?</span><span class="sxs-lookup"><span data-stu-id="5e639-243">Does HoloLens support branding?</span></span>

<span data-ttu-id="5e639-244">No.</span><span class="sxs-lookup"><span data-stu-id="5e639-244">No.</span></span> <span data-ttu-id="5e639-245">Tuttavia, è possibile risolvere questo problema usando uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e639-245">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="5e639-246">Creare un'app personalizzata e quindi abilitare [la modalità tutto schermo](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="5e639-246">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="5e639-247">L'app personalizzata può essere personalizzata e può avviare altre app, ad esempio Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="5e639-247">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="5e639-248">Modificare tutte le immagini del profilo utente in Azure AD al logo aziendale.</span><span class="sxs-lookup"><span data-stu-id="5e639-248">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="5e639-249">Tuttavia, potrebbe non essere consigliabile per tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="5e639-249">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="5e639-250">Quali funzionalità di registrazione HoloLens 2 offerte?</span><span class="sxs-lookup"><span data-stu-id="5e639-250">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="5e639-251">La registrazione è limitata alle tracce che possono essere acquisite negli scenari di sviluppo o risoluzione dei problemi o ai dati di telemetria inviati dai dispositivi ai server Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5e639-251">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="5e639-252">Domande sulla protezione dei HoloLens mobili</span><span class="sxs-lookup"><span data-stu-id="5e639-252">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="5e639-253">Vedere [le informazioni HoloLens 2 sicurezza.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5e639-253">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="5e639-254">Per HoloLens dispositivi di prima generazione, vedere [queste domande frequenti.](hololens1-faq-security.yml)</span><span class="sxs-lookup"><span data-stu-id="5e639-254">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.yml).</span></span>

[<span data-ttu-id="5e639-255">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="5e639-255">Back to list</span></span>](#list)
