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
ms.openlocfilehash: f1968afe7d450425776bac24532f2d84c4dc3c62
ms.sourcegitcommit: 9f79ed9f76b930b8ceb97844d5f9eace9316b8a3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442593"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="d6ab2-104">Connettere HoloLens a una rete</span><span class="sxs-lookup"><span data-stu-id="d6ab2-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="d6ab2-105">Per eseguire la maggior parte delle operazioni in HoloLens, è necessario essere connessi a una rete.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="d6ab2-106">HoloLens contiene una radio 2x2 Wi-Fi con supporto 802.11ac e la connessione a una rete è simile alla connessione di un dispositivo Windows 10 Desktop o Mobile a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="d6ab2-107">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="d6ab2-107">This guide will help you:</span></span>

- <span data-ttu-id="d6ab2-108">Connetterti a una rete tramite Wi-Fi o (solo per HoloLens 2) Ethernet tramite USB-C</span><span class="sxs-lookup"><span data-stu-id="d6ab2-108">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="d6ab2-109">Disabilitare e riabilitare il Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d6ab2-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="d6ab2-110">Leggi altre informazioni sull'[uso di HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="d6ab2-111">Connessione per la prima volta</span><span class="sxs-lookup"><span data-stu-id="d6ab2-111">Connecting for the first time</span></span>

