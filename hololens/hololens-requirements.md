---
title: Configurare HoloLens in un ambiente commerciale
description: Altre informazioni sulla distribuzione e la gestione di HoloLens in ambienti aziendali, tra cui infrastruttura, Azure Active Directory e gestione dei dispositivi mobili.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309522"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 distribuzione e gestione aziendale

Questa panoramica ha lo scopo di aiutare i professionisti IT a comprendere le considerazioni per la distribuzione e la gestione Microsoft HoloLens 2 dispositivi all'interno dell'azienda.

HoloLens 2 viene eseguito in Windows 10 Holographic che offre alle organizzazioni tecnologie di gestione di dispositivi mobili e app affidabili, flessibili e integrate. Windows 10 Holographic supporta la gestione del ciclo di vita dei dispositivi end-to-end per offrire alle aziende il controllo su dispositivi, dati e app. La HoloLens 2 può essere facilmente incorporata nelle procedure standard del ciclo di vita, dalla registrazione dei dispositivi, alla configurazione e alla gestione delle applicazioni, alla manutenzione e al ritiro usando una soluzione completa di gestione dei dispositivi mobili.

## <a name="prepare"></a>Preparare

Quando si prepara la distribuzione di HoloLens 2 nell'ambiente aziendale aziendale, è necessario esaminare e comprendere diverse considerazioni quando si inizia a pianificare distribuzioni di scalabilità di HoloLens 2.

### <a name="infrastructure-essentials"></a>Informazioni di base sulle infrastrutture

