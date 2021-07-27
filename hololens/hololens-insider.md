---
title: Insider Preview per Microsoft HoloLens
description: Informazioni su come iniziare a usare le build Insider e fornire feedback preziosi per il prossimo aggiornamento principale del sistema operativo per HoloLens.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b7e5a7cbaa746f58fe0344dd8bf5b027e2e8cea7
ms.sourcegitcommit: dc5d6f3802c997749775be04de522af8cb6d0850
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2021
ms.locfileid: "114693706"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuti alle build insider preview più recenti per HoloLens! È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Note sulla versione insider

Siamo entusiasti di iniziare a eseguire il volo di nuove funzionalità per Windows Insider. Le nuove build verranno aggiornate ai canali Dev e Beta per gli aggiornamenti più recenti. Questa pagina continuerà ad essere aggiornata quando si aggiungono altre funzionalità e aggiornamenti alle build Windows Insider. Prepararsi a combinare questi aggiornamenti nella realtà.

| Funzionalità                 | Descrizione                | Utente o scenario | Build introdotta |
|-------------------------|----------------------------|--------------|------------------|
| [Modifiche di CSP per la creazione di report HoloLens dettagli](#csp-changes-for-reporting-hololens-details) | Nuovi CSP per eseguire query sui dati | Amministratori IT    | 20348.1403                 |
| [Criteri di accesso automatico controllati da CSP](#auto-login-policy-controlled-by-csp) | Usato per accedere automaticamente a un account | Amministratori IT | 20348.1405 |
| [Supporto di file PFX per Gestione certificati](#pfx-file-support-for-certificate-manager) | Aggiungere certificati PFX tramite l'interfaccia Impostazioni utente | Utente finale | 20348.1405 |
| [Visualizzare il report di diagnostica avanzato in Impostazioni in HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Visualizzare i log di diagnostica MDM nel dispositivo | Risoluzione dei problemi | 20348.1405 |
| [Notifiche di diagnostica offline](#offline-diagnostics-notifications) | Commenti e suggerimenti per l'audiovisual per la raccolta di log | Risoluzione dei problemi | 20348.1405 |
| [Usare solo app dello Store privato solo per Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configurare l'app dello Store per visualizzare solo le app dell'organizzazione | Amministratore IT | 20348.1408 |
| [Correzioni e miglioramenti](hololens-insider.md#fixes-and-improvements) | Correzioni e miglioramenti per HoloLens. | Tutti | 20348.1408 |

### <a name="csp-changes-for-reporting-hololens-details"></a>Modifiche di CSP per la creazione di report HoloLens dettagli

- Introduzione alla Windows Insider, 20348.1403

I CSP seguenti sono stati aggiornati con nuovi modi per segnalare le informazioni dai HoloLens dispositivi.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - Versione Archiviazione

DevDetail CSP ora segnala anche lo spazio di archiviazione disponibile HoloLens dispositivo. Dovrebbe corrispondere approssimativamente al valore visualizzato nella pagina Impostazioni'app Archiviazione app. Di seguito è riportato il nodo specifico contenente queste informazioni.

- ./DevDetail/Ext/Microsoft/FreeStorage (solo operazione GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>CSP DeviceStatus - SSID e BSSID

DeviceStatus CSP ora segnala anche SSID e BSSID Wi-Fi rete con cui HoloLens è attivamente connesso. Di seguito sono riportati i nodi specifici contenenti queste informazioni.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac *address of Wi-Fi adapter*/BSSID

BLOB syncml di esempio (per i fornitori MDM) per eseguire query per NetworkIdentifiers

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

Questo nuovo criterio AutoLogonUser controlla se un utente verrà connesso automaticamente. Alcuni clienti vogliono configurare dispositivi associati a un'identità ma che non vogliono alcuna esperienza di accesso. Imagine il ritiro di un dispositivo e l'uso immediato dell'assistenza remota. Oppure avere il vantaggio di poter distribuire rapidamente i dispositivi HoloLens e consentire agli utenti finali di velocizzare l'accesso.

Quando il criterio è impostato su un valore non vuoto, specifica l'indirizzo di posta elettronica dell'utente con accesso automatico. L'utente specificato deve accedere al dispositivo almeno una volta per abilitare l'accesso automatico.

URI OMA del nuovo valore string `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` dei criteri

- L'utente con lo stesso indirizzo di posta elettronica avrà l'accesso automatico abilitato.

In un dispositivo in cui è configurato questo criterio, l'utente specificato nei criteri dovrà accedere almeno una volta. I successivi riavvii del dispositivo dopo il primo accesso avranno l'utente specificato connesso automaticamente. È supportato un solo utente di accesso automatico. Una volta abilitato, l'utente connesso automaticamente non sarà in grado di disconnettersi manualmente. Per eseguire l'accesso come utente diverso, è prima necessario che i criteri siano disabilitati.

> [!NOTE]
> - Alcuni eventi, ad esempio gli aggiornamenti principali del sistema operativo, potrebbero richiedere all'utente specificato di accedere di nuovo al dispositivo per riprendere il comportamento di accesso automatico. 
> - L'accesso automatico è supportato solo per gli utenti msa e AAD.

### <a name="pfx-file-support-for-certificate-manager"></a>Supporto di file PFX per Gestione certificati

Introdotto in Windows Insider build 20348.1405. È stato aggiunto il supporto a [Gestione certificati per](certificate-manager.md) l'uso dei certificati con estensione pfx. Quando gli utenti passano **a Impostazioni** certificati di & di sicurezza e selezionare Installa un certificato l'interfaccia utente ora supporta il file di certificato con estensione  >    >  pfx. 
Gli utenti possono importare il certificato con estensione pfx, con chiave privata, nell'archivio utenti o nell'archivio computer.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Visualizzare il report di diagnostica avanzato in Impostazioni in HoloLens

Per i dispositivi gestiti durante la risoluzione dei problemi, verificare che sia applicata una configurazione dei criteri prevista è un passaggio importante. In precedenza questa nuova funzionalità doveva essere eseguita tramite MDM o vicino al dispositivo dopo l'esportazione dei log di diagnostica MDM raccolti tramite gli account Impostazioni Accedi **all'istituto** di istruzione o all'istituto di istruzione e seleziona Esporta i log di gestione e visualizzato in un PC nelle  ->    >  vicinanze. 

È ora possibile visualizzare la diagnostica MDM nel dispositivo usando il browser Edge. Per visualizzare più facilmente il report di diagnostica MDM, passare alla pagina Accedi all'istituto di istruzione o all'istituto di istruzione e selezionare **Visualizza report di diagnostica avanzato.** Verrà generato e aperto il report in una nuova finestra di Edge.

![Visualizzare il report di diagnostica avanzato nell Impostazioni app.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Notifiche di diagnostica offline

Si tratta di un aggiornamento per una funzionalità esistente denominata [Diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics). In precedenza, non era presente alcun indicatore chiaro per gli utenti che avevano attivato la raccolta diagnostica o che era stata completata.
A questo punto, Windows build insider, sono disponibili due forme di feedback visivo per la diagnostica offline. Il primo è notifiche di tipo avviso popup visualizzate sia all'avvio che al completamento della raccolta. Verranno visualizzati quando l'utente è connesso e dispone di oggetti visivi.

![Avviso popup per la raccolta di log.](./images/logcollection1.jpg)

![Avviso popup al termine della raccolta dei log.](./images/logcollection2.jpg)
 
Poiché gli utenti usano spesso La diagnostica offline come meccanismo di raccolta dei log di fallback per quando non hanno accesso a una visualizzazione, non possono accedere o sono ancora in Configurazione guidata. Verrà inoltre riprodotto un segnale audio quando vengono raccolti i log. Questo suono verrà riprodotto oltre alla notifica di tipo avviso popup.

Questa nuova funzionalità verrà abilitata quando il dispositivo viene aggiornato e non deve essere abilitata o gestita. In qualsiasi caso in cui questo nuovo feedback non possa essere visualizzato o ascoltato, la diagnostica offline verrà comunque generata.

Con questa aggiunta più recente di commenti e suggerimenti per l'audio è più facile raccogliere dati di diagnostica e risolvere più rapidamente i problemi.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Usare solo app dello Store privato per Microsoft Store

Il criterio RequirePrivateStoreOnly è stato abilitato per HoloLens. Questo criterio consente all'app Microsoft Store di essere configurata in modo da visualizzare solo l'archivio privato configurato per l'organizzazione. Limitazione dell'accesso solo alle app rese disponibili.

Altre informazioni su [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="fixes-and-improvements"></a>Correzioni e miglioramenti:

- È stato risolto un problema noto per Portale di dispositivi il download dei file bloccati non era [richiesto.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- È stato risolto un problema noto per Portale di dispositivi timeout di caricamento e [download di file.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Risolve i problemi relativi alla segnalazione delle proprietà di conformità HoloLens dispositivi; Potrebbe essere necessario un riavvio per attivare la segnalazione corretta nelle build Insider.  
- È stata aggiornata la versione di Remote Assist installata in flash nuovi.


## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider

> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
> - Il comando vocale "Riavvia il dispositivo" funziona correttamente. 
> - È anche possibile scegliere il pulsante di riavvio in Impostazioni/Windows Programma Insider.
>
> Si è verificato un bug nel back-end che potrebbe essere stato rilevato e ciò consente di tornare in funzione.

In un dispositivo HoloLens 2 passare **a** Impostazioni  >  **aggiornamento & sicurezza**  >  **Windows Programma Insider** selezionare **Introduzione.** Collegare l'account usato per la registrazione come Windows Insider.

Windows insider sta ora passando a Canali. L'anello veloce diventerà dev  **channel,** l'anello  lento diventerà l'Canale beta e l'anello di anteprima della versione diventerà il canale di anteprima della **versione.**   Ecco l'aspetto del mapping:

![Windows Spiegazione dei canali insider](images/WindowsInsiderChannels.png)

Per altre informazioni, vedere [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introduzione Windows Insider Channels Windows Blog).
Selezionare quindi **Sviluppo attivo di** Windows, scegliere se si desidera  ricevere dev **channel** o build Canale beta ed esaminare le condizioni del programma.
Selezionare **Conferma > riavvia ora** per completare l'operazione. Dopo il riavvio del dispositivo, passare Impostazioni > **aggiornamento & sicurezza** > verificare la disponibilità di aggiornamenti per ottenere la build più recente.

### <a name="update-error-0x80070490-work-around"></a>Risolvere i 0x80070490 errore di aggiornamento

Se si verifica un errore di aggiornamento 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema a breve termine seguente. Comporta lo spostamento del canale Insider, la raccolta dell'aggiornamento e quindi il ritorno del canale Insider.

#### <a name="stage-one---release-preview"></a>Fase 1 - Versione di anteprima

1.  Impostazioni, Update & Security, Windows Programma Insider, selezionare **Release Preview Channel (Canale di anteprima versione).**

2.  Impostazioni, Update & Security, Windows Update, Check **for updates**. Dopo l'aggiornamento, passare alla fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev Channel

1. Impostazioni, Aggiornare & Security, Windows Programma Insider selezionare **Dev Channel**.

2. Impostazioni, Update & Security, Windows Update, Check **for updates**.

## <a name="ffu-download-and-flash-directions"></a>Istruzioni flash e download FFU

Per testare con un volo firmato ffu, è prima necessario sbloccare il dispositivo prima di lampeggiare il volo firmato ffu.

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

Se non si vogliono più ricevere build Insider di Windows Holographic, è possibile rifiutare esplicitamente quando il [](hololens-recovery.md) HoloLens esegue una build di produzione oppure è possibile ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo a una versione non Insider di Windows Holographic.

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che annullano la registrazione dalle compilazioni Insider Preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu. Successivamente, devono ripristinare manualmente il dispositivo. Per informazioni dettagliate complete su se si sarebbe o meno in grado di influire, vedere altre informazioni su [questo problema noto.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Per verificare che l'HoloLens sia in esecuzione una build di produzione:

1. Passare a **Impostazioni > sistema > Informazioni su** e trovare il numero di build.

1. [Vedere le note sulla versione per i numeri di build di produzione](hololens-release-notes.md).

Per rifiutare esplicitamente le build Insider:

1. In un HoloLens esecuzione di una build di produzione, passare a Impostazioni > **Update & Security > Windows Programma Insider** e selezionare Stop Insider builds (Arresta **compilazioni Insider).**

1. Seguire le istruzioni per rifiutare esplicitamente il dispositivo.
