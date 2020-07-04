---
title: Riavviare, ripristinare o recuperare HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 837a019f110a58c490618d3d5c47e83e58231d18
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828581"
---
# Riavviare, ripristinare o recuperare HoloLens (prima generazione)

Se riscontri problemi sul tuo HoloLens, puoi provare a riavviare o ripristinare il tuo dispositivo, o addirittura a reinstallare il file immagine con lo strumento di recupero.

Di seguito sono riportate alcune procedure che puoi provare se il tuo HoloLens non funziona.  Questo articolo ti guida attraverso i passaggi consecutivi consigliati per il ripristino.

Se vuoi ripristinare un dispositivo HoloLens 2, consulta la pagina [Ripristinare un HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), perché la procedura è differente.

Questo articolo è incentrato sul dispositivo e il software HoloLens. Se gli ologrammi non sono corretti, [questo articolo](hololens-environment-considerations.md) descrive i fattori ambientali che migliorano la qualità degli ologrammi.

## Riavviare

### Eseguire un riavvio sicuro con Cortana

L’uso di Cortana è il modo più sicuro per riavviare il visore HoloLens. Si tratta, in genere, di un semplice primo passaggio quando si verifica un problema con HoloLens. 

> [!NOTE]
> Cortana non è disponibile in tutti i dispositivi. Cortana è disponibile in tutti i dispositivi HoloLens di prima generazione.
> Cortana è disponibile nei dispositivi HoloLens 2 con una build precedente a Windows Holographic versione 2004.

1. Indossa il tuo dispositivo
1. Assicurati che sia alimentato, che un utente vi stia accedendo, e che il dispositivo non richieda una password per sbloccarsi.
1. Pronuncia “Ciao Cortana, riavvia” o “Ciao Cortana, esegui il reboot”.
1. Cortana ti chiederà delle informazioni quando avrà ricevuto la richiesta. Attendi un secondo che venga riprodotto un suono dopo che ti ha rivolto la sua domanda, indicando che ti sta ascoltando, e pronuncia “Sì”.
1. Il dispositivo viene ora riavviato.

### Eseguire un riavvio sicuro con il pulsante di accensione

Se non riesci a riavviare il dispositivo, puoi provare a riavviarlo usando il pulsante di accensione:

1. Tieni premuto il tasto di accensione per 5 secondi.
   1. Dopo un secondo, tutti i cinque LED si accenderanno, e si spegneranno poi in sequenza da destra a sinistra.
   1. Dopo cinque secondi tutti i LED saranno spenti, per indicare che il comando di spegnimento è stato eseguito correttamente.
   1. Nota che è importante smettere di premere il pulsante subito dopo che tutti i LED si sono spenti.
1. Attendi un minuto il completamento della procedura di spegnimento. Nota che lo spegnimento potrebbe ancora essere in corso, anche se le luci sono spente.
1. Riaccendi il dispositivo tenendo premuto il tasto di accensione per un secondo.

### Eseguire un riavvio sicuro usando Windows Device Portal

