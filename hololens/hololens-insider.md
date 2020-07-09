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
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b054b61b269522d673be104ffbda9abc1bc85415
ms.sourcegitcommit: 168a7659420525e5f3e3088d7ce0b5e03c969029
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "10860606"
---
# Insider Preview per Microsoft HoloLens

Benvenuti alle build di insider Preview più recenti per HoloLens!  È facile iniziare e dare un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.

Windows Insider ora sta passando ai canali. L'anello **veloce** diventerà il canale **dev**, l'anello **lento** diventerà il **canale Beta**e l' **anteprima del rilascio** diventerà il canale di **anteprima del rilascio**. Ecco come si presenta il mapping:

![Spiegazione di Windows Insider Channels](images/WindowsInsiderChannels.png)

Per altre informazioni: [immissione di Blog di Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)

## Iniziare a ricevere compilazioni Insider

In un dispositivo HoloLens 2 passa a **Impostazioni**di  ->  **aggiornamento &**  ->  **programma sicurezza Windows Insider** e selezionare per **iniziare**. Collegare l'account usato per la registrazione come Windows Insider.

Selezionare quindi **lo sviluppo attivo di Windows**, scegliere se si vuole ricevere le build del canale **dev** o del canale **beta** e rivedere le condizioni del programma.

Selezionare **conferma-> Riavvia ora** per completare l'installazione. Dopo aver riavviato il dispositivo, passa a **Impostazioni-> aggiorna & sicurezza-> verificare la disponibilità di aggiornamenti** per ottenere la build più recente.

## Interrompere la ricezione delle build Insider

