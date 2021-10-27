---
title: Insider Preview per Microsoft HoloLens
description: Informazioni su come iniziare a usare le build Insider e fornire feedback utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.
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
ms.date: 10/19/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 382c979138068ab1d9682ee4e84831accc9e4553
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351656"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuti alle build insider preview più recenti per HoloLens! È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Note sulla versione insider

Quali sono le novità e l'orizzonte per HoloLens? Vedere questi nuovi aggiornamenti in HoloLens!

### <a name="colorblind-mode"></a>Modalità colorblind

Aggiunta nella build Insider 20348.1463

La modalità colorblind è utile per rendere la HoloLens più accessibile. La nuova modalità colorblind è disponibile nell'app Impostazioni in Impostazioni  ->  **Accessibilità**  ->  **Filtri colore**. Sono disponibili diversi nuovi filtri. Ecco un esempio visivo di alcuni filtri disponibili.

| Off | Grigi | Tritanopia |
|-----|-----------|------------|
| ![Filtro colori disattivato](images/colorblind-off.png)   | ![Scala di grigi del filtro colori](images/colorblind-greyscale.png)         | ![Tritanopia del filtro colori](images/colorblind-tritanopia.png)          |

### <a name="fixes-and-improvements"></a>Correzioni e miglioramenti

- Risolto un problema noto a causa del quale ogni volta che l'alimentazione passa al [18%,](hololens-troubleshooting.md#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)il dispositivo si arresta improvvisamente automaticamente.
- Miglioramenti alla modalità di spostamento della piattaforma quando si rileva la direzione verso il basso.
- È stato risolto un problema relativo alle finestre di dialogo di aggiornamento.
- Aggiornamento della Microsoft Edge del browser.
- È stato risolto un problema a causa del quale l'associazione di dati di diagnostica facoltativi non rende persistente l'impostazione scelta nella pagina delle impostazioni di telemetria dopo un riavvio.
- Correzione e problema per cui i codici A/A non sono stati riconosciuti quando sono stati ruotati con un angolo di 45 gradi rispetto al dispositivo.

## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider

> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
>
> - Il comando vocale "Riavvia il dispositivo" funziona correttamente.
> - È anche possibile scegliere il pulsante di riavvio in Impostazioni/Windows Programma Insider.
>
> Si è verificato un bug nel back-end che potrebbe essere stato rilevato e ciò consente di tornare in funzione.

In un dispositivo HoloLens 2 passare **a** Impostazioni  >  **Update & Security**  >  **Windows Programma Insider** e selezionare **Get started (Introduzione).** Collegare l'account usato per la registrazione come Windows Insider.

> [!NOTE]
> Per registrare il dispositivo nelle build Insider, è necessario abilitare i dati di telemetria facoltativi. Se non è già stato fatto, aprire l'app Impostazioni e selezionare Diagnostica della privacy & commenti e suggerimenti e quindi selezionare Dati di diagnostica  ->   **facoltativi**.

Windows insider sta ora passando a Canali. L'anello veloce diventerà dev  **channel,** l'anello  lento diventerà l'Canale beta e l'anello di anteprima della versione diventerà il canale di anteprima della **versione.**   Ecco l'aspetto del mapping:

![Windows Spiegazione dei canali insider.](images/WindowsInsiderChannels.png)

Per altre informazioni, vedere [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introduzione Windows Insider Channels Windows Blog).
Selezionare quindi **Sviluppo attivo di** Windows, scegliere se si desidera  ricevere dev **channel** o build Canale beta ed esaminare le condizioni del programma.
Selezionare **Conferma > riavvia ora** per completare l'operazione. Dopo il riavvio del dispositivo, passare Impostazioni > **aggiornamento & sicurezza** > verificare la disponibilità di aggiornamenti per ottenere la build più recente.

### <a name="update-error-0x80070490-work-around"></a>Risolvere i 0x80070490 di errore di aggiornamento

Se si verifica un errore di 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema a breve termine seguente. Comporta lo spostamento del canale insider, il ritiro dell'aggiornamento e quindi il ritorno del canale Insider.

#### <a name="stage-one---release-preview"></a>Fase 1 - Versione di anteprima

1. Impostazioni, Update & Security, Windows Programma Insider, selezionare Release **Preview Channel (Canale di anteprima versione).**

2. Impostazioni, Update & Security, Windows Update, **Check for updates**. Dopo l'aggiornamento, passare alla fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev Channel

1. Impostazioni, Aggiornare & Security, Windows Programma Insider, selezionare Dev **Channel**.

2. Impostazioni, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>Istruzioni flash e download FFU

Per testare con un volo firmato ffu, è prima necessario sbloccare il dispositivo prima di lampeggiare il volo firmato ffu.

1. Nel PC:
    1. Scaricare ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installare ARC (Advanced Recovery Companion) dal Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. In HoloLens - Flight Unlock: **aprire** Impostazioni  >  **update & Security**  >  **Windows Programma Insider** quindi iscriversi e riavviare il dispositivo.

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
> Esiste un problema noto in cui gli utenti che annullano la registrazione dalle compilazioni Insider Preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu. Successivamente, devono ripristinare manualmente il dispositivo. Per informazioni dettagliate complete su se si sarebbe stati o meno influenzati, vedere altre informazioni su [questo problema noto.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Per verificare che il HoloLens sia in esecuzione una build di produzione:

1. Passare a **Impostazioni > sistema > Informazioni su** e trovare il numero di build.

1. [Vedere le note sulla versione per i numeri di build di produzione](hololens-release-notes.md).

Per rifiutare esplicitamente le build Insider:

1. In un HoloLens esecuzione di una build di produzione, passare a Impostazioni > **Update & Security > Windows Programma Insider** e selezionare Stop Insider builds (Arresta **compilazioni Insider).**

1. Seguire le istruzioni per rifiutare esplicitamente il dispositivo.
