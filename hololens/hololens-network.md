---
title: Connessione HoloLens a una rete
description: Informazioni su come configurare e connettersi a Internet con HoloLens e su come identificare l'indirizzo IP del dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, wireless, internet, ip, indirizzo IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640220"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="3f6c6-104">Connessione HoloLens a una rete</span><span class="sxs-lookup"><span data-stu-id="3f6c6-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="3f6c6-105">Per eseguire la maggior parte delle HoloLens, è necessario essere connessi a una rete.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="3f6c6-106">HoloLens contiene una radio Wi-Fi 2x2 con funzionalità 802.11ac e la connessione a una rete è simile alla connessione di un dispositivo Windows 10 Desktop o Mobile a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="3f6c6-107">Questa guida consente di:</span><span class="sxs-lookup"><span data-stu-id="3f6c6-107">This guide will help you:</span></span>

- <span data-ttu-id="3f6c6-108">Connessione a una rete tramite Wi-Fi o solo per HoloLens 2, Wi-Fi Direct o Ethernet su USB-C</span><span class="sxs-lookup"><span data-stu-id="3f6c6-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="3f6c6-109">Disabilitare e riattivare Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3f6c6-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="3f6c6-110">Altre informazioni [sull'uso HoloLens offline.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="3f6c6-111">Connessione per la prima volta</span><span class="sxs-lookup"><span data-stu-id="3f6c6-111">Connecting for the first time</span></span>

<span data-ttu-id="3f6c6-112">La prima volta che usi HoloLens, dovrai seguire le istruzioni per la connessione a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="3f6c6-113">Se si verificano problemi di connessione a Wi-Fi durante l'installazione, assicurarsi che la rete sia aperta e protetta da password o captive portal rete.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="3f6c6-114">Verificare anche che la rete non richieda l'uso di un certificato per la connessione.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="3f6c6-115">Dopo l'installazione, è possibile connettersi ad altri tipi di Wi-Fi rete.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="3f6c6-116">Nei HoloLens 2 un utente può anche usare un adattatore [USB-C per Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) per connettersi direttamente a Wi-Fi per facilitare la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="3f6c6-117">Dopo aver configurato il dispositivo, un utente può continuare a usare l'adattatore oppure disconnettere il dispositivo dall'adattatore e connettersi al [Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)dopo aver configurato .</span><span class="sxs-lookup"><span data-stu-id="3f6c6-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="3f6c6-118">Connessione a un Wi-Fi dopo l'installazione</span><span class="sxs-lookup"><span data-stu-id="3f6c6-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="3f6c6-119">Preformare **il movimento Start** e selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="3f6c6-120">L Impostazioni app verrà posizionata automaticamente davanti all'utente.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3f6c6-121">Selezionare **Rete &**  >  **Wi-Fi Internet.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="3f6c6-122">Assicurarsi che Wi-Fi sia attivata.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="3f6c6-123">Se la rete non è visualizzata, scorrere l'elenco verso il basso.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="3f6c6-124">Selezionare una rete, quindi selezionare **Connessione**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="3f6c6-125">Se viene richiesta una password di rete, digitarla e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi impostazioni](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="3f6c6-127">Per verificare di essere connessi a una rete Wi-Fi, controllare lo Wi-Fi stato nel menu **Start:**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="3f6c6-128">Aprire il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3f6c6-129">Esaminare l'angolo in alto a sinistra del menu **Start** per Wi-Fi stato.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="3f6c6-130">Verranno visualizzati lo Wi-Fi e l'SSID della rete connessa.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="3f6c6-131">Se Wi-Fi non è disponibile, è anche possibile [connettersi alle reti cellulare e 5G.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f6c6-132">Per impostazione predefinita, gli utenti non possono ottimizzare il comportamento di roaming Wi-Fi del HoloLens 2. L'unico modo per aggiornare l'elenco di Wi-Fi è attivare o disattivare **Wi-Fi.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="3f6c6-133">In questo modo si evitano molti problemi, ad esempio quando un dispositivo può rimanere "bloccato" in un punto di accesso quando non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="3f6c6-134">Connessione HoloLens a Enterprise Wi-Fi rete</span><span class="sxs-lookup"><span data-stu-id="3f6c6-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="3f6c6-135">Enterprise Wi-Fi profili usano il protocollo EAP (Extensible Authentication Protocol) per autenticare Wi-Fi connessioni.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="3f6c6-136">HoloLens Enterprise Wi-Fi profilo può essere configurato tramite MDM o il pacchetto di provisioning creato da [Windows Progettazione configurazione](/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="3f6c6-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="3f6c6-137">Per Microsoft Intune dispositivo gestito, vedere [Intune per istruzioni](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-137">For Microsoft Intune managed device, refer to [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="3f6c6-138">Per creare un pacchetto di provisioning Wi-Fi in WCD, è necessario un file Wi-Fi profilo .xml preconfigurato.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="3f6c6-139">Di seguito è riportato un profilo Wi-Fi di esempio WPA2-Enterprise con l'autenticazione EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="3f6c6-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="3f6c6-140">Potrebbe essere necessario effettuare il provisioning del certificato CA radice del server e del certificato client nel dispositivo a seconda del tipo EAP.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="3f6c6-141">Risorse aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="3f6c6-141">Additional resources:</span></span>

