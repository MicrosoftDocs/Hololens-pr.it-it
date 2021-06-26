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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977227"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuti nelle build insider preview più recenti per HoloLens. È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.

## <a name="windows-insider-release-notes"></a>partecipante al Programma Windows Insider sulla versione

Siamo molto contenti di iniziare a eseguire nuovamente il volo di nuove funzionalità per Windows Insiders. Le nuove build verranno aggiornate ai canali Dev e Beta per gli aggiornamenti più recenti. Questa pagina continuerà ad essere aggiornata quando si aggiungono altre funzionalità e aggiornamenti alle partecipante al Programma Windows Insider build. Prepararsi a combinare questi aggiornamenti nella realtà.

| Funzionalità                 | Descrizione                | Utenti di destinazione | Build introdotta |
|-------------------------|----------------------------|--------------|------------------|
| Modifiche di CSP in HoloLens | Nuovi CSP per eseguire query sui dati | Amministratori IT    | 20348.1403                 |

### <a name="csp-changes-on-hololens"></a>Modifiche di CSP in HoloLens

- Introduzione alla partecipante al Programma Windows Insider build 20348.1403

#### <a name="devdetail-csp"></a>DevDetail

DevDetail CSP ora segnala anche lo spazio di archiviazione disponibile nel dispositivo HoloLens. Dovrebbe corrispondere approssimativamente al valore visualizzato nella pagina Archiviazione dell'app impostazioni. Di seguito è riportato il nodo specifico contenente queste informazioni.

- ./DevDetail/Ext/Microsoft/FreeStorage (solo operazione GET)

#### <a name="devicestatus-csp"></a>DeviceStatus

DeviceStatus CSP ora segnala anche SSID e BSSID della rete Wi-Fi con cui HoloLens è attivamente connesso. Di seguito sono riportati i nodi specifici contenenti queste informazioni.

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

### <a name="fixes-and-improvements"></a>Correzioni e miglioramenti:

- È stato risolto un problema noto per Portale di dispositivi il download dei file bloccati non era [richiesto.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- È stato risolto un problema noto per Portale di dispositivi timeout di caricamento e [download di file.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider
> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
> - Il comando vocale "Riavvia il dispositivo" funziona correttamente. 
> - È anche possibile scegliere il pulsante di riavvio in Impostazioni/Programma Windows Insider.
>
> Si è verificato un bug nel back-end che potrebbe essere stato rilevato e ciò consente di tornare in funzione.

In un dispositivo HoloLens 2 passare a **Impostazioni** Aggiornamento &  >  **sicurezza**  >  **Programma Windows Insider** e selezionare **Introduzione.** Collegare l'account usato per la registrazione come partecipante al Programma Windows Insider.
Windows Insider sta ora passando ai canali. L'anello veloce diventerà dev  **channel,** l'anello  lento diventerà l'Canale beta e l'anello di anteprima della versione diventerà il canale di anteprima della **versione.**   Ecco l'aspetto del mapping: spiegazione partecipante al Programma Windows Insider canali per altre informazioni, vedere ![ ](images/WindowsInsiderChannels.png) [Introducing partecipante al Programma Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introduzione partecipante al Programma Windows Insider canali nei blog di Windows).
Selezionare quindi **Sviluppo attivo di Windows,** scegliere se si  desidera ricevere dev **channel** o build Canale beta ed esaminare le condizioni del programma.
Selezionare **Conferma > riavvia ora** per completare l'operazione. Dopo il riavvio del dispositivo, passare a Impostazioni **> aggiornamento & sicurezza > verificare** la disponibilità di aggiornamenti per ottenere la build più recente.
### <a name="update-error-0x80070490-work-around"></a>Risolvere i 0x80070490 errore di aggiornamento
Se si verifica un errore di aggiornamento 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema a breve termine seguente. Comporta lo spostamento del canale Insider, la raccolta dell'aggiornamento e quindi il ritorno del canale Insider.
#### <a name="stage-one---release-preview"></a>Fase 1 - Versione di anteprima
1.  Impostazioni, Aggiorna & Sicurezza, Programma Windows Insider, selezionare **Canale di anteprima versione**.
2.  Impostazioni, Update & Security, Windows Update, **Check for updates**. Dopo l'aggiornamento, passare alla fase 2.
#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev Channel
1. Impostazioni, Aggiorna & Sicurezza, Programma Windows Insider, selezionare **Dev Channel**.
2. Impostazioni, Update & Security, Windows Update, **Check for updates**.
## <a name="ffu-download-and-flash-directions"></a>Istruzioni flash e download FFU
Per testare con un volo firmato ffu, è prima necessario sbloccare il dispositivo prima di lampeggiare il volo firmato ffu.
1. Nel PC:
    1. Scaricare ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installare ARC (Advanced Recovery Companion) dal Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. In HoloLens - Flight Unlock: **aprire** l'aggiornamento delle impostazioni & sicurezza Programma Windows Insider quindi iscriversi  >    >   e riavviare il dispositivo.
1. Flash FFU: ora è possibile eseguire il flash del volo firmato FFU usando ARC.
### <a name="provide-feedback-and-report-issues"></a>Inviare commenti e suggerimenti e segnalare i problemi
Usare [l'app Hub di Feedback app](hololens-feedback.md) in HoloLens per inviare commenti e suggerimenti e segnalare i problemi. L Hub di Feedback garantisce che siano incluse tutte le informazioni di diagnostica necessarie per consentire ai tecnici di eseguire rapidamente il debug e risolvere il problema.  I problemi relativi alla versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.
> [!NOTE]
> Assicurarsi di accettare il prompt che chiede se si desidera Hub di Feedback accedere alla cartella Documenti (selezionare **Sì** quando richiesto).
## <a name="note-for-developers"></a>Nota per gli sviluppatori
Si è invitati a provare a sviluppare applicazioni usando build Insider di HoloLens.  Per iniziare, vedere la documentazione per sviluppatori di [HoloLens.](https://developer.microsoft.com/windows/mixed-reality/development) Queste stesse istruzioni funzionano con le build Insider di HoloLens.  È possibile usare le stesse build di Unity e Visual Studio già in uso per lo sviluppo HoloLens.
## <a name="stop-receiving-insider-builds"></a>Interrompere la ricezione di build Insider
Se non si vogliono più ricevere build Insider di Windows Holographic, è possibile rifiutare esplicitamente [](hololens-recovery.md) quando HoloLens esegue una build di produzione oppure è possibile ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo in una versione non Insider di Windows Holographic.
> [!CAUTION]
> Esiste un problema noto in cui gli utenti che annullano la registrazione dalle build insider preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu. Successivamente, devono ripristinare manualmente il dispositivo. Per informazioni dettagliate complete su se si sarebbe o meno in grado di influire, vedere altre informazioni su [questo problema noto.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
Per verificare che HoloLens sia in esecuzione una build di produzione:
1. Passare a **Impostazioni > sistema > Informazioni su** e trovare il numero di build.
1. [Vedere le note sulla versione per i numeri di build di produzione](hololens-release-notes.md).
Per rifiutare esplicitamente le build Insider:
1. In un'istanza di HoloLens che esegue una build di produzione passare a Impostazioni **> Aggiorna**& sicurezza > Programma Windows Insider e selezionare Arresta **compilazioni Insider**.
1. Seguire le istruzioni per rifiutare esplicitamente il dispositivo.
