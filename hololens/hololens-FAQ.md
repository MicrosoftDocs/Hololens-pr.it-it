---
title: Domande frequenti su dispositivi HoloLens e ologrammi
description: Hai una domanda rapida su HoloLens o sull'interazione con gli ologrammi?  Questo articolo offre una risposta rapida e altre risorse.
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
ms.openlocfilehash: 660c3b4d3a35a7794de5e3e2fb18f2a4aba03c0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309178"
---
# <a name="frequently-asked-questions-about-hololens-devices-and-holograms"></a>Domande frequenti su dispositivi HoloLens e ologrammi

Questo articolo risponde ad alcune domande su come usare HoloLens, tra cui come posizionare gli ologrammi, usare gli spazi e altro ancora.

Ogni volta che si verificano problemi, assicurati che a HoloLens sia [addebitato .](https://support.microsoft.com/help/12627/hololens-charge-your-hololens) Provare [a riavviarlo](hololens-restart-recover.md) per verificare se ciò consente di risolvere il problema. Usare l'app Feedback per inviare informazioni sul problema. È possibile trovare l'app Feedback nel menu [ **Start**](holographic-home.md).

Per suggerimenti su come portare holoLens, vedi Domande frequenti su [HoloLens (prima generazione).](hololens1-fit-comfort-faq.md)

Questo articolo risolve le domande e i problemi seguenti: <a id="list"></a>

- [Gli ologrammi non sembrano a destra o si spostano](#my-holograms-dont-look-right-or-are-moving-around)
- [Viene visualizzato un messaggio che indica "Ricerca dello spazio"](#i-see-a-message-that-says-finding-your-space)
- [Non vengono visualizzati gli ologrammi che si prevede di vedere nel mio spazio](#im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space)
- [Non è possibile posizionare gli ologrammi dove si vuole](#i-cant-place-holograms-where-i-want-to)
- [Gli ologrammi scompaiono o sono racchiusi in altri ologrammi o oggetti](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Sono in grado di vedere gli ologrammi sull'altro lato di una barriera](#i-can-see-holograms-that-are-on-the-other-side-of-a-wall)
- [Quando si posiziona un ologramma su una barriera, l'ologramma sembra mobile](#when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float)
- [Le app vengono visualizzate troppo vicino quando si tenta di spostarle](#apps-appear-too-close-to-me-when-im-trying-to-move-them)
- [Si verifica un errore di spazio su disco insufficiente](#im-getting-a-low-disk-space-error)
- [HoloLens non risponde ai movimenti](#hololens-doesnt-respond-to-my-gestures)
- [HoloLens non risponde alla voce](#hololens-doesnt-respond-to-my-voice)
- [Si verificano problemi durante l'associazione o l'uso di un dispositivo Bluetooth](#im-having-problems-pairing-or-using-a-bluetooth-device)
- [Le impostazioni di HoloLens elencano i dispositivi come disponibili, ma non funzionano](#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)
- [Si verificano problemi durante l'uso del clicker HoloLens](#im-having-problems-using-the-hololens-clicker)
- [Non è possibile connettersi al Wi-Fi](#i-cant-connect-to-wi-fi)
- [HoloLens non è in esecuzione, non risponde o non viene avviato](#my-hololens-isnt-running-well-is-unresponsive-or-wont-start)
- [Non è possibile accedere a un dispositivo HoloLens perché è stato configurato in precedenza per un altro utente](#i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else)
- [Domande sulla gestione dei dispositivi HoloLens](#questions-about-managing-hololens-devices)
- [Domande sulla protezione dei dispositivi HoloLens](#questions-about-securing-hololens-devices)
- [Ricerca per categorie eliminare tutti gli spazi?](#how-do-i-delete-all-spaces)
- [Non è possibile trovare o usare la tastiera per digitare nell'emulatore HoloLens 2](#i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator)

## <a name="my-holograms-dont-look-right-or-are-moving-around"></a>Gli ologrammi non hanno un aspetto giusto o si spostano

Se gli ologrammi non hanno un aspetto corretto(ad esempio, sono instabilità o traballanti o sono visualizzati patch nere sopra di essi), provare una di queste correzioni:

- [Pulire la visiera del](hololens1-hardware.md#care-and-cleaning) dispositivo e assicurarsi che nulla blocchi i sensori.
- Assicurarsi di essere in una stanza ben illuminata che non abbia molta luce diretta.
- Provare a guardare l'ambiente circostante in modo che HoloLens possa analizzarli in modo più completo.
- Se sono stati inseriti molti ologrammi, provare a rimuoverli.

Se si verificano ancora problemi, provare a eseguire l'app Calibrazione. Questa app calibra HoloLens solo per consentire agli ologrammi di guardare al meglio. A tale scopo, passare a **Impostazioni Utilità**  >  **di**  >  **sistema**. In **Calibrazione** selezionare **Open Calibration (Apri calibrazione).**

[Torna all'elenco](#list)

## <a name="i-see-a-message-that-says-finding-your-space"></a>Viene visualizzato un messaggio che indica "Ricerca dello spazio"

Quando HoloLens sta imparando o caricando uno spazio, è possibile che venga visualizzato un breve messaggio che indica "Ricerca dello spazio". Se questo messaggio viene visualizzato per più di pochi secondi, verrà visualizzato un altro messaggio sotto il menu Start che indica "Still looking for your space".

Questi messaggi significano che HoloLens ha problemi a eseguire il mapping dello spazio. In questo caso, è possibile aprire le app, ma non posizionare gli ologrammi nell'ambiente.

Se questi messaggi vengono visualizzati spesso, provare una o più delle correzioni seguenti:

- Assicurarsi di essere in una stanza ben illuminata che non abbia molta disartizione diretta.
- Assicurarsi che il visore del dispositivo sia pulito. [Informazioni su come pulire il visore](hololens1-hardware.md#care-and-cleaning).
- Assicurarsi di avere un segnale Wi-Fi sicuro. Se immetti un nuovo ambiente senza Wi-Fi o un segnale Wi-Fi debole, HoloLens non sarà in grado di trovare lo spazio. Controllare la Wi-Fi connessione selezionando **Impostazioni** Rete  >  **&amp; Internet**  >  **Wi-Fi.**
- Provare a spostarsi più lentamente.

[Torna all'elenco](#list)

## <a name="im-not-seeing-the-holograms-that-i-expect-to-see-in-my-space"></a>Non vengono visualizzati gli ologrammi che si prevede di vedere nel mio spazio

Se non vengono visualizzati gli ologrammi inseriti o se ne vengono visualizzati alcuni non previsti, provare una o più delle correzioni seguenti:

- Accendere alcune luci. HoloLens funziona meglio in uno spazio ben illuminato.
- Per rimuovere gli ologrammi non necessari, vedere Impostazioni   >    >  **Ologrammi** di sistema  >  **Rimuovi ologrammi vicini.** In caso contrario, selezionare **Rimuovi tutti gli ologrammi.**

  > [!NOTE]
  > Se il layout o l'illuminazione nello spazio cambiano in modo significativo, il dispositivo potrebbe avere problemi a identificare lo spazio e visualizzare gli ologrammi.

[Torna all'elenco](#list)

## <a name="i-cant-place-holograms-where-i-want-to"></a>Non è possibile posizionare gli ologrammi nel punto in cui si vuole

Di seguito sono riportati alcuni aspetti da provare in caso di problemi di posizionamento degli ologrammi:

- Posizionarsi tra uno e tre metri da dove si sta tentando di posizionare l'ologramma.
- Non posizionare ologrammi su superfici nere o riflettenti.
- Assicurarsi di essere in una stanza ben illuminata che non abbia molta luce diretta.
- Aggirare le stanze in modo che HoloLens possa eseguire nuovamente l'analisi dell'ambiente circostante. Per visualizzare ciò che è già stato analizzato, toccare l'aria per visualizzare l'immagine della mesh di mapping.

[Torna all'elenco](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Gli ologrammi scompaiono o sono racchiusi in altri ologrammi o oggetti

Se ci si avvicina troppo a un ologramma, questo scompare temporaneamente per ripristinare &mdash; l'ologramma, semplicemente allontanarsi da esso. Inoltre, se sono stati posizionati più ologrammi vicini, alcuni potrebbero scomparire. Provare a rimuovere alcuni elementi.

Gli ologrammi possono anche essere bloccati o racchiusi da altri ologrammi o da oggetti come le pareti. In questo caso, provare una delle correzioni seguenti:

- Se l'ologramma è racchiuso in un altro ologramma, spostare l'ologramma racchiuso in un'altra posizione. A tale scopo, selezionare **Regola** e quindi toccare e tenere premuto per posizionarlo.
- Se l'ologramma è racchiuso in una barriera, selezionare **Regola**, quindi andare verso la barriera fino a quando non viene visualizzato l'ologramma. Toccare e tenere premuto, quindi estrarre l'ologramma in avanti e in uscita dalla barriera.
- Se non è possibile spostare l'ologramma usando i movimenti, usare la voce per rimuoverlo. Osservare l'ologramma e quindi pronunciare "Remove". Riaprire quindi l'ologramma e posizionarlo in una nuova posizione.

[Torna all'elenco](#list)

## <a name="i-can-see-holograms-that-are-on-the-other-side-of-a-wall"></a>Sono in grado di vedere gli ologrammi sull'altro lato di una barriera

Se sei molto vicino a una barriera o se HoloLens non ha ancora digitalizzato la barriera, puoi vedere gli ologrammi presenti nella stanza successiva. Per eseguire la scansione della barriera, passare da uno a tre metri dalla barriera e fissarla.

Un oggetto nero o riflettente (ad esempio, un divano nero o un refrigeratore in aureo senza problemi) vicino alla barriera può causare problemi quando HoloLens prova a eseguire la scansione della pareti. Se è presente un oggetto di questo tipo, analizzare l'altro lato della barriera.

[Torna all'elenco](#list)

## <a name="when-i-place-a-hologram-on-a-wall-the-hologram-seems-to-float"></a>Quando si posiziona un ologramma su una barriera, l'ologramma sembra mobile

Un ologramma che si posiziona su una barriera in genere sembra essere un pollice o così lontano dalla barriera. Se sembra essere più lontano, provare una o più delle correzioni seguenti:

- Quando si posiziona un ologramma su una barriera, posizionarsi tra uno e tre metri dalla barriera e affrontare direttamente la superficie.
- Toccare la barriera per visualizzare l'immagine della mesh di mapping. Assicurarsi che la mesh sia allineata alla superficie. In caso contrario, rimuovere l'ologramma, ripetere l'analisi della parete e riprovare.
- Se il problema persiste, eseguire l'app Calibrazione. È possibile trovarlo in Impostazioni **Utilità**  >  **di**  >  **sistema**.

[Torna all'elenco](#list)

## <a name="apps-appear-too-close-to-me-when-im-trying-to-move-them"></a>Le app appaiono troppo vicine quando si tenta di spostarle

Provare a spostarsi e a guardare l'area in cui si posiziona l'app in modo che HoloLens eserciti la scansione dell'area da angolazioni diverse. [Anche la pulizia della visiera del](hololens1-hardware.md#care-and-cleaning) dispositivo può essere utile.

[Torna all'elenco](#list)

## <a name="im-getting-a-low-disk-space-error"></a>Si verifica un errore di spazio su disco insufficiente

Liberare spazio di archiviazione eseguendo una o più delle operazioni seguenti:

- Rimuovere alcuni degli ologrammi inseriti o rimuovere alcuni dati salvati dall'interno delle app. [Ricerca per categorie trovare i dati?](holographic-data.md)
- Eliminare alcune immagini e video nell'app Foto.
- Disinstallare alcune app da HoloLens. **Nell'elenco Tutte le app** toccare e tenere premuta l'app da disinstallare, quindi selezionare **Disinstalla**. La disinstallazione dell'app elimina anche tutti i dati archiviati dall'app nel dispositivo.

[Torna all'elenco](#list)

## <a name="hololens-doesnt-respond-to-my-gestures"></a>HoloLens non risponde ai movimenti

Per assicurarsi che HoloLens possa visualizzare i movimenti, tenere la mano nel frame del movimento. La cornice del movimento si estende di un paio di metri su entrambi i lati. HoloLens può anche vedere meglio la mano quando la tieni davanti a circa 18 pollici (anche se non devi essere precisa). Quando HoloLens vede la mano, il cursore cambia da punto a anello. Altre informazioni [sull'uso dei movimenti in HoloLens 2](hololens2-basic-usage.md) o sull'uso dei movimenti in [HoloLens (prima generazione).](hololens1-basic-usage.md)

[Torna all'elenco](#list)

## <a name="hololens-doesnt-respond-to-my-voice"></a>HoloLens non risponde alla mia voce

HoloLens (prima generazione) e HoloLens 2 hanno il riconoscimento vocale incorporato e supportano anche Cortana (riconoscimento vocale online).

### <a name="built-in-voice-commands-do-not-work"></a>I comandi vocali predefiniti non funzionano

In HoloLens (prima generazione) il riconoscimento vocale incorporato non è configurabile. È sempre attivata. Nella HoloLens 2 è possibile scegliere se attivare il riconoscimento vocale e Cortana durante la configurazione del dispositivo.

Se il HoloLens 2 non risponde alla voce, assicurarsi che il riconoscimento vocale sia attivato. Passare a **Impostazioni di**  >  **avvio**  >  **Privacy**  >  **Riconoscimento vocale** e attivare Riconoscimento **vocale.**

### <a name="cortana-or-dictation-doesnt-work"></a>Cortana o Dettatura non funziona

Se Cortana o Dettatura non rispondono alla voce, assicurarsi che il riconoscimento vocale online sia attivato. Passare a **Impostazioni start**  >    >  **Privacy Speech**  >  **e** verificare le impostazioni di Riconoscimento **vocale** online. 

Se Cortana non risponde ancora, eseguire una delle operazioni seguenti per verificare che Cortana stesso sia attivato:

- In **Tutte le app** selezionare **Cortana** > Menu Notebook Settings   >  **(Impostazioni notebook**  >  **menu)** per apportare modifiche.
- Nella HoloLens 2 selezionare il **pulsante Impostazioni voce** o pronunciare "Impostazioni voce".

Per altre informazioni su ciò che puoi dire, vedi [Usare la voce con HoloLens.](hololens-cortana.md)

[Torna all'elenco](#list)

## <a name="im-having-problems-pairing-or-using-a-bluetooth-device"></a>Si verificano problemi durante l'associazione o l'uso di un dispositivo Bluetooth

Se si verificano problemi durante [l'associazione di un dispositivo Bluetooth,](hololens-connect-devices.md)provare a eseguire le operazioni seguenti:

- Passare a **Impostazioni**  >  **Dispositivi** e verificare che Bluetooth sia attivato. In caso contrario, disattivarlo e riattivarlo.
- Assicurarsi che il dispositivo Bluetooth sia completamente carico o abbia batterie nuove.
- Se non è ancora possibile connettersi, [riavviare HoloLens.](hololens-recovery.md)

[Torna all'elenco](#list)

## <a name="hololens-settings-lists-devices-as-available-but-the-devices-dont-work"></a>Le impostazioni di HoloLens elencano i dispositivi come disponibili, ma non funzionano

HoloLens (prima generazione) non supporta i profili audio Bluetooth. I dispositivi audio Bluetooth, ad esempio altoparlanti e visori, possono essere visualizzati come disponibili nelle impostazioni di HoloLens, ma non sono supportati.

HoloLens 2 supporta il profilo audio Bluetooth A2DP per la riproduzione stereo. Il profilo Bluetooth Hands Free che consente l'acquisizione del microfono da una periferica Bluetooth non è supportato HoloLens 2.

Se si verificano problemi durante l'uso di un dispositivo Bluetooth, assicurarsi che sia un dispositivo supportato. I dispositivi supportati includono:

- Tastiere Bluetooth QWERTY in lingua inglese (è possibile usarle ovunque si usi la tastiera olografica).
- Mouse Bluetooth.
- Il [clicker HoloLens](hololens1-clicker.md).

È possibile associare altri dispositivi HID Bluetooth e GATT con HoloLens. Tuttavia, potrebbe essere necessario installare le app complementari corrispondenti da Microsoft Store per usare effettivamente i dispositivi.

[Torna all'elenco](#list)

## <a name="im-having-problems-using-the-hololens-clicker"></a>Si verificano problemi durante l'uso del clicker HoloLens

Usare il [clicker](hololens1-clicker.md) per selezionare, scorrere, spostare e ridimensionare gli ologrammi. Le singole app possono supportare movimenti clicker aggiuntivi.

Se si verificano problemi durante l'uso del clicker, assicurati che sia addebitato e associato a HoloLens. Se la batteria è in esaurimento, la luce dell'indicatore lampeggia ambra. Per verificare che il clicker sia associato, passare a **Impostazioni**  >  **Dispositivi** e verificare se viene visualizzato qui. Per altre informazioni, vedere [Associare il clicker.](hololens1-clicker.md)

Se il clicker viene addebitato e associato e si verificano ancora problemi, reimpostarlo tenendo premuto il pulsante principale e il pulsante di associazione per 15 secondi. Associa quindi di nuovo il clicker a HoloLens.

Se la reimpostazione del clicker non è utile, vedi [Riavviare o ripristinare il clicker HoloLens.](hololens1-clicker.md#restart-or-recover-the-clicker)

[Torna all'elenco](#list)

## <a name="i-cant-connect-to-wi-fi"></a>Non è possibile connettersi a Wi-Fi

Di seguito sono riportati alcuni aspetti da provare se non è possibile connettere HoloLens a una Wi-Fi rete:

- Assicurarsi che la Wi-Fi sia attivata. Per verificare, usare il movimento Avvia e quindi selezionare **Impostazioni**  >  **Rete &amp; Internet**  >  **Wi-Fi.** Se Wi-Fi è attivata, provare a disattivarla e quindi ad attivarla di nuovo.
- Spostarsi più vicino al router o al punto di accesso.
- Riavviare il router Wi-Fi, quindi [riavviare HoloLens.](hololens-recovery.md) Provare a eseguire di nuovo la connessione.
- Se nessuna di queste operazioni funziona, verificare che il router utilizzi il firmware più recente. Queste informazioni sono disponibili nel sito Web del produttore.

[Torna all'elenco](#list)

## <a name="my-hololens-isnt-running-well-is-unresponsive-or-wont-start"></a>HoloLens non è in esecuzione, non risponde o non viene avviato

Se il dispositivo non funziona correttamente, vedere [Riavviare, reimpostare o ripristinare HoloLens.](hololens-recovery.md)

[Torna all'elenco](#list)

## <a name="i-cant-sign-in-to-a-hololens-device-because-it-was-previously-set-up-for-someone-else"></a>Non è possibile accedere a un dispositivo HoloLens perché è stato configurato in precedenza per un altro utente

Se il dispositivo è stato configurato in precedenza per un altro utente, per un client o per un ex dipendente e non si ha la password per sbloccare il dispositivo, è possibile eseguire una delle operazioni seguenti:

- Per un dispositivo registrato nella gestione dei dispositivi mobili (MDM) di Intune, è possibile usare Intune per cancellare in remoto [il](https://docs.microsoft.com/intune/remote-actions/devices-wipe) dispositivo. Il dispositivo viene quindi nuovamente lampeggiato.  
   > [!IMPORTANT]  
   > Quando si cancella il dispositivo, assicurarsi di lasciare deselezionata l'opzione Mantieni lo stato **di registrazione e l'account** utente.
- Per un dispositivo non MDM, è possibile impostare la modalità [ **flashing**](hololens-recovery.md#clean-reflash-the-device) e usare Advanced Recovery Companion per ripristinare il dispositivo.

[Torna all'elenco](#list)

## <a name="questions-about-managing-hololens-devices"></a>Domande sulla gestione dei dispositivi HoloLens

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>È possibile usare System Center Gestione configurazione (SCCM) per gestire i dispositivi HoloLens?

No. È necessario usare un sistema MDM per gestire i dispositivi HoloLens.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>È possibile usare Active Directory Domain Services (AD DS) per gestire gli account utente di HoloLens?

No. È necessario usare Azure Active Directory (Azure AD) per gestire gli account utente per i dispositivi HoloLens.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>HoloLens è in grado di eseguire la registrazione automatica di Automated Data Capture Systems (ADCS) ?

No.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>HoloLens può partecipare a autenticazione integrata di Windows?

No.

### <a name="does-hololens-support-branding"></a>HoloLens supporta la personalizzazione?

No. Tuttavia, è possibile risolvere questo problema usando uno degli approcci seguenti:

- Creare un'app personalizzata e quindi abilitare [la modalità tutto schermo](hololens-kiosk.md). L'app personalizzata può essere personalizzata e può avviare altre app, ad esempio Remote Assist.  
- Modificare tutte le immagini del profilo utente in Azure AD al logo aziendale. Tuttavia, questa operazione potrebbe non essere utile per tutti gli scenari.

### <a name="what-logging-capabilities-do-hololens-1st-gen-and-hololens-2-offer"></a>Quali funzionalità di registrazione offrono HoloLens (prima generazione) e HoloLens 2?

La registrazione è limitata alle tracce che possono essere acquisite in scenari di sviluppo o risoluzione dei problemi o ai dati di telemetria che i dispositivi inviano ai server Microsoft.

[Torna all'elenco](#list)

## <a name="questions-about-securing-hololens-devices"></a>Domande sulla protezione dei dispositivi HoloLens

Vedere [le informazioni HoloLens 2 sicurezza.](security-overview.md)
Per i dispositivi HoloLens di prima generazione, vedere [queste domande frequenti.](hololens1-faq-security.md)

[Torna all'elenco](#list)

## <a name="how-do-i-delete-all-spaces"></a>Ricerca per categorie eliminare tutti gli spazi?

*Presto disponibili*

[Torna all'elenco](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Non è possibile trovare o usare la tastiera per digitare nell'emulatore HoloLens 2

*Presto disponibili*

[Torna all'elenco](#list)
