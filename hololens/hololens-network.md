---
title: Connettere HoloLens a una rete
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
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923602"
---
# <a name="connect-hololens-to-a-network"></a>Connettere HoloLens a una rete

Per eseguire la maggior parte delle operazioni in HoloLens, devi essere connesso a una rete. HoloLens contiene una radio Wi-Fi 2x2 con funzionalità 802.11ac e la connessione a una rete è simile alla connessione di un dispositivo Windows 10 Desktop o Mobile a una rete Wi-Fi. Questa guida consente di:

- Connettersi a una rete tramite Wi-Fi o solo per HoloLens 2, Wi-Fi Direct o Ethernet su USB-C
- Disabilitare e riattivare Wi-Fi

Altre informazioni [sull'uso di HoloLens offline.](hololens-offline.md)

## <a name="connecting-for-the-first-time"></a>Connessione per la prima volta

La prima volta che usi HoloLens, dovrai seguire le istruzioni per la connessione a una rete Wi-Fi. Se si verificano problemi di connessione a Wi-Fi durante l'installazione, assicurarsi che la rete sia aperta e protetta da password o captive portal rete. Verificare anche che la rete non richieda l'uso di un certificato per la connessione. Dopo l'installazione, è possibile connettersi ad altri tipi di Wi-Fi rete.

Nei HoloLens 2 un utente può anche usare un adattatore [DA USB-C a Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) per connettersi direttamente a Wi-Fi per facilitare la configurazione del dispositivo. Dopo aver configurato il dispositivo, un utente può continuare a usare l'adattatore oppure disconnettere il dispositivo dall'adattatore e connettersi al [Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)dopo aver configurato . 

## <a name="connecting-to-wi-fi-after-setup"></a>Connessione a un Wi-Fi dopo l'installazione

1. Preform the **Start gesture (Preform the Start gesture)** (Preforma il movimento Start) e **selezionare Settings (Impostazioni).** L'app Impostazioni verrà posizionata automaticamente davanti all'utente.
1. Selezionare **Rete &**  >  **Wi-Fi Internet.** Assicurarsi che Wi-Fi sia attivata. Se la rete non è visualizzata, scorrere verso il basso nell'elenco.
1. Selezionare una rete, quindi selezionare **Connetti.**
1. Se viene richiesta una password di rete, digitarla e quindi selezionare **Avanti.**

![Impostazioni Wi-Fi HoloLens](./images/hololens-2-wifi-settings.jpg)

Per verificare di essere connessi a una rete Wi-Fi, controllare lo Wi-Fi stato nel menu **Start:**

1. Aprire il menu **Start**.
1. Esaminare l'angolo in alto a sinistra del menu **Start** per Wi-Fi stato. Verranno visualizzati lo Wi-Fi e l'SSID della rete connessa.

> [!TIP]
> Se Wi-Fi non è disponibile, è anche possibile [connettersi alle reti cellulare e 5G.](hololens-cellular.md)

> [!IMPORTANT]
> Per impostazione predefinita, gli utenti non possono ottimizzare il comportamento di roaming Wi-Fi del HoloLens 2. L'unico modo per aggiornare l'elenco di Wi-Fi è attivare o disattivare **Wi-Fi.** In questo modo si evitano molti problemi, ad esempio quando un dispositivo può rimanere "bloccato" in un punto di accesso quando non è compreso nell'intervallo.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Connettere HoloLens a Enterprise Wi-Fi Network

I Wi-Fi enterprise usano il protocollo EAP (Extensible Authentication Protocol) per autenticare Wi-Fi connessioni. Il profilo di Wi-Fi HoloLens Enterprise può essere configurato tramite MDM o il pacchetto di provisioning creato da [Progettazione configurazione di Windows.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

Per Microsoft Intune dispositivo gestito, vedere [Intune per istruzioni](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) di configurazione.

Per creare un pacchetto di provisioning Wi-Fi in WCD, è necessario un file Wi-Fi profilo .xml preconfigurato. Di seguito è riportato un profilo Wi-Fi di esempio WPA2-Enterprise con l'autenticazione EAP-TLS:

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


Potrebbe essere necessario effettuare il provisioning del certificato CA radice del server e del certificato client nel dispositivo a seconda del tipo EAP.

Risorse aggiuntive:

- Schema WLANv1Profile: [[MS-GPWL]: Profilo LAN wireless v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Schema EAP-TLS: [[MS-GPWL]: Schema TLS Microsoft EAP | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Se si [verificano](hololens2-enterprise-troubleshooting.md#) problemi di connessione al Wi-Fi, vedere la pagina Risoluzione dei problemi.

## <a name="configure-network-proxy"></a>Configurare il proxy di rete

Questa sezione illustra il proxy di rete per il sistema operativo HoloLens e le app piattaforma UWP (Universal Windows Platform) (UWP) che usano lo stack HTTP di Windows. Le applicazioni che usano stack HTTP non Windows possono avere la propria configurazione e gestione del proxy. 

### <a name="proxy-configurations"></a>Configurazioni proxy 

- Script di configurazione automatica del proxy: un [file PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (apre un sito non Microsoft) contiene una funzione JavaScript FindProxyForURL(url, host). 
- Proxy statico: nel formato Server:Porta.  
- Web Proxy Auto-Discovery Protocol (WPAD): specificare l'URL del file di configurazione del proxy tramite DHCP o DNS. 

### <a name="proxy-provisioning-methods"></a>Metodi di provisioning proxy 
Esistono tre modi per effettuare il provisioning dei proxy:

 

1.  **Interfaccia utente delle impostazioni:** 
    1. Proxy per utente (20H2 o versioni precedenti):
        1. Aprire il menu Start e selezionare Impostazioni.
        2. Selezionare Rete & Internet e quindi Proxy nel menu a sinistra.
        3. Scorrere verso il basso fino a Manual proxy setup (Configurazione manuale del proxy) e impostare Use a proxy server (Usa un server proxy) su On (Attiva).
        4. Immettere l'indirizzo IP del server proxy.
        5. Immettere il numero di porta.
        6. Fare clic su Salva.
      1. Proxy Wi-Fi (21H1 o superiore):
          1. Aprire il menu Start e passare alla Wi-Fi proprietà della rete virtuale.
          1. Scorrere verso il basso fino a Proxy
          1. Passare all'installazione manuale
          1. Immettere l'indirizzo IP del server proxy.
          1. Immettere il numero di porta.
          1. Fare clic su Applica.
        
 2. **MDM** 
     1. Intune: seguire questa [procedura per](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) configurare il proxy in Intune. È necessario scorrere fino alla fine della sezione.
     1. Altre soluzioni MDM di terze parti: usare un [provider di servizi di configurazione Wi-Fi.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)

3. **PPKG** 
    1. Aprire Progettazione configurazione di Windows
    1. Fare clic su Provisioning avanzato, immettere il nome del nuovo progetto e fare clic su Avanti.
    1. Selezionare Windows Holographic (HoloLens 2) e fare clic su Avanti.
    1. Importare il file PPKG (facoltativo) e fare clic su Fine.
    1. Espandere Impostazioni di runtime -> Connectivity Profiles -> WLAN -> WLAN Proxy.
    1. Immettere l'SSID della rete Wi-Fi e fare clic su Aggiungi.
    1. Selezionare la Wi-Fi rete virtuale nella finestra a sinistra e immettere le personalizzazioni desiderate. Le personalizzazioni abilitate verranno mostrate in grassetto nel menu a sinistra.
    1. Fare clic su Salva ed esci.
    1. [Applica](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) il pacchetto di provisioning a HoloLens.

[I provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) di servizi cloud sono alla base di molte delle attività e dei criteri di gestione per Windows 10, sia in Microsoft Intune che nei provider di servizi MDM non Microsoft. È anche possibile usare [Progettazione configurazione di Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) per creare un pacchetto di [provisioning](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) e applicarlo al HoloLens 2.
I CSP più probabili che verranno applicati al HoloLens 2 sono:

- [Provider di servizi di configurazione Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)proxy Wi-Fi profilo 

[Altri CSP supportati nei dispositivi HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>Connessione
Una connessione VPN consente di fornire una connessione più sicura e l'accesso alla rete aziendale e a Internet. HoloLens 2 supporta il client VPN predefinito e il plug-in VPN piattaforma UWP (Universal Windows Platform) (UWP). 

Protocolli VPN predefiniti supportati:
- IKEv2
- L2TP
- PPTP

Se il certificato viene usato per l'autenticazione per il client VPN predefinito, il certificato client richiesto deve essere aggiunto all'archivio certificati utente. Per verificare se un plug-in VPN di terze parti supporta HoloLens 2, passare a Store per individuare l'app VPN e verificare se HoloLens è elencato come dispositivo supportato e nella pagina Requisiti di sistema l'app supporta l'architettura ARM o ARM64. HoloLens supporta solo piattaforma UWP (Universal Windows Platform) applicazioni per VPN di terze parti.

 La VPN può essere gestita da MDM [tramite Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)e impostata tramite  [il criterio Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

Altre informazioni su [come configurare la VPN con](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) queste [guide.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)  

### <a name="vpn-via-ui"></a>VPN tramite interfaccia utente

La VPN non è abilitata per  impostazione predefinita, ma può essere abilitata manualmente aprendo l'app Impostazioni e passando **a Rete & Internet -> VPN**.
1. Selezionare un provider VPN.
1. Creare un nome di connessione. 
1. Immettere il nome o l'indirizzo del server.
1. Selezionare il tipo di VPN.
1. Selezionare il tipo di informazioni di accesso. 
1. Facoltativamente, aggiungere il nome utente e la password.
1. Applicare le impostazioni VPN. 

![Impostazioni VPN di HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Set VPN tramite pacchetto di provisioning

> [!TIP] 
> In Windows Holographic versione 20H2 è stato risolto un problema di configurazione del proxy per la connessione VPN. Se si intende usare questo flusso, è consigliabile aggiornare i dispositivi a questa build.

1. Avviare Progettazione configurazione Windows.
1. Fare **clic su Provisioning dispositivi HoloLens,** quindi selezionare dispositivo di destinazione e **Avanti.**
1. Immettere il nome e il percorso del pacchetto.
1. Fare **clic su Passa all'editor avanzato**.
1. Aprire **Impostazioni di runtime**  ->  **ConnettivitàProfili**  ->    ->  **VPNImpostazioni VPN**.
1. Configurare VPNProfileName
1. Selezionare ProfileType: **Nativo** **o Di terze parti.**
    1. Per Profilo nativo selezionare **NativeProtocolType,** quindi configurare il server, i criteri di routing, il tipo di autenticazione e altre impostazioni.
    1. Per il profilo "Di terze parti", configurare l'URL del server, il nome della famiglia di pacchetti dell'app plug-in VPN (solo 3 predefiniti) e le configurazioni personalizzate.
1. Esportare il pacchetto.
1. Connettere HoloLens e copiare il file con estensione ppkg nel dispositivo. 
1. In HoloLens applicare il file ppkg VPN aprendo il menu Start e selezionando Impostazioni Accesso account aziendale o dell'istituto di istruzione Aggiungere o rimuovere il pacchetto di  ->    ->    ->  **provisioning** -> Selezionare il pacchetto VPN.


### <a name="setting-up-vpn-via-intune"></a>Configurazione della VPN tramite Intune
Per iniziare, seguire i documenti di Intune. Quando si segue questa procedura, tenere presenti i protocolli VPN predefiniti supportati da dispositivi HoloLens. 

[Creare profili VPN per connettersi ai server VPN in Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)

[Windows 10 impostazioni del dispositivo Windows Holographic per aggiungere connessioni VPN con Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)

Al termine, ricordarsi di [assegnare il profilo](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN tramite soluzioni MDM di terze parti
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

Esempio di VPN IKEv2 nativa:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Disabilitazione Wi-Fi in HoloLens (prima generazione)

### <a name="using-the-settings-app-on-hololens"></a>Uso dell'app Impostazioni in HoloLens

1. Aprire il menu **Start**.
1. Selezionare **l'app** Impostazioni **da Start** o dall'elenco **Tutte** le app a destra del menu **Start.** **L'app** Impostazioni verrà posizionata automaticamente davanti all'utente.
1. Selezionare **Rete & Internet**.
1. Selezionare lWi-Fi del dispositivo di scorrimento per spostarlo nella **posizione Disattivato.** Verranno disattivati i componenti RF della radio Wi-Fi e verranno disabilitate tutte Wi-Fi funzionalità in HoloLens.

    > [!WARNING]
    > Quando la Wi-Fi radio è disabilitata, HoloLens non sarà in grado di caricare automaticamente gli [spazi.](hololens-spaces.md)

1. Spostare l'interruttore **del** dispositivo di scorrimento sulla posizione On per attivare la radio Wi-Fi e ripristinare Wi-Fi funzionalità Microsoft HoloLens. Lo stato Wi-Fi radio selezionato (**On** o **Off**) verrà mantenuto tra i riavvii.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identificazione dell'indirizzo IP di HoloLens nella Wi-Fi rete

### <a name="by-using-the-settings-app"></a>Usando l'app Impostazioni

1. Aprire il menu **Start**.
1. Selezionare **l'app** Impostazioni **da Start** o dall'elenco **Tutte** le app a destra del menu **Start.** **L'app** Impostazioni verrà posizionata automaticamente davanti all'utente.
1. Selezionare **Rete & Internet**.
1. Scorrere verso il basso fino a sotto l'elenco delle reti Wi-Fi e selezionare **Proprietà hardware**.

    ![Proprietà hardware nelle impostazioni Wi-Fi hardware](./images/wifi-hololens-hwdetails.jpg)

   L'indirizzo IP viene visualizzato accanto **all'indirizzo IPv4.**

### <a name="by-using-voice-commands"></a>Usando i comandi vocali

A seconda della compilazione dei dispositivi, è possibile usare i comandi vocali predefiniti o Cortana per visualizzare l'indirizzo IP. Nelle build dopo [la versione 19041.1103](hololens-release-notes.md#windows-holographic-version-2004) pronunciare "Qual è l'indirizzo IP?" e verrà visualizzato. Per le build precedenti o HoloLens (prima generazione) pronunciare "Hey Cortana, Qual è l'indirizzo IP?" e Cortana visualizzano e leggono l'indirizzo IP.

### <a name="by-using-windows-device-portal"></a>Usando Portale di dispositivi di Windows

1. In un Web browser nel PC aprire il portale [dei dispositivi.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Passare alla **sezione Rete.**  
   In questa sezione vengono visualizzati l'indirizzo IP e altre informazioni di rete. Usando questo metodo, è possibile copiare e incollare l'indirizzo IP nel PC di sviluppo.

## <a name="change-ip-address-to-static-address"></a>Modificare l'indirizzo IP in indirizzo statico
### <a name="by-using-settings"></a>Usando le impostazioni
 
1. Aprire il menu **Start**.
1. Selezionare **l'app** Impostazioni **da Start** o dall'elenco **Tutte** le app a destra del menu **Start.** **L'app** Impostazioni verrà posizionata automaticamente davanti all'utente.
1. Selezionare **Rete & Internet**.
1. Scorrere verso il basso fino a sotto l'elenco delle reti Wi-Fi e selezionare **Proprietà hardware**.
1. Nella finestra Edit IP settings (Modifica impostazioni **IP)** modificare il primo campo in **Manual (Manuale).**
1. Immettere la configurazione IP desiderata nei campi rimanenti e quindi fare clic su **Salva**.

### <a name="by-using-windows-device-portal"></a>Usando Portale di dispositivi di Windows

1. In un Web browser nel PC aprire il portale [dei dispositivi.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Passare alla **sezione Rete.**
1. Selezionare il **pulsante Configurazione IPv4.**
1. Selezionare **Usa l'indirizzo IP seguente e** immettere la configurazione TCP/IP desiderata.
1. Selezionare **Usa gli indirizzi del server DNS seguenti** e immettere gli indirizzi del server DNS preferito e alternativo, se necessario.
1. Fare clic su **Salva**. 
