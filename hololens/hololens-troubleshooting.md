---
title: Risolvere problemi relativi a HoloLens
description: Soluzioni per problemi di HoloLens comuni.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: problemi, bug, risoluzione dei problemi, correzione, guida, supporto, HoloLens
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4897d02f4b789c77204d57c0a7750e3c3803d7bb
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829021"
---
# Risolvere problemi relativi a HoloLens

Questo articolo descrive come risolvere diversi problemi di HoloLens comuni.

## Il mio HoloLens non risponde o non si avvia

Se il HoloLens non si avvia:

- Se i LED accanto al pulsante di alimentazione non si accendono o un solo LED lampeggia brevemente, potrebbe essere necessario [caricare il HoloLens.](hololens-recovery.md#charging-the-device)
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

## HoloLens non risponde ai movimenti

Per assicurarsi che HoloLens possa visualizzare i movimenti.  Tieni la mano nel riquadro gestuale: quando HoloLens può vedere la tua mano, il cursore cambia da un punto a un anello.

Altre informazioni sull'uso dei movimenti in [HoloLens (1a generazione)](hololens1-basic-usage.md#use-hololens-with-your-hands) o [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se l'ambiente è troppo scuro, HoloLens potrebbe non vedere la mano, quindi verificare che ci sia abbastanza luce.

Se la visiera ha impronte digitali o macchie, usare il panno in microfibra fornito con il HoloLens per pulire delicatamente la visiera.

## HoloLens non risponde ai comandi vocali

Se Cortana non risponde ai comandi vocali, verificare che Cortana sia attivato. Nell'elenco tutte le app selezionare impostazioni del **Cortana**  >  **Menu**  >  **blocco appunti**del menu Cortana  >  **Settings** per apportare modifiche. Per ulteriori informazioni sulle frasi che è possibile pronunciare, vedere [Usare la voce con HoloLens](hololens-cortana.md).

## Non è possibile collocare gli ologrammi o vedere gli ologrammi precedentemente inseriti

Se HoloLens non riesce a mappare o caricare lo spazio, entra in modalità limitata e non sarà possibile inserire gli ologrammi o vedere gli ologrammi inseriti. Ecco alcune soluzioni possibili:

- Assicurarsi che nell'ambiente sia presente abbastanza luce in modo che HoloLens possa visualizzare e mappare lo spazio.
- Assicurarsi di essere connessi a una rete Wi-Fi. Se non si è connessi a una rete Wi-Fi, HoloLens non riesce a identificare e caricare uno spazio noto.
- Se è necessario creare un nuovo spazio, connettersi a Wi-Fi e quindi riavviare il HoloLens.
- Per verificare se lo spazio corretto è attivo o per caricare manualmente uno spazio, passa a spazi del sistema di **Impostazioni**  >  **System**  >  **Spaces**.
- Se viene caricato lo spazio corretto e si verificano ancora problemi, lo spazio potrebbe essere danneggiato. Per risolvere il problema, selezionare lo spazio e quindi scegliere **Rimuovi**. Dopo aver rimosso lo spazio, HoloLens inizia a mappare l'ambiente circostante e a creare un nuovo spazio.

## Il mio HoloLens non può dire in quale spazio mi trovo

Se il HoloLens non riesce a identificare e caricare lo spazio in cui ci si trova automaticamente, verificare i fattori seguenti:

- Verificare di essere connessi a una rete Wi-Fi
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
