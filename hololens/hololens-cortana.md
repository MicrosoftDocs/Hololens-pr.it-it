---
title: Usare la voce per operare HoloLens
description: Scopri come Cortana per eseguire qualsiasi tipo di operazione nei dispositivi HoloLens realtà mista, inclusi comandi vocali, dettatura e interazioni con ologrammi.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427255"
---
# <a name="use-your-voice-to-operate-hololens"></a>Usare la voce per operare HoloLens

È possibile usare la voce per eseguire quasi tutte le HoloLens, ad esempio scattare una foto rapida o aprire un'app. Molti comandi vocali sono incorporati in HoloLens, mentre altri sono disponibili tramite Cortana.

Questo articolo illustra come controllare la HoloLens e il mondo olografico con la voce e con Cortana.

> [!NOTE]
> Il riconoscimento vocale è supportato solo in [alcune lingue.](hololens2-language-support.md) La lingua di riconoscimento vocale è basata sulla lingua Windows di visualizzazione, non sulla lingua della tastiera.  
>  
> È possibile verificare la lingua Windows la lingua di visualizzazione selezionando **Impostazioni**  >  **ora e lingua.**  >  

## <a name="built-in-voice-commands"></a>Comandi vocali predefiniti

È possibile HoloLens più velocemente con questi comandi di base. Per usare questi elementi, è necessario abilitare Il riconoscimento vocale durante la prima esecuzione del dispositivo o **in** Impostazioni  >  **privacy.**  >   È sempre possibile controllare se il riconoscimento vocale è abilitato esaminando lo stato nella parte superiore della menu Start. Per ottenere risultati ottimali per il riconoscimento vocale, HoloLens 2 usa i servizi basati sul cloud Microsoft. Tuttavia, è possibile usare Impostazioni per disabilitare questa funzionalità. A tale scopo, in Impostazioni disattivare Riconoscimento **vocale online.** Dopo aver modificato questa impostazione, HoloLens 2 solo i dati vocali in locale per riconoscere i comandi e la dettatura e Cortana non saranno disponibili.

### <a name="general-speech-commands"></a>Comandi vocali generali

Usare questi comandi in tutta Windows Mixed Reality per spostarsi più velocemente. Alcuni comandi usano il cursore sguardo fisso, che viene visualizzato pronunciando "seleziona".

> [!NOTE]
> I raggi della mano non sono supportati HoloLens (prima generazione).

| Pronunciare questo | Per |
| - | - |
| "Seleziona" | Pronunciare "select" per visualizzare il cursore sguardo fisso. Quindi, ruotare la testa per posizionare il cursore sull'oggetto che si vuole selezionare e pronunciare di nuovo "select". |
| "Vai a Start" |  Aprire il menu Start |
| "Chiudi"  | Chiudere il menu Start |
| Pronunciare "Vai a Start" per visualizzare il menu delle azioni rapide e quindi pronunciare "Mixed reality home".  | Uscire da un'app immersiva |
| "Nascondi raggio mano" / "Mostra raggio mano" | Nascondere e visualizzare il raggio della mano |
| "Cosa posso dire?"  | Vedere i comandi vocali disponibili |

A partire dalla versione 19041.x di HoloLens 2, è anche possibile usare questi comandi:

| Pronunciare questo | Per |
| - | - |
| "Riavvia dispositivo" | Viene aperto un dialogo per confermare che si vuole riavviare il dispositivo. È possibile scegliere "Sì" per riavviare. |
| "Arresta il dispositivo" | Viene attivata una finestra di dialogo per confermare che si vuole spegnere il dispositivo. È possibile scegliere "Sì" per confermare. |
| "Luminosità su/giù" | Aumentare o diminuire la luminosità dello schermo del 10%. |
| "Volume up/down" | Aumentare o ridurre il volume del 10%. |
| "Qual è l'indirizzo IP" | Viene visualizzata una finestra di dialogo che mostra l'indirizzo IP corrente del dispositivo nella rete locale. |
| "Take a picture" | Acquisire una foto di realtà mista di ciò che si sta attualmente vedendo. |
| "Take a video" | Avviare la registrazione di un video di realtà mista. | 
| "Arresta registrazione" | Arresta la registrazione video di realtà mista corrente, se ne è in corso una. |

### <a name="hologram-commands"></a>Comandi dell'ologramma

Per usare questi comandi, osservare un oggetto 3D, un ologramma o una finestra dell'app.