> [!NOTE]
> Per eseguire l’operazione, HoloLens deve essere configurato come un dispositivo per sviluppatori.  
> Maggiori informazioni su [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Se la procedura precedente non ha funzionato, puoi provare a riavviare il dispositivo usando [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). Nell’angolo in alto a destra trovi un’opzione per riavviare o spegnere il dispositivo.

### Eseguire un riavvio forzato rischioso

Se non sei riuscito a riavviare il dispositivo con i metodi precedenti, puoi provare con un riavvio forzato. Questo metodo equivale a rimuovere la batteria dall’HoloLens.  Si tratta di un’operazione pericolosa, che può danneggiare il tuo dispositivo.  Se si verifica, dovrai ripristinare manualmente il tuo HoloLens.  

> [!WARNING]
> È un metodo potenzialmente pericoloso, e deve essere usato soltanto quando nessuno dei metodi precedenti ha funzionato.

1. Tieni premuto il tasto di accensione per almeno 10 secondi.
   - Puoi anche tenere premuto il tasto per più di 10 secondi.
   - Puoi ignorare qualsiasi attività dei LED.
1. Rilascia il pulsante e attendi due o tre secondi.
1. Riaccendi il dispositivo tenendo premuto il tasto di accensione per un secondo.
Se i problemi non sono risolti, tieni premuto il tasto di accensione per 4 secondi, finché tutti gli indicatori della batteria si spengono e gli ologrammi non sono più mostrati sullo schermo. Attendi 1 minuto, e premi poi il tasto di accensione di nuovo per accendere il dispositivo.

## Ripristinare le impostazioni di fabbrica

> [!NOTE]
> Per eseguire il ripristino, la batteria deve essere carica almeno al 40%.

Se riscontri ancora problemi sul tuo HoloLens dopo il riavvio, prova a ripristinare le impostazioni di fabbrica.  Il ripristino dell’HoloLens mantiene inalterata la versione installata del software Windows Holographic, e ripristina le impostazioni di fabbrica per tutto il resto.

Se si ripristina il dispositivo, tutti i dati personali, le app e le impostazioni verranno eliminati, compreso il ripristino del TPM. Durante il ripristino viene soltanto installata l’ultima versione di Windows Holographic, e dovrai completare di nuovo tutte le operazioni di inizializzazione (calibrazione, connessione Wi-Fi, creazione di un account utente, scaricamento delle app, e così via).

1. Lancia l’app Impostazioni e seleziona **Aggiorna** > **Ripristina**.
1. Seleziona l’opzione **Ripristina dispositivo** e leggi il messaggio di conferma.
1. Se accetti di ripristinare il dispositivo, questo si riavvierà e mostrerà una serie di ingranaggi rotanti con un indicatore di stato.
1. Attendi circa 30 minuti per il completamento del processo.
1. Al termine, il ripristino è completato e il dispositivo si riavvia offrendo l’esperienza iniziale.

## Reinstallare il sistema operativo

Se il dispositivo ha ancora problemi dopo il riavvio e il ripristino, puoi usare uno strumento di recupero sul tuo computer per reinstallare il sistema operativo e il firmware di HoloLens.  

Tutti i dati di cui HoloLens ha bisogno per il ripristino sono inclusi in un file FFU (Full Flash Update).  Questo è simile ai file ISO, WIM o VHD.  [Scopri di più sulle immagini FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Se necessario, puoi installare un sistema operativo completamente nuovo sul tuo HoloLens di prima generazione usando Windows Device Recovery Tool. 

Prima di usare lo strumento, stabilisci se il riavvio o il ripristino del tuo HoloLens possa risolvere il problema. La procedura di recupero può richiedere più tempo.  Al termine, sul tuo HoloLens sarà installata l’ultima versione del software Windows Holographic approvata per il tuo dispositivo.

Per usare lo strumento, è necessario un computer che esegue Windows 10 o versione successiva con almeno 4 GB di spazio di archiviazione libero.  Nota che non puoi eseguire questo strumento su una macchina virtuale.

### Recuperare l’HoloLens:

1. Scarica e installa [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) sul tuo PC.
1. Connetti l’HoloLens di prima generazione al tuo computer usando il cavo micro USB fornito insieme all’HoloLens.
1. Esegui Windows Device Recovery Tool e segui le istruzioni.

Se HoloLens (prima generazione) non viene rilevato automaticamente, seleziona **Il mio dispositivo non è stato rilevato** per attivare la modalità di recupero del tuo dispositivo.

### Modalità di lampeggiamento manuale:

Se il tuo dispositivo non viene rilevato, usa questo metodo per attivare manualmente la modalità di lampeggiamento manuale.

1. Scollega il dispositivo da tutte le fonti di alimentazione.
1. Se il dispositivo è acceso, tieni premuto il tasto di accensione fino a quando è completamente spento.
1. Tieni premuto il tasto **Volume su**, e tocca brevemente il tasto **Volume giù**. 
1. Il dispositivo dovrebbe avviare il ciclo di avvio, e solo il LED centrale dovrebbe essere acceso.
1. Collega il dispositivo al tuo PC.
1. Esegui Windows Device Recovery Tool.
1. Devi selezionare *Il mio dispositivo non è stato rilevato**, e scegliere poi **HoloLens**. 
1. Segui le istruzioni per recuperare il tuo dispositivo.
