---
title: Usare la voce per gestire HoloLens
description: Informazioni su come usare Cortana per eseguire tutti i tipi di operazioni nei dispositivi con Realtà mista HoloLens, inclusi comandi vocali, dettatura e interazioni con gli ologrammi.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393870"
---
# <a name="use-your-voice-to-operate-hololens"></a>Usare la voce per gestire HoloLens

Puoi usare la tua voce per fare quasi tutto su HoloLens, ad esempio per scattare una foto veloce o aprire un'app. Molti comandi vocali sono incorporati in HoloLens, mentre altri sono disponibili tramite Cortana.

Questo articolo spiega come controllare HoloLens e il tuo mondo olografico con la tua voce e con Cortana.

> [!NOTE]
> I comandi vocali sono supportati solo in [alcune lingue](hololens2-language-support.md). La lingua dei comandi vocali si basa sulla lingua di visualizzazione di Windows e non sulla lingua della tastiera.  
>  
> È possibile verificare la lingua di visualizzazione di Windows selezionando **Impostazioni** > **Data/ora e lingua** > **Lingua**.

## <a name="built-in-voice-commands"></a>Comandi vocali predefiniti

Spostati più velocemente in HoloLens con questi comandi di base. Per usare tali comandi devi abilitare i comandi vocali alla prima esecuzione del dispositivo o in **Impostazioni** > **Privacy** > **Comandi vocali**. Puoi sempre verificare se il riconoscimento vocale è abilitato guardando lo stato nella parte superiore del menu Start. Per ottenere risultati ottimali di riconoscimento vocale, HoloLens 2 usa i servizi basati sul cloud Microsoft. Tuttavia, puoi usare le Impostazioni per disabilitare questa funzionalità. A questo scopo, disattiva **Riconoscimento vocale online** in Impostazioni. Dopo aver modificato questa opzione, HoloLens 2 elabora solo i dati vocali a livello locale in modo da riconoscere comandi e dettatura. Cortana non sarà disponibile.

### <a name="general-speech-commands"></a>Comandi vocali generali

Usa questi comandi in Windows Mixed Reality per spostarti più rapidamente. Alcuni comandi usano il cursore dello sguardo, che si apre pronunciando “Seleziona”.

> [!NOTE]
> I raggi della mano non sono supportati in HoloLens (prima generazione).

| Pronuncia la frase | Per |
| - | - |
| "Seleziona" | Pronuncia "Seleziona" per visualizzare il cursore dello sguardo. Gira quindi la testa per posizionare il cursore sull'oggetto che vuoi selezionare e ripeti "Seleziona". |
| "Vai a Start" |  Apri il menu Start |
| "Chiudi"  | Chiudi il menu Start |
| Pronuncia"Vai a Start" per visualizzare il menu azioni rapide, quindi pronuncia "ambiente iniziale".  | Chiudere un'app immersiva |
| "Nascondi raggio della mano"/"Mostra raggio della mano" | Nascondere e visualizzare il raggio della mano |
| "Cosa posso dire?"  | Vedere i comandi vocali disponibili |

Iniziando con la versione 19041.x di HoloLens 2, puoi usare i seguenti comandi:

| Pronuncia | Per eseguire questa operazione |
| - | - |
| "Riavvia dispositivo" | Apre una finestra di dialogo per confermare che desideri riavviare il dispositivo. Puoi dire "sì" per riavviarlo. |
| "Arresta dispositivo" | Apre una finestra di dialogo per confermare che desideri spegnere il dispositivo. Puoi dire "sì" per confermare. |
| "Alza/abbassa la luminosità" | Aumenta o riduce la luminosità del display del 10%. |
| "Alza/abbassa il volume" | Aumenta o riduce il volume del 10%. |
| "Qual è il mio indirizzo IP" | Apre una finestra di dialogo che mostra l'attuale indirizzo IP del tuo dispositivo sulla rete locale. |
| "Scatta una foto" | Scatta una foto di realtà mista di ciò che vedi. |
| "Acquisisci video" | Avvia la registrazione di un video di realtà mista. | 
| "Interrompi video" | Interrompe la registrazione corrente del video di realtà mista, se in corso. |

### <a name="hologram-commands"></a>Comandi olografici

Per usare questi comandi, fissa un oggetto 3D, un ologramma o una finestra dell'app.

