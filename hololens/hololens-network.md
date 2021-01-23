---
title: Connettere HoloLens a una rete
description: Informazioni su come configurare e connettere a Internet il dispositivo HoloLens e su come identificare l'indirizzo IP del dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, wireless, Internet, IP, indirizzo IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 6d11ae0907aa82df71d7c86bb37996dcce71d845
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283977"
---
# <span data-ttu-id="111c7-104">Connettere HoloLens a una rete</span><span class="sxs-lookup"><span data-stu-id="111c7-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="111c7-105">Per eseguire la maggior parte delle operazioni in HoloLens, è necessario essere connessi a una rete.</span><span class="sxs-lookup"><span data-stu-id="111c7-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="111c7-106">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="111c7-106">This guide will help you:</span></span>

- <span data-ttu-id="111c7-107">Connetterti a una rete tramite Wi-Fi o (solo per HoloLens 2) Ethernet tramite USB-C</span><span class="sxs-lookup"><span data-stu-id="111c7-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="111c7-108">Disabilitare e riabilitare il Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="111c7-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="111c7-109">Leggi altre informazioni sull'[uso di HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="111c7-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="111c7-110">Connessione per la prima volta</span><span class="sxs-lookup"><span data-stu-id="111c7-110">Connecting for the first time</span></span>

<span data-ttu-id="111c7-111">La prima volta che usi HoloLens, dovrai seguire le istruzioni per la connessione a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="111c7-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="111c7-112">In caso di problemi di connessione a una rete Wi-Fi durante l'installazione, verifica che la rete sia aperta, protetta da password o captive portal.</span><span class="sxs-lookup"><span data-stu-id="111c7-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="111c7-113">Verifica che la rete non richieda l'uso di un certificato per la connessione.</span><span class="sxs-lookup"><span data-stu-id="111c7-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="111c7-114">Dopo la configurazione, potrai connetterti ad altri tipi di reti Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="111c7-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="111c7-115">Sui dispositivi HoloLens 2 un utente potrebbe anche [usare un adattatore USB-C per Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) per collegarsi direttamente al Wi-Fi e facilitare la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="111c7-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="111c7-116">Dopo aver configurato il dispositivo, l'utente può continuare a usare l'adattatore, oppure potrebbe scollegare il dispositivo dalla scheda e [connettersi a una rete Wi-Fi dopo la configurazione](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="111c7-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="111c7-117">Connessione alla rete Wi-Fi dopo la configurazione</span><span class="sxs-lookup"><span data-stu-id="111c7-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="111c7-118">Eseguire il **gesto Start** e selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="111c7-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="111c7-119">L'app Impostazioni verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="111c7-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="111c7-120">Seleziona **Rete e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="111c7-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="111c7-121">Verifica che il Wi-Fi sia attivato.</span><span class="sxs-lookup"><span data-stu-id="111c7-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="111c7-122">Se non vedi la tua rete, scorri in basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="111c7-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="111c7-123">Seleziona una rete, quindi fai clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="111c7-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="111c7-124">Se viene richiesto di digitare una password di rete, inseriscila, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="111c7-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="111c7-125">HoloLens contiene una radio Wi-Fi 2x2, con supporto di 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="111c7-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="111c7-126">La connessione di HoloLens a una rete Wi-Fi avviene in modo simile alla connessione di un dispositivo desktop o mobile Windows 10 a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="111c7-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Impostazioni Wi-Fi di HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="111c7-128">Puoi anche verificare che la connessione a una rete Wi-Fi sia stabilita, controllando lo stato Wi-Fi nel menu **Start**:</span><span class="sxs-lookup"><span data-stu-id="111c7-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="111c7-129">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="111c7-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="111c7-130">In alto a sinistra del menu **Start** controlla lo stato del Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="111c7-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="111c7-131">Verranno visualizzati stato del Wi-Fi e SSID della rete connessa.</span><span class="sxs-lookup"><span data-stu-id="111c7-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="111c7-132">Risoluzione dei problemi relativi alla connessione al Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="111c7-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="111c7-133">Se si verificano problemi di connessione al Wi-Fi, vedere [Non riesco a connettermi al Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="111c7-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="111c7-134">Quando si accede a un account aziendale o dell'organizzazione sul dispositivo, è possibile che vengano applicati anche criteri di gestione di dispositivi mobili (MDM), se i criteri sono configurati dall'amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="111c7-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="111c7-135">Connettere HoloLens a una rete Wi-Fi aziendale</span><span class="sxs-lookup"><span data-stu-id="111c7-135">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="111c7-136">I profili Wi-Fi aziendali usano il protocollo EAP (Extensible Authentication Protocol) per autenticare le connessioni Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="111c7-136">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="111c7-137">Il profilo Wi-Fi aziendale HoloLens può essere configurato tramite MDM o pacchetto di provisioning creato tramite [Progettazione immagine e configurazione di Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="111c7-137">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="111c7-138">Per il dispositivo gestito da Microsoft Intune, fare riferimento a [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) per le istruzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="111c7-138">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="111c7-139">Per creare un pacchetto di provisioning Wi-Fi in WCD, è necessario un file .xml del profilo Wi-Fi preconfigurato.</span><span class="sxs-lookup"><span data-stu-id="111c7-139">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="111c7-140">Di seguito è riportato un profilo Wi-Fi di esempio per WPA2-Enterprise con autenticazione EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="111c7-140">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="111c7-141">Potrebbe essere necessario eseguire il provisioning del certificato CA radice del server e del certificato client sul dispositivo a seconda del tipo di EAP.</span><span class="sxs-lookup"><span data-stu-id="111c7-141">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="111c7-142">Risorse aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="111c7-142">Additional resources:</span></span>

