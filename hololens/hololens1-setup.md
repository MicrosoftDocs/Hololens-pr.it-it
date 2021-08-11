---
title: Preparare una nuova HoloLens
description: Scopri come preparare, modificare e configurare per la prima volta HoloLens dispositivo di realtà mista di prima generazione.
ms.prod: hololens
ms.sitesec: library
author: JesseMcCulloch
ms.author: jemccull
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/12/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- Hololens (1st gen)
ms.openlocfilehash: 03a84f1035154660fe51ec5be07c3f32f4746564b95616ec45ef3978fb49b911
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662170"
---
# <a name="get-your-hololens-1st-gen-ready-to-use"></a>Prepararsi HoloLens (prima generazione) per l'uso

Seguire la procedura per configurare un HoloLens (prima generazione) per la prima volta.

## <a name="charge-your-hololens-1st-gen"></a>Addebito HoloLens (prima generazione)

Per caricare il HoloLens, collegare l'alimentatore alla porta di ricarica usando il cavo Micro USB incluso. Collegare quindi l'alimentatore a una presa di alimentazione. Quando il dispositivo è in carica, l'indicatore della batteria si accende in base a un modello d'onda.

![Immagine che mostra come collegare il cavo Micro USB al HoloLens](./images/hololens-charging.png)

Quando la HoloLens è on, l'indicatore della batteria mostra il livello della batteria in incrementi. Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%. Se il livello della batteria è molto basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente, quindi si esce.

> [!TIP]
> Per ottenere una stima del livello corrente della batteria, pronunciare "Hey Cortana, quanti batteria sono rimasti?"

L'alimentatore e il cavo USB forniti con il dispositivo sono il modo migliore per HoloLens (prima generazione).  L'alimentatore fornisce 18W di alimentazione (9 V 2A).

La velocità e la velocità di ricarica possono variare a seconda dell'ambiente in cui è in esecuzione il dispositivo.

## <a name="adjust-fit"></a>Adatta

> [!VIDEO https://www.microsoft.com/videoplayer/embed/be3cb527-f2f1-4f85-b4f7-a34fbaba980d]

| &nbsp; | &nbsp; |
|:--- |:--- |
|1. Ruotare il headband fino a circa 20-30 gradi.|![Passaggio 1: ruotare la fascia](./images/FitGuideStep1.png)|
|2. Eseguire il push indietro del headband. Non estrarlo o manipolare la banda dietro la cerniata, perché nel tempo ciò può interrompere la banda.|![Passaggio 2, eseguire il push indietro del headband](./images/FitGuideStep2.png)|
|3. Ruotare la ruota di regolazione per estendere la banda della testa fino all'uscita. |![Passaggio 3: usare la ruota di regolazione per estendere la fascia](./images/FitGuideStep3.png)|
|4. Tenere il dispositivo in mano e posizionarlo sulla testa. Assicurarsi che la banda della testa sieda nella parte superiore della fronte e quindi stringere la ruota di regolazione.|![Passaggio 4, inserire il dispositivo e regolare la fascia](./images/FitGuideStep4.png)|
|5. Far scorrere di nuovo il visore e quindi controllare l'adattamento del dispositivo. La fascia deve essere posta nella parte superiore della fronte, appena sotto la linea dei capelloni, con gli altoparlanti sopra le sedie. Le lenti devono essere centrate sugli occhi.|![Passaggio 5, far scorrere di nuovo il visore e controllare l'adattamento](./images/FitGuideSetep5.png)|

## <a name="turn-on-your-hololens"></a>Attivare l'HoloLens

Usare il pulsante di alimentazione per HoloLens attivare e disattivare la modalità standby.

![Immagine che mostra il pulsante HoloLens'alimentazione](./images/hololens-power.png)

Se il dispositivo non risponde o non si avvia, vedere [Riavviare, reimpostare o](hololens-restart-recover.md)ripristinare HoloLens .

Quando il HoloLens è spento o in standby, attivarlo premendo il pulsante di alimentazione per un secondo. Se non viene attivata, collegarla e addebitarla per almeno 30 minuti.

> [!TIP]
> Per riavviare HoloLens, pronunciare "Hey Cortana, riavviare il dispositivo".

### <a name="put-hololens-in-standby"></a>Mettere HoloLens in standby

Per mettere il HoloLens in standby mentre è acceso, premere una volta il pulsante di alimentazione. Gli indicatori della batteria lampeggiano. Per riattivarlo dalla modalità standby, premere di nuovo il pulsante di alimentazione.

HoloLens passa automaticamente in standby dopo 3 minuti di inattività. Quando è in standby, si arresta automaticamente dopo 4 ore o dopo che il livello della batteria scende del 10%.

### <a name="shut-down-hololens"></a>Arrestare HoloLens

Per arrestare (disattivare) il HoloLens, tenere premuto il pulsante di alimentazione per quattro secondi. Gli indicatori della batteria si spegnino uno alla volta e il dispositivo si arresta.

HoloLens si arresta automaticamente quando il livello della batteria scende all'1%, anche se è alimentato. Dopo aver alzato la batteria al 3%, sarà possibile riattivare HoloLens'alimentazione.

## <a name="adjust-volume-and-brightness"></a>Regolare volume e luminosità

I pulsanti di luminosità e volume sono sopra il volume degli elementi del dispositivo a destra e la &mdash; luminosità a sinistra.

![Immagine che mostra i HoloLens personalizzati](./images/hololens-buttons.jpg)

## <a name="hololens-indicator-lights"></a>HoloLens indicatori di prestazioni

![Immagine che mostra le luci HoloLens indicatori di prestazioni](./images/hololens-lights.png)

Non si è certi del significato delle luci HoloLens dispositivo? Ecco alcune informazioni.

|Quando le luci fanno questo |Significa |
|---|---|
|Scorrere dal centro verso l'esterno. |HoloLens è in corso l'avvio. |
|Rimanere accesi (tutti o alcuni). |HoloLens è disponibile e pronto per l'uso. La durata della batteria viene visualizzata in incrementi del 20%. |
|Scorrere, quindi accendere e quindi scorrere. |HoloLens è on e addebito. La durata della batteria viene visualizzata in incrementi del 20%. |
|Disattivare uno alla volta. |HoloLens è in fase di arresto. |
|Disattivare tutto contemporaneamente. |HoloLens è in standby. |
|Si accende tutto, quindi si lampeggia brevemente, quindi tutti si disattivano. |La batteria è estremamente bassa. HoloLens deve essere addebitato. |
|Scorrere tutti, quindi lampeggiare e quindi scorrere tutti. |La batteria è estremamente bassa. HoloLens addebito. |

## <a name="safety-and-comfort"></a>Sicurezza e comfort

### <a name="use-in-safe-surroundings"></a>Uso in ambienti sicuri

Usare le HoloLens in uno spazio sicuro privo di ostruzione e rischi di inciampo. Non usarlo quando è necessario un campo di vista chiaro e la massima attenzione, ad esempio quando si usa un veicolo o si effettuano altre attività potenzialmente pericolose.

### <a name="stay-comfortable"></a>Rimanere a proprio agio

Mantenere le prime sessioni con HoloLens breve e assicurarsi di fare delle pause. In caso di disagi, fermarsi e attendere fino a quando non si è migliori. Può trattarsi di temporanea malattia, mal di movimento, vertigini, disorientamento, difficoltà, affaticamento, affaticamento oculare o occhi secchi.

> [!div class="nextstepaction"]
> [Avviare e configurare il HoloLens (prima generazione)](hololens1-start.md)
