---
title: Insider Preview per Microsoft HoloLens
description: Informazioni su come iniziare a usare le build Insider e fornire feedback preziosi per il prossimo aggiornamento principale del sistema operativo per HoloLens.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ebd3992458daa94726e73742b1fba4d7fa97a48b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309603"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuti nelle build insider preview più recenti per HoloLens. È semplice iniziare e [fornire feedback](hololens-insider.md#start-receiving-insider-builds) utili per il prossimo aggiornamento principale del sistema operativo per HoloLens.

## <a name="windows-insider-release-notes"></a>partecipante al Programma Windows Insider sulla versione

Siamo molto contenti di iniziare a eseguire nuovamente il volo di nuove funzionalità per Windows Insiders. Per gli aggiornamenti più recenti, le nuove build verranno aggiornate in Dev Channel. Questa pagina continuerà ad essere aggiornata quando si aggiungono altre funzionalità e aggiornamenti alle partecipante al Programma Windows Insider build.  Prepararsi a combinare questi aggiornamenti nella realtà.

Questo aggiornamento delle funzionalità contiene le funzionalità per due destinatari. Funzionalità che possono essere usate da chiunque in un dispositivo dall'utente finale e nuove opzioni di gestione dei dispositivi che possono essere configurate dagli amministratori IT. La tabella delle funzionalità seguente specifica i destinatari con cui è possibile usare ogni nuova funzionalità. Se si è un amministratore IT, vedere l'elenco di controllo per l'aggiornamento dell'amministratore [IT](#it-admin---update-checklist)

> [!IMPORTANT]
> Se in precedenza si usava l'app Impostazioni o l'app Microsoft Edge in modalità tutto schermo, queste app sono state sostituite con nuove app che usano un ID app diverso. Di seguito è consigliabile leggere [Le nuove funzionalità AUMID per le nuove app in modalità tutto schermo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) In questo modo si continuerà a avere l'app Impostazioni nel chiosco multimediale o si includerà la nuova app Microsoft Edge app.

<br>

| Nome funzionalità                                              | Breve descrizione                                                                      | Destinatari | Disponibile nella compilazione |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Nuovo Microsoft Edge](#introducing-the-new-microsoft-edge) | Il nuovo modello basato su Chromium Microsoft Edge ora disponibile per HoloLens 2                         | Utente finale | 20279.1006 |
| [Visualizzatore WebXR e 360](#webxr-and-360-viewer)             | Provare esperienze Web immersive e riproduzione di video a 360 minuti                                           | Utente finale | 20289.1000 |
| [Nuova app Impostazioni](#new-settings-app)                     | L'app impostazioni legacy verrà sostituita da una versione aggiornata con nuove funzionalità e impostazioni | Utente finale | 20279.1006 |
| [Calibrazione dei colori dello schermo](#display-color-calibration)   | Selezionare un profilo colori alternativo per la HoloLens 2 schermo                                | Utente finale | 20293.1000 |
| [Selezione app predefinita](#default-app-picker)                 | Scegliere l'app da avviare per ogni tipo di file o collegamento                                      | Utente finale | 20279.1006 |
| [Controllo del volume per app](#per-app-volume-control) |  Controllare il volume a livello di app indipendentemente dal volume di sistema | Utente finale | 20293.1000 |
| [App Web di Office](#office-web-app)                         | Un collegamento all'app Web di Office è ora elencato in "Tutte le app"                                   | Utente finale | 20279.1006 |
| [Scorrimento rapido fino al tipo](#swipe-to-type)                           | Usare la punta del dito per "scorrere" le parole sulla tastiera olografica                        | Utente finale | 20279.1006 |
| [Menu Di alimentazione da Start](#power-menu-from-start) | Nel menu Start riavviare e arrestare il dispositivo HoloLens | Utente finale | 20293.1000 |
| [Più utenti elencati nella schermata di accesso](#multiple-users-listed-on-sign-in-screen) | Visualizzare più account utente nella schermata di accesso | Utente finale | 20293.1000 |
| [Supporto microfono esterno USB-C](#usb-c-external-microphone-support) | Usare i microfoni USB-C per app e/o Remote Assist.| Utente finale | 20279.1006 |
| [Accesso automatico dei visitatori per chioschi in modalità tutto schermo](#visitor-auto-logon-for-kiosks)                          | Abilita l'accesso automatico sugli account Visitor da usare per le modalità tutto schermo.                         | Amministratore IT | 20279.1006                 |
| [Nuovi AUMID per le nuove app in modalità tutto schermo](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMID per le nuove impostazioni e le app Edge | Amministratore IT | 20279.1006 |
| [Miglioramento della distribuzione degli errori in modalità tutto schermo](#kiosk-mode-behavior-changes-for-handling-of-failures) | La modalità tutto schermo cerca Accesso assegnato globale prima del menu Start vuoto. | Amministratore IT | 20279.1006 |
| [Nuove impostazioniURI per la visibilità delle impostazioni della pagina](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | Oltre 20 nuove impostazioniURI per i criteri Settings/PageVisibilityList | Amministratore IT | 20289.1000 |
| [Configurare la diagnostica di fallback](#configuring-fallback-diagnostics-via-settings-app) | Impostazione del comportamento di diagnostica di fallback nell'app Impostazioni | Amministratore IT | 20279.1006 |
| [Condividere elementi con dispositivi nelle vicinanze](#share-things-with-nearby-devices) | Condividere file o URL da un dispositivo HoloLens a un PC | Tutti | 20279.1006 |
| [Nuovo strumento di risoluzione dei problemi di aggiornamento del sistema operativo](#new-os-update-troubleshooter) | Nuovo strumento di risoluzione dei problemi in Impostazioni per gli aggiornamenti del sistema operativo | Amministratore IT | 20279.1006 |
| [Ottimizzazione recapito anteprima](#delivery-optimization-preview) | Ridurre il consumo di larghezza di banda per i download da più dispositivi HoloLens | Amministratore IT | 20301.1000 |
| [Miglioramenti e correzioni nell'aggiornamento](#improvements-and-fixes-in-the-update) | Correzioni aggiuntive nell'aggiornamento. | Tutti | 20279.1006 |

### <a name="it-admin---update-checklist"></a>Amministratore IT - Elenco di controllo aggiornamenti

Questo elenco di controllo consente di conoscere i nuovi elementi aggiunti in questo aggiornamento delle funzionalità che potrebbero influire sulle configurazioni correnti di gestione dei dispositivi o sulle nuove funzionalità che si potrebbe voler iniziare a usare.

#### <a name="updates-to-kiosk-mode"></a>Aggiornamenti alla modalità tutto schermo

[**Nuovi AUMID per le nuove app in modalità tutto schermo**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Se in precedenza si usava l'app Impostazioni o l'app Microsoft Edge in modalità tutto schermo, queste app sono state sostituite con nuove app che usano un ID app diverso. Di seguito è consigliabile leggere [Le nuove funzionalità AUMID per le nuove app in modalità tutto schermo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) In questo modo si continuerà a avere l'app Impostazioni nel chiosco multimediale o si includerà la nuova app Microsoft Edge app.

Queste modifiche possono essere eseguite ora e distribuite in tutti i dispositivi e consentono una transizione più agevole all'aggiornamento.

[**Accesso automatico dei visitatori per chioschi in modalità tutto schermo**](#visitor-auto-logon-for-kiosks)

I visitatori possono ora accedere automaticamente a un chiosco multimediale. Questo comportamento è attivata per impostazione predefinita, ma può essere gestita e disabilitata.

[**Miglioramento della distribuzione degli errori in modalità tutto schermo**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Se l'appartenenza al gruppo AAD dell'utente AAD connesso non viene determinata correttamente, viene usata la configurazione globale della modalità tutto schermo per il menu Start (se presente) in caso contrario all'utente viene visualizzato un menu Start vuoto. Anche se il menu Start vuoto non è una configurazione che è possibile impostare direttamente, questa nuova gestione potrebbe essere qualcosa di cui informare il reparto di supporto se si usano i chioschi in modalità tutto schermo, in quanto ciò potrebbe essere applicabile alle configurazioni o potrebbe essere necessario apportare nuove modifiche alle configurazioni di accesso assegnate.

#### <a name="updates-to-page-settings-visibility"></a>Aggiornamenti alla visibilità delle impostazioni di pagina

[**Nuove impostazioniURIs per la visibilità delle impostazioni di pagina**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

Se si usa la [visibilità delle impostazioni](settings-uri-list.md) di pagina, è possibile apportare modifiche agli URI esistenti consentiti o bloccati.

#### <a name="updates-for-your-wdac-policy"></a>Aggiornamenti per i criteri WDAC

Se in precedenza si bloccavano Microsoft Edge tramite WDAC, è necessario aggiornare i criteri WDAC. Esaminare [quanto segue e](#using-wdac-to-block-new-microsoft-edge) usare il codice di esempio fornito.

#### <a name="enable-new-endpoints-for-edge"></a>Abilitare nuovi endpoint per Edge

Se si dispone di un'infrastruttura che prevede la configurazione di endpoint di rete, ad esempio proxy o firewall, abilitare questi nuovi endpoint per la nuova [app Microsoft Edge rete.](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>Elementi appena configurabili

- [Configurare la diagnostica di fallback](#configuring-fallback-diagnostics-via-settings-app)
  - È possibile configurare se e chi può raccogliere la diagnostica di fallback.
- [Condividere elementi con dispositivi nelle vicinanze](#share-things-with-nearby-devices)
  - È possibile disabilitare la nuova funzionalità di condivisione nelle vicinanze.
- [Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Esaminare le nuove configurazioni disponibili per Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nuovo strumento di diagnostica

- [Nuovo strumento di risoluzione dei problemi di aggiornamento del sistema operativo](#new-os-update-troubleshooter)
  - Raccogliere i log correlati agli aggiornamenti del sistema operativo

### <a name="introducing-the-new-microsoft-edge"></a>Introduzione al nuovo Microsoft Edge

![Animazione del logo Microsoft Edge legacy al nuovo logo Microsoft Edge](images/new-edge.gif)

Il nuovo Microsoft Edge adotta il progetto [Chromium open source](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) per creare una migliore compatibilità per i clienti e una minore frammentazione del Web per gli sviluppatori Web.

Con questa anteprima Insider, il nuovo Microsoft Edge è disponibile per HoloLens 2 clienti per la prima volta. Anche se il nuovo Microsoft Edge sostituirà i Microsoft Edge legacy HoloLens 2, entrambi i browser sono attualmente disponibili per i insider. Condividere commenti e suggerimenti e bug con il team tramite la funzionalità **Invia commenti** e suggerimenti nel nuovo Microsoft Edge o [tramite Hub di Feedback](hololens-feedback.md).

![Screenshot Microsoft Edge nuova versione](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Avvio del nuovo Microsoft Edge

Sono disponibili due versioni di Microsoft Edge per i insider: la nuova icona Microsoft Edge nuova Microsoft Edge (rappresentata da un'icona a scorrimento blu e verde) e la Microsoft Edge legacy (rappresentata dall'icona ![ ](images/new_edge_logo.png) "e" bianca). Il nuovo Microsoft Edge viene aggiunto al menu Start e verrà avviato automaticamente quando si attiva un collegamento Web. Se si vuole ripristinare l'uso di Microsoft Edge legacy come Web browser predefinito, vedere le istruzioni seguenti per la reimpostazione [delle app predefinite.](#default-app-picker)

> [!NOTE]
> Quando si avvia per la prima volta la nuova Microsoft Edge in HoloLens 2, le impostazioni e i dati verranno importati da Microsoft Edge. Se si continua a usare i Microsoft Edge legacy dopo l'avvio del nuovo Microsoft Edge, i nuovi dati non verranno sincronizzati dai dati Microsoft Edge legacy al nuovo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge

Il nuovo Microsoft Edge offre agli amministratori IT un set molto più ampio di criteri del browser HoloLens 2 rispetto a quelli disponibili in precedenza con le versioni Microsoft Edge.

Ecco alcune risorse utili per altre informazioni sulla gestione delle impostazioni dei criteri per il nuovo Microsoft Edge:

- [Configurare Microsoft Edge impostazioni dei criteri con Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Versione legacy di Microsoft Edge mapping Microsoft Edge criteri](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapping dei criteri da Google Chrome a Microsoft Edge criteri](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentazione [completa Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> A causa del volume di criteri del browser supportati dal nuovo Microsoft Edge, il team non è in grado di garantire che ogni nuovo criterio funzioni HoloLens 2. Tuttavia, sono stati testati e confermati rispetto al nuovo Microsoft Edge equivalente di ogni criterio Microsoft Edge legacy supportato in precedenza HoloLens 2 funzionano come previsto. Vedere [Versione legacy di Microsoft Edge per Microsoft Edge mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) dei criteri per trovare il nuovo Microsoft Edge equivalente di ogni criterio Microsoft Edge browser legacy in uso con HoloLens 2.
>
> Esistono almeno due nuovi criteri Microsoft Edge che non *funzionano* con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Cosa aspettarsi dalla nuova Microsoft Edge in HoloLens 2

Poiché il nuovo Microsoft Edge è un'app Win32 nativa con un nuovo livello di adapter UWP che ne consente l'esecuzione in dispositivi solo UWP come HoloLens 2, alcune funzionalità potrebbero non essere immediatamente disponibili. Nei prossimi mesi verranno supportati nuovi scenari e funzionalità, quindi controllare questo spazio per informazioni aggiornate.

**Scenari e funzionalità previsti per il funzionamento:**
- Esperienza di prima esecuzione, accesso al profilo e sincronizzazione
- I siti Web devono eseguire il rendering e comportarsi come previsto
- La maggior parte delle funzionalità del browser (Preferiti, Cronologia e così via) dovrebbe funzionare come previsto
- Modalità scura
- Installazione di app Web nel dispositivo
- Installazione delle estensioni (determinare se si usano estensioni che non funzionano correttamente in HoloLens 2)
- Visualizzazione e contrassegno di un PDF
- Audio spaziale da una singola finestra del browser
- Aggiornamento automatico e manuale del browser
- Salvataggio di un file PDF dal menu Stampa (usando l'opzione "Salva in PDF")
- Estensione WebXR e visualizzatore 360
- Ripristino del contenuto nella finestra corretta, quando si esplorano più finestre posizionate nell'ambiente

**Scenari e funzionalità che non dovrebbero funzionare:**
- Audio spaziale da più finestre con flussi audio simultanei
- "See it, say it"
- Stampa

**Principali problemi noti del browser:**
- Wi-Fi configurazioni proxy, ovvero criteri proxy che hanno come destinazione singole connessioni Wi-Fi, non funzionano attualmente con il nuovo Microsoft Edge. Microsoft sta lavorando attivamente per sbloccare questo problema prima del rilascio pubblico dell'aggiornamento del sistema operativo.
- L'anteprima della lente di ingrandimento nella tastiera olografica è stata disabilitata per il nuovo Microsoft Edge. Ci auguriamo di poter riabilitare questa funzionalità in un aggiornamento futuro, una volta che l'ingrandimento funziona correttamente.
- Due caratteri sulla tastiera giapponese non funzionano come previsto nella nuova Microsoft Edge. Questo problema è stato causato dalla radice e dovrebbe essere risolto a breve.
- I collegamenti Web nell Microsoft Store app potrebbero non avviare il browser
- L'audio può essere riprodotto dalla finestra del browser errata se è aperta e attiva un'altra finestra del browser. È possibile risolvere questo problema chiudendo l'altra finestra attiva che non dovrebbe riprodurre l'audio.
- Quando si riproduce l'audio da una finestra del browser in modalità ["Seguimi",](hololens2-basic-usage.md#follow-me-stop-following)l'audio continuerà a essere riprodotto se si disabilita la modalità "Seguimi". È possibile risolvere questo problema interrompendo la riproduzione audio prima di disabilitare la modalità "Seguimi" o chiudendo la finestra con il **pulsante X.**
- L'interazione con le finestre Microsoft Edge attive può causare l'inattività imprevista di altre finestre dell'app 2D. È possibile riattivare queste finestre interagendo di nuovo con esse.
- L'apertura di un collegamento Web da un'altra app o di determinati tipi di documenti, ad esempio pdf, può causare l'apertura di una seconda scheda vuota nel browser (oltre alla nuova scheda creata con il contenuto del collegamento Web o del collegamento file). È possibile risolvere questo problema chiudendo la scheda vuota aggiuntiva.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge insider

Il team Microsoft Edge rende disponibili tre canali di anteprima per la community di Edge Insider: Beta, Dev e Canary. L'installazione di un canale di anteprima non disinstalla la versione rilasciata di Microsoft Edge nel HoloLens 2 ed è possibile installarne più di una contemporaneamente. 

Visitare la [home page Microsoft Edge Insider per](https://www.microsoftedgeinsider.com) altre informazioni sulla community di Edge Insider. Per altre informazioni sui diversi canali Edge Insider e per iniziare, visitare la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)

Sono disponibili due metodi per l'installazione di Microsoft Edge Insider per HoloLens 2:

**Installazione diretta nel dispositivo (attualmente disponibile solo per i dispositivi non gestiti)**
  1. Nel HoloLens 2, visitare la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Selezionare il **pulsante Download for HoloLens 2** per il canale Edge Insider che si vuole installare.
  1. Avviare il file msix scaricato dalla coda di download edge o dalla cartella "Download" del dispositivo (usando Esplora file).
  1. [Verrà avviato il programma](app-deploy-app-installer.md) di installazione dell'app.
  1. Selezionare il pulsante **Installa**.
  1. Al termine dell'installazione, sarà possibile trovare Microsoft Edge Beta, Dev o Canary come voce separata nell'elenco Tutte le app del menu Start. 

**Eseguire l'installazione tramite PC Portale di dispositivi di Windows (è [necessario che la modalità sviluppatore](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) sia abilitata HoloLens 2)**
  1. Nel PC visitare la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Selezionare il **pulsante freccia a discesa** accanto al pulsante "Download for Windows 10" (Scarica per Windows 10) per il canale Edge Insider che si vuole installare.
  1. Selezionare **HoloLens 2** nel menu a discesa.
  1. Salvare il file con estensione msix nella cartella "Download" del PC (o in un'altra cartella facilmente individuabile).
  1. Usare [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) nel PC per installare il file msix scaricato HoloLens 2.
  1. Al termine dell'installazione, sarà possibile trovare Microsoft Edge Beta, Dev o Canary come voce separata nell'elenco Tutte le app del menu Start. 

> [!NOTE]
> Durante questa partecipante al Programma Windows Insider anteprima per HoloLens 2, la versione di Microsoft Edge nel dispositivo potrebbe essere superiore a quella disponibile in alcuni o in tutti i canali insider Microsoft Edge. In questo modo si garantisce che le nuove funzionalità e le correzioni specifiche per il Web browser HoloLens 2 siano disponibili per i partecipanti al Programma Windows Insider il più rapidamente possibile. Subito dopo il rilascio pubblico del prossimo aggiornamento di Windows, le compilazioni del canale Microsoft Edge Insider supereranno e resteranno in anticipo rispetto alla versione di Microsoft Edge nel HoloLens 2.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso di WDAC per bloccare nuovi Microsoft Edge

Per gli amministratori IT che desiderano aggiornare i criteri [WDAC](windows-defender-application-control-wdac.md) per bloccare la nuova app Microsoft Edge, è necessario aggiungere quanto segue al criterio.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gestione degli endpoint per il nuovo Microsoft Edge

Alcuni ambienti possono avere restrizioni di rete da tenere in considerazione. Per garantire un'esperienza ottimale con il nuovo edge, [abilitare questi endpoint Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Altre informazioni sugli endpoint attualmente [disponibili per HoloLens.](hololens-offline.md)

### <a name="webxr-and-360-viewer"></a>Visualizzatore WebXR e 360

*Aggiunta in partecipante al Programma Windows Insider build 20289.1000*

La nuova Microsoft Edge include il supporto per WebXR, che è il nuovo standard per la creazione di esperienze Web immersive (sostituendo WebVR). Molte esperienze Web immersive sono state progettate con la realtà virtuale (sostituiscono il campo di visualizzazione con un ambiente virtuale), ma queste esperienze sono supportate anche da HoloLens 2. Lo standard WebXR consente anche esperienze Web immersive di realtà aumentata e mista che usano l'ambiente fisico. Poiché gli sviluppatori dedicano più tempo a WebXR, prevediamo che arriveranno nuove esperienze immersive di realtà aumentata e mista che i clienti HoloLens 2 provare.

L'estensione 360 Viewer è compilata su WebXR e viene installata automaticamente insieme al nuovo Microsoft Edge in HoloLens 2. Questa estensione Web offre la possibilità di immersi in video a 360 gradi. YouTube offre la selezione più ampia di 360 video, quindi è necessario iniziare da qui.

#### <a name="how-to-use-webxr"></a>Come usare WebXR

1. Passare a un sito Web con supporto WebXR.
1. Selezionare il **pulsante Enter VR (Immetti VR)** nel sito Web. La posizione e la rappresentazione visiva di questo pulsante possono variare per ogni sito Web, ma può essere simile a:

    ![Immettere l'esempio di pulsante VR](images/75px-enter-vr.png)

1. La prima volta che si tenta di avviare un'esperienza WebXR in un dominio specifico, il browser chiederà il consenso per immettere una visualizzazione immersiva, selezionare **Consenti**.
1. Usare [HoloLens 2 movimenti per](hololens2-basic-usage.md#the-hand-tracking-frame) modificare l'esperienza.
1. Se l'esperienza non ha un pulsante **Esci,** usare il [movimento Avvia](hololens2-basic-usage.md#start-gesture) per tornare a casa.

**Esempi di WebXR consigliati**
- Visualizzatore 360 (vedere la sezione successiva)
- [Dinosauri XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Come usare il visualizzatore 360

1. Passare a un video a 360 gradi su YouTube.
1. Nel fotogramma video selezionare il pulsante visore VR di realtà mista:

    ![Pulsante per attivare il visualizzatore 360](images/enter-360-viewer.jpg)

1. La prima volta che si prova ad avviare 360 Viewer in un dominio specifico, il browser chiederà il consenso per accedere a una visualizzazione immersiva. selezionare **Consenti**.
1. [Tocco per](hololens2-basic-usage.md#select-using-air-tap) visualizzare i controlli di riproduzione. Usa [i raggi della](hololens2-basic-usage.md#select-using-air-tap) mano e il tocco dell'aria per riprodurre/sospendere, ignorare avanti/indietro, attivare/disattivare i sottotitoli o arrestare l'esperienza (che esce dalla visualizzazione immersiva). I controlli di riproduzione scompariranno dopo alcuni secondi di inattività.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principali problemi noti di WebXR e 360 Viewer
- A seconda della complessità dell'esperienza WebXR, la frequenza dei frame può essere notevolmente più complessa.
- Il supporto per le giunzioni delle mani articolate in WebXR non è abilitato per impostazione predefinita. Gli sviluppatori possono abilitare il `edge://flags` supporto tramite attivando "WebXR Hand Input".
- Quando si esce da un'esperienza WebXR o 360 Viewer, la visualizzazione degli ologrammi nel ambiente iniziale potrebbe richiedere più di 30 secondi.
- 360 video da siti Web diversi da YouTube potrebbero non funzionare come previsto.
- Le didascalie sono attualmente disabilitate nel visualizzatore 360 HoloLens 2. Si prevede di abilitare questa funzionalità in un aggiornamento futuro.
- La sospensione di un video in 360 Viewer arresta il rendering del video ,ma selezionando il pulsante di riproduzione viene ripresa correttamente la riproduzione.
- Il pulsante "video successivo" nel visualizzatore 360 non funziona attualmente.
- È possibile riprodurre video 2D in modalità "teatro" immersiva, ma la frequenza dei fotogrammi può essere inferiore a 30 fps.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornire commenti e suggerimenti su WebXR e 360 Viewer

Condividere commenti e suggerimenti e bug con il team tramite la funzionalità **Invia commenti** e suggerimenti nel nuovo Microsoft Edge.

### <a name="new-settings-app"></a>Nuova app Impostazioni

Questa versione introduce una nuova versione dell'app Impostazioni. La nuova app Impostazioni include nuove funzionalità e impostazioni espanse per HoloLens 2 nelle aree seguenti: Audio, Sospensione di Power &, Rete & Internet, App, Account, Accessibilità e altro ancora.

> [!NOTE]
> Poiché la nuova app Impostazioni è distinta dall'app Impostazioni legacy, tutte le finestre Impostazioni posizionate in precedenza nell'ambiente verranno rimosse al momento dell'aggiornamento.

![Home page dell'app Nuove impostazioni](images/new-settings-app.png)

**Nuove funzionalità e impostazioni**
- Ricerca impostazioni: cercare le impostazioni dalla home page impostazioni usando parole chiave o il nome dell'impostazione.
- Suono > sistema:
  - Dispositivi audio di input e output: scegliere in modo indipendente i dispositivi audio di input e output( ad esempio, ascoltare l'audio tramite le cuffia Bluetooth o usare un microfono USB-C per l'input audio).
    > [!NOTE]
    > I microfoni Bluetooth non sono supportati da HoloLens 2.
  - Volume dell'app: regolare in modo indipendente il volume di ogni app. Vedere [controllo del volume per ogni app.](#per-app-volume-control)
- Sistema > alimentazione & sospensione: scegliere quando il dispositivo deve andare in sospensione dopo un periodo di inattività.
- Batteria > di sistema: abilitare manualmente la risparmio batteria o impostare una soglia della batteria a quel punto risparmio batteria si attiva automaticamente.
- Dispositivi > USB: è possibile disabilitare le connessioni USB per impostazione predefinita.
- Rete & Internet:
  - Le schede Ethernet USB-C verranno ora visualizzate in Rete & Internet.
  - Sono ora disponibili le impostazioni della scheda Ethernet USB-C, incluso il relativo indirizzo IP.
  - È ora possibile abilitare la modalità aereo HoloLens 2.
- App: è possibile reimpostare le app predefinite usate per i tipi di file e collegamenti. Per altre informazioni, vedere [Selezione app predefinita.](#default-app-picker)
- Account > altri utenti: i proprietari dei dispositivi possono aggiungere utenti, aggiornare gli utenti standard ai proprietari dei dispositivi, effettuare il downgrade dei proprietari di dispositivi agli utenti standard e rimuovere gli utenti.
- Accessibilità: modificare le dimensioni del testo e alcuni effetti visivi.

**Problemi noti**
- Le finestre Impostazioni posizionate in precedenza verranno rimosse (vedere la nota precedente).
- Non è più possibile rinominare il dispositivo con l'app Impostazioni. Gli amministratori IT possono rinominare i dispositivi usando il [modello Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot) per HoloLens 2 o il nodo MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- La pagina Ethernet mostra sempre un dispositivo Ethernet virtuale ("UsbNcm").
- L'utilizzo della batteria per il nuovo Microsoft Edge potrebbe non essere accurato, a causa della sua natura come applicazione desktop Win32 supportata da un livello adattatore UWP (non è prevista alcuna correzione a breve).

### <a name="display-color-calibration"></a>Calibrazione dei colori dello schermo

*Aggiunta in partecipante al Programma Windows Insider build 20293.1000*

Con questa nuova impostazione è possibile selezionare un profilo colori alternativo per la HoloLens 2 schermo. In questo modo i colori possono risultare più accurati, in particolare a livelli di luminosità inferiori dello schermo. La calibrazione dei colori dello schermo è disponibile nell'app Impostazioni, nella pagina > Calibrazione.

> [!NOTE]
> Poiché questa impostazione salva un nuovo profilo colori nel firmware di visualizzazione, si tratta di un'impostazione per dispositivo (e non univoca per ogni account utente).

#### <a name="how-to-use-display-color-calibration"></a>Come usare la calibrazione dei colori di visualizzazione

1. Avviare **l'app Impostazioni** e passare a **Calibrazione > sistema**.
1. In **Calibrazione colori visualizzazione** selezionare il pulsante Esegui **calibrazione** colori visualizzazione.
1. Verrà avviata l'esperienza di calibrazione del colore dello schermo e si consiglia di assicurarsi che la visiera sia nella posizione corretta.
1. Dopo aver proceduto con le finestre di dialogo delle istruzioni, la luminosità dello schermo verrà automaticamente ridotta al 30%.
    > [!TIP]
    > Se si verificano problemi con la visualizzazione della scena in grigio nell'ambiente, è possibile regolare manualmente il livello di luminosità di HoloLens 2 usando i pulsanti di luminosità sul lato sinistro del dispositivo.
1. Selezionare i pulsanti da 1 a 6 per provare immediatamente ogni profilo di colore e trovarne uno che sia più adatto agli occhi (questo in genere significa che il profilo che consente alla scena di apparire più neutro, con il modello in scala di grigi e i toni della pelle che sembrano come previsto).

    ![Visualizzare la scena di calibrazione dei colori](images/color-cal-ui.png)
    
1. Quando si è soddisfatti del profilo selezionato, selezionare il pulsante Salva & **Esci**
1. Se si preferisce non apportare modifiche, selezionare il pulsante **Annulla & Esci** e le modifiche verranno ripristinate

> [!TIP]
> Ecco alcuni suggerimenti utili da tenere presenti durante l'uso dell'impostazione di calibrazione del colore dello schermo:
> - È possibile eseguire di nuovo la calibrazione del colore di visualizzazione da Impostazioni ogni volta che si desidera
> - Se qualcuno nel dispositivo ha usato in precedenza l'impostazione per modificare i profili colori, la data/ora della modifica più recente verrà riflessa nella pagina Impostazioni
> - Quando si esegue di nuovo la calibrazione dei colori dello schermo, il profilo colori salvato in precedenza verrà evidenziato e il profilo 0 non verrà visualizzato (poiché il profilo 0 rappresenta il profilo colori originale dello schermo)
> - Se si vuole ripristinare il profilo colori originale dello schermo, è possibile farlo dalla pagina Impostazioni (vedere come reimpostare il [profilo colori)](#how-to-reset-color-profile)

#### <a name="how-to-reset-color-profile"></a>Come reimpostare il profilo colori

Se non si è soddisfatti del profilo colori personalizzato salvato nel HoloLens 2, è possibile ripristinare il profilo colori originale del dispositivo:
1. Avviare **l'app Impostazioni** e passare a **Calibrazione > sistema**.
1. In **Calibrazione colori schermo** selezionare il pulsante Ripristina profilo **colori** predefinito.
1. Quando viene visualizzata la finestra di dialogo, selezionare **Riavvia** se si è pronti per riavviare HoloLens 2 e applicare le modifiche.

#### <a name="top-display-color-calibration-known-issues"></a>Problemi noti di calibrazione del colore di visualizzazione superiore

- Nella pagina Impostazioni la stringa di stato che indica quando è stata modificata l'ultima modifica del profilo colori non sarà aggiornata fino a quando non si ricarica la pagina di Impostazioni.
    - Soluzione alternativa: selezionare un'altra pagina Impostazioni e quindi selezionare nuovamente la pagina Calibrazione.

### <a name="default-app-picker"></a>Selezione app predefinita

Quando si attiva un collegamento ipertestuale o si apre un tipo di file con più di un'app installata che lo supporta, viene visualizzata una nuova finestra che richiede di selezionare l'app installata che deve gestire il tipo di file o collegamento. In questa finestra è anche possibile scegliere di fare in modo che l'app selezionata gestirà il file o il tipo di collegamento "Una sola volta" o "Sempre".

![Finestra di selezione app](images/default-app-picker.png)

Se si sceglie "Sempre" ma in un secondo momento si vuole modificare l'app che gestisce un determinato file o tipo di collegamento, è possibile reimpostare le impostazioni predefinite salvate in **Impostazioni > app**. Scorrere fino alla fine della  pagina e selezionare il pulsante Cancella in "App predefinite per i tipi di file" e/o "App predefinite per i tipi di collegamento". A differenza dell'impostazione simile nei PC desktop, non è possibile reimpostare le impostazioni predefinite dei singoli tipi di file.

### <a name="per-app-volume-control"></a>Controllo del volume per app

In questa fase partecipante al Programma Windows Insider gli utenti della compilazione possono regolare manualmente il livello di volume di ogni app. Ciò consente agli utenti di concentrarsi meglio sulle app necessarie o di ascoltare meglio quando usano più app. Ad esempio, la necessità di disattivare il volume di un'app mentre chiama un'altra persona per assistenza remota in un'altra.

Per impostare il volume di una singola app, passare a Impostazioni Audio del sistema e in Opzioni audio avanzate  ->    ->  selezionare **Volume dell'app e preferenze del dispositivo.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>App Web di Office

>[!NOTE]
>A partecipante al Programma Windows Insider build 20325.1000, l'app Web di Office non sarà più preinstallato e non sarà preinstallato per la prossima versione pubblica dell'aggiornamento del sistema operativo. Per installare l'app Web di Office, visitare https://www.office.com e selezionare il pulsante App **disponibile** o Installa **Office** nella barra degli indirizzi. Selezionare **Installa** per confermare.

L'app Web di Office è stata aggiunta all'elenco "Tutte le app" nel menu Start. Questa app Web può anche essere aggiunta a Start o disinstallata. Poiché si tratta di un'app Web, la relativa funzionalità corrisponde esattamente a quella che si avrebbe visitando https://www.office.com . La funzionalità dell'app Web di Office è disponibile solo HoloLens 2 la connessione Internet attiva.

**Problema noto**
- La reimpostazione del dispositivo rimuoverà l'app Web di Office

### <a name="swipe-to-type"></a>Scorrimento rapido verso il testo

Alcuni clienti trovano più veloce "digitare" sulle tastiere virtuali scorrendo la forma della parola che intende digitare e questa funzionalità è disponibile in anteprima per la tastiera olografica. È possibile scorrere una parola alla volta passando la punta del dito attraverso il piano della tastiera olografica, scorrendo la forma della parola e quindi ritirando la punta del dito dal piano della tastiera. È possibile scorrere rapidamente le parole di follow-up senza dover premere la barra spaziatrice rimuovendo il dito dalla tastiera tra le parole. Si saprà che la funzionalità funziona se viene visualizzata una traccia di scorrimento rapido che segue il movimento del dito sulla tastiera.

Si noti che questa funzionalità può essere difficile da usare e master a causa della natura di una tastiera olografica in cui non si prova resistenza contro il dito (a differenza di un display del telefono cellulare). Questa funzionalità viene valutata per la versione pubblica, quindi i commenti e suggerimenti sono importanti. indipendentemente dal fatto che la funzionalità sia utile o che si abbia un feedback costruttivo, è possibile contattarci [tramite Hub di Feedback](hololens-feedback.md).

### <a name="power-menu-from-start"></a>Menu Di alimentazione da Start

Nuovo menu che consente all'utente di disconnettersi, arrestare e riavviare il dispositivo. Indicatore nell'elenco di schermata Start HoloLens che indica quando è disponibile un aggiornamento del sistema.

#### <a name="how-to-use"></a>Uso

1. Aprire il schermata Start HoloLens usando il [movimento Start](hololens2-basic-usage.md#start-gesture) o pronunciando "Vai a Start".

2. Si noti l'icona con i puntini di sospensione (...) accanto all'immagine del profilo utente:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Selezionare l'immagine del profilo utente usando le mani o il comando vocale "Power".

4. Viene visualizzato un menu con le opzioni Disconnetti, Riavvia o Arresta il dispositivo:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Seleziona le opzioni di menu per disconnettersi, riavviare o arrestare HoloLens. L'opzione Disconnei potrebbe non essere disponibile se il dispositivo è configurato per un singolo [account Microsoft (MSA) o un account locale.](hololens-identity.md)

6. Chiudere il menu toccando un altro punto o chiudendo il menu Start con il movimento Start.

#### <a name="update-indicator"></a>Indicatore di aggiornamento

Quando è disponibile un aggiornamento, l'icona con i puntini di sospensione si accende per indicare che un riavvio installerà l'aggiornamento Le opzioni di menu cambiano anche in base alla presenza dell'aggiornamento.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Più utenti elencati nella schermata di accesso

In precedenza la schermata di accesso mostrava solo l'utente che ha eseguito l'accesso più di recente, oltre a un punto di ingresso "Altro utente". Sono stati ricevuti commenti e suggerimenti dei clienti che non sono sufficienti se più utenti hanno eseguito l'accesso al dispositivo. Era comunque necessario digitare nuovamente il nome utente e così via.

Introdotta in questa build partecipante al Programma Windows Insider,  quando si seleziona Altro utente a destra del campo Immissione PIN, nella schermata Di accesso verranno visualizzati più utenti con accesso al dispositivo eseguito in precedenza. In questo modo gli utenti possono selezionare il proprio profilo utente e quindi accedere usando le Windows Hello credenziali. È anche possibile aggiungere un nuovo utente al dispositivo da questa pagina Altri utenti tramite il **pulsante Aggiungi account.**

Nel menu Altri utenti il pulsante Altri utenti visualizza l'ultimo utente che ha eseguito l'accesso al dispositivo. Selezionare questo pulsante per tornare alla schermata Di accesso per questo utente.

![Impostazione predefinita della schermata di accesso](./images/multiusers1.jpg)

<br>

![Schermata di accesso per altri utenti](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Supporto microfono esterno USB-C

> [!IMPORTANT]
> L'inserimento di un microfono USB non **lo imposta automaticamente come dispositivo di input.** Quando si collega un set di cuffia USB-C, gli utenti osserveranno che l'audio della cuffia verrà reindirizzato automaticamente alle cuffia, ma il sistema operativo HoloLens assegna la priorità all'array di microfoni interni sopra qualsiasi altro dispositivo di input. **Per usare un microfono USB-C, seguire questa procedura.**

Gli utenti possono selezionare microfoni esterni connessi USB-C usando il **pannello Impostazioni** audio. I microfoni USB-C possono essere usati per chiamare, registrare e così via.

Aprire **l'app Impostazioni** e selezionare **Suono di**  >  **sistema**.

![Impostazioni audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Per usare microfoni esterni **con** Remote Assist , gli utenti dovranno fare clic sul collegamento ipertestuale "Gestisci dispositivi audio".
>
> Usare quindi l'elenco a discesa per impostare il microfono esterno come **Predefinito** o **Predefinito per le comunicazioni.** Se **si sceglie Predefinito,** il microfono esterno verrà usato ovunque.
>
> Se **si sceglie Comunicazioni** predefinite, il microfono esterno verrà usato in Remote Assist e in altre app per le comunicazioni, ma l'array di microfoni HoloLens può comunque essere usato per altre attività.

![Gestire i dispositivi audio](images/usbc-mic-2.png)

<br>

![Impostare il microfono predefinito](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Informazioni sul supporto del microfono Bluetooth

Sfortunatamente, i microfoni Bluetooth non sono ancora supportati in HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Risoluzione dei problemi relativi ai microfoni USB-C

Tenere presente che alcuni microfoni USB-C segnalano erroneamente se stessi sia come *microfono che come* altoparlante. Si tratta di un problema con il microfono e non con HoloLens. Quando si collega uno di questi microfoni a HoloLens, l'audio potrebbe essere perso. Fortunatamente è disponibile una semplice correzione.  

In **Impostazioni suono** di sistema impostare in modo esplicito gli altoparlanti predefiniti (driver audio della funzionalità  ->    ->   **analoga)** come **dispositivo predefinito.** HoloLens deve ricordare questa impostazione anche se il microfono viene rimosso e riconnesso in un secondo momento.

![Risoluzione dei problemi relativi ai microfoni USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Accesso automatico del visitatore per chioschi

Questa nuova funzionalità consente di usare l'accesso automatico per gli account visitatore per le modalità tutto schermo.

Per una configurazione non AAD, per configurare un dispositivo per l'accesso automatico dei visitatori:

1. Creare un pacchetto di provisioning che:
    1. Configura le impostazioni **di runtime/AssignedAccess per** consentire gli account Visitor.
    1. Facoltativamente, registra il dispositivo in MDM **(Impostazioni di runtime/Area di lavoro/Registrazioni)** in modo che possa essere gestito in un secondo momento.
    1. Non creare un account locale
1. [Applicare il pacchetto di provisioning](hololens-provisioning.md).

Per una configurazione di AAD, gli utenti possono ottenere oggi un risultato simile a questo senza questa modifica. I dispositivi aggiunti ad AAD configurati per la modalità tutto schermo possono accedere a un account visitatore con un solo pulsante nella schermata di accesso. Dopo l'accesso all'account visitatore, il dispositivo non richiederà di nuovo l'accesso fino a quando il visitatore non viene disconnesso in modo esplicito dal menu Start o il dispositivo non viene riavviato.

L'accesso automatico del visitatore può essere gestito [tramite criteri URI OMA](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) personalizzati:

- Valore URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Criteri  | Descrizione   | Configurazioni  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Consente a un visitatore di accedere automaticamente a un chiosco multimediale   | 1 (Sì), 0 (No, impostazione predefinita).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Usare le nuove app Impostazioni ed Edge in modalità tutto schermo

Quando si includono app in [chioschi,](hololens-kiosk.md)un amministratore IT spesso aggiunge l'app al chiosco multimediale, ma usando l'ID modello utente dell'app (AUMID). Poiché sia l'app Impostazioni che l'app Microsoft Edge sono considerate nuove app e diverse rispetto alle app meno recenti che usano AUMID per tali app, sarà necessario aggiornare per usare la nuova app AUMID.

Quando si modifica un chiosco multimediale per includere le nuove app, è consigliabile aggiungere nel nuovo AUMID e lasciare quella precedente. In questo modo si creerà una transizione semplice quando gli utenti aggiornano il sistema operativo e non sarà necessario ricevere nuovi criteri per continuare a usare la modalità tutto schermo come previsto.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| App impostazioni precedente       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nuova app impostazioni       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| App Microsoft Edge precedente | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nuova app Microsoft Edge app | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifiche del comportamento della modalità tutto schermo per la gestione degli errori

Nelle build precedenti, se un dispositivo ha una configurazione tutto schermo, che è una combinazione di accesso assegnato a livello globale e di accesso assegnato ai membri del gruppo AAD, se la determinazione dell'appartenenza al gruppo AAD non è riuscita, l'utente visualizza " nulla visualizzato nel menu[Start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)".

A partire dalla partecipante al Programma Windows Insider, l'esperienza tutto schermo verrà fallback alla configurazione globale della modalità tutto schermo (se presente) in caso di errori durante la modalità tutto schermo del gruppo AAD.

### <a name="new-settingsuris-for-page-settings-visibility"></a>Nuove impostazioniURIs per la visibilità delle impostazioni di pagina

In [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) sono stati aggiunti i criteri [Impostazioni/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visibili all'interno dell'app Impostazioni. PageVisibilityList è un criterio che consente agli amministratori IT di impedire la visualizzazione o l'accessibilità di pagine specifiche nell'app Impostazioni di sistema oppure di eseguire questa operazione per tutte le pagine tranne quelle specificate.

Se si visita [Visibilità impostazioni pagina](settings-uri-list.md), è possibile trovare le istruzioni per usare questo provider di servizi di configurazione e l'elenco degli URI disponibili nelle versioni precedenti.

Nelle partecipante al Programma Windows Insider compilazioni si espande l'elenco degli URI delle impostazioni disponibili, che gli amministratori IT possono gestire. Alcuni di questi URI sono per le nuove aree disponibili all'interno della nuova app Impostazioni. Se si usano i criteri Settings/PageVisibilityList, esaminare l'elenco seguente e modificare le pagine consentite o bloccate in base alle esigenze.

> [!NOTE]
> **Deprecato: ms-settings:network-proxy**
>
> Una pagina delle impostazioni è deprecata in queste build più nuove. La vecchia **pagina & proxy Internet** non è più disponibile come impostazione  >   globale. Le nuove impostazioni proxy per connessione sono disponibili in Network & Internet Wi-Fi Properties (Proprietà Wi-Fi **Internet)** o Network & Internet Ethernet Properties (Proprietà  >    >     >  **Ethernet**  >  Internet).

<br>

| Pagina Impostazioni                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| App > app & funzionalità                               | `ms-settings:appsfeatures`                         |
| App > app & funzionalità > Opzioni avanzate          | `ms-settings:appsfeatures-app`                     |
| App > mappe offline                                  | `ms-settings:maps`                                 |
| App > mappe offline > download mappe                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivi > mouse                                      | `ms-settings:mouse`                                |
| Dispositivi > USB                                        | `ms-settings:usb`                                  |
| Modalità aereo & Internet > rete                   | `ms-settings:network-airplanemode`                 |
| Privacy > Generale                                    | `ms-settings:privacy-general`                      |
| Privacy e > personalizzazione & input penna             | `ms-settings:privacy-speechtyping`                 |
| Privacy > Motion                                     | `ms-settings:privacy-motion`                       |
| Bordi dello screenshot > privacy                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Screenshot > privacy e app                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batteria > sistema                                     | `ms-settings:batterysaver`                         |
| Batteria > sistema                                     | `ms-settings:batterysaver-settings`                |
| Suono > sistema                                       | `ms-settings:sound`                                |
| System > Sound > Volume app e preferenze del dispositivo | `ms-settings:apps-volume`                          |
| System > Sound > Gestire i dispositivi audio              | `ms-settings:sound-devices`                        |
| Configurazione > archiviazione > di Sensore memoria         | `ms-settings:storagepolicies`                      |
| Ora & lingua > data & ora                        | `ms-settings:dateandtime`                          |
| Tastiera & lingua > tempo                           | `ms-settings:keyboard`                             |
| Ora & lingua > lingua                           | `ms-settings:language`                             |
| Lingua & lingua > lingua                           | `ms-settings:regionlanguage-languageoptions`       |
| Aggiornare & sicurezza > ripristino & ripristino               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URI aggiornati

In precedenza i due URI seguenti non portava un utente direttamente alle pagine indicate, ma bloccava solo la pagina principale degli aggiornamenti. Gli elementi seguenti sono stati aggiornati per indirizzare le pagine:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configurazione della diagnostica di fallback tramite l'app Impostazioni

Nell'app Impostazioni un utente può ora configurare il comportamento di [Diagnostica di fallback.](hololens-diagnostic-logs.md) Nell'app Impostazioni passare alla **pagina Risoluzione dei** problemi  ->  **relativi** alla privacy per configurare questa impostazione.

> [!NOTE]
> Se per il dispositivo sono configurati criteri MDM, l'utente non sarà in grado di eseguire l'override di tale comportamento.  

### <a name="share-things-with-nearby-devices"></a>Condividere elementi con i dispositivi vicini

Condividere le informazioni con dispositivi Windows 10, inclusi PC e altri dispositivi HoloLens 2 che eseguono build HoloLens Insider 20279.1006+. È possibile provarlo in **Impostazioni** Esperienze condivise del sistema per condividere file o URL da  ->    ->   un HoloLens a un PC. Per altri dettagli, leggere altre informazioni su come condividere [elementi con i dispositivi vicini in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Questa funzionalità può essere gestita tramite [Connectivity/AllowConnectedDevices.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-update-troubleshooter"></a>Nuovo strumento di risoluzione dei problemi di aggiornamento del sistema operativo

Oltre ai precedenti strumento di risoluzione dei problemi all'interno dell'app Impostazioni, è stato aggiunto un nuovo strumento di risoluzione dei problemi con l'aggiunta della nuova app Impostazioni per gli aggiornamenti del sistema operativo. Passare a **Impostazioni Aggiorna** risoluzione dei  ->  **problemi &amp; di**  >    >  **Windows Update** e selezionare **Avvia.** In questo modo è possibile raccogliere tracce durante la riproduzione del problema con gli aggiornamenti del sistema operativo per facilitare la risoluzione dei problemi con l'IT o il supporto tecnico.

### <a name="delivery-optimization-preview"></a>Ottimizzazione recapito anteprima

Con questo aggiornamento di HoloLens Insider, Windows Holographic for Business un'anteprima anticipata per le impostazioni di ottimizzazione recapito per ridurre il consumo di larghezza di banda per i download da più dispositivi HoloLens. Una descrizione più completa di questa funzionalità insieme alla configurazione di rete consigliata è disponibile qui: Ottimizzazione recapito [per Windows 10 aggiornamenti](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Le impostazioni seguenti sono abilitate come parte dell'area di gestione e [possono essere configurate da Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

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
- Windows Holographic for Business supporta solo le modalità di download HTTP e i download da un [endpoint cache connessa Microsoft](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). Le modalità di download peer-to-peer e le assegnazioni di gruppo non sono attualmente supportate per i dispositivi HoloLens.
- HoloLens non supporta l'ottimizzazione della distribuzione o del recapito Windows Server Update Services endpoint.
- La risoluzione dei problemi richiederà la diagnostica nel server cache connessa o la raccolta di una traccia in HoloLens in HoloLens tramite l'aggiornamento delle impostazioni & Risoluzione dei problemi di  >    >     >   **sicurezza Windows Update**.

### <a name="improvements-and-fixes-in-the-update"></a>Miglioramenti e correzioni nell'aggiornamento:

- [La diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics) includerà anche informazioni aggiuntive sul dispositivo per il numero di serie e la versione del sistema operativo.

### <a name="known-issues-and-work-around"></a>Problemi noti e risoluzione dei problemi

#### <a name="pairing-hololens-to-pc"></a>Associazione di HoloLens a PC

Prima della build 20325.1000 di partecipante al Programma Windows Insider, quando un utente aveva impostato le credenziali di associazione in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o [Windows Holographic, versione 2004](hololens-release-notes.md#windows-holographic-version-2004) e aggiornata alle build partecipante al Programma Windows Insider, le credenziali del set precedente per l'associazione di HoloLens al PC ai fini della distribuzione e del debug di app come tramite Visual Studio non funzionavano più. partecipante al Programma Windows Insider build 20325.1000 corregge questo problema e non richiede azioni aggiuntive per riprendere l'uso del portale dei dispositivi.

Gli utenti che hanno lampeggiato il dispositivo con una build [Insider](#ffu-download-and-flash-directions) dovranno ora eseguire il reflash dei dispositivi (alla versione 20325.1000+ o a una build a livello di riga) per associare i dispositivi al PC.

Gli utenti che non si sono registrati in Windows Insider e che riceveranno l'aggiornamento della funzionalità quando è disponibile a livello generale non sono interessati.


## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider

> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
> - Il comando vocale "Riavvia il dispositivo" funziona correttamente. 
> - È anche possibile scegliere il pulsante di riavvio in Impostazioni/Programma Windows Insider.
>
> Si è verificato un bug nel back-end che potrebbe essere stato rilevato e ciò consente di tornare in funzione.

In un dispositivo HoloLens 2 passare a **Impostazioni**  >  **Aggiorna & sicurezza**  >  **Programma Windows Insider** e selezionare **Inizia.** Collegare l'account usato per la registrazione come partecipante al Programma Windows Insider.

Windows Insider sta ora passando ai canali. L'anello veloce diventerà il  **canale di** sviluppo, l'anello lento  diventerà l'Canale beta e l'anello di anteprima della versione diventerà **il canale di anteprima della versione.**   Ecco l'aspetto del mapping:

![partecipante al Programma Windows Insider dei canali](images/WindowsInsiderChannels.png)

Per altre informazioni, vedere Introducing partecipante al Programma Windows Insider Channels on Windows Blogs [(Introduzione partecipante al Programma Windows Insider canali](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nei blog di Windows).

Selezionare quindi **Sviluppo attivo di Windows,** scegliere se si  desidera ricevere Dev **Channel** o build Canale beta ed esaminare le condizioni del programma.

Selezionare **Conferma > Riavvia ora** per completare l'operazione. Dopo il riavvio del dispositivo, passare a Impostazioni **> Aggiornamento & sicurezza > verificare** la disponibilità di aggiornamenti per ottenere la build più recente.

### <a name="update-error-0x80070490-work-around"></a>Risolvere i 0x80070490 errore di aggiornamento
Se si verifica un errore di 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema seguente a breve termine. Comporta lo spostamento del canale Insider, il ritiro dell'aggiornamento e quindi lo spostamento del canale Insider.

#### <a name="stage-one---release-preview"></a>Fase 1 - Versione di anteprima
1.  Impostazioni, Aggiorna & sicurezza, Programma Windows Insider selezionare **Canale di anteprima versione.**
2.  Impostazioni, Aggiorna & sicurezza, Windows Update, **Verifica disponibilità aggiornamenti**. Dopo l'aggiornamento, passare alla fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Canale di sviluppo
1. Impostazioni, Aggiorna & sicurezza, Programma Windows Insider, selezionare **Canale di sviluppo.**
2. Impostazioni, Aggiorna & sicurezza, Windows Update, **Verifica disponibilità aggiornamenti**.

## <a name="ffu-download-and-flash-directions"></a>Istruzioni flash e download FFU
Per testare con un volo firmato ffu, è prima necessario sbloccare il dispositivo prima di lampeggiare il volo firmato ffu.
1. Nel PC:

    1. Scaricare ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installare ARC (Advanced Recovery Companion) dal Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. In HoloLens - Flight Unlock: **aprire** l'aggiornamento delle impostazioni & sicurezza Programma Windows Insider quindi iscriversi  >    >   e riavviare il dispositivo.

1. Flash FFU: ora è possibile eseguire il flash del volo firmato FFU usando ARC.

## <a name="provide-feedback-and-report-issues"></a>Inviare commenti e suggerimenti e segnalare i problemi

Usare [l'app Hub di Feedback app](hololens-feedback.md) in HoloLens per inviare commenti e suggerimenti e segnalare i problemi. L Hub di Feedback garantisce che siano incluse tutte le informazioni di diagnostica necessarie per consentire ai tecnici di eseguire rapidamente il debug e risolvere il problema.  I problemi relativi alla versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurarsi di accettare il prompt che chiede se si desidera Hub di Feedback accedere alla cartella Documenti (selezionare **Sì** quando richiesto).

## <a name="note-for-developers"></a>Nota per gli sviluppatori

Si è invitati a provare a sviluppare applicazioni usando build Insider di HoloLens.  Per iniziare, vedere la documentazione per sviluppatori di [HoloLens.](https://developer.microsoft.com/windows/mixed-reality/development) Queste stesse istruzioni funzionano con le build Insider di HoloLens.  È possibile usare le stesse build di Unity e Visual Studio già in uso per lo sviluppo HoloLens.

## <a name="stop-receiving-insider-builds"></a>Interrompere la ricezione di build Insider

Se non si vogliono più ricevere build Insider di Windows Holographic, è possibile rifiutare esplicitamente [](hololens-recovery.md) quando HoloLens esegue una build di produzione oppure è possibile ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo in una versione non Insider di Windows Holographic.

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che annullano la registrazione dalle build insider preview dopo la reinstallazione manuale di una nuova build di anteprima visualizzano una schermata blu. Successivamente, devono ripristinare manualmente il dispositivo. Per informazioni dettagliate su se si è o meno influenzati, vedere altre informazioni su [questo problema noto.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Per verificare che HoloLens ese sia in esecuzione una build di produzione:

1. Passare a **Impostazioni > sistema > Informazioni su** e trovare il numero di build.

1. [Vedere le note sulla versione per i numeri di build di produzione.](hololens-release-notes.md)

Per rifiutare esplicitamente le build Insider:

1. In un dispositivo HoloLens che esegue una build di produzione, passare a Impostazioni **> Aggiorna**& sicurezza > Programma Windows Insider e selezionare Stop Insider builds (Arresta build **Insider).**

1. Seguire le istruzioni per rifiutare esplicitamente il dispositivo.
