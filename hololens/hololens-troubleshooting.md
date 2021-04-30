---
title: Risoluzione dei problemi
description: Rimanere aggiornati sulle soluzioni più comuni per i problemi dei dispositivi HoloLens e le tecniche di risoluzione dei problemi.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemi, bug, risoluzione dei problemi, correzione, guida, supporto, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309515"
---
# <a name="troubleshooting"></a>Risoluzione dei problemi

Questo articolo descrive come risolvere diversi problemi comuni di HoloLens.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>HoloLens non risponde o non si avvia

Se HoloLens non si avvia:

- Se i LED accanto al pulsante di alimentazione non si accende o un solo LED lampeggia brevemente, potrebbe essere necessario caricare [HoloLens.](hololens-recovery.md#charge-the-device)
- Se i LED si accendeno quando si preme il pulsante di alimentazione, ma non è possibile visualizzare nulla sui display, pre-ripristinare [il dispositivo](hololens-recovery.md#hard-reset-procedure).

Se HoloLens si blocca o non risponde:

- Disattiva HoloLens premendo il pulsante di alimentazione fino a quando tutti e cinque i LED non si spegnino o per 15 secondi se i LED non rispondono. Per avviare HoloLens, premi di nuovo il pulsante di alimentazione.

Se questi passaggi non funzionano, [](hololens-recovery.md) puoi provare a ripristinare il dispositivo HoloLens 2 [o HoloLens (prima generazione).](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Gli ologrammi non sembrano buoni

Se gli ologrammi sono instabili, salti o non sembrano proprio, provare:

- Pulizia del visore del dispositivo e della barra del sensore nella parte anteriore di HoloLens.
- Aumentare la luce nella stanza.
- A guardare l'ambiente circostante in modo che HoloLens possa analizzarli in modo più completo.
- Calibrazione di HoloLens per gli occhi. Passare a **Impostazioni**  >  **Utilità di**  >  **sistema**. In **Calibrazione** selezionare **Open Calibration (Apri calibrazione).**
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Segnalazione di problemi in cui gli ologrammi sono instabili o non sembrano proprio
 
1. Registrare e un [Acquisizione realtà mista video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) del problema. Questo video può essere caricato in un secondo momento Hub di Feedback come file allegato.  
1. Abilitare i dati  di telemetria completi tramite l'app Impostazioni -> **Privacy** Diagnostics & feedback e  ->  **in** **Dati di diagnostica** facoltativi assicurarsi che l'interruttore sia impostato su **Sì**
1. Ottenere le correzioni più recenti per la scalabilità e la stabilità degli ologrammi aggiornando al sistema operativo [Windows Holographic più recente (20H2 o versione successiva).](hololens-release-notes.md#windows-holographic-version-20h2) Dopo l'aggiornamento, eseguire le operazioni seguenti:
    1. Rimuovere tutti gli ologrammi tramite **l'app** Impostazioni -> **ologrammi** di sistema -> quindi selezionare Rimuovi tutti  ->   **gli ologrammi** e iniziare con una nuova mappa.
    1. Creare una nuova mappa dello spazio indossando HoloLens e girando per la stanza e osservando tutte le aree e le superfici nello spazio. Eseguire questa operazione per 2-3 minuti.
    1. Eseguire la calibrazione ipd. Passare a **Impostazioni**  >  **Utilità di**  >  **sistema**. In **Calibrazione** selezionare **Apri calibrazione.**
    1. Testare nuovamente lo scenario e verificare se è ancora persistente.
1. Se l'aggiornamento non risolve il problema, determinare [Hub di Feedback problema](hololens-feedback.md). Dopo aver compilato i commenti e  suggerimenti, è possibile usare il pulsante Condividi per creare un collegamento facile da condividere che può essere inviato quando si contatta il supporto tecnico.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens non risponde all'input manuale

Per assicurarsi che HoloLens possa visualizzare le mani, è necessario mantenerle nel frame del movimento.  La home page di realtà mista fornisce commenti e suggerimenti che consentono di sapere quando vengono rilevate le mani.  Il feedback è diverso nelle diverse versioni di HoloLens:
- In HoloLens (prima generazione), il cursore dello sguardo cambia da punto a anello
- Al HoloLens 2, un cursore a punta del dito viene visualizzato quando la mano è vicina a un ardesia e un raggio della mano viene visualizzato quando gli ardesi sono più lontani

Molte app immersive seguono modelli di input simili a quelli della home page di Realtà mista.  Altre informazioni sull'uso dell'input manuale [in HoloLens (prima generazione)](hololens1-basic-usage.md#use-hololens-with-your-hands) [e HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se si dispone di un paio di scarpe, si noti che alcuni tipi di scarpe non funzionano con il tracciamento delle mani.  Un esempio comune è quello dei 1000 scarpe nere, che tendono ad assalere la luce a indotta e non vengono prelevati dalla fotocamera di profondità.  Se il lavoro prevede un paio di scarpe da forno, è consigliabile provare un colore più chiaro, ad esempio blu o grigio.  Un altro esempio è l'utilizzo di ampi ovaiosi, che tendono a nascondere la forma della mano. Per ottenere risultati ottimali, è consigliabile usare i fori il più possibile adattabili al modulo.

Se il visore ha impronte digitali o sbavature, usa la pulizia del microfibero fornita con HoloLens per pulire il visore.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens non risponde ai comandi vocali

Se Cortana non risponde ai comandi vocali, assicurarsi che Cortana sia attivato. Nell'elenco Tutte le app selezionare **Cortana**  >  **Menu** Notebook Settings  >  **(Impostazioni notebook menu** Cortana) per  >   apportare modifiche. Per altre informazioni su ciò che puoi dire, vedi [Usare la voce con HoloLens.](hololens-cortana.md)

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Non è possibile posizionare gli ologrammi o visualizzare gli ologrammi inseriti in precedenza

Se HoloLens non può eseguire il mapping o caricare lo spazio, viene attivata la modalità Limitata e non sarà possibile posizionare gli ologrammi o visualizzare gli ologrammi posizionati. Ecco alcuni aspetti da provare:

- Assicurarsi che nell'ambiente sia presente una luce sufficiente in modo che HoloLens possa visualizzare ed eseguire il mapping dello spazio.
- Assicurarsi di essere connessi a una rete Wi-Fi rete. Se non sei connesso al Wi-Fi, HoloLens non può identificare e caricare uno spazio noto.
- Se è necessario creare un nuovo spazio, connettersi al Wi-Fi e quindi riavviare HoloLens.
- Per verificare se lo spazio corretto è attivo o per caricare manualmente uno spazio, passare a **Impostazioni** Spazi  >  **di**  >  **sistema.**
- Se viene caricato lo spazio corretto e si verificano ancora problemi, è possibile che lo spazio sia danneggiato. Per risolvere il problema, selezionare lo spazio e quindi **selezionare Rimuovi**. Dopo aver rimosso lo spazio, HoloLens inizia a mappare l'ambiente circostante e a creare un nuovo spazio.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>HoloLens non è in grado di indicare lo spazio in cui si è in

Se HoloLens non è in grado di identificare e caricare automaticamente lo spazio in cui si è in esecuzione, verificare i fattori seguenti:

- Assicurarsi di essere connessi a Wi-Fi
- Assicurarsi che ci sia molta luce nella stanza
- Assicurarsi che non siano state apportate modifiche importanti all'ambiente circostante.

È anche possibile caricare uno spazio manualmente o gestire gli spazi in **Impostazioni**  >  **Spazi di**  >  **sistema**.

## <a name="im-getting-a-low-disk-space-error"></a>Viene visualizzato un errore di "spazio su disco insufficiente"

È necessario liberare spazio di archiviazione eseguendo una o più delle operazioni seguenti:

- Eliminare alcuni spazi inutilizzati. Passare a **Impostazioni**  >  **Spazi di**  >  **sistema,** selezionare uno spazio non più necessario e quindi selezionare Rimuovi .
- Rimuovere alcuni ologrammi inseriti.
- Eliminare alcune immagini e video dall'app Foto.
- Disinstallare alcune app da HoloLens. **Nell'elenco Tutte le app** toccare e tenere premuta l'app da disinstallare e quindi selezionare **Disinstalla**.

## <a name="my-hololens-cant-create-a-new-space"></a>HoloLens non può creare un nuovo spazio

Il problema più probabile è che lo spazio di archiviazione è insufficiente. Provare uno dei suggerimenti [precedenti per](#im-getting-a-low-disk-space-error) liberare spazio su disco.

## <a name="the-hololens-emulator-isnt-working"></a>L'emulatore HoloLens non funziona

Le informazioni sull'emulatore HoloLens sono disponibili nella documentazione per sviluppatori.  Altre informazioni sulla risoluzione [dei problemi dell'emulatore HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
