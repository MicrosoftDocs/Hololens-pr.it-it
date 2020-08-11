---
title: Migliorare la qualità visiva e il comfort
description: La calibrazione della distanza interpupillare può migliorare la qualità degli indicatori visivi. Entrambi i visori VR immersive HoloLens e Windows Mixed Reality consentono di personalizzare la distanza interpupillare in diversi modi.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: calibrazione, comfort, indicatori visivi, qualità, distanza interpupillare
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 627631ee7070af6cb6c60e91890f05472ce0f6be
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919157"
---
# Migliorare la qualità visiva e il comfort

HoloLens 2 e HoloLens (prima generazione) funzionano meglio quando sono calibrati esclusivamente per i tuoi occhi.

Entrambi i dispositivi debbano essere calibrati per garantire la migliore esperienza di visualizzazione degli ologrammi, ma le tecnologie e le tecniche di calibrazione utilizzate sono diverse.  Passa a [Calibrazione di HoloLens 2](#calibrating-your-hololens-2) o [HoloLens 2 di HoloLens (prima generazione)](#calibrating-your-hololens-1st-gen).

## Calibrazione di HoloLens 2

HoloLens 2 usa la tecnologia di tracciamento degli occhi per migliorare l'esperienza di visualizzazione e interazione con l'ambiente virtuale. La calibrazione di HoloLens 2 garantisce un tracciamento accurato degli occhi tuoi e di chiunque altro usi il dispositivo. Contribuisce inoltre al comfort dell’utente, all’allineamento dell’ologramma e al tracciamento della mano. Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando la visiera si sposta sulla testa.

HoloLens 2 richiede a un utente di calibrare il dispositivo nei seguenti casi:

- L'utente usa il dispositivo per la prima volta
- L'utente ha precedentemente scelto di non eseguire il processo di calibrazione
- Il processo di calibrazione non è riuscito l'ultima volta che l'utente ha usato il dispositivo
- L'utente ha eliminato i profili di calibrazione
- Il dispositivo viene tolto e ripristinato e si applicano le circostanze precedenti 


![Richiesta di calibrazione](./images/07-et-adjust-for-your-eyes.png)

Durante questo processo, dovrai guardare una serie di obiettivi (gemme). Durante la calibrazione, puoi battere le palpebre, ma cerca di rimanere concentrato sulle gemme anziché su altri oggetti presenti nella stanza.  HoloLens usa questo processo per ottenere informazioni sulla posizione degli occhi, per garantire un rendering ottimale del mondo olografico.

![Richiesta di calibrazione](./images/07-et-hold-head-still.png)

![Richiesta di calibrazione](./images/08-et-gems.png)

![Richiesta di calibrazione](./images/09-et-adjusting.png)

Se la calibrazione è stata eseguita correttamente, verrà visualizzata una schermata di successo.  In caso contrario, leggi altre informazioni sulla diagnosi degli errori di calibrazione [qui](#troubleshooting-hololens-2-calibration).

![Richiesta di calibrazione](./images/10-et-success.png)

### Calibrazione durante la condivisione di un dispositivo o di una sessione

Un dispositivo HoloLens 2 può essere condiviso da più utenti, senza che ciascuno di essi ne esegua la configurazione. Quando un nuovo utente indossa il dispositivo per la prima volta, HoloLens 2 gli chiede automaticamente di calibrare gli indicatori visivi. Quando un utente che ha calibrato in precedenza gli indicatori visivi indossa il dispositivo, lo schermo viene regolato per una qualità ottimale e un'esperienza di visualizzazione confortevole.  

### Avvio manuale del processo di calibrazione

1. Usa il gesto Start per aprire il [menu**Start**](hololens2-basic-usage.md#start-gesture).
1. Se l'app Impostazioni non è aggiunta a **Start**, seleziona **Tutte le app**.
1. Seleziona **Impostazioni**, quindi **Sistema** > **Calibrazione** > **Calibrazione occhi** > **Esegui calibrazione occhi**.

   ![L'app Impostazioni con l'opzione per eseguire la calibrazione degli occhi](./images/C-Settings.Calibration.png)

### Risoluzione dei problemi relativi alla calibrazione di HoloLens 2

La calibrazione dovrebbe essere seguita correttamente per la maggior parte delle persone, ma in alcuni casi potrebbe avere esito negativo.
  
Alcuni possibili motivi per un errore di calibrazione includono:

- L'utente si distrae e non segue gli obiettivi di calibrazione
- La visiera del dispositivo è sporca o graffiata o non è posizionata correttamente
- Le lenti sono sporche o graffiate
- Alcuni tipi di lenti a contatto e occhiali (lenti a contatto colorate, alcune lenti a contatto toriche, occhiali anti infrarosso, alcuni occhiali con alta gradazione, occhiali da sole o simili)
- Trucco più pronunciato e alcune estensioni delle ciglia
- Capelli o montature spesse di occhiali, qualora impediscano al dispositivo dal vedere i tuoi occhi
- Fisiologia oculare, condizioni oculari o chirurgia oculare specifiche, come occhi stretti, ciglia lunghe, ambliopia, nistagmo, alcuni casi di chirurgia dell'occhio laser o altri interventi di chirurgia oculare

Se la calibrazione non riesce, provare quanto segue:

- Pulire la visiera del dispositivo
- Pulire gli occhiali
- Spingere la visiera del dispositivo il più vicino possibile agli occhi
- Rimuovere eventuali oggetti che potrebbero trovarsi in corrispondenza della visiera (ad esempio, i capelli)
- Accendere una luce nella stanza o allontanarsi dalla luce diretta del sole

Se sono state seguite tutte le linee guida e la calibrazione ancora non riesce, puoi disabilitare la richiesta di calibrazione nelle Impostazioni. Puoi comunicarcelo anche inviando un tuo feedback tramite l’[Hub di Feedback](hololens-feedback.md).

Consulta anche le informazioni correlate sulla [risoluzione dei problemi relativi a colore dell'immagine o luminosità.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Tieni presente che l'impostazione della distanza interpupillare non è applicabile per Hololens 2, perché le posizioni degli occhi sono calcolate dal sistema. 

### Dati di calibrazione e sicurezza

Le informazioni sulla calibrazione vengono memorizzate localmente nel dispositivo e non sono associate alle informazioni sull'account. Non viene mantenuto alcun record qualora un utente utilizzi il dispositivo senza calibrazione. Ai nuovi utenti verrà pertanto richiesto di calibrare gli indicatori visivi quando usano il dispositivo per la prima volta. Lo stesso avverrà per gli utenti che hanno scelto di non eseguire la calibrazione in precedenza o qualora la calibrazione abbia avuto esito negativo.

Il dispositivo può archiviare localmente fino a 50 profili di calibrazione. Una volta raggiunto questo numero, il dispositivo eliminerà automaticamente il profilo inutilizzato meno recente.

Le informazioni sulla calibrazione possono essere sempre eliminate dal dispositivo in **Impostazioni** > **Privacy** > **Tracciatore oculare**.  

### Disabilitare la calibrazione

Puoi anche possibile disabilitare la richiesta di calibrazione tramite la procedura seguente:

1. Selezione **Impostazioni** > **Sistema** > **Calibrazione**.
1. Disattiva **Quando una nuova persona usa questo dispositivo HoloLens, chiedi automaticamente di eseguire la calibrazione degli occhi**.

> [!IMPORTANT]
> Questa impostazione può avere un impatto negativo sulla qualità del rendering dell'ologramma e sul comfort.  Quando disattivi questa impostazione, le funzionalità che dipendono dal tracciamento oculare (ad esempio lo scorrimento del testo) non funzionano più nelle applicazioni immersive.

### Tecnologia di tracciamento oculare di HoloLens 2

Il dispositivo usa la tecnologia per il tracciamento degli occhi per migliorare la qualità di visualizzazione e per garantire che tutti gli ologrammi siano posizionati in modo accurato e comodo per la visualizzazione in 3D. Poiché usa gli occhi come punti di riferimento, il dispositivo è in grado di eseguire in automatico la regolazione per ogni utente e l'ottimizzazione degli indicatori visivi quando il visore si sposta leggermente durante l'uso.  Tutte le regolazioni avvengono al volo senza bisogno di eseguire l'ottimizzazione manuale.
> [!NOTE]
> L'impostazione della distanza interpupillare non è applicabile per Hololens 2, in quanto le posizioni degli occhi sono calcolate dal sistema.

Le applicazioni HoloLens usano il tracciamento oculare per individuare in tempo reale la posizione verso cui guarda l'utente. Si tratta della principale funzionalità che gli sviluppatori possono sfruttare per consentire un livello completamente nuovo di contesto, comprensione umana e interazioni all'interno dell'esperienza olografica. Gli sviluppatori non devono eseguire alcuna operazione per sfruttare questa funzionalità.

## Calibrazione del dispositivo HoloLens (prima generazione)

HoloLens (prima generazione) regola la visualizzazione degli ologrammi in base alla [distanza di interpupillare](https://en.wikipedia.org/wiki/Interpupillary_distance). Se la distanza interpupillare non è corretta, gli ologrammi potrebbero apparire instabili o a una distanza errata. Per migliorare la qualità degli indicatori visivi, puoi calibrare il dispositivo in base alla distanza interpupillare.

Quando configuri il dispositivo Hololens (prima generazione), ti viene richiesto di calibrare gli indicatori visivi dopo l'introduzione di Cortana. È consigliabile completare il passaggio di calibrazione durante questa fase di configurazione. Puoi comunque saltare questa procedura ogni volta che Cortana te la propone, pronunciando "Salta".

Durante il processo di calibrazione, HoloLens chiede di allineare il dito con una serie di sei obiettivi per occhio. HoloLens usa questo processo per impostare correttamente la distanza interpupillare dei tuoi occhi.

![Schermata di allineamento della distanza oculare tramite dita, seconda fase](./images/ipd-finger-alignment-300px.jpg)

### Avvio manuale del processo di calibrazione

Se devi aggiornare la calibrazione o se un nuovo utente deve effettuarne la regolazione, è possibile eseguire manualmente l'app di calibrazione in qualsiasi momento. L'app calibrazione viene installata per impostazione predefinita. Puoi accedervi usando il menu **Start** o l'app Impostazioni.

Per usare il menu **Start** per eseguire l'app di calibrazione, effettua quanto segue:

1. Usa la [mano a fiore](hololens1-basic-usage.md) per aprire il menu **Start**.
1. Per visualizzare tutte le app, seleziona **+**.
1. Seleziona **Calibrazione**.

![Accesso all'app di calibrazione dalla shell](./images/calibration-shell.png)

![App di calibrazione visualizzata come cubo dinamico dopo l'avvio](./images/calibration-livecube-200px.png)

Per usare l'app Impostazioni per eseguire l'app di calibrazione, effettua quanto segue:

1. Usa la [mano a fiore](hololens1-basic-usage.md) per aprire il menu **Start**.
1. Se **Impostazioni** non è aggiunto a **Start**, seleziona **+** per visualizzare tutte le app.
1. Seleziona **Impostazioni**.
1. Seleziona **Sistema** > **Utilità** > **Apri Calibrazione**.

![Avvio dell'app di calibrazione dall'app Impostazioni](./images/calibration-settings-500px.jpg)

## Visore VR immersive

Alcuni visori VR immersive offrono la possibilità di personalizzare l'impostazione della distanza interpupillare. Per cambiare la distanza interpupillare per il visore VR, apri l'app Impostazioni e seleziona **Realtà mista** > **Display headset**, quindi sposta il dispositivo di scorrimento. Le modifiche verranno visualizzate in tempo reale nel visore VR. Se conosci la tua distanza interpupillare, ad esempio in seguito a una visita dall'optometrista, puoi anche immetterla direttamente.

Puoi inoltre regolare questa impostazione nel PC selezionando **Impostazioni** > **Realtà mista** > **Display headset**.

Se il visore VR non supporta la personalizzazione della distanza interpupillare, questa impostazione verrà disabilitata.
