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
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397262"
---
# <a name="troubleshoot-common-issues"></a>Risolvere i problemi comuni

Questo articolo descrive come risolvere diversi problemi comuni di HoloLens.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>HoloLens non risponde o non si avvia

Se HoloLens non viene avviato:

- Se i LED accanto al pulsante di accensione non si accrendono o un solo LED lampeggia brevemente, potrebbe essere necessario caricare [HoloLens.](hololens-recovery.md#charge-the-device)
- Se i LED si accrendono quando si preme il pulsante di alimentazione ma non è possibile visualizzare alcun elemento sui display, pre-configurare un [hard reset del dispositivo](hololens-recovery.md#hard-reset-procedure).

Se HoloLens viene bloccato o non risponde:

- Disattivare HoloLens premendo il pulsante di accensione fino a quando tutti e cinque i LED non si spegnino o per 15 secondi se i LED non rispondono. Per avviare HoloLens, premere di nuovo il pulsante di alimentazione.

Se questi passaggi non funzionano, [](hololens-recovery.md) è possibile provare a ripristinare il dispositivo HoloLens 2 [o HoloLens (prima generazione).](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Gli ologrammi non sembrano buoni

Se gli ologrammi sono instabili, salti o non hanno un aspetto giusto, provare:

- Pulizia della visiera del dispositivo e della barra del sensore nella parte anteriore di HoloLens.
- Aumentare la luce nella stanza.
- Andare in giro e guardare l'ambiente circostante in modo che HoloLens possa analizzarli in modo più completo.
- Calibrazione di HoloLens per gli occhi. Passare a **Impostazioni**  >  **Utilità di**  >  **sistema**. In **Calibrazione** selezionare **Apri calibrazione.**
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Segnalazione di problemi in cui gli ologrammi sono instabili o non hanno un aspetto giusto
 
1. Registrare e un [Acquisizione realtà mista video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) del problema. Questo video può essere caricato in un secondo momento Hub di Feedback come file allegato.  
1. Abilitare la telemetria completa tramite **l'app** Impostazioni -> **Privacy** Diagnostics & feedback e in Dati di diagnostica facoltativi verificare che l'interruttore  ->   sia impostato su **Sì** 
1. Ottenere le correzioni più recenti per la scalabilità e la stabilità degli ologrammi aggiornando al sistema operativo [Windows Holographic più recente (20H2 o versione successiva).](hololens-release-notes.md#windows-holographic-version-20h2) Dopo l'aggiornamento, eseguire le operazioni seguenti:
    1. Rimuovere tutti gli ologrammi tramite **l'app** Settings -> **System**  ->  **Holograms** -> quindi selezionare **Remove all holograms** (Rimuovi tutti gli ologrammi) e iniziare con una mappa nuova.
    1. Crea una nuova mappa dello spazio con HoloLens, aggirando la stanza e osservando tutte le aree e le superfici nello spazio. Eseguire questa operazione per 2-3 minuti.
    1. Eseguire la calibrazione ipd. Passare a **Impostazioni**  >  **Utilità di**  >  **sistema**. In **Calibrazione** selezionare **Open Calibration (Apri calibrazione).**
    1. Testare nuovamente lo scenario e verificare se è ancora persistente.
1. Se l'aggiornamento non risolve il problema, determinare [Hub di Feedback problema.](hololens-feedback.md) Dopo aver inserito commenti e suggerimenti, è possibile usare il pulsante Condividi per creare un collegamento facile da condividere che può essere inviato quando si contatta il supporto tecnico. 

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens non risponde all'input manuale

Per assicurarsi che HoloLens possa visualizzare le mani, devi mantenerle nel fotogramma del movimento.  La home page di Realtà mista fornisce commenti e suggerimenti che consentono di sapere quando vengono tracciate le mani.  Il feedback è diverso nelle diverse versioni di HoloLens:
- In HoloLens (prima generazione), il cursore sguardo fisso cambia da punto a anello
- In HoloLens 2 viene visualizzato un cursore punta del dito quando la mano è vicina a uno slate e viene visualizzato un raggio della mano quando gli slate sono più lontano

Molte app immersive seguono modelli di input simili a quelli di Mixed Reality Home.  Altre informazioni sull'uso dell'input manuale [in HoloLens (prima generazione)](hololens1-basic-usage.md#use-hololens-with-your-hands) [e HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se si indossano i guanto, si noti che alcuni tipi di guanto non funzionano con il tracciamento delle mani.  Un esempio comune sono i guanto di gomma nera, che tendono ad assorbire la luce a raggi infrarossi e non vengono prelevati dalla fotocamera di profondità.  Se il lavoro prevede i guanto di gomma, è consigliabile provare un colore più chiaro, ad esempio blu o grigio.  Un altro esempio sono i grossi guanto da baggy, che tendono a nascondere la forma della mano. Per ottenere risultati ottimali, è consigliabile usare i guanto il più possibile adattabili al modulo.

Se la visiera ha impronte digitali o sbavature, usare il panno di pulizia microfibra fornito con HoloLens per pulire la visiera in modo pulito.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens non risponde ai comandi vocali

Se Cortana non risponde ai comandi vocali, assicurarsi che Cortana sia attivato. Nell'elenco Tutte le app selezionare Impostazioni notebook del menu **Cortana**  >    >    >   per apportare modifiche. Per altre informazioni su ciò che è possibile dire, vedere [Usare la voce con HoloLens.](hololens-cortana.md)

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Non è possibile posizionare ologrammi o visualizzare gli ologrammi inseriti in precedenza

Se HoloLens non è in grado di eseguire il mapping o caricare lo spazio, viene attivata la modalità Limitata e non sarà possibile posizionare ologrammi o visualizzare gli ologrammi inseriti. Ecco alcuni aspetti da provare:

- Assicurarsi che nell'ambiente sia presente una luce sufficiente in modo che HoloLens possa visualizzare ed eseguire il mapping dello spazio.
- Assicurarsi di essere connessi a una rete Wi-Fi rete. Se non si è connessi al Wi-Fi, HoloLens non può identificare e caricare uno spazio noto.
- Se è necessario creare un nuovo spazio, connettersi al Wi-Fi, quindi riavviare HoloLens.
- Per verificare se lo spazio corretto è attivo o per caricare manualmente uno spazio, passare a **Impostazioni**  >  **Spazi di**  >  **sistema**.
- Se viene caricato lo spazio corretto e si verificano ancora problemi, lo spazio potrebbe essere danneggiato. Per risolvere il problema, selezionare lo spazio e quindi selezionare **Rimuovi.** Dopo aver rimosso lo spazio, HoloLens inizia a mappare l'ambiente circostante e a creare un nuovo spazio.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>HoloLens non è in grado di indicare lo spazio in cui si è in

Se HoloLens non è in grado di identificare e caricare automaticamente lo spazio in cui ti sei inserito, verifica i fattori seguenti:

- Assicurarsi di essere connessi a Wi-Fi
- Assicurarsi che la stanza sia piena di luce
- Assicurarsi che non siano state apportate modifiche importanti all'ambiente circostante.

È anche possibile caricare uno spazio manualmente o gestire gli spazi selezionando Impostazioni **Spazi**  >  **di**  >  **sistema.**

## <a name="im-getting-a-low-disk-space-error"></a>Viene visualizzato un errore di "spazio su disco insufficiente"

È necessario liberare spazio di archiviazione eseguendo una o più delle operazioni seguenti:

- Eliminare alcuni spazi inutilizzati. Passare a **Impostazioni**  >  **Spazi di**  >  **sistema,** selezionare uno spazio non più necessario e quindi selezionare **Rimuovi.**
- Rimuovere alcuni degli ologrammi posizionati.
- Eliminare alcune immagini e video dall'app Foto.
- Disinstallare alcune app da HoloLens. **Nell'elenco Tutte le** app toccare e tenere premuta l'app da disinstallare e quindi selezionare **Disinstalla.**

## <a name="my-hololens-cant-create-a-new-space"></a>HoloLens non può creare un nuovo spazio

Il problema più probabile è che lo spazio di archiviazione è insufficiente. Provare uno dei suggerimenti [precedenti per](#im-getting-a-low-disk-space-error) liberare spazio su disco.

## <a name="the-hololens-emulator-isnt-working"></a>L'emulatore HoloLens non funziona

Le informazioni sull'emulatore HoloLens sono disponibili nella documentazione per sviluppatori.  Altre informazioni sulla [risoluzione dei problemi dell'emulatore HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
