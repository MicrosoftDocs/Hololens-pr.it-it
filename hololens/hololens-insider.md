---
title: Insider Preview per Microsoft HoloLens
description: Informazioni su come iniziare a usare le build Insider e fornire feedback preziosi per il prossimo aggiornamento principale del sistema operativo per HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924361"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuti alle build insider preview più recenti per HoloLens! È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Note sulla versione insider

Siamo entusiasti del fatto che tutte le funzionalità recenti di Insider sono state pubbliche. Per altre informazioni, vedere la pagina delle note [sulla versione](hololens-release-notes.md)

## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider

> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
>
> - Il comando vocale "Riavvia il dispositivo" funziona correttamente.
> - È anche possibile scegliere il pulsante di riavvio in Impostazioni/Windows Programma Insider.
>
> Si è verificato un bug nel back-end che potrebbe essere stato rilevato e ciò consente di tornare in funzione.

In un dispositivo HoloLens 2 passare **a** Impostazioni  >  **Aggiornamento & sicurezza**  >  **Windows Programma Insider** e selezionare **Introduzione.** Collegare l'account usato per la registrazione come Windows Insider.

> [!NOTE]
> Per registrare il dispositivo nelle build Insider, è necessario abilitare i dati di telemetria facoltativi. Se questa operazione non è già stata eseguita, aprire l'app Impostazioni e selezionare Diagnostica della privacy & commenti e suggerimenti e quindi  ->   selezionare Dati di **diagnostica facoltativi.**

Windows insider sta ora passando a Canali. L'anello veloce diventerà dev  **channel,** l'anello  lento diventerà l'Canale beta e l'anello di anteprima della versione diventerà il canale di anteprima della **versione.**   Ecco l'aspetto del mapping:

![Windows Spiegazione dei canali insider.](images/WindowsInsiderChannels.png)

Per altre informazioni, vedere [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introduzione Windows Insider Channels Windows Blog).
Selezionare quindi **Sviluppo attivo di** Windows, scegliere se si desidera  ricevere dev **channel** o build Canale beta ed esaminare le condizioni del programma.
Selezionare **Conferma > riavvia ora** per completare l'operazione. Dopo il riavvio del dispositivo, passare Impostazioni > **aggiornamento & sicurezza** > verificare la disponibilità di aggiornamenti per ottenere la build più recente.

### <a name="update-error-0x80070490-work-around"></a>Risolvere i 0x80070490 errore di aggiornamento

Se si verifica un errore di 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema a breve termine seguente. Comporta lo spostamento del canale Insider, la raccolta dell'aggiornamento e quindi il ritorno del canale Insider.

#### <a name="stage-one---release-preview"></a>Fase 1 - Versione di anteprima

1. Impostazioni, Update & Security, Windows Programma Insider, selezionare **Release Preview Channel (Canale di anteprima versione).**

2. Impostazioni, Update & Security, Windows Update, **Check for updates**. Dopo l'aggiornamento, passare alla fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev Channel

1. Impostazioni, Aggiornare & Security, Windows Programma Insider, selezionare Dev **Channel**.

2. Impostazioni, Update & Security, Windows Update, **Check for updates**.

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

Si è invitati a provare a sviluppare applicazioni usando build Insider di HoloLens.  Per [iniziare, vedere HoloLens per](https://developer.microsoft.com/windows/mixed-reality/development) sviluppatori. Queste stesse istruzioni funzionano con le build Insider di HoloLens.  È possibile usare le stesse build di Unity e Visual Studio che si sta già usando per HoloLens sviluppo.

## <a name="stop-receiving-insider-builds"></a>Interrompere la ricezione di build Insider

Se non si vogliono più ricevere build Insider di Windows Holographic, è possibile rifiutare esplicitamente quando il [](hololens-recovery.md) HoloLens esegue una build di produzione oppure è possibile ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo a una versione non Insider di Windows Holographic.

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che annullano la registrazione dalle build insider preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu. Successivamente, devono ripristinare manualmente il dispositivo. Per informazioni dettagliate complete su se si sarebbe o meno in grado di influire, vedere altre informazioni su [questo problema noto.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Per verificare che il HoloLens sia in esecuzione una build di produzione:

1. Passare a **Impostazioni > sistema > informazioni su** e trovare il numero di build.

1. [Vedere le note sulla versione per i numeri di build di produzione](hololens-release-notes.md).

Per rifiutare esplicitamente le build Insider:

1. In un HoloLens esecuzione di una build di produzione, passare a Impostazioni > **Update & Security > Windows Programma Insider** e selezionare Stop Insider builds (Arresta **compilazioni Insider).**

1. Seguire le istruzioni per rifiutare esplicitamente il dispositivo.
