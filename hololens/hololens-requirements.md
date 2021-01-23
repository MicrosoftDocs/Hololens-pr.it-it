---
title: Configurare HoloLens in un ambiente commerciale
description: Leggi altre informazioni sulla distribuzione e la gestione di HoloLens in ambienti aziendali, tra cui Infrastructure, Azure Active Directory e gestione di dispositivi mobili.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
ms.openlocfilehash: 9458a6fd02cf96dd265580cb099e39fa221d4206
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284047"
---
# Distribuzione e gestione di HoloLens 2 Enterprise

Questa panoramica ha lo scopo di aiutare i professionisti IT a comprendere le considerazioni per la distribuzione e la gestione dei dispositivi Microsoft HoloLens 2 all'interno dell'organizzazione.

HoloLens 2 viene eseguito in Windows 10 olografico che offre alle organizzazioni un dispositivo mobile e tecnologie di gestione delle app robusto, flessibile e integrato. Windows 10 olografico supporta la gestione del ciclo di vita del dispositivo end-to-end per consentire alle aziende di controllare i propri dispositivi, dati e app. HoloLens 2 può essere facilmente incorporato in pratiche di ciclo di vita standard, dalla registrazione dei dispositivi, dalla configurazione e dalla gestione delle applicazioni alla manutenzione e alla pensione con una soluzione di gestione di dispositivi mobili completa.

## Preparare

Mentre ti prepari a distribuire HoloLens 2 nell'ambiente aziendale, ci sono diverse considerazioni che dovrebbero essere esaminate e comprese quando inizi a pianificare le distribuzioni in scala di HoloLens 2.

### Elementi essenziali dell'infrastruttura

Per HoloLens 2 in uno scenario di distribuzione dell'organizzazione aziendale, sono necessari alcuni servizi infrastrutturali essenziali per supportare il set completo di funzionalità. HoloLens 2 è stato creato con la [moderna gestione di dispositivi mobili](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) in considerazione per la distribuzione e la gestione. Con Azure AD join + MDM come mezzo principale per raggiungere questo obiettivo in una forza lavoro mobile sempre crescente. Gli argomenti seguenti offrono una breve panoramica di ogni componente dell'infrastruttura che deve essere considerato nella pianificazione della distribuzione per HoloLens 2.

### Azure Active Directory
Azure AD è un servizio directory basato su cloud che offre funzionalità di gestione delle identità e dell'accesso. Puoi integrarlo con directory locali esistenti per creare una soluzione di gestione delle identità ibrida. Le organizzazioni che usano Microsoft Office 365 o Intune stanno già usando Azure AD, che include tre edizioni: Free, Premium P1 e Premium P2 (Vedi [edizioni di Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Tutte le edizioni supportano la registrazione di Azure AD Device, ma è necessario Premium P1 per abilitare l'iscrizione automatica MDM. HoloLens 2 richiede l'aggiunta di Azure Active Directory per abilitare la maggior parte delle funzionalità e delle caratteristiche del livello aziendale.

> [!NOTE]
> In locale Active Directory join non è supportato in HoloLens 2.

### Gestione dei dispositivi mobili
HoloLens 2 è progettato in modo specifico per essere gestito da sistemi di gestione di dispositivi mobili (MDM) in un ambiente aziendale. Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), parte di Enterprise Mobility + Security, è un sistema MDM basato sul cloud che gestisce i dispositivi nell'organizzazione. Come Office 365, Intune USA Azure AD per la gestione delle identità, quindi i dipendenti usano le stesse credenziali per la registrazione dei dispositivi in Intune che usano per accedere a Office 365. Più sistemi MDM supportano Windows10 e la maggior parte supporta scenari di distribuzione con dispositivi personali e aziendali. I sistemi MDM possono anche gestire le distribuzioni delle applicazioni e gli aggiornamenti per HoloLens 2. Altri provider MDM che supportano HoloLens 2 attualmente includono: MobileIron e altri. Tutti i fornitori di sistemi MDM hanno uguale accesso a Windows 10 Device Management Configuration Service Providers (CSP) s, offrendo alle organizzazioni IT la libertà di selezionare il sistema più adatto ai requisiti di gestione, sia Microsoft Intune che un prodotto MDM di terze parti.

