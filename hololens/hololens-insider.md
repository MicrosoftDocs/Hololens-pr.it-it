---
title: Insider Preview per Microsoft HoloLens
description: Scopri come iniziare a usare le build Insider e fornire feedback utili per il prossimo aggiornamento del sistema operativo principale per HoloLens.
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
ms.date: 2/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 885f9a841c5f59f2816667256de0856f8a1f2612
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340540"
---
# Insider Preview per Microsoft HoloLens

Benvenuto nelle ultime build di Insider Preview per HoloLens! È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento del sistema operativo principale per HoloLens.

## Note sulla versione di Windows Insider

Siamo contenti di iniziare di nuovo la distribuzione di nuove funzionalità di anteprima ai windows insider. Per gli aggiornamenti più recenti, le nuove build verranno aggiornate al Canale di sviluppo. Continueremo ad aggiornare questa pagina man quando aggiungeremo altre funzionalità e aggiornamenti alle build di Windows Insider.  Prepararsi a combinare questi aggiornamenti nella realtà.

> [!IMPORTANT]
> Se in precedenza usavi l'app Impostazioni o l'app Microsoft Edge in un chiosco multimediale, queste app sono state sostituite con nuove app che usano un ID app diverso. Ti consigliamo vivamente di leggere [di seguito i nuovi AUMID per le nuove app in modalità tutto schermo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) In questo modo potrai continuare a avere l'app Impostazioni nel chiosco multimediale o includere la nuova app Microsoft Edge.

<br>

