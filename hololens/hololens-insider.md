---
title: Insider Preview per Microsoft HoloLens
description: Scopri come iniziare a usare le build Insider e fornisci un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 2/2/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e36d25a31495b09e2e9f08f8ea5a8bf34fadafeb
ms.sourcegitcommit: 12d96e5d0c733e733f6ff7da2f4efb8e0f96c27b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "11311832"
---
# Insider Preview per Microsoft HoloLens

Benvenuti alle build di insider Preview più recenti per HoloLens! È facile [iniziare e dare](hololens-insider.md#start-receiving-insider-builds) un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.

## Note sulla versione di Windows Insider

Siamo entusiasti di iniziare a volare nuove funzionalità per i partecipanti al programma Windows Insider. Per gli aggiornamenti più recenti sarà possibile eseguire il volo per il canale dev. Continueremo ad aggiornare questa pagina man mano che aggiungiamo altre funzionalità e aggiornamenti alle nostre Build Insider di Windows.  Diventa entusiasta e pronto a combinare questi aggiornamenti nella tua realtà.

| Nome caratteristica                                              | Descrizione breve                                                                      | Disponibile nella build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nuovo Microsoft Edge](#introducing-the-new-microsoft-edge) | Il nuovo Edge Microsoft basato su cromo è ora disponibile per HoloLens 2                         | 20279,1006 |
| [Visualizzatore di WebXR e 360](#webxr-and-360-viewer)             | Provare le esperienze Web immersive e la riproduzione di video di 360                                           | 20289,1000 |
| [App nuove impostazioni](#new-settings-app)                     | L'app impostazioni legacy viene sostituita da una versione aggiornata con nuove funzionalità e impostazioni | 20279,1006 |
| [Selezione app predefinita](#default-app-picker)                 | Scegliere l'app che deve essere avviata per ogni file o tipo di collegamento                                      | 20279,1006 |
| [Office Web App](#office-web-app)                         | Un collegamento a Office Web App è ora elencato in "tutte le app"                                   | 20279,1006 |
| [Scorrere rapidamente verso il tipo](#swipe-to-type)                           | Usare la punta del dito per "scorrere rapidamente" le parole sulla tastiera olografica                        | 20279,1006 |
| [Supporto per microfono esterno USB-C](#usb-c-external-microphone-support) | Usare microfoni USB-C per app e/o assistenza remota.| 20279,1006 |
| [Nuovo Aumid per le nuove app in modalità Kiosk](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | Aumid per le nuove impostazioni e le app Edge | 20279,1006 |
| [Miglioramento della modalità di mancato funzionamento del chiosco](#kiosk-mode-behavior-changes-for-handling-of-failures) | La modalità Kiosk cerca l'accesso assegnato globale prima del menu Start vuoto. | 20279,1006 |
| [Configurare la diagnostica di fallback](#configuring-fallback-diagnostics-via-settings-app) | Impostazione del comportamento di diagnostica di fallback nell'app impostazioni | 20279,1006 |

### Introduzione al nuovo Microsoft Edge

![Animazione del logo legacy Microsoft Edge con il nuovo logo Microsoft Edge](images/new-edge.gif)

Il nuovo Microsoft Edge [adotta il progetto open source Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) per creare una migliore compatibilità per i clienti e una minore frammentazione del Web per gli sviluppatori Web.

Con questa anteprima Insider, il nuovo Microsoft Edge è disponibile per i clienti di HoloLens 2 per la prima volta. Mentre il nuovo Microsoft Edge rimpiazzerà Microsoft Edge legacy in HoloLens 2, entrambi i browser saranno attualmente disponibili per i partecipanti al programma Insider. Condividere feedback e bug con il team tramite la caratteristica **Invia feedback** nel nuovo Microsoft Edge o tramite [Hub feedback](hololens-feedback.md).

![Nuova schermata Microsoft Edge](images/new-edge-ui.png)

#### Avvio del nuovo Microsoft Edge

Esistono due versioni di Microsoft Edge disponibili per i partecipanti al programma Insider: la nuova icona Microsoft Edge nuovo Microsoft bordo ![ ](images/new_edge_logo.png) (rappresentata da un'icona di turbinio blu e verde) e Microsoft Edge Legacy (rappresentato dall'icona "e" bianca). Il nuovo Microsoft Edge viene aggiunto al menu Start e viene avviato automaticamente quando si attiva un collegamento Web. Se si vuole ripristinare l'uso di Microsoft Edge legacy come Web browser predefinito, vedere le istruzioni seguenti per [reimpostare le app predefinite](#default-app-picker).

> [!NOTE]
> La prima volta che si avvia il nuovo Microsoft Edge in HoloLens 2, le impostazioni e i dati verranno importati da Microsoft Edge legacy. Se si continua a usare Microsoft Edge legacy dopo l'avvio del nuovo Microsoft Edge, i nuovi dati non verranno sincronizzati da Microsoft Edge legacy al nuovo Microsoft Edge.

#### Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge

Il nuovo Microsoft Edge offre agli amministratori IT un set molto più ampio di criteri per i browser in HoloLens 2 rispetto a quelli precedentemente disponibili con Microsoft Edge legacy.

Ecco alcune risorse utili per saperne di più sulla gestione delle impostazioni dei criteri per il nuovo Microsoft Edge:

- [Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Mapping dei criteri della versione legacy di Microsoft Edge a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapping dei criteri di Google Chrome a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentazione completa di [Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Dato il volume dei criteri del browser supportati dal nuovo Microsoft Edge, il nostro team non è in grado di garantire che ogni nuovo criterio funzioni in HoloLens 2. Tuttavia, abbiamo testato e confermato che il nuovo equivalente Microsoft Edge di ogni criterio legacy Microsoft Edge precedentemente supportato in HoloLens 2 funziona come previsto. Vedere [Microsoft Edge legacy per Microsoft Edge Policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) per trovare il nuovo equivalente Microsoft Edge di ogni criterio del browser Microsoft Edge legacy in uso con HoloLens 2.
>
> Esistono almeno due nuovi criteri Microsoft Edge noti che *non* funzionano con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### Cosa aspettarsi dal nuovo Microsoft Edge in HoloLens 2

Dato che il nuovo Microsoft Edge è un'app Win32 nativa con un nuovo layer di adapter UWP che consente l'esecuzione su dispositivi UWP, come HoloLens 2, alcune caratteristiche potrebbero non essere immediatamente disponibili. Verranno supportati nuovi scenari e funzionalità nei prossimi mesi, quindi controlla questo spazio per le informazioni aggiornate.

**Scenari e funzionalità attesi per l'utilizzo:**
- Esperienza di prima esecuzione, accesso al profilo e sincronizzazione
- I siti Web devono eseguire il rendering e il comportamento previsto
- La maggior parte delle funzionalità del browser (Preferiti, cronologia e così via) dovrebbe funzionare come previsto
- Modalità scuro
- Installazione di app Web nel dispositivo
- Installazione delle estensioni (verificare se si usano le estensioni che non funzionano correttamente in HoloLens 2)
- Visualizzazione e contrassegno di un PDF
- Audio spaziale da una singola finestra del browser
- Aggiornamento automatico e manuale del browser
- Salvataggio di un PDF dal menu Stampa (con l'opzione "Salva in PDF")

**Scenari e funzionalità disponibili in breve:**
- Estensione del Visualizzatore WebXR e 360
- Ripristino del contenuto per correggere la finestra durante l'esplorazione tra più finestre inserite nell'ambiente

**Scenari e funzionalità che non si prevede di utilizzare:**
- Audio spaziale proveniente da più finestre con flussi audio simultanei
- "Vedi, Dillo"
- Stampa

**Principali problemi noti del browser:**
- La reimpostazione del dispositivo rimuoverà il nuovo Microsoft Edge
- L'anteprima della lente di ingrandimento nella tastiera olografica Mostra contenuto non corretto

#### Canali Insider di Microsoft Edge

Il team Microsoft Edge rende disponibili tre canali di anteprima per la community di Edge Insider: beta, dev e Canary. L'installazione di un canale di anteprima non disinstalla la versione rilasciata di Microsoft Edge in HoloLens 2 ed è possibile installarne più di uno simultaneamente. 

Visita la [Home page di Microsoft Edge Insider](https://www.microsoftedgeinsider.com) per altre informazioni sulla community di Edge Insider. Per altre informazioni sui diversi canali Insider e per iniziare, visita la [pagina di download di Edge Insider](https://www.microsoftedgeinsider.com/download).

Per installare i canali Microsoft Edge insider in HoloLens 2 è disponibile un paio di metodi:

**Installazione diretta sul dispositivo (attualmente disponibile solo per i dispositivi non gestiti)**
  1. In HoloLens 2, visitare la [pagina di download di Edge Insider](https://www.microsoftedgeinsider.com/download)
  1. Selezionare il pulsante **Scarica per HoloLens 2** per il canale Insider di Edge che si vuole installare
  1. Avviare il file msix scaricato dalla coda di download Edge o dalla cartella "download" del dispositivo (tramite Esplora file)
  1. Il [programma di installazione dell'app](app-deploy-app-installer.md) verrà avviato
  1. Selezionare il pulsante **Installa**
  1. Dopo aver completato l'installazione, si troverà Microsoft Edge beta, dev o Canary come voce separata nell'elenco **tutte le app** del menu Start.

**Installare tramite PC con Windows Device Portal (è necessario abilitare la [modalità sviluppatore](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) in HoloLens 2)**
  1. Nel PC, visitare la [pagina di download di Edge Insider](https://www.microsoftedgeinsider.com/download)
  1. Selezionare il **pulsante della freccia a discesa** accanto al pulsante "Scarica per Windows 10" per il canale Insider di Edge che si vuole installare
  1. Selezionare **HoloLens 2** nel menu a discesa
  1. Salvare il file con estensione msix nella cartella "Downloads" del PC (o in un'altra cartella che è possibile trovare facilmente)
  1. Usare [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) nel PC per installare il file msix scaricato in HoloLens 2
  1. Dopo aver completato l'installazione, si troverà Microsoft Edge beta, dev o Canary come voce separata nell'elenco **tutte le app** del menu Start.

> [!NOTE]
> Durante questo Windows Insider Preview per HoloLens 2, la versione di Microsoft Edge nel dispositivo potrebbe essere superiore a quella disponibile in alcuni (o tutti) dei canali Microsoft Edge Insider. Questo per garantire che le nuove funzionalità e le correzioni in particolare destinate al Web browser in HoloLens 2 siano disponibili al più presto possibile per i partecipanti al programma Windows Insider. Subito dopo il rilascio pubblico del prossimo aggiornamento di Windows, le build del canale Microsoft Edge Insider supereranno la versione di Microsoft Edge in HoloLens 2.

### Visualizzatore di WebXR e 360

*Aggiunta in Windows Insider Build 20289,1000*

Il nuovo Microsoft Edge include il supporto per WebXR, che è il nuovo standard per la creazione di esperienze Web Immersive (sostituendo WebVR). Molte esperienze Web immersive sono state progettate pensando a VR (sostituiscono il campo di visualizzazione con un ambiente virtuale), ma queste esperienze sono supportate anche da HoloLens 2. Lo standard WebXR consente inoltre di sfruttare le esperienze Web Immersive in realtà aumentata e mista che sfruttano l'ambiente fisico. Quando gli sviluppatori dedicano più tempo a WebXR, anticipiamo che le nuove esperienze immersive di Augmented e Mixed Reality arriveranno per i clienti di HoloLens 2 da provare.

L'estensione del Visualizzatore di 360 è basata su WebXR e viene installata automaticamente accanto al nuovo Microsoft Edge in HoloLens 2. Questa estensione Web ti offre la possibilità di immergerti in video di 360 gradi. YouTube offre la più grande selezione di video di 360, quindi ti invitiamo a iniziare da lì.

#### Come usare WebXR

1. Passare a un sito Web con il supporto di WebXR.
1. Selezionare il pulsante **Immetti VR** nel sito Web. La posizione e la rappresentazione visiva di questo pulsante possono variare in base al sito Web, ma possono avere un aspetto simile al seguente:

    ![Esempio di pulsante Inserisci VR](images/75px-enter-vr.png)

1. La prima volta che si tenta di avviare un'esperienza di WebXR su un dominio specifico, il browser chiederà il consenso per l'immissione di una visualizzazione immersiva, selezionare **Consenti**.
1. USA i [movimenti di HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) per modificare l'esperienza.
1. Se l'esperienza non ha un pulsante **Esci** , usa il [gesto Start](hololens2-basic-usage.md#start-gesture) per tornare a casa.

**Esempi di WebXR consigliati**
- Visualizzatore di 360 (vedere la sezione successiva)
- [XR dinosauri](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [Colore WebXR](https://threejs.org/examples/webxr_vr_paint.html)

#### Come usare il Visualizzatore di 360

1. Passare a un video di 360 gradi su YouTube.
1. Nel fotogramma video selezionare il pulsante dell'auricolare Mixed Reality:

    ![Pulsante per attivare il Visualizzatore di 360](images/enter-360-viewer.jpg)

1. La prima volta che si tenta di avviare il Visualizzatore di 360 in un dominio specifico, il browser chiederà il consenso per l'immissione di una visualizzazione immersiva. Selezionare **Consenti**.
1. [Toccare aria](hololens2-basic-usage.md#select-using-air-tap) per visualizzare i controlli di riproduzione. Usare i [raggi delle mani e il tocco aria](hololens2-basic-usage.md#select-using-air-tap) per riprodurre/sospendere, saltare avanti/indietro, attivare/disattivare i sottotitoli o interrompere l'esperienza (che esce dalla visualizzazione immersiva). I controlli di riproduzione scompariranno dopo pochi secondi di inattività.

#### Principali problemi noti di WebXR e 360 Viewer
- Nelle esperienze WebXR gli ologrammi possono spostarsi o inclinarsi quando si inclina la testa o si sposta intorno all'ambiente.
- A seconda della complessità dell'esperienza di WebXR, il framerate può eliminare o balbettare.
- Le articolazioni delle mani articolate non sono ancora disponibili in WebXR.
- Quando si esce da un'esperienza di WebXR o di un visualizzatore di 360, potrebbero essere necessarie 30 secondi o più per ricomparire gli ologrammi della realtà mista Home.
- i video di 360 provenienti da siti Web diversi da YouTube potrebbero non funzionare come previsto.
- Se i video di 360 non entrano in visualizzazione immersiva (o se il pulsante dell'auricolare mixed reality non viene visualizzato), provare a aggiornare la pagina.
- Le didascalie non sono ancora visibili nel Visualizzatore di 360 in HoloLens 2.
- La sospensione di un video nel Visualizzatore di 360 interrompe il rendering del video (ma se si seleziona il pulsante Riproduci riprende correttamente la riproduzione).
- Il pulsante "prossimo video" nel Visualizzatore di 360 non è attualmente in uso.
- È possibile riprodurre video 2D in modalità "Theater" immersiva, ma la frequenza dei fotogrammi sarà inferiore a 30 fps.

#### Fornire commenti e suggerimenti su WebXR e 360 Viewer

Condividere feedback e bug con il team tramite la caratteristica **Invia feedback** nel nuovo Microsoft Edge.

### App nuove impostazioni

Con questa versione, stiamo introducendo una nuova versione dell'app Impostazioni. L'app nuove impostazioni include le nuove caratteristiche e le impostazioni espanse per HoloLens 2 nelle aree seguenti: audio, Power & Sleep, Network & Internet, app, account, facilità di accesso e altro ancora.

> [!NOTE]
> Dato che l'app nuove impostazioni è diversa dall'app impostazioni legacy, tutte le finestre delle impostazioni precedentemente inserite intorno all'ambiente verranno rimosse dopo l'aggiornamento.

![Home page dell'app nuove impostazioni](images/new-settings-app.png)

**Nuove funzionalità e impostazioni**
- Ricerca impostazioni: cercare le impostazioni dalla Home page delle impostazioni usando le parole chiave o il nome dell'impostazione
- Sistema > audio:
  - Dispositivi audio di input e output: scegliere in modo indipendente i dispositivi audio di input e output, ad esempio ascoltare l'audio tramite auricolari Bluetooth o usare un microfono USB-C per l'input audio. Nota: i microfoni Bluetooth non sono supportati da HoloLens 2.
  - Volume dell'app: modificare in modo indipendente il volume di ogni app
- Sistema > Power & Sleep: scegliere quando il dispositivo deve andare a dormire dopo un periodo di inattività
- Sistema > batteria: abilitare manualmente la modalità risparmio batteria o impostare una soglia di batteria a cui si attiva automaticamente la modalità risparmio batteria del punto
- Dispositivi > USB: è possibile disabilitare le connessioni USB per impostazione predefinita
- Rete & Internet:
  - Le schede Ethernet USB-C compariranno ora in rete & Internet
  - Le impostazioni della scheda Ethernet USB-C sono ora disponibili, incluso il relativo indirizzo IP
  - Ora è possibile abilitare la modalità aereo in HoloLens 2
- App: puoi reimpostare le app predefinite usate per i tipi di file e collegamenti. Per altre informazioni, vedere [selezione delle app predefinite](#default-app-picker) .
- Account > altri utenti: i proprietari di dispositivi possono aggiungere utenti, aggiornare gli utenti standard ai proprietari dei dispositivi, declassare i proprietari dei dispositivi agli utenti standard e rimuovere gli utenti.
- Accesso facilitato: modificare le dimensioni del testo e alcuni effetti visivi

**Problemi noti**
- Le finestre delle impostazioni precedentemente inserite verranno rimosse (Vedi nota sopra)
- La visita alla pagina notifiche può arrestarsi in modo anomalo nell'app Impostazioni (analisi)
- La pagina Ethernet attualmente non viene visualizzata (per essere risolta a breve)
- Non è più possibile rinominare il dispositivo con l'app Impostazioni (gli amministratori IT possono usare i pacchetti di provisioning o MDM per rinominare i dispositivi)
- L'utilizzo della batteria per il nuovo Microsoft Edge potrebbe non essere corretto, a causa della sua natura di applicazione desktop Win32 supportata da un layer di adapter UWP (nessuna correzione anticipata presto)

### Selezione app predefinita

Quando si attiva un collegamento ipertestuale o si apre un tipo di file con più app installate che la supportano, viene visualizzata una nuova finestra che chiede di selezionare l'app installata deve gestire il tipo di file o di collegamento. In questa finestra puoi anche scegliere se l'app selezionata può gestire il file o il tipo di collegamento "once" o "Always".

![Finestra di selezione delle app](images/default-app-picker.png)

Se si sceglie "sempre", ma in seguito si vuole modificare l'app che gestisce un determinato file o tipo di collegamento, è possibile reimpostare le impostazioni predefinite salvate nelle **> app**. Scorrere fino alla fine della pagina e selezionare il pulsante **Cancella** in "app predefinite per i tipi di file" e/o "app predefinite per i tipi di collegamento". Diversamente dall'impostazione simile nei PC desktop, non è possibile reimpostare le impostazioni predefinite dei singoli tipi di file.

### Office Web App

Office Web App è stato aggiunto all'elenco "tutte le app" nel menu Start. Questa app Web può anche essere bloccata per avviare o disinstallare. Dato che si tratta di un'app Web, la sua funzionalità corrisponde esattamente a quella che si è verificata visitando https://www.office.com . La funzionalità di Office Web App è disponibile solo quando il HoloLens 2 dispone di una connessione Internet attiva.

### Scorrere rapidamente verso il tipo

Alcuni clienti trovano più veloce "digitare" sulle tastiere virtuali scorrendo rapidamente la forma della parola che intendono digitare e si sta eseguendo l'anteprima di questa caratteristica per la tastiera olografica. È possibile scorrere rapidamente una parola alla volta passando la punta del dito attraverso il piano della tastiera olografica, scorrendo rapidamente la forma della parola e quindi ritirando la punta del dito dal piano della tastiera. Puoi scorrere rapidamente le parole di completamento senza dover premere la barra spaziatrice rimuovendo il dito dalla tastiera tra le parole. Si saprà che la funzionalità sta funzionando se viene visualizzata una traccia di scorrimento rapido seguendo il movimento del dito sulla tastiera.

Tieni presente che questa caratteristica può essere difficile da usare e padroneggiare a causa della natura di una tastiera olografica in cui non si sente resistenza al dito (a differenza di uno schermo di un cellulare). Stiamo valutando questa funzionalità per il rilascio pubblico, quindi il feedback è importante; Se la funzionalità è utile o si ha un feedback costruttivo, fatecelo sapere tramite hub di [feedback](hololens-feedback.md).

### Supporto per microfono esterno USB-C

> [!IMPORTANT]
> Il collegamento di **un microfono USB non viene impostato automaticamente come dispositivo di input**. Quando si collega un set di cuffie USB-C, gli utenti osserveranno che l'audio della cuffia viene reindirizzato automaticamente alle cuffie, ma il sistema operativo HoloLens privilegia la matrice microfono interna sopra qualsiasi altro dispositivo di input. **Per usare un microfono USB-C, seguire i passaggi seguenti.**

Gli utenti possono selezionare i microfoni esterni USB-C tramite il pannello impostazioni **audio** . I microfoni USB-C possono essere usati per chiamare, registrare e così via.

Aprire l'app **Impostazioni** e selezionare **sistema**  ->  **audio**.

![Impostazioni audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Per usare i microfoni esterni con **assistenza remota**, gli utenti dovranno fare clic sul collegamento ipertestuale "Gestisci dispositivi audio".
>
> Quindi usa l'elenco a discesa per impostare il microfono esterno come predefinito **o per** le **comunicazioni predefinite.** La scelta **predefinita** indica che il microfono esterno verrà usato ovunque.
>
> La scelta delle **comunicazioni predefinite** indica che il microfono esterno verrà usato nelle app Remote assist e altre comunicazioni, ma la matrice HoloLens MIC può essere ancora usata per altre attività.

![Gestire i dispositivi audio](images/usbc-mic-2.png)

<br>

![Impostare l'impostazione predefinita del microfono](images/usbc-mic-3.jpg)

#### Informazioni sul supporto del microfono Bluetooth

Purtroppo i microfoni Bluetooth non sono ancora supportati in HoloLens 2.

#### Risoluzione dei problemi relativi ai microfoni USB-C

Tieni presente che alcuni microfoni USB-C si riferiscono erroneamente sia come microfono *che* come altoparlante. Si tratta di un problema con il microfono e non con HoloLens. Quando si collega uno di questi microfoni in HoloLens, è possibile che il suono vada perduto. Fortunatamente c'è una semplice correzione.  

In **Impostazioni**  ->  **sistema**  ->  **audio**, imposta esplicitamente gli altoparlanti incorporati **(driver audio di funzionalità analogica)** come **dispositivo predefinito**. HoloLens deve ricordare questa impostazione anche se il microfono viene rimosso e riconnesso in un secondo momento.

![Risoluzione dei problemi relativi ai microfoni USB-C](images/usbc-mic-4.png)

### Usare le nuove app Impostazioni e Edge in modalità Kiosk

Quando Includi app in [chioschi multimediali](hololens-kiosk.md), un amministratore IT spesso aggiunge l'app al chiosco, ma usando l'ID del modello utente dell'app (AUMID). Poiché sia l'app impostazioni che l'app Microsoft Edge sono considerate nuove app e diverse che le app meno recenti che usano Aumid per queste app dovranno essere aggiornate per usare il nuovo AUMID.

Quando modifichi un chiosco per includere le nuove app, ti consigliamo di aggiungere il nuovo AUMID e di uscire da quello precedente. In questo modo è possibile creare una transizione semplice quando gli utenti aggiornano il sistema operativo e non devono ricevere nuovi criteri per usare il chiosco come previsto.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| App Impostazioni obsolete       | HolographicSystemSettings_cw5n1h2txyewy. App            |
| App nuove impostazioni       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| App Microsoft Edge precedente | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nuova app Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe. MSEDGE    |

### Modifiche al comportamento della modalità Kiosk per la gestione degli errori

Nelle build meno recenti, se un dispositivo dispone di una configurazione Kiosk, che è una combinazione di accesso assegnato sia a livello globale che ad accesso assegnato ai membri del gruppo AAD, se la determinazione dell'appartenenza al gruppo AAD non è riuscita, l'utente vedrebbe il menu "[niente visualizzato in Start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)".

A partire da Windows Insider release, l'esperienza del chiosco si ripiego alla configurazione del chiosco globale (se presente) in caso di errori durante la modalità Kiosk del gruppo AAD.

### Configurazione della diagnostica di fallback tramite l'app impostazioni

Ora, nell'app Impostazioni, un utente può configurare il comportamento della [diagnostica di fallback](hololens-diagnostic-logs.md). Nella pagina Impostazioni passare alla ****  ->  pagina relativa alla**risoluzione dei problemi** di privacy per configurare questa impostazione.

> [!NOTE]
> Se è configurato un criterio MDM per il dispositivo, l'utente non sarà in grado di eseguire l'override di tale comportamento.  






## Iniziare a ricevere compilazioni Insider

> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
> - Il comando vocale "dispositivo di riavvio" funziona bene. 
> - È anche possibile scegliere il pulsante Riavvia in Impostazioni/programma Insider di Windows.
>
> Abbiamo avuto un bug sul back-end che potresti aver incontrato e questo ti riporterà in carreggiata.

In un dispositivo HoloLens 2 passa a **Impostazioni**di  >  **aggiornamento &**  >  **programma sicurezza Windows Insider** e selezionare per **iniziare**. Collegare l'account usato per la registrazione come Windows Insider.

Windows Insider ora sta passando ai canali. L'anello **veloce** diventerà il canale **dev**, l'anello **lento** diventerà il **canale Beta**e l' **anteprima del rilascio** diventerà il canale di **anteprima del rilascio**. Ecco come si presenta il mapping:

![Spiegazione di Windows Insider Channels](images/WindowsInsiderChannels.png)

Per altre informazioni, vedere [Introduzione ai canali Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nei Blog di Windows.

Selezionare quindi **lo sviluppo attivo di Windows**, scegliere se si vuole ricevere le build del canale **dev** o del canale **beta** e rivedere le condizioni del programma.

Selezionare **conferma > Riavvia ora** per completare l'installazione. Dopo aver riavviato il dispositivo, accedere a **impostazioni > aggiorna & sicurezza > verificare la disponibilità di aggiornamenti** per ottenere la build più recente.

### Errore di aggiornamento 0x80070490 work-in giro
Se si verifica un errore di aggiornamento 0x80070490 durante l'aggiornamento sul canale dev o beta, provare il lavoro a breve termine seguente. Si tratta di spostare il canale Insider, ritirare l'aggiornamento e quindi spostare il canale Insider di nuovo.

#### Fase 1-versione Preview
1.  Impostazioni, aggiorna & sicurezza, Windows Insider Program, selezionare **Release Preview Channel**.
2.  Impostazioni, aggiornare & sicurezza, Windows Update, **controllare la disponibilità di aggiornamenti**. Dopo l'aggiornamento, continuare con la fase due.

#### Fase due-dev Channel
1. Impostazioni, aggiorna & sicurezza, Windows Insider Program, seleziona **dev Channel**.
2. Impostazioni, aggiornare & sicurezza, Windows Update, **controllare la disponibilità di aggiornamenti**.

## FFU download e istruzioni Flash
Per eseguire il test con un FFU firmato per il volo, è necessario prima di tutto sbloccare il dispositivo prima di infiammare il volo firmato FFU.
1. Nel PC:

    1. Scaricare FFU dal PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installare ARC (Advanced Recovery Companion) da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. In HoloLens-Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Windows Insider Program** , quindi iscriviti, riavvia il dispositivo.

1. Flash FFU-ora è possibile flashare il FFU firmato in anteprima con ARC.

## Inviare feedback e segnalare i problemi

Usare [l'app hub di feedback](hololens-feedback.md) in HoloLens per inviare commenti e segnalazioni. L'uso di hub di feedback assicura che vengano incluse tutte le informazioni di diagnostica necessarie per aiutare i nostri ingegneri a eseguire rapidamente il debug e risolvere il problema.  I problemi con la versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurarsi di accettare il messaggio che chiede se si vuole che l'hub di feedback acceda alla cartella documenti (selezionare **Sì** quando richiesto).

## Nota per gli sviluppatori

Sei il benvenuto e ti consigliamo di provare a sviluppare le tue applicazioni usando le build Insider di HoloLens.  Per iniziare, vedere la [documentazione di HoloLens per sviluppatori](https://developer.microsoft.com/windows/mixed-reality/development) . Le stesse istruzioni funzionano con le build Insider di HoloLens.  Puoi usare le stesse build di Unity e Visual Studio che stai già usando per lo sviluppo di HoloLens.

## Interrompere la ricezione delle build Insider

Se non si vuole più ricevere Build Insider di Windows olografico, è possibile rifiutare la disattivazione quando HoloLens è in esecuzione una build di produzione oppure è possibile [recuperare il dispositivo](hololens-recovery.md) usando il compagno di ripristino avanzato per recuperare il dispositivo in una versione non Insider di Windows olografico.

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che non si iscrivono da insider Preview Builds dopo la reinstallazione manuale di una nuova versione di anteprima acquisiranno una schermata blu. In seguito dovrà recuperare manualmente il dispositivo. Per informazioni dettagliate su se si è interessati o meno, vedere altre informazioni su questo [problema noto](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Per verificare che HoloLens esegua una build di produzione:

1. Accedere a **impostazioni > sistema > informazioni**e trovare il numero di Build.

1. [Vedere le note sulla versione per i numeri di build della produzione](hololens-release-notes.md).

Per rifiutare le build Insider:

1. In un HoloLens in cui è in corso una build di produzione, passare a **impostazioni > aggiornare & sicurezza > programma Windows Insider**e selezionare **Interrompi Build Insider**.

1. Seguire le istruzioni per rifiutare il dispositivo.
