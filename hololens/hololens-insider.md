---
title: Insider Preview per Microsoft HoloLens
description: Informazioni su come iniziare a usare le build Insider e fornire feedback utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 80346fd74c9b38ed557d815ed138b1da5702609e
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859018"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuti alle build insider preview più recenti per HoloLens! È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Note sulla versione insider

Siamo entusiasti di iniziare a eseguire il volo di nuove funzionalità per Windows Insider. Le nuove build verranno aggiornate ai canali Dev e Beta per gli aggiornamenti più recenti. Questa pagina continuerà ad essere aggiornata quando si aggiungono altre funzionalità e aggiornamenti alle build di Windows Insider. Prepararsi a combinare questi aggiornamenti nella realtà.

Questo riguarda la risoluzione dei problemi migliorata e i report dei dispositivi, alcuni bug risolti in modalità tutto schermo e il visualizzatore di certificati, la superficie di gestibilità espansa e la maggiore affidabilità degli aggiornamenti. Una nuova funzionalità di punta di questo aggiornamento delle funzionalità HoloLens è la modalità piattaforma mobile. Scopri tutte le nuove funzionalità per HoloLens 2!

| Funzionalità                 | Descrizione                | Utente o scenario | Build introdotta |
|-------------------------|----------------------------|--------------|------------------|
| [Spostamento della modalità piattaforma](#moving-platform-mode) | Introduce la versione beta della modalità piattaforma mobile, che, se configurata, consente l'uso di HoloLens 2 su grandi navi di navi con movimento a bassa dinamica. | Tutti | 20348.1411 |
| [Supporto di file PFX per Gestione certificati](#pfx-file-support-for-certificate-manager) | Aggiungere certificati PFX tramite l'interfaccia Impostazioni utente | Utente finale | 20348.1405 |
| [Visualizzare il report di diagnostica avanzato in Impostazioni in HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Visualizzare i log di diagnostica MDM nel dispositivo | Risoluzione dei problemi | 20348.1405 |
| [Notifiche di diagnostica offline](#offline-diagnostics-notifications) | Commenti e suggerimenti per l'audiovisual per la raccolta di log | Risoluzione dei problemi | 20348.1405 |
| [Miglioramenti della raccolta di log di archiviazione a basso livello](#low-storage-log-collection-improvements) | Miglioramenti agli scenari di raccolta dei log in situazioni di archiviazione bassa. | Risoluzione dei problemi | 20348.1412 |
| [Modifiche CSP per la creazione di report HoloLens dettagli](#csp-changes-for-reporting-hololens-details) | Nuovi CSP per eseguire query sui dati | Amministratori IT    | 20348.1403                 |
| [Criteri di accesso automatico controllati da CSP](#auto-login-policy-controlled-by-csp) | Usato per accedere automaticamente a un account | Amministratori IT | 20348.1405 |
| [Rilevamento e notifiche del riavvio degli aggiornamenti migliorati](#improved-update-restart-detection-and-notifications) | Nuovi criteri abilitati e esperienza utente per gli aggiornamenti. | Amministratori IT | 20348.1405 |
| [Nuovo tentativo intelligente per gli aggiornamenti dell'app](#smart-retry-for-app-updates) | Consente agli amministratori IT di eseguire tentativi pianificati per aggiornare le app. | Amministratori IT | 20348.1405 |
| [Usare solo app dello Store privato solo per Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configurare l'app dello Store per visualizzare solo le app dell'organizzazione | Amministratore IT | 20348.1408 |
| [Usare le app WDAC e LOB](#use-wdac-and-lob-apps) | Consente agli amministratori IT di usare le proprie app e di usare ancora WDAC per bloccare altre app. | Amministratori IT | 20348.1405 |
| [Correzioni e miglioramenti](#fixes-and-improvements) | Correzioni e miglioramenti per HoloLens. | Tutti | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Elenco di controllo delle funzionalità insider per amministratori IT

✔️ se si desidera impostare un singolo account Azure AD per l'accesso automatico, [configurare questo nuovo provider di servizi di configurazione.](#auto-login-policy-controlled-by-csp) <br>
✔️ se si desidera configurare le app in modo che tentino automaticamente di eseguire l'aggiornamento dopo l'aggiornamento non riuscito, impostare questo nuovo provider di servizi di configurazione [per un nuovo tentativo intelligente.](#smart-retry-for-app-updates) <br>
✔️ se si desidera avere maggiore controllo degli aggiornamenti del sistema operativo, vedere questi criteri [di aggiornamento appena abilitati.](#improved-update-restart-detection-and-notifications) <br>
✔️ Se è necessario rendere disponibili le app dell'organizzazione nell'archivio aziendale tramite il Microsoft Store, ma si vuole consentire solo l'accesso alle app dell'organizzazione e non all'archivio completo, impostare questo [criterio.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ se si desidera conoscere lo spazio di archiviazione gratuito, SSID o BSSID dei dispositivi HoloLens vedere questi [CSP di report.](#csp-changes-for-reporting-hololens-details) <br>
✔️ se si desidera usare WDAC per bloccare l'avvio di app o processi, ma è anche necessario usare app line-of-bushiness personalizzate, è ora possibile consentire LOB nei criteri [WDAC.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Spostamento della modalità piattaforma

A data **della build Insider 20348.1411** è stato aggiunto il supporto beta per il rilevamento di piattaforme con movimento basso dinamico in HoloLens 2. Dopo aver installato la build e aver abilitato la modalità piattaforma mobile, sarà possibile usare il HoloLens 2 in ambienti inaccessibili in precedenza, ad esempio grandi navi e navi di grandi dimensioni. Attualmente, la funzionalità è destinata ad abilitare solo queste piattaforme in movimento specifiche. Sebbene nulla impedisca di provare a usare la funzionalità in altri ambienti, la funzionalità è incentrata sull'aggiunta del supporto per questi ambienti.

Per altre informazioni sulle funzionalità supportate e su come abilitare questa nuova funzionalità, [visitare la pagina della piattaforma mobile.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>Supporto di file PFX per Gestione certificati

Introdotto in Windows Insider build 20348.1405. È stato aggiunto il supporto a [Gestione certificati per](certificate-manager.md) l'uso dei certificati con estensione pfx. Quando gli utenti passano **Impostazioni** certificati & di sicurezza e seleziona Installa un certificato l'interfaccia utente ora  >    >  supporta il file di certificato con estensione pfx. 
Gli utenti possono importare il certificato con estensione pfx, con chiave privata, nell'archivio utenti o nell'archivio computer.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Visualizzare il report di diagnostica avanzato in Impostazioni in HoloLens

Per i dispositivi gestiti durante la risoluzione dei problemi, verificare che sia applicata una configurazione dei criteri prevista è un passaggio importante. In precedenza per questa nuova funzionalità, la visualizzazione di queste informazioni doveva essere eseguita fuori dal dispositivo tramite MDM o vicino al dispositivo dopo l'esportazione dei log di diagnostica MDM raccolti tramite gli account **Impostazioni** Accesso all'istituto di istruzione o all'istituto di istruzione e selezionare Esporta i log di gestione e visualizzati in un PC nelle  ->    >  vicinanze. 

È ora possibile visualizzare la diagnostica MDM nel dispositivo usando il browser Edge. Per visualizzare più facilmente il report di diagnostica MDM, passare alla pagina Accesso aziendale o dell'istituto di istruzione e selezionare **Visualizza report di diagnostica avanzato**. Verrà generato e aperto il report in una nuova finestra di Edge.

![Visualizzare il report di diagnostica avanzato nell Impostazioni app.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Notifiche di diagnostica offline

Si tratta di un aggiornamento per una funzionalità esistente denominata [Diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics). In precedenza, non era presente alcun indicatore chiaro per gli utenti che avevano attivato la raccolta diagnostica o che era stata completata.
A questo punto, Windows build Insider, sono disponibili due forme di feedback visivo per la diagnostica offline. Il primo è notifiche di tipo avviso popup visualizzate sia per l'avvio che per il completamento della raccolta. Verranno visualizzati quando l'utente è connesso e dispone di oggetti visivi.

![Avviso popup per la raccolta di log.](./images/logcollection1.jpg)

![Avviso popup al termine della raccolta dei log.](./images/logcollection2.jpg)

Poiché spesso gli utenti usano la diagnostica offline come meccanismo di raccolta dei log di fallback per quando non hanno accesso a una visualizzazione, non possono accedere o sono ancora nella configurazione guidata. Verrà inoltre riprodotto un segnale audio quando vengono raccolti i log. Questo suono verrà riprodotto oltre alla notifica di tipo avviso popup.

Questa nuova funzionalità verrà abilitata quando il dispositivo viene aggiornato e non deve essere abilitata o gestita. Nel caso in cui questo nuovo feedback non possa essere visualizzato o non sia stato ricevuto, verrà comunque generata la diagnostica offline.

Ci auguriamo che con questa aggiunta più recente di commenti e suggerimenti audio-video sia più facile raccogliere dati di diagnostica e più rapidamente essere in grado di risolvere i problemi.

### <a name="low-storage-log-collection-improvements"></a>Miglioramenti della raccolta di log di archiviazione insufficiente

Negli scenari in cui un dispositivo sembra avere spazio su disco insufficiente quando vengono raccolti i log di diagnostica, verrà creato un report aggiuntivo denominatoStorageDiagnostics.zip **dati.** La soglia di spazio di archiviazione insufficiente viene determinata automaticamente dal Windows [di archiviazione.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="csp-changes-for-reporting-hololens-details"></a>Modifiche CSP per la creazione di report HoloLens dettagli

- Introdotto nella Windows Insider, 20348.1403

I CSP seguenti sono stati aggiornati con nuovi modi per segnalare le informazioni dai HoloLens dispositivi.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - Versione Archiviazione

DevDetail CSP ora segnala anche lo spazio di archiviazione disponibile HoloLens dispositivo. Dovrebbe corrispondere approssimativamente al valore visualizzato nella Impostazioni dell'app Archiviazione app. Di seguito è riportato il nodo specifico contenente queste informazioni.

- ./DevDetail/Ext/Microsoft/FreeStorage (solo operazione GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>Provider di servizi di configurazione DeviceStatus - SSID e BSSID

Il provider di servizi di configurazione DeviceStatus ora segnala anche SSID e BSSID Wi-Fi rete con cui HoloLens è attivamente connessa. Di seguito sono riportati i nodi specifici contenenti queste informazioni.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*indirizzo mac* Wi-Fi adapter /SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*indirizzo mac* della Wi-Fi/BSSID

Blob syncml di esempio (per i fornitori MDM) per eseguire una query per NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Criteri di accesso automatico controllati da CSP

Questo nuovo criterio AutoLogonUser controlla se un utente verrà connesso automaticamente. Alcuni clienti vogliono configurare dispositivi associati a un'identità, ma che non vogliono alcuna esperienza di accesso. Imagine il ritiro di un dispositivo e l'uso immediato di Assistenza remota. Oppure avere il vantaggio di poter distribuire rapidamente i dispositivi HoloLens e consentire agli utenti finali di accelerare l'accesso.

Quando il criterio è impostato su un valore non vuoto, specifica l'indirizzo di posta elettronica dell'utente che esegue l'accesso automatico. L'utente specificato deve accedere al dispositivo almeno una volta per abilitare l'accesso automatico.

URI OMA del nuovo valore string `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` dei criteri

- Per l'utente con lo stesso indirizzo di posta elettronica sarà abilitato l'accesso automatico.

In un dispositivo in cui è configurato questo criterio, l'utente specificato nei criteri dovrà eseguire l'accesso almeno una volta. I successivi riavvii del dispositivo dopo il primo accesso avranno l'utente specificato connesso automaticamente. È supportato un solo utente con accesso automatico. Una volta abilitato, l'utente connesso automaticamente non sarà in grado di disconnettersi manualmente. Per accedere come utente diverso, i criteri devono prima essere disabilitati.

> [!NOTE]
>
> - Alcuni eventi, ad esempio gli aggiornamenti principali del sistema operativo, possono richiedere all'utente specificato di accedere di nuovo al dispositivo per riprendere il comportamento di accesso automatico.
> - L'accesso automatico è supportato solo per gli utenti msa e AAD.

### <a name="improved-update-restart-detection-and-notifications"></a>Miglioramento del rilevamento del riavvio degli aggiornamenti e delle notifiche

Tra l'orario di attività e i criteri dell'ora di installazione, è possibile evitare il riavvio HoloLens dispositivi quando sono in uso. Tuttavia, potrebbe anche ritardare l'adozione degli aggiornamenti se non si verificano riavvii per completare l'installazione di un aggiornamento necessario. Sono stati ora aggiunti criteri per consentire all'IT di applicare scadenze e riavvii necessari e garantire che l'installazione di un aggiornamento sia stata completata in modo corretto. Gli utenti possono ricevere una notifica prima dell'avvio del riavvio e possono ritardare il riavvio in base ai criteri IT.

Sono stati aggiunti i criteri di aggiornamento seguenti:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="smart-retry-for-app-updates"></a>Ripetizione intelligente dei tentativi per gli aggiornamenti dell'app

Ora abilitato per HoloLens è un nuovo criterio che consente agli amministratori IT di impostare una data ricorrente o una data di riavvio per riavviare le app il cui aggiornamento non è riuscito perché l'app è in uso consentendo l'applicazione dell'aggiornamento. Questi possono essere impostati in base ad alcuni trigger diversi, ad esempio un orario pianificato o l'accesso. Per altre informazioni su come usare questa visualizzazione dei [criteri, vedere ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Usare solo app dello Store privato per Microsoft Store

Il criterio RequirePrivateStoreOnly è stato abilitato per HoloLens. Questo criterio consente di configurare Microsoft Store app per mostrare solo lo store privato configurato per l'organizzazione. Limitare l'accesso solo alle app rese disponibili.

Altre informazioni su [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="use-wdac-and-lob-apps"></a>Usare le app WDAC e LOB

È ora possibile usare WDAC per bloccare l'avvio di app o processi e continuare a usare la propria linea di app. È ora possibile consentirle nei criteri di WDAC. L'uso di questo criterio comporta l'esecuzione di una riga di codice aggiuntiva in PowerShell durante la creazione dei criteri wdac. [Esaminare i passaggi qui.](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>Correzioni e miglioramenti

- È stato [risolto un problema noto per Portale di dispositivi non era presente alcuna richiesta di download dei file bloccati.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- È stato risolto [un problema noto per Portale di dispositivi di caricamento e download di file.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Risolve i problemi relativi alla segnalazione delle proprietà di conformità HoloLens dispositivi; Potrebbe essere necessario un riavvio per attivare la segnalazione corretta nelle build Insider.  
- È stata [abilitata un'API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) di accesso assegnato in modo che le app possano ora determinare se un HoloLens è in esecuzione in modalità tutto schermo per l'utente connesso al HoloLens.
- È stata aggiornata la versione di Remote Assist installata in flash aggiornati.

## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider

> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
>
> - Il comando vocale "Riavvia il dispositivo" funziona correttamente.
> - È anche possibile scegliere il pulsante di riavvio Impostazioni/Windows Programma Insider.
>
> È stato rilevato un bug nel back-end che potrebbe essere stato rilevato e che in questo modo si torna a tracciare.

In un dispositivo HoloLens 2 passare a **Impostazioni**  >  **Aggiornamento & sicurezza**  >  **Windows Programma Insider** e **selezionare Inizia.** Collegare l'account usato per la registrazione come Windows Insider.

Windows insider sta passando ai canali. L'anello veloce diventerà il  **canale di** sviluppo, l'anello lento  diventerà l'Canale beta e l'anello di anteprima della versione diventerà **il canale di anteprima della versione.**   Ecco l'aspetto del mapping:

![Windows Spiegazione dei canali Insider](images/WindowsInsiderChannels.png)

Per altre informazioni, vedere [Introducing Windows Insider Channels (Introduzione Windows Insider)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows Blog.
Selezionare quindi **Sviluppo attivo di** Windows , scegliere se si desidera ricevere dev **channel** o build **Canale beta** ed esaminare le condizioni del programma.
Selezionare **Conferma > Riavvia ora** per completare l'operazione. Dopo il riavvio del dispositivo, passare a Update **Impostazioni > & Security > Check for updates to** get the latest build (Verificare la disponibilità di aggiornamenti per ottenere la build più recente).

### <a name="update-error-0x80070490-work-around"></a>Risolvere i 0x80070490 errore

Se si verifica un errore di 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema seguente a breve termine. Comporta lo spostamento del canale Insider, il ritiro dell'aggiornamento e quindi lo spostamento del canale Insider.

#### <a name="stage-one---release-preview"></a>Fase 1 - Versione di anteprima

1. Impostazioni, Update & Security (Sicurezza Windows Programma Insider) selezionare **Release Preview Channel (Canale di anteprima versione).**

2. Impostazioni, Update & Security, Windows Update, **Check for updates**. Dopo l'aggiornamento, passare alla fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Canale di sviluppo

1. Impostazioni, Update & Security (Windows Programma Insider Sicurezza) selezionare **Dev Channel (Canale di sviluppo).**

2. Impostazioni, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>Istruzioni flash e download FFU

Per eseguire il test con un volo firmato ffu, devi prima sbloccare il dispositivo prima di eseguire il flashing del volo firmato ffu.

1. Nel PC:
    1. Scaricare ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installare ARC (Advanced Recovery Companion) dal Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. In HoloLens - Flight Unlock: **aprire** Impostazioni  >  **Update & Security**  >  **Windows Programma Insider** quindi iscriversi e riavviare il dispositivo.

1. Flash FFU: ora è possibile eseguire il flash del volo firmato FFU usando ARC.

### <a name="provide-feedback-and-report-issues"></a>Inviare commenti e suggerimenti e segnalare i problemi

Usare [l'app Hub di Feedback nel](hololens-feedback.md) HoloLens per inviare commenti e suggerimenti e segnalare i problemi. L Hub di Feedback garantisce che siano incluse tutte le informazioni di diagnostica necessarie per consentire ai tecnici di eseguire rapidamente il debug e risolvere il problema.  I problemi relativi alla versione cinese e giapponese HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurarsi di accettare il prompt che chiede se si desidera Hub di Feedback accedere alla cartella Documenti (selezionare **Sì** quando richiesto).

## <a name="note-for-developers"></a>Nota per gli sviluppatori

Si è invitati a provare a sviluppare applicazioni usando build Insider di HoloLens.  Per [iniziare, HoloLens per](https://developer.microsoft.com/windows/mixed-reality/development) sviluppatori. Queste stesse istruzioni funzionano con le build Insider di HoloLens.  È possibile usare le stesse build di Unity e Visual Studio già in uso per lo HoloLens sviluppo.

## <a name="stop-receiving-insider-builds"></a>Interrompere la ricezione di build Insider

Se non si vogliono più ricevere build Insider di Windows Holographic, è possibile rifiutare esplicitamente quando [](hololens-recovery.md) il HoloLens esegue una build di produzione oppure è possibile ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo a una versione non Insider di Windows Holographic.

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che annullano la registrazione dalle compilazioni Insider Preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu. Successivamente, devono ripristinare manualmente il dispositivo. Per informazioni dettagliate complete su se si sarebbe stati o meno influenzati, vedere altre informazioni su [questo problema noto.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Per verificare che il HoloLens sia in esecuzione una build di produzione:

1. Passare a **Impostazioni > sistema > informazioni su** e trovare il numero di build.

1. [Vedere le note sulla versione per i numeri di build di produzione](hololens-release-notes.md).

Per rifiutare esplicitamente le build Insider:

1. In un HoloLens esecuzione di una build di produzione passare a Impostazioni > Aggiornamento & **sicurezza > Windows Programma Insider** e selezionare **Arresta** compilazioni Insider .

1. Seguire le istruzioni per rifiutare esplicitamente il dispositivo.