Se non si vuole più ricevere Build Insider di Windows olografico, è possibile rifiutare la disattivazione quando HoloLens è in esecuzione una build di produzione oppure è possibile [recuperare il dispositivo](hololens-recovery.md) usando il compagno di ripristino avanzato per recuperare il dispositivo in una versione non Insider di Windows olografico.

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che non si iscrivono da insider Preview Builds dopo la reinstallazione manuale di una nuova versione di anteprima acquisiranno una schermata blu. In seguito dovrà recuperare manualmente il dispositivo. Per informazioni dettagliate su se si è interessati o meno, vedere altre informazioni su questo [problema noto](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Per verificare che HoloLens esegua una build di produzione:

1. Accedere a **impostazioni > sistema > informazioni**e trovare il numero di Build.
1. [Vedere le note sulla versione per i numeri di build della produzione.](hololens-release-notes.md)

Per rifiutare le build Insider:

1. In un HoloLens in cui è in corso una build di produzione, passare a **impostazioni > aggiornare & sicurezza > programma Windows Insider**e selezionare **Interrompi Build Insider**.
1. Seguire le istruzioni per rifiutare il dispositivo.


## Inviare feedback e segnalare i problemi

Usare [l'app hub di feedback](hololens-feedback.md) in HoloLens per inviare commenti e segnalazioni. L'uso di hub di feedback assicura che vengano incluse tutte le informazioni di diagnostica necessarie per aiutare i nostri ingegneri a eseguire rapidamente il debug e risolvere il problema.  I problemi con la versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurarsi di accettare il messaggio che chiede se si vuole che l'hub di feedback acceda alla cartella documenti (selezionare **Sì** quando richiesto).

## Nota per gli sviluppatori

Sei il benvenuto e ti consigliamo di provare a sviluppare le tue applicazioni usando le build Insider di HoloLens.  Per iniziare, vedere la [documentazione di HoloLens per sviluppatori](https://developer.microsoft.com/windows/mixed-reality/development) . Le stesse istruzioni funzionano con le build Insider di HoloLens.  Puoi usare le stesse build di Unity e Visual Studio che stai già usando per lo sviluppo di HoloLens.


## Note sulla versione di Windows Insider

Dal nostro [Windows olografico maggio 2020 Update](hololens-release-notes.md) Release tutte le funzionalità di anteprima del rilascio sono ora disponibili in generale. Assicurati di [aggiornare il HoloLens](hololens-update-hololens.md) per ottenere tutte le caratteristiche più recenti.

La pagina verrà aggiornata di nuovo con le nuove funzionalità quando le rilasceremo alle build Insider di Windows.


### Supporto per la posizione degli occhi automatici

In HoloLens 2 le posizioni degli occhi permettono un posizionamento accurato degli ologrammi, un'esperienza di visualizzazione confortevole e una qualità di visualizzazione migliorata. Le posizioni degli occhi vengono calcolate come parte del risultato del rilevamento degli occhi. Tuttavia, questo richiede a ogni utente di passare alla calibrazione della verifica degli occhi, anche quando l'esperienza non richiede l'input dello sguardo oculare.

La **posizione degli occhi automatici (AEP)** consente a questi scenari di calcolare le posizioni degli occhi per l'utente in modo libero da interazioni.  La posizione degli occhi automatici inizia a lavorare in background automaticamente dal momento in cui l'utente inserisce il dispositivo. Se l'utente non ha una calibrazione preventiva degli occhi, la posizione degli occhi automatici inizierà a fornire le posizioni degli occhi dell'utente al sistema di visualizzazione dopo un breve periodo di elaborazione. Questo tempo di elaborazione è in genere compreso tra 20-60 secondi. I dati dell'utente non vengono mantenuti nel dispositivo e quindi questo processo viene ripetuto se l'utente decolla e riattiva il dispositivo o se il dispositivo si riavvia o si risveglia dal sonno.  

Ci sono alcune modifiche al comportamento del sistema con la funzionalità posizione occhio automatico quando un utente non calibrato inserisce il dispositivo. Un utente non calibrato fa riferimento a una persona che non ha superato il processo di calibrazione del rilevamento degli occhi nel dispositivo in precedenza.

|     Applicazione attiva                           |     Comportamento corrente                                   |     Comportamento da Windows Insider Build 19041.1339 +                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     App o Shell olografica abilitata per gli occhi non consentiti    |     Viene visualizzata la richiesta di calibrazione del rilevamento degli occhi.    |     Non viene visualizzato alcun messaggio.                                                                                |
|     App sguardo abilitato                             |     Viene visualizzata la richiesta di calibrazione del rilevamento degli occhi.    |     La richiesta di calibrazione degli occhi viene visualizzata solo quando l'applicazione accede al flusso dello sguardo oculare.     |

 Se l'utente passa da un'applicazione abilitata senza lo sguardo a quella che accede ai dati sugli sguardi, verrà visualizzata la richiesta di calibrazione. Non verrà modificato il flusso di esperienza fuori scatola. 
 
Per le esperienze che richiedono dati sugli occhi o un posizionamento olografico molto preciso, è consigliabile che gli utenti non calibrati eseguano la calibrazione della verifica degli occhi dalla richiesta di calibrazione degli occhi o lancino l'app Impostazioni dal menu Start e quindi selezionando **sistema > calibrazione > calibrazione degli occhi > eseguire la calibrazione degli**occhi.

**Problemi noti**
1.  Stiamo esaminando un problema in cui il processo di host del driver dell'eye tracker potrebbe arrestarsi in modo anomalo durante l'esecuzione in un carico di memoria elevato. Il processo host del driver di rilevamento degli occhi deve essere recuperato automaticamente.

## FFU download e istruzioni Flash
Per eseguire il test con un FFU firmato per il volo, è necessario prima di tutto sbloccare il dispositivo prima di infiammare il volo firmato FFU.
1. Su PC
    1. Scaricare FFU nel PC da:[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. Installare ARC (Advanced Recovery Companion) da Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
1. In HoloLens-Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Windows Insider Program** quindi iscriviti, riavvia il dispositivo
1. Flash FFU-ora è possibile flashare il Flight signed FFU usando ARC