- <span data-ttu-id="3f6c6-142">Schema WLANv1Profile: [[MS-GPWL]: Profilo LAN wireless v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="3f6c6-143">Schema EAP-TLS: [[MS-GPWL]: Schema TLS Microsoft EAP | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="3f6c6-144">Se si [verificano](hololens2-enterprise-troubleshooting.md#) problemi di connessione al Wi-Fi, vedere la pagina Risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="3f6c6-145">Configurare il proxy di rete</span><span class="sxs-lookup"><span data-stu-id="3f6c6-145">Configure Network Proxy</span></span>

<span data-ttu-id="3f6c6-146">Questa sezione illustra il proxy di rete per HoloLens app del sistema operativo e della piattaforma UWP (Universal Windows Platform) usando Windows stack HTTP.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="3f6c6-147">Le applicazioni che usano Windows stack HTTP possono avere la propria configurazione e gestione del proxy.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="3f6c6-148">Configurazioni proxy</span><span class="sxs-lookup"><span data-stu-id="3f6c6-148">Proxy Configurations</span></span> 

- <span data-ttu-id="3f6c6-149">Script di configurazione automatica del proxy: un [file PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (apre un sito non Microsoft) contiene una funzione JavaScript FindProxyForURL(url, host).</span><span class="sxs-lookup"><span data-stu-id="3f6c6-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="3f6c6-150">Proxy statico: nel formato Server:Porta.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="3f6c6-151">Web Proxy Auto-Discovery Protocol (WPAD): specificare l'URL del file di configurazione del proxy tramite DHCP o DNS.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="3f6c6-152">Metodi di provisioning proxy</span><span class="sxs-lookup"><span data-stu-id="3f6c6-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="3f6c6-153">Esistono tre modi per effettuare il provisioning dei proxy:</span><span class="sxs-lookup"><span data-stu-id="3f6c6-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="3f6c6-154">**Impostazioni Ui:**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="3f6c6-155">Proxy per utente (20H2 o versioni precedenti):</span><span class="sxs-lookup"><span data-stu-id="3f6c6-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="3f6c6-156">Aprire il menu Start e selezionare Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="3f6c6-157">Selezionare Rete & Internet e quindi Proxy nel menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="3f6c6-158">Scorrere verso il basso fino a Manual proxy setup (Configurazione manuale del proxy) e impostare Use a proxy server (Usa un server proxy) su On (Attiva).</span><span class="sxs-lookup"><span data-stu-id="3f6c6-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="3f6c6-159">Immettere l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="3f6c6-160">Immettere il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-160">Enter the port number.</span></span>
        6. <span data-ttu-id="3f6c6-161">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-161">Click Save.</span></span>
      1. <span data-ttu-id="3f6c6-162">Proxy Wi-Fi (21H1 o superiore):</span><span class="sxs-lookup"><span data-stu-id="3f6c6-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="3f6c6-163">Aprire il menu Start e passare alla Wi-Fi proprietà della rete virtuale.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="3f6c6-164">Scorrere verso il basso fino a Proxy</span><span class="sxs-lookup"><span data-stu-id="3f6c6-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="3f6c6-165">Passare all'installazione manuale</span><span class="sxs-lookup"><span data-stu-id="3f6c6-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="3f6c6-166">Immettere l'indirizzo IP del server proxy.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="3f6c6-167">Immettere il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-167">Enter the port number.</span></span>
          1. <span data-ttu-id="3f6c6-168">Fare clic su Applica.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="3f6c6-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-169">**MDM**</span></span> 
     1. <span data-ttu-id="3f6c6-170">Intune: seguire questa [procedura per](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) configurare il proxy in Intune.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-170">Intune - Use these [steps](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="3f6c6-171">È necessario scorrere fino alla fine della sezione.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="3f6c6-172">Altre soluzioni MDM di terze parti: usare un provider di servizi di configurazione [WiFi.](/windows/client-management/mdm/wifi-csp)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-172">Other 3rd party MDM solutions - Use a [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="3f6c6-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-173">**PPKG**</span></span> 
    1. <span data-ttu-id="3f6c6-174">Aprire Progettazione Windows configurazione</span><span class="sxs-lookup"><span data-stu-id="3f6c6-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="3f6c6-175">Fare clic su Provisioning avanzato, immettere il nome del nuovo Project fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="3f6c6-176">Selezionare Windows olografico (HoloLens 2) e fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="3f6c6-177">Importare il file PPKG (facoltativo) e fare clic su Fine.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="3f6c6-178">Espandere Runtime Impostazioni -> Connectivity Profiles -> WLAN -> WLAN Proxy .</span><span class="sxs-lookup"><span data-stu-id="3f6c6-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="3f6c6-179">Immettere l'SSID della rete Wi-Fi e fare clic su Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="3f6c6-180">Selezionare la Wi-Fi rete virtuale nella finestra a sinistra e immettere le personalizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="3f6c6-181">Le personalizzazioni abilitate verranno mostrate in grassetto nel menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="3f6c6-182">Fare clic su Salva ed esci.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="3f6c6-183">[Applicare](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) il pacchetto di provisioning al HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="3f6c6-184">[I provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) di servizi cloud sono alla base di molte delle attività e dei criteri di gestione per Windows 10, sia in Microsoft Intune che nei provider di servizi MDM non Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="3f6c6-185">È anche possibile usare [Windows Progettazione configurazione per](/windows/configuration/provisioning-packages/provisioning-install-icd) creare un pacchetto di [provisioning](/windows/configuration/provisioning-packages/provisioning-packages) e applicarlo al HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-185">You can also use [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="3f6c6-186">I CSP più probabili che verranno applicati al HoloLens 2 sono:</span><span class="sxs-lookup"><span data-stu-id="3f6c6-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="3f6c6-187">[Provider di servizi di configurazione Wi-Fi:](/windows/client-management/mdm/wifi-csp)proxy Wi-Fi profilo</span><span class="sxs-lookup"><span data-stu-id="3f6c6-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="3f6c6-188">Altri CSP supportati nei HoloLens mobili</span><span class="sxs-lookup"><span data-stu-id="3f6c6-188">Other CSPs supported in HoloLens devices</span></span>](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="3f6c6-189">Connessione</span><span class="sxs-lookup"><span data-stu-id="3f6c6-189">VPN</span></span>
<span data-ttu-id="3f6c6-190">Una connessione VPN consente di fornire una connessione più sicura e l'accesso alla rete aziendale e a Internet.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="3f6c6-191">HoloLens 2 supporta il client VPN predefinito e il plug-in VPN UWP (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="3f6c6-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="3f6c6-192">Protocolli VPN predefiniti supportati:</span><span class="sxs-lookup"><span data-stu-id="3f6c6-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="3f6c6-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="3f6c6-193">IKEv2</span></span>
- <span data-ttu-id="3f6c6-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="3f6c6-194">L2TP</span></span>
- <span data-ttu-id="3f6c6-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="3f6c6-195">PPTP</span></span>

<span data-ttu-id="3f6c6-196">Se il certificato viene usato per l'autenticazione per il client VPN predefinito, il certificato client richiesto deve essere aggiunto all'archivio certificati utente.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="3f6c6-197">Per verificare se un plug-in VPN di terze parti supporta HoloLens 2, passare a Store per individuare l'app VPN e verificare se HoloLens è elencato come dispositivo supportato e nella pagina Requisiti di sistema l'app supporta l'architettura ARM o ARM64.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="3f6c6-198">HoloLens supporta solo applicazioni Universal Windows Platform per VPN di terze parti.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="3f6c6-199">La VPN può essere gestita da MDM [tramite Impostazioni/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)e impostata tramite [il criterio Vpnv2-csp](/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="3f6c6-199">VPN can be managed by MDM via [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="3f6c6-200">Altre informazioni su [come configurare la VPN con](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) queste [guide.](/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="3f6c6-201">VPN tramite interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="3f6c6-201">VPN via UI</span></span>

<span data-ttu-id="3f6c6-202">La VPN non è abilitata per impostazione predefinita, ma può essere abilitata manualmente aprendo l'app Impostazioni e passando **a** **Rete & Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="3f6c6-203">Selezionare un provider VPN.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="3f6c6-204">Creare un nome di connessione.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-204">Create a connection name.</span></span> 
1. <span data-ttu-id="3f6c6-205">Immettere il nome o l'indirizzo del server.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="3f6c6-206">Selezionare il tipo di VPN.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-206">Select the VPN type.</span></span>
1. <span data-ttu-id="3f6c6-207">Selezionare il tipo di informazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="3f6c6-208">Facoltativamente, aggiungere il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="3f6c6-209">Applicare le impostazioni VPN.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-209">Apply the VPN settings.</span></span> 

![HoloLens Impostazioni VPN](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="3f6c6-211">Set VPN tramite pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="3f6c6-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="3f6c6-212">Nel nostro Windows Holographic versione 20H2 è stato risolto un problema di configurazione del proxy per la connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="3f6c6-213">Se si intende usare questo flusso, è consigliabile aggiornare i dispositivi a questa build.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="3f6c6-214">Avviare Windows Progettazione configurazione.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="3f6c6-215">Fare **clic su Provisioning HoloLens dispositivi,** quindi selezionare dispositivo di destinazione e **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="3f6c6-216">Immettere il nome e il percorso del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-216">Enter package name and path.</span></span>
1. <span data-ttu-id="3f6c6-217">Fare **clic su Passa all'editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="3f6c6-218">Aprire **Impostazioni di runtime**  ->  **ConnettivitàProfili**  ->    ->  **VPNImpostazioni VPN**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="3f6c6-219">Configurare VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="3f6c6-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="3f6c6-220">Selezionare ProfileType: **Nativo** **o Di terze parti.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="3f6c6-221">Per Profilo nativo selezionare **NativeProtocolType,** quindi configurare il server, i criteri di routing, il tipo di autenticazione e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="3f6c6-222">Per il profilo "Di terze parti", configurare l'URL del server, il nome della famiglia di pacchetti dell'app plug-in VPN (solo 3 predefiniti) e le configurazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="3f6c6-223">Esportare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-223">Export your package.</span></span>
1. <span data-ttu-id="3f6c6-224">Connessione il HoloLens copiare il file con estensione ppkg nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="3f6c6-225">Nella HoloLens applicare il file ppkg VPN aprendo il menu Start e selezionando Impostazioni Account Access work  ->    ->  **or school** Add or remove provisioning package -> Select your VPN package (Aggiungi o rimuovi pacchetto di  ->  **provisioning** -> Selezionare il pacchetto VPN).</span><span class="sxs-lookup"><span data-stu-id="3f6c6-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="3f6c6-226">Configurazione della VPN tramite Intune</span><span class="sxs-lookup"><span data-stu-id="3f6c6-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="3f6c6-227">Per iniziare, seguire i documenti di Intune.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="3f6c6-228">Quando si segue questa procedura, tenere presenti i protocolli VPN predefiniti supportati HoloLens dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="3f6c6-229">[Creare profili VPN per connettersi ai server VPN in Intune.](/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-229">[Create VPN profiles to connect to VPN servers in Intune](/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="3f6c6-230">[Windows 10 e Windows impostazioni del dispositivo Holographic per aggiungere connessioni VPN tramite Intune.](/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="3f6c6-231">Al termine, ricordarsi di [assegnare il profilo](/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="3f6c6-231">When done please remember to [assign the profile](/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="3f6c6-232">VPN tramite soluzioni MDM di terze parti</span><span class="sxs-lookup"><span data-stu-id="3f6c6-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="3f6c6-233">Esempio di connessione VPN di terze parti:</span><span class="sxs-lookup"><span data-stu-id="3f6c6-233">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="3f6c6-234">Esempio di VPN IKEv2 nativa:</span><span class="sxs-lookup"><span data-stu-id="3f6c6-234">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="3f6c6-235">Disabilitazione Wi-Fi in HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="3f6c6-236">Uso dell'app Impostazioni in HoloLens</span><span class="sxs-lookup"><span data-stu-id="3f6c6-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="3f6c6-237">Aprire il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3f6c6-238">Selezionare **l Impostazioni app** da **Start** o dall'elenco **Tutte** le app a destra del menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="3f6c6-239">**L Impostazioni app** verrà posizionata automaticamente davanti all'utente.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3f6c6-240">Selezionare **Rete & Internet**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="3f6c6-241">Selezionare lWi-Fi del dispositivo di scorrimento per spostarlo nella **posizione Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="3f6c6-242">Verranno disattivati i componenti RF della radio Wi-Fi e verranno disabilitate tutte Wi-Fi funzionalità HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="3f6c6-243">Quando la Wi-Fi radio è disabilitata, HoloLens non sarà in grado di caricare automaticamente gli [spazi](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="3f6c6-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="3f6c6-244">Spostare l'interruttore **del** dispositivo di scorrimento sulla posizione On per attivare la radio Wi-Fi e ripristinare Wi-Fi funzionalità Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="3f6c6-245">Lo stato Wi-Fi radio selezionato (**On** o **Off**) verrà mantenuto tra i riavvii.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="3f6c6-246">Identificazione dell'indirizzo IP del HoloLens nella rete Wi-Fi rete</span><span class="sxs-lookup"><span data-stu-id="3f6c6-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="3f6c6-247">Usando l'app Impostazioni app</span><span class="sxs-lookup"><span data-stu-id="3f6c6-247">By using the Settings app</span></span>

1. <span data-ttu-id="3f6c6-248">Aprire il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3f6c6-249">Selezionare **l Impostazioni app** da **Start** o dall'elenco **Tutte** le app a destra del menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="3f6c6-250">**L Impostazioni app** verrà posizionata automaticamente davanti all'utente.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3f6c6-251">Selezionare **Rete & Internet**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="3f6c6-252">Scorrere verso il basso fino a sotto l'elenco delle reti Wi-Fi e selezionare **Proprietà hardware**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Proprietà hardware nelle impostazioni Wi-Fi hardware](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="3f6c6-254">L'indirizzo IP viene visualizzato accanto **all'indirizzo IPv4.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="3f6c6-255">Usando i comandi vocali</span><span class="sxs-lookup"><span data-stu-id="3f6c6-255">By using voice commands</span></span>

<span data-ttu-id="3f6c6-256">A seconda della compilazione dei dispositivi, è possibile usare comandi vocali predefiniti o Cortana visualizzare l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="3f6c6-257">Nelle build dopo [la versione 19041.1103](hololens-release-notes.md#windows-holographic-version-2004) pronunciare "Qual è l'indirizzo IP?"</span><span class="sxs-lookup"><span data-stu-id="3f6c6-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="3f6c6-258">e verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-258">and it will be displayed.</span></span> <span data-ttu-id="3f6c6-259">Per le build precedenti o HoloLens (prima generazione) pronunciare "Hey Cortana, What's my IP address?"</span><span class="sxs-lookup"><span data-stu-id="3f6c6-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="3f6c6-260">e Cortana visualizzare e leggere l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="3f6c6-261">Usando Windows Portale di dispositivi</span><span class="sxs-lookup"><span data-stu-id="3f6c6-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="3f6c6-262">In un Web browser nel PC aprire il portale [dei dispositivi.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="3f6c6-263">Passare alla **sezione Rete.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="3f6c6-264">In questa sezione vengono visualizzati l'indirizzo IP e altre informazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="3f6c6-265">Usando questo metodo, è possibile copiare e incollare l'indirizzo IP nel PC di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="3f6c6-266">Modificare l'indirizzo IP in indirizzo statico</span><span class="sxs-lookup"><span data-stu-id="3f6c6-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="3f6c6-267">Usando Impostazioni</span><span class="sxs-lookup"><span data-stu-id="3f6c6-267">By using Settings</span></span>
 
1. <span data-ttu-id="3f6c6-268">Aprire il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3f6c6-269">Selezionare **l Impostazioni app** da **Start** o dall'elenco **Tutte** le app a destra del menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="3f6c6-270">**L Impostazioni app** verrà posizionata automaticamente davanti all'utente.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3f6c6-271">Selezionare **Rete & Internet**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="3f6c6-272">Scorrere verso il basso fino a sotto l'elenco delle reti Wi-Fi e selezionare **Proprietà hardware**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="3f6c6-273">Nella finestra **Modifica impostazioni IP** modificare il primo campo in **Manuale.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="3f6c6-274">Immettere la configurazione IP desiderata nei campi rimanenti e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="3f6c6-275">Usando Windows Portale di dispositivi</span><span class="sxs-lookup"><span data-stu-id="3f6c6-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="3f6c6-276">In un Web browser nel PC aprire il portale [dei dispositivi.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="3f6c6-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="3f6c6-277">Passare alla **sezione Rete.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="3f6c6-278">Selezionare il **pulsante Configurazione IPv4.**</span><span class="sxs-lookup"><span data-stu-id="3f6c6-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="3f6c6-279">Selezionare **Usa l'indirizzo IP seguente e** immettere la configurazione TCP/IP desiderata.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="3f6c6-280">Selezionare **Usa gli indirizzi del server DNS seguenti** e immettere gli indirizzi del server DNS preferito e alternativo, se necessario.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="3f6c6-281">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3f6c6-281">Click **Save**.</span></span> 
