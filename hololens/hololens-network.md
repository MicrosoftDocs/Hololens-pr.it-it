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
# Connettere HoloLens a una rete

Per eseguire la maggior parte delle operazioni in HoloLens, è necessario essere connessi a una rete. Questa guida ti aiuterà a:

- Connetterti a una rete tramite Wi-Fi o (solo per HoloLens 2) Ethernet tramite USB-C
- Disabilitare e riabilitare il Wi-Fi

Leggi altre informazioni sull'[uso di HoloLens offline](hololens-offline.md).

## Connessione per la prima volta

La prima volta che usi HoloLens, dovrai seguire le istruzioni per la connessione a una rete Wi-Fi. In caso di problemi di connessione a una rete Wi-Fi durante l'installazione, verifica che la rete sia aperta, protetta da password o captive portal. Verifica che la rete non richieda l'uso di un certificato per la connessione. Dopo la configurazione, potrai connetterti ad altri tipi di reti Wi-Fi.

Sui dispositivi HoloLens 2 un utente potrebbe anche [usare un adattatore USB-C per Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) per collegarsi direttamente al Wi-Fi e facilitare la configurazione del dispositivo. Dopo aver configurato il dispositivo, l'utente può continuare a usare l'adattatore, oppure potrebbe scollegare il dispositivo dalla scheda e [connettersi a una rete Wi-Fi dopo la configurazione](hololens-network.md#connecting-to-wi-fi-after-setup). 

## Connessione alla rete Wi-Fi dopo la configurazione

1. Eseguire il **gesto Start** e selezionare **Impostazioni**. L'app Impostazioni verrà posizionata automaticamente di fronte a te.
1. Seleziona **Rete e Internet** > **Wi-Fi**. Verifica che il Wi-Fi sia attivato. Se non vedi la tua rete, scorri in basso nell'elenco.
1. Seleziona una rete, quindi fai clic su **Connetti**.
1. Se viene richiesto di digitare una password di rete, inseriscila, quindi seleziona **Avanti**.

HoloLens contiene una radio Wi-Fi 2x2, con supporto di 802.11ac. La connessione di HoloLens a una rete Wi-Fi avviene in modo simile alla connessione di un dispositivo desktop o mobile Windows 10 a una rete Wi-Fi.

![Impostazioni Wi-Fi di HoloLens](./images/wifi-hololens-600px.jpg)

Puoi anche verificare che la connessione a una rete Wi-Fi sia stabilita, controllando lo stato Wi-Fi nel menu **Start**:

1. Apri il menu **Start**.
1. In alto a sinistra del menu **Start** controlla lo stato del Wi-Fi. Verranno visualizzati stato del Wi-Fi e SSID della rete connessa.

## Risoluzione dei problemi relativi alla connessione al Wi-Fi

Se si verificano problemi di connessione al Wi-Fi, vedere [Non riesco a connettermi al Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Quando si accede a un account aziendale o dell'organizzazione sul dispositivo, è possibile che vengano applicati anche criteri di gestione di dispositivi mobili (MDM), se i criteri sono configurati dall'amministratore IT.

## Connettere HoloLens a una rete Wi-Fi aziendale

I profili Wi-Fi aziendali usano il protocollo EAP (Extensible Authentication Protocol) per autenticare le connessioni Wi-Fi. Il profilo Wi-Fi aziendale HoloLens può essere configurato tramite MDM o pacchetto di provisioning creato tramite [Progettazione immagine e configurazione di Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).

Per il dispositivo gestito da Microsoft Intune, fare riferimento a [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) per le istruzioni di configurazione.

Per creare un pacchetto di provisioning Wi-Fi in WCD, è necessario un file .xml del profilo Wi-Fi preconfigurato. Di seguito è riportato un profilo Wi-Fi di esempio per WPA2-Enterprise con autenticazione EAP-TLS:

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


Potrebbe essere necessario eseguire il provisioning del certificato CA radice del server e del certificato client sul dispositivo a seconda del tipo di EAP.

Risorse aggiuntive:

- Schema WLANv1Profile: [[MS-GPWL]: Profilo Wireless LAN v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Schema EAP-TLS: [[MS-GPWL]: schema Microsoft EAP TLS | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

### Risoluzione dei problemi di EAP

1. Controllare che il profilo Wi-Fi abbia le giuste impostazioni:
   1. Il tipo di EAP è configurato correttamente, tipi di EAP comuni: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).
   1. Il nome Wi-Fi SSID è corretto e corrisponde alla stringa HEX.
   1. Per EAP-TLS, TrustedRootCA contiene l'hash SHA-1 del certificato CA radice attendibile del server&#39;s. Su PC Windows, il comando &quot;certutil.exe -dump cert\_file\_name&quot; mostrerà una stringa hash SHA-1 del certificato&#39;s.
1. Raccogliere acquisizioni di pacchetti di rete sui registri del server di punto di accesso, controller oppure AAA per comprendere dove non è riuscita la sessione EAP.
   1. Se l'identità EAP fornita da HoloLens non è prevista, controllare se il provisioning dell'identità è stato eseguito correttamente tramite il profilo Wi-Fi o il certificato client.
   1. Se il server rifiuta il certificato client HoloLens, controllare se il certificato client richiesto sia stato fornito nel dispositivo.
   1. Se HoloLens rifiuta il certificato del server, verificare se è stato eseguito il provisioning del certificato CA radice del server in HoloLens.
1. Se il profilo aziendale viene fornito tramite il pacchetto di provisioning Wi-Fi, è consigliabile l’applicazione del pacchetto di provisioning su un PC Windows 10. Se fallisce anche su PC Windows 10, seguire la [Guida alla risoluzione dei problemi di autenticazione 802.1X del client Windows](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).
1. Inviare feedback tramite [Hub di feedback](https://docs.microsoft.com/hololens/hololens-feedback).

### Risorse aggiuntive:
- [Esportare le impostazioni Wi-Fi da un dispositivo Windows](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## VPN
Una connessione VPN può essere utile per garantire una connessione più sicura e l'accesso alla rete aziendale e a Internet. HoloLens 2 supporta il client VPN predefinito e il plug-in VPN UWP (Universal Windows Platform). 

Protocolli VPN predefiniti supportati:
- IKEv2
- L2TP
- PPTP

Se il certificato viene usato per l'autenticazione per il client VPN predefinito, è necessario aggiungere il certificato client necessario all'archivio certificati utente. Per scoprire se un plug-in VPN di terze parti supporta HoloLens 2, passare allo Store per individuare l'app VPN e controllare se HoloLens compare tra i dispositivi supportati e se nella pagina dei requisiti di sistema l'app supporta l'architettura ARM o ARM64. HoloLens supporta solo le applicazioni della piattaforma UWP per la rete VPN di terze parti.

 La rete VPN può essere gestita da MDM tramite [Impostazioni/ConsentiVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) e impostata con il [criterio Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

Scoprire ulteriori informazioni su [come configurare la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [queste guide](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

### VPN tramite interfaccia utente

Per impostazione predefinita, la VPN non è abilitata, ma può essere abilitata manualmente aprendo l'app **Impostazioni**, quindi passando a **Rete e internet -> VPN**.
1. Selezionare un provider VPN.
1. Creare un nome di connessione. 
1. Immettere il nome o l'indirizzo del server.
1. Selezionare il tipo di VPN.
1. Selezionare il tipo di informazioni di accesso. 
1. Aggiungere facoltativamente il nome utente e la password.
1. Applicare le impostazioni VPN. 

![Impostazioni VPN di HoloLens](./images/vpn-settings-ui.jpg)

### VPN impostato tramite il pacchetto di provisioning

> [!TIP] 
> In Windows Holographic, versione 20H2 è stato risolto un problema di configurazione del proxy per la connessione VPN. Se si intende usare questo flusso, valutare l'aggiornamento dei dispositivi a questa build.

1. Avviare Progettazione immagine e configurazione di Windows.
1. Fare clic su **Effettua il provisioning dei dispositivi HoloLens**, quindi selezionare un dispositivo di destinazione ed infine **Avanti**.
1. Immettere il nome e il percorso del pacchetto.
1. Fare clic su **Passa a Editor avanzato**.
1. Aprire le **Impostazioni di runtime**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.
1. Configurare VPNProfileName
1. Selezionare ProfileType: **Nativo** o di **Terze parti**.
    1. Per profilo nativo, selezionare **NativeProtocolType**, quindi configurare server, criteri di routing, tipo di autenticazione e altre impostazioni.
    1. Per il profilo "Terze parti", configurare l'URL del server, il nome della famiglia di pacchetti dell'app plug-in VPN (solo 3 predefiniti) e le configurazioni personalizzate.
1. Esportare il pacchetto.
1. Connettere HoloLens e copiare il file con estensione ppkg nel dispositivo. 
1. In HoloLens, applicare il VPN. ppkg aprendo il menu Start e selezionando l'opzione **Impostazioni**  ->  **Account**  ->  **Accedi all’azienda o all’istituto di istruzione** ->  **Aggiungi o rimuovi il pacchetto di provisioning** -> Seleziona pacchetto VPN.


### Configurazione di VPN tramite Intune
Basta seguire i documenti di Intune per iniziare. Quando si seguono questi passaggi, tenere presente i protocolli VPN integrati supportati dai dispositivi HoloLens. 

[Creare profili VPN per la connessione ai server VPN in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).

[Impostazioni del dispositivo Windows 10 e Windows Holographic per l'aggiunta di connessioni VPN tramite Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).

Al termine, ricordarsi di [assegnare il profilo](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

### VPN tramite soluzioni MDM di terze parti
Esempio di connessione VPN di terze parti:
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

Esempio di VPN IKEv2 nativo:
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
## Disabilitazione della rete Wi-Fi in HoloLens (prima generazione)

### Uso dell'app Impostazioni in HoloLens

1. Apri il menu **Start**.
1. Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**. L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.
1. Seleziona **Rete e Internet**.
1. Seleziona il dispositivo di scorrimento Wi-Fi per spostarlo nella posizione **Off**. I componenti RF della radio Wi-Fi verranno disattivati e tutte le funzionalità Wi-Fi in HoloLens verranno disabilitate.

    > [!WARNING]
    > Quando la radio Wi-Fi è disabilitata, HoloLens non sarà in grado di caricare automaticamente gli [spazi](hololens-spaces.md).

1. Sposta il dispositivo di scorrimento sulla posizione **Attivato** per attivare la radio Wi-Fi e ripristinare la funzionalità Wi-Fi su Microsoft HoloLens. Lo stato della radio Wi-Fi selezionato (**Attivato** o **Disattivato**) verrà mantenuto a ogni riavvio.

## Identificazione dell'indirizzo IP di HoloLens nella rete Wi-Fi

### Usando l'app Impostazioni

1. Apri il menu **Start**.
1. Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**. L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.
1. Seleziona **Rete e Internet**.
1. Scorri in basso verso la fine dell'elenco delle reti Wi-Fi disponibili e seleziona **Proprietà hardware**.

    ![Proprietà hardware nelle impostazioni Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   L'indirizzo IP viene visualizzato accanto all'**indirizzo IPv4**.

### Tramite i comandi vocali

A seconda del tipo di dispositivo in uso, è possibile usare il comando vocale predefinito o Cortana per visualizzare l'indirizzo IP. Nelle build successive a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) dire "Qual è il mio indirizzo IP?" e verrà visualizzato. Per le build precedenti o per HoloLens (prima generazione) dire "Ehi Cortana, qual è il mio indirizzo IP?" e Cortana visualizzerà e leggerà l'indirizzo IP.

### Usando il Portale di dispositivi di Windows

1. In un Web browser nel PC apri il [portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Passa alla sezione **Reti**.  
   In questa sezione vengono visualizzati l'indirizzo IP e altre informazioni di rete. Usando questo metodo, potrai copiare e incollare l'indirizzo IP nel PC di sviluppo.
