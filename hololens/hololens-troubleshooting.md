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
keywords: problemi, bug, risoluzione dei problemi, risolvere, guida, supporto, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283047"
---
# Risoluzione dei problemi

Questo articolo descrive come risolvere diversi problemi comuni di HoloLens.

## Il mio HoloLens non risponde o non si avvia

Se HoloLens non si avvia:

- Se i LED accanto al pulsante di accensione non si illuminano o un solo LED lampeggia brevemente, potrebbe essere necessario caricare [HoloLens.](hololens-recovery.md#charge-the-device)
- Se i LED si accende quando premi il pulsante di alimentazione ma non vedi nulla sugli schermi, preforma un ripristino del [dispositivo.](hololens-recovery.md#hard-reset-procedure)

Se HoloLens diventa bloccato o non risponde:

- Spegni HoloLens premendo il pulsante di alimentazione fino a quando tutti e cinque i LED non si spegnino o per 15 secondi se i LED non rispondono. Per avviare HoloLens, premi di nuovo il pulsante di alimentazione.

Se questi passaggi non funzionano, puoi provare a recuperare il dispositivo [HoloLens 2](hololens-recovery.md) o [HoloLens (prima generazione).](hololens1-recovery.md)

## Gli ologrammi non hanno un aspetto positivo

Se gli ologrammi sono instabili, instabili o non hanno un aspetto giusto, prova:

- Pulizia della visiera del dispositivo e della barra dei sensori nella parte anteriore di HoloLens.
- Aumentando la luce nella tua stanza.
- Andare in giro e guardare l'ambiente circostante in modo che HoloLens possa analizzarli in modo più completo.
- Calibrazione di HoloLens per gli occhi. Passare a **Impostazioni**  >  **Utilità di**  >  **sistema.** In **Calibrazione**, selezionare **Apri Calibrazione**.
 
### Segnalazione di problemi in cui gli ologrammi sono instabili o non hanno un aspetto giusto
 
1. Registrare e un [video dell'acquisizione](holographic-photos-and-videos.md#capture-a-mixed-reality-video) in realtà mista del problema. Questo video può essere caricato in seguito tramite Hub di Feedback come file allegato.  
1. Abilitare la telemetria completa tramite **l'app** Impostazioni -> **feedback**sulla diagnostica della privacy & e in Dati di diagnostica facoltativi verificare che l'interruttore  ->  **** sia impostato su **Attivato** ****
1. Ottieni le correzioni più recenti della scala ologramma e della stabilità aggiornando il sistema operativo Windows Holographic più recente [(20H2 o versione successiva).](hololens-release-notes.md#windows-holographic-version-20h2) Dopo l'aggiornamento, eseguire le operazioni seguenti:
    1. Rimuovi tutti gli ologrammi tramite **l'app** Impostazioni -> **ologrammi**di sistema -> quindi seleziona Rimuovi tutti  ->  **** **gli ologrammi** e inizia con una nuova mappa.
    1. Crea una nuova mappa del tuo spazio indossando HoloLens e aggirando la tua stanza e osservando tutte le aree e le superfici nello spazio. Eseguire questa operazione per 2-3 minuti.
    1. Eseguire la calibrazione ipd. Passare a **Impostazioni**  >  **Utilità di**  >  **sistema.** In **Calibrazione**, selezionare **Apri Calibrazione**.
    1. Testare nuovamente lo scenario e verificare se persiste ancora.
1. Se l'aggiornamento non risolve il problema, invia un problema [all'Hub di Feedback.](hololens-feedback.md) Dopo aver inviato il feedback, **** puoi usare il pulsante Condividi per creare un collegamento facile da condividere che può essere inviato quando contatti il supporto.

## HoloLens non risponde all'input della mano

Per assicurarti che HoloLens possa vedere le mani, devi tenerle nel fotogramma del gesto.  The Mixed Reality Home provides feedback that lets you know when your hands are tracked.  Il feedback è diverso nelle diverse versioni di HoloLens:
- In HoloLens (prima generazione), il cursore dello sguardo fisso cambia da un punto a un anello
- In HoloLens 2, viene visualizzato un cursore con la punta delle dita quando la mano è vicina a una lavagna e quando gli ardesia sono più lontani viene visualizzato un raggio della mano

Molte app immersive seguono modelli di input simili alla home page di realtà mista.  Altre informazioni sull'uso dell'input manuale [in HoloLens (prima generazione)](hololens1-basic-usage.md#use-hololens-with-your-hands) e [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Se indossi i guanto, tieni presente che alcuni tipi di guanto non funzionano con il tracciamento delle mani.  Un esempio comune sono i guanto di gomma nera, che tendono ad assorbire la luce a infrarossi e non vengono raccolti dalla fotocamera di profondità.  Se il tuo lavoro riguarda i guanti di gomma, ti consigliamo di provare un colore più chiaro, ad esempio blu o grigio.  Un altro esempio sono i grandi guanti baggy, che tendono a oscurare la forma della mano. Per ottenere risultati ottimali, è consigliabile utilizzare i guanti il più possibile adattabili alla forma.

Se la visiera ha impronte digitali o sbavature, usa il panno per la pulizia in microfibra fornito con HoloLens per pulire delicatamente la visiera.

## HoloLens non risponde ai comandi vocali

Se Cortana non risponde ai comandi vocali, assicurati che Cortana sia attivata. Nell'elenco Tutte le app seleziona Impostazioni blocco appunti del menu **di Cortana**  >  ****  >  ****  >  **** per apportare modifiche. Per ulteriori informazioni sulle frasi che è possibile pronunciare, vedere [Usare la voce con HoloLens](hololens-cortana.md).

## I can't place holograms or see holograms that I previously placed

Se HoloLens non è in grado di mappare o caricare lo spazio, entra in modalità Limitata e non potrai posizionare gli ologrammi o vedere gli ologrammi che hai posizionato. Ecco alcune soluzioni possibili:

- Assicurati che nell'ambiente ci sia luce sufficiente in modo che HoloLens possa vedere e mappare lo spazio.
- Assicurarsi di essere connessi a una Wi-Fi rete. Se non sei connesso al Wi-Fi, HoloLens non può identificare e caricare uno spazio noto.
- Se devi creare un nuovo spazio, connettiti al Wi-Fi e quindi riavvia HoloLens.
- Per verificare se lo spazio corretto è attivo o per caricare manualmente uno spazio, passare a **Impostazioni**  >  **Di**  >  **sistema.**
- Se viene caricato lo spazio corretto e si verificano ancora problemi, è possibile che lo spazio sia danneggiato. Per risolvere il problema, selezionare lo spazio, quindi **selezionare Rimuovi.** Dopo aver rimosso lo spazio, HoloLens inizia a mappare l'ambiente circostante e a creare un nuovo spazio.

## My HoloLens can't tell what space I'm in

Se HoloLens non è in grado di identificare e caricare automaticamente lo spazio in cui si è in esecuzione, controllare i fattori seguenti:

- Assicurarsi di essere connessi a Wi-Fi
- Assicurarsi che la stanza sia piena di luce
- Assicurati che non siano state apportate modifiche principali all'ambiente circostante.

Puoi anche caricare uno spazio manualmente o gestire gli spazi andando in **Impostazioni**  >  **Spazi di**  >  **sistema.**

## Viene visualizzato un errore di "spazio su disco insufficiente"

È necessario liberare spazio di archiviazione eseguendo una o più delle operazioni seguenti:

- Eliminare alcuni spazi inutilizzati. Vai a **Impostazioni**  >  ****  >  **Spazi di sistema,** seleziona uno spazio non più necessario e quindi seleziona **Rimuovi.**
- Rimuovere alcuni degli ologrammi posizionati.
- Elimina alcune immagini e video dall'app Foto app.
- Disinstallare alcune app da HoloLens. **Nell'elenco Tutte le app** tocca e tieni premuta l'app che vuoi disinstallare e quindi seleziona **Disinstalla.**

## Il mio HoloLens non può creare un nuovo spazio

Il problema più probabile è che lo spazio di archiviazione è insufficiente. Provare uno dei suggerimenti [precedenti per](#im-getting-a-low-disk-space-error) liberare spazio su disco.

## L'emulatore di HoloLens non funziona

Le informazioni sull'emulatore di HoloLens sono disponibili nella documentazione per sviluppatori.  Altre informazioni sulla risoluzione [dei problemi relativi all'emulatore di HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
