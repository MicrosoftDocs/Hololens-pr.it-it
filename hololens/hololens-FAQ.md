---
title: Domande frequenti su HoloLens dispositivi e ologrammi
description: Si hanno domande rapide sull'HoloLens o sull'interazione con gli ologrammi?  Questo articolo offre una risposta rapida e altre risorse.
keywords: hololens, domande frequenti, problema noto, guida
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428964"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Ologrammi delle interazioni e delle interazioni

Questo articolo consente di risolvere i problemi relativi all'inserimento di ologrammi, all'uso degli spazi e alla segnalazione di problemi relativi agli ologrammi.

Ogni volta che si verificano problemi, assicurarsi di:
- Provare [a riavviarlo](hololens-restart-recover.md) per verificare se ciò consente di risolvere il problema.
- Prima di risolvere il problema, assicurarsi HoloLens venga [addebitato](hololens2-charging.md) un addebito di almeno un'ora. 


Usare l'app Feedback per inviare informazioni sul problema. È possibile trovare l'app Feedback nel menu [ **Start**](holographic-home.md). 

Per suggerimenti su come usurare la HoloLens, vedere [Adattare](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Non è possibile creare nuovi spazi](#new-spaces-cant-be-created)
- [Non è possibile identificare o caricare spazi](#spaces-cant-be-identified-or-loaded)
- [Ricerca per categorie eliminare tutti gli spazi?](#how-do-i-delete-all-spaces)
- [Ologrammi l'aspetto non è quello giusto o ci si sposta](#holograms-dont-look-right-or-are-moving-around)
- [Messaggio "Ricerca dello spazio"](#finding-your-space-message)
- [Gli ologrammi previsti non vengono visualizzati nello spazio](#expected-holograms-arent-showing-in-my-space)
- [Non è possibile posizionare gli ologrammi o visualizzare gli ologrammi posizionati in precedenza](#cant-place-holograms-or-see-previously-placed-holograms)
- [Ologrammi scompaiono o sono racchiusi in altri ologrammi o oggetti](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Ologrammi visualizzati sull'altro lato di una barriera](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Dopo aver posizionato un ologramma su una barriera, sembra fluttuare](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Le app appaiono troppo vicine dopo lo spostamento](#apps-appear-too-close-after-moving-them)
- [Segnalazione di problemi con ologrammi instabili o inesatti](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Non è possibile creare nuovi spazi

Il problema più probabile è che lo spazio di archiviazione è insufficiente. [Liberare spazio su disco e](hololens-troubleshooting.md#low-disk-space-error) riprovare.

[Torna all'elenco](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Non è possibile identificare o caricare spazi

Se il HoloLens non è in grado di identificare e caricare automaticamente lo spazio in cui si è in esecuzione, controllare i fattori seguenti:

- Assicurarsi di essere connessi a Wi-Fi
- Assicurarsi che la stanza sia piena di luce
- Assicurarsi che non siano state apportate modifiche importanti all'ambiente circostante.

È anche possibile caricare uno spazio manualmente o gestire gli spazi selezionando **Impostazioni**  >  **di**  >  **sistema.**

[Torna all'elenco](#list)

## <a name="how-do-i-delete-all-spaces"></a>Ricerca per categorie eliminare tutti gli spazi?

*Presto disponibili*

[Torna all'elenco](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Ologrammi l'aspetto non è quello giusto o ci si sposta

Se l'aspetto degli ologrammi non è corretto (ad esempio, sono instabilità o traballanti o vengono visualizzati patch nere sopra), provare una di queste correzioni:

- [Pulire il visore del dispositivo](hololens1-hardware.md#care-and-cleaning) e assicurarsi che i sensori non blocchino nulla.
- Assicurarsi di essere in una stanza ben illuminata che non abbia molta disartizione diretta.
- Provare a spostarsi e a guardare l'ambiente circostante in modo che HoloLens possibile analizzarli in modo più completo.
- Se sono stati inseriti molti ologrammi, provare a rimuoverli.

Se si verificano ancora problemi, provare a eseguire l'app di calibrazione. Questa app calibra le HoloLens solo per consentire agli ologrammi di avere un aspetto ottimale. A tale scopo, passare **a** Impostazioni  >  **Utilità**  >  **di sistema**. In **Calibrazione** selezionare **Open Calibration (Apri calibrazione).**

[Torna all'elenco](#list)

## <a name="finding-your-space-message"></a>Messaggio "Ricerca dello spazio"

Quando HoloLens sta imparando o caricando uno spazio, è possibile che venga visualizzato un breve messaggio che indica "Ricerca dello spazio". Se questo messaggio viene visualizzato per più di pochi secondi, verrà visualizzato un altro messaggio sotto il menu Start che indica "Still looking for your space".

Questi messaggi significano che HoloLens problemi di mapping dello spazio. In questo caso, è possibile aprire le app, ma non inserire ologrammi nell'ambiente.

Se questi messaggi vengono visualizzati spesso, provare una o più delle correzioni seguenti:

- Assicurarsi di essere in una stanza ben illuminata che non abbia molta disartizione diretta.
- Assicurarsi che il visore del dispositivo sia pulito. [Informazioni su come pulire il visore](hololens1-hardware.md#care-and-cleaning).
- Assicurarsi di avere un segnale di Wi-Fi sicuro. Se si immette un nuovo ambiente senza Wi-Fi o un segnale Wi-Fi debole, HoloLens non sarà in grado di trovare lo spazio. Controllare la Wi-Fi di rete selezionando **Impostazioni**  >  **&amp; Rete Internet**  >  **Wi-Fi**.
- Provare a spostarsi più lentamente.

[Torna all'elenco](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Gli ologrammi previsti non vengono visualizzati nello spazio

Se gli ologrammi inseriti non sono visualizzati o se ne vengono visualizzati alcuni non previsti, provare una o più delle correzioni seguenti:

- Accendere alcune luci. HoloLens funziona meglio in uno spazio ben illuminato.
- Rimuovere gli ologrammi che non sono necessari selezionando Impostazioni  >  **system**  >  **Ologrammi**  >  **Remove nearby holograms (Rimuovi ologrammi vicini).** In caso contrario, se necessario, **selezionare Rimuovi tutti gli ologrammi**.

  > [!NOTE]
  > Se il layout o l'illuminazione nello spazio cambia in modo significativo, il dispositivo potrebbe avere problemi a identificare lo spazio e a visualizzare gli ologrammi.

[Torna all'elenco](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Non è possibile posizionare gli ologrammi o visualizzare gli ologrammi posizionati in precedenza

Se HoloLens non è in grado di eseguire il mapping o caricare lo spazio, viene attivata la modalità Limitata e non sarà possibile posizionare gli ologrammi o visualizzare gli ologrammi posizionati. Ecco alcuni aspetti da provare:

- Assicurarsi che nell'ambiente sia presente una luce sufficiente per HoloLens visualizzare ed eseguire il mapping dello spazio.
- Passare da uno a tre metri dal punto in cui si sta tentando di posizionare l'ologramma.
- Non posizionare gli ologrammi su superfici nere o riflettenti.
- Assicurarsi di essere connessi a una rete Wi-Fi rete. Se non si è connessi alla rete Wi-Fi, HoloLens può identificare e caricare uno spazio noto.
- Spostarsi tra le stanze in modo HoloLens possibile eseguire di nuovo l'analisi dell'ambiente circostante. Per vedere cosa è già stato digitalizzato, fare clic per visualizzare l'immagine della mesh di mapping.
- Se è necessario creare un nuovo spazio, connettersi al Wi-Fi, quindi riavviare il HoloLens.
- Per verificare se lo spazio corretto è attivo o per caricare manualmente uno spazio, passare a Impostazioni  >  **di**  >  **sistema.**
- Se viene caricato lo spazio corretto e si verificano ancora problemi, lo spazio potrebbe essere danneggiato. Per risolvere il problema, selezionare lo spazio e quindi selezionare **Rimuovi.** Dopo aver rimosso lo spazio, HoloLens inizia a eseguire il mapping dell'ambiente circostante e creare un nuovo spazio.

[Torna all'elenco](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Ologrammi scompaiono o sono racchiusi in altri ologrammi o oggetti

Se ci si avvicina troppo a un ologramma, il ripristino dell'ologramma verrà temporaneamente &mdash; rimosso. Inoltre, se sono stati posizionati più ologrammi vicini, alcuni potrebbero scomparire. Provare a rimuoverle alcune.

Ologrammi possono anche essere bloccati o racchiusi da altri ologrammi o da oggetti come le pareti. In questo caso, provare una delle correzioni seguenti:

- Se l'ologramma è racchiuso in un altro ologramma, spostare l'ologramma racchiuso in un'altra posizione. A tale scopo, selezionare **Regola** e quindi toccare e tenere premuto per posizionarlo.
- Se l'ologramma è racchiuso in una barriera, selezionare **Regola**, quindi andare verso la barriera fino a quando non viene visualizzato l'ologramma. Toccare e tenere premuto, quindi estrarre l'ologramma in avanti e fuori dalla barriera.
- Se non è possibile spostare l'ologramma usando i movimenti, usare la voce per rimuoverlo. Osservare l'ologramma e quindi pronunciare "Remove". Riaprire quindi l'ologramma e posizionarlo in una nuova posizione.

[Torna all'elenco](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Ologrammi vengono visualizzati sull'altro lato di un muro

Se si è molto vicini a una parete o se HoloLens non ha ancora analizzato la parete, è possibile visualizzare gli ologrammi presenti nella stanza successiva. Per analizzare la parete, passare da uno a tre metri dalla parete e fissarla.

Un oggetto nero o riflettente (ad esempio, un divano nero o un frigorifero in acciaio inossidabile) vicino alla parete può causare problemi quando HoloLens tenta di analizzare la parete. Se è presente un oggetto di questo tipo, analizzare l'altro lato della parete.

[Torna all'elenco](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Dopo aver posizionato un ologramma su una parete, sembra fluttuare

Un ologramma che si posiziona su una parete in genere sembra essere un pollice o così lontano dalla parete. Se sembra essere più lontano, provare una o più delle correzioni seguenti:

- Quando si posiziona un ologramma su una parete, posizionarsi tra uno e tre metri dalla parete e affrontare direttamente la parete.
- Toccare la parete per visualizzare l'immagine della mesh di mapping. Assicurarsi che la mesh sia allineata alla parete. In caso contrario, rimuovere l'ologramma, ripetere l'analisi della parete e riprovare.
- Se il problema persiste, eseguire l'app Calibrazione. È possibile trovarlo in utilità **Impostazioni**  >    >  **di sistema**.

[Torna all'elenco](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Le app vengono visualizzate troppo vicine dopo lo spostamento

Provare a spostarsi e a guardare l'area in cui si posiziona l'app in modo che HoloLens'area da angolazioni diverse. [Anche la pulizia della visiera](hololens1-hardware.md#care-and-cleaning) del dispositivo può essere utile.

[Torna all'elenco](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Segnalazione di problemi con ologrammi instabili o inesatti
 
1. Registrare e un [Acquisizione realtà mista video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) del problema. Questo video può essere caricato in un secondo momento Hub di Feedback come file allegato.  
1. Abilitare i dati di telemetria completi **tramite** l'app Impostazioni -> **Privacy** Diagnostics & feedback e in Dati di diagnostica facoltativi verificare che l'opzione sia  ->   impostata su **Sì** 
1. Per ottenere le correzioni più recenti per la scalabilità e la stabilità degli ologrammi, eseguire l'aggiornamento alla versione più recente del sistema operativo [Windows Holographic, (20H2 o versione successiva).](hololens-release-notes.md#windows-holographic-version-20h2) Dopo l'aggiornamento, eseguire le operazioni seguenti:
    1. Rimuovere tutti i Ologrammi tramite **Impostazioni** app -> **System** Ologrammi -> quindi selezionare Rimuovi tutti  ->   **gli ologrammi** e iniziare con una nuova mappa.
    1. Creare una nuova mappa dello spazio indossando il HoloLens e girando per la stanza e osservando tutte le aree e le superfici nello spazio. Eseguire questa operazione per 2-3 minuti.
    1. Eseguire la calibrazione ipd. Passare a **Impostazioni**  >  **utilità di**  >  **sistema**. In **Calibrazione** selezionare **Apri calibrazione.**
    1. Testare nuovamente lo scenario e verificare se è ancora persistente.
1. Se l'aggiornamento non risolve il problema, determinare [Hub di Feedback problema](hololens-feedback.md). Dopo aver compilato i commenti e  suggerimenti, è possibile usare il pulsante Condividi per creare un collegamento facile da condividere che può essere inviato quando si contatta il supporto tecnico.

[Torna all'elenco](#list)