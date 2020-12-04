---
title: Risoluzione dei problemi
description: Soluzioni per problemi di HoloLens comuni.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: problemi, bug, risoluzione dei problemi, correzione, guida, supporto, HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 4f077a8bb2592ab9b650e2e8021c97d3d8524dcc
ms.sourcegitcommit: d20f610edd7db452ccc2ac554fc8d21bd89b0b99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "11195282"
---
# Risoluzione dei problemi

Questo articolo descrive come risolvere diversi problemi di HoloLens comuni.

## Il mio HoloLens non risponde o non si avvia

Se il HoloLens non si avvia:

- Se i LED accanto al pulsante di alimentazione non si accendono o un solo LED lampeggia brevemente, potrebbe essere necessario [caricare il HoloLens.](hololens-recovery.md#charge-the-device)
- Se i LED si accendono quando si preme il pulsante di alimentazione, ma non si riesce a vedere nulla sugli schermi, [preformare un ripristino rigido del dispositivo](hololens-recovery.md#hard-reset-procedure).

Se il HoloLens diventa bloccato o non risponde:

- Disattivare il HoloLens premendo il pulsante di alimentazione finché tutti e cinque i LED non si spengono o per 15 secondi se i LED non rispondono. Per avviare il HoloLens, premere di nuovo il pulsante di alimentazione.

Se questa procedura non funziona, è possibile provare a [recuperare il dispositivo HoloLens 2](hololens-recovery.md) o [HoloLens (1a Gen).](hololens1-recovery.md)

## Gli ologrammi non hanno un bell'aspetto

Se gli ologrammi sono instabili, nervosi o non hanno un aspetto corretto, provare a:

- Pulizia della visiera del dispositivo e della barra del sensore nella parte anteriore della HoloLens.
- Aumentare la luce in camera.
- Spostarsi e osservare l'ambiente circostante in modo che HoloLens possa analizzarli più completamente.
- Calibrazione della HoloLens per gli occhi. Accedere alle utilità di sistema **delle impostazioni**  >  **System**  >  **Utilities**. In **Calibrazione**, selezionare **Apri Calibrazione**.
 
### Segnalazione di problemi in cui gli ologrammi sono instabili o non hanno un aspetto corretto
 
1. Registrare e un [video di acquisizione di realtà mista](holographic-photos-and-videos.md#capture-a-mixed-reality-video) del problema. Questo video può essere caricato in seguito tramite hub feedback come file allegato.  
1. Abilitare la telemetria completa tramite l'app **Impostazioni** -> la diagnostica **sulla privacy**  ->  **& feedback** e in **dati di diagnostica facoltativi** verificare che l'attivazione sia impostata **su** attivato
1. Ottenere gli ultimi aggiornamenti della scala e della stabilità degli ologrammi aggiornando il [sistema operativo Windows olografico più recente (20H2 o versione successiva)](hololens-release-notes.md#windows-holographic-version-20h2). Dopo l'aggiornamento, eseguire le operazioni seguenti:
    1. Rimuovere tutti gli ologrammi tramite l'app **Impostazioni** - **System**  ->  **ologrammi** del sistema >-> quindi selezionare **Rimuovi tutti gli ologrammi** e iniziare con una nuova mappa.
    1. Crea una nuova mappa dello spazio indossando il HoloLens e camminando per la tua stanza e guardando tutte le aree e le superfici nello spazio. Eseguire questa operazione per 2-3 minuti.
    1. Eseguire la calibrazione di dpi. Accedere alle utilità di sistema **delle impostazioni**  >  **System**  >  **Utilities**. In **Calibrazione**, selezionare **Apri Calibrazione**.
    1. Ripetere il test dello scenario e verificare se è ancora persistente.
1. Se l'aggiornamento non risolve il problema, inviare un [problema di hub di feedback](hololens-feedback.md). Dopo aver completato il feedback, è possibile usare il pulsante **Condividi** per creare un collegamento facile da condividere che può essere inviato durante il contatto con il supporto.

## HoloLens non risponde all'input della mano

Per assicurarti che HoloLens possa vedere le tue mani, devi mantenerle nel riquadro gestuale.  La Home realtà mista fornisce un feedback che consente di sapere quando si tiene traccia delle mani.  Il feedback è diverso nelle diverse versioni di HoloLens:
- In HoloLens (1a generazione) il cursore dello sguardo cambia da un punto a un anello
- In HoloLens 2 viene visualizzato un cursore della punta delle dita quando la mano è vicina a una lavagna e viene visualizzato un raggio di mano quando le ardesie sono più lontane

Molte app immersive seguono modelli di input simili a Home realtà mista.  Leggi altre informazioni sull'uso dell'input manuale in [HoloLens (1a generazione)](hololens1-basic-usage.md#use-hololens-with-your-hands) e [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se si indossano guanti, tenere presente che alcuni tipi di guanti non funzionano con il rilevamento manuale.  Un esempio comune è il guanto di gomma nera, che tende ad assorbire la luce infrarossa e non viene captato dalla fotocamera di profondità.  Se il lavoro prevede guanti di gomma, è consigliabile provare un colore più chiaro, ad esempio blu o grigio.  Un altro esempio è il grande guanto larghi, che tende ad oscurare la forma della mano. Per ottenere risultati ottimali, è consigliabile usare i guanti più adatti possibile.

Se la visiera ha impronte digitali o macchie, usare il panno in microfibra fornito con il HoloLens per pulire delicatamente la visiera.

## HoloLens non risponde ai comandi vocali

Se Cortana non risponde ai comandi vocali, verificare che Cortana sia attivato. Nell'elenco tutte le app selezionare impostazioni del **Cortana**  >  **Menu**  >  **blocco appunti**del menu Cortana  >  **Settings** per apportare modifiche. Per ulteriori informazioni sulle frasi che è possibile pronunciare, vedere [Usare la voce con HoloLens](hololens-cortana.md).

## Non è possibile collocare gli ologrammi o vedere gli ologrammi precedentemente inseriti

Se HoloLens non riesce a mappare o caricare lo spazio, entra in modalità limitata e non sarà possibile inserire gli ologrammi o vedere gli ologrammi inseriti. Ecco alcune soluzioni possibili:

- Assicurarsi che nell'ambiente sia presente abbastanza luce in modo che HoloLens possa visualizzare e mappare lo spazio.
- Assicurarsi di essere connessi a una rete di Wi-Fi. Se non si è connessi a una rete Wi-Fi, HoloLens non riesce a identificare e caricare uno spazio noto.
- Se è necessario creare un nuovo spazio, connettersi a Wi-Fi e quindi riavviare il HoloLens.
- Per verificare se lo spazio corretto è attivo o per caricare manualmente uno spazio, passa a spazi del sistema di **Impostazioni**  >  **System**  >  **Spaces**.
- Se viene caricato lo spazio corretto e si verificano ancora problemi, lo spazio potrebbe essere danneggiato. Per risolvere il problema, selezionare lo spazio e quindi scegliere **Rimuovi**. Dopo aver rimosso lo spazio, HoloLens inizia a mappare l'ambiente circostante e a creare un nuovo spazio.

## Il mio HoloLens non può dire in quale spazio mi trovo

Se il HoloLens non riesce a identificare e caricare lo spazio in cui ci si trova automaticamente, verificare i fattori seguenti:

- Assicurarsi di essere connessi a Wi-Fi
- Verificare che nella sala sia presente molta luce
- Verificare che non siano state apportate modifiche importanti all'ambiente circostante.

È anche possibile caricare uno spazio manualmente o gestire gli spazi passando agli spazi di sistema **delle impostazioni**  >  **System**  >  **Spaces**.

## Viene visualizzato un errore di "spazio su disco ridotto"

È necessario liberare spazio di archiviazione eseguendo una o più delle operazioni seguenti:

- Eliminare alcuni spazi inutilizzati. Accedere a spazi del sistema **Impostazioni**  >  **System**  >  **Spaces**, selezionare uno spazio non più necessario e quindi scegliere **Rimuovi**.
- Rimuovere alcuni degli ologrammi posizionati.
- Eliminare alcune immagini e video dall'app foto.
- Disinstallare alcune app da HoloLens. Nell'elenco **tutte le app** toccare e tenere premuta l'app che si vuole disinstallare, quindi selezionare **Disinstalla**.

## Il mio HoloLens non riesce a creare un nuovo spazio

Il problema più probabile è che si sta esaurendo lo spazio di archiviazione. Provare uno dei [suggerimenti precedenti](#im-getting-a-low-disk-space-error) per liberare spazio su disco.

## L'emulatore HoloLens non funziona

Le informazioni sull'emulatore HoloLens si trovano nella documentazione per gli sviluppatori.  Per altre informazioni, vedere [risoluzione dei problemi relativi all'emulatore HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
