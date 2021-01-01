---
title: Domande frequenti sui dispositivi e gli ologrammi di HoloLens
description: Si hanno domande riguardanti HoloLens o l'interazione con gli ologrammi?  Il presente articolo fornisce risposte e ulteriori risorse.
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
ms.openlocfilehash: 72b976560664c89b7ae3cd9270c57ead438679cd
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253123"
---
# Domande frequenti sui dispositivi e gli ologrammi di HoloLens

Questo articolo risponde ad alcune domande relative all'uso di HoloLens, tra cui come posizionare gli ologrammi, lavorare con gli spazi e altro ancora.

Ogni volta che si verificano problemi, assicurarsi che HoloLens sia [carico](https://support.microsoft.com/help/12627/hololens-charge-your-hololens). Provare a [riavviarlo](hololens-restart-recover.md) per verificare se ciò risolve il problema. Usare l'app Feedback per inviare informazioni riguardanti il problema. L'app Feedback è disponibile nel menu [**Start**](holographic-home.md).

Per suggerimenti su come indossare l'HoloLens, vedere [Domande frequenti su come indossare comodamente HoloLens (1ª generazione)](hololens1-fit-comfort-faq.md).

Il presente articolo affronta le domande e i problemi seguenti:
<a id="list"></a>

- [Gli ologrammi non sono visualizzati correttamente o si muovono](#my-holograms-dont-look-right-or-are-moving-around)
- [Viene visualizzato un messaggio che riporta la dicitura "Ricerca dello spazio in corso"](#i-see-a-message-that-says-finding-your-space)
- [Non vengono visualizzati gli ologrammi previsti nello spazio](#im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space)
- [Non è possibile posizionare gli ologrammi dove si preferisce](#i-cant-place-holograms-where-i-want-to)
- [Gli ologrammi spariscono o sono racchiusi tra altri ologrammi od oggetti](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Vengono visualizzati gli ologrammi che si trovano sull'altro lato di un muro](#i-can-see-holograms-that-are-on-the-other-side-of-a-wall)
- [Quando si inserisce un ologramma su un muro, l'ologramma sembra fluttuare](#when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float)
- [Le app sembrano troppo ravvicinate quando si prova a spostarle](#apps-appear-too-close-to-me-when-im-trying-to-move-them)
- [Viene visualizzato un errore che avverte che lo spazio su disco è insufficiente](#im-getting-a-low-disk-space-error)
- [HoloLens non risponde ai movimenti](#hololens-doesnt-respond-to-my-gestures)
- [HoloLens non risponde alla voce](#hololens-doesnt-respond-to-my-voice)
- [Si verificano problemi nell'associazione o nell'utilizzo di un dispositivo Bluetooth](#im-having-problems-pairing-or-using-a-bluetooth-device)
- [Le impostazioni di HoloLens indicano che i dispositivi sono disponibili ma questi non funzionano](#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)
- [Si verificano problemi durante l'utilizzo del clicker di HoloLens](#im-having-problems-using-the-hololens-clicker)
- [Non è possibile connettersi al Wi-Fi](#i-cant-connect-to-wi-fi)
- [HoloLens non funziona correttamente, non risponde o non si avvia](#my-hololens-isnt-running-well-is-unresponsive-or-wont-start)
- [Non è possibile accedere a un dispositivo HoloLens poiché è stato configurato in precedenza per un'altra persona](#i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else)
- [Domande riguardanti la gestione dei dispositivi HoloLens](#questions-about-managing-hololens-devices)
- [Domande riguardanti la sicurezza dei dispositivi HoloLens](#questions-about-securing-hololens-devices)
- [Come fare per eliminare tutti gli spazi?](#how-do-i-delete-all-spaces)
- [Non è possibile trovare o utilizzare la tastiera per digitare nell'emulatore HoloLens 2](#i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator)

## Gli ologrammi non sono visualizzati correttamente o si muovono

Se gli ologrammi non sono visualizzati correttamente (ad esempio se risultano tremolanti o instabili o se sono presenti delle macchie nere su di essi), provare una delle seguenti soluzioni:

- [Pulire il visore del dispositivo](hololens1-hardware.md#care-and-cleaning) e assicurarsi che nulla ostruisca i sensori.
- Assicurarsi di essere in una stanza ben illuminata, ma senza luce diretta del sole.
- Provare a passeggiare e osservare l'ambiente circostante in modo che HoloLens possa effettuarne la scansione in modo più completo.
- Se sono stati posizionati molti ologrammi, provare a rimuoverne qualcuno.

Se i problemi persistono, provare a eseguire l'app Calibrazione. Questa app calibra HoloLens e consente una corretta visualizzazione degli ologrammi. Per farlo, accedere a **Impostazioni** > **Sistema** > **Utilità**. In **Calibrazione**, selezionare **Apri Calibrazione**.

[Torna all'elenco](#list)

## Viene visualizzato un messaggio che riporta la dicitura "Ricerca dello spazio in corso"

Quando HoloLens sta scoprendo o caricando uno spazio, potrebbe essere visualizzato un breve messaggio con la dicitura "Ricerca dello spazio in corso". Se il messaggio viene visualizzato per più di qualche secondo, verrà visualizzato un ulteriore messaggio nel menu Start con la dicitura "Ricerca ulteriore dello spazio in corso".

Questi messaggi indicano che HoloLens non riesce a eseguire il mapping dello spazio. In questo caso, è possibile aprire le app ma non è possibile posizionare gli ologrammi nell'ambiente.

Se questi messaggi vengono visualizzati spesso, provare una o più delle seguenti soluzioni:

- Assicurarsi di essere in una stanza ben illuminata, ma senza luce diretta del sole.
- Assicurarsi che il visore del dispositivo sia pulito. [Informazioni su come pulire il visore](hololens1-hardware.md#care-and-cleaning).
- Assicurarsi di avere un forte segnale Wi-Fi. Se si entra in un nuovo ambiente in cui il segnale Wi-Fi è debole o nullo, HoloLens non sarà in grado di trovare lo spazio. Controllare la connessione Wi-Fi accedendo a **Impostazioni** > **Rete &amp; Internet** > **Wi-Fi**.
- Provare a spostarsi più lentamente.

[Torna all'elenco](#list)

## Non vengono visualizzati gli ologrammi previsti nello spazio

Se gli ologrammi posizionati non sono visualizzati o se ne sono visualizzati alcuni non previsti, provare una o più delle seguenti soluzioni:

- Accendere qualche luce. HoloLens funziona meglio in spazi ben illuminati.
- Rimuovere gli ologrammi non necessari accedendo a **Impostazioni** > **Sistema** > **Ologrammi** > **Rimuovi ologrammi nelle vicinanze**. Se necessario, selezionare **Rimuovi tutti gli ologrammi**.

  > [!NOTE]
  > Se il layout o l'illuminazione nello spazio cambiano in modo significativo, il dispositivo potrebbe avere problemi a identificare lo spazio e a visualizzare gli ologrammi.

[Torna all'elenco](#list)

## Non è possibile posizionare gli ologrammi dove si preferisce

Ecco alcune operazioni da provare in caso di problemi nel posizionamento degli ologrammi:

- Posizionarsi a una distanza compresa tra uno e tre metri dal luogo in cui si desidera posizionare l'ologramma.
- Non posizionare gli ologrammi su superfici nere o riflettenti.
- Assicurarsi di essere in una stanza ben illuminata, ma senza luce diretta del sole.
- Passeggiare per la stanza in modo che HoloLens possa effettuare nuovamente la scansione dell'ambiente circostante. Per visualizzare cosa è stato già sottoposto a scansione, simulare il tocco per rivelare la grafica mesh della mappatura.

[Torna all'elenco](#list)

## Gli ologrammi spariscono o sono racchiusi tra altri ologrammi od oggetti

Se ci si avvicina troppo a un ologramma, questo sparirà temporaneamente&mdash;; per ripristinarlo, allontanarsi. Inoltre, se sono stati posizionati vicini diversi ologrammi, alcuni potrebbero sparire. Provare a rimuoverne alcuni.

Gli ologrammi possono anche essere bloccati o racchiusi da altri ologrammi o da oggetti come i muri. In questo caso, provare una delle seguenti soluzioni:

- Se l'ologramma è racchiuso in un altro ologramma, spostarlo in un'altra posizione. Per farlo, selezionare **Regola**, quindi toccare e tenere premuto per posizionarlo.
- Se l'ologramma è racchiuso in un muro, selezionare **Regola**, quindi camminare verso il muro finché l'ologramma non viene visualizzato. Toccare e tenere premuto, quindi tirare l'ologramma in avanti e spostarlo dal muro.
- Se non è possibile spostare l'ologramma tramite i movimenti, utilizzare la voce per rimuoverlo. Fissare l'ologramma, quindi pronunciare "Rimuovi". Riaprire l'ologramma e posizionarlo in una nuova posizione.

[Torna all'elenco](#list)

## Vengono visualizzati gli ologrammi che si trovano sull'altro lato di un muro

Se ci si trova troppo vicini a un muro, oppure se HoloLens non ha ancora effettuato la scansione del muro, è possibile vedere gli ologrammi che si trovano nella stanza accanto. Per effettuare la scansione del muro, posizionarsi a una distanza compresa tra uno e tre metri dal muro e fissarlo.

Un oggetto nero o riflettente (ad esempio, un divano nero o un frigorifero in acciaio inossidabile) nei pressi del muro può causare problemi quando HoloLens tenta di effettuare la scansione del muro. Se è presente un oggetto di questo tipo, effettuare la scansione del lato opposto del muro.

[Torna all'elenco](#list)

## Quando si inserisce un ologramma su un muro, l'ologramma sembra fluttuare

Un ologramma posizionato su un muro di solito appare distante circa un centimetro. Se risulta più lontano, provare una o più delle seguenti soluzioni:

- Quando si posiziona un ologramma su un muro, posizionarsi di fronte a una distanza compresa tra uno e tre metri.
- Simulare il tocco sul muro per rivelare la grafica mesh della mappatura. Assicurarsi che la mesh sia allineata al muro. In caso contrario, rimuovere l'ologramma, effettuare nuovamente la scansione del muro e riprovare.
- Se il problema persiste, eseguire l'app Calibrazione, disponibile in **Impostazioni** > **Sistema** > **Utilità**.

[Torna all'elenco](#list)

## Le app sembrano troppo ravvicinate quando si prova a spostarle

Provare a passeggiare e guardare l'area in cui si sta posizionando l'app in modo che HoloLens effettui una scansione dell'area da diverse angolazioni. Anche [pulire la visiera del dispositivo](hololens1-hardware.md#care-and-cleaning) può essere di aiuto.

[Torna all'elenco](#list)

## Viene visualizzato un errore che avverte che lo spazio su disco è insufficiente

Liberare lo spazio di archiviazione eseguendo una o più delle seguenti operazioni:

- Rimuovere alcuni ologrammi posizionati oppure rimuovere i dati salvati nelle app. [Come fare per trovare i dati?](holographic-data.md)
- Eliminare alcune foto e alcuni video nell'app Foto.
- Disinstallare alcune app da HoloLens. Nell'elenco **Tutte le app**, toccare e tenere premuta l'app che si desidera disinstallare, quindi selezionare **Disinstalla** (la disinstallazione dell'app elimina anche i relativi dati archiviati sul dispositivo).

[Torna all'elenco](#list)

## HoloLens non risponde ai movimenti

Per fare in modo che HoloLens veda i movimenti, tenere la mano nel frame dei movimenti. Il frame dei movimenti si estende a qualsiasi lato a un paio di metri di distanza. Inoltre HoloLens riesce a vedere meglio la mano quando è posizionata a circa 45 cm di distanza davanti al corpo (non è necessario essere precisi). Quando HoloLens riesce a vedere la mano, il cursore passa da un punto a un anello. Ulteriori informazioni sull'[utilizzo dei movimenti in HoloLens 2](hololens2-basic-usage.md) o sull'[utilizzo dei movimenti in HoloLens (1ª generazione)](hololens1-basic-usage.md).

[Torna all'elenco](#list)

## HoloLens non risponde alla voce

HoloLens (1ª generazione) e HoloLens 2 dispongono di un riconoscimento vocale predefinito e, inoltre, supportano Cortana (riconoscimento vocale online).

### I comandi vocali predefiniti non funzionano

In HoloLens (1ª generazione) non è possibile configurare il riconoscimento vocale predefinito, che è sempre attivo. In HoloLens 2 è possibile scegliere se attivare il riconoscimento vocale e Cortana durante la configurazione del dispositivo.

Se HoloLens 2 non risponde alla voce, assicurarsi che il riconoscimento vocale sia attivo. Accedere a **Start** > **Impostazioni** > **Privacy** > **Parlato**, quindi attivare **Riconoscimento vocale**.

### Cortana o la dettatura non funzionano

Se Cortana o la dettatura non rispondono alla voce, assicurarsi che il riconoscimento vocale online sia attivo. Accedere a **Start** > **Impostazioni** > **Privacy** > **Parlato**, quindi controllare le impostazioni del **riconoscimento vocale online**. 

Se Cortana continua a non rispondere, eseguire una delle seguenti operazioni per verificare che sia attiva:

- In **Tutte le app**, selezionare **Cortana** > selezionare **Menu** > **Appunti** > **Impostazioni** per apportare modifiche.
- In HoloLens 2, selezionare il pulsante **Impostazioni Parlato** oppure pronunciare "Impostazioni Parlato".

Per ulteriori informazioni sulle frasi che è possibile pronunciare, vedere [Usare la voce con HoloLens](hololens-cortana.md).

[Torna all'elenco](#list)

## Si verificano problemi nell'associazione o nell'utilizzo di un dispositivo Bluetooth

Se si verificano problemi con l'[associazione di un dispositivo Bluetooth](hololens-connect-devices.md), provare quanto segue:

- Accedere a **Impostazioni** > **Dispositivi** e assicurarsi che il Bluetooth sia attivo. In tal caso, disattivarlo e attivarlo nuovamente.
- Assicurarsi che il dispositivo Bluetooth sia completamente carico o che abbia delle nuove batterie.
- Se non si riesce ancora a connettersi, [riavviare HoloLens](hololens-recovery.md).

[Torna all'elenco](#list)

## Le impostazioni di HoloLens indicano che i dispositivi sono disponibili ma questi non funzionano

HoloLens non supporta i profili audio del Bluetooth. I dispositivi audio Bluetooth, come altoparlanti e cuffie, possono risultare disponibili nelle impostazioni di HoloLens, ma non sono supportati.

Se si verificano problemi nell'utilizzo di un dispositivo Bluetooth, verificare che si tratti di un dispositivo supportato. I dispositivi supportati sono:

- Tastiere Bluetooth QWERTY in lingua inglese (è possibile utilizzarle ovunque si usi la tastiera olografica).
- Mouse Bluetooth.
- Il [clicker di HoloLens](hololens1-clicker.md).

È possibile associare altri dispositivi Bluetooth HID e GATT insieme a HoloLens. Tuttavia, potrebbe essere necessario installare app complementari corrispondenti da Microsoft Store per utilizzare effettivamente i dispositivi.

[Torna all'elenco](#list)

## Si verificano problemi durante l'utilizzo del clicker di HoloLens

Usare il [clicker](hololens1-clicker.md) per selezionare, scorrere, spostare e ridimensionare gli ologrammi. Le app individuali possono supportare movimenti del clicker aggiuntivi.

Se si verificano problemi nell'utilizzo del clicker, assicurarsi che sia carico e associato a HoloLens. Se la batteria è scarica, la spia lampeggia in giallo. Per verificare che il clicker sia associato, accedere a **Impostazioni** > **Dispositivi** e controllare che sia presente. Per ulteriori informazioni, vedere [Associare il clicker](hololens-connect-devices.md#hololens-1st-gen-pair-the-clicker).

Se il clicker è carico e associato e continuano a verificarsi problemi, reimpostarlo tenendo premuto il pulsante principale e il pulsante di associazione per 15 secondi. Quindi, associare nuovamente il clicker a HoloLens.

Se la reimpostazione del clicker non risolve il problema, vedere [Riavviare o ripristinare il clicker di HoloLens](hololens1-clicker.md#restart-or-recover-the-clicker).

[Torna all'elenco](#list)

## Non è possibile connettersi al Wi-Fi

Ecco alcune operazioni da provare nel caso in cui non si riesca a connettere HoloLens alla rete Wi-Fi:

- Verificare che il Wi-Fi sia attivato. Per farlo, utilizzare il gesto Start, quindi selezionare **Impostazioni** > **Rete&amp; Internet** > **Wi-Fi**. Se il Wi-Fi è attivo, provare a disattivarlo e quindi attivarlo nuovamente.
- Avvicinarsi al router o al punto di accesso.
- Riavviare il router Wi-Fi, quindi [riavviare HoloLens](hololens-recovery.md). Provare a connettersi di nuovo.
- Se nessuna di queste operazioni funziona, assicurarsi che il router stia utilizzando il firmware più recente. Queste informazioni sono disponibili sul sito Web del produttore.

[Torna all'elenco](#list)

## HoloLens non funziona correttamente, non risponde o non si avvia

Se il dispositivo non funziona correttamente, vedere [Riavviare, reimpostare o ripristinare HoloLens](hololens-recovery.md).

[Torna all'elenco](#list)

## Non è possibile accedere a un dispositivo HoloLens poiché è stato configurato in precedenza per un'altra persona

Se il dispositivo è stato precedentemente configurato per un'altra persona, che sia un cliente o un ex-dipendente, e non si dispone della sua password per sbloccare il dispositivo, è possibile eseguire una delle seguenti operazioni:

- Per i dispositivi registrati nella gestione di dispositivi mobili (MDM) di Intune, è possibile utilizzare Intune per [cancellare i dati](https://docs.microsoft.com/intune/remote-actions/devices-wipe) in remoto dal dispositivo. Il dispositivo eseguirà nuovamente il flashing.  
   > [!IMPORTANT]  
   > Quando si cancellano i dati dal dispositivo, assicurarsi di non selezionare **Mantieni lo stato di registrazione e l'account utente**.
- Per un dispositivo non registrato nella gestione di dispositivi mobili, è possibile [inserirlo in **modalità flash** e utilizzare Companion di ripristino avanzato](hololens-recovery.md#clean-reflash-the-device) per ripristinarlo.

[Torna all'elenco](#list)

## Domande riguardanti la gestione dei dispositivi HoloLens

### Posso utilizzare System Center Configuration Manager per gestire i dispositivi HoloLens?

No. È necessario utilizzare un sistema MDM per gestire i dispositivi HoloLens.

### Posso utilizzare Active Directory Domain Services (Ad DS) per gestire gli account utente di HoloLens?

No. È necessario usare Azure Active Directory (Azure AD) per gestire gli account utente per i dispositivi HoloLens.

### HoloLens è in grado di registrare automaticamente Automated Data Capture System (ADCS)?

No.

### HoloLens può partecipare all'autenticazione integrata di Windows?

No.

### HoloLens supporta la personalizzazione?

No. Tuttavia, è possibile risolvere questo problema tramite uno dei seguenti approcci:

- Creare un'app personalizzata, quindi [abilitare la modalità tutto schermo](hololens-kiosk.md). L'app può essere personalizzata e può lanciare altre app (come Remote Assist).  
- Modificare tutte le immagini del profilo utente in Azure AD per il logo della società. (questa soluzione potrebbe non essere adatta a tutte le situazioni).

### Quali funzionalità di registrazione sono disponibili in HoloLens (1ª generazione) e HoloLens 2?

La registrazione è limitata alle tracce che possono essere acquisite in scenari di sviluppo o risoluzione dei problemi o alla telemetria che i dispositivi inviano ai server Microsoft.

[Torna all'elenco](#list)

## Domande riguardanti la sicurezza dei dispositivi HoloLens

Vedere [le informazioni sulla sicurezza di HoloLens 2](security-overview.md).
Per i dispositivi HoloLens 1st Gen, vedere le [domande frequenti](hololens1-faq-security.md).

[Torna all'elenco](#list)

## Come fare per eliminare tutti gli spazi?

*Presto disponibili*

[Torna all'elenco](#list)

## Non è possibile trovare o utilizzare la tastiera per digitare nell'emulatore HoloLens 2

*Presto disponibili*

[Torna all'elenco](#list)
