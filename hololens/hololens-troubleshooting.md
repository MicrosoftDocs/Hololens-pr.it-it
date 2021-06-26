---
title: Risoluzione dei problemi del dispositivo HoloLens
description: Rimanere aggiornati sulle soluzioni più comuni per i problemi dei dispositivi HoloLens e le tecniche di risoluzione dei problemi.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemi, bug, risoluzione dei problemi, correzione, guida, supporto, HoloLens, emulatore
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924622"
---
# <a name="device-troubleshooting"></a>Risoluzione dei problemi del dispositivo

Questo articolo descrive come risolvere diversi problemi comuni di HoloLens.

>[!IMPORTANT]
> Prima di avviare qualsiasi procedura di risoluzione dei problemi, assicurarsi che il dispositivo venga addebitato al **20-40%** della capacità della batteria, se possibile. Le [luci indicatore della batteria](hololens2-setup.md#lights-that-indicate-the-battery-level) posizionate sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.

<a id="list"></a>

**Problemi noti**
- [Remote Assist video si blocca dopo 20 minuti](#remote-assist-video-freezes-after-20-minutes)
- [L'accesso automatico richiede l'accesso](#auto-login-asks-for-log-in)
- [Microsoft Edge non viene avviato](#microsoft-edge-fails-to-launch)
- [La tastiera non passa ai caratteri speciali](#keyboard-doesnt-switch-to-special-characters)
- [Il download dei file bloccati non mostra un errore](#downloading-locked-files-doesnt-error)
- [Portale di dispositivi timeout di caricamento/download di file](#device-portal-file-uploaddownload-times-out)
- [Schermata blu dopo l'annullamento della registrazione da Insider Preview in un dispositivo flash con una build Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive non carica automaticamente le immagini](#onedrive-doesnt-automatically-upload-pictures)

**Generale**
- [HoloLens non risponde o non si avvia](#hololens-is-unresponsive-or-wont-start)
- [Errore "Spazio su disco insufficiente"](#low-disk-space-error)
- [Calibrazione non riuscita](#calibration-fails)
- [Non è possibile accedere perché HoloLens è stato configurato in precedenza per un altro utente](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity non funziona](#unity-isnt-working)
- [Portale di dispositivi di Windows non funziona correttamente](#windows-device-portal-isnt-working-correctly)
- [L'emulatore HoloLens non funziona](#the-hololens-emulator-isnt-working)

**Input**
- [I comandi vocali non funzionano](#voice-commands-arent-working)
- [L'input manuale non funziona](#hand-input-isnt-working)

**Connettività**
- [Non è possibile connettersi al Wi-Fi](#cant-connect-to-wi-fi)

**Dispositivi esterni** 
- [I dispositivi Bluetooth non sono associati](#bluetooth-devices-arent-pairing)
- [Il microfono USB-C non funziona](#usb-c-microphone-isnt-working)
- [I dispositivi elencati come disponibili in Impostazioni non funzionano](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist video si blocca dopo 20 minuti

> [!NOTE]
> A causa della gravità di questo problema noto, la disponibilità di Windows Holographic versione 21H1 è stata sospesa. Se si vuole aggiornare ancora i dispositivi alla versione 21H1, fare riferimento alle istruzioni nelle note sulla versione [nella parte superiore della pagina.](hololens-release-notes.md)

Nella versione più recente di [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)alcuni utenti di Remote Assist hanno riscontrato il blocco dei video durante le chiamate per più di 20 minuti. Si tratta di **un problema noto.**

### <a name="workarounds"></a>Soluzioni alternative

#### <a name="restart-in-between-calls"></a>Riavvio tra le chiamate

Se le chiamate hanno una durata di 20 minuti e si verifica questo problema, provare a riavviare il dispositivo. Il riavvio del dispositivo tra Remote Assist le chiamate aggiorna il dispositivo e lo riporta a uno stato valido.

Per riavviare rapidamente un dispositivo in [Windows Holographic, versione 21H1](hololens-release-notes.md#windows-holographic-version-21h1) aprire il menu Start e selezionare l'icona utente, quindi selezionare **Riavvia**.

#### <a name="revert-to-an-older-build"></a>Ripristinare una compilazione precedente

Alcuni clienti hanno rilevato che quando si ripristina una versione precedente del sistema operativo il problema non si verifica più. Se si è verificato questo problema nei dispositivi, provare a seguire questa procedura:


Soluzioni alternative:

- Se possibile per l'azienda, il caricamento automatico della fotocamera è supportato per gli account Microsoft consumer. È possibile accedere al proprio account Microsoft oltre all'account aziendale o dell'istituto di istruzione (l'app OneDrive supporta l'accesso doppio). Dal profilo account Microsoft all'interno di OneDrive è possibile abilitare il caricamento automatico del rullino della fotocamera in background.

- Se non è possibile usare in modo sicuro un account Microsoft consumer per caricare automaticamente le foto, è possibile caricare manualmente le foto nell'account aziendale o dell'istituto di istruzione dall'app OneDrive. A tale scopo, assicurarsi di aver eseguito l'accesso all'account aziendale o dell'istituto di istruzione nell'app OneDrive. Selezionare il **+** pulsante e scegliere **Carica.** Trovare le foto o i video da caricare passando a **Pictures (Immagini) > Camera Roll (Rullino foto).** Selezionare le foto o i video da caricare e quindi selezionare il **pulsante** Apri.


1. [Scaricare la build per Windows Holographic, versione 20H2 - Aggiornamento di maggio 2021](https://aka.ms/hololens2download/10.0.19041.1146)
1. Seguire le [istruzioni per tornare a una versione precedente del sistema operativo](hololens-update-hololens.md#go-back-to-a-previous-version)
1. Sospendere [manualmente gli aggiornamenti del sistema operativo nel dispositivo](hololens-updates.md#pause-updates-via-device) o per molti dispositivi usare il [rinvio tramite MDM.](hololens-updates.md#configure-an-update-deferral-policy)

[Torna all'elenco](#list)

## <a name="auto-login-asks-for-log-in"></a>L'accesso automatico richiede l'accesso

Un HoloLens 2 può essere configurato per l'accesso automatico tramite Impostazioni Account Opzioni di accesso -> e in   ->    ->   **Obbligatorio** impostare il valore su **Mai**. Ad alcuni utenti potrebbe essere richiesto di accedere di nuovo al dispositivo quando si aggiorna un dispositivo con un aggiornamento di grandi dimensioni, ad esempio un aggiornamento delle funzionalità. Si tratta di **un problema noto.**

Esempio di quando può verificarsi questo problema:

- Aggiornamento di un dispositivo da Windows Holographic versione 2004 (build 19041.xxxx) a Windows Holographic versione 21H1 (build 20346.xxxx)
- Aggiornamento di un dispositivo per eseguire un aggiornamento di grandi dimensioni nella stessa build principale, ad esempio Da Windows Holographic, versione 2004 a Windows Holographic, versione 20H2
- Aggiornamento di un dispositivo da un'immagine factory all'immagine più recente

Questa operazione non deve verificarsi durante:

- Dispositivi che estraeno un aggiornamento di manutenzione mensile

Aggirare i metodi:

- Metodi di accesso come PIN, password, Iris, autenticazione Web o chiavi FIDO2.
- Se non è possibile ricordare il PIN del dispositivo e non sono disponibili altri metodi di autenticazione, un utente può usare la modalità [reflashing manuale.](hololens-recovery.md#manual-procedure)

[Torna all'elenco](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge non viene avviato

> [!NOTE]
> Questo problema è stato originariamente creato con la versione di Microsoft Edge in considerazione. Questo problema può essere risolto nel [nuovo Microsoft Edge](hololens-new-edge.md). In caso contrario, inviare commenti e suggerimenti.

Alcuni clienti hanno segnalato un problema a causa del quale Microsoft Edge non viene avviato. Per questi clienti, il problema persiste durante il riavvio e non viene risolto con gli aggiornamenti di Windows o dell'applicazione. Se si verifica questo problema e si è verificato che [Windows](hololens-updates.md#manually-check-for-updates)è aggiornato, mettere un bug dall'app [Hub di Feedback](hololens-feedback.md) con la categoria e la sottocatego; Installare e aggiornare > Downloading, installing, and configuring Windows Update (Download, installazione e configurazione di Windows Update).

Non sono disponibili soluzioni alternative note perché finora non è stato possibile stabilire la causa radice del problema. La segnalazione di un bug tramite Hub di Feedback sarà utile per l'analisi. Si tratta di **un problema noto.**

[Torna all'elenco](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>La tastiera non passa ai caratteri speciali

Si verifica un problema durante la Configurazione fuori rete, in cui dopo che l'utente ha scelto un account aziendale o dell'istituto di istruzione e ha immesso la password, il tentativo di passare ai caratteri speciali sulla tastiera toccando il pulsante &123 non cambia in caratteri speciali. Si tratta di **un problema noto.**

Operazioni da risolvere:
-   Chiudere la tastiera e riaprirla toccando il campo di testo.
-   Immettere la password in modo non corretto. Al successivo riavvio, la tastiera funzionerà come previsto.
- Autenticazione Web, chiudere la tastiera e selezionare **Accedi da un altro dispositivo.**
-   Se si immettono solo numeri, un utente può tenere premuti determinati tasti per aprire un menu espanso.
-   Uso di una tastiera USB.

Ciò non influisce su:
- Utenti che scelgono di usare un account personale.

[Torna all'elenco](#list)


## <a name="downloading-locked-files-doesnt-error"></a>Il download dei file bloccati non ha un errore
> ! NOTA Si tratta di **un problema** noto risolto in partecipante al Programma Windows Insider build, versione 20348.1403.


Nelle build precedenti di Windows Holographic, quando si tenta di scaricare un file bloccato, il risultato è una pagina di errore HTTP. Nell'aggiornamento di Windows Holographic versione 21H1, il tentativo di scaricare un file bloccato non comporta alcuna operazione visibile. Il file non viene scaricato e non si verifica alcun errore. 

[Torna all'elenco](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portale di dispositivi timeout del caricamento/download di file
> ! NOTA: si tratta **di un** problema noto risolto in partecipante al Programma Windows Insider build, versione 20348.1403. Se in precedenza è stata disabilitata la connessione SSL come parte della soluzione alternativa, è consigliabile ri-abilitarla.


Alcuni clienti hanno rilevato che, quando si tenta di caricare o scaricare file, l'operazione potrebbe bloccarsi e quindi verificarsi un timeout o non essere mai completata. Questo problema è separato dal problema noto["file bloccato",](#downloading-locked-files-doesnt-error) che interessa le build sul mercato di Windows Holographic, versioni 2004, 20H2 e 21H1. Il problema è stato causato da un bug nella gestione di determinate richieste di Portale di dispositivi ed è stato raggiunto in modo più coerente quando si usa https, che è l'impostazione predefinita. 

### <a name="workaround"></a>Soluzione alternativa

Questa soluzione alternativa, che si applica ugualmente Wi-Fi e UsbNcm, consiste nel disabilitare l'opzione "obbligatorio" in "Connessione SSL". A tale scopo, passare a Portale di dispositivi, **Sistema** e selezionare la **pagina** Preferenze. Nella sezione **Sicurezza del dispositivo** individuare Connessione **SSL** e deselezionare per disabilitare **Obbligatorio.**

L'utente dovrebbe quindi passare a http://, non https:// (indirizzo IP) e le funzionalità come il caricamento e il download di file funzioneranno.

[Torna all'elenco](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Schermata blu dopo la annullamento della registrazione da Insider Preview in un dispositivo flash con una build Insider

Si tratta di un problema che interessa gli utenti che si trovavano in una build insider preview, ha ricompresso il proprio HoloLens 2 con una nuova build insider preview e quindi ne è stata annullata la registrazione dal programma Insider. Si tratta di un **problema noto.**

Ciò non influisce su:
- Utenti che non sono registrati in partecipante al Programma Windows Insider 
- Addetti ai lavori:
    - Se un dispositivo è stato registrato dopo le build Insider era la versione 18362.x
    - Se hanno flashed un Insider firmato 19041.x build E rimanere registrati nel programma Insider

Risolvere il problema: 
- Evitare il problema 
    - Eseguire il flash di una build non insider. Uno degli aggiornamenti mensili regolari.
    - Rimanere in Insider Preview
- Reflash del dispositivo

    1. Impostare la [HoloLens 2 in modalità flashing](hololens-recovery.md) manualmente, attivando completamente l'alimentazione senza connettersi. Quindi, tenendo premuto Volume, toccare il pulsante Di alimentazione.
    
    1. Connettersi al PC e aprire Advanced Recovery Companion.
    
    1. Eseguire il flash HoloLens 2 alla compilazione predefinita.

[Torna all'elenco](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive non carica automaticamente le immagini

L'app OneDrive per HoloLens non supporta il caricamento automatico della fotocamera per gli account aziendali o dell'istituto di istruzione. Si tratta di un **problema noto.**

Soluzioni alternative:

- Se possibile per l'azienda, il caricamento automatico della fotocamera è supportato sugli account Microsoft consumer. È possibile accedere al proprio account Microsoft oltre all'account aziendale o dell'istituto di istruzione (l'app OneDrive supporta il doppio accesso). Dal profilo account Microsoft all'interno di OneDrive è possibile abilitare il caricamento automatico del rullino in background.

- Se non è possibile usare in modo sicuro un account Microsoft consumer per caricare automaticamente le foto, è possibile caricare manualmente le foto nell'account aziendale o dell'istituto di istruzione dall'app OneDrive. A tale scopo, assicurarsi di aver eseguito l'accesso all'account aziendale o dell'istituto di istruzione nell'app OneDrive. Selezionare il **+** pulsante e scegliere **Carica**. Trovare le foto o i video da caricare passando a **Immagini > Rullino.** Selezionare le foto o i video da caricare e quindi fare clic **sul pulsante** Apri.

[Torna all'elenco](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens non risponde o non viene avviato

Se HoloLens non viene avviato:

- Se i LED accanto al pulsante di accensione non si accrendono o un solo LED lampeggia brevemente, potrebbe essere necessario caricare [HoloLens.](hololens2-charging.md#charging-the-device)
- Se i LED si accrendono quando si preme il pulsante di accensione ma non è possibile visualizzare alcun elemento sui display, eseguire un [hard reset del dispositivo](hololens-recovery.md#hard-reset-procedure).

Se HoloLens viene bloccato o non risponde:

- Disattivare HoloLens premendo il pulsante di accensione fino a quando tutti e cinque i LED non si spegnino o per 15 secondi se i LED non rispondono. Per avviare HoloLens, premere di nuovo il pulsante di alimentazione.

Se questi passaggi non funzionano, [](hololens-recovery.md) è possibile provare a ripristinare il dispositivo HoloLens 2 [o HoloLens (prima generazione).](hololens1-recovery.md)

[Torna all'elenco](#list)

## <a name="low-disk-space-error"></a>Errore "Spazio su disco insufficiente"

È necessario liberare spazio di archiviazione eseguendo una o più delle operazioni seguenti:

- Eliminare alcuni spazi inutilizzati. Passare a **Impostazioni**  >  **Spazi di**  >  **sistema,** selezionare uno spazio non più necessario e quindi selezionare Rimuovi .
- Rimuovere alcuni ologrammi inseriti.
- Eliminare alcune immagini e video dall'app Foto.
- Disinstallare alcune app da HoloLens. **Nell'elenco Tutte le app** toccare e tenere premuta l'app da disinstallare e quindi selezionare **Disinstalla**.

[Torna all'elenco](#list)

## <a name="calibration-fails"></a>La calibrazione non riesce

La calibrazione dovrebbe funzionare per la maggior parte delle persone, ma in alcuni casi la calibrazione ha esito negativo.
  
Alcuni possibili motivi di errore di calibrazione includono:

- Distrarsi e non seguire gli obiettivi di calibrazione
- Visiera o visiera del dispositivo dirty o scratched non posizionata correttamente
- Occhiali dirty o scratched
- Alcuni tipi di lenti a contatto e occhiali (lenti a contatto colorate, alcune lenti a contatto torico, occhiali bloccante IR, alcuni occhiali da vista alti, occhiali da sole o simili)
- Make-up più pronunciato e alcune estensioni ciglia
- Capello o occhiali di spessore se bloccano la visualizzazione degli occhi da parte del dispositivo
- Alcune fisiologia oculare, condizioni oculari o interventi oculari come occhi ristretti, ciglia lunghe, amblyopia, nystagmus, alcuni casi di LASIK o altri interventi oculari

Se la calibrazione non riesce, provare:

- Pulizia della visiera del dispositivo
- Pulizia degli occhiali
- Push del visore del dispositivo il più vicino possibile agli occhi
- Spostare gli oggetti nella visiera fuori strada (ad esempio i peli)
- Accendere una luce nella stanza o uscire dalla luce diretta

Se sono seguite tutte le linee guida e la calibrazione ha ancora esito negativo, è possibile disabilitare la richiesta di calibrazione in Impostazioni. È anche possibile inviare commenti e suggerimenti in [Hub di Feedback](hololens-feedback.md).

Vedere anche le informazioni correlate per la risoluzione [dei problemi relativi al colore o alla luminosità dell'immagine.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

L'impostazione di IPD non è applicabile HoloLens 2, poiché le posizioni degli occhi vengono calcolate dal sistema. 

[Torna all'elenco](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Non è possibile accedere perché holoLens è stato configurato in precedenza per un altro utente

È possibile [impostare il dispositivo in modalità **Flashing e** usare Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) per ripristinare il dispositivo.

[Torna all'elenco](#list)


## <a name="unity-isnt-working"></a>Unity non funziona

- Vedere [Installare gli strumenti](/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Unity consigliata per lo sviluppo HoloLens.
- I problemi noti con Unity HoloLens Technical Preview sono documentati nei forum di [HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Torna all'elenco](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Portale di dispositivi di Windows non funziona correttamente

- La funzionalità Anteprima dinamica nell'acquisizione di realtà mista può presentare alcuni secondi di latenza.

- Nella pagina Input virtuale i controlli Movimento e Scorrimento nella sezione Movimenti virtuali non sono funzionali. Il loro uso non avrà alcun effetto. La tastiera virtuale nella pagina di input virtuale funziona correttamente.

- Dopo l'abilitazione della modalità sviluppatore in Impostazioni, potrebbero essere trascorsi alcuni secondi prima che l'interruttore accerti Portale di dispositivi abilitata.

[Torna all'elenco](#list)

## <a name="emulator"></a>Emulatore
### <a name="the-hololens-emulator-isnt-working"></a>L'emulatore HoloLens non funziona

Le informazioni sull'emulatore HoloLens sono disponibili nella documentazione per sviluppatori.  Altre informazioni sulla [risoluzione dei problemi dell'emulatore HoloLens.](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)


- Non tutte le app nella Microsoft Store sono compatibili con l'emulatore. Ad esempio, Young Conker e Fragments non sono riproducibili nell'emulatore.
- Non è possibile usare la webcam del PC nell'emulatore.
- La funzionalità Anteprima dinamica del Portale di dispositivi di Windows non funziona con l'emulatore. È comunque possibile acquisire video e immagini di realtà mista.

[Torna all'elenco](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Non è possibile trovare o usare la tastiera per digitare nell'emulatore HoloLens 2

*Presto disponibili*

[Torna all'elenco](#list)

## <a name="voice-commands-arent-working"></a>I comandi vocali non funzionano

Se Cortana non risponde ai comandi vocali, assicurarsi che Cortana sia attivato. Nell'elenco Tutte le app selezionare Impostazioni notebook del menu **Cortana**  >    >    >   per apportare modifiche. Per altre informazioni su ciò che è possibile dire, vedere [Usare la voce con HoloLens.](hololens-cortana.md)

In HoloLens (prima generazione), il riconoscimento vocale incorporato non è configurabile. È sempre attivata. In HoloLens 2, è possibile scegliere se attivare sia il riconoscimento vocale che Cortana durante la configurazione del dispositivo.

Se il HoloLens 2 non risponde alla voce, assicurarsi che il riconoscimento vocale sia attivato. Passare a **Start**  >  **Settings**  >  Privacy Speech (Impostazioni di **avvio) Privacy** Speech  >  **(Riconoscimento** vocale) e attivare Riconoscimento **vocale.**

[Torna all'elenco](#list)

## <a name="hand-input-isnt-working"></a>L'input manuale non funziona

Per assicurarsi che HoloLens possa visualizzare le mani, è necessario mantenerle nel frame del movimento.  La home page di realtà mista fornisce commenti e suggerimenti che consentono di sapere quando vengono rilevate le mani.  Il feedback è diverso nelle diverse versioni di HoloLens:
- In HoloLens (prima generazione), il cursore dello sguardo cambia da punto a anello
- Al HoloLens 2, un cursore a punta del dito viene visualizzato quando la mano è vicina a un ardesia e un raggio della mano viene visualizzato quando gli ardesi sono più lontani

Molte app immersive seguono modelli di input simili a Quelli della home page di realtà mista.  Altre informazioni sull'uso dell'input manuale [in HoloLens (prima generazione)](hololens1-basic-usage.md#use-hololens-with-your-hands) [e HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se si indossano i guanto, si noti che alcuni tipi di guanto non funzionano con il tracciamento delle mani.  Un esempio comune sono i guanto di gomma nera, che tendono ad assorbire la luce a raggi infrarossi e non vengono prelevati dalla fotocamera di profondità.  Se il lavoro prevede i guanto di gomma, è consigliabile provare un colore più chiaro, ad esempio blu o grigio.  Un altro esempio sono i grossi guanto da baggy, che tendono a nascondere la forma della mano. Per ottenere risultati ottimali, è consigliabile usare i guanto il più possibile adattabili al modulo.

Se la visiera ha impronte digitali o sbavature, usare il panno di pulizia microfibra fornito con HoloLens per pulire la visiera in modo pulito.

[Torna all'elenco](#list)

## <a name="cant-connect-to-wi-fi"></a>Non è possibile connettersi a Wi-Fi

Ecco alcuni aspetti da provare se non è possibile connettere HoloLens a una rete Wi-Fi rete:

- Assicurarsi che la Wi-Fi sia attivata. Per controllare, usare il movimento Avvia e quindi selezionare **Impostazioni**  >  **Rete &amp; Internet**  >  **Wi-Fi**. Se Wi-Fi è attivata, provare a disattivarla e quindi attivarla di nuovo.
- Passare più vicino al router o al punto di accesso.
- Riavviare il router Wi-Fi, quindi [riavviare HoloLens](hololens-recovery.md). Provare a eseguire di nuovo la connessione.
- Se nessuna di queste operazioni funziona, verificare che il router utilizzi il firmware più recente. Queste informazioni sono disponibili nel sito Web del produttore.

[Torna all'elenco](#list)
## <a name="bluetooth-devices-arent-pairing"></a>I dispositivi Bluetooth non sono associati

Se si verificano problemi durante [l'associazione di un dispositivo Bluetooth,](hololens-connect-devices.md)provare a eseguire le operazioni seguenti:

- Passare a **Impostazioni**  >  **Dispositivi** e verificare che Bluetooth sia attivato. In caso contrario, disattivarlo e riattivarlo.
- Assicurarsi che il dispositivo Bluetooth sia completamente carico o abbia batterie nuove.
- Se non è ancora possibile connettersi, [riavviare HoloLens.](hololens-recovery.md)

[Torna all'elenco](#list)

## <a name="usb-c-microphone-isnt-working"></a>Il microfono USB-C non funziona
Tenere presente che alcuni microfoni USB-C segnalano erroneamente se stessi sia come *microfono che come* altoparlante. Si tratta di un problema con il microfono e non con HoloLens. Quando si collega uno di questi microfoni a HoloLens, l'audio potrebbe essere perso. Fortunatamente è disponibile una semplice correzione.  

In **Impostazioni suono** di sistema impostare in modo esplicito gli altoparlanti predefiniti (driver audio della funzionalità  ->    ->   **analoga)** come **dispositivo predefinito.** HoloLens deve ricordare questa impostazione anche se il microfono viene rimosso e riconnesso in un secondo momento.

![Risoluzione dei problemi relativi ai microfoni USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>I dispositivi elencati come disponibili in Impostazioni non funzionano

HoloLens (prima generazione) non supporta i profili audio Bluetooth. I dispositivi audio Bluetooth, ad esempio altoparlanti e visori, possono essere visualizzati come disponibili nelle impostazioni di HoloLens, ma non sono supportati.

HoloLens 2 supporta il profilo audio Bluetooth A2DP per la riproduzione stereo. Il profilo Bluetooth Hands Free che consente l'acquisizione del microfono da una periferica Bluetooth non è supportato HoloLens 2.

Se si verificano problemi durante l'uso di un dispositivo Bluetooth, assicurarsi che sia un dispositivo supportato. I dispositivi supportati includono:

- Tastiere Bluetooth QWERTY in lingua inglese (è possibile usarle ovunque si usi la tastiera olografica).
- Mouse Bluetooth.
- Il [clicker HoloLens](hololens1-clicker.md).

È possibile associare altri dispositivi HID Bluetooth e GATT con HoloLens. Tuttavia, potrebbe essere necessario installare app complementari corrispondenti da Microsoft Store per usare effettivamente i dispositivi.

[Torna all'elenco](#list)
