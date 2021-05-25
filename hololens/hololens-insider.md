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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397822"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuti alle build insider preview più recenti per HoloLens. È facile iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) prezioso per il prossimo aggiornamento principale del sistema operativo per HoloLens.

## <a name="windows-insider-release-notes"></a>partecipante al Programma Windows Insider sulla versione

Siamo molto contenti di iniziare a eseguire di nuovo la distribuzione di nuove funzionalità a Windows Insider. Le nuove build verranno aggiornate ai canali Dev e Beta per gli aggiornamenti più recenti. Questa pagina continuerà ad essere aggiornata man appena verranno aggiunti altri aggiornamenti e funzionalità alle partecipante al Programma Windows Insider build. Prepararsi a combinare questi aggiornamenti nella realtà. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive for work or school Camera Roll upload

*Introdotto nella build 20346.1402*

È stata aggiunta una nuova funzionalità all'app Impostazioni di HoloLens 2, che consente ai clienti di caricare automaticamente foto e video di realtà mista dalla cartella Pictures > Camera Roll del dispositivo alla cartella OneDrive for work o school corrispondente. Questa funzionalità risolve una lacune di funzionalità all'interno [dell'app OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) in HoloLens 2, che supporta solo il caricamento automatico del rullo della fotocamera nel account Microsoft personale di un cliente (e non nell'account aziendale o dell'istituto di istruzione).

**Funzionamento**

- Visitare **Impostazioni > sistema > Fotocamera realtà mista** per abilitare il caricamento della fotocamera.
- Impostando questa funzionalità  sulla posizione Attiva, tutte le foto o i video di realtà mista acquisiti nel dispositivo verranno automaticamente accodati per il caricamento nella cartella Pictures > Camera Roll dell'account OneDrive for work o school.
    >[!NOTE]
    >Le foto e i video acquisiti prima di abilitare questa *funzionalità* non verranno accodati per il caricamento e dovranno comunque essere caricati manualmente.
- Un messaggio di stato nella pagina Impostazioni visualizza il numero di file in attesa di caricamento (o legge "OneDrive è aggiornato" quando tutti i file in sospeso sono stati caricati).
- Se si è interessati alla larghezza di banda o si vuole "sospendere" il caricamento per qualsiasi motivo, è possibile impostare la funzionalità sulla **posizione Disattivato.** La disabilitazione temporanea della funzionalità garantisce che la coda di caricamento continui ad aumentare quando si aggiungono nuovi file alla cartella Camera Roll, ma i file non verranno caricati fino a quando non si ri enablerà la funzionalità.
- I file più recenti verranno caricati per primi (last in, first out).
- Se l'account OneDrive presenta problemi , ad  esempio dopo la modifica della password, nella pagina Impostazioni verrà visualizzato il pulsante Correggi ora.
- Non esistono dimensioni massime dei file, ma si noti che il caricamento di file di grandi dimensioni richiederà più tempo,soprattutto se la larghezza di banda del caricamento è limitata. Se si "sospende" o si disattiva il caricamento durante il caricamento di un file di grandi dimensioni, il caricamento verrà annullato immediatamente. Il caricamento verrà riavviato quando si ribiliterà la funzionalità. Non si perderanno file, ma il caricamento parziale verrà eliminato.

**Problemi noti e avvertenze**

- Questa impostazione non ha limitazioni predefinite in base all'utilizzo corrente della larghezza di banda. Se è necessario ottimizzare la larghezza di banda per un altro scenario, disattivare manualmente l'impostazione. Il caricamento verrà sospeso, ma la funzionalità continuerà a monitorare i file appena aggiunti al rullino. Abilitare nuovamente il caricamento quando si è pronti per continuare.
- Questa funzionalità deve essere abilitata per ogni account utente nel dispositivo e può caricare attivamente solo i file per l'utente che ha eseguito l'accesso al dispositivo.
- Se si stanno scattare foto o video mentre si guarda il numero di caricamenti nella pagina Impostazioni in tempo reale, si noti che il numero di file in sospeso potrebbe non cambiare fino al completamento del caricamento del file corrente.
- Il caricamento verrà sospeso se il dispositivo è in stato di sospensione o è spento. Per assicurarsi che i caricamenti in sospeso siano stati completati, usare attivamente il dispositivo fino a quando la pagina Impostazioni non legge "OneDrive è aggiornato" o modificare le impostazioni **di sospensione & Power** &.

## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider
> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
> - Il comando vocale "Riavvia il dispositivo" funziona correttamente. 
> - È anche possibile scegliere il pulsante di riavvio in Impostazioni/Programma Windows Insider.
>
> Nel back-end è stato rilevato un bug che potrebbe essere stato rilevato e ciò consente di tornare a essere tracciati.

In un dispositivo HoloLens 2 passare a **Impostazioni**  >  **Aggiorna & sicurezza**  >  **Programma Windows Insider** e selezionare **Inizia.** Collegare l'account usato per la registrazione come partecipante al Programma Windows Insider.
Windows Insider sta ora passando ai canali. L'anello veloce diventerà il  **canale di** sviluppo, l'anello lento  diventerà l'Canale beta e l'anello di anteprima della versione diventerà **il canale di anteprima della versione.**   Ecco l'aspetto del mapping: spiegazione partecipante al Programma Windows Insider canali per altre informazioni, vedere ![ ](images/WindowsInsiderChannels.png) [Introducing partecipante al Programma Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introduzione partecipante al Programma Windows Insider canali nei blog di Windows).
Selezionare quindi **Sviluppo attivo di Windows,** scegliere se si  desidera ricevere dev **channel** o build Canale beta ed esaminare le condizioni del programma.
Selezionare **Confirm > Restart Now (Conferma riavvio ora)** per completare l'operazione. Dopo il riavvio del dispositivo, passare a Impostazioni **> Aggiornamento & sicurezza > verificare** la disponibilità di aggiornamenti per ottenere la build più recente.
### <a name="update-error-0x80070490-work-around"></a>Risolvere i 0x80070490 errore di aggiornamento
Se si verifica un errore di 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema seguente a breve termine. Comporta lo spostamento del canale Insider, il ritiro dell'aggiornamento e quindi lo spostamento del canale Insider.
#### <a name="stage-one---release-preview"></a>Fase 1 - Versione di anteprima
1.  Impostazioni, Aggiorna & sicurezza, Programma Windows Insider selezionare **Canale di anteprima versione.**
2.  Impostazioni, Aggiorna & sicurezza, Windows Update, **Verifica disponibilità aggiornamenti**. Dopo l'aggiornamento, passare alla fase 2.
#### <a name="stage-two---dev-channel"></a>Fase 2 - Canale di sviluppo
1. Impostazioni, Aggiorna & sicurezza, Programma Windows Insider, selezionare **Canale di sviluppo.**
2. Impostazioni, Aggiorna & sicurezza, Windows Update, **Verifica disponibilità aggiornamenti**.
## <a name="ffu-download-and-flash-directions"></a>Istruzioni flash e download FFU
Per testare con un volo firmato ffu, è prima necessario sbloccare il dispositivo prima di lampeggiare il volo firmato ffu.
1. Nel PC:
    1. Scaricare ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installare ARC (Advanced Recovery Companion) dal Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. In HoloLens - Flight Unlock: **aprire** l'aggiornamento delle & sicurezza Programma Windows Insider quindi iscriversi  >    >   e riavviare il dispositivo.
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
> Esiste un problema noto in cui gli utenti che annullano la registrazione dalle build insider preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu. Successivamente, devono ripristinare manualmente il dispositivo. Per informazioni dettagliate su se si è o meno influenzati, vedere altre informazioni su [questo problema noto.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)
Per verificare che HoloLens ese sia in esecuzione una build di produzione:
1. Passare a **Impostazioni > sistema > Informazioni su** e trovare il numero di build.
1. [Vedere le note sulla versione per i numeri di build di produzione.](hololens-release-notes.md)
Per rifiutare esplicitamente le build Insider:
1. In un dispositivo HoloLens che esegue una build di produzione, passare a Impostazioni **> Aggiorna**& sicurezza > Programma Windows Insider e selezionare Stop Insider builds (Arresta build **Insider).**
1. Seguire le istruzioni per rifiutare esplicitamente il dispositivo.