| Pronunciare questo | Per |
| - | - |
| "Bigger" | Aumenta le dimensioni |
| "Smaller" | Renderlo più piccolo |
| "Guardami" | Trasformala in viso |
| "Sposta" | Spostarla (seguire lo sguardo) |
| "Chiudi" | Chiuderla |
| "Follow me" / "Stop following" | Fare in modo che segua l'utente mentre ci si sposta |

### <a name="see-it-say-it"></a>Guarda, parla

Molti pulsanti e altri elementi HoloLens risposta anche alla **voce,** ad  esempio Seguimi e chiudi sulla barra dell'app o il **pulsante** Indietro in Edge. Per scoprire se un pulsante è abilitato per la voce,  posizionare il **cursore** dello sguardo fisso, toccare il **cursore** o un raggio della mano per un momento. Se il pulsante è abilitato per la voce, verrà visualizzato un suggerimento vocale.

### <a name="dictation-mode"></a>Modalità dettatura

La digitazione è un'insod distorsi Passare alla modalità dettatura ogni volta che la tastiera olografica è attiva. Per iniziare, selezionare il pulsante del microfono o pronunciare "Avvia dettatura". Per interrompere la dettatura, selezionare di nuovo il pulsante o pronunciare "Stop dictating" (Interrompi dettatura). Per eliminare i dati appena dettati, pronunciare "Elimina". 

> [!NOTE]
> Per usare la modalità dettatura, è necessario disporre di una connessione Internet.

HoloLens dettatura usa la punteggiatura esplicita, ovvero il nome della punteggiatura che si vuole usare. Ad esempio, si potrebbe dire "Hey **comma** what are you up to **question mark**".

Ecco le parole chiave di punteggiatura che è possibile usare:

- Punto, virgola, punto interrogativo, punto esclamativo/punto esclamativo
- Nuova riga/nuovo paragrafo
- Punto e virgola, due punti
- Virgolette aperte, virgolette di chiusura
- Hashtag, smiley/smiley face, frowny, winky
- Dollaro, percentuale

In alcuni casi è utile formulare alcune informazioni, ad esempio gli indirizzi di posta elettronica. Ad esempio, per indicare example@outlook.com , si pronuncia "E X A M P L E at outlook dot com".

## <a name="do-more-with-cortana"></a>Eseguire altre Cortana

Cortana può essere utile eseguire tutti i tipi di operazioni nel HoloLens, ma a seconda della versione di Windows Holographic in uso, le funzionalità potrebbero essere diverse. Per altre informazioni sulle funzionalità aggiornate della versione più recente di Cortana, vedere Cortana nella prossima versione [di Windows 10,](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)incentrata sulla produttività con sicurezza e privacy avanzate. 

![Hey Cortana!](images/cortana-on-hololens.png)

Ecco alcune cose che è possibile provare a dire (ricordarsi di dire "Hey Cortana" prima).

**Hey, Cortana**...

- What can I say?
- Avviare <*nome dell'app*>.
- Che ora è?
- Mostrami i punteggi NBA più recenti.
- Mi dica una barzelletta.

Se si usa la *versione 18362.x* o precedente, è anche possibile usare questi comandi:

**Hey, Cortana**...

- Aumentare il volume.
- Ridurre la luminosità.
- Spegni.
- Riavvia.
- Andare a letto.
- Muto.
- Spostare <*nome dell'app*> qui (osservare il punto in cui si vuole spostare l'app).
- Fare clic su Start.
- Scattare una foto.
- Avviare la registrazione. Avvia la registrazione di un video.
- Arrestare la registrazione. Interrompe la registrazione di un video.
- Quanta batteria è rimasto?

Alcune funzionalità Cortana usate da Windows nel PC o nel telefono (ad esempio, promemoria e notifiche) non sono supportate in Microsoft HoloLens e l'esperienza Cortana può variare da un'area all'altra.

### <a name="turn-cortana-off"></a>Disattivare Cortana

Cortana è la prima volta che si usa il HoloLens quando si abilita la voce. È possibile disattivarla nelle Cortana del dispositivo. **Nell'elenco Tutte le** app selezionare **Cortana**  >  **Impostazioni**. Disattivare quindi Cortana suggerimenti, idee, promemoria, avvisi e altro ancora.

Se Cortana non risponde a "Hey Cortana", verificare che il riconoscimento vocale sia abilitato in Start e passare alle impostazioni di Cortana e verificare che sia attivata.