> [!NOTE]
> I tradizionali sistemi di gestione dei PC locali, come System Center Configuration Manager, non sono supportati in HoloLens 2.

### Windows Update for Business
Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti. Vedere la documentazione sugli [aggiornamenti di HoloLens](https://docs.microsoft.com/hololens/hololens-updates) per informazioni dettagliate sulla gestione degli aggiornamenti di HoloLens 2.

### Certificati
HoloLens 2 supporta la distribuzione di certificati tramite MDM se l'ambiente richiede certificati per l'autenticazione di rete Wi-Fi Corp o l'accesso ad altre risorse. Alcune configurazioni dell'infrastruttura MDM possono essere necessarie per abilitare le distribuzioni di certificati a HoloLens 2. Informazioni su come [preparare i certificati e i profili di rete per HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Se si usa Intune, vedere i dettagli della [configurazione della certificazione](https://docs.microsoft.com/mem/intune/protect/certificates-configure) .

## Configurazione

Gli amministratori MDM possono definire e implementare le impostazioni dei criteri in qualsiasi dispositivo aziendale registrato in un sistema MDM. Le impostazioni di configurazione usate saranno diverse in base allo scenario di distribuzione. In Windows 10, i provider di servizi di configurazione (CSP) sono un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione nel dispositivo. Queste impostazioni corrispondono a chiavi del Registro di sistema o file. Per altre informazioni sui CSP per la gestione dei dispositivi di Windows 10 per HoloLens 2, vedere l'elenco completo dei [CSP supportati nei dispositivi HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

HoloLens 2 supporta inoltre l'impostazione di un set limitato di configurazioni CSP tramite pacchetti di provisioning personalizzati. I pacchetti di provisioning vengono in genere sfruttati per i dispositivi gestiti non MDM e richiedono l'applicazione manuale a ogni dispositivo. Per informazioni dettagliate sulla creazione di pacchetti di provisioning personalizzati, vedere la documentazione di provisioning di [HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) .

> [!NOTE]
> HoloLens 2 supporta [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), offrendo un processo semplice e facile per la gestione delle configurazioni dei dispositivi Windows 10 aziendali.

### Gestione delle identità

I dipendenti possono usare un solo account per inizializzare un dispositivo in modo che&#39;s imperativo che l'organizzazione controlli per primo quale account è abilitato. L'account scelto determinerà chi controlla il dispositivo e influirà sulle funzionalità di gestione. HoloLens 2 supporta 3 tipi di account: account utente locale, account Microsoft personale e account di Azure Active Directory. È vivamente consigliabile sfruttare Azure Active Directory per la soluzione di gestione delle identità aziendali, in quanto consentirà di abilitare tutte le funzionalità dei dispositivi HoloLens 2. Per altre informazioni sulle identità di HoloLens 2, vedere l' [identità di HoloLens](https://docs.microsoft.com/hololens/hololens-identity) .

### Rete e connettività

Poiché HoloLens 2 è un primo dispositivo cloud, è necessario l'accesso alla rete alle risorse online per rendere disponibili le funzionalità e le funzionalità complete. Se si distribuiscono dispositivi HoloLens 2 con connettività alla rete Intranet aziendale, potrebbe essere necessario aggiornare le regole proxy/firewall per consentire l'accesso ai servizi cloud di HoloLens 2. Per altre informazioni, vedere l'elenco di [endpoint comuni per il sistema operativo HoloLens 2](https://docs.microsoft.com/hololens/hololens-offline). L'accesso a endpoint aggiuntivi può essere necessario per l'esecuzione di applicazioni o altri servizi cloud su HoloLens 2 con successo.

Di seguito sono riportati alcuni servizi comuni di HoloLens 2 che richiedono ulteriori accessi agli endpoint:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guide d365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [Assistenza remota di d365 (infrastruttura teams di Office 365)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### Distribuzione di certificati

Se sono necessari certificati per l'accesso alle reti aziendali Wi-Fi o ad altri servizi all'interno dell'organizzazione, HoloLens 2 supporta la distribuzione di certificati utente e dispositivi tramite MDM. Nota: la soluzione MDM può richiedere un'ulteriore configurazione dell'infrastruttura per distribuire i certificati ai dispositivi Windows 10.

### Revisione della sicurezza

La maggior parte dei reparti IT aziendali richiederà la valutazione e la revisione di nuovi dispositivi distribuiti in una rete aziendale. Se l'organizzazione ha bisogno di una revisione di sicurezza di HoloLens 2, è possibile trovare altri dettagli per facilitare l' [ottenimento delle approvazioni di sicurezza](https://docs.microsoft.com/hololens/security-overview).

### Impostazioni comuni di HoloLens 2 Device

Quando si distribuiscono dispositivi HoloLens 2 in un ambiente aziendale, sono disponibili diverse configurazioni di dispositivi comuni che possono essere considerate durante la pianificazione della distribuzione di HoloLens 2. Questo elenco evidenzia le configurazioni e le impostazioni che risultano abbastanza comuni e non includono un elenco completo delle opzioni disponibili:

| Impostazione del dispositivo | Breve descrizione.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrizioni hardware](hololens-requirements.md#hardware-restrictions)               | Le restrizioni hardware riducono la connettività e facilitano la protezione dei dati.                        |
| [Profili Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configurare i profili Wi-Fi senza l'intervento o l'interazione dell'utente.                              |
| [Certificati](hololens-requirements.md#certificates-1)               | Fornisci account e/o Wi-Fi l'autenticazione, la crittografia VPN e la crittografia SSL del contenuto Web. |
| [Proxy](hololens-requirements.md#proxy)              | Gestire il traffico interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controllare l'accesso alle app e alle risorse nell'Intranet della società.                               |
| [Modalità tutto schermo](hololens-requirements.md#kiosk-mode) | Limita le applicazioni presentate agli utenti tramite l'interfaccia utente. |

#### Restrizioni hardware

HoloLens 2 usa una tecnologia all'avanguardia che include caratteristiche hardware popolari come fotocamere, microfoni, altoparlanti, interfacce USB, interfacce Bluetooth e Wi-Fi. Puoi usare le restrizioni hardware per controllare la disponibilità di queste funzionalità.

Di seguito sono elencate le impostazioni MDM più comunemente usate che HoloLens 2 supporta per configurare le restrizioni hardware. Alcune di queste restrizioni hardware forniscono connettività e agevolano la protezione dei dati.

- [**Consenti WiFi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se gli utenti possono abilitare e usare la radio Wi-Fi nei propri dispositivi
- [**Consenti connessione USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se è abilitata la connessione USB (doesn&#39;t influenzano la ricarica USB)
- [**Consenti Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se gli utenti possono abilitare e usare la radio Bluetooth nei propri dispositivi

Per altre informazioni, vedere altre [restrizioni sui dispositivi comuni.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Profili Wi-Fi

La maggior parte delle reti Wi-Fi aziendali richiede certificati e altre informazioni complesse per limitare e proteggere l'accesso degli utenti. Queste informazioni di Wi-Fi avanzate sono difficili da configurare per gli utenti tipici, ma i sistemi MDM possono configurare questi profili di Wi-Fi senza l'intervento dell'utente. Puoi creare più profili Wi-Fi nel sistema MDM.

Per altre informazioni sulle impostazioni di Wi-Fi per Windows 10, vedere [impostazioni di WiFi per il profilo aziendale](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

#### Certificati

I certificati consentono di migliorare la sicurezza fornendo l'autenticazione dell'account, l'autenticazione Wi-Fi, la crittografia VPN e la crittografia SSL del contenuto Web. Anche se gli amministratori possono gestire i certificati sui dispositivi manualmente tramite il provisioning dei pacchetti, è&#39;una procedura consigliata per usare il sistema MDM per gestire tali certificati per tutto il ciclo di vita, dall'iscrizione al rinnovo e alla revoca. Il sistema MDM può distribuire automaticamente questi certificati ai dispositivi&#39; archivi di certificati dopo la registrazione del dispositivo (purché il sistema MDM supporti il protocollo SCEP) o gli standard di crittografia a chiave pubblica #12 (PKCS # 12)). MDM può anche eseguire query ed eliminare certificati client registrati o attivare una nuova richiesta di registrazione prima della scadenza del certificato corrente.

Per altre informazioni, vedere come [preparare certificati e profili di rete per HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

La maggior parte delle reti Intranet aziendali sfrutta un proxy per gestire il traffico interno. Con HoloLens 2 è possibile configurare un server proxy per le connessioni Ethernet e Wi-Fi. Queste impostazioni non si applicano alle connessioni VPN.

Per altre informazioni sulle impostazioni proxy per Windows 10, Vedi [CSP di NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### VPN

Le organizzazioni usano spesso una VPN per controllare l'accesso alle app e alle risorse nella Intranet aziendale&#39;s. HoloLens 2 supporta le connessioni VPN SSL, che richiedono un plug-in scaricabile da Microsoft Store e sono specifiche del fornitore di VPN a scelta.

Per altri dettagli sui profili VPN, vedi [CSP VPNv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### Modalità tutto schermo

Puoi configurare un dispositivo HoloLens 2 in modo che funzioni come dispositivo a scopo fisso, detto anche chiosco, configurando il dispositivo per l'esecuzione in modalità Kiosk. La modalità Kiosk limita le applicazioni (o gli utenti) disponibili nel dispositivo. La modalità Kiosk è una caratteristica comoda che puoi usare per dedicare un dispositivo HoloLens 2 alle app aziendali o per usare il dispositivo HoloLens 2 in una demo dell'app.

Per altre informazioni sulla configurazione di un HoloLens 2 in modalità Kiosk, vedere [configurazione di HoloLens come chiosco](https://docs.microsoft.com/hololens/hololens-kiosk)

## Distribuisci

### Registrazione di un dispositivo MDM

Per le distribuzioni aziendali, è consigliabile [registrare i dispositivi](https://docs.microsoft.com/hololens/hololens-enroll-mdm) in MDM come dispositivi aziendali solo con Azure ad join e la registrazione automatica MDM (Azure ad + MDM). Questo richiede Azure AD Premium e supporta l'iscrizione automatica a diversi provider MDM, tra cui Intune.

Leggi altre informazioni sul metodo [autopilota](https://docs.microsoft.com/hololens/hololens2-autopilot)di registrazione automatica.

### Distribuzione di applicazioni

La produttività degli utenti nei dispositivi mobili spesso dipende dalle app.

Windows10 consente di sviluppare app che funzionano perfettamente su più dispositivi con la piattaforma UWP (Universal Windows Platform) per app di Windows.

Esistono diversi modi per distribuire le applicazioni in dispositivi HoloLens 2. Le app possono essere distribuite direttamente tramite MDM, Microsoft Store for business o sideload tramite un pacchetto di provisioning. Per altre informazioni, vedere la documentazione sulla [distribuzione dell'app](https://docs.microsoft.com/hololens/app-deploy-overview) .

> [!NOTE]
> HoloLens 2 supporta l'uso solo delle app UWP ARM64.

## Gestione

Negli ambienti IT aziendali occorre trovare il giusto compromesso tra le esigenze di sicurezza e controllo dei costi e la volontà di offrire le tecnologie più recenti agli utenti. Poiché attacchi cibernetici è diventato un evento quotidiano, è importante mantenere correttamente lo stato dei dispositivi Windows 10. Il personale IT deve controllare le impostazioni di configurazione, verificando che rimangano entro i limiti di conformità, oltre a stabilire quali dispositivi possono accedere alle applicazioni interne. HoloLens 2 offre le funzionalità di gestione delle operazioni mobili necessarie per garantire che i dispositivi siano conformi ai criteri aziendali.

### Opzioni di manutenzione del sistema operativo

**Processo di aggiornamento semplificato**

Microsoft ha semplificato il ciclo di progettazione e rilascio dei prodotti Windows in modo da riuscire a fornire le nuove funzionalità, esperienze e caratteristiche richieste dal mercato molto più velocemente che nel passato. Microsoft prevede di fornire due aggiornamenti delle funzionalità all'anno (periodo di 12 mesi). **Gli aggiornamenti delle caratteristiche** stabiliscono un ramo o un CB corrente e hanno una versione associata.

Microsoft consentirà inoltre di distribuire e installare gli aggiornamenti per la sicurezza e la stabilità direttamente nei dispositivi HoloLens 2. Questi **aggiornamenti di qualità** , rilasciati in Microsoft Control tramite Windows Update, sono disponibili mensilmente. HoloLens 2 utilizza gli aggiornamenti delle funzionalità e gli aggiornamenti di qualità nell'ambito dello stesso processo di aggiornamento standard.

I clienti aziendali possono gestire l'esperienza di aggiornamento e il processo su HoloLens 2S usando un sistema MDM. Nella maggior parte dei casi, i criteri per gestire il processo di aggiornamento verranno applicati sia agli aggiornamenti della funzionalità che agli aggiornamenti di qualità. Ulteriori informazioni sulla [configurazione di MDM per gli aggiornamenti di HoloLens](https://docs.microsoft.com/hololens/hololens-updates).

### Gestione delle applicazioni

Gli amministratori IT possono controllare quali app sono consentite per l'installazione in HoloLens 2 e come devono essere mantenute aggiornate.

HoloLens 2 supporta [Windows Defender Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac), che consente agli amministratori di creare, consentire o impedire gli elenchi di app da Microsoft Store. Questa funzionalità si estende anche alle app predefinite. La possibilità di consentire o negare le app contribuisce a garantire che gli utenti usino i loro dispositivi per scopi previsti. Tuttavia, non sempre è semplice trovare il giusto equilibrio tra quello che serve ai dipendenti o che viene richiesto dai dipendenti e le problematiche a livello di sicurezza. La creazione di elenchi di app consentite o non consentite implica anche di dover rimanere sempre al passo con il mondo delle app in continua evoluzione in Microsoft Store.

Per altre informazioni, Vedi [CSP del controllo applicazione](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### Ritiro

La pensione del dispositivo è l'ultima fase del ciclo di vita del dispositivo. &#39;s importante che i dispositivi sostituiti con i modelli più recenti vengano ritirati in modo sicuro poiché Don&#39;t vuole che i dati aziendali rimangano su dispositivi scartati che potrebbero compromettere la riservatezza dei dati. Il personale IT deve anche predisporre un servizio di supporto adeguato per gli utenti che devono cancellare i dispositivi smarriti o rubati.

HoloLens 2 supporta 3 metodi per pulire il dispositivo

**Cancellazione della Factory MDM:** Reimposta HoloLens 2 sull'immagine Factory tramite il comando MDM avviato dall'amministratore. Cancella tutti i dati archiviati nel dispositivo.

**Reimpostazione del dispositivo dall'interno delle impostazioni:** Gli utenti finali possono reimpostare manualmente il HoloLens 2 nell'app impostazioni nel dispositivo. Cancella tutti i dati archiviati nel dispositivo.

**Complemento avanzato di ripristino (Arc):** Da un PC che gestisce lo strumento ARC, un utente o un amministratore può flashare un HoloLens 2 collegato al PC tramite cavo USB. Cancella tutti i dati archiviati nel dispositivo.

> [!div class="nextstepaction"]
> [Scenari di distribuzione comuni](common-scenarios.md)
