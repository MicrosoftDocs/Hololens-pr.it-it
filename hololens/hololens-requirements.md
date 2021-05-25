---
title: Configurare HoloLens in un ambiente commerciale
description: Altre informazioni sulla distribuzione e la gestione di HoloLens in ambienti aziendali, tra cui l'infrastruttura, Azure Active Directory e la gestione dei dispositivi mobili.
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
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397222"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 distribuzione e gestione aziendali

Questa panoramica ha lo scopo di aiutare i professionisti IT a comprendere le considerazioni per la distribuzione e la gestione Microsoft HoloLens 2 dispositivi all'interno dell'azienda.

HoloLens 2 viene eseguito in Windows 10 Holographic che offre alle organizzazioni tecnologie di gestione di dispositivi mobili e app affidabili, flessibili e integrate. Windows 10 Holographic supporta la gestione del ciclo di vita dei dispositivi end-to-end per offrire alle aziende il controllo su dispositivi, dati e app. Il HoloLens 2 può essere facilmente incorporato nelle procedure standard del ciclo di vita, dalla registrazione dei dispositivi, alla configurazione e alla gestione delle applicazioni fino alla manutenzione e al ritiro usando una soluzione completa di gestione dei dispositivi mobili.

## <a name="prepare"></a>Preparazione

Quando si prepara la distribuzione di HoloLens 2 nell'ambiente aziendale aziendale, è necessario esaminare e comprendere diverse considerazioni quando si inizia a pianificare distribuzioni su larga scala di HoloLens 2.

### <a name="infrastructure-essentials"></a>Informazioni di base dell'infrastruttura

