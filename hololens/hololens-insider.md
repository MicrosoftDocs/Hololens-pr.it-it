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
ms.date: 3/4/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 7c11dfbdb78e59493d648fb3a172d3e1f73048c8
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393880"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuto nelle ultime build di Insider Preview per HoloLens! È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento del sistema operativo principale per HoloLens.

## <a name="windows-insider-release-notes"></a>Note sulla versione di Windows Insider

Siamo contenti di iniziare di nuovo la distribuzione di nuove funzionalità di anteprima ai windows insider. Per gli aggiornamenti più recenti, le nuove build verranno aggiornate al Canale di sviluppo. Continueremo ad aggiornare questa pagina man quando aggiungeremo altre funzionalità e aggiornamenti alle build di Windows Insider.  Prepararsi a combinare questi aggiornamenti nella realtà.

Questo aggiornamento delle funzionalità contiene le funzionalità per due gruppi di destinatari. Funzionalità che possono essere usate da chiunque su un dispositivo dall'utente finale e nuove opzioni di gestione dei dispositivi che possono essere configurate dagli amministratori IT. La tabella delle caratteristiche seguente specifica i gruppi di destinatari con cui è possibile utilizzare ogni nuova funzionalità. Gli amministratori IT possono consultare l'elenco di controllo per l'aggiornamento [dell'amministratore IT](#it-admin---update-checklist)

> [!IMPORTANT]
> Se in precedenza usavi l'app Impostazioni o l'app Microsoft Edge in un chiosco multimediale, queste app sono state sostituite con nuove app che usano un ID app diverso. Ti consigliamo vivamente di leggere [di seguito i nuovi AUMID per le nuove app in modalità tutto schermo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) In questo modo potrai continuare a avere l'app Impostazioni nel chiosco multimediale o includere la nuova app Microsoft Edge.

<br>

| Nome caratteristica                                              | Descrizione breve                                                                      | Destinatari | Disponibile in build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Nuovo Microsoft Edge](#introducing-the-new-microsoft-edge) | Il nuovo Microsoft Edge basato su Chromium è ora disponibile per HoloLens 2                         | Utente finale | 20279.1006 |
| [Visualizzatore WebXR e 360](#webxr-and-360-viewer)             | Prova esperienze Web immersive e riproduzione di video a 360                                           | Utente finale | 20289.1000 |
| [Nuova app Impostazioni](#new-settings-app)                     | L'app Impostazioni legacy viene sostituita da una versione aggiornata con nuove funzionalità e impostazioni | Utente finale | 20279.1006 |
| [Calibrazione del colore dello schermo](#display-color-calibration)   | Selezionare un profilo colori alternativo per lo schermo holoLens 2                                | Utente finale | 20293.1000 |
| [Selezione app predefinita](#default-app-picker)                 | Scegliere l'app da avviare per ogni tipo di file o collegamento                                      | Utente finale | 20279.1006 |
| [Controllo del volume per app](#per-app-volume-control) |  Controllare il volume a livello di app in modo indipendente dal volume di sistema | Utente finale | 20293.1000 |
| [Office Web App](#office-web-app)                         | Un collegamento all'app Web di Office è ora elencato in "Tutte le app"                                   | Utente finale | 20279.1006 |
| [Scorrimento rapido per digitare](#swipe-to-type)                           | Usare la punta del dito per "scorrere" le parole sulla tastiera olografica                        | Utente finale | 20279.1006 |
| [Menu Alimentazione da Start](#power-menu-from-start) | Nel menu Start riavvia e arresta il dispositivo HoloLens | Utente finale | 20293.1000 |
| [Più utenti elencati nella schermata di accesso](#multiple-users-listed-on-sign-in-screen) | Visualizzare più account utente nella schermata di accesso | Utente finale | 20293.1000 |
| [Supporto microfono esterno USB-C](#usb-c-external-microphone-support) | Usa microfoni USB-C per app e/o Assistenza remota.| Utente finale | 20279.1006 |
| [Accesso automatico dei visitatori per chioschi](#visitor-auto-logon-for-kiosks)                          | Consente di abilitare l'accesso automatico agli account dei visitatori per le modalità tutto schermo.                         | Amministratore IT | 20279.1006                 |
| [Nuovi AUMID per le nuove app in modalità tutto schermo](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMID per nuove impostazioni e app Edge | Amministratore IT | 20279.1006 |
| [Miglioramento della gestione degli errori in modalità tutto schermo](#kiosk-mode-behavior-changes-for-handling-of-failures) | La modalità tutto schermo cerca l'accesso assegnato globale prima del menu Start vuoto. | Amministratore IT | 20279.1006 |
| [New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | Oltre 20 nuovi criteri SettingsURIs per Settings/PageVisibilityList | Amministratore IT | 20289.1000 |
| [Configurare la diagnostica di fallback](#configuring-fallback-diagnostics-via-settings-app) | Impostazione del comportamento di diagnostica di fallback nell'app Impostazioni | Amministratore IT | 20279.1006 |
| [Condividere elementi con dispositivi vicini](#share-things-with-nearby-devices) | Condividere file o URL da un HoloLens a un PC | Tutte | 20279.1006 |
| [Nuovo strumento di risoluzione dei problemi dell'aggiornamento del sistema operativo](#new-os-update-troubleshooter) | Nuovo strumento di risoluzione dei problemi in Impostazioni per gli aggiornamenti del sistema operativo | Amministratore IT | 20279.1006 |
| [Anteprima ottimizzazione recapito](#delivery-optimization-preview) | Ridurre il consumo di larghezza di banda per i download da più dispositivi HoloLens | Amministratore IT | 20301.1000 |
| [Miglioramenti e correzioni nell'aggiornamento](#improvements-and-fixes-in-the-update) | Correzioni aggiuntive nell'aggiornamento. | Tutte | 20279.1006 |

### <a name="it-admin---update-checklist"></a>Amministratore IT - Elenco di controllo per l'aggiornamento

Questo elenco di controllo ti aiuterà a conoscere i nuovi elementi aggiunti in questo aggiornamento delle funzionalità che potrebbero influire sulle configurazioni correnti di gestione dei dispositivi o sulle nuove funzionalità che potresti voler iniziare a usare.

#### <a name="updates-to-kiosk-mode"></a>Aggiornamenti alla modalità tutto schermo

[**Nuovi AUMID per le nuove app in modalità tutto schermo**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Se in precedenza usavi l'app Impostazioni o l'app Microsoft Edge in un chiosco multimediale, queste app sono state sostituite con nuove app che usano un ID app diverso. Ti consigliamo vivamente di leggere [di seguito i nuovi AUMID per le nuove app in modalità tutto schermo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) In questo modo potrai continuare a avere l'app Impostazioni nel chiosco multimediale o includere la nuova app Microsoft Edge.

Queste modifiche possono essere eseguite ora e distribuite in tutti i dispositivi e consentono una transizione più fluida all'aggiornamento.

[**Accesso automatico dei visitatori per chioschi**](#visitor-auto-logon-for-kiosks)

I visitatori possono ora accedere automaticamente a un chiosco multimediale. Questo comportamento è attivata per impostazione predefinita, ma può essere gestita e disabilitata.

[**Miglioramento della gestione degli errori in modalità tutto schermo**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Questo aggiornamento ora mantiene i dispositivi più controllati dalla modalità tutto schermo, consentendo di eseguire il fall back a diversi tipi di chioschi prima di presentare semplicemente un chiosco multimediale vuoto. Anche se non è gestibile, potrebbe essere utile informare il reparto di supporto se si usano i chioschi multimediale in un modo che potrebbe essere applicabile alla configurazione.

#### <a name="updates-to-page-settings-visibility"></a>Aggiornamenti alla visibilità delle impostazioni della pagina

[**New SettingsURIs for Page Settings Visibility**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

Se attualmente si usa [Visibilità impostazioni](settings-uri-list.md) pagina, è possibile apportare modifiche agli URI esistenti consentiti o bloccati.

#### <a name="updates-for-your-wdac-policy"></a>Aggiornamenti per i criteri WDAC

Se in precedenza bloccavi Microsoft Edge tramite WDAC, dovrai aggiornare i criteri WDAC. Esamina [quanto segue e](#using-wdac-to-block-new-microsoft-edge) usa il codice di esempio fornito.

#### <a name="newly-configurable-items"></a>Elementi configurabili di recente

- [Configurare la diagnostica di fallback](#configuring-fallback-diagnostics-via-settings-app)
  - È possibile configurare se e chi può raccogliere la diagnostica di fallback.
- [Condividere elementi con dispositivi vicini](#share-things-with-nearby-devices)
  - È possibile disabilitare la nuova funzionalità di condivisione nelle vicinanze.
- [Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Esaminare le nuove configurazioni disponibili per Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nuovo strumento di diagnostica

- [Nuovo strumento di risoluzione dei problemi dell'aggiornamento del sistema operativo](#new-os-update-troubleshooter)
  - Raccogliere i log correlati agli aggiornamenti del sistema operativo

### <a name="introducing-the-new-microsoft-edge"></a>Introduzione al nuovo Microsoft Edge

![Animazione del logo Microsoft Edge legacy nel nuovo logo di Microsoft Edge](images/new-edge.gif)

Il nuovo Microsoft Edge adotta il progetto [open source Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) per creare una migliore compatibilità per i clienti e una minore frammentazione del Web per gli sviluppatori Web.

Con questa anteprima insider, il nuovo Microsoft Edge è disponibile per la prima volta per i clienti di HoloLens 2. Mentre il nuovo Microsoft Edge sostituirà Microsoft Edge legacy in HoloLens 2, entrambi i browser sono attualmente disponibili per i insider. Condividere feedback e bug con il team tramite la funzionalità **Invia feedback** nel nuovo Microsoft Edge o tramite Hub [di Feedback.](hololens-feedback.md)

![Screenshot del nuovo Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Avvio del nuovo Microsoft Edge

Sono disponibili due versioni di Microsoft Edge per i insider: la nuova icona di Microsoft Edge di Microsoft Edge (rappresentata da un'icona a scorrimento blu e verde) e l'icona legacy di Microsoft Edge (rappresentata dall'icona ![ ](images/new_edge_logo.png) "e" bianca). Il nuovo Microsoft Edge viene aggiunto al menu Start e viene avviato automaticamente quando attivi un collegamento Web. Se vuoi ripristinare l'uso di Microsoft Edge legacy come Web browser predefinito, vedi le istruzioni seguenti per la reimpostazione [delle app predefinite.](#default-app-picker)

> [!NOTE]
> Quando avvii per la prima volta il nuovo Microsoft Edge in HoloLens 2, le impostazioni e i dati verranno importati da Microsoft Edge legacy. Se si continua a usare Microsoft Edge legacy dopo l'avvio del nuovo Microsoft Edge, i nuovi dati non verranno sincronizzati da Microsoft Edge legacy al nuovo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge

Il nuovo Microsoft Edge offre agli amministratori IT un set molto più ampio di criteri del browser in HoloLens 2 rispetto a quanto precedentemente disponibile con Microsoft Edge legacy.

Ecco alcune risorse utili per saperne di più sulla gestione delle impostazioni dei criteri per il nuovo Microsoft Edge:

- [Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Mapping dei criteri della versione legacy di Microsoft Edge a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapping dei criteri di Google Chrome a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentazione [completa di Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> A causa del volume di criteri del browser supportati dal nuovo Microsoft Edge, il team non è in grado di garantire che ogni nuovo criterio funzioni in HoloLens 2. Tuttavia, abbiamo testato e confermato che il nuovo equivalente di Microsoft Edge di ogni criterio di Microsoft Edge legacy supportato in precedenza in HoloLens 2 funziona come previsto. Vedi il mapping dei criteri da Microsoft Edge Legacy a [Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) per trovare il nuovo equivalente di Microsoft Edge di ogni criterio browser Microsoft Edge legacy che usavi con HoloLens 2.
>
> Esistono almeno due nuovi criteri di ** Microsoft Edge che non funzioneranno con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Cosa aspettarsi dal nuovo Microsoft Edge in HoloLens 2

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
- Estensione Visualizzatore WebXR e 360
- Ripristino del contenuto per correggere la finestra, quando si esplorano più finestre posizionate nell'ambiente

**Scenari e funzionalità non previsti:**
- Suono spaziale da più finestre con flussi audio simultanei
- "Vedi, pronuncialo"
- Stampa

**Principali problemi noti del browser:**
- La reimpostazione del dispositivo rimuoverà il nuovo Microsoft Edge
- L'anteprima della lente di ingrandimento nella tastiera olografica mostra contenuto non corretto
- A volte lo scorrimento può stutter
- I collegamenti Web nell'app di Microsoft Store potrebbero non avviare il browser
- L'audio potrebbe essere riprodotto dalla finestra del browser errata se l'audio è stato riprodotto in precedenza da un'altra finestra del browser

#### <a name="microsoft-edge-insider-channels"></a>Canali Microsoft Edge Insider

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
> Durante questa anteprima di Windows Insider per HoloLens 2, la versione di Microsoft Edge nel dispositivo potrebbe essere superiore a quella disponibile in alcuni (o tutti) canali Microsoft Edge Insider. Ciò garantisce che le nuove funzionalità e le correzioni specifiche per il Web browser in HoloLens 2 accendono i nostri Partecipanti al Programma Windows Insider il prima possibile. Poco dopo il rilascio pubblico del prossimo aggiornamento di Windows, le build del canale Microsoft Edge Insider sorpasseranno e resteranno al passo con la versione di Microsoft Edge in HoloLens 2.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso di WDAC per bloccare il nuovo Microsoft Edge

Per gli amministratori IT che desiderano aggiornare i criteri [WDAC](windows-defender-application-control-wdac.md) per bloccare la nuova app Microsoft Edge, dovrai aggiungere quanto segue ai criteri.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

### <a name="webxr-and-360-viewer"></a>Visualizzatore WebXR e 360

*Aggiunta nella build 20289.1000 di Windows Insider*

Il nuovo Microsoft Edge include il supporto per WebXR, che è il nuovo standard per la creazione di esperienze Web immersive (sostituendo WebVR). Molte esperienze Web immersive sono state progettate in base alla realtà virtuale (sostituiscono il campo di vista con un ambiente virtuale), ma queste esperienze sono supportate anche da HoloLens 2. Lo standard WebXR consente inoltre esperienze Web immersive in realtà aumentata e mista che usano l'ambiente fisico. Poiché gli sviluppatori trascorrono più tempo con WebXR, prevediamo che nuove esperienze immersive di realtà aumentata e mista arriveranno per i clienti di HoloLens 2.

L'estensione visualizzatore 360 si basa su WebXR e viene installata automaticamente insieme al nuovo Microsoft Edge in HoloLens 2. Questa estensione Web offre la possibilità di immersi in video a 360 gradi. YouTube offre la selezione più ampia di 360 video, quindi ti invitiamo a iniziare da qui.

#### <a name="how-to-use-webxr"></a>Come usare WebXR

1. Passare a un sito Web con supporto WebXR.
1. Seleziona il **pulsante Enter VR** nel sito Web. La posizione e la rappresentazione visiva di questo pulsante possono variare in base al sito Web, ma l'aspetto potrebbe essere simile al seguente:

    ![Esempio di pulsante Enter VR](images/75px-enter-vr.png)

1. La prima volta che si tenta di avviare un'esperienza WebXR in un dominio specifico, il browser chiederà il consenso per l'immissione di una visualizzazione immersiva, selezionare **Consenti.**
1. Usa [i movimenti di HoloLens 2 per](hololens2-basic-usage.md#the-hand-tracking-frame) manipolare l'esperienza.
1. Se l'esperienza non ha un pulsante **Esci,** usa il gesto [Start](hololens2-basic-usage.md#start-gesture) per tornare a casa.

**Esempi WebXR consigliati**
- Visualizzatore 360 (vedere la sezione successiva)
- [Dinosauri XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Come usare il visualizzatore a 360

1. Passa a un video a 360 gradi su YouTube.
1. Nel fotogramma video seleziona il pulsante dell'headset in realtà mista:

    ![Pulsante per attivare visualizzatore 360](images/enter-360-viewer.jpg)

1. La prima volta che provi ad avviare il visualizzatore 360 in un dominio specifico, il browser chiederà il consenso per accedere a una visualizzazione immersiva. Selezionare **Consenti.**
1. [Air tap](hololens2-basic-usage.md#select-using-air-tap) to bring up the playback controls. Usa [i raggi della mano](hololens2-basic-usage.md#select-using-air-tap) e il tocco dell'aria per riprodurre/mettere in pausa, andare avanti/indietro, attivare/disattivare i sottotitoli o interrompere l'esperienza (che esce dalla visualizzazione immersiva). I controlli di riproduzione scompariranno dopo alcuni secondi di inattività.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principali problemi noti del visualizzatore WebXR e 360
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

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Commenti e suggerimenti su WebXR e visualizzatore 360

Condividere feedback e bug con il team tramite la **funzionalità Invia feedback** nel nuovo Microsoft Edge.

### <a name="new-settings-app"></a>Nuova app Impostazioni

Con questa versione stiamo introducendo una nuova versione dell'app Impostazioni. La nuova app Impostazioni include nuove funzionalità e impostazioni espanse per HoloLens 2 nelle aree seguenti: Audio, Alimentazione & sospensione, Rete & Internet, App, Account, Accessibilità e altro ancora.

> [!NOTE]
> Poiché la nuova app Impostazioni è distinta dall'app Impostazioni legacy, tutte le finestre Impostazioni posizionate in precedenza nell'ambiente verranno rimosse al momento dell'aggiornamento.

![Home page dell'app Nuove impostazioni](images/new-settings-app.png)

**Nuove caratteristiche e impostazioni**
- Ricerca impostazioni: cercare le impostazioni dalla home page Impostazioni usando parole chiave o il nome dell'impostazione.
- Suono > sistema:
  - Dispositivi audio di input e output: scegli in modo indipendente i dispositivi audio di input e output (ad esempio, ascolta l'audio tramite le cuffie Bluetooth o usa un microfono USB-C per l'input audio).
    > [!NOTE]
    > Bluetooth microfoni non sono supportati da HoloLens 2.
  - Volume dell'app: regola in modo indipendente il volume di ogni app. Vedi [il controllo del volume per app.](#per-app-volume-control)
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
- Non puoi più rinominare il dispositivo con l'app Impostazioni. Gli amministratori IT possono rinominare i dispositivi usando il modello di nome del dispositivo [Windows Autopilot per HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) o il nodo MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- La pagina Ethernet mostra sempre un dispositivo Ethernet virtuale ("UsbNcm").
- L'utilizzo della batteria per il nuovo Microsoft Edge potrebbe non essere accurato, a causa della sua natura come applicazione desktop Win32 supportata da un livello di scheda UWP (nessuna correzione prevista a breve).

### <a name="display-color-calibration"></a>Calibrazione del colore dello schermo

*Aggiunta nella build 20293.1000 di Windows Insider*

Con questa nuova impostazione, è possibile selezionare un profilo colori alternativo per il display HoloLens 2. In questo modo i colori possono risultare più precisi, soprattutto a livelli di luminosità dello schermo inferiori. La calibrazione del colore dello schermo è disponibile nell'app Impostazioni, nella pagina Calibrazione > sistema.

> [!NOTE]
> Poiché questa impostazione salva un nuovo profilo colori nel firmware dello schermo, si tratta di un'impostazione per dispositivo (e non univoca per ogni account utente).

#### <a name="how-to-use-display-color-calibration"></a>Come usare la calibrazione del colore dello schermo

1. Avvia **l'app** Impostazioni e passa a **Calibrazione > sistema.**
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

#### <a name="how-to-reset-color-profile"></a>Come reimpostare il profilo colori

Se non sei soddisfatto del profilo colori personalizzato salvato in HoloLens 2, puoi ripristinare il profilo colori originale del dispositivo:
1. Avvia **l'app** Impostazioni e passa a **Calibrazione > sistema.**
1. In **Calibrazione colore visualizzazione**selezionare il pulsante Ripristina profilo **colori** predefinito.
1. When the dialog box opens, select **Restart** if you're ready to restart HoloLens 2 and apply your changes.

#### <a name="top-display-color-calibration-known-issues"></a>Problemi noti relativi alla calibrazione del colore dello schermo superiore

- Nella pagina Impostazioni, la stringa di stato che indica quando è stata modificata l'ultima modifica del profilo colori non sarà aggiornata fino a quando non si ricarica la pagina di Impostazioni 
    - Soluzione alternativa: selezionare un'altra pagina Impostazioni e quindi selezionare di nuovo la pagina Calibrazione.
- Se HoloLens 2 va in sospensione durante l'esecuzione della calibrazione del colore dello schermo, in seguito riprenderà nella casa della realtà mista e il livello di luminosità dello schermo continuerà a essere inattiva.
- Potrebbe essere necessario provare a premere i pulsanti di luminosità sul lato sinistro del dispositivo verso l'alto o verso il basso alcune volte prima che funzionino come previsto.
- La localizzazione non è completa per tutti i mercati

### <a name="default-app-picker"></a>Selezione app predefinita

Quando attivi un collegamento ipertestuale o apri un tipo di file con più app installate, che lo supporta, viene visualizzata una nuova finestra che ti chiede di selezionare l'app installata che deve gestire il tipo di file o collegamento. In questa finestra puoi anche scegliere di fare in modo che l'app selezionata gestirà il file o il tipo di collegamento "Una volta" o "Sempre".

![Finestra di selezione app](images/default-app-picker.png)

Se scegli "Sempre" ma in seguito vuoi modificare l'app che gestisce un determinato tipo di file o collegamento, puoi reimpostare le impostazioni predefinite salvate in Impostazioni **> app.** Scorrere fino alla fine della **** pagina e selezionare il pulsante Cancella in "App predefinite per i tipi di file" e/o "App predefinite per i tipi di collegamento". A differenza dell'impostazione simile nei PC desktop, non è possibile reimpostare le impostazioni predefinite dei singoli tipi di file.

### <a name="per-app-volume-control"></a>Controllo del volume per app

Ora in questa build di Windows Insider gli utenti possono modificare manualmente il livello di volume di ogni app. Ciò consente agli utenti di concentrarsi meglio sulle app necessarie o di ascoltare meglio quando usano più app. Ad esempio, se devi disattivare il volume di un'app mentre chiami un'altra persona per assistenza remota in un'altra.

Per impostare il volume di una singola app, passa a **Impostazioni**audio di sistema e in Opzioni audio avanzate  ->  ****  ->  **** seleziona **Volume dell'app e preferenze del dispositivo.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office Web App

L'app Web di Office è stata aggiunta all'elenco "Tutte le app" del menu Start. Questa app Web può anche essere aggiunta a Start o disinstallata. Poiché si tratta di un'app Web, la funzionalità corrispondente corrisponde esattamente a quella che si potrebbe sperimentare visitando https://www.office.com . La funzionalità Office Web App è disponibile solo quando HoloLens 2 dispone di una connessione Internet attiva.

**Problema noto**
- La reimpostazione del dispositivo rimuove l'app Web di Office

### <a name="swipe-to-type"></a>Scorrimento rapido per digitare

Alcuni clienti trovano più veloce "digitare" sulle tastiere virtuali scorrendo rapidamente la forma della parola che vogliono digitare e stiamo visualizzando in anteprima questa funzionalità per la tastiera olografica. Puoi scorrere una parola alla volta passando la punta del dito attraverso il piano della tastiera olografica, scorrendo la forma della parola e quindi ritirando la punta del dito dal piano della tastiera. Puoi scorrere rapidamente le parole di follow-up senza dover premere la barra spaziatrice rimuovendo il dito dalla tastiera tra le parole. La funzionalità funziona se viene visualizzata una traccia di scorrimento rapido che segue il movimento del dito sulla tastiera.

Tieni presente che questa funzionalità può essere difficile da usare e master a causa della natura di una tastiera olografica in cui non provi resistenza al dito (a differenza dello schermo di un cellulare). We are evaluating this feature for public release, so your feedback is important; Se la funzionalità è utile o se si dispone di feedback positivi, contattaci tramite [Hub di Feedback.](hololens-feedback.md)

### <a name="power-menu-from-start"></a>Menu Alimentazione da Start

Un nuovo menu che consente all'utente di disconnettersi, arrestare e riavviare il dispositivo. Indicatore nella schermata Start di HoloLens che mostra quando è disponibile un aggiornamento del sistema.

#### <a name="how-to-use"></a>Modalità di utilizzo

1. Apri la schermata Start di HoloLens usando il gesto [Start](hololens2-basic-usage.md#start-gesture) o pronunciando "Vai a Start".

2. Si noti l'icona con i puntini di sospensione (...) accanto all'immagine del profilo utente:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Selezionare l'immagine del profilo utente usando le mani o il comando vocale "Alimentazione".

4. Viene visualizzato un menu con opzioni per disconnettersi, riavviare o arrestare il dispositivo:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Seleziona le opzioni di menu per disconnettersi, riavviare o arrestare HoloLens. L'opzione Disconnenneti potrebbe non essere disponibile se il dispositivo è configurato per un singolo [account Microsoft (MSA)](hololens-identity.md)o per un account locale.

6. Chiudi il menu toccando qualsiasi altro punto o chiudendo il menu Start con il gesto Start.

#### <a name="update-indicator"></a>Indicatore di aggiornamento

Quando è disponibile un aggiornamento, l'icona dei puntini di sospensione si accenderà per indicare che un riavvio installerà l'aggiornamento Le opzioni di menu cambiano in modo da riflettere la presenza dell'aggiornamento.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Più utenti elencati nella schermata di accesso

In precedenza la schermata di accesso mostrava solo l'utente che ha effettuato l'accesso più di recente, nonché un punto di ingresso "Altro utente". Abbiamo ricevuto il feedback dei clienti che non è sufficiente se più utenti hanno effettuato l'accesso al dispositivo. Era comunque necessario digitare di nuovo il nome utente e così via.

Introdotto in questa build di **** Windows Insider, quando selezioni Altro utente che si trova a destra del campo di immissione del PIN, nella schermata di accesso verranno visualizzati più utenti con cui in precedenza è stato effettuato l'accesso al dispositivo. In questo modo gli utenti possono selezionare il proprio profilo utente e quindi accedere con le credenziali di Windows Hello. Un nuovo utente può anche essere aggiunto al dispositivo da questa pagina Altri utenti tramite il **pulsante Aggiungi account.**

Nel menu Altri utenti, il pulsante Altri utenti visualizza l'ultimo utente che ha eseguito l'accesso al dispositivo. Selezionare questo pulsante per tornare alla schermata di accesso dell'utente.

![Impostazione predefinita della schermata di accesso](./images/multiusers1.jpg)

<br>

![Schermata di accesso di altri utenti](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Supporto microfono esterno USB-C

> [!IMPORTANT]
> L'inserimento di un microfono USB non **lo imposta automaticamente come dispositivo di input.** Quando collegano un set di cuffie USB-C, gli utenti osserveranno che l'audio della cuffia verrà reindirizzato automaticamente alle cuffie, ma il sistema operativo HoloLens assegna la priorità all'array di microfoni interni rispetto a qualsiasi altro dispositivo di input. **Per usare un microfono USB-C, segui i passaggi seguenti.**

Gli utenti possono selezionare i microfoni esterni connessi tramite USB-C usando il **pannello Impostazioni** audio. I microfoni USB-C possono essere usati per chiamate, registrazioni e così via.

Apri **l'app Impostazioni** e seleziona **Suono di**  >  **sistema.**

![Impostazioni audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Per usare i microfoni esterni con **Assistenza remota,** gli utenti dovranno fare clic sul collegamento ipertestuale "Gestisci dispositivi audio".
>
> Usa quindi l'elenco a discesa per impostare il microfono esterno come **predefinito** o **predefinito per le comunicazioni.** Scegliendo **Predefinito,** il microfono esterno verrà utilizzato ovunque.
>
> Scegliendo **Communications Default,** il microfono esterno verrà usato in Remote Assist e in altre app per le comunicazioni, ma l'array di microfoni HoloLens potrebbe essere ancora usato per altre attività.

![Gestire i dispositivi audio](images/usbc-mic-2.png)

<br>

![Impostare il microfono predefinito](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E il supporto Bluetooth microfono?

Purtroppo Bluetooth microfoni non sono ancora supportati in HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Risoluzione dei problemi relativi ai microfoni USB-C

Tenere presente che alcuni microfoni USB-C segnalano erroneamente se stessi come microfono *e* altoparlante. Si tratta di un problema con il microfono e non con HoloLens. Quando si collega uno di questi microfoni a HoloLens, l'audio potrebbe essere perso. Fortunatamente, esiste una semplice correzione.  

In **Impostazioni suono**di sistema imposta in modo esplicito gli altoparlanti predefiniti (driver audio funzionalità  ->  ****  ->  **** **analogica)** come **dispositivo predefinito.** HoloLens dovrebbe ricordare questa impostazione anche se il microfono viene rimosso e riconnesso in un secondo momento.

![Risoluzione dei problemi relativi ai microfoni USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Accesso automatico dei visitatori per chioschi

Questa nuova funzionalità consente di usare l'accesso automatico per gli account dei visitatori per le modalità tutto schermo.

Per una configurazione non AAD, per configurare un dispositivo per l'accesso automatico dei visitatori:

1. Creare un pacchetto di provisioning che:
    1. Configura le impostazioni **di runtime/AssignedAccess per** consentire gli account dei visitatori.
    1. Facoltativamente, registra il dispositivo in MDM **(impostazioni di runtime/Workplace/Registrazioni)** in modo che possa essere gestito in un secondo momento.
    1. Non creare un account locale
1. [Applica il pacchetto di provisioning.](hololens-provisioning.md)

Per una configurazione di AAD, gli utenti possono ottenere un risultato simile a questo oggi senza questa modifica. I dispositivi aggiunti ad AAD configurati per la modalità tutto schermo possono accedere a un account visitatore con un singolo tocco pulsante dalla schermata di accesso. Dopo aver eseguito l'accesso all'account del visitatore, il dispositivo non richiederà di nuovo l'accesso fino a quando il visitatore non viene disconnesso esplicitamente dal menu Start o non viene riavviato il dispositivo.

L'accesso automatico dei visitatori può essere gestito tramite [criteri URI OMA](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) personalizzati:

- Valore URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Criterio  | Descrizione   | Configurazioni  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Consente a un visitatore di accedere automaticamente a un chiosco multimediale   | 1 (Sì), 0 (No, impostazione predefinita).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Usare le nuove app Impostazioni e Edge in modalità tutto schermo

Quando si includono [app](hololens-kiosk.md)in chioschi, un amministratore IT spesso aggiunge l'app al chiosco multimediale ma usa il suo ID modello utente app (AUMID). Poiché sia l'app Impostazioni che l'app Microsoft Edge sono considerate nuove app e diverse da quelle delle app precedenti che usano AUMID per tali app, sarà necessario aggiornarsi per usare il nuovo AUMID.

Quando si modifica un chiosco multimediale per includere le nuove app, è consigliabile aggiungere nel nuovo AUMID e lasciare quella precedente. In questo modo verrà creata una transizione semplice quando gli utenti aggiorneranno il sistema operativo e non sarà necessario ricevere nuovi criteri per continuare a usare il chiosco multimediale come previsto.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| App Impostazioni precedente       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nuova app Impostazioni       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| App Microsoft Edge precedente | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nuova app Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifiche al comportamento della modalità tutto schermo per la gestione degli errori

Nelle build precedenti, se un dispositivo aveva una configurazione tutto schermo, ovvero una combinazione dell'accesso assegnato globale e dell'accesso assegnato ai membri del gruppo AAD, se la determinazione dell'appartenenza al gruppo AAD non è riuscita, l'utente non visualizzava " nulla nel menu[Start".](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)

A partire dalla versione Windows Insider, l'esperienza di chiosco multimediale verrà fallback alla configurazione globale del chiosco multimediale (se presente) in caso di errori durante la modalità tutto schermo del gruppo AAD.

### <a name="new-settingsuris-for-page-settings-visibility"></a>New SettingsURIs for Page Settings Visibility

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
| Sistema > audio > volume dell'app e preferenze del dispositivo | `ms-settings:apps-volume`                          |
| System > Sound > Gestire i dispositivi audio              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Ora & lingua > data & ora                        | `ms-settings:dateandtime`                          |
| Ora & lingua > tastiera                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Aggiornamento & sicurezza > ripristino & ripristino               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URI aggiornati

In precedenza, i due URI seguenti non portava un utente direttamente alle pagine indicate, ma bloccava solo la pagina degli aggiornamenti principali. Gli elementi seguenti sono stati aggiornati per indirizzare le pagine:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configurazione della diagnostica di fallback tramite l'app Impostazioni

Ora, nell'app Impostazioni, un utente può configurare il comportamento di [Diagnostica fallback.](hololens-diagnostic-logs.md) Nell'app Impostazioni passare alla **pagina Risoluzione**  ->  **dei** problemi relativi alla privacy per configurare questa impostazione.

> [!NOTE]
> Se sono configurati criteri MDM per il dispositivo, l'utente non sarà in grado di ignorare tale comportamento.  

### <a name="share-things-with-nearby-devices"></a>Condividere elementi con dispositivi vicini

Condividere elementi con dispositivi Windows 10 vicini, inclusi PC e altri dispositivi HoloLens 2 che eseguono HoloLens Insider builds 20279.1006+. Puoi provarlo in **** Impostazioni esperienze condivise di sistema per condividere file o URL da  ->  ****  ->  **** un HoloLens a un PC. Per altri dettagli, leggi altre informazioni su come condividere [elementi con dispositivi vicini in Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Questa funzionalità può essere gestita tramite [Connectivity/AllowConnectedDevices.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-update-troubleshooter"></a>Nuovo strumento di risoluzione dei problemi dell'aggiornamento del sistema operativo

Oltre agli strumento di risoluzione dei problemi precedenti nell'app Impostazioni, è stato aggiunto un nuovo strumento di risoluzione dei problemi con l'aggiunta della nuova app Impostazioni per gli aggiornamenti del sistema operativo. Passa a **Settings**  ->  **Update &amp; Security**  >  **Troubleshoot**  >  **Windows Update** e seleziona **Start.** In questo modo è possibile raccogliere le tracce durante la riproduzione del problema con gli aggiornamenti del sistema operativo per agevolare la risoluzione dei problemi relativi all'IT o al supporto tecnico.

### <a name="delivery-optimization-preview"></a>Anteprima ottimizzazione recapito

Con questo aggiornamento di HoloLens Insider, Windows Holographic for Business offre un'anteprima anticipata delle impostazioni di ottimizzazione del recapito per ridurre il consumo di larghezza di banda per i download da più dispositivi HoloLens. Una descrizione più completa di questa funzionalità insieme alla configurazione di rete consigliata è disponibile qui: Ottimizzazione recapito per gli [aggiornamenti di Windows 10.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

Le impostazioni seguenti sono abilitate come parte della superficie di gestione e [possono essere configurate da Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Alcune avvertenze su questa offerta di anteprima:

- Il supporto di HoloLens è limitato in questa anteprima solo agli aggiornamenti del sistema operativo.
- Windows Holographic for Business supporta solo le modalità di download HTTP e i download da un [endpoint della cache connessa Microsoft;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Attualmente le modalità di download peer-to-peer e le assegnazioni di gruppo non sono supportate per i dispositivi HoloLens.
- HoloLens non supporta l'ottimizzazione della distribuzione o del recapito per gli endpoint di Windows Server Update Services.
- La risoluzione dei problemi richiederà la diagnostica nel server della cache connessa o la raccolta di una traccia in HoloLens in HoloLens tramite **Settings**  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update.**

### <a name="improvements-and-fixes-in-the-update"></a>Miglioramenti e correzioni nell'aggiornamento:

- [La diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics) includerà anche informazioni aggiuntive sul dispositivo per il numero di serie e la versione del sistema operativo.






## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider

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

Selezionare **Confirm > Restart Now** per completare l'operazione. Dopo il riavvio del dispositivo, vai a Impostazioni **> Aggiornamento & sicurezza > verificare** la disponibilità di aggiornamenti per ottenere la build più recente.

### <a name="update-error-0x80070490-work-around"></a>Aggiornamento degli errori 0x80070490 risolvere il problema
Se si verifica un errore di aggiornamento 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a eseguire le operazioni seguenti a breve termine. Si tratta di spostare il canale Insider, raccogliere l'aggiornamento e quindi spostare di nuovo il canale Insider.

#### <a name="stage-one---release-preview"></a>Passaggio 1 - Versione di anteprima
1.  Impostazioni, Aggiornamento & Sicurezza, Programma Windows Insider, seleziona **Canale di anteprima versione.**
2.  Settings, Update & Security, Windows Update, **Check for updates.** Dopo l'aggiornamento, passare al passaggio 2.

#### <a name="stage-two---dev-channel"></a>Fase due - Dev Channel
1. Impostazioni, Update & Security, Programma Windows Insider, seleziona **Dev Channel.**
2. Settings, Update & Security, Windows Update, **Check for updates.**

## <a name="ffu-download-and-flash-directions"></a>Indicazioni stradali per il download e il flash FFU
Per eseguire il test con una versione di anteprima firmata ffu, devi prima sbloccare il dispositivo prima di lampeggiare la versione di anteprima firmata ffu.
1. Nel PC:

    1. Scarica ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installare ARC (Advanced Recovery Companion) da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. On HoloLens - Flight Unlock: Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up, reboot device.

1. Flash FFU: ora puoi lampeggiare la versione di anteprima firmata FFU usando ARC.

## <a name="provide-feedback-and-report-issues"></a>Inviare commenti e suggerimenti e segnalare i problemi

Usa [l'app Hub di Feedback](hololens-feedback.md) in HoloLens per fornire feedback e segnalare i problemi. L'uso di Hub di Feedback garantisce che tutte le informazioni di diagnostica necessarie siano incluse per aiutare i tecnici a eseguire rapidamente il debug e risolvere il problema.  I problemi con la versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurati di accettare la richiesta che ti chiede se vuoi che Hub di Feedback accedono alla cartella Documenti (seleziona **Sì** quando richiesto).

## <a name="note-for-developers"></a>Nota per gli sviluppatori

Sei il benvenuto e ti incoraggi a provare a sviluppare le tue applicazioni con le build Insider di HoloLens.  Per iniziare, consultare la documentazione per sviluppatori [di HoloLens.](https://developer.microsoft.com/windows/mixed-reality/development) Queste stesse istruzioni funzionano con le build Insider di HoloLens.  Puoi usare le stesse build di Unity e Visual Studio già in uso per lo sviluppo di HoloLens.

## <a name="stop-receiving-insider-builds"></a>Interrompere la ricezione delle build Insider

Se non vuoi più ricevere build Insider di Windows Holographic, puoi rifiutare esplicitamente quando HoloLens esegue una build di produzione oppure puoi ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo in una versione non Insider di Windows Holographic. [](hololens-recovery.md)

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che annullano la registrazione alle build di Insider Preview dopo aver reinstallato manualmente una nuova build di anteprima visualizzano una schermata blu. Successivamente devono ripristinare manualmente il dispositivo. Per informazioni dettagliate su se l'utente sarebbe stato o meno in grado di verificarsi, consultare altre informazioni su [questo problema noto.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Per verificare che HoloLens ese in esecuzione una build di produzione:

1. Vai a **Impostazioni > sistema > informazioni su**e trova il numero di build.

1. [Vedi le note sulla versione per i numeri di build di produzione.](hololens-release-notes.md)

Per rifiutare esplicitamente le build Insider:

1. In un HoloLens che esegue una build di produzione, vai a Impostazioni **> Update & Security > Windows Insider Program**e seleziona Interrompi build **Insider.**

1. Segui le istruzioni per rifiutare esplicitamente il dispositivo.
