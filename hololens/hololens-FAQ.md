---
title: Domande frequenti su dispositivi e ologrammi HoloLens
description: Si ha una domanda rapida su HoloLens o sull'interazione con gli ologrammi?  Questo articolo offre una risposta rapida e altre risorse.
keywords: hololens, domande frequenti, problemi noti, guida
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
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924027"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Risoluzione dei problemi relativi a ologrammi e interazioni

Questo articolo risolve i problemi relativi all'inserimento di ologrammi, all'uso degli spazi e alla segnalazione di problemi con gli ologrammi.

In caso di problemi, assicurarsi di:
- Provare [a riavviarlo](hololens-restart-recover.md) per verificare se ciò consente di risolvere i problemi.
- Prima di risolvere il problema, assicurarsi che a HoloLens venga addebitato [un](hololens2-charging.md) addebito di almeno un'ora. 


Usare l'app Feedback per inviare informazioni sul problema. L'app Feedback è nel menu [ **Start**](holographic-home.md). 

Per suggerimenti su come utilizzare HoloLens, vedere [Adattare](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Non è possibile creare nuovi spazi](#new-spaces-cant-be-created)
- [Gli spazi non possono essere identificati o caricati](#spaces-cant-be-identified-or-loaded)
- [Ricerca per categorie eliminare tutti gli spazi?](#how-do-i-delete-all-spaces)
- [Gli ologrammi non hanno un aspetto giusto o si spostano](#holograms-dont-look-right-or-are-moving-around)
- [Messaggio "Ricerca dello spazio"](#finding-your-space-message)
- [Gli ologrammi previsti non vengono visualizzati nello spazio](#expected-holograms-arent-showing-in-my-space)
- [Non è possibile posizionare ologrammi o visualizzare ologrammi posizionati in precedenza](#cant-place-holograms-or-see-previously-placed-holograms)
- [Gli ologrammi scompaiono o sono racchiusi in altri ologrammi o oggetti](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Gli ologrammi vengono visualizzati sull'altro lato di un muro](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Dopo aver posizionato un ologramma su una parete, sembra fluttuare](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Le app vengono visualizzate troppo vicine dopo lo spostamento](#apps-appear-too-close-after-moving-them)
- [Segnalazione di problemi con ologrammi instabili o inesatti](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Non è possibile creare nuovi spazi

Il problema più probabile è che lo spazio di archiviazione è insufficiente. [Liberare spazio su disco e](hololens-troubleshooting.md#low-disk-space-error) quindi riprovare.

[Torna all'elenco](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Gli spazi non possono essere identificati o caricati

Se HoloLens non è in grado di identificare e caricare automaticamente lo spazio in cui si è in esecuzione, verificare i fattori seguenti:

- Assicurarsi di essere connessi a Wi-Fi
- Assicurarsi che ci sia molta luce nella stanza
- Assicurarsi che non siano state apportate modifiche importanti all'ambiente circostante.

È anche possibile caricare uno spazio manualmente o gestire gli spazi in **Impostazioni**  >  **Spazi di**  >  **sistema**.

[Torna all'elenco](#list)

## <a name="how-do-i-delete-all-spaces"></a>Ricerca per categorie eliminare tutti gli spazi?

*Presto disponibili*

[Torna all'elenco](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Gli ologrammi non hanno un aspetto giusto o si spostano

Se gli ologrammi non hanno un aspetto corretto(ad esempio, sono instabilità o traballanti o sono visualizzati patch nere sopra di essi), provare una di queste correzioni:

- [Pulire la visiera del](hololens1-hardware.md#care-and-cleaning) dispositivo e assicurarsi che nulla blocchi i sensori.
- Assicurarsi di essere in una stanza ben illuminata che non ha molta luce diretta.
- Provare a guardare l'ambiente circostante in modo che HoloLens possa analizzarli in modo più completo.
- Se sono stati inseriti molti ologrammi, provare a rimuoverli.

Se si verificano ancora problemi, provare a eseguire l'app Calibrazione. Questa app calibra holoLens solo per consentire agli ologrammi di ottenere risultati ottimali. A tale scopo, passare a **Impostazioni Utilità**  >  **di**  >  **sistema**. In **Calibrazione** selezionare **Apri calibrazione.**

[Torna all'elenco](#list)

## <a name="finding-your-space-message"></a>Messaggio "Ricerca dello spazio"

Quando HoloLens sta imparando o caricando uno spazio, è possibile che venga visualizzato un breve messaggio che indica "Ricerca dello spazio". Se questo messaggio viene visualizzato per più di pochi secondi, verrà visualizzato un altro messaggio sotto il menu Start che indica "Ancora alla ricerca dello spazio".

Questi messaggi significano che HoloLens ha problemi a eseguire il mapping dello spazio. In questo caso, è possibile aprire le app, ma non è possibile inserire ologrammi nell'ambiente.

Se questi messaggi vengono visualizzati spesso, provare una o più delle correzioni seguenti:

- Assicurarsi di essere in una stanza ben illuminata che non ha molta luce diretta.
- Assicurarsi che la visiera del dispositivo sia pulita. [Informazioni su come pulire la visiera.](hololens1-hardware.md#care-and-cleaning)
- Assicurarsi di avere un segnale Wi-Fi sicuro. Se si immette un nuovo ambiente senza Wi-Fi o un segnale Wi-Fi debole, HoloLens non sarà in grado di trovare lo spazio. Controllare la Wi-Fi connessione selezionando **Impostazioni**  >  **Rete &amp; Internet**  >  **Wi-Fi**.
- Provare a spostarsi più lentamente.

[Torna all'elenco](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Gli ologrammi previsti non vengono visualizzati nello spazio

Se gli ologrammi inseriti non sono visualizzati o se ne vengono visualizzati alcuni non previsti, provare una o più delle correzioni seguenti:

- Accendere alcune luci. HoloLens funziona meglio in uno spazio ben illuminato.
- Per rimuovere gli ologrammi non necessari, vedere **Impostazioni**  >    >  **Ologrammi** di sistema  >  **Rimuovi ologrammi vicini.** In caso contrario, selezionare **Rimuovi tutti gli ologrammi.**

  > [!NOTE]
  > Se il layout o l'illuminazione nello spazio cambiano in modo significativo, il dispositivo potrebbe avere problemi a identificare lo spazio e visualizzare gli ologrammi.

[Torna all'elenco](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Non è possibile posizionare ologrammi o visualizzare ologrammi posizionati in precedenza

Se HoloLens non è in grado di eseguire il mapping o caricare lo spazio, viene attivata la modalità Limitata e non sarà possibile posizionare ologrammi o visualizzare gli ologrammi inseriti. Ecco alcuni aspetti da provare:

- Assicurarsi che nell'ambiente sia presente una luce sufficiente in modo che HoloLens possa visualizzare ed eseguire il mapping dello spazio.
- Posizionarsi tra uno e tre metri da dove si sta tentando di posizionare l'ologramma.
- Non posizionare ologrammi su superfici nere o riflettenti.
- Assicurarsi di essere connessi a una rete Wi-Fi rete. Se non si è connessi al Wi-Fi, HoloLens non può identificare e caricare uno spazio noto.
- Aggirare le stanze in modo che HoloLens possa eseguire nuovamente l'analisi dell'ambiente circostante. Per visualizzare ciò che è già stato analizzato, toccare l'aria per visualizzare l'immagine della mesh di mapping.
- Se è necessario creare un nuovo spazio, connettersi al Wi-Fi, quindi riavviare HoloLens.
- Per verificare se lo spazio corretto è attivo o per caricare manualmente uno spazio, passare a **Impostazioni**  >  **Spazi di**  >  **sistema**.
- Se lo spazio corretto viene caricato e si verificano ancora problemi, è possibile che lo spazio sia danneggiato. Per risolvere il problema, selezionare lo spazio e quindi **selezionare Rimuovi**. Dopo aver rimosso lo spazio, HoloLens inizia a mappare l'ambiente circostante e a creare un nuovo spazio.

[Torna all'elenco](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Gli ologrammi scompaiono o sono racchiusi in altri ologrammi o oggetti

Se ci si avvicina troppo a un ologramma, questo scompare temporaneamente per ripristinare &mdash; l'ologramma, semplicemente allontanarsi da esso. Inoltre, se sono stati posizionati più ologrammi vicini, alcuni potrebbero scomparire. Provare a rimuovere alcuni elementi.

Gli ologrammi possono anche essere bloccati o racchiusi da altri ologrammi o da oggetti come le pareti. In questo caso, provare una delle correzioni seguenti:

- Se l'ologramma è racchiuso in un altro ologramma, spostare l'ologramma racchiuso in un'altra posizione. A tale scopo, selezionare **Regola**, quindi toccare e tenere premuto per posizionarlo.
- Se l'ologramma è racchiuso in una parete, selezionare **Regola**, quindi andare verso la parete fino a quando non viene visualizzato l'ologramma. Toccare e tenere premuto, quindi tirare l'ologramma in avanti e fuori dalla parete.
- Se non è possibile spostare l'ologramma usando i movimenti, usare la voce per rimuoverlo. Osservare l'ologramma e quindi pronunciare "Rimuovi". Riaprire quindi l'ologramma e posizionarlo in una nuova posizione.

[Torna all'elenco](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Gli ologrammi vengono visualizzati sull'altro lato di una barriera

Se sei molto vicino a una barriera o se HoloLens non ha ancora digitalizzato la barriera, puoi vedere gli ologrammi presenti nella stanza successiva. Per eseguire la scansione della barriera, passare da uno a tre metri dalla barriera e fissarla.

Un oggetto nero o riflettente (ad esempio, un divano nero o un refrigeratore in aureo senza problemi) vicino alla barriera può causare problemi quando HoloLens prova a eseguire la scansione della pareti. Se è presente un oggetto di questo tipo, analizzare l'altro lato della barriera.

[Torna all'elenco](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Dopo aver posizionato un ologramma su una barriera, sembra essere mobile

Un ologramma che si posiziona su una barriera in genere sembra essere un pollice o così lontano dalla barriera. Se sembra essere più lontano, provare una o più delle correzioni seguenti:

- Quando si posiziona un ologramma su una barriera, posizionarsi tra uno e tre metri dalla barriera e affrontare direttamente la superficie.
- Toccare la barriera per visualizzare l'immagine della mesh di mapping. Assicurarsi che la mesh sia allineata alla superficie. In caso contrario, rimuovere l'ologramma, ripetere l'analisi della barriera e riprovare.
- Se il problema persiste, eseguire l'app Calibrazione. È possibile trovarlo in Impostazioni **Utilità**  >  **di**  >  **sistema**.

[Torna all'elenco](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Le app appaiono troppo vicine dopo lo spostamento

Provare a spostarsi e a esaminare l'area in cui si posiziona l'app in modo che HoloLens animi l'area da diverse angolazioni. [Può essere utile anche pulire il visore](hololens1-hardware.md#care-and-cleaning) del dispositivo.

[Torna all'elenco](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Segnalazione di problemi con ologrammi instabili o inesatti
 
1. Registrare e un [Acquisizione realtà mista video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) del problema. Questo video può essere caricato in un secondo momento Hub di Feedback come file allegato.  
1. Abilitare la telemetria completa tramite **l'app** Impostazioni -> **Privacy** Diagnostics & feedback e  ->  **in** **Dati di** diagnostica facoltativi verificare che l'interruttore sia impostato su **Sì**
1. Ottenere le correzioni più recenti per la scalabilità e la stabilità degli ologrammi aggiornando al sistema operativo [Windows Holographic più recente (20H2 o versione successiva).](hololens-release-notes.md#windows-holographic-version-20h2) Dopo l'aggiornamento, eseguire le operazioni seguenti:
    1. Rimuovere tutti gli ologrammi tramite **l'app** Settings -> **System**  ->  **Holograms** -> quindi selezionare **Remove all holograms** (Rimuovi tutti gli ologrammi) e iniziare con una mappa nuova.
    1. Crea una nuova mappa dello spazio con HoloLens, aggirando la stanza e osservando tutte le aree e le superfici nello spazio. Eseguire questa operazione per 2-3 minuti.
    1. Eseguire la calibrazione ipd. Passare a **Impostazioni**  >  **Utilità di**  >  **sistema**. In **Calibrazione** selezionare **Open Calibration (Apri calibrazione).**
    1. Testare nuovamente lo scenario e verificare se è ancora persistente.
1. Se l'aggiornamento non risolve il problema, determinare [Hub di Feedback problema.](hololens-feedback.md) Dopo aver inserito commenti e suggerimenti, è possibile usare il pulsante Condividi per creare un collegamento facile da condividere che può essere inviato quando si contatta il supporto tecnico. 

[Torna all'elenco](#list)