Per HoloLens 2 in uno scenario di distribuzione aziendale aziendale, sono necessari alcuni servizi di infrastruttura essenziali per supportare il set completo di funzionalità. HoloLens 2 è stato creato con [modern mobile device management](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) in mente per la distribuzione e la gestione. Con Azure AD join + MDM come mezzo principale per ottenere questo risultato in una forza lavoro mobile in continua crescita. Negli argomenti seguenti viene fornita una breve panoramica di ogni componente dell'infrastruttura che deve essere considerato nella pianificazione della distribuzione per HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD è un servizio directory basato su cloud che offre funzionalità di gestione delle identità e dell'accesso. Puoi integrarlo con directory locali esistenti per creare una soluzione di gestione delle identità ibrida. Le organizzazioni che usano Microsoft Office 365 o Intune usano già Azure AD, che include tre edizioni: Gratuito, Premium P1 e Premium P2 (vedere Azure Active Directory [edizioni](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Tutte le edizioni supportano Azure AD del dispositivo, ma è necessario premium P1 per abilitare la registrazione automatica MDM. HoloLens 2 richiede Azure Active Directory join per abilitare la maggior parte delle funzionalità a livello aziendale.

> [!NOTE]
> L'aggiunta ad Active Directory locale non è supportata in HoloLens 2.

### <a name="mobile-device-management"></a>Gestione dei dispositivi mobili
HoloLens 2 è progettato specificamente per essere gestito da sistemi di gestione di dispositivi mobili (MDM) in un ambiente aziendale. Microsoft [Intune,](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)parte del Enterprise Mobility + Security, è un sistema MDM basato sul cloud che gestisce i dispositivi nell'organizzazione. Analogamente a Office 365, Intune usa Azure AD per la gestione delle identità, quindi i dipendenti usano le stesse credenziali per registrare i dispositivi in Intune che usano per accedere a Office 365. Più sistemi MDM supportano Windows 10 e la maggior parte supporta scenari di distribuzione con dispositivi personali e aziendali. I sistemi MDM possono anche gestire le distribuzioni e gli aggiornamenti delle HoloLens 2 applicazioni. Altri provider MDM che supportano HoloLens 2 attualmente includono AirWatch, MobileIron e altri. Tutti i fornitori di sistemi MDM hanno lo stesso accesso ai provider di servizi di configurazione della gestione dei dispositivi (CSP) di Windows 10, offrendo alle organizzazioni IT la libertà di selezionare il sistema più adatto ai propri requisiti di gestione, Microsoft Intune o un prodotto MDM di terze parti.

> [!NOTE]
> I sistemi di gestione dei PC locali System Center Gestione configurazione non sono supportati in HoloLens 2.

### <a name="windows-update-for-business"></a>Windows Update for Business
Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti. Per informazioni dettagliate sulla gestione degli aggiornamenti [HoloLens 2 HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) vedere la documentazione sugli aggiornamenti di HoloLens.

### <a name="certificates"></a>Certificati
HoloLens 2 supporta la distribuzione di certificati tramite MDM se l'ambiente richiede certificati per l'autenticazione Wi-Fi rete aziendale o l'accesso ad altre risorse. Alcune configurazioni dell'infrastruttura MDM potrebbero essere necessarie per abilitare le distribuzioni di certificati HoloLens 2. Informazioni su come preparare [i certificati e i profili di rete per HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Se si usa Intune, vedere i dettagli di [configurazione della](https://docs.microsoft.com/mem/intune/protect/certificates-configure) certificazione.

## <a name="configure"></a>Configurare

Gli amministratori MDM possono definire e implementare le impostazioni dei criteri in qualsiasi dispositivo aziendale registrato in un sistema MDM. Le impostazioni di configurazione usate variano in base allo scenario di distribuzione. In Windows 10, i provider di servizi di configurazione (CSP) sono un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione nel dispositivo. Queste impostazioni corrispondono a chiavi del Registro di sistema o file. Per altre informazioni sui Windows 10 di gestione dei dispositivi per HoloLens 2, vedere l'elenco completo dei CSP supportati [nei dispositivi HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2 supporta anche l'impostazione di un set limitato di configurazioni CSP tramite pacchetti di provisioning personalizzati. I pacchetti di provisioning vengono in genere sfruttati per i dispositivi gestiti non MDM e devono essere applicati manualmente a ogni dispositivo. Per informazioni dettagliate sulla creazione di pacchetti di provisioning personalizzati, vedere la documentazione sul provisioning di [HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)

> [!NOTE]
> HoloLens 2 [supporta](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)Windows Autopilot , offrendo un processo semplice e semplice per la gestione delle configurazioni dei dispositivi Windows 10 aziendali.

### <a name="identity-management"></a>Identity Management

I dipendenti possono usare un solo account per inizializzare un dispositivo in modo&#39;imperativo che l'organizzazione controlli per primo quale account è abilitato. L'account scelto determinerà chi controlla il dispositivo e influirà sulle funzionalità di gestione. HoloLens 2 supporta 3 tipi di account: account utente locale, account Microsoft personale e account Azure Active Directory account. È altamente consigliabile sfruttare Azure Active Directory per la soluzione di gestione delle identità aziendali, in quanto abiliterà le funzionalità complete nei dispositivi HoloLens 2 aziendali. Per altri dettagli su Identities for HoloLens 2, vedere Identità di [HoloLens.](https://docs.microsoft.com/hololens/hololens-identity)

### <a name="network-and-connectivity"></a>Rete e connettività

Poiché HoloLens 2 è un primo dispositivo cloud, l'accesso alla rete alle risorse online è necessario per la disponibilità di funzionalità e funzionalità complete. Se si distribuiscono HoloLens 2 con connettività alla rete Intranet aziendale, potrebbe essere necessario aggiornare le regole proxy/firewall per consentire l'accesso HoloLens 2 servizi cloud. Per altre informazioni, vedere l'elenco degli endpoint comuni per il HoloLens 2 [operativo](https://docs.microsoft.com/hololens/hololens-offline). L'accesso ad altri endpoint può essere necessario per l'esecuzione di applicazioni o altri servizi cloud HoloLens 2 correttamente.

Di seguito sono HoloLens 2 comuni servizi che richiedono un accesso endpoint aggiuntivo:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guide D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (infrastruttura di O365 Teams)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Distribuzione del certificato

Se sono necessari certificati per l'accesso alle reti Wi-Fi aziendali o ad altri servizi all'interno dell'organizzazione, HoloLens 2 supporta la distribuzione di certificati utente e dispositivo tramite MDM. Nota: la soluzione MDM potrebbe richiedere una configurazione aggiuntiva dell'infrastruttura per distribuire i certificati Windows 10 dispositivi.

### <a name="security-review"></a>Verifica della sicurezza

La maggior parte dei reparti IT aziendali richiederà la valutazione e la revisione dei nuovi dispositivi distribuiti in una rete aziendale. Se l'organizzazione necessita di una revisione della sicurezza HoloLens 2 sicurezza, è possibile trovare altri dettagli per facilitare l'ottenimento [delle approvazioni della sicurezza.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Impostazioni HoloLens 2 comuni del dispositivo

Quando si distribuiscono HoloLens 2 in un ambiente aziendale aziendale, è possibile considerare diverse configurazioni comuni dei dispositivi durante la pianificazione della distribuzione di HoloLens 2. Questo elenco evidenzia le configurazioni e le impostazioni che sono piuttosto comuni e non include un elenco completo delle opzioni disponibili:

| Impostazione del dispositivo | Breve descrizione.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrizioni hardware](hololens-requirements.md#hardware-restrictions)               | Le restrizioni hardware riducono la connettività e assiste nella protezione dei dati.                        |
| [Profili Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configurare i Wi-Fi senza l'intervento dell'utente o l'interazione.                              |
| [Certificati](hololens-requirements.md#certificates-1)               | Fornire account e/o Wi-Fi autenticazione, crittografia VPN e crittografia SSL del contenuto Web. |
| [Proxy](hololens-requirements.md#proxy)              | Gestire il traffico interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controllare l'accesso ad app e risorse nella rete Intranet aziendale.                               |
| [Modalità tutto schermo](hololens-requirements.md#kiosk-mode) | Limita le applicazioni presentate agli utenti tramite l'interfaccia utente. |

#### <a name="hardware-restrictions"></a>Restrizioni hardware

HoloLens 2 usa una tecnologia all'avanguardia che include funzionalità hardware comuni, ad esempio fotocamere, microfoni, altoparlanti, interfacce USB, interfacce Bluetooth e Wi-Fi. Puoi usare le restrizioni hardware per controllare la disponibilità di queste funzionalità.

Di seguito sono elencate le impostazioni MDM più comunemente HoloLens 2 per configurare le restrizioni hardware. alcune di queste restrizioni hardware forniscono connettività e agevolano la protezione dei dati.

- [**Consenti Wi-Fi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Indica se gli utenti possono abilitare e usare la Wi-Fi radio nei dispositivi
- [**Consenti connessione USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Indica se la connessione USB è abilitata (&#39;non influisce sulla ricarica USB)
- [**Consenti Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Indica se gli utenti possono abilitare e usare la radio Bluetooth nei dispositivi

Altre informazioni sulle altre [restrizioni comuni dei dispositivi.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Profili Wi-Fi

La maggior parte delle reti Wi-Fi aziendali richiede certificati e altre informazioni complesse per limitare e proteggere l'accesso degli utenti. Queste informazioni Wi-Fi avanzate sono difficili da configurare per gli utenti tipici, ma i sistemi MDM possono configurare completamente questi profili Wi-Fi senza l'intervento dell'utente. Puoi creare più profili Wi-Fi nel sistema MDM.

Per altri dettagli sulle impostazioni Wi-Fi per Windows 10, vedere [Impostazioni Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)del profilo aziendale .

#### <a name="certificates"></a>Certificati

I certificati consentono di migliorare la sicurezza fornendo l'autenticazione dell'account, Wi-Fi, la crittografia VPN e la crittografia SSL del contenuto Web. Anche se gli amministratori possono gestire manualmente i certificati nei dispositivi&#39;tramite il provisioning dei pacchetti, è consigliabile usare il sistema MDM per gestire i certificati per l'intero ciclo di vita, dalla registrazione al rinnovo e alla revoca. Il sistema MDM può distribuire automaticamente questi certificati nei dispositivi&#39; archivi certificati dopo la registrazione del dispositivo (purché il sistema MDM supporti Simple Certificate Enrollment Protocol (SCEP) o Public Key Cryptography Standards #12 (PKCS #12)). MDM può anche eseguire query ed eliminare i certificati client registrati o attivare una nuova richiesta di registrazione prima della scadenza del certificato corrente.

Altre informazioni su come preparare [i certificati e i profili di rete per HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

La maggior parte delle reti Intranet aziendali sfrutta un proxy per gestire il traffico interno. Con HoloLens 2 è possibile configurare un server proxy per le connessioni ethernet e Wi-Fi connessioni. Queste impostazioni non si applicano alle connessioni VPN.

Per altre informazioni sulle impostazioni proxy per Windows 10, vedere [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### <a name="vpn"></a>Connessione

Le organizzazioni usano spesso una VPN per controllare l'accesso alle app e alle risorse&#39;intranet aziendale. HoloLens 2 supporta le connessioni VPN SSL, che richiedono un plug-in scaricabile dal Microsoft Store e sono specifiche del fornitore VPN di propria scelta.

Per altri dettagli sui profili VPN, vedi [CSP VPNv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Modalità tutto schermo

È possibile configurare un HoloLens 2 per funzionare come dispositivo per utilizzo fisso, detto anche chiosco multimediale, configurando il dispositivo per l'esecuzione in modalità tutto schermo. La modalità tutto schermo limita le applicazioni (o gli utenti) disponibili nel dispositivo. La modalità tutto schermo è una funzionalità pratica che è possibile usare per dedicare un dispositivo HoloLens 2 alle app aziendali o per usare il dispositivo HoloLens 2 in una demo di app.

Per altre informazioni sulla configurazione di un HoloLens 2 in modalità tutto schermo, vedere [Configurare HoloLens come chiosco multimediale](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Distribuisci

### <a name="mdm-device-enrollment"></a>Registrazione di dispositivi MDM

Per le distribuzioni aziendali, [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) è consigliabile registrare i dispositivi in MDM come dispositivi aziendali solo con l'aggiunta Azure AD e la registrazione MDM automatica (Azure AD+MDM). Questa operazione richiede Azure AD Premium e supporta la registrazione automatica a diversi provider MDM, tra cui Intune.

Altre informazioni sul metodo di registrazione [autopilot con distribuzione automatica.](https://docs.microsoft.com/hololens/hololens2-autopilot)

### <a name="application-deployment"></a>Distribuzione dell'applicazione

La produttività degli utenti nei dispositivi mobili spesso dipende dalle app.

Windows 10 consente di sviluppare app che funzionano perfettamente su più dispositivi con la piattaforma UWP (Universal Windows Platform) per app di Windows.

Esistono diversi modi per distribuire le applicazioni nei HoloLens 2 dispositivi. Le app possono essere distribuite direttamente tramite MDM, il Microsoft Store per le aziende o il sideloaded tramite un pacchetto di provisioning. Per altri [dettagli, vedere](https://docs.microsoft.com/hololens/app-deploy-overview) la documentazione sulla distribuzione dell'app.

> [!NOTE]
> HoloLens 2 supporta solo l'esecuzione di app ARM64 UWP.

## <a name="maintain"></a>Effettuare la manutenzione

Negli ambienti IT aziendali occorre trovare il giusto compromesso tra le esigenze di sicurezza e controllo dei costi e la volontà di offrire le tecnologie più recenti agli utenti. Poiché gli attacchi informatici sono diventati un evento quotidiano, è importante mantenere correttamente lo stato dei Windows 10 dispositivi. Il personale IT deve controllare le impostazioni di configurazione, verificando che rimangano entro i limiti di conformità, oltre a stabilire quali dispositivi possono accedere alle applicazioni interne. HoloLens 2 offre le funzionalità di gestione delle operazioni mobili necessarie per garantire che i dispositivi siano conformi ai criteri aziendali.

### <a name="os-servicing-options"></a>Opzioni di manutenzione del sistema operativo

**Processo di aggiornamento semplificato**

Microsoft ha semplificato il ciclo di progettazione e rilascio dei prodotti Windows in modo da riuscire a fornire le nuove funzionalità, esperienze e caratteristiche richieste dal mercato molto più velocemente che nel passato. Microsoft prevede di fornire due aggiornamenti delle funzionalità all'anno (periodo di 12 mesi). **Gli aggiornamenti delle** funzionalità stabiliscono Current Branch o CB e hanno una versione associata.

Microsoft inoltrerà e installerà gli aggiornamenti per la sicurezza e la stabilità direttamente HoloLens 2 dispositivi. Questi **aggiornamenti qualitativi,** rilasciati sotto il controllo Microsoft tramite Windows Update, sono disponibili mensilmente. HoloLens 2 utilizza gli aggiornamenti delle funzionalità e gli aggiornamenti qualitativi come parte dello stesso processo di aggiornamento standard.

I clienti aziendali possono gestire l'esperienza di aggiornamento e il processo in HoloLens 2s usando un sistema MDM. Nella maggior parte dei casi, i criteri per gestire il processo di aggiornamento verranno applicati sia agli aggiornamenti della funzionalità che agli aggiornamenti di qualità. Altre informazioni sulla [configurazione di MDM per gli aggiornamenti di HoloLens](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="managing-applications"></a>Gestione delle applicazioni

Gli amministratori IT possono controllare quali app possono essere installate nel HoloLens 2 e come devono essere aggiornate.

HoloLens 2 supporta Windows Defender [application control (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)che consente agli amministratori di creare, consentire o non consentire elenchi di app dal Microsoft Store. Questa funzionalità si estende anche alle app predefinite. La possibilità di consentire o negare le app consente di garantire che gli utenti usino i propri dispositivi per gli scopi specifici. Tuttavia, non sempre è semplice trovare il giusto equilibrio tra quello che serve ai dipendenti o che viene richiesto dai dipendenti e le problematiche a livello di sicurezza. La creazione di elenchi consentiti o non consentiti richiede anche di tenere il passo con la modifica dell'ambiente dell'app nel Microsoft Store.

Per altre informazioni, vedere [Application Control CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### <a name="retire"></a>Ritiro

Il ritiro dei dispositivi è l'ultima fase del ciclo di vita del dispositivo. È&#39;&#39;importante che i dispositivi sostituiti con modelli più recenti vengano ritirati in modo sicuro perché non si vuole che i dati aziendali rimangano nei dispositivi eliminati che potrebbero compromettere la riservatezza dei dati. Il personale IT deve anche predisporre un servizio di supporto adeguato per gli utenti che devono cancellare i dispositivi smarriti o rubati.

HoloLens 2 supporta 3 metodi di pulizia del dispositivo

**Cancellazione della factory MDM:** Reimposta il HoloLens 2'immagine della factory tramite il comando MDM avviato dall'amministratore. Cancella tutti i dati archiviati nel dispositivo.

**Reimpostazione del dispositivo da Impostazioni:** Gli utenti finali possono reimpostare manualmente il HoloLens 2 all'interno dell'app Impostazioni nel dispositivo. Cancella tutti i dati archiviati nel dispositivo.

**Advanced Recovery Companion (ARC):** Da un PC che esegue lo strumento ARC, un utente o un amministratore può lampeggiare un HoloLens 2 connesso al PC tramite cavo USB. Cancella tutti i dati archiviati nel dispositivo.

> [!div class="nextstepaction"]
> [Scenari di distribuzione comuni](common-scenarios.md)