<span data-ttu-id="d6ab2-112">La prima volta che usi HoloLens, dovrai seguire le istruzioni per la connessione a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="d6ab2-113">In caso di problemi di connessione a una rete Wi-Fi durante l'installazione, verifica che la rete sia aperta, protetta da password o captive portal.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="d6ab2-114">Verificare inoltre che la rete non richieda l'utilizzo di un certificato per la connessione.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="d6ab2-115">Dopo la configurazione, potrai connetterti ad altri tipi di reti Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="d6ab2-116">Nei dispositivi HoloLens 2, un utente può anche usare una scheda [da USB-C a Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) per connettersi direttamente a Wi-Fi per facilitare la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="d6ab2-117">Dopo aver configurato il dispositivo, un utente può continuare a usare la scheda oppure disconnettere il dispositivo dalla scheda e connettersi al [Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)dopo aver configurato.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="d6ab2-118">Connessione alla rete Wi-Fi dopo la configurazione</span><span class="sxs-lookup"><span data-stu-id="d6ab2-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="d6ab2-119">Eseguire il **gesto Start** e selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="d6ab2-120">L'app Impostazioni verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="d6ab2-121">Seleziona **Rete e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="d6ab2-122">Verifica che il Wi-Fi sia attivato.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="d6ab2-123">Se non vedi la tua rete, scorri in basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="d6ab2-124">Seleziona una rete, quindi fai clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="d6ab2-125">Se viene richiesto di digitare una password di rete, inseriscila, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![Impostazioni Wi-Fi di HoloLens](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="d6ab2-127">Per verificare di essere connessi a una rete Wi-Fi, controllare lo stato Wi-Fi nel menu **Start:**</span><span class="sxs-lookup"><span data-stu-id="d6ab2-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="d6ab2-128">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="d6ab2-129">In alto a sinistra del menu **Start** controlla lo stato del Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="d6ab2-130">Verranno visualizzati stato del Wi-Fi e SSID della rete connessa.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="d6ab2-131">Se il Wi-Fi non è disponibile, puoi anche connetterti alle reti [cellulare e 5G.](https://docs.microsoft.com/hololens/hololens-cellular)</span><span class="sxs-lookup"><span data-stu-id="d6ab2-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6ab2-132">Per impostazione predefinita, gli utenti non possono ottimizzare il comportamento di roaming di Wi-Fi di HoloLens 2: l'unico modo per aggiornare l'elenco di Wi-Fi è attivare e disattivare i Wi-Fi Off e **On.**</span><span class="sxs-lookup"><span data-stu-id="d6ab2-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="d6ab2-133">In questo modo si evitano molti problemi, ad esempio quando un dispositivo può rimanere "bloccato" a un punto di accesso quando non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="d6ab2-134">Risoluzione dei problemi relativi alla connessione al Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d6ab2-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="d6ab2-135">Se si verificano problemi di connessione al Wi-Fi, vedere [Non riesco a connettermi al Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="d6ab2-136">Quando si accede a un account aziendale o dell'organizzazione sul dispositivo, è possibile che vengano applicati anche criteri di gestione di dispositivi mobili (MDM), se i criteri sono configurati dall'amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="d6ab2-137">Connettere HoloLens a una rete Wi-Fi aziendale</span><span class="sxs-lookup"><span data-stu-id="d6ab2-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="d6ab2-138">I profili Wi-Fi aziendali usano il protocollo EAP (Extensible Authentication Protocol) per autenticare le connessioni Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="d6ab2-139">Il profilo Wi-Fi aziendale HoloLens può essere configurato tramite MDM o pacchetto di provisioning creato tramite [Progettazione immagine e configurazione di Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="d6ab2-140">Per il dispositivo gestito da Microsoft Intune, fare riferimento a [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) per le istruzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="d6ab2-141">Per creare un pacchetto di provisioning Wi-Fi in WCD, è necessario un file .xml del profilo Wi-Fi preconfigurato.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="d6ab2-142">Di seguito è riportato un profilo Wi-Fi di esempio per WPA2-Enterprise con autenticazione EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="d6ab2-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="d6ab2-143">Potrebbe essere necessario eseguire il provisioning del certificato CA radice del server e del certificato client sul dispositivo a seconda del tipo di EAP.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="d6ab2-144">Risorse aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="d6ab2-144">Additional resources:</span></span>

- <span data-ttu-id="d6ab2-145">Schema WLANv1Profile: [[MS-GPWL]: Profilo Wireless LAN v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="d6ab2-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="d6ab2-146">Schema EAP-TLS: [[MS-GPWL]: schema Microsoft EAP TLS | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="d6ab2-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <a name="eap-troubleshooting"></a><span data-ttu-id="d6ab2-147">Risoluzione dei problemi di EAP</span><span class="sxs-lookup"><span data-stu-id="d6ab2-147">EAP Troubleshooting</span></span>

1. <span data-ttu-id="d6ab2-148">Controllare che il profilo Wi-Fi abbia le giuste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="d6ab2-148">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="d6ab2-149">Il tipo di EAP è configurato correttamente, tipi di EAP comuni: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-149">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="d6ab2-150">Il nome Wi-Fi SSID è corretto e corrisponde alla stringa HEX.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-150">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="d6ab2-151">Per EAP-TLS, TrustedRootCA contiene l'hash SHA-1 del certificato CA radice attendibile del server&#39;s.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-151">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="d6ab2-152">Su PC Windows, il comando &quot;certutil.exe -dump cert\_file\_name&quot; mostrerà una stringa hash SHA-1 del certificato&#39;s.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-152">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="d6ab2-153">Raccogliere acquisizioni di pacchetti di rete sui registri del server di punto di accesso, controller oppure AAA per comprendere dove non è riuscita la sessione EAP.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-153">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="d6ab2-154">Se l'identità EAP fornita da HoloLens non è prevista, controllare se il provisioning dell'identità è stato eseguito correttamente tramite il profilo Wi-Fi o il certificato client.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-154">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="d6ab2-155">Se il server rifiuta il certificato client HoloLens, controllare se il certificato client richiesto sia stato fornito nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-155">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="d6ab2-156">Se HoloLens rifiuta il certificato del server, verificare se è stato eseguito il provisioning del certificato CA radice del server in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-156">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="d6ab2-157">Se il profilo aziendale viene fornito tramite il pacchetto di provisioning Wi-Fi, è consigliabile l’applicazione del pacchetto di provisioning su un PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-157">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="d6ab2-158">Se fallisce anche su PC Windows 10, seguire la [Guida alla risoluzione dei problemi di autenticazione 802.1X del client Windows](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-158">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="d6ab2-159">Inviare feedback tramite [Hub di feedback](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-159">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d6ab2-160">Risorse aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="d6ab2-160">Additional resources:</span></span>
- [<span data-ttu-id="d6ab2-161">Esportare le impostazioni Wi-Fi da un dispositivo Windows</span><span class="sxs-lookup"><span data-stu-id="d6ab2-161">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="vpn"></a><span data-ttu-id="d6ab2-162">VPN</span><span class="sxs-lookup"><span data-stu-id="d6ab2-162">VPN</span></span>
<span data-ttu-id="d6ab2-163">Una connessione VPN può essere utile per garantire una connessione più sicura e l'accesso alla rete aziendale e a Internet.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-163">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="d6ab2-164">HoloLens 2 supporta il client VPN predefinito e il plug-in VPN UWP (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-164">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="d6ab2-165">Protocolli VPN predefiniti supportati:</span><span class="sxs-lookup"><span data-stu-id="d6ab2-165">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="d6ab2-166">IKEv2</span><span class="sxs-lookup"><span data-stu-id="d6ab2-166">IKEv2</span></span>
- <span data-ttu-id="d6ab2-167">L2TP</span><span class="sxs-lookup"><span data-stu-id="d6ab2-167">L2TP</span></span>
- <span data-ttu-id="d6ab2-168">PPTP</span><span class="sxs-lookup"><span data-stu-id="d6ab2-168">PPTP</span></span>

<span data-ttu-id="d6ab2-169">Se il certificato viene usato per l'autenticazione per il client VPN predefinito, è necessario aggiungere il certificato client necessario all'archivio certificati utente.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-169">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="d6ab2-170">Per scoprire se un plug-in VPN di terze parti supporta HoloLens 2, passare allo Store per individuare l'app VPN e controllare se HoloLens compare tra i dispositivi supportati e se nella pagina dei requisiti di sistema l'app supporta l'architettura ARM o ARM64.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-170">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="d6ab2-171">HoloLens supporta solo le applicazioni della piattaforma UWP per la rete VPN di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-171">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="d6ab2-172">La rete VPN può essere gestita da MDM tramite [Impostazioni/ConsentiVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) e impostata con il [criterio Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-172">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="d6ab2-173">Scoprire ulteriori informazioni su [come configurare la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [queste guide](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-173">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="d6ab2-174">VPN tramite interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d6ab2-174">VPN via UI</span></span>

<span data-ttu-id="d6ab2-175">Per impostazione predefinita, la VPN non è abilitata, ma può essere abilitata manualmente aprendo l'app **Impostazioni**, quindi passando a **Rete e internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-175">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="d6ab2-176">Selezionare un provider VPN.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-176">Select a VPN provider.</span></span>
1. <span data-ttu-id="d6ab2-177">Creare un nome di connessione.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-177">Create a connection name.</span></span> 
1. <span data-ttu-id="d6ab2-178">Immettere il nome o l'indirizzo del server.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-178">Enter your server name or address.</span></span>
1. <span data-ttu-id="d6ab2-179">Selezionare il tipo di VPN.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-179">Select the VPN type.</span></span>
1. <span data-ttu-id="d6ab2-180">Selezionare il tipo di informazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-180">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="d6ab2-181">Aggiungere facoltativamente il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-181">Optionally add user name and password.</span></span>
1. <span data-ttu-id="d6ab2-182">Applicare le impostazioni VPN.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-182">Apply the VPN settings.</span></span> 

![Impostazioni VPN di HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="d6ab2-184">VPN impostato tramite il pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="d6ab2-184">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="d6ab2-185">In Windows Holographic, versione 20H2 è stato risolto un problema di configurazione del proxy per la connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-185">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="d6ab2-186">Se si intende usare questo flusso, valutare l'aggiornamento dei dispositivi a questa build.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-186">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="d6ab2-187">Avviare Progettazione immagine e configurazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-187">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="d6ab2-188">Fare clic su **Effettua il provisioning dei dispositivi HoloLens**, quindi selezionare un dispositivo di destinazione ed infine **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-188">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="d6ab2-189">Immettere il nome e il percorso del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-189">Enter package name and path.</span></span>
1. <span data-ttu-id="d6ab2-190">Fare clic su **Passa a Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-190">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="d6ab2-191">Aprire le **Impostazioni di runtime**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-191">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="d6ab2-192">Configurare VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="d6ab2-192">Configure VPNProfileName</span></span>
1. <span data-ttu-id="d6ab2-193">Selezionare ProfileType: **Nativo** o di **Terze parti**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-193">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="d6ab2-194">Per profilo nativo, selezionare **NativeProtocolType**, quindi configurare server, criteri di routing, tipo di autenticazione e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-194">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="d6ab2-195">Per il profilo "Terze parti", configurare l'URL del server, il nome della famiglia di pacchetti dell'app plug-in VPN (solo 3 predefiniti) e le configurazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-195">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="d6ab2-196">Esportare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-196">Export your package.</span></span>
1. <span data-ttu-id="d6ab2-197">Connettere HoloLens e copiare il file con estensione ppkg nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-197">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="d6ab2-198">In HoloLens, applicare il VPN. ppkg aprendo il menu Start e selezionando l'opzione **Impostazioni**  ->  **Account**  ->  **Accedi all’azienda o all’istituto di istruzione** ->  **Aggiungi o rimuovi il pacchetto di provisioning** -> Seleziona pacchetto VPN.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-198">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="d6ab2-199">Configurazione di VPN tramite Intune</span><span class="sxs-lookup"><span data-stu-id="d6ab2-199">Setting up VPN via Intune</span></span>
<span data-ttu-id="d6ab2-200">Basta seguire i documenti di Intune per iniziare.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-200">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="d6ab2-201">Quando si seguono questi passaggi, tenere presente i protocolli VPN integrati supportati dai dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-201">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="d6ab2-202">[Creare profili VPN per la connessione ai server VPN in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-202">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="d6ab2-203">[Impostazioni del dispositivo Windows 10 e Windows Holographic per l'aggiunta di connessioni VPN tramite Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-203">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="d6ab2-204">Al termine, ricordarsi di [assegnare il profilo](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-204">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="d6ab2-205">VPN tramite soluzioni MDM di terze parti</span><span class="sxs-lookup"><span data-stu-id="d6ab2-205">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="d6ab2-206">Esempio di connessione VPN di terze parti:</span><span class="sxs-lookup"><span data-stu-id="d6ab2-206">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="d6ab2-207">Esempio di VPN IKEv2 nativo:</span><span class="sxs-lookup"><span data-stu-id="d6ab2-207">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="d6ab2-208">Disabilitazione della rete Wi-Fi in HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="d6ab2-208">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="d6ab2-209">Uso dell'app Impostazioni in HoloLens</span><span class="sxs-lookup"><span data-stu-id="d6ab2-209">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="d6ab2-210">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-210">Open the **Start** menu.</span></span>
1. <span data-ttu-id="d6ab2-211">Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-211">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="d6ab2-212">L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-212">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="d6ab2-213">Seleziona **Rete e Internet**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-213">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="d6ab2-214">Seleziona il dispositivo di scorrimento Wi-Fi per spostarlo nella posizione **Off**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-214">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="d6ab2-215">I componenti RF della radio Wi-Fi verranno disattivati e tutte le funzionalità Wi-Fi in HoloLens verranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-215">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="d6ab2-216">Quando la radio Wi-Fi è disabilitata, HoloLens non sarà in grado di caricare automaticamente gli [spazi](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-216">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="d6ab2-217">Sposta il dispositivo di scorrimento sulla posizione **Attivato** per attivare la radio Wi-Fi e ripristinare la funzionalità Wi-Fi su Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-217">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="d6ab2-218">Lo stato della radio Wi-Fi selezionato (**Attivato** o **Disattivato**) verrà mantenuto a ogni riavvio.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-218">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="d6ab2-219">Identificazione dell'indirizzo IP di HoloLens nella rete Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d6ab2-219">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="d6ab2-220">Usando l'app Impostazioni</span><span class="sxs-lookup"><span data-stu-id="d6ab2-220">By using the Settings app</span></span>

1. <span data-ttu-id="d6ab2-221">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-221">Open the **Start** menu.</span></span>
1. <span data-ttu-id="d6ab2-222">Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-222">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="d6ab2-223">L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-223">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="d6ab2-224">Seleziona **Rete e Internet**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-224">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="d6ab2-225">Scorri in basso verso la fine dell'elenco delle reti Wi-Fi disponibili e seleziona **Proprietà hardware**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-225">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Proprietà hardware nelle impostazioni Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="d6ab2-227">L'indirizzo IP viene visualizzato accanto all'**indirizzo IPv4**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-227">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="d6ab2-228">Tramite i comandi vocali</span><span class="sxs-lookup"><span data-stu-id="d6ab2-228">By using voice commands</span></span>

<span data-ttu-id="d6ab2-229">A seconda del tipo di dispositivo in uso, è possibile usare il comando vocale predefinito o Cortana per visualizzare l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-229">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="d6ab2-230">Nelle build successive a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) dire "Qual è il mio indirizzo IP?"</span><span class="sxs-lookup"><span data-stu-id="d6ab2-230">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="d6ab2-231">e verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-231">and it will be displayed.</span></span> <span data-ttu-id="d6ab2-232">Per le build precedenti o per HoloLens (prima generazione) dire "Ehi Cortana, qual è il mio indirizzo IP?"</span><span class="sxs-lookup"><span data-stu-id="d6ab2-232">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="d6ab2-233">e Cortana visualizzerà e leggerà l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-233">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="d6ab2-234">Usando il Portale di dispositivi di Windows</span><span class="sxs-lookup"><span data-stu-id="d6ab2-234">By using Windows Device Portal</span></span>

1. <span data-ttu-id="d6ab2-235">In un Web browser nel PC apri il [portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="d6ab2-235">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="d6ab2-236">Passa alla sezione **Reti**.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-236">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="d6ab2-237">In questa sezione vengono visualizzati l'indirizzo IP e altre informazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-237">This section displays your IP address and other network information.</span></span> <span data-ttu-id="d6ab2-238">Usando questo metodo, potrai copiare e incollare l'indirizzo IP nel PC di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="d6ab2-238">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
