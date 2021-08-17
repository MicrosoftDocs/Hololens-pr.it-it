---
title: Insider Preview per Microsoft HoloLens
description: Informazioni su come iniziare a usare le build Insider e fornire feedback prezioso per il prossimo aggiornamento principale del sistema operativo per HoloLens.
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
ms.date: 08/19/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 3ccb9d0f7175a358262c39c76d364aee464c5469
ms.sourcegitcommit: e2a3e85882b7c594d73d08fbd7ae85856d22f8c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2021
ms.locfileid: "122213911"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuti alle build Insider Preview più recenti per HoloLens! È facile iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) prezioso per il prossimo aggiornamento principale del sistema operativo per HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Note sulla versione Insider

Siamo molto contenti di iniziare a creare nuove funzionalità per Windows Insider. Le nuove build verranno aggiornate ai canali Dev e Beta per gli aggiornamenti più recenti. Questa pagina continuerà ad essere aggiornata man appena verranno aggiunti altri aggiornamenti e funzionalità alle build Windows Insider. Prepararsi a combinare questi aggiornamenti nella realtà.

| Funzionalità                 | Descrizione                | Utente o scenario | Build introdotta |
|-------------------------|----------------------------|--------------|------------------|
| [Modifiche CSP per la creazione di report HoloLens dettagli](#csp-changes-for-reporting-hololens-details) | Nuovi CSP per per eseguire query sui dati | Amministratori IT    | 20348.1403                 |
| [Criteri di accesso automatico controllati da CSP](#auto-login-policy-controlled-by-csp) | Usato per accedere automaticamente a un account | Amministratori IT | 20348.1405 |
| [Miglioramento del rilevamento del riavvio degli aggiornamenti e delle notifiche](#improved-update-restart-detection-and-notifications) | Nuovi controlli abilitati e esperienza utente per gli aggiornamenti. | Amministratori IT | 20348.1405 |
| [Supporto di file PFX per Gestione certificati](#pfx-file-support-for-certificate-manager) | Aggiungere certificati PFX tramite l'Impostazioni utente | Utente finale | 20348.1405 |
| [Ripetizione intelligente dei tentativi per gli aggiornamenti dell'app](#smart-retry-for-app-updates) | Consente agli amministratori IT di eseguire tentativi pianificati per aggiornare le app. | Amministratori IT | 20348.1405 |
| [Visualizzare il report di diagnostica avanzato Impostazioni in HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Visualizzare i log di diagnostica MDM nel dispositivo | Risoluzione dei problemi | 20348.1405 |
| [Notifiche di diagnostica offline](#offline-diagnostics-notifications) | Commenti e suggerimenti audio-video per la raccolta di log | Risoluzione dei problemi | 20348.1405 |
| [Usare solo app dello Store privato solo per Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configurare l'app dello Store in modo da visualizzare solo le app dell'organizzazione | Amministratore IT | 20348.1408 |
| [Miglioramenti della raccolta di log di archiviazione insufficiente](#low-storage-log-collection-improvements) | Miglioramenti agli scenari di raccolta dei log in situazioni di archiviazione insufficiente. | Amministratore IT | 20348.1412 |
| [Spostamento della modalità piattaforma](#moving-platform-mode) | Introduce la versione beta della modalità della piattaforma mobile, che, se configurata, consente l'uso di HoloLens 2 in grandi quantità di movimento dinamico. | Tutti | 20348.1411 |
| [Correzioni e miglioramenti](#fixes-and-improvements) | Correzioni e miglioramenti per HoloLens. | Tutti | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>Modifiche CSP per la creazione di report HoloLens dettagli

- Introdotto nella Windows Insider, 20348.1403

I CSP seguenti sono stati aggiornati con nuovi modi per segnalare le informazioni dai HoloLens dispositivi.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - Versione Archiviazione

DevDetail CSP ora segnala anche lo spazio di archiviazione disponibile HoloLens dispositivo. Dovrebbe corrispondere approssimativamente al valore visualizzato nella pagina Impostazioni'app Archiviazione app. Di seguito è riportato il nodo specifico contenente queste informazioni.

- ./DevDetail/Ext/Microsoft/FreeStorage (solo operazione GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>Provider di servizi di configurazione DeviceStatus - SSID e BSSID

Il provider di servizi di configurazione DeviceStatus ora segnala anche SSID e BSSID Wi-Fi rete con cui HoloLens è attivamente connessa. Di seguito sono riportati i nodi specifici contenenti queste informazioni.

- Indirizzo mac ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*della scheda Wi-Fi*/SSID
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

Tra l'orario di attività e i criteri per l'ora di installazione, è possibile evitare il riavvio HoloLens dispositivi quando sono in uso. Tuttavia, potrebbe anche ritardare l'adozione degli aggiornamenti se non si verificano riavvii per completare l'installazione di un aggiornamento necessario. Sono stati ora aggiunti criteri per consentire all'IT di applicare scadenze e riavvii necessari e garantire che l'installazione di un aggiornamento sia stata completata in modo corretto. Gli utenti possono ricevere una notifica prima dell'avvio del riavvio e possono ritardare il riavvio in base ai criteri IT.

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

### <a name="pfx-file-support-for-certificate-manager"></a>Supporto di file PFX per Gestione certificati

Introdotto in Windows Insider build 20348.1405. È stato aggiunto il supporto a [Gestione certificati per](certificate-manager.md) l'uso dei certificati con estensione pfx. Quando gli utenti passano **a Impostazioni** i & di sicurezza e seleziona Installa un certificato l'interfaccia utente ora  >    >  supporta il file di certificato con estensione pfx. 
Gli utenti possono importare il certificato con estensione pfx, con chiave privata, nell'archivio utenti o nell'archivio computer.

### <a name="smart-retry-for-app-updates"></a>Nuovo tentativo intelligente per gli aggiornamenti dell'app

Ora abilitato per HoloLens è un nuovo criterio che consente agli amministratori IT di impostare una data ricorrente o una data di riavvio per riavviare le app il cui aggiornamento non è riuscito a causa dell'app in uso che consente l'applicazione dell'aggiornamento. Questi valori possono essere impostati in base ad alcuni trigger diversi, ad esempio un'ora pianificata o l'accesso. Per altre informazioni su come usare questo criterio, vedere [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Visualizzare il report di diagnostica avanzato in Impostazioni in HoloLens

Per i dispositivi gestiti durante la risoluzione dei problemi, verificare che sia applicata una configurazione dei criteri prevista è un passaggio importante. In precedenza questa nuova funzionalità doveva essere eseguita fuori dal dispositivo tramite MDM o vicino al dispositivo dopo l'esportazione dei log di diagnostica MDM raccolti tramite gli account **Impostazioni** Accesso aziendale o dell'istituto di istruzione e selezionare Esporta i log di gestione e visualizzato in un PC nelle  ->    >  vicinanze. 

È ora possibile visualizzare la diagnostica MDM nel dispositivo usando il browser Edge. Per visualizzare più facilmente il report di diagnostica MDM, passare alla pagina Accedi all'istituto di istruzione o all'istituto di istruzione e selezionare **Visualizza report di diagnostica avanzato.** Verrà generato e aperto il report in una nuova finestra di Edge.

![Visualizzare il report di diagnostica avanzato nell Impostazioni app.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Notifiche di diagnostica offline

Si tratta di un aggiornamento per una funzionalità esistente denominata [Diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics). In precedenza, non era presente alcun indicatore chiaro per gli utenti che avevano attivato la raccolta diagnostica o che era stata completata.
A questo punto, Windows build insider, sono disponibili due forme di feedback visivo per la diagnostica offline. Il primo è notifiche di tipo avviso popup visualizzate sia per l'avvio che per il completamento della raccolta. Verranno visualizzati quando l'utente è connesso e dispone di oggetti visivi.

![Avviso popup per la raccolta di log.](./images/logcollection1.jpg)

![Avviso popup al termine della raccolta dei log.](./images/logcollection2.jpg)

Poiché spesso gli utenti usano la diagnostica offline come meccanismo di raccolta dei log di fallback per quando non hanno accesso a una visualizzazione, non possono accedere o sono ancora nella configurazione guidata. Verrà inoltre riprodotto un segnale audio quando vengono raccolti i log. Questo suono verrà riprodotto oltre alla notifica di tipo avviso popup.

Questa nuova funzionalità verrà abilitata quando il dispositivo viene aggiornato e non deve essere abilitata o gestita. In qualsiasi caso in cui questo nuovo feedback non possa essere visualizzato o ascoltato, la diagnostica offline verrà comunque generata.

Con questa aggiunta più recente di commenti e suggerimenti per l'audio è più facile raccogliere dati di diagnostica e risolvere più rapidamente i problemi.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Usare solo app dello Store privato per Microsoft Store

Il criterio RequirePrivateStoreOnly è stato abilitato per HoloLens. Questo criterio consente di Microsoft Store'app per visualizzare solo l'archivio privato configurato per l'organizzazione. Limitazione dell'accesso solo alle app rese disponibili.

Altre informazioni [su ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Miglioramenti della raccolta di log di archiviazione a basso livello

Negli scenari in cui lo spazio su disco di un dispositivo  sembra insufficiente quando vengono raccolti i log di diagnostica, verrà creato un report aggiuntivo denominatoStorageDiagnostics.zipdati. La soglia di spazio di archiviazione basso viene determinata automaticamente dal Windows [di archiviazione.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="moving-platform-mode"></a>Spostamento della modalità piattaforma

A data **della build Insider 20348.1411** è stato aggiunto il supporto beta per il rilevamento di piattaforme con movimento basso dinamico in HoloLens 2. Dopo aver installato la build e aver abilitato la modalità piattaforma mobile, sarà possibile usare il HoloLens 2 in ambienti inaccessibili in precedenza, ad esempio grandi navi e navi di grandi dimensioni. Attualmente, la funzionalità è destinata ad abilitare solo queste piattaforme in movimento specifiche. Anche se nulla impedisce di provare a usare la funzionalità in altri ambienti, la funzionalità è incentrata sull'aggiunta del supporto per questi ambienti.

Per altre informazioni su ciò che è supportato e su come è abilitata questa nuova funzionalità, [visitare la pagina della piattaforma mobile.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>Correzioni e miglioramenti

- È stato risolto un problema noto per Portale di dispositivi il download dei file bloccati [non era richiesto.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- È stato risolto un problema noto per Portale di dispositivi timeout di caricamento e [download di file.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Risolve i problemi relativi alla segnalazione delle proprietà di conformità HoloLens dispositivi; Potrebbe essere necessario un riavvio per attivare la segnalazione corretta nelle build Insider.  
- È stata [abilitata un'API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) Di accesso assegnato in modo che le app possano ora determinare se un HoloLens è in esecuzione in modalità tutto schermo per l'utente connesso alla HoloLens.
- È stata aggiornata la versione di Remote Assist installata in flash nuovi.

## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider

> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
>
> - Il comando vocale "Riavvia il dispositivo" funziona correttamente.
> - È anche possibile scegliere il pulsante di riavvio Impostazioni/Windows Programma Insider.
>
> Si è verificato un bug nel back-end che potrebbe essere stato rilevato e ciò consente di tornare in funzione.

In un dispositivo HoloLens 2 passare **a**  >  **Impostazioni aggiornamento & sicurezza**  >  **Windows Programma Insider** e selezionare **Introduzione.** Collegare l'account usato per la registrazione come Windows Insider.

Windows insider sta ora passando a Canali. L'anello veloce diventerà dev  **channel,** l'anello  lento diventerà l'Canale beta e l'anello di anteprima della versione diventerà il canale di anteprima della **versione.**   Ecco l'aspetto del mapping:

![Windows Spiegazione dei canali insider](images/WindowsInsiderChannels.png)

Per altre informazioni, vedere [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introduzione ai canali Insider Windows Blog).
Selezionare quindi **Sviluppo attivo di** Windows, scegliere se si desidera ricevere  dev **channel** o build Canale beta ed esaminare le condizioni del programma.
Selezionare **Conferma > riavvia ora** per completare l'operazione. Dopo il riavvio del dispositivo, passare Impostazioni > **aggiornamento & sicurezza** > verificare la disponibilità di aggiornamenti per ottenere la build più recente.

### <a name="update-error-0x80070490-work-around"></a>Risolvere i 0x80070490 errore di aggiornamento

Se si verifica un errore di 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema a breve termine seguente. Comporta lo spostamento del canale Insider, la raccolta dell'aggiornamento e quindi il ritorno del canale Insider.

#### <a name="stage-one---release-preview"></a>Fase 1 - Versione di anteprima

1. Impostazioni, Aggiornare & Security, Windows Programma Insider, selezionare **Release Preview Channel (Canale di anteprima versione).**

2. Impostazioni, Update & Security, Windows Update, **Check for updates**. Dopo l'aggiornamento, passare alla fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev Channel

1. Impostazioni, Aggiornare & Security, Windows Programma Insider, selezionare Dev **Channel**.

2. Impostazioni, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>Istruzioni flash e download FFU

Per testare con un volo firmato ffu, è prima necessario sbloccare il dispositivo prima di lampeggiare il volo firmato ffu.

1. Nel PC:
    1. Scaricare ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installare ARC (Advanced Recovery Companion) dal Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. In HoloLens - Flight Unlock: **aprire** Impostazioni update &  >  **Security**  >  **Windows Programma Insider** quindi iscriversi e riavviare il dispositivo.

1. Flash FFU: ora è possibile eseguire il flash del volo firmato FFU usando ARC.

### <a name="provide-feedback-and-report-issues"></a>Inviare commenti e suggerimenti e segnalare i problemi

Usare [l'app Hub di Feedback nel](hololens-feedback.md) HoloLens per inviare commenti e suggerimenti e segnalare i problemi. L Hub di Feedback garantisce che siano incluse tutte le informazioni di diagnostica necessarie per consentire ai tecnici di eseguire rapidamente il debug e risolvere il problema.  I problemi relativi alla versione cinese e giapponese HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurarsi di accettare il prompt che chiede se si desidera Hub di Feedback accedere alla cartella Documenti (selezionare **Sì** quando richiesto).

## <a name="note-for-developers"></a>Nota per gli sviluppatori

Si è invitati a provare a sviluppare applicazioni usando build Insider di HoloLens.  Per [iniziare, HoloLens per](https://developer.microsoft.com/windows/mixed-reality/development) sviluppatori. Queste stesse istruzioni funzionano con le build Insider di HoloLens.  È possibile usare le stesse build di Unity e Visual Studio che si sta già usando per HoloLens sviluppo.

## <a name="stop-receiving-insider-builds"></a>Interrompere la ricezione di build Insider

Se non si vogliono più ricevere build Insider di Windows Holographic, è possibile rifiutare esplicitamente quando il [](hololens-recovery.md) HoloLens esegue una build di produzione oppure è possibile ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo a una versione non Insider di Windows Holographic.

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che annullano la registrazione dalle compilazioni Insider Preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu. Successivamente, devono ripristinare manualmente il dispositivo. Per informazioni dettagliate complete su se si sarebbe o meno in grado di influire, vedere altre informazioni su [questo problema noto.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Per verificare che il HoloLens sia in esecuzione una build di produzione:

1. Passare a **Impostazioni > sistema > informazioni su** e trovare il numero di build.

1. [Vedere le note sulla versione per i numeri di build di produzione](hololens-release-notes.md).

Per rifiutare esplicitamente le build Insider:

1. In un HoloLens di una build di produzione passare a Impostazioni > **Update & Security > Windows Programma Insider** e selezionare Stop Insider builds (Arresta **compilazioni Insider).**

1. Seguire le istruzioni per rifiutare esplicitamente il dispositivo.