| Pronuncia la frase | Per |
| - | - |
| "Più grande" | Ingrandire l'oggetto |
| "Più piccolo" | Ridurre le dimensioni dell'oggetto |
| "Guardami" | Rivolgere l'oggetto verso di te |
| "Sposta" | Spostare l'oggetto (seguendo il tuo sguardo fisso) |
| "Chiudi" | Chiuderlo |
| "Seguimi"/"Smettila di seguirmi" | Farti seguire dall'oggetto mentre ti sposti |

### <a name="see-it-say-it"></a>Vedere e pronunciare

Molti pulsanti e altri elementi in HoloLens rispondono anche alla tua voce, ad esempio **Seguimi** e **Chiudi** sulla barra dell'app o il pulsante **Indietro** in Microsoft Edge. Per scoprire se un pulsante è abilitato per la voce, posiziona il **cursore dello sguardo fisso, il**, **cursore tocco** o un **raggio della mano** su di esso per un momento. Se il pulsante è abilitato per la voce, viene visualizzato un suggerimento vocale.

### <a name="dictation-mode"></a>Modalità di dettatura

Sei stanco di digitare? Passa alla modalità dettatura ogni volta che la tastiera olografica è attiva. Per iniziare, seleziona il pulsante del microfono oppure pronuncia "Avvia dettatura". Per arrestare la dettatura, seleziona di nuovo il pulsante oppure pronuncia "Arresta dettatura". Per eliminare ciò che hai appena dettato, pronuncia "Eliminalo". 

> [!NOTE]
> Per usare la modalità di dettatura, è necessario disporre di una connessione Internet.

La dettatura HoloLens usa la punteggiatura esplicita, vale a dire il nome della punteggiatura che si vuole usare va pronunciato. Ad esempio, potresti dire "Ehi **virgola** che cosa stai facendo **punto interrogativo**".

Ecco le parole chiave di punteggiatura che puoi usare:

- Punto, virgola, punto interrogativo, punto esclamativo
- Nuova riga/nuovo paragrafo
- Punto e virgola, due punti
- Virgolette aperte, virgolette chiuse
- Hashtag, smiley/smiley, accigliato, ammiccante
- Dollaro, percentuale

A volte è utile compitare elementi come gli indirizzi di posta elettronica. Ad esempio, per dettare example@outlook.com, devi dire "E X A M P L E at Outlook dot com".

## <a name="do-more-with-cortana"></a>Eseguire altre operazioni con Cortana

Cortana può aiutarti a eseguire tutti i tipi di operazioni su HoloLens, ma a seconda della versione di Windows Holographic in uso, le funzionalità potrebbero essere diverse. Per altre informazioni sulle funzionalità aggiornate della versione più recente di Cortana, vedere Cortana nella prossima versione di [Windows 10,](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)incentrata sulla produttività con sicurezza e privacy avanzate. 

![Ehi Cortana](images/cortana-on-hololens.png)

Ecco alcune operazioni che puoi provare a ripetere (ricorda di dire "Ehi Cortana" prima).

**Ehi, Cortana**...

- Cosa posso dire?
- Avvia <*nome dell'app*>.
- Che ora è?
- Mostra gli ultimi risultati NBA.
- Raccontami una barzelletta.

Se stai usando la *versione 18362.x o una precedente*, puoi usare i seguenti comandi:

**Ehi, Cortana**...

- Aumenta il volume.
- Riduci la luminosità.
- Arresta il sistema.
- Riavvia il sistema.
- Sospendi.
- Disattiva audio.
- Sposta <*nome dell'app*> qui (fissa il punto in cui vuoi spostare l'app).
- Vai a Start.
- Scatta una foto.
- Avvia registrazione. (Avvia la registrazione di un video).
- Interrompi registrazione. (Interrompe la registrazione di un video).
- Quanta batteria mi rimane?

Alcune funzionalità di Cortana usate per Windows nel PC o nel telefono (ad esempio, promemoria e notifiche) non sono supportate in Microsoft HoloLens e l'esperienza di Cortana può essere diversa a seconda dell'area geografica in cui viene utilizzata.

### <a name="turn-cortana-off"></a>Disattivare Cortana

Cortana viene attivata la prima volta che utilizzi HoloLens quando abiliti i comandi vocali. Puoi disattivarla nelle impostazioni di Cortana. Nell'elenco **Ogni app** seleziona **Cortana** > **Impostazioni**. Quindi attiva Cortana per ricevere suggerimenti, idee, promemoria, avvisi e altro ancora.

Se Cortana non risponde a "Ehi Cortana", controlla che i comandi vocali siano abilitati nel menu Start e passa alle impostazioni di Cortana per verificare che sia attiva.
