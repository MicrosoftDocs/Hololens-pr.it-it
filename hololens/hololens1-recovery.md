---
title: Riavviare, ripristinare o recuperare HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Come usare lo strumento Windows Device Recovery Tool per reinstallare il file immagine di HoloLens (prima generazione).
keywords: guida, riavvio, reset, ripristino, recupero, ripristino automatico, ciclo di alimentazione, HoloLens, spegnimento, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f50a885f6cc82256d146d7f4914aca934e81c0c0
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439042"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Riavviare, ripristinare o recuperare HoloLens (prima generazione)

Se si riscontrano problemi su HoloLens, è possibile provare a riavviare o ripristinare il dispositivo, o addirittura a riconfigurarlo utilizzando lo strumento di recupero. Questo articolo illustra i passaggi consigliati ed il loro ordine di esecuzione per il ripristino.

Se si vuole ripristinare un HoloLens 2, vedere [Ripristino di un HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), visto che i processi sono differenti.

> [!NOTE]
> Questo articolo è incentrato sul dispositivo ed il software HoloLens. Se gli ologrammi non sembrano essere corretti, vedere **[considerazioni sull'ambiente HoloLens](hololens-environment-considerations.md)** per informazioni sui fattori che migliorano la qualità degli ologrammi.

## <a name="restart"></a>Riavviare

### <a name="do-a-safe-restart-by-using-cortana"></a>Riavviare in sicurezza usando Cortana

Il modo più sicuro per riavviare HoloLens consiste nell'usare Cortana, che in genere è la prima cosa da provare quando si verifica un problema con HoloLens.

> [!NOTE] 
> Cortana non è disponibile su tutti i dispositivi.
> - Cortana è disponibile su tutti i dispositivi HoloLens di 1 generazione. 
> - Cortana è disponibile sui dispositivi HoloLens 2 con build precedenti a Windows Holographic, versione 2004 aggiornata.

1. Attivare HoloLens.
1. Assicurarsi che l’utente abbia già effettuato l’accesso e che il dispositivo non richieda una password per sbloccarsi.
2. Pronuncia “Ciao Cortana, riavvia” o “Ciao Cortana, esegui il reboot”.
3. Cortana risponderà e chiederà di confermare. Attendere la riproduzione di un suono dopo la domanda e successivamente dire “Sì". Il dispositivo viene ora riavviato.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Usare il pulsante di accensione per riavviare in sicurezza

Se ancora risulta impossibile riavviare il dispositivo, ritentare utilizzando il pulsante di **accensione**:

1. Tenere premuto il pulsante di **accensione** per 5 secondi. Dopo 1 secondo, tutti e cinque i LED si accenderanno disattivandosi lentamente uno alla volta da destra a sinistra. Dopo 5 secondi, tutti i LED saranno spenti, segno di arresto avvenuto correttamente.
      
   > [!IMPORTANT]
   > È necessario smettere di premere il pulsante subito dopo lo spegnimento di tutti i LED.
1. Attendere 1 minuto per il completamento della chiusura. Lo spegnimento potrebbe ancora essere in corso nonostante lo spegnimento delle luci.
2. Riaccendere il dispositivo tenendo premuto il tasto di **accensione** per 1 secondo.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Eseguire un riavvio sicuro usando il Portale di dispositivi di Windows

> [!NOTE]
> Per questo processo, HoloLens deve essere configurato come un dispositivo per sviluppatori. Maggiori informazioni sul [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Se la procedura precedente non ha funzionato, è possibile provare a riavviare il dispositivo usando il [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). Nell’angolo in alto a destra si trova l’opzione per riavviare o spegnere il dispositivo.

### <a name="do-an-unsafe-forced-restart"></a>Eseguire un riavvio forzato rischioso

Se i metodi precedenti non hanno riavviato HoloLens, forzarne il riavvio. Questo metodo equivale a rimuovere e reinstallare la batteria. Tale procedura rappresenta un rischio perché potrebbe danneggiare il dispositivo. Se si verifica, dovrai ripristinare manualmente il tuo HoloLens.  

> [!WARNING]
> Questo è un metodo potenzialmente pericoloso e dovrebbe essere usato soltanto quando nessuno dei metodi precedenti ha funzionato.

1. Tenere premuto il tasto di **accensione** per almeno 10 secondi.
   - Puoi anche tenere premuto il tasto per più di 10 secondi.
   - Puoi ignorare qualsiasi attività dei LED.
1. Rilasciare il pulsante e attendere 2 o 3 secondi.
1. Tenere premuto il pulsante di **accensione** per 1 secondo.
1. Se il problema persiste, tenere premuto il tasto di **accensione** per 4 secondi, finché tutti gli indicatori della batteria si spengono e gli ologrammi non sono più mostrati sullo schermo. Attendere 1 minuto, e premere poi il tasto di **accensione** di nuovo per accendere il dispositivo.

## <a name="reset-to-factory-settings"></a>Ripristinare le impostazioni di fabbrica

> [!NOTE]
> Per eseguire il ripristino, la batteria deve essere carica almeno al 40%.

Se il problema persiste sul Microsoft HoloLens, provare a ripristinare le impostazioni di fabbrica. Questo processo mantiene inalterata la versione installata del software Windows Holographic e ripristina le impostazioni di fabbrica per tutto il resto.

>[!WARNING]
> Se si ripristina il dispositivo, tutti i dati personali, le app e le impostazioni verranno eliminati, incluse le informazioni sul ripristino del TPM. Il ripristino installerà solo l’ultima versione installata di Windows Holographic. È necessario ripetere tutti i passaggi di inizializzazione (calibratura, connessione al Wi-Fi, creazione dell’account utente, download delle app e così via).

1. Aprire l’app Impostazioni e seleziona **Aggiorna** > **Ripristino**.
1. Seleziona l’opzione **Ripristina dispositivo** e leggi il messaggio di conferma.
1. Confermare il ripristino. Il dispositivo si riavvierà e mostrerà una serie di ingranaggi rotanti con un indicatore di stato.
1. Attendi circa 30 minuti per il completamento del processo. Al termine, il dispositivo si riavvierà in modalità “impatto fuori scatola”.

## <a name="reinstall-the-operating-system"></a>Reinstallare il sistema operativo

Se il dispositivo presenta ancora problemi dopo il riavvio e il ripristino, è possibile usare uno strumento di recupero sul computer per reinstallare il sistema operativo e il firmware di HoloLens.  

I dati necessari per reimpostare HoloLens sono inclusi in un Full Flash Update (FFU), che è simile a un file con estensione ISO, WIM o VHD. [Scopri di più sulle immagini FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Usando il Windows Device Recovery Tool è possibile installare un sistema operativo completamente nuovo su un HoloLens di 1 generazione.  Prima di usare tale strumento, è preferibile stabilire se il riavvio o il ripristino di HoloLens possano risolvere il problema.

La procedura di recupero può richiedere del tempo. Al termine, sarà installata l’ultima versione del software Windows Holographic.

Per usare lo strumento, è necessario un computer dotato di Windows 10 o versione successiva e di almeno 4 GB di spazio di archiviazione libero. Non è possibile eseguire questo strumento su una macchina virtuale.

### <a name="recover-your-hololens"></a>Recupero di HoloLens

1. Scarica e installa [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) sul tuo PC.
1. Connettere un HoloLens di 1 generazione al computer usando il cavo micro USB fornito in dotazione.
1. Eseguire Windows Device Recovery Tool e seguire le istruzioni.

Se l'HoloLens di 1 generazione non viene rilevato automaticamente, selezionare **il mio dispositivo non è stato rilevato**. Seguire quindi le istruzioni per far entrare il dispositivo in modalità di ripristino.

### <a name="manual-flashing-mode"></a>Modalità di riconfigurazione manuale

Se il dispositivo non viene rilevato, eseguire le operazioni seguenti per farlo entrare in modalità di riconfigurazione:

1. Scollegare il dispositivo da tutte le fonti di alimentazione.
1. Se il dispositivo è acceso, tenere premuto il tasto di **accensione** fino al suo completo spegnimento.
2. Tenere premuto il tasto **volume verso l’alto** e toccare brevemente il tasto di **accensione**. Il dispositivo dovrebbe avviarsi e solo il LED centrale dovrebbe essere acceso.
3. Collega il dispositivo al tuo PC.
4. Eseguire Windows Device Recovery Tool.
5. Selezionare**Il mio dispositivo non è stato rilevato** e quindi **HoloLens**. 
6. Segui le istruzioni per recuperare il tuo dispositivo.