Per HoloLens 2 in uno scenario di distribuzione aziendale aziendale, sono necessari alcuni servizi di infrastruttura essenziali per supportare il set completo di funzionalità. HoloLens 2 è stata creata con [la gestione moderna dei dispositivi mobili](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) per la distribuzione e la gestione. Con Azure AD Join + MDM come mezzo principale per ottenere questo risultato in una forza lavoro mobile in continua crescita. Gli argomenti seguenti offrono una breve panoramica di ogni componente dell'infrastruttura che deve essere preso in considerazione nella pianificazione della distribuzione per HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD è un servizio directory basato su cloud che offre funzionalità di gestione delle identità e dell'accesso. Puoi integrarlo con directory locali esistenti per creare una soluzione di gestione delle identità ibrida. Le organizzazioni che usano Microsoft Office 365 o Intune usano già Azure AD, che include tre edizioni: Gratuito, Premium P1 e Premium P2 (vedere Azure Active Directory [edizioni).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Tutte le edizioni supportano Azure AD registrazione del dispositivo, ma è necessario premium P1 per abilitare la registrazione automatica MDM. HoloLens 2 richiede Azure Active Directory join per abilitare la maggior parte delle funzionalità e delle funzionalità di livello aziendale.

> [!NOTE]
> L'aggiunta ad Active Directory locale non è supportata HoloLens 2.

### <a name="mobile-device-management"></a>Gestione dei dispositivi mobili
HoloLens 2 è progettato in modo specifico per essere gestito dai sistemi di gestione dei dispositivi mobili (MDM) in un ambiente aziendale. Microsoft [Intune,](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)parte del Enterprise Mobility + Security, è un sistema MDM basato sul cloud che gestisce i dispositivi nell'azienda. Analogamente a Office 365, Intune usa Azure AD per la gestione delle identità, quindi i dipendenti usano le stesse credenziali per registrare i dispositivi in Intune che usano per accedere a Office 365. Più sistemi MDM supportano Windows 10 e la maggior parte supporta scenari di distribuzione con dispositivi personali e aziendali. I sistemi MDM possono anche gestire le distribuzioni e gli aggiornamenti delle HoloLens 2 applicazioni. Altri provider MDM che supportano HoloLens 2 attualmente includono: AirWatch, MobileIron e altri. Tutti i fornitori di sistemi MDM hanno uguale accesso Windows 10 provider di servizi di configurazione della gestione dei dispositivi (CSP), offrendo alle organizzazioni IT la libertà di selezionare qualsiasi sistema più adatto ai propri requisiti di gestione, Microsoft Intune o un prodotto MDM di terze parti.

> [!NOTE]
> I sistemi di gestione dei PC locali tradizionali come System Center Gestione configurazione non sono supportati in HoloLens 2.

### <a name="windows-update-for-business"></a>Windows Update for Business
Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti. Vedere la [documentazione sugli aggiornamenti di HoloLens](https://docs.microsoft.com/hololens/hololens-updates) per informazioni dettagliate sulla gestione HoloLens 2 aggiornamenti.

### <a name="certificates"></a>Certificati
HoloLens 2 la distribuzione di certificati tramite MDM se l'ambiente richiede certificati per l'autenticazione di rete di Corp Wi-Fi o l'accesso ad altre risorse. Alcune configurazioni dell'infrastruttura MDM potrebbero essere necessarie per abilitare le distribuzioni di certificati HoloLens 2. Informazioni su come preparare [i certificati e i profili di rete per HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Se si usa Intune, vedere i dettagli di configurazione [della](https://docs.microsoft.com/mem/intune/protect/certificates-configure) certificazione.

## <a name="configure"></a>Configurare

Gli amministratori MDM possono definire e implementare le impostazioni dei criteri in qualsiasi dispositivo aziendale registrato in un sistema MDM. Le impostazioni di configurazione usate variano in base allo scenario di distribuzione. In Windows 10, i provider di servizi di configurazione (CSP) sono un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione nel dispositivo. Queste impostazioni corrispondono a chiavi del Registro di sistema o file. Per altre informazioni sui CSP Windows 10 gestione dei dispositivi per HoloLens 2, vedere l'elenco completo dei CSP [supportati nei dispositivi HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2 supporta anche l'impostazione di un set limitato di configurazioni CSP tramite pacchetti di provisioning personalizzati. I pacchetti di provisioning vengono in genere sfruttati per i dispositivi non gestiti da MDM e devono essere applicati manualmente a ogni dispositivo. Per informazioni dettagliate sulla creazione di pacchetti di provisioning personalizzati, vedere la documentazione sul provisioning di [HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)

> [!NOTE]
> HoloLens 2 [supporta](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)Windows Autopilot , offrendo un processo semplice e semplice per la gestione delle configurazioni dei dispositivi Windows 10 aziendali.

### <a name="identity-management"></a>Identity Management

I dipendenti possono usare un solo account per inizializzare un dispositivo&#39;è fondamentale che l'organizzazione controlli quale account è abilitato per primo. L'account scelto determinerà chi controlla il dispositivo e influirà sulle funzionalità di gestione. HoloLens 2 supporta 3 tipi di account: account utente locale, account Microsoft personale e account Azure Active Directory account. È consigliabile sfruttare i Azure Active Directory per la soluzione di gestione delle identità aziendali, perché consentirà di abilitare le funzionalità complete nei dispositivi HoloLens 2 aziendali. Per altre informazioni sulle identità per le HoloLens 2, vedere Identità di [HoloLens.](https://docs.microsoft.com/hololens/hololens-identity)

### <a name="network-and-connectivity"></a>Rete e connettività

Poiché HoloLens 2 è un dispositivo cloud first, l'accesso di rete alle risorse online è necessario per la disponibilità di funzionalità e funzionalità complete. Se si distribuiscono dispositivi HoloLens 2 con connettività alla rete Intranet aziendale, potrebbe essere necessario aggiornare le regole proxy/firewall per consentire l'accesso HoloLens 2 servizi cloud. Per altre informazioni, vedere l'elenco di endpoint comuni per il [HoloLens 2 operativo](https://docs.microsoft.com/hololens/hololens-offline). L'accesso ad altri endpoint può essere necessario per l'esecuzione corretta di applicazioni o altri servizi cloud HoloLens 2 servizio.

Di seguito sono HoloLens 2 servizi comuni che richiedono l'accesso agli endpoint aggiuntivi:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guide di D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (infrastruttura di O365 Teams)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Distribuzione di certificati

Se sono necessari certificati per l'accesso alle reti Wi-Fi aziendali o ad altri servizi all'interno dell'organizzazione, HoloLens 2 supporta la distribuzione di certificati utente e dispositivo tramite MDM. Nota: la soluzione MDM potrebbe richiedere una configurazione aggiuntiva dell'infrastruttura per distribuire i certificati Windows 10 dispositivi.

### <a name="security-review"></a>Verifica della sicurezza

La maggior parte dei reparti IT aziendali richiederà la valutazione e la revisione dei nuovi dispositivi distribuiti in una rete aziendale aziendale. Se l'organizzazione necessita di una verifica della sicurezza HoloLens 2, è possibile trovare altri dettagli per facilitare l'ottenimento [delle approvazioni della sicurezza.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Impostazioni HoloLens 2 comuni del dispositivo

Quando si distribuiscono HoloLens 2 in un ambiente aziendale aziendale, è possibile considerare diverse configurazioni di dispositivi comuni durante la pianificazione della distribuzione di HoloLens 2. Questo elenco evidenzia le configurazioni e le impostazioni che sono state trovate abbastanza comuni e non include un elenco completo delle opzioni disponibili:

| Impostazione del dispositivo | Breve descrizione.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrizioni hardware](hololens-requirements.md#hardware-restrictions)               | Le restrizioni hardware riducono la connettività e assistono nella protezione dei dati.                        |
| [Profili Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configurare i Wi-Fi senza l'intervento dell'utente o l'interazione.                              |
| [Certificati](hololens-requirements.md#certificates-1)               | Fornire l'account e/o Wi-Fi, la crittografia VPN e la crittografia SSL del contenuto Web. |
| [Proxy](hololens-requirements.md#proxy)              | Gestire il traffico interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controllare l'accesso ad app e risorse nella intranet aziendale.                               |
| [Modalità tutto schermo](hololens-requirements.md#kiosk-mode) | Limita le applicazioni presentate agli utenti tramite l'interfaccia utente. |

#### <a name="hardware-restrictions"></a>Restrizioni hardware

HoloLens 2 usa una tecnologia all'avanguardia che include funzionalità hardware comuni come fotocamere, microfoni, altoparlanti, interfacce USB, interfacce Bluetooth e Wi-Fi. Puoi usare le restrizioni hardware per controllare la disponibilità di queste funzionalità.

Di seguito sono elencate le impostazioni MDM più usate che HoloLens 2 per configurare le restrizioni hardware. alcune di queste restrizioni hardware forniscono connettività e agevolano la protezione dei dati.

- [**Consenti Wi-Fi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Indica se gli utenti possono abilitare e usare Wi-Fi radio nei propri dispositivi
- [**Consenti connessione USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se la connessione USB è abilitata (non&#39;influisce sulla ricarica USB)
- [**Consenti Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Indica se gli utenti possono abilitare e usare la radio Bluetooth nei propri dispositivi

Altre informazioni su altre [restrizioni comuni per i dispositivi.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Profili Wi-Fi

La maggior parte delle reti Wi-Fi aziendali richiede certificati e altre informazioni complesse per limitare e proteggere l'accesso degli utenti. Queste informazioni Wi-Fi avanzate sono difficili da configurare per gli utenti tipici, ma i sistemi MDM possono configurare completamente questi profili Wi-Fi senza l'intervento dell'utente. Puoi creare più profili Wi-Fi nel sistema MDM.

Per altre informazioni sulle impostazioni Wi-Fi per Windows 10, vedere [Impostazioni Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)del profilo Enterprise.

#### <a name="certificates"></a>Certificati

I certificati consentono di migliorare la sicurezza fornendo autenticazione dell'account, Wi-Fi autenticazione, crittografia VPN e crittografia SSL del contenuto Web. Anche se gli amministratori possono gestire manualmente i certificati nei dispositivi tramite il provisioning dei pacchetti&#39;, è consigliabile usare il sistema MDM per gestire tali certificati per l'intero ciclo di vita, dalla registrazione al rinnovo e alla revoca. Il sistema MDM può distribuire automaticamente questi certificati agli archivi certificati dei dispositivi&#39; dopo la registrazione del dispositivo (purché il sistema MDM supporti Simple Certificate Enrollment Protocol (SCEP) o Public Key Cryptography Standards #12 (PKCS #12)). MDM può anche eseguire query ed eliminare i certificati client registrati o attivare una nuova richiesta di registrazione prima della scadenza del certificato corrente.

Altre informazioni su come preparare [i certificati e i profili di rete per HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

La maggior parte delle reti Intranet aziendali sfrutta un proxy per gestire il traffico interno. Con HoloLens 2 è possibile configurare un server proxy per ethernet e Wi-Fi connessioni. Queste impostazioni non si applicano alle connessioni VPN.

Per altre informazioni sulle impostazioni proxy per Windows 10, vedere Provider di servizi di configurazione [NetworkProxy.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

#### <a name="vpn"></a>Connessione

Le organizzazioni usano spesso una VPN per controllare l'accesso ad app e risorse nella rete&#39;intranet aziendale. HoloLens 2 le connessioni VPN SSL, che richiedono un plug-in scaricabile dal Microsoft Store e sono specifiche del fornitore VPN di propria scelta.

Per altri dettagli sui profili VPN, vedi [CSP VPNv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Modalità tutto schermo

È possibile configurare un HoloLens 2 per il funzionamento come dispositivo a utilizzo fisso, denominato anche chiosco multimediale, configurando il dispositivo per l'esecuzione in modalità tutto schermo. La modalità tutto schermo limita le applicazioni (o gli utenti) disponibili nel dispositivo. La modalità tutto schermo è una funzionalità pratica che è possibile usare per dedicare un dispositivo HoloLens 2 alle app aziendali o per usare il dispositivo HoloLens 2 in una demo dell'app.

Per altre informazioni sulla configurazione di un HoloLens 2 in modalità tutto schermo, vedere [Configurare HoloLens come chiosco multimediale](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Distribuisci

### <a name="mdm-device-enrollment"></a>Registrazione di dispositivi MDM

Per le distribuzioni aziendali, [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) è consigliabile registrare i dispositivi in MDM come dispositivi aziendali solo con l'aggiunta Azure AD e la registrazione MDM automatica (Azure AD+MDM). Questa operazione richiede Azure AD Premium e supporta la registrazione automatica in diversi provider MDM, tra cui Intune.

Altre informazioni sul metodo di registrazione [auto-distribuzione Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### <a name="application-deployment"></a>Distribuzione dell'applicazione

La produttività degli utenti nei dispositivi mobili spesso dipende dalle app.

Windows 10 consente di sviluppare app che funzionano perfettamente su più dispositivi con la piattaforma UWP (Universal Windows Platform) per app di Windows.

Esistono diversi modi per distribuire applicazioni in HoloLens 2 dispositivi. Le app possono essere distribuite direttamente tramite MDM, Microsoft Store per le aziende o sideloaded tramite un pacchetto di provisioning. Per altri [dettagli, vedere](https://docs.microsoft.com/hololens/app-deploy-overview) la documentazione sulla distribuzione di app.

> [!NOTE]
> HoloLens 2 supporta solo l'esecuzione di app ARM64 UWP.

## <a name="maintain"></a>Effettuare la manutenzione

Negli ambienti IT aziendali occorre trovare il giusto compromesso tra le esigenze di sicurezza e controllo dei costi e la volontà di offrire le tecnologie più recenti agli utenti. Poiché gli attacchi informatici sono diventati un evento quotidiano, è importante mantenere correttamente lo stato dei Windows 10 dispositivi. Il personale IT deve controllare le impostazioni di configurazione, verificando che rimangano entro i limiti di conformità, oltre a stabilire quali dispositivi possono accedere alle applicazioni interne. HoloLens 2 offre le funzionalità di gestione delle operazioni mobili necessarie per garantire che i dispositivi siano conformi ai criteri aziendali.

### <a name="os-servicing-options"></a>Opzioni di manutenzione del sistema operativo

**Processo di aggiornamento semplificato**

Microsoft ha semplificato il ciclo di progettazione e rilascio dei prodotti Windows in modo da riuscire a fornire le nuove funzionalità, esperienze e caratteristiche richieste dal mercato molto più velocemente che nel passato. Microsoft prevede di fornire due aggiornamenti delle funzionalità all'anno (periodo di 12 mesi). **Gli aggiornamenti delle** funzionalità stabiliscono Current Branch o CB e hanno una versione associata.

Microsoft consegnerà e installerà anche gli aggiornamenti per la sicurezza e la stabilità direttamente HoloLens 2 dispositivi. Questi **aggiornamenti qualitativi,** rilasciati sotto il controllo di Microsoft Windows Update, sono disponibili ogni mese. HoloLens 2 utilizza gli aggiornamenti delle funzionalità e gli aggiornamenti qualitativi come parte dello stesso processo di aggiornamento standard.

I clienti aziendali possono gestire l'esperienza di aggiornamento e l'elaborazione in HoloLens 2s usando un sistema MDM. Nella maggior parte dei casi, i criteri per gestire il processo di aggiornamento verranno applicati sia agli aggiornamenti della funzionalità che agli aggiornamenti di qualità. Per altre informazioni, [vedere Configuring MDM for HoloLens updates (Configurazione di MDM per gli aggiornamenti di HoloLens).](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="managing-applications"></a>Gestione delle applicazioni

Gli amministratori IT possono controllare quali app possono essere installate nel HoloLens 2 e come devono essere mantenute aggiornate.

HoloLens 2 supporta Windows Defender controllo delle applicazioni [,](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)che consente agli amministratori di creare, consentire o non consentire elenchi di app dal Microsoft Store. Questa funzionalità si estende anche alle app predefinite. La possibilità di consentire o negare le app consente di garantire che gli utenti usino i propri dispositivi per gli scopi destinati. Tuttavia, non sempre è semplice trovare il giusto equilibrio tra quello che serve ai dipendenti o che viene richiesto dai dipendenti e le problematiche a livello di sicurezza. La creazione di elenchi consenti o non consentiti richiede anche il mantenimento dell'ambiente dell'app in Microsoft Store.

Per altri dettagli, vedere [Application Control CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### <a name="retire"></a>Ritiro

Il ritiro dei dispositivi è l'ultima fase del ciclo di vita del dispositivo. È&#39;&#39;che i dispositivi sostituiti con modelli più recenti vengano ritirati in modo sicuro perché non si vuole che i dati aziendali rimangano nei dispositivi scartati che potrebbero compromettere la riservatezza dei dati. Il personale IT deve anche predisporre un servizio di supporto adeguato per gli utenti che devono cancellare i dispositivi smarriti o rubati.

HoloLens 2 supporta 3 metodi per la pulizia del dispositivo

**Cancellazione delle impostazioni di fabbrica MDM:** Reimposta il HoloLens 2 all'immagine factory tramite il comando MDM avviato dall'amministratore. Cancella tutti i dati archiviati nel dispositivo.

**Reimpostazione del dispositivo da Impostazioni:** Gli utenti finali possono reimpostare manualmente il HoloLens 2 all'interno dell'app Impostazioni nel dispositivo. Cancella tutti i dati archiviati nel dispositivo.

**Advanced Recovery Companion (ARC):** Da un PC che esegue lo strumento ARC, un utente o un amministratore può eseguire il flash di un HoloLens 2 connesso al PC tramite un cavo USB. Cancella tutti i dati archiviati nel dispositivo.

> [!div class="nextstepaction"]
> [Scenari di distribuzione comuni](common-scenarios.md)
