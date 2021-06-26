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
# <a name="troubleshooting-implementation-and-managed-devices"></a>Risoluzione dei problemi di implementazione e dispositivi gestiti 

Questo articolo descrive come risolvere diversi problemi o rispondere a domande relative all'implementazione e alla gestione dei HoloLens 2.

>[!IMPORTANT]
> Prima di avviare qualsiasi procedura di risoluzione dei problemi, assicurarsi che il dispositivo venga addebitato al **20-40%** della capacità della batteria, se possibile. Le [luci dell'indicatore della](hololens2-setup.md#lights-that-indicate-the-battery-level) batteria che si trovano sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.


<a id="list"></a>
- [Risoluzione dei problemi EAP](#eap-troubleshooting)
- [Risoluzione dei problemi wi-fi](#wi-fi-troubleshooting)
- [Risoluzione dei problemi di rete](#network-troubleshooting)
- [Non è possibile accedere a un dispositivo HoloLens precedentemente](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Non è possibile accedere dopo l'aggiornamento a Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Risoluzione dei problemi di Autopilot](#autopilot-troubleshooting)
- [Domande frequenti sui dispositivi HoloLens gestiti](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Risoluzione dei problemi EAP
1. Verificare che Wi-Fi profilo abbia le impostazioni giuste:
    - Il tipo EAP è configurato correttamente, tipi EAP comuni: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).
    - Wi-Fi il nome SSID è giusto e corrisponde alla stringa HEX.
    - Per EAP-TLS, TrustedRootCA contiene l'hash SHA-1 del certificato della CA radice attendibile del server. Nel comando "certutil.exe -dump cert_file_name" del PC Windows verrà mostrata la stringa hash SHA-1 di un certificato.
2. Raccogliere l'acquisizione di pacchetti di rete nei log del punto di accesso o del controller o del server AAA per individuare il punto di errore della sessione EAP.
    - Se l'identità EAP fornita da HoloLens non è prevista, verificare se il provisioning dell'identità è stato eseguito correttamente tramite un profilo Wi-Fi o un certificato client.
    - Se il server rifiuta il certificato client HoloLens, verificare se è stato effettuato il provisioning del certificato client richiesto nel dispositivo.
    - Se HoloLens rifiuta il certificato del server, verificare se è stato effettuato il provisioning del certificato della CA radice del server in HoloLens.
3. Se il provisioning del profilo aziendale viene eseguito Wi-Fi pacchetto di provisioning, è consigliabile applicare il pacchetto di provisioning in un PC Windows 10 locale. Se si verifica un errore anche Windows 10 PC, seguire la guida alla risoluzione dei problemi di autenticazione 802.1X del client Windows.
4. Inviare commenti e suggerimenti tramite Hub di Feedback.

[Torna all'elenco](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi risoluzione dei problemi

Ecco alcuni aspetti da provare se non è possibile connettere HoloLens a una rete Wi-Fi rete:

1. Assicurarsi che la Wi-Fi sia attivata. Per controllare, usare il movimento Avvia e quindi selezionare Impostazioni > rete & Internet > Wi-Fi. Se Wi-Fi è attivata, provare a disattivarla e quindi attivarla di nuovo.
2. Passare più vicino al router o al punto di accesso.
3. Riavviare il router Wi-Fi, quindi riavviare HoloLens. Provare a eseguire di nuovo la connessione.
4. Se nessuna di queste operazioni funziona, verificare che il router utilizzi il firmware più recente. Queste informazioni sono disponibili nel sito Web del produttore.

Quando si accede a un account aziendale o aziendale nel dispositivo, può anche applicare i criteri di gestione dei dispositivi mobili (MDM), se i criteri sono configurati dall'amministratore IT.

## <a name="network-troubleshooting"></a>Risoluzione dei problemi di rete
Se i problemi di rete sono un ostacolo per la corretta distribuzione e l'uso di HoloLens 2 nell'organizzazione, vedere come due noti strumenti di diagnostica di rete, Fiddler e Wireshark, consentono di analizzare, diagnosticare e identificare i problemi. Per altri [dettagli, vedere](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) questo blog.

[Torna all'elenco](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Non è possibile accedere a un dispositivo HoloLens precedentemente

Se il dispositivo è stato configurato in precedenza per un altro utente, per un client o per un ex dipendente [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) e non si ha la password per sbloccare il dispositivo, è possibile usare Intune per cancellare in remoto il dispositivo. Il dispositivo viene quindi nuovamente lampeggiato.  
> [!IMPORTANT]
> Quando si cancella il dispositivo, assicurarsi di lasciare deselezionato Mantieni lo stato **di registrazione e l'account** utente.
[Torna all'elenco](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Non è possibile accedere dopo l'aggiornamento a Windows Holographic 21H1

### <a name="symptoms"></a>Sintomi
- L'uso del PIN per l'accesso avrà esito negativo dopo l'immissione del PIN corretto.
- L'uso del metodo di accesso Web avrà esito negativo dopo l'accesso nella pagina Web.
- Il dispositivo non è elencato come "Azure AD aggiunto" [in](https://portal.azure.com/) portale di Azure -> Azure Active Directory -> Dispositivi.

### <a name="cause"></a>Causa
È possibile che il dispositivo in oggetto sia stato eliminato dal tenant Azure AD destinazione. Ad esempio, questa operazione può verificarsi per i seguenti:

- Un amministratore o un utente ha eliminato il dispositivo nel portale di Azure o usando PowerShell.
- Il dispositivo è stato rimosso dal tenant Azure AD a causa dell'inattività. Per un ambiente gestito in modo efficiente, è in genere consigliabile che gli amministratori IT rimuovono i dispositivi [inattivi](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)non più Azure AD tenant .

Quando un dispositivo inciso tenta di contattare nuovamente il tenant Azure AD dopo l'eliminazione, non riuscirà a eseguire l'autenticazione con Azure AD. Questo effetto è spesso invisibile all'utente del dispositivo, perché l'accesso memorizzato nella cache tramite PIN continuerà a consentire all'utente di accedere.

### <a name="mitigation"></a>Mitigazione
Attualmente non è possibile aggiungere un dispositivo HoloLens eliminato in Azure AD. I dispositivi interessati dovranno essere puliti seguendo le istruzioni per [il reflashing del dispositivo.](hololens-recovery.md#clean-reflash-the-device)

## <a name="autopilot-troubleshooting"></a>Risoluzione dei problemi di Autopilot

Gli articoli seguenti possono essere una risorsa utile per ottenere altre informazioni e risolvere i problemi di Autopilot, tuttavia tenere presente che questi articoli sono basati su Windows 10 Desktop e che non tutte le informazioni possono essere valide per HoloLens:

- [Windows Autopilot problemi noti](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Risolvere i problemi di registrazione dei dispositivi Windows in Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Conflitti di criteri](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Domande frequenti sui dispositivi HoloLens gestiti

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>È possibile usare System Center Gestione configurazione (SCCM) per gestire i dispositivi HoloLens?

No. È necessario usare un sistema MDM per gestire i dispositivi HoloLens.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>È possibile usare Active Directory Domain Services (Ad DS) per gestire gli account utente di HoloLens?

No. È necessario usare Azure Active Directory (Azure AD) per gestire gli account utente per i dispositivi HoloLens.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>HoloLens è in grado di eseguire la registrazione automatica di Automated Data Capture Systems (ADCS) ?

No.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>HoloLens può partecipare a autenticazione integrata di Windows?

No.

### <a name="does-hololens-support-branding"></a>HoloLens supporta la personalizzazione?

No. Tuttavia, è possibile risolvere questo problema usando uno degli approcci seguenti:

- Creare un'app personalizzata e quindi abilitare [la modalità tutto schermo](hololens-kiosk.md). L'app personalizzata può essere personalizzata e può avviare altre app, ad esempio Remote Assist.  
- Modificare tutte le immagini del profilo utente in Azure AD al logo aziendale. Tuttavia, potrebbe non essere consigliabile per tutti gli scenari.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Quali funzionalità di registrazione HoloLens 2 offerte?

La registrazione è limitata alle tracce che possono essere acquisite negli scenari di sviluppo o risoluzione dei problemi o ai dati di telemetria inviati dai dispositivi ai server Microsoft.

## <a name="questions-about-securing-hololens-devices"></a>Domande sulla protezione dei dispositivi HoloLens

Vedere [le informazioni HoloLens 2 sicurezza.](security-overview.md)
Per i dispositivi HoloLens di prima generazione, vedere [queste domande frequenti.](hololens1-faq-security.md)

[Torna all'elenco](#list)
