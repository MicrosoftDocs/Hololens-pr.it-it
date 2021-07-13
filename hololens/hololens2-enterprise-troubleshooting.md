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
# <a name="troubleshooting-implementation-and-managed-devices"></a>Risoluzione dei problemi di implementazione e dispositivi gestiti 

Questo articolo descrive come risolvere diversi problemi o rispondere a domande relative all'implementazione e alla gestione HoloLens 2.

>[!IMPORTANT]
> Prima di iniziare qualsiasi procedura di risoluzione dei problemi, assicurarsi che il dispositivo venga addebitato al **20-40%** della capacità della batteria, se possibile. Le [luci indicatore della batteria](hololens2-setup.md#lights-that-indicate-the-battery-level) posizionate sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.


<a id="list"></a>
- [Risoluzione dei problemi EAP](#eap-troubleshooting)
- [Risoluzione dei problemi relativi al Wi-Fi](#wi-fi-troubleshooting)
- [Risoluzione dei problemi di rete](#network-troubleshooting)
- [Non è possibile accedere a un dispositivo di configurazione HoloLens precedente](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Non è possibile accedere dopo l'aggiornamento Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Risoluzione dei problemi di Autopilot](#autopilot-troubleshooting)
- [Domande frequenti HoloLens dispositivi gestiti](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Risoluzione dei problemi EAP
1. Verificare che Wi-Fi profilo abbia le impostazioni giuste:
    - Il tipo EAP è configurato correttamente, tipi EAP comuni: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).
    - Wi-Fi nome SSID è a destra e corrisponde alla stringa HEX.
    - Per EAP-TLS, TrustedRootCA contiene l'hash SHA-1 del certificato CA radice attendibile del server. Nel Windows PC "certutil.exe -dump cert_file_name" visualizza la stringa hash SHA-1 di un certificato.
2. Raccogliere l'acquisizione di pacchetti di rete nel punto di accesso, nel controller o nei log del server AAA per individuare la posizione in cui la sessione EAP ha esito negativo.
    - Se l'identità EAP fornita da HoloLens non è prevista, verificare se è stato eseguito correttamente il provisioning dell'identità tramite un profilo Wi-Fi o un certificato client.
    - Se il server rifiuta HoloLens certificato client, verificare se è stato effettuato il provisioning del certificato client richiesto nel dispositivo.
    - Se HoloLens rifiuta il certificato del server, verificare se è stato effettuato il provisioning del certificato CA radice del server HoloLens.
3. Se il provisioning del profilo aziendale viene effettuato tramite Wi-Fi di provisioning, è consigliabile applicare il pacchetto di provisioning in un PC Windows 10. Se si verifica un errore anche Windows 10 PC, seguire la guida alla risoluzione dei Windows di autenticazione 802.1X del client.
4. Inviare commenti e suggerimenti tramite Hub di Feedback.

[Torna all'elenco](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi risoluzione dei problemi

Di seguito sono riportati alcuni aspetti da provare se non è possibile connettere il HoloLens a una Wi-Fi rete:

1. Assicurarsi che la Wi-Fi sia attivata. Per verificare, usare il movimento Avvia, quindi selezionare Impostazioni > rete & Internet > Wi-Fi. Se Wi-Fi è attivata, provare a disattivarla e quindi ad attivarla di nuovo.
2. Spostarsi più vicino al router o al punto di accesso.
3. Riavviare il router Wi-Fi, quindi riavviare HoloLens. Provare a eseguire di nuovo la connessione.
4. Se nessuna di queste operazioni funziona, verificare che il router utilizzi il firmware più recente. Queste informazioni sono disponibili nel sito Web del produttore.

Quando si accede a un account aziendale o aziendale nel dispositivo, può anche essere applicato un criterio di gestione dei dispositivi mobili (MDM), se il criterio è configurato dall'amministratore IT.

[Torna all'elenco](#list)

## <a name="network-troubleshooting"></a>Risoluzione dei problemi di rete
Se i problemi di rete sono un ostacolo alla distribuzione e all'uso di HoloLens 2 nell'organizzazione, configurare Fiddler e/o Wireshark per acquisire e analizzare il traffico HTTP/HTTPS. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Configurare Fiddler per l'acquisizione del traffico HTTP
Fiddler è un proxy di debug Web e viene usato per risolvere i problemi relativi a HTTP(S). Acquisisce ogni richiesta HTTP che il computer effettua e registra tutti gli elementi associati. La ricerca di problemi di autenticazione dell'utente finale per le app HTTPS migliora la produttività e l'efficienza per i casi d'uso HoloLens 2 destinazione. 

#### <a name="prerequisites"></a>Prerequisiti
 
- HoloLens 2 dispositivi e il PC devono essere nella stessa rete
- Prendere nota dell'indirizzo IP del PC

#### <a name="install-and-configure-fiddler"></a>Installare e configurare Fiddler

1. Nel PC installare [e](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) avviare Fiddler.  
1. Nel PC configurare Fiddler per consentire ai computer remoti di connettersi.
    1. Passare a Fiddler Impostazioni -> Connessioni
    1. Si noti la porta di ascolto per Fiddler (il valore predefinito è 8866)
    1. Selezionare Consenti ai computer remoti di connettersi
    1. Fare clic su Salva.
3. Nel HoloLens 2 configurare Fiddler come server proxy<sup>1:</sup>
    1. Aprire il menu Start e selezionare Impostazioni
    1. Selezionare Rete & Internet e quindi Proxy nel menu a sinistra
    1. Scorrere verso il basso fino a Manual proxy setup (Configurazione manuale del proxy) e impostare Use a proxy server (Usa un server proxy) su On (Attiva)
    1. Immettere l'indirizzo IP del PC in cui è installato Fiddler
    1. Immettere il numero di porta indicato in precedenza (il valore predefinito è 8866)
    1. Fare clic su Salva.

<sup>1</sup> Per le build 20279.1006+ (Insider e la versione futura), seguire questa procedura per configurare il proxy:
1. Aprire il menu Start e passare alla pagina Wi-Fi proprietà della rete virtuale 
1. Scorrere verso il basso fino a Proxy
1. Passare all'installazione manuale
1. Immettere l'indirizzo IP del PC in cui è installato Fiddler
1. Immettere il numero di porta indicato in precedenza. (il valore predefinito è 8866)
1. Fare clic su Applica
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Decrittografare il traffico HTTPS HoloLens 2

1. Nel PC esportare il certificato di Fiddler.
    1. Passare a Fiddler Impostazioni -> HTTPS ed espandere Impostazioni
    2. Fare clic su Export Fiddler certificate (Esporta certificato Fiddler). Verrà salvato sul desktop
    3. Spostare il certificato nella cartella Download nel HoloLens 2

2.  Nel HoloLens 2 importare il certificato di Fiddler.
    1. Passare a Impostazioni -> aggiornamento e sicurezza -> certificati
    2. Fare clic su Installa certificato, passare alla cartella Download e selezionare il certificato Fiddler
    3. Modificare il percorso dell'archivio in Computer locale
    4. Modificare l'archivio certificati nella radice
    5. Selezionare Installa
    6. Verificare che il certificato sia visualizzato nell'elenco dei certificati. In caso contrario, ripetere i passaggi precedenti

#### <a name="inspect-https-sessions"></a>Esaminare le sessioni HTTP(S)

Nel PC Fiddler mostrerà le HoloLens 2 HTTP(S) attive del dispositivo. Il pannello Inspectors (Controlli) in Fiddler può visualizzare la richiesta/risposta HTTP(S) in visualizzazioni diverse. Ad esempio, la visualizzazione "Raw" mostra la richiesta o la risposta non elaborata in testo normale. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Configurare Wireshark per l'acquisizione del traffico di rete
Wireshark è un analizzatore di protocolli di rete e viene usato per controllare il traffico TCP/UDP da e verso i dispositivi HoloLens 2 rete. In questo modo è facile identificare il traffico che attraversa la rete verso il HoloLens 2, la quantità, la frequenza, la latenza tra determinati hop e così via.

#### <a name="prerequisites"></a>Prerequisiti:
- Il PC deve avere accesso a Internet e supportare la condivisione Internet su Wi-Fi

#### <a name="install-and-configure-wireshark"></a>Installare e configurare Wireshark
1. Nel PC installare [Wireshark](https://www.wireshark.org/#download) 
1. Nel PC abilitare Hotspot per dispositivi mobili per condividere la connessione Internet dal Wi-Fi.
1. Nel PC avviare Wireshark e acquisire il traffico dall'interfaccia hotspot mobile. 
1. Nel HoloLens 2: modificare la Wi-Fi di rete nell'hotspot Mobile del PC. HoloLens 2 Il traffico IP verrà visualizzato in Wireshark.

#### <a name="analyze-wireshark-logs"></a>Analizzare i log di Wireshark
I filtri Wireshark consentono di filtrare i pacchetti di interesse. 

Vedere il [blog originale.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)

[Torna all'elenco](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Non è possibile accedere a un dispositivo di configurazione HoloLens precedente

Se il dispositivo è stato configurato in precedenza per un altro utente, per un client o per un ex dipendente [](/intune/remote-actions/devices-wipe) e non si ha la password per sbloccare il dispositivo, è possibile usare Intune per cancellare in remoto il dispositivo. Il dispositivo viene quindi nuovamente lampeggiato.  
> [!IMPORTANT]
> Quando si cancella il dispositivo, assicurarsi di lasciare deselezionato Mantieni lo stato **di registrazione e l'account** utente.

[Torna all'elenco](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Non è possibile accedere dopo l'aggiornamento a Windows Holographic 21H1

### <a name="symptoms"></a>Sintomi
- L'uso del PIN per l'accesso avrà esito negativo dopo l'immissione del PIN corretto.
- L'uso del metodo di accesso Web avrà esito negativo dopo l'accesso nella pagina Web.
- Il dispositivo non è elencato come "Azure AD aggiunto" [in](https://portal.azure.com/) portale di Azure -> Azure Active Directory -> Dispositivi.

### <a name="cause"></a>Causa
Il dispositivo in oggetto potrebbe essere stato eliminato dal tenant Azure AD destinazione. Ad esempio, ciò può verificarsi perché:

- Un amministratore o un utente ha eliminato il dispositivo nel portale di Azure o usando PowerShell.
- Il dispositivo è stato rimosso dal tenant Azure AD a causa dell'inattività. Per un ambiente gestito in modo efficiente, è in genere consigliabile che gli amministratori IT rimuovono i dispositivi inattivi non più [Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).

Quando un dispositivo inciso tenta di contattare nuovamente il tenant Azure AD dopo l'eliminazione, non riuscirà a eseguire l'autenticazione con Azure AD. Questo effetto è spesso invisibile all'utente del dispositivo, perché l'accesso memorizzato nella cache tramite PIN continuerà a consentire all'utente di accedere.

### <a name="mitigation"></a>Mitigazione
Attualmente non è possibile aggiungere un dispositivo HoloLens eliminato in Azure AD. I dispositivi interessati dovranno essere puliti seguendo le istruzioni per [il reflashing del dispositivo.](hololens-recovery.md#clean-reflash-the-device)

[Torna all'elenco](#list)

## <a name="autopilot-troubleshooting"></a>Risoluzione dei problemi di Autopilot

Gli articoli seguenti possono essere una risorsa utile per ottenere altre informazioni e risolvere i problemi di Autopilot, tuttavia tenere presente che questi articoli sono basati su Windows 10 Desktop e che non tutte le informazioni possono essere applicabili a HoloLens:

- [Windows Autopilot - Problemi noti](/mem/autopilot/known-issues)
- [Risolvere i problemi di registrazione dei dispositivi Windows in Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Conflitti di criteri](/mem/autopilot/policy-conflicts)

[Torna all'elenco](#list)

## <a name="managed-hololens-devices-faqs"></a>Domande frequenti HoloLens dispositivi gestiti

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>È possibile usare System Center Configuration Manager (SCCM) per gestire HoloLens dispositivi?

No. È necessario usare un sistema MDM per gestire i HoloLens mobili.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>È possibile usare Active Directory Domain Services (Ad DS) per gestire HoloLens account utente?

No. È necessario usare Azure Active Directory (Azure AD) per gestire gli account utente per HoloLens dispositivi.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>È HoloLens la registrazione automatica di Automated Data Capture Systems (ADCS) ?

No.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>È HoloLens partecipare all'autenticazione Windows integrata?

No.

### <a name="does-hololens-support-branding"></a>La HoloLens supporta la personalizzazione?

No. Tuttavia, è possibile risolvere questo problema usando uno degli approcci seguenti:

- Creare un'app personalizzata e quindi abilitare [la modalità tutto schermo](hololens-kiosk.md). L'app personalizzata può essere personalizzata e può avviare altre app, ad esempio Remote Assist.  
- Modificare tutte le immagini del profilo utente in Azure AD al logo aziendale. Tuttavia, potrebbe non essere consigliabile per tutti gli scenari.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Quali funzionalità di registrazione HoloLens 2 offerte?

La registrazione è limitata alle tracce che possono essere acquisite negli scenari di sviluppo o risoluzione dei problemi o ai dati di telemetria inviati dai dispositivi ai server Microsoft.

## <a name="questions-about-securing-hololens-devices"></a>Domande sulla protezione dei HoloLens mobili

Vedere [le informazioni HoloLens 2 sicurezza.](security-overview.md)
Per HoloLens dispositivi di prima generazione, vedere [queste domande frequenti.](hololens1-faq-security.yml)

[Torna all'elenco](#list)