| Nome caratteristica                                              | Descrizione breve                                                                      | Disponibile in build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nuovo Microsoft Edge](#introducing-the-new-microsoft-edge) | Il nuovo Microsoft Edge basato su Chromium è ora disponibile per HoloLens 2                         | 20279.1006 |
| [Visualizzatore WebXR e 360](#webxr-and-360-viewer)             | Prova esperienze Web immersive e riproduzione di video a 360                                           | 20289.1000 |
| [Nuova app Impostazioni](#new-settings-app)                     | L'app Impostazioni legacy viene sostituita da una versione aggiornata con nuove funzionalità e impostazioni | 20279.1006 |
| [Calibrazione del colore dello schermo](#display-color-calibration)   | Selezionare un profilo colori alternativo per lo schermo holoLens 2                                | 20293.1000 |
| [Selezione app predefinita](#default-app-picker)                 | Scegliere l'app da avviare per ogni tipo di file o collegamento                                      | 20279.1006 |
| [Office Web App](#office-web-app)                         | Un collegamento all'app Web di Office è ora elencato in "Tutte le app"                                   | 20279.1006 |
| [Scorrimento rapido per digitare](#swipe-to-type)                           | Usare la punta del dito per "scorrere" le parole sulla tastiera olografica                        | 20279.1006 |
| [Supporto microfono esterno USB-C](#usb-c-external-microphone-support) | Usa microfoni USB-C per app e/o Assistenza remota.| 20279.1006 |
| [Nuovi AUMID per le nuove app in modalità tutto schermo](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMID per nuove impostazioni e app Edge | 20279.1006 |
| [New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | Oltre 20 nuovi criteri SettingsURIs per Settings/PageVisibilityList | 20289.1000 |
| [Miglioramento della gestione degli errori in modalità tutto schermo](#kiosk-mode-behavior-changes-for-handling-of-failures) | La modalità tutto schermo cerca l'accesso assegnato globale prima del menu Start vuoto. | 20279.1006 |
| [Configurare la diagnostica di fallback](#configuring-fallback-diagnostics-via-settings-app) | Impostazione del comportamento di diagnostica di fallback nell'app Impostazioni | 20279.1006 |
| [Condividere elementi con dispositivi vicini](#share-things-with-nearby-devices) | Condividere file o URL da un HoloLens a un PC | 20279.1006 |
| [Nuovo strumento di risoluzione dei problemi dell'aggiornamento del sistema operativo](#new-os-update-troubleshooter) | Nuovo strumento di risoluzione dei problemi in Impostazioni per gli aggiornamenti del sistema operativo | 20279.1006 |
| [Miglioramenti e correzioni nell'aggiornamento](#improvements-and-fixes-in-the-update) | Correzioni aggiuntive nell'aggiornamento. | 20279.1006 |

### Introduzione al nuovo Microsoft Edge

![Animazione del logo Microsoft Edge legacy nel nuovo logo di Microsoft Edge](images/new-edge.gif)

Il nuovo Microsoft Edge adotta il progetto [open source Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) per creare una migliore compatibilità per i clienti e una minore frammentazione del Web per gli sviluppatori Web.

Con questa anteprima insider, il nuovo Microsoft Edge è disponibile per la prima volta per i clienti di HoloLens 2. Mentre il nuovo Microsoft Edge sostituirà Microsoft Edge legacy in HoloLens 2, entrambi i browser sono attualmente disponibili per i insider. Condividere feedback e bug con il team tramite la funzionalità **Invia feedback** nel nuovo Microsoft Edge o tramite Hub [di Feedback.](hololens-feedback.md)

![Screenshot del nuovo Microsoft Edge](images/new-edge-ui.png)

#### Avvio del nuovo Microsoft Edge

Sono disponibili due versioni di Microsoft Edge per i insider: la nuova icona di Microsoft Edge di Microsoft Edge (rappresentata da un'icona a scorrimento blu e verde) e l'icona legacy di Microsoft Edge (rappresentata dall'icona ![ ](images/new_edge_logo.png) "e" bianca). Il nuovo Microsoft Edge viene aggiunto al menu Start e viene avviato automaticamente quando attivi un collegamento Web. Se vuoi ripristinare l'uso di Microsoft Edge legacy come Web browser predefinito, vedi le istruzioni seguenti per la reimpostazione [delle app predefinite.](#default-app-picker)

> [!NOTE]
> Quando avvii per la prima volta il nuovo Microsoft Edge in HoloLens 2, le impostazioni e i dati verranno importati da Microsoft Edge legacy. Se si continua a usare Microsoft Edge legacy dopo l'avvio del nuovo Microsoft Edge, i nuovi dati non verranno sincronizzati da Microsoft Edge legacy al nuovo Microsoft Edge.

#### Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge

Il nuovo Microsoft Edge offre agli amministratori IT un set molto più ampio di criteri del browser in HoloLens 2 rispetto a quanto precedentemente disponibile con Microsoft Edge legacy.

Ecco alcune risorse utili per saperne di più sulla gestione delle impostazioni dei criteri per il nuovo Microsoft Edge:

- [Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Mapping dei criteri della versione legacy di Microsoft Edge a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapping dei criteri di Google Chrome a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentazione [completa di Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> A causa del volume di criteri del browser supportati dal nuovo Microsoft Edge, il team non è in grado di garantire che ogni nuovo criterio funzioni in HoloLens 2. Tuttavia, abbiamo testato e confermato che il nuovo equivalente di Microsoft Edge di ogni criterio di Microsoft Edge legacy supportato in precedenza in HoloLens 2 funziona come previsto. Vedi il mapping dei criteri da [Microsoft Edge Legacy](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) a Microsoft Edge per trovare il nuovo equivalente di Microsoft Edge di ogni criterio browser Microsoft Edge legacy che usavi con HoloLens 2.
>
> Esistono almeno due nuovi criteri di ** Microsoft Edge che non funzioneranno con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### Cosa aspettarsi dal nuovo Microsoft Edge in HoloLens 2

Poiché il nuovo Microsoft Edge è un'app Win32 nativa con un nuovo livello di scheda UWP che ne consente l'esecuzione su dispositivi solo UWP come HoloLens 2, alcune funzionalità potrebbero non essere immediatamente disponibili. Supporteremo nuovi scenari e funzionalità nei prossimi mesi, quindi controlla questo spazio per informazioni aggiornate.

**Scenari e funzionalità previsti per il funzionamento:**
- Esperienza di prima esecuzione, accesso al profilo e sincronizzazione
- Il rendering dei siti Web deve essere eseguito e comportarsi come previsto
- La maggior parte delle funzionalità del browser (Preferiti, Cronologia e così via) dovrebbe funzionare come previsto
- Modalità scura
- Installazione di app Web nel dispositivo
- Installazione delle estensioni (determinare se si usano estensioni che non funzionano correttamente in HoloLens 2)
- Visualizzazione e contrassegno di un PDF
- Suono spaziale da una singola finestra del browser
- Aggiornamento automatico e manuale del browser
- Salvataggio di un PDF dal menu Stampa (con l'opzione "Salva in PDF")

**Scenari e funzionalità a breve:**
- Estensione Visualizzatore WebXR e 360
- Ripristino del contenuto per correggere la finestra durante l'esplorazione tra più finestre posizionate nell'ambiente

**Scenari e funzionalità non previsti:**
- Suono spaziale da più finestre con flussi audio simultanei
- "Vedi, pronuncialo"
- Stampa

**Principali problemi noti del browser:**
- La reimpostazione del dispositivo rimuoverà il nuovo Microsoft Edge
- L'anteprima della lente di ingrandimento nella tastiera olografica mostra contenuto non corretto

#### Canali Microsoft Edge Insider

Il team di Microsoft Edge rende disponibili tre canali di anteprima per la community di Edge Insider: Beta, Dev e Canary. L'installazione di un canale di anteprima non disinstalla la versione rilasciata di Microsoft Edge in HoloLens 2 ed è possibile installarne più di uno contemporaneamente. 

Visita la home [page di Microsoft Edge Insider](https://www.microsoftedgeinsider.com) per altre informazioni sulla community di Edge Insider. Per altre informazioni sui diversi canali Edge Insider e per iniziare, visita la pagina di [download di Edge Insider.](https://www.microsoftedgeinsider.com/download)

Sono disponibili due metodi per installare i canali Microsoft Edge Insider in HoloLens 2:

**Installazione diretta nel dispositivo (attualmente disponibile solo per i dispositivi non gestiti)**
  1. In HoloLens 2, visitare la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Seleziona il **pulsante Download per HoloLens 2** per il canale Edge Insider che vuoi installare.
  1. Avvia il file msix scaricato dalla coda di download di Edge o dalla cartella "Download" del dispositivo (usando Esplora file).
  1. [Il programma di installazione app](app-deploy-app-installer.md) verrà avviato.
  1. Seleziona il **pulsante** Installa.
  1. Dopo l'installazione, Microsoft Edge Beta, Dev o Canary è **** una voce separata nell'elenco Tutte le app del menu Start.

**Eseguire l'installazione tramite PC con Windows Device Portal [(è](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) necessario che la modalità sviluppatore sia abilitata in HoloLens 2)**
  1. Nel PC, visita la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Seleziona il **pulsante della freccia dell'elenco** a discesa accanto al pulsante "Scarica per Windows 10" per il canale Edge Insider che vuoi installare.
  1. Seleziona **HoloLens 2** nel menu a discesa.
  1. Salva il file msix nella cartella "Download" del PC (o in un'altra cartella facilmente individuabile).
  1. Usa [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) nel PC per installare il file msix scaricato in HoloLens 2.
  1. Dopo l'installazione, Microsoft Edge Beta, Dev o Canary è **** una voce separata nell'elenco Tutte le app del menu Start.

> [!NOTE]
> Durante questa anteprima di Windows Insider per HoloLens 2, la versione di Microsoft Edge nel dispositivo potrebbe essere superiore a quella disponibile in alcuni (o tutti) canali Microsoft Edge Insider. Ciò garantisce che le nuove funzionalità e le correzioni specifiche per il Web browser in HoloLens 2 accendono i nostri Partecipanti al Programma Windows Insider il prima possibile. Poco dopo il rilascio pubblico del prossimo aggiornamento di Windows, le build del canale Microsoft Edge Insider sorpasseranno la versione di Microsoft Edge su HoloLens 2.

### Visualizzatore WebXR e 360

*Aggiunta nella build 20289.1000 di Windows Insider*

Il nuovo Microsoft Edge include il supporto per WebXR, che è il nuovo standard per la creazione di esperienze Web immersive (sostituendo WebVR). Molte esperienze Web immersive sono state progettate in base alla realtà virtuale (sostituiscono il campo di vista con un ambiente virtuale), ma queste esperienze sono supportate anche da HoloLens 2. Lo standard WebXR consente inoltre esperienze Web immersive in realtà aumentata e mista che usano l'ambiente fisico. Poiché gli sviluppatori trascorrono più tempo con WebXR, prevediamo che nuove esperienze immersive di realtà aumentata e mista arriveranno per i clienti di HoloLens 2.

L'estensione visualizzatore 360 si basa su WebXR e viene installata automaticamente insieme al nuovo Microsoft Edge in HoloLens 2. Questa estensione Web offre la possibilità di immersi in video a 360 gradi. YouTube offre la selezione più ampia di 360 video, quindi ti invitiamo a iniziare da qui.

#### Come usare WebXR

1. Passare a un sito Web con supporto WebXR.
1. Seleziona il **pulsante Enter VR** nel sito Web. La posizione e la rappresentazione visiva di questo pulsante possono variare in base al sito Web, ma l'aspetto potrebbe essere simile al seguente:

    ![Esempio di pulsante Enter VR](images/75px-enter-vr.png)

1. La prima volta che si tenta di avviare un'esperienza WebXR in un dominio specifico, il browser chiederà il consenso per l'immissione di una visualizzazione immersiva, selezionare **Consenti.**
1. Usa [i movimenti di HoloLens 2 per](hololens2-basic-usage.md#the-hand-tracking-frame) modificare l'esperienza.
1. Se l'esperienza non ha un pulsante **Esci,** usa il gesto [Start](hololens2-basic-usage.md#start-gesture) per tornare a casa.

**Esempi WebXR consigliati**
- Visualizzatore 360 (vedere la sezione successiva)
- [Dinosauri XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### Come usare il visualizzatore a 360

1. Passa a un video a 360 gradi su YouTube.
1. Nel fotogramma video seleziona il pulsante dell'headset in realtà mista:

    ![Pulsante per attivare visualizzatore 360](images/enter-360-viewer.jpg)

1. La prima volta che provi ad avviare il visualizzatore 360 in un dominio specifico, il browser chiederà il consenso per accedere a una visualizzazione immersiva. Selezionare **Consenti.**
1. [Air tap](hololens2-basic-usage.md#select-using-air-tap) to bring up the playback controls. Usa [i raggi della mano](hololens2-basic-usage.md#select-using-air-tap) e il tocco dell'aria per riprodurre/mettere in pausa, andare avanti/indietro, attivare/disattivare i sottotitoli o interrompere l'esperienza (che esce dalla visualizzazione immersiva). I controlli di riproduzione scompariranno dopo alcuni secondi di inattività.

#### Principali problemi noti di WebXR e visualizzatore 360
- Nelle esperienze WebXR, gli ologrammi possono cambiare o inclinare quando si inclina la testa o si sposta nell'ambiente.
- A seconda della complessità dell'esperienza WebXR, la frequenza dei fotogrammi può essere notevolmente più complessa.
- Le giunzioni delle mani articolate non sono ancora disponibili in WebXR.
- Quando si esce da un'esperienza WebXR o 360 Viewer, potrebbero essere necessario 30 secondi o più perché gli ologrammi nella casa della realtà mista possano riapparire.
- 360 video da siti Web diversi da YouTube potrebbero non funzionare come previsto.
- Se 360 video non entrano nella visualizzazione immersive (o il pulsante headset della realtà mista non viene visualizzato), prova ad aggiornare la pagina.
- Le didascalie non sono ancora visibili nel visualizzatore 360 in HoloLens 2.
- La sospensione di un video nel visualizzatore 360 interrompe il rendering del video (ma selezionando il pulsante di riproduzione viene ripresa correttamente la riproduzione).
- Il pulsante "Video successivo" nel visualizzatore 360 non funziona attualmente.
- Puoi riprodurre video 2D in una modalità immersiva "cinema", ma la frequenza dei fotogrammi sarà inferiore a 30 fps.

#### Commenti e suggerimenti su WebXR e visualizzatore 360

Condividere feedback e bug con il team tramite la **funzionalità Invia feedback** nel nuovo Microsoft Edge.

### Nuova app Impostazioni

Con questa versione, stiamo introducendo una nuova versione dell'app Impostazioni. La nuova app Impostazioni include nuove funzionalità e impostazioni espanse per HoloLens 2 nelle aree seguenti: Audio, Alimentazione & sospensione, Rete & Internet, App, Account, Accessibilità e altro ancora.

> [!NOTE]
> Poiché la nuova app Impostazioni è distinta dall'app Impostazioni legacy, tutte le finestre Impostazioni posizionate in precedenza nell'ambiente verranno rimosse al momento dell'aggiornamento.

![Home page dell'app Nuove impostazioni](images/new-settings-app.png)

**Nuove caratteristiche e impostazioni**
- Ricerca impostazioni: cercare le impostazioni dalla home page Impostazioni usando parole chiave o il nome dell'impostazione.
- Suono > sistema:
  - Dispositivi audio di input e output: scegli in modo indipendente i dispositivi audio di input e output (ad esempio, ascolta l'audio tramite le cuffie Bluetooth o usa un microfono USB-C per l'input audio).
    > [!NOTE]
    > Bluetooth microfoni non sono supportati da HoloLens 2.
  - Volume dell'app: regola in modo indipendente il volume di ogni app.
- Sistema > stato & sospensione: scegli quando il dispositivo deve passare alla modalità sospensione dopo un periodo di inattività.
- Sistema > batteria: abilita manualmente la modalità risparmio batteria o imposta una soglia della batteria a quel punto la modalità risparmio batteria si attiva automaticamente.
- Dispositivi > USB: puoi disabilitare le connessioni USB per impostazione predefinita.
- Rete & Internet:
  - Le schede Ethernet USB-C verranno ora visualizzate in Rete & Internet.
  - Le impostazioni della scheda Ethernet USB-C sono ora disponibili, incluso il relativo indirizzo IP.
  - Ora puoi abilitare la modalità aereo in HoloLens 2.
- App: puoi reimpostare le app predefinite usate per i tipi di file e collegamenti. Per altre informazioni, vedi [Selezione app predefinita.](#default-app-picker)
- Account > altri utenti: i proprietari dei dispositivi possono aggiungere utenti, aggiornare gli utenti standard ai proprietari dei dispositivi, eseguire il downgrade dei proprietari dei dispositivi a utenti standard e rimuovere gli utenti.
- Accessibilità: modifica delle dimensioni del testo e di alcuni effetti visivi.

**Problemi noti**
- Le finestre Impostazioni posizionate in precedenza verranno rimosse (vedere la nota precedente).
- La visita alla pagina Notifiche potrebbe causare l'arresto anomalo dell'app Impostazioni (in corso di analisi).
- La pagina Ethernet attualmente non viene visualizzata (che verrà corretta a breve).
- Non puoi più rinominare il dispositivo con l'app Impostazioni (gli amministratori IT possono usare pacchetti di provisioning o MDM per rinominare i dispositivi).
- L'utilizzo della batteria per il nuovo Microsoft Edge potrebbe non essere accurato, a causa della sua natura come applicazione desktop Win32 supportata da un livello di scheda UWP (nessuna correzione prevista a breve).

### Calibrazione del colore dello schermo

*Aggiunta nella build 20293.1000 di Windows Insider*

Con questa nuova impostazione, è possibile selezionare un profilo colori alternativo per il display HoloLens 2. In questo modo i colori possono risultare più accurati, soprattutto a livelli di luminosità dello schermo inferiori. La calibrazione del colore dello schermo è disponibile nell'app Impostazioni, nella pagina Calibrazione > sistema.

#### Come usare la calibrazione del colore dello schermo

1. Avvia **l'app Impostazioni** e passa a **Calibrazione > sistema.**
1. In **Calibrazione del colore dello**schermo selezionare il pulsante Esegui **calibrazione del colore dello** schermo.
1. L'esperienza di calibrazione del colore dello schermo si avvierà e ti incoraggerà a assicurarti che la visiera sia nella posizione corretta.
1. Dopo aver seguito le finestre di dialogo delle istruzioni, lo schermo viene automaticamente visualizzato in grigio fino a una luminosità del 30%.
    > [!TIP]
    > Se hai problemi a visualizzare la scena in grigio nel tuo ambiente, puoi regolare manualmente il livello di luminosità di HoloLens 2 usando i pulsanti di luminosità sul lato sinistro del dispositivo.
1. Seleziona i pulsanti da 1 a 6 per provare immediatamente ogni profilo di colore e trovane uno che sia il migliore per i tuoi occhi (questo in genere significa che il profilo che consente alla scena di apparire più neutra, con il motivo a gradazioni di grigio e i toni della buccia che appaiono come previsto).

    ![Visualizzare la scena di calibrazione dei colori](images/color-cal-ui.png)
    
1. Quando sei soddisfatto del profilo selezionato, seleziona il pulsante Salva & **Esci**
1. Se si preferisce non apportare modifiche, selezionare il pulsante **Annulla & Esci** e le modifiche verranno ripristinate

> [!TIP]
> Ecco alcuni suggerimenti utili da tenere presenti durante l'uso dell'impostazione di calibrazione del colore dello schermo:
> - È possibile eseguire di nuovo la calibrazione del colore dello schermo da Impostazioni ogni volta che si desidera
> - Se qualcuno nel dispositivo ha usato in precedenza l'impostazione per modificare i profili colori, la data/ora della modifica più recente verrà visualizzata nella pagina Impostazioni
> - Quando si rieseguono la calibrazione dei colori dello schermo, il profilo colori salvato in precedenza verrà evidenziato e il profilo 0 non verrà visualizzato (poiché il profilo 0 rappresenta il profilo colori originale dello schermo)
> - Se si desidera ripristinare il profilo colori originale dello schermo, è possibile farlo dalla pagina Impostazioni (vedere come reimpostare il profilo [colori)](#how-to-reset-color-profile)

#### Come reimpostare il profilo colori

Se non sei soddisfatto del profilo colori personalizzato salvato in HoloLens 2, puoi ripristinare il profilo colori originale del dispositivo:
1. Avvia **l'app Impostazioni** e passa a **Calibrazione > sistema.**
1. In **Calibrazione colore visualizzazione**selezionare il pulsante Ripristina profilo **colori** predefinito.
1. Lo schermo si spegnerà per diversi secondi durante la reimpostazione. Ti consigliamo di riavviare il dispositivo *anche dopo che* lo schermo si accende nuovamente (vedi problemi [noti).](#top-display-color-calibration-known-issues)

#### Problemi noti relativi alla calibrazione del colore dello schermo superiore

- Nella pagina Impostazioni, la stringa di stato che indica quando è stata modificata l'ultima modifica del profilo colori non sarà aggiornata fino a quando non si ricarica la pagina di Impostazioni 
    - Soluzione alternativa: selezionare un'altra pagina Impostazioni e quindi selezionare di nuovo la pagina Calibrazione.
- Il pulsante "Ripristina profilo colori predefinito" consente di aprire una finestra di dialogo senza testo. Il pulsante "Reimposta" nella finestra di dialogo funziona come previsto.
- Dopo aver selezionato il pulsante "Reimposta", lo schermo potrebbe andare vuoto per 5-10 secondi e potresti notare un comportamento imprevisto nella casa della realtà mista. Please restart your device after using the "Reset" button (we'll be fixing this soon to automatically restart your device and we'll update the Settings text di conseguenza).
- Se HoloLens 2 va in sospensione durante l'esecuzione della calibrazione del colore dello schermo, in seguito riprenderà nella casa della realtà mista e il livello di luminosità dello schermo continuerà a essere inattiva.
- Potrebbe essere necessario provare a premere i pulsanti di luminosità sul lato sinistro del dispositivo verso l'alto o verso il basso alcune volte prima che funzionino come previsto.

### Selezione app predefinita

Quando attivi un collegamento ipertestuale o apri un tipo di file con più app installate, che lo supporta, viene visualizzata una nuova finestra che ti chiede di selezionare l'app installata che deve gestire il tipo di file o collegamento. In questa finestra puoi anche scegliere di fare in modo che l'app selezionata gestirà il file o il tipo di collegamento "Una volta" o "Sempre".

![Finestra di selezione app](images/default-app-picker.png)

Se scegli "Sempre" ma in seguito vuoi modificare l'app che gestisce un determinato tipo di file o collegamento, puoi reimpostare le impostazioni predefinite salvate in Impostazioni **> app.** Scorrere fino alla parte inferiore **** della pagina e selezionare il pulsante Cancella in "App predefinite per i tipi di file" e/o "App predefinite per i tipi di collegamento". A differenza dell'impostazione simile nei PC desktop, non è possibile reimpostare le impostazioni predefinite dei singoli tipi di file.

### Office Web App

L'app Web di Office è stata aggiunta all'elenco "Tutte le app" del menu Start. Questa app Web può anche essere aggiunta a Start o disinstallata. Poiché si tratta di un'app Web, la funzionalità corrispondente corrisponde esattamente a quella che si potrebbe sperimentare visitando https://www.office.com . La funzionalità Office Web App è disponibile solo quando HoloLens 2 dispone di una connessione Internet attiva.

### Scorrimento rapido per digitare

Alcuni clienti trovano più veloce "digitare" sulle tastiere virtuali scorrendo rapidamente la forma della parola che vogliono digitare e stiamo visualizzando in anteprima questa funzionalità per la tastiera olografica. Puoi scorrere una parola alla volta passando la punta del dito attraverso il piano della tastiera olografica, scorrendo la forma della parola e quindi ritirando la punta del dito dal piano della tastiera. Puoi scorrere rapidamente le parole di follow-up senza dover premere la barra spaziatrice rimuovendo il dito dalla tastiera tra le parole. Saprai che la funzionalità funziona se vedi una traccia di scorrimento rapido che segue il movimento del dito sulla tastiera.

Tieni presente che questa funzionalità può essere difficile da usare e master a causa della natura di una tastiera olografica in cui non provi resistenza al dito (a differenza dello schermo di un cellulare). We are evaluating this feature for public release, so your feedback is important; Se la funzionalità è utile o se si dispone di feedback positivi, contattaci tramite [Hub di Feedback.](hololens-feedback.md)

### Supporto microfono esterno USB-C

> [!IMPORTANT]
> L'inserimento di un microfono USB non **lo imposta automaticamente come dispositivo di input.** Quando collegano un set di cuffie USB-C, gli utenti osserveranno che l'audio della cuffia verrà reindirizzato automaticamente alle cuffie, ma il sistema operativo HoloLens assegna la priorità all'array di microfoni interni rispetto a qualsiasi altro dispositivo di input. **Per usare un microfono USB-C, segui i passaggi seguenti.**

Gli utenti possono selezionare i microfoni esterni connessi tramite USB-C usando il **pannello Impostazioni** audio. I microfoni USB-C possono essere usati per chiamate, registrazioni e così via.

Apri **l'app Impostazioni** e seleziona **Suono di**  ->  **sistema.**

![Impostazioni audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Per usare i microfoni esterni con **Assistenza remota,** gli utenti dovranno fare clic sul collegamento ipertestuale "Gestisci dispositivi audio".
>
> Usa quindi l'elenco a discesa per impostare il microfono esterno come **predefinito** o **predefinito per le comunicazioni.** Scegliendo **Predefinito,** il microfono esterno verrà utilizzato ovunque.
>
> Scegliendo **Communications Default,** il microfono esterno verrà usato in Remote Assist e in altre app per le comunicazioni, ma l'array di microfoni HoloLens può comunque essere usato per altre attività.

![Gestire i dispositivi audio](images/usbc-mic-2.png)

<br>

![Impostare il microfono predefinito](images/usbc-mic-3.jpg)

#### E il supporto Bluetooth microfono?

Purtroppo Bluetooth microfoni non sono ancora supportati in HoloLens 2.

#### Risoluzione dei problemi relativi ai microfoni USB-C

Tenere presente che alcuni microfoni USB-C segnalano erroneamente se stessi come microfono *e* altoparlante. Si tratta di un problema con il microfono e non con HoloLens. Quando si collega uno di questi microfoni a HoloLens, il suono potrebbe essere perso. Fortunatamente, esiste una semplice correzione.  

In **Impostazioni suono**di sistema imposta in modo esplicito gli altoparlanti predefiniti (driver audio funzionalità  ->  ****  ->  **** **analogica)** come **dispositivo predefinito.** HoloLens dovrebbe ricordare questa impostazione anche se il microfono viene rimosso e riconnesso in un secondo momento.

![Risoluzione dei problemi relativi ai microfoni USB-C](images/usbc-mic-4.png)

### Usare le nuove app Impostazioni e Edge in modalità tutto schermo

Quando si includono app in [chioschi,](hololens-kiosk.md)un amministratore IT spesso aggiunge l'app al chiosco multimediale ma usa il suo ID modello utente app (AUMID). Poiché sia l'app Impostazioni che l'app Microsoft Edge sono considerate nuove app e diverse da quelle delle app precedenti che usano AUMID per tali app, sarà necessario aggiornarsi per usare il nuovo AUMID.

Quando si modifica un chiosco multimediale per includere le nuove app, è consigliabile aggiungere nel nuovo AUMID e lasciare quella precedente. In questo modo verrà creata una transizione semplice quando gli utenti aggiorneranno il sistema operativo e non sarà necessario ricevere nuovi criteri per continuare a usare il chiosco multimediale come previsto.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| App Impostazioni precedente       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nuova app Impostazioni       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| App Microsoft Edge precedente | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nuova app Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### New SettingsURIs for Page Settings Visibility

In [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) è stato aggiunto il criterio [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visibili all'interno dell'app Impostazioni. PageVisibilityList è un criterio che consente agli amministratori IT di impedire che pagine specifiche nelle impostazioni di sistema siano visibili o accessibili oppure di farlo per tutte le pagine ad accezioni di quelle specificate.

Se si visita [Visibilità impostazioni](settings-uri-list.md)pagina, è possibile trovare istruzioni per l'uso di questo provider di servizi di configurazione e l'elenco degli URI disponibili nelle versioni precedenti.

Nelle build di Windows Insider stiamo espandendo l'elenco degli URI delle impostazioni disponibili, che gli amministratori IT possono gestire. Alcuni di questi URI sono per le nuove aree disponibili all'interno della nuova app Impostazioni. Se si usa il criterio Settings/PageVisibilityList, esaminare l'elenco seguente e modificare le pagine consentite o bloccate in base alle esigenze.

> [!NOTE]
> **Deprecato: ms-settings:network-proxy**
>
> Una pagina delle impostazioni è deprecata nelle build più nuove. La vecchia **pagina & proxy Internet**non è più disponibile come impostazione  >  **** globale. Le nuove impostazioni proxy per ogni connessione sono disponibili in Network **& Internet**  >  **Wi-Fi**  >  **Properties** o **Network & Internet**  >  **Ethernet**  >  **Properties.**

<br>

| Pagina delle impostazioni                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| App > app & funzionalità                               | `ms-settings:appsfeatures`                         |
| App > app & funzionalità > opzioni avanzate          | `ms-settings:appsfeatures-app`                     |
| App > mappe offline                                  | `ms-settings:maps`                                 |
| App > mappe offline > scaricare mappe                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivi > mouse                                      | `ms-settings:mouse`                                |
| Dispositivi > USB                                        | `ms-settings:usb`                                  |
| Modalità & Internet > aereo                   | `ms-settings:network-airplanemode`                 |
| Privacy > Generale                                    | `ms-settings:privacy-general`                      |
| Privacy > personalizzazione & input penna             | `ms-settings:privacy-speechtyping`                 |
| Privacy > Motion                                     | `ms-settings:privacy-motion`                       |
| Bordi dello screenshot > privacy                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Screenshot > privacy e app                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batteria > di sistema                                     | `ms-settings:batterysaver`                         |
| Batteria > di sistema                                     | `ms-settings:batterysaver-settings`                |
| Suono > sistema                                       | `ms-settings:sound`                                |
| Sistema > audio > preferenze del dispositivo e del volume dell'app | `ms-settings:apps-volume`                          |
| System > Sound > Gestire i dispositivi audio              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Time & Language > Date & time                        | `ms-settings:dateandtime`                          |
| Ora & lingua > tastiera                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Aggiornamento & sicurezza > ripristino & ripristino               | `ms-settings:reset`                                |

#### URI aggiornati

In precedenza, i due URI seguenti non portava un utente direttamente alle pagine indicate, ma bloccava solo la pagina degli aggiornamenti principali. Gli elementi seguenti sono stati aggiornati per indirizzare le pagine:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### Modifiche al comportamento della modalità tutto schermo per la gestione degli errori

Nelle build precedenti, se un dispositivo aveva una configurazione tutto schermo, ovvero una combinazione dell'accesso assegnato globale e dell'accesso assegnato ai membri del gruppo AAD, se la determinazione dell'appartenenza al gruppo AAD non è riuscita, l'utente non visualizzava " nulla nel menu[Start".](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)

A partire dalla versione Windows Insider, l'esperienza di chiosco multimediale verrà fallback alla configurazione globale del chiosco multimediale (se presente) in caso di errori durante la modalità tutto schermo del gruppo AAD.

### Configurazione della diagnostica di fallback tramite l'app Impostazioni

Ora, nell'app Impostazioni, un utente può configurare il comportamento di [Diagnostica fallback.](hololens-diagnostic-logs.md) Nell'app Impostazioni passa alla **pagina Risoluzione dei**problemi relativi alla privacy per configurare questa  ->  **** impostazione.

> [!NOTE]
> Se sono configurati criteri MDM per il dispositivo, l'utente non sarà in grado di ignorare tale comportamento.  

### Condividere elementi con dispositivi vicini

Condividere elementi con dispositivi Windows 10 vicini, inclusi PC e altri dispositivi HoloLens 2 che eseguono HoloLens Insider builds 20279.1006+. Puoi provarlo in **** Impostazioni esperienze condivise di sistema per condividere file o URL da  ->  ****  ->  **** un HoloLens a un PC. Per altri dettagli, leggi altre informazioni su come condividere [elementi con dispositivi vicini in Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Questa funzionalità può essere gestita tramite [Connectivity/AllowConnectedDevices.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### Nuovo strumento di risoluzione dei problemi dell'aggiornamento del sistema operativo

Oltre agli strumento di risoluzione dei problemi precedenti nell'app Impostazioni, è stato aggiunto un nuovo strumento di risoluzione dei problemi con l'aggiunta della nuova app Impostazioni per gli aggiornamenti del sistema operativo. Passa a **Settings**  ->  **Update &amp; Security**  ->  **Troubleshoot**  ->  **Windows Update** e seleziona **Start.** In questo modo è possibile raccogliere le tracce durante la riproduzione del problema con gli aggiornamenti del sistema operativo per agevolare la risoluzione dei problemi relativi all'IT o al supporto tecnico.

### Miglioramenti e correzioni nell'aggiornamento:

- [La diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics) includerà anche informazioni aggiuntive sul dispositivo per il numero di serie e la versione del sistema operativo.






## Iniziare a ricevere build Insider

> [!NOTE]
> Se non hai aggiornato di recente, riavvia il dispositivo per aggiornare lo stato e ottenere la build più recente.
> - Il comando vocale "Reboot device" funziona correttamente. 
> - Puoi anche scegliere il pulsante di riavvio in Impostazioni/Programma Windows Insider.
>
> Si è verificato un bug nel back-end che potrebbe essere stato riscontrato e ciò consente di tornare in funzione.

In un dispositivo HoloLens 2 vai a **Settings**  >  **Update & Security Windows**Insider  >  **Program** e seleziona **Get started.** Collega l'account che hai usato per registrarti come Windows Insider.

Windows Insider sta ora passando ai canali. **L'anello Fast** diventerà **dev Channel,** **l'anello Slow** diventerà il Canale **Beta**e l'anello **Release Preview** diventerà il Canale di anteprima **delle versioni.** Ecco l'aspetto del mapping:

![Spiegazione dei canali Windows Insider](images/WindowsInsiderChannels.png)

Per altre informazioni, vedi [Introduzione ai canali Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nei blog di Windows.

Seleziona Quindi **Sviluppo attivo di Windows,** scegli se vuoi ricevere le build del Canale **sviluppatore** o del Canale **beta** ed esamina le condizioni del programma.

Selezionare **Confirm > Restart Now** per completare l'operazione. Dopo il riavvio del dispositivo, vai a Impostazioni > Aggiornamento & **sicurezza > verificare** la disponibilità di aggiornamenti per ottenere la build più recente.

### Aggiornamento degli errori 0x80070490 risolvere il problema
Se si verifica un errore di aggiornamento 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a eseguire le operazioni seguenti a breve termine. Si tratta di spostare il canale Insider, raccogliere l'aggiornamento e quindi spostare di nuovo il canale Insider.

#### Passaggio 1 - Versione di anteprima
1.  Impostazioni, Aggiornamento & Sicurezza, Programma Windows Insider, seleziona **Canale di anteprima versione.**
2.  Settings, Update & Security, Windows Update, **Check for updates.** Dopo l'aggiornamento, passare al passaggio 2.

#### Fase due - Dev Channel
1. Impostazioni, Update & Security, Programma Windows Insider, seleziona **Dev Channel.**
2. Settings, Update & Security, Windows Update, **Check for updates.**

## Indicazioni stradali per il download e il flash FFU
Per eseguire il test con una versione di anteprima firmata ffu, devi prima sbloccare il dispositivo prima di lampeggiare la versione di anteprima firmata ffu.
1. Nel PC:

    1. Scarica ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installare ARC (Advanced Recovery Companion) da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. On HoloLens - Flight Unlock: Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up, reboot device.

1. Flash FFU: ora puoi lampeggiare la versione di anteprima firmata FFU usando ARC.

## Inviare commenti e suggerimenti e segnalare i problemi

Usa [l'app Hub di Feedback](hololens-feedback.md) in HoloLens per fornire feedback e segnalare i problemi. L'uso di Hub di Feedback garantisce che tutte le informazioni di diagnostica necessarie siano incluse per aiutare i nostri tecnici a eseguire rapidamente il debug e risolvere il problema.  I problemi con la versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurati di accettare la richiesta che ti chiede se vuoi che Hub di Feedback accedono alla cartella Documenti (seleziona **Sì** quando richiesto).

## Nota per gli sviluppatori

Sei il benvenuto e ti incoraggi a provare a sviluppare le tue applicazioni con le build Insider di HoloLens.  Per iniziare, consultare la documentazione per sviluppatori [di HoloLens.](https://developer.microsoft.com/windows/mixed-reality/development) Queste stesse istruzioni funzionano con le build Insider di HoloLens.  Puoi usare le stesse build di Unity e Visual Studio già in uso per lo sviluppo di HoloLens.

## Interrompere la ricezione delle build Insider

Se non vuoi più ricevere build Insider di Windows Holographic, puoi rifiutare esplicitamente quando HoloLens esegue una build di produzione oppure puoi ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo in una versione non Insider di Windows Holographic. [](hololens-recovery.md)

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che annullano la registrazione alle build di Insider Preview dopo aver reinstallato manualmente una nuova build di anteprima visualizzano una schermata blu. Successivamente devono ripristinare manualmente il dispositivo. Per informazioni dettagliate su se l'utente sarebbe stato o meno in grado di verificarsi, consultare altre informazioni su [questo problema noto.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Per verificare che HoloLens ese in esecuzione una build di produzione:

1. Vai a **Impostazioni > sistema > informazioni su**e trova il numero di build.

1. [Vedi le note sulla versione per i numeri di build di produzione.](hololens-release-notes.md)

Per rifiutare esplicitamente le build Insider:

1. In un HoloLens che esegue una build di produzione, vai a Impostazioni **> Update & Security > Windows Insider Program**e seleziona Interrompi build **Insider.**

1. Segui le istruzioni per rifiutare esplicitamente il dispositivo.