- <span data-ttu-id="111c7-143">Schema WLANv1Profile: [[MS-GPWL]: Profilo Wireless LAN v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="111c7-143">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="111c7-144">Schema EAP-TLS: [[MS-GPWL]: schema Microsoft EAP TLS | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="111c7-144">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <span data-ttu-id="111c7-145">Risoluzione dei problemi di EAP</span><span class="sxs-lookup"><span data-stu-id="111c7-145">EAP Troubleshooting</span></span>

1. <span data-ttu-id="111c7-146">Controllare che il profilo Wi-Fi abbia le giuste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="111c7-146">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="111c7-147">Il tipo di EAP è configurato correttamente, tipi di EAP comuni: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="111c7-147">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="111c7-148">Il nome Wi-Fi SSID è corretto e corrisponde alla stringa HEX.</span><span class="sxs-lookup"><span data-stu-id="111c7-148">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="111c7-149">Per EAP-TLS, TrustedRootCA contiene l'hash SHA-1 del certificato CA radice attendibile del server&#39;s.</span><span class="sxs-lookup"><span data-stu-id="111c7-149">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="111c7-150">Su PC Windows, il comando &quot;certutil.exe -dump cert\_file\_name&quot; mostrerà una stringa hash SHA-1 del certificato&#39;s.</span><span class="sxs-lookup"><span data-stu-id="111c7-150">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="111c7-151">Raccogliere acquisizioni di pacchetti di rete sui registri del server di punto di accesso, controller oppure AAA per comprendere dove non è riuscita la sessione EAP.</span><span class="sxs-lookup"><span data-stu-id="111c7-151">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="111c7-152">Se l'identità EAP fornita da HoloLens non è prevista, controllare se il provisioning dell'identità è stato eseguito correttamente tramite il profilo Wi-Fi o il certificato client.</span><span class="sxs-lookup"><span data-stu-id="111c7-152">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="111c7-153">Se il server rifiuta il certificato client HoloLens, controllare se il certificato client richiesto sia stato fornito nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="111c7-153">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="111c7-154">Se HoloLens rifiuta il certificato del server, verificare se è stato eseguito il provisioning del certificato CA radice del server in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="111c7-154">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="111c7-155">Se il profilo aziendale viene fornito tramite il pacchetto di provisioning Wi-Fi, è consigliabile l’applicazione del pacchetto di provisioning su un PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="111c7-155">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="111c7-156">Se fallisce anche su PC Windows 10, seguire la [Guida alla risoluzione dei problemi di autenticazione 802.1X del client Windows](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span><span class="sxs-lookup"><span data-stu-id="111c7-156">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="111c7-157">Inviare feedback tramite [Hub di feedback](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="111c7-157">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <span data-ttu-id="111c7-158">Risorse aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="111c7-158">Additional resources:</span></span>
- [<span data-ttu-id="111c7-159">Esportare le impostazioni Wi-Fi da un dispositivo Windows</span><span class="sxs-lookup"><span data-stu-id="111c7-159">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <span data-ttu-id="111c7-160">VPN</span><span class="sxs-lookup"><span data-stu-id="111c7-160">VPN</span></span>
<span data-ttu-id="111c7-161">Una connessione VPN può essere utile per garantire una connessione più sicura e l'accesso alla rete aziendale e a Internet.</span><span class="sxs-lookup"><span data-stu-id="111c7-161">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="111c7-162">HoloLens 2 supporta il client VPN predefinito e il plug-in VPN UWP (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="111c7-162">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="111c7-163">Protocolli VPN predefiniti supportati:</span><span class="sxs-lookup"><span data-stu-id="111c7-163">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="111c7-164">IKEv2</span><span class="sxs-lookup"><span data-stu-id="111c7-164">IKEv2</span></span>
- <span data-ttu-id="111c7-165">L2TP</span><span class="sxs-lookup"><span data-stu-id="111c7-165">L2TP</span></span>
- <span data-ttu-id="111c7-166">PPTP</span><span class="sxs-lookup"><span data-stu-id="111c7-166">PPTP</span></span>

<span data-ttu-id="111c7-167">Se il certificato viene usato per l'autenticazione per il client VPN predefinito, è necessario aggiungere il certificato client necessario all'archivio certificati utente.</span><span class="sxs-lookup"><span data-stu-id="111c7-167">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="111c7-168">Per scoprire se un plug-in VPN di terze parti supporta HoloLens 2, passare allo Store per individuare l'app VPN e controllare se HoloLens compare tra i dispositivi supportati e se nella pagina dei requisiti di sistema l'app supporta l'architettura ARM o ARM64.</span><span class="sxs-lookup"><span data-stu-id="111c7-168">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="111c7-169">HoloLens supporta solo le applicazioni della piattaforma UWP per la rete VPN di terze parti.</span><span class="sxs-lookup"><span data-stu-id="111c7-169">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="111c7-170">La rete VPN può essere gestita da MDM tramite [Impostazioni/ConsentiVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) e impostata con il [criterio Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="111c7-170">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="111c7-171">Scoprire ulteriori informazioni su [come configurare la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [queste guide](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="111c7-171">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <span data-ttu-id="111c7-172">VPN tramite interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="111c7-172">VPN via UI</span></span>

<span data-ttu-id="111c7-173">Per impostazione predefinita, la VPN non è abilitata, ma può essere abilitata manualmente aprendo l'app **Impostazioni**, quindi passando a **Rete e internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="111c7-173">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="111c7-174">Selezionare un provider VPN.</span><span class="sxs-lookup"><span data-stu-id="111c7-174">Select a VPN provider.</span></span>
1. <span data-ttu-id="111c7-175">Creare un nome di connessione.</span><span class="sxs-lookup"><span data-stu-id="111c7-175">Create a connection name.</span></span> 
1. <span data-ttu-id="111c7-176">Immettere il nome o l'indirizzo del server.</span><span class="sxs-lookup"><span data-stu-id="111c7-176">Enter your server name or address.</span></span>
1. <span data-ttu-id="111c7-177">Selezionare il tipo di VPN.</span><span class="sxs-lookup"><span data-stu-id="111c7-177">Select the VPN type.</span></span>
1. <span data-ttu-id="111c7-178">Selezionare il tipo di informazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="111c7-178">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="111c7-179">Aggiungere facoltativamente il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="111c7-179">Optionally add user name and password.</span></span>
1. <span data-ttu-id="111c7-180">Applicare le impostazioni VPN.</span><span class="sxs-lookup"><span data-stu-id="111c7-180">Apply the VPN settings.</span></span> 

![Impostazioni VPN di HoloLens](./images/vpn-settings-ui.jpg)

### <span data-ttu-id="111c7-182">VPN impostato tramite il pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="111c7-182">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="111c7-183">In Windows Holographic, versione 20H2 è stato risolto un problema di configurazione del proxy per la connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="111c7-183">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="111c7-184">Se si intende usare questo flusso, valutare l'aggiornamento dei dispositivi a questa build.</span><span class="sxs-lookup"><span data-stu-id="111c7-184">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="111c7-185">Avviare Progettazione immagine e configurazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="111c7-185">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="111c7-186">Fare clic su **Effettua il provisioning dei dispositivi HoloLens**, quindi selezionare un dispositivo di destinazione ed infine **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="111c7-186">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="111c7-187">Immettere il nome e il percorso del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="111c7-187">Enter package name and path.</span></span>
1. <span data-ttu-id="111c7-188">Fare clic su **Passa a Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="111c7-188">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="111c7-189">Aprire le **Impostazioni di runtime**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="111c7-189">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="111c7-190">Configurare VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="111c7-190">Configure VPNProfileName</span></span>
1. <span data-ttu-id="111c7-191">Selezionare ProfileType: **Nativo** o di **Terze parti**.</span><span class="sxs-lookup"><span data-stu-id="111c7-191">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="111c7-192">Per profilo nativo, selezionare **NativeProtocolType**, quindi configurare server, criteri di routing, tipo di autenticazione e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="111c7-192">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="111c7-193">Per il profilo "Terze parti", configurare l'URL del server, il nome della famiglia di pacchetti dell'app plug-in VPN (solo 3 predefiniti) e le configurazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="111c7-193">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="111c7-194">Esportare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="111c7-194">Export your package.</span></span>
1. <span data-ttu-id="111c7-195">Connettere HoloLens e copiare il file con estensione ppkg nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="111c7-195">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="111c7-196">In HoloLens, applicare il VPN. ppkg aprendo il menu Start e selezionando l'opzione **Impostazioni**  ->  **Account**  ->  **Accedi all’azienda o all’istituto di istruzione** ->  **Aggiungi o rimuovi il pacchetto di provisioning** -> Seleziona pacchetto VPN.</span><span class="sxs-lookup"><span data-stu-id="111c7-196">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <span data-ttu-id="111c7-197">Configurazione di VPN tramite Intune</span><span class="sxs-lookup"><span data-stu-id="111c7-197">Setting up VPN via Intune</span></span>
<span data-ttu-id="111c7-198">Basta seguire i documenti di Intune per iniziare.</span><span class="sxs-lookup"><span data-stu-id="111c7-198">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="111c7-199">Quando si seguono questi passaggi, tenere presente i protocolli VPN integrati supportati dai dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="111c7-199">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="111c7-200">[Creare profili VPN per la connessione ai server VPN in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="111c7-200">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="111c7-201">[Impostazioni del dispositivo Windows 10 e Windows Holographic per l'aggiunta di connessioni VPN tramite Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="111c7-201">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="111c7-202">Al termine, ricordarsi di [assegnare il profilo](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="111c7-202">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="111c7-203">VPN tramite soluzioni MDM di terze parti</span><span class="sxs-lookup"><span data-stu-id="111c7-203">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="111c7-204">Esempio di connessione VPN di terze parti:</span><span class="sxs-lookup"><span data-stu-id="111c7-204">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="111c7-205">Esempio di VPN IKEv2 nativo:</span><span class="sxs-lookup"><span data-stu-id="111c7-205">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <span data-ttu-id="111c7-206">Disabilitazione della rete Wi-Fi in HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="111c7-206">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="111c7-207">Uso dell'app Impostazioni in HoloLens</span><span class="sxs-lookup"><span data-stu-id="111c7-207">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="111c7-208">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="111c7-208">Open the **Start** menu.</span></span>
1. <span data-ttu-id="111c7-209">Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="111c7-209">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="111c7-210">L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="111c7-210">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="111c7-211">Seleziona **Rete e Internet**.</span><span class="sxs-lookup"><span data-stu-id="111c7-211">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="111c7-212">Seleziona il dispositivo di scorrimento Wi-Fi per spostarlo nella posizione **Off**.</span><span class="sxs-lookup"><span data-stu-id="111c7-212">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="111c7-213">I componenti RF della radio Wi-Fi verranno disattivati e tutte le funzionalità Wi-Fi in HoloLens verranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="111c7-213">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="111c7-214">Quando la radio Wi-Fi è disabilitata, HoloLens non sarà in grado di caricare automaticamente gli [spazi](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="111c7-214">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="111c7-215">Sposta il dispositivo di scorrimento sulla posizione **Attivato** per attivare la radio Wi-Fi e ripristinare la funzionalità Wi-Fi su Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="111c7-215">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="111c7-216">Lo stato della radio Wi-Fi selezionato (**Attivato** o **Disattivato**) verrà mantenuto a ogni riavvio.</span><span class="sxs-lookup"><span data-stu-id="111c7-216">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="111c7-217">Identificazione dell'indirizzo IP di HoloLens nella rete Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="111c7-217">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="111c7-218">Usando l'app Impostazioni</span><span class="sxs-lookup"><span data-stu-id="111c7-218">By using the Settings app</span></span>

1. <span data-ttu-id="111c7-219">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="111c7-219">Open the **Start** menu.</span></span>
1. <span data-ttu-id="111c7-220">Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="111c7-220">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="111c7-221">L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="111c7-221">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="111c7-222">Seleziona **Rete e Internet**.</span><span class="sxs-lookup"><span data-stu-id="111c7-222">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="111c7-223">Scorri in basso verso la fine dell'elenco delle reti Wi-Fi disponibili e seleziona **Proprietà hardware**.</span><span class="sxs-lookup"><span data-stu-id="111c7-223">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Proprietà hardware nelle impostazioni Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="111c7-225">L'indirizzo IP viene visualizzato accanto all'**indirizzo IPv4**.</span><span class="sxs-lookup"><span data-stu-id="111c7-225">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="111c7-226">Tramite i comandi vocali</span><span class="sxs-lookup"><span data-stu-id="111c7-226">By using voice commands</span></span>

<span data-ttu-id="111c7-227">A seconda del tipo di dispositivo in uso, è possibile usare il comando vocale predefinito o Cortana per visualizzare l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="111c7-227">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="111c7-228">Nelle build successive a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) dire "Qual è il mio indirizzo IP?"</span><span class="sxs-lookup"><span data-stu-id="111c7-228">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="111c7-229">e verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="111c7-229">and it will be displayed.</span></span> <span data-ttu-id="111c7-230">Per le build precedenti o per HoloLens (prima generazione) dire "Ehi Cortana, qual è il mio indirizzo IP?"</span><span class="sxs-lookup"><span data-stu-id="111c7-230">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="111c7-231">e Cortana visualizzerà e leggerà l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="111c7-231">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="111c7-232">Usando il Portale di dispositivi di Windows</span><span class="sxs-lookup"><span data-stu-id="111c7-232">By using Windows Device Portal</span></span>

1. <span data-ttu-id="111c7-233">In un Web browser nel PC apri il [portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="111c7-233">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="111c7-234">Passa alla sezione **Reti**.</span><span class="sxs-lookup"><span data-stu-id="111c7-234">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="111c7-235">In questa sezione vengono visualizzati l'indirizzo IP e altre informazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="111c7-235">This section displays your IP address and other network information.</span></span> <span data-ttu-id="111c7-236">Usando questo metodo, potrai copiare e incollare l'indirizzo IP nel PC di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="111c7-236">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
