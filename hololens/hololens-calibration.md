---
title: Migliorare la qualità e il comfort dell'oggetto visivo
description: Informazioni su come calibrare la distanza interpupillare (IPD) per migliorare la qualità degli oggetti visivi HoloLens dispositivi.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: calibrazione, comfort, oggetti visivi, qualità, ipd, HoloLens, Windows Mixed Reality, visori VR
ms.openlocfilehash: b3d917c71ac7441aeaf8dcbc25748ee07b9fbfa3
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428623"
---
# <a name="improve-visual-quality-and-comfort"></a>Migliorare la qualità e il comfort dell'oggetto visivo

HoloLens 2 e HoloLens (prima generazione) funzionano meglio quando sono calibrati in base agli occhi univoci.

Anche se entrambi i dispositivi devono calibrare per la migliore esperienza di visualizzazione degli ologrammi, usano tecniche e tecnologie di calibrazione diverse.  Passare alla [calibrazione HoloLens 2](#calibrating-your-hololens-2) o [HoloLens (prima generazione).](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>Calibrazione del HoloLens 2

HoloLens 2 usa la tecnologia di tracciamento oculare per migliorare l'esperienza di visualizzazione e interazione con l'ambiente virtuale. La calibrazione HoloLens 2 garantisce che possa tenere traccia accuratamente degli occhi (e degli occhi di chiunque usi il dispositivo). Aiuta anche con il comfort dell'utente, l'allineamento degli ologrammi e il tracciamento delle mani. Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando la visiera si sposta sulla testa.

HoloLens 2 richiede all'utente di calibrare il dispositivo nelle circostanze seguenti:

- L'utente usa il dispositivo per la prima volta
- L'utente ha precedentemente scelto esplicitamente di rifiutare esplicitamente il processo di calibrazione
- Il processo di calibrazione non è riuscito l'ultima volta che l'utente ha usato il dispositivo
- L'utente ha eliminato i profili di calibrazione
- Il dispositivo viene spento e rimette in uso e si applica una delle circostanze precedenti 


![Richiesta di calibrazione per la regolazione agli occhi.](./images/07-et-adjust-for-your-eyes.png)

Durante questo processo verrà visualizzato un set di destinazioni (gemme). Va bene se si lampeggia durante la calibrazione, ma si cerca di rimanere concentrati sulle gemme anziché su altri oggetti nella stanza.  Concentrarsi sulle gemme consente HoloLens informazioni sulla posizione dell'occhio per eseguire il rendering del mondo olografico.

![Richiesta di calibrazione che indica all'utente di mantenere la testa ferma e di seguire i punti con gli occhi.](./images/07-et-hold-head-still.png)

![Richiesta di calibrazione con esempio di gemma.](./images/08-et-gems.png)

![Regolazione della richiesta di calibrazione.](./images/09-et-adjusting.png)

Se la calibrazione ha avuto esito positivo, verrà visualizzata una schermata di esito positivo.  In caso contrario, leggere altre informazioni sulla [diagnosi degli errori di calibrazione.](hololens2-display.md#troubleshooting)

![La richiesta di calibrazione ha esito positivo.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Calibrazione quando si condivide un dispositivo o una sessione

Più utenti possono condividere un HoloLens 2 dispositivo, senza che ogni utente possa eseguire la configurazione del dispositivo. Quando un nuovo utente mette il dispositivo in testa per la prima volta, HoloLens 2 chiede automaticamente all'utente di calibrare gli oggetti visivi. Quando un utente con oggetti visivi calibrati in precedenza mette il dispositivo in testa, lo schermo si adatta perfettamente alla qualità e a un'esperienza di visualizzazione comoda.  

### <a name="manually-starting-the-calibration-process"></a>Avvio manuale del processo di calibrazione

1. Usare il movimento di avvio per aprire il [**menu Start**](hololens2-basic-usage.md#start-gesture).
1. Se l Impostazioni app non è aggiunta a **Start,** selezionare **Tutte le app.**
1. Selezionare **Impostazioni** e quindi selezionare Calibrazione oculare calibrazione del sistema  >    >    >  **Calibrazione oculare Eseguire calibrazione oculare**.

   ![L Impostazioni app, che mostra l'opzione Esegui calibrazione oculare.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Supporto della posizione dell'occhio automatico

In HoloLens 2, le posizioni oculare consentono un posizionamento accurato dell'ologramma, un'esperienza di visualizzazione comoda e una migliore qualità dello schermo. Le posizioni oculare vengono calcolate internamente come parte del calcolo del tracciamento oculare. Tuttavia, ciò richiede che ogni utente eserciti la calibrazione del tracciamento oculare, anche quando l'esperienza potrebbe non richiedere l'input dello sguardo fisso.

**Auto Eye Position (AEP)** abilita questi scenari con un modo senza interazione per calcolare le posizioni oculare per l'utente. Auto Eye Position inizia a lavorare automaticamente in background dal momento in cui l'utente inserisce il dispositivo. Se l'utente non ha una calibrazione del tracciamento oculare precedente, Posizione oculare automatica inizierà a fornire le posizioni oculare dell'utente al sistema di visualizzazione dopo un tempo di elaborazione di 20-30 secondi. I dati utente non vengono resi persistenti nel dispositivo e questo processo viene ripetuto se l'utente si disconnette e riattiva il dispositivo o se il dispositivo viene riavviato o riattivato dalla sospensione.

Esistono alcune modifiche al comportamento del sistema con la funzionalità Posizione oculare automatica quando un utente non bilanciato inserisce il dispositivo. In questo contesto, un utente non bilanciato fa riferimento a un utente che non ha mai passato il processo di calibrazione del tracciamento oculare nel dispositivo in precedenza.

| Applicazione attiva | Comportamento precedente | Comportamento da Windows Holographic, versione 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| App non abilitata per lo sguardo o Holographic Shell |Viene visualizzata la finestra di dialogo di richiesta di calibrazione del rilevamento oculare. | Non viene visualizzato alcun prompt. |
| App abilitata per lo sguardo | Viene visualizzata la finestra di dialogo di richiesta di calibrazione del rilevamento oculare. | La richiesta di calibrazione del tracciamento oculare viene visualizzata solo quando l'applicazione accede al flusso dello sguardo fisso. |

Se l'utente passa da un'applicazione non abilitata per lo sguardo a un'applicazione che accede ai dati dello sguardo, verrà visualizzata la richiesta di calibrazione. 

Tutti gli altri comportamenti del sistema saranno simili a quando l'utente corrente non ha una calibrazione del tracciamento oculare attiva. Ad esempio, il movimento One-handed Start non verrà abilitato. Non verrà apportata alcuna modifica all'esperienza out-of-box per la configurazione iniziale.

Per le esperienze che richiedono dati dello sguardo fisso o un posizionamento preciso dell'ologramma, è consigliabile che gli utenti non bilanciati esereranno la calibrazione del tracciamento oculare. È accessibile dal prompt di calibrazione del tracciamento oculare o avviando l'app Impostazioni dal menu Start e quindi selezionando Calibrazione > sistema > calibrazione **oculare > Calibrazione** oculare.

#### <a name="deferred-calibration-prompt"></a>Richiesta di calibrazione posticipata

Con La posizione automatica dell'occhio, la finestra di dialogo di richiesta di calibrazione del rilevamento oculare viene posticipata fino a quando un'applicazione non richiede i dati dello sguardo fisso. Ciò garantisce che non venga visualizzata alcuna richiesta all'utente quando l'applicazione attiva non richiede lo sguardo. Se l'applicazione richiede i dati dello sguardo fisso e l'utente corrente non è calibrato, all'utente viene visualizzata una richiesta di calibrazione. Questo comportamento può essere usato per visualizzare la richiesta di calibrazione del tracciamento oculare in un momento appropriato per l'esperienza. Questo metodo è consigliato per i motivi seguenti

1.  La finestra di dialogo Richiesta calibrazione tracciamento oculare fornisce all'utente informazioni dettagliate sul motivo per cui è necessario il tracciamento oculare.
2.  Presenta all'utente un modo per rifiutare di calibrare gli occhi.

Se l'utente sceglie di avviare la calibrazione del rilevamento oculare, lo stato attivo dovrebbe tornare all'applicazione originale al termine della calibrazione. 

### <a name="calibration-data-and-security"></a>Dati di calibrazione e sicurezza

Le informazioni di calibrazione vengono archiviate in locale nel dispositivo e non sono associate ad alcuna informazione sull'account. Non è stato registrato chi ha usato il dispositivo senza calibrazione. Ciò significa che i nuovi utenti riceveranno la richiesta di calibrare gli oggetti visivi quando usano il dispositivo per la prima volta e gli utenti che hanno scelto di rifiutare esplicitamente la calibrazione in precedenza o se la calibrazione ha avuto esito negativo.

Il dispositivo può archiviare in locale fino a 50 profili di calibrazione. Dopo aver raggiunto questo numero, il dispositivo elimina automaticamente il profilo inutilizzato meno recente.

Le informazioni di calibrazione possono sempre essere eliminate dal dispositivo in **Impostazioni**  >  **Privacy**  >  **Eye Tracker**.  

### <a name="disable-calibration"></a>Disabilitare la calibrazione

È anche possibile disabilitare la richiesta di calibrazione seguendo questa procedura:

1. Selezionare **Impostazioni**  >  **calibrazione**  >  **del sistema.**
1. Disattivare **Quando una nuova persona usa questo HoloLens, chiedere automaticamente di eseguire la calibrazione oculare.**

   > [!IMPORTANT]
   > Questa impostazione può influire negativamente sulla qualità e sul comfort del rendering degli ologrammi.  Quando si disattiva questa impostazione, le funzionalità che dipendono dal tracciamento oculare (ad esempio lo scorrimento del testo) non funzionano più nelle applicazioni immersive.

> [!NOTE]
> Il Impostazioni è stato rimosso a Windows Holographic, versione 20H2 con l'avvio del supporto della posizione [oculare automatica](hololens-release-notes.md#auto-eye-position-support). La richiesta di calibrazione verrà visualizzata automaticamente solo se un utente non bilanciato usa un'app abilitata per Eye Tracking.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 tecnologia di tracciamento oculare

Il dispositivo usa la tecnologia di tracciamento oculare per migliorare la qualità dello schermo e garantire che tutti gli ologrammi siano posizionati in modo accurato e comodo da visualizzare in 3D. Poiché usa gli occhi come punti di riferimento, il dispositivo può regolarsi per ogni utente e ottimizzare gli oggetti visivi quando il visore cambia leggermente durante l'uso.  Tutte le modifiche vengono apportate in tempo reale senza necessità di ottimizzazione manuale.
> [!NOTE]
> L'impostazione dell'IPD non è applicabile per Hololens 2, poiché le posizioni degli occhi vengono calcolate dal sistema.

HoloLens applicazioni usano il tracciamento oculare per tenere traccia della posizione in tempo reale. Questa è la funzionalità principale che gli sviluppatori possono usare per abilitare un nuovo livello di contesto, comprensione umana e interazioni all'interno dell'esperienza Holographic. Gli sviluppatori non devono eseguire qualsiasi operazione per usare questa funzionalità.

## <a name="calibrating-your-hololens-1st-gen"></a>Calibrazione del HoloLens (prima generazione)

HoloLens (prima generazione) regola la visualizzazione dell'ologramma in base alla distanza [interpupillaria](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Se l'IPD non è accurato, gli ologrammi possono apparire instabili o a una distanza non corretta. È possibile migliorare la qualità degli oggetti visivi calibrando il dispositivo in base alla distanza interpupillaria (IPD).

Quando si configura il dispositivo HoloLens (prima generazione), viene richiesto di calibrare gli oggetti visivi dopo Cortana si presenta. È consigliabile completare il passaggio di calibrazione durante questa fase di installazione. È tuttavia possibile ignorarlo attendendo Cortana e quindi pronunciando "Ignora".

Durante il processo di calibrazione, HoloLens chiede di allineare il dito con una serie di sei destinazioni per occhio. HoloLens usa questo processo per impostare correttamente l'IPD per gli occhi.

![Schermata di allineamento del dito IPD nel secondo passaggio.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Avviare manualmente il processo di calibrazione

Se è necessario aggiornare la calibrazione o se un nuovo utente deve regolarla, è possibile eseguire manualmente l'app Calibrazione in qualsiasi momento. L'app Calibrazione viene installata per impostazione predefinita. È possibile accedervi usando il menu **Start** o l'app Impostazioni app.

Per usare il menu **Start** per eseguire l'app Calibrazione, seguire questa procedura:

1. Usare il [movimento di fiore](hololens1-basic-usage.md) per aprire il menu **Start.**
1. Per visualizzare tutte le app, selezionare **+** .
1. Selezionare **Calibrazione.**

   ![Accesso all'app di calibrazione dalla shell.](./images/calibration-shell.png)

   ![App di calibrazione visualizzata come cubo live dopo l'avvio.](./images/calibration-livecube-200px.png)

Per usare l'app Impostazioni per eseguire l'app Calibrazione, seguire questa procedura:

1. Usare il [movimento di fiore](hololens1-basic-usage.md) per aprire il menu **Start.**
1. Se **Impostazioni** non è aggiunto a **Start,** selezionare questa opzione **+** per visualizzare tutte le app.
1. Selezionare **Impostazioni**.
1. Selezionare **Utilità di**  >  **sistema** Aprire  >  **Calibrazione.**

   ![Avvio dell'app di calibrazione dall'app delle impostazioni.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Visori VR immersive

Alcuni visori VR immersive offrono la possibilità di personalizzare l'impostazione ipd. Per modificare l'IPD per il visore VR, aprire l'app Impostazioni e selezionare **Visualizzazione** visore VR realtà mista  >  e quindi spostare il dispositivo di scorrimento. Le modifiche verranno visualizzati in tempo reale nel visore VR. Se si conosce l'IPD, ad esempio da una visita all'optometrista, è possibile immetterlo direttamente.

È anche possibile modificare questa impostazione nel PC selezionando Impostazioni  >  **visore**  >  **VR di realtà mista.**

Se il visore VR non supporta la personalizzazione ipd, questa impostazione verrà disabilitata.
