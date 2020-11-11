---
title: Insider Preview per Microsoft HoloLens
description: È semplice iniziare con le build Insider e dare un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.
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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162950"
---
# Insider Preview per Microsoft HoloLens

Benvenuti alle build di insider Preview più recenti per HoloLens! È facile [iniziare e dare](hololens-insider.md#start-receiving-insider-builds) un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.

## Note sulla versione di Windows Insider

### Installare app in HoloLens 2 tramite il programma di installazione di app
Spediremo la funzionalità di installazione dell'app subito dopo l'aggiornamento di Windows olografico, versione 20H2. Aggiungiamo **una nuova funzionalità (Installer delle app) per consentire l'installazione delle applicazioni in modo più trasparente** nei dispositivi HoloLens 2. La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti**. Per evitare interruzioni alle aziende, il programma di installazione **delle app non sarà disponibile per i dispositivi gestiti** in questo momento.  

Un dispositivo viene considerato "gestito **" Se una delle opzioni** seguenti è vera:
- MDM [registrato](hololens-enroll-mdm.md)
- Configurato con il [pacchetto di provisioning](hololens-provisioning.md)
- L' [identità](hololens-identity.md) dell'utente è AAD

Ora è possibile installare le app senza dover abilitare la modalità sviluppatore o usando Device Portal.  È sufficiente scaricare (tramite USB o Edge) il bundle appx nel dispositivo e passare al bundle appx in Esplora file per richiedere di avviare l'installazione.  In alternativa, [avviare un'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Proprio come le app installate da Microsoft Store o trasferire localmente usando la funzionalità di distribuzione dell'app LOB di MDM, le app devono essere firmate digitalmente con lo [strumento Sign](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e il [certificato usato per firmare deve essere considerato attendibile](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) dal dispositivo HoloLens prima che l'app possa essere distribuita.

**Istruzioni per l'installazione dell'applicazione.**

1.  Verificare che il dispositivo non sia considerato gestito
1.  Verificare che il dispositivo HoloLens 2 sia acceso e connesso al PC
1.  Verificare di avere effettuato l'accesso al dispositivo HoloLens 2
1.  Nel PC passare all'app personalizzata e copiare YourApp. appxbundle in yourdevicename\Internal Storage\Downloads.   Dopo aver completato la copia del file, è possibile disconnettere il dispositivo
1.  Dal dispositivo HoloLens 2 aprire il menu Start, selezionare tutte le app e avviare l'app Esplora file.
1.  Passare alla cartella Downloads. Potrebbe essere necessario nel pannello sinistro dell'app selezionare prima questo dispositivo, quindi passare a download.
1.  Selezionare il file YourApp. appxbundle.
1.  Verrà avviato il programma di installazione dell'app. Selezionare il pulsante Installa per installare la tua app.
L'app installata verrà avviata automaticamente al termine dell'installazione.

Puoi trovare app di esempio in [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) per testare questo flusso.

Leggere il processo completo di [installazione delle app in HoloLens 2 con il programma di installazione dell'app](app-deploy-app-installer.md).  

![Installazione di esempi di MRTK tramite il programma di installazione dell'app](images/hololens-app-installer-picture.jpg)

## Iniziare a ricevere compilazioni Insider

> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
> - Il comando vocale "dispositivo di riavvio" funziona bene. 
> - È anche possibile scegliere il pulsante Riavvia in Impostazioni/programma Insider di Windows.
>
> Abbiamo avuto un bug sul back-end che potresti aver incontrato e questo ti riporterà in carreggiata.

In un dispositivo HoloLens 2 passa a **Impostazioni**di  >  **aggiornamento &**  >  **programma sicurezza Windows Insider** e selezionare per **iniziare**. Collegare l'account usato per la registrazione come Windows Insider.

Windows Insider ora sta passando ai canali. L'anello **veloce** diventerà il canale **dev**, l'anello **lento** diventerà il **canale Beta**e l' **anteprima del rilascio** diventerà il canale di **anteprima del rilascio**. Ecco come si presenta il mapping:

![Spiegazione di Windows Insider Channels](images/WindowsInsiderChannels.png)

Per altre informazioni, vedere [Introduzione ai canali Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nei Blog di Windows.

Selezionare quindi **lo sviluppo attivo di Windows**, scegliere se si vuole ricevere le build del canale **dev** o del canale **beta** e rivedere le condizioni del programma.

Selezionare **conferma > Riavvia ora** per completare l'installazione. Dopo aver riavviato il dispositivo, accedere a **impostazioni > aggiorna & sicurezza > verificare la disponibilità di aggiornamenti** per ottenere la build più recente.

## FFU download e istruzioni Flash
Per eseguire il test con un FFU firmato per il volo, è necessario prima di tutto sbloccare il dispositivo prima di infiammare il volo firmato FFU.
1. Nel PC:

    1. Scaricare FFU dal PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installare ARC (Advanced Recovery Companion) da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. In HoloLens-Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Windows Insider Program** , quindi iscriviti, riavvia il dispositivo.

1. Flash FFU-ora è possibile flashare il FFU firmato in anteprima con ARC.

## Inviare feedback e segnalare i problemi

Usare [l'app hub di feedback](hololens-feedback.md) in HoloLens per inviare commenti e segnalazioni. L'uso di hub di feedback assicura che vengano incluse tutte le informazioni di diagnostica necessarie per aiutare i nostri ingegneri a eseguire rapidamente il debug e risolvere il problema.  I problemi con la versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurarsi di accettare il messaggio che chiede se si vuole che l'hub di feedback acceda alla cartella documenti (selezionare **Sì** quando richiesto).

## Nota per gli sviluppatori

Sei il benvenuto e ti consigliamo di provare a sviluppare le tue applicazioni usando le build Insider di HoloLens.  Per iniziare, vedere la [documentazione di HoloLens per sviluppatori](https://developer.microsoft.com/windows/mixed-reality/development) . Le stesse istruzioni funzionano con le build Insider di HoloLens.  Puoi usare le stesse build di Unity e Visual Studio che stai già usando per lo sviluppo di HoloLens.

## Interrompere la ricezione delle build Insider

Se non si vuole più ricevere Build Insider di Windows olografico, è possibile rifiutare la disattivazione quando HoloLens è in esecuzione una build di produzione oppure è possibile [recuperare il dispositivo](hololens-recovery.md) usando il compagno di ripristino avanzato per recuperare il dispositivo in una versione non Insider di Windows olografico.

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che non si iscrivono da insider Preview Builds dopo la reinstallazione manuale di una nuova versione di anteprima acquisiranno una schermata blu. In seguito dovrà recuperare manualmente il dispositivo. Per informazioni dettagliate su se si è interessati o meno, vedere altre informazioni su questo [problema noto](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Per verificare che HoloLens esegua una build di produzione:

1. Accedere a **impostazioni > sistema > informazioni**e trovare il numero di Build.

1. [Vedere le note sulla versione per i numeri di build della produzione](hololens-release-notes.md).

Per rifiutare le build Insider:

1. In un HoloLens in cui è in corso una build di produzione, passare a **impostazioni > aggiornare & sicurezza > programma Windows Insider**e selezionare **Interrompi Build Insider**.

1. Seguire le istruzioni per rifiutare il dispositivo.
