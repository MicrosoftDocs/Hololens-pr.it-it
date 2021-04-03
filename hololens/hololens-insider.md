---
title: Insider Preview per Microsoft HoloLens
description: Scopri come iniziare a usare le build Insider e fornire feedback preziosi per il nostro prossimo aggiornamento del sistema operativo principale per HoloLens.
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
ms.sourcegitcommit: ad725427c2c88e73df2e5753001a26502b2327de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474841"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview per Microsoft HoloLens

Benvenuti nelle ultime build di Insider Preview per HoloLens! È semplice iniziare e [fornire](hololens-insider.md#start-receiving-insider-builds) feedback utili per il prossimo aggiornamento del sistema operativo principale per HoloLens.

## <a name="windows-insider-release-notes"></a>Note sulla versione di Windows Insider

Siamo felici di iniziare di nuovo a eseguire il flighting delle nuove funzionalità per i Windows Insider. Per gli aggiornamenti più recenti, le nuove build verranno in esecuzione sul Canale di sviluppo. Continueremo ad aggiornare questa pagina quando aggiungiamo altre funzionalità e aggiornamenti alle build di Windows Insider.  Prepararsi a combinare questi aggiornamenti nella realtà.

Questo aggiornamento delle funzionalità contiene funzionalità per due gruppi di destinatari. Funzionalità che possono essere usate da chiunque su un dispositivo dall'utente finale e nuove opzioni di gestione dei dispositivi che possono essere configurate dagli amministratori IT. La tabella delle funzionalità seguente specifica i gruppi di destinatari con cui è possibile utilizzare ogni nuova funzionalità. Se sei un amministratore IT, dai un'occhiata all'amministratore [IT - Elenco di controllo per l'aggiornamento](#it-admin---update-checklist)

> [!IMPORTANT]
> Se in precedenza usavi l'app Impostazioni o l'app Microsoft Edge in un chiosco multimediale, queste app sono state sostituite con nuove app che usano un ID app diverso. Ti consigliamo vivamente di leggere Di seguito [nuovi AUMID per le nuove app in modalità tutto schermo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) In questo modo potrai continuare ad avere l'app Impostazioni nel chiosco multimediale o includere la nuova app Microsoft Edge.

<br>

| Nome caratteristica                                              | Descrizione breve                                                                      | Gruppo di destinatari | Disponibile in build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Nuovo Microsoft Edge](#introducing-the-new-microsoft-edge) | Il nuovo Microsoft Edge basato su Chromium è ora disponibile per HoloLens 2                         | Utente finale | 20279.1006 |
| [Visualizzatore WebXR e 360](#webxr-and-360-viewer)             | Provare esperienze Web immersive e riproduzione video a 360                                           | Utente finale | 20289.1000 |
| [Nuova app Impostazioni](#new-settings-app)                     | L'app Impostazioni legacy viene sostituita da una versione aggiornata con nuove funzionalità e impostazioni | Utente finale | 20279.1006 |
| [Calibrazione dei colori dello schermo](#display-color-calibration)   | Selezionare un profilo colori alternativo per il display HoloLens 2                                | Utente finale | 20293.1000 |
| [Selezione app predefinita](#default-app-picker)                 | Scegliere l'app da avviare per ogni tipo di file o collegamento                                      | Utente finale | 20279.1006 |
| [Controllo del volume per app](#per-app-volume-control) |  Controllare il volume a livello di app in modo indipendente dal volume di sistema | Utente finale | 20293.1000 |
| [Office Web App](#office-web-app)                         | Un collegamento all'app Web di Office è ora elencato in "Tutte le app"                                   | Utente finale | 20279.1006 |
| [Scorrimento rapido verso il testo](#swipe-to-type)                           | Usare la punta del dito per "scorrere" le parole sulla tastiera olografica                        | Utente finale | 20279.1006 |
| [Menu Alimentazione da Start](#power-menu-from-start) | Nel menu Start riavvia e arresta il dispositivo HoloLens | Utente finale | 20293.1000 |
| [Più utenti elencati nella schermata di accesso](#multiple-users-listed-on-sign-in-screen) | Visualizzare più account utente nella schermata di accesso | Utente finale | 20293.1000 |
| [Supporto microfono esterno USB-C](#usb-c-external-microphone-support) | Usa i microfoni USB-C per app e/o Assistenza remota.| Utente finale | 20279.1006 |
| [Accesso automatico dei visitatori per chioschi multimediale](#visitor-auto-logon-for-kiosks)                          | Consente di utilizzare l'accesso automatico sugli account dei visitatori per la modalità tutto schermo.                         | Amministratore IT | 20279.1006                 |
| [Nuovi AUMID per le nuove app in modalità tutto schermo](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs per nuove impostazioni e app Edge | Amministratore IT | 20279.1006 |
| [Miglioramento della gestione degli errori in modalità tutto schermo](#kiosk-mode-behavior-changes-for-handling-of-failures) | La modalità tutto schermo cerca Accesso assegnato globale prima del menu start vuoto. | Amministratore IT | 20279.1006 |
| [New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20+ nuovi criteri SettingsURIs for Settings/PageVisibilityList | Amministratore IT | 20289.1000 |
| [Configurare la diagnostica di fallback](#configuring-fallback-diagnostics-via-settings-app) | Impostazione del comportamento di diagnostica di fallback nell'app Impostazioni | Amministratore IT | 20279.1006 |
| [Condividere elementi con i dispositivi nelle vicinanze](#share-things-with-nearby-devices) | Condividere file o URL da un HoloLens a un PC | Tutte | 20279.1006 |
| [Nuovo strumento di risoluzione dei problemi di aggiornamento del sistema operativo](#new-os-update-troubleshooter) | Nuovo strumento di risoluzione dei problemi in Impostazioni per gli aggiornamenti del sistema operativo | Amministratore IT | 20279.1006 |
| [Anteprima ottimizzazione recapito](#delivery-optimization-preview) | Ridurre il consumo di larghezza di banda per i download da più dispositivi HoloLens | Amministratore IT | 20301.1000 |
| [Miglioramenti e correzioni nell'aggiornamento](#improvements-and-fixes-in-the-update) | Correzioni aggiuntive nell'aggiornamento. | Tutte | 20279.1006 |

### <a name="it-admin---update-checklist"></a>Amministratore IT - Elenco di controllo per l'aggiornamento

Questo elenco di controllo ti aiuterà a conoscere i nuovi elementi aggiunti in questo aggiornamento delle funzionalità che potrebbero influire sulle configurazioni correnti di gestione dei dispositivi o sulle nuove funzionalità che potresti voler iniziare a usare.

#### <a name="updates-to-kiosk-mode"></a>Aggiornamenti alla modalità tutto schermo

[**Nuovi AUMID per le nuove app in modalità tutto schermo**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Se in precedenza usavi l'app Impostazioni o l'app Microsoft Edge in un chiosco multimediale, queste app sono state sostituite con nuove app che usano un ID app diverso. Ti consigliamo vivamente di leggere Di seguito [nuovi AUMID per le nuove app in modalità tutto schermo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) In questo modo potrai continuare ad avere l'app Impostazioni nel chiosco multimediale o includere la nuova app Microsoft Edge.

Queste modifiche possono essere eseguite ora e distribuite in tutti i dispositivi e consentono una transizione più agevole all'aggiornamento.

[**Accesso automatico dei visitatori per chioschi multimediale**](#visitor-auto-logon-for-kiosks)

I visitatori possono ora essere connessi automaticamente a un chiosco multimediale. Questo comportamento è attivata per impostazione predefinita, ma può essere gestita e disabilitata.

[**Miglioramento della gestione degli errori in modalità tutto schermo**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Se l'appartenenza al gruppo AAD dell'utente AAD connesso non viene determinata correttamente, la configurazione globale del chiosco multimediale viene utilizzata per il menu start (se presente) altrimenti all'utente viene presentato un menu start vuoto. Anche se il menu start vuoto non è una configurazione che è possibile impostare direttamente, questa nuova gestione potrebbe essere qualcosa che informa il reparto di supporto se si utilizzano chioschi multimediale, in quanto ciò potrebbe essere applicabile alle configurazioni o potrebbe essere necessario apportare nuove modifiche alle configurazioni di accesso assegnate.

#### <a name="updates-to-page-settings-visibility"></a>Aggiornamenti della visibilità delle impostazioni della pagina

[**New SettingsURIs for Page Settings Visibility**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

SE attualmente si usa [Visibilità](settings-uri-list.md) impostazioni pagina, è possibile apportare modifiche agli URI esistenti consentiti o bloccati.

#### <a name="updates-for-your-wdac-policy"></a>Aggiornamenti per i criteri WDAC

Se in precedenza si bloccava Microsoft Edge tramite WDAC, è necessario aggiornare i criteri WDAC. Esaminare [quanto segue e](#using-wdac-to-block-new-microsoft-edge) usare il codice di esempio fornito.

#### <a name="enable-new-endpoints-for-edge"></a>Abilitare nuovi endpoint per Edge

Se si dispone di un'infrastruttura che prevede la configurazione di endpoint di rete come proxy o firewall, abilitare questi nuovi [endpoint per la nuova app Microsoft Edge.](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>Elementi configurabili di recente

- [Configurare la diagnostica di fallback](#configuring-fallback-diagnostics-via-settings-app)
  - È possibile configurare se e chi può raccogliere la diagnostica di fallback.
- [Condividere elementi con i dispositivi nelle vicinanze](#share-things-with-nearby-devices)
  - È possibile disabilitare la nuova funzionalità di condivisione nelle vicinanze.
- [Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Esaminare le nuove configurazioni disponibili per Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nuovo strumento di diagnostica

- [Nuovo strumento di risoluzione dei problemi di aggiornamento del sistema operativo](#new-os-update-troubleshooter)
  - Raccogliere i log correlati agli aggiornamenti del sistema operativo

### <a name="introducing-the-new-microsoft-edge"></a>Introduzione al nuovo Microsoft Edge

![Animazione del logo legacy di Microsoft Edge al nuovo logo di Microsoft Edge](images/new-edge.gif)

Il nuovo Microsoft Edge adotta il progetto [open source Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) per creare una migliore compatibilità per i clienti e una minore frammentazione del Web per gli sviluppatori Web.

Con questa anteprima insider, il nuovo Microsoft Edge è disponibile per la prima volta per i clienti di HoloLens 2! Mentre il nuovo Microsoft Edge sostituirà Microsoft Edge legacy in HoloLens 2, entrambi i browser sono attualmente disponibili per i insider. Condividere feedback e bug con il team tramite la **funzionalità Invia feedback** nel nuovo Microsoft Edge o tramite Hub di [Feedback.](hololens-feedback.md)

![Nuovo screenshot di Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Avvio del nuovo Microsoft Edge

Esistono due versioni di Microsoft Edge disponibili per i insider: la nuova icona di Microsoft Edge di Microsoft Edge (rappresentata da un'icona verde e blu) e l'icona legacy di Microsoft Edge (rappresentata dall'icona ![ ](images/new_edge_logo.png) "e" bianca). Il nuovo Microsoft Edge viene aggiunto al menu Start e verrà avviato automaticamente quando si attiva un collegamento Web. Se vuoi ripristinare l'uso di Microsoft Edge legacy come web browser predefinito, vedi le istruzioni seguenti per [la reimpostazione delle app predefinite.](#default-app-picker)

> [!NOTE]
> Quando avvii per la prima volta il nuovo Microsoft Edge in HoloLens 2, le impostazioni e i dati verranno importati da Microsoft Edge legacy. Se si continua a usare Microsoft Edge legacy dopo l'avvio del nuovo Microsoft Edge, i nuovi dati non verranno sincronizzati da Microsoft Edge legacy al nuovo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge

Il nuovo Microsoft Edge offre agli amministratori IT un set molto più ampio di criteri del browser in HoloLens 2 rispetto a quelli precedentemente disponibili con Microsoft Edge legacy.

Ecco alcune risorse utili per saperne di più sulla gestione delle impostazioni dei criteri per il nuovo Microsoft Edge:

- [Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Mapping dei criteri della versione legacy di Microsoft Edge a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapping dei criteri di Google Chrome a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentazione [completa di Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> A causa del volume di criteri del browser supportati dal nuovo Microsoft Edge, il team non è in grado di garantire che ogni nuovo criterio funzioni in HoloLens 2. Tuttavia, abbiamo testato e confermato che il nuovo equivalente di Microsoft Edge di ogni criterio legacy di Microsoft Edge precedentemente supportato in HoloLens 2 funziona come previsto. Vedi Mapping dei criteri legacy di Microsoft Edge a [Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) per trovare il nuovo equivalente di Microsoft Edge di ogni criterio browser Microsoft Edge legacy che usavi con HoloLens 2.
>
> Esistono almeno due nuovi criteri di ** Microsoft Edge che non funzioneranno con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Cosa aspettarsi dal nuovo Microsoft Edge in HoloLens 2

Poiché il nuovo Microsoft Edge è un'app Win32 nativa con un nuovo livello di scheda UWP che ne consente l'esecuzione su dispositivi solo UWP come HoloLens 2, alcune funzionalità potrebbero non essere immediatamente disponibili. Supporteremo nuovi scenari e nuove funzionalità nei prossimi mesi, quindi controlla questo spazio per informazioni aggiornate.

**Scenari e funzionalità previsti per il funzionamento:**
- Esperienza di prima esecuzione, accesso al profilo e sincronizzazione
- I siti Web devono eseguire il rendering e comportarsi come previsto
- La maggior parte delle funzionalità del browser (Preferiti, Cronologia e così via) dovrebbe funzionare come previsto
- Modalità scura
- Installazione di app Web nel dispositivo
- Installazione delle estensioni (per favore facci sapere se usi estensioni che non funzionano correttamente in HoloLens 2)
- Visualizzazione e contrassegno di un PDF
- Suono spaziale da una singola finestra del browser
- Aggiornamento automatico e manuale del browser
- Salvataggio di un PDF dal menu Stampa (con l'opzione "Salva in PDF")
- Estensione visualizzatore WebXR e 360
- Ripristino del contenuto per correggere la finestra, quando si esplorano più finestre posizionate nell'ambiente

**Scenari e funzionalità non previsti:**
- Suono spaziale da più finestre con flussi audio simultanei
- "Vedi, dica"
- Stampa

**Principali problemi noti del browser:**
- Wi-Fi le configurazioni proxy, che sono criteri proxy per le singole connessioni Wi-Fi, attualmente non funzionano con il nuovo Microsoft Edge. Stiamo lavorando attivamente per sbloccare questo problema prima del rilascio pubblico dell'aggiornamento del sistema operativo.
- L'anteprima della lente di ingrandimento nella tastiera olografica è stata disabilitata per il nuovo Microsoft Edge. Speriamo di riabilitare questa funzionalità in un aggiornamento futuro, una volta che l'ingrandimento funziona correttamente.
- Due caratteri sulla tastiera giapponese non funzionano come previsto nel nuovo Microsoft Edge. This issue has been root caused and should be fixed soon.
- I collegamenti Web nell'app di Microsoft Store potrebbero non avviare il browser
- L'audio potrebbe essere riprodotto dalla finestra del browser errata se è aperta e attiva un'altra finestra del browser. Puoi risolvere questo problema chiudendo l'altra finestra attiva che non dovrebbe riprodurre l'audio.
- Quando si riproduce l'audio da una finestra del browser in [modalità "Seguimi",](hololens2-basic-usage.md#follow-me-stop-following)l'audio continuerà a essere riprodotto se si disabilita la modalità "Seguimi". Puoi risolvere questo problema interrompendo la riproduzione audio prima di disabilitare la modalità "Seguimi" o chiudendo la finestra con il **pulsante X.**
- L'interazione con le finestre di Microsoft Edge attive può causare l'inattività imprevista di altre finestre dell'app 2D. Puoi riattivare queste finestre interagendo di nuovo con esse.
- L'apertura di un collegamento Web da un'altra app o da alcuni tipi di documenti come i PDF può causare l'apertura di una seconda scheda vuota nel browser (oltre alla nuova scheda creata con il contenuto del collegamento Web o del collegamento file). È possibile risolvere questo problema chiudendo la scheda vuota aggiuntiva.

#### <a name="microsoft-edge-insider-channels"></a>Canali Microsoft Edge Insider

Il team di Microsoft Edge rende disponibili tre canali di anteprima per la community di Edge Insider: Beta, Dev e Canary. L'installazione di un canale di anteprima non disinstalla la versione rilasciata di Microsoft Edge in HoloLens 2 ed è possibile installarne più di uno contemporaneamente. 

Visita la home [page di Microsoft Edge Insider](https://www.microsoftedgeinsider.com) per altre informazioni sulla community Edge Insider. Per altre informazioni sui diversi canali Edge Insider e per iniziare, visita la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)

Sono disponibili due metodi per installare i canali Microsoft Edge Insider in HoloLens 2:

**Installazione diretta nel dispositivo (attualmente disponibile solo per i dispositivi non gestiti)**
  1. In HoloLens 2, visita la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Seleziona il **pulsante Scarica per HoloLens 2** per il canale Edge Insider che vuoi installare.
  1. Avvia il file MSIX scaricato dalla coda di download di Edge o dalla cartella "Download" del dispositivo (usando Esplora file).
  1. [Il programma di installazione dell'app](app-deploy-app-installer.md) verrà avviato.
  1. Seleziona il **pulsante** Installa.
  1. Una volta completata l'installazione, Microsoft Edge Beta, Dev o Canary è una voce separata **nell'elenco Tutte** le app del menu Start.

**Eseguire l'installazione tramite PC con Windows Device Portal [(richiede](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) che la modalità sviluppatore sia abilitata in HoloLens 2)**
  1. Nel PC, visita la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Seleziona il **pulsante freccia dell'elenco** a discesa accanto al pulsante "Scarica per Windows 10" per il canale Edge Insider che vuoi installare.
  1. Seleziona **HoloLens 2** nel menu a discesa.
  1. Salva il file MSIX nella cartella "Download" del PC (o in un'altra cartella facilmente individuabile).
  1. Usa [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) nel PC per installare il file msix scaricato in HoloLens 2.
  1. Una volta completata l'installazione, Microsoft Edge Beta, Dev o Canary è una voce separata **nell'elenco Tutte** le app del menu Start.

> [!NOTE]
> Durante questa anteprima di Windows Insider per HoloLens 2, la versione di Microsoft Edge nel dispositivo potrebbe essere superiore a quella disponibile in alcuni (o tutti) canali Microsoft Edge Insider. Ciò consente di garantire che le nuove funzionalità e le correzioni specifiche per il Web browser in HoloLens 2 siano disponibili il prima possibile ai nostri Partecipanti al programma Windows Insider. Poco dopo il rilascio pubblico del prossimo aggiornamento di Windows, le build del canale Microsoft Edge Insider supereranno e rimarranno in anticipo rispetto alla versione di Microsoft Edge sul tuo HoloLens 2.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Utilizzo di WDAC per bloccare il nuovo Microsoft Edge

Per gli amministratori IT che desiderano aggiornare i criteri [WDAC](windows-defender-application-control-wdac.md) per bloccare la nuova app Microsoft Edge, dovrai aggiungere quanto segue al criterio.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gestione degli endpoint per il nuovo Microsoft Edge

Alcuni ambienti potrebbero avere restrizioni di rete da tenere in considerazione. Per garantire un'esperienza ottimale con il nuovo edge, [abilita questi endpoint Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Altre informazioni sugli endpoint attualmente [disponibili per HoloLens.](hololens-offline.md)

### <a name="webxr-and-360-viewer"></a>Visualizzatore WebXR e 360

*Aggiunta in Windows Insider build 20289.1000*

Il nuovo Microsoft Edge include il supporto per WebXR, che è il nuovo standard per la creazione di esperienze Web immersive (sostituendo WebVR). Molte esperienze Web immersive sono state progettate per la realtà virtuale (sostituiscono il campo di visualizzazione con un ambiente virtuale), ma queste esperienze sono supportate anche da HoloLens 2. Lo standard WebXR consente inoltre esperienze Web immersive in realtà aumentata e mista che usano l'ambiente fisico. Poiché gli sviluppatori trascorrono più tempo con WebXR, prevediamo che nuove esperienze immersive in realtà aumentata e mista arriveranno ai clienti di HoloLens 2 per provare!

L'estensione visualizzatore 360 si basa su WebXR e viene installata automaticamente insieme al nuovo Microsoft Edge in HoloLens 2. Questa estensione Web offre la possibilità di immergersi in video a 360 gradi. YouTube offre la selezione più ampia di 360 video, quindi ti invitiamo a iniziare da qui.

#### <a name="how-to-use-webxr"></a>Come usare WebXR

1. Passare a un sito Web con supporto WebXR.
1. Seleziona il **pulsante Enter VR** nel sito Web. La posizione e la rappresentazione visiva di questo pulsante possono variare in base al sito Web, ma l'aspetto potrebbe essere simile al seguente:

    ![Esempio di pulsante Enter VR](images/75px-enter-vr.png)

1. La prima volta che si tenta di avviare un'esperienza WebXR in un dominio specifico, il browser chiederà il consenso per immettere una visualizzazione immersiva, selezionare **Consenti**.
1. Usa [i gesti holoLens 2 per](hololens2-basic-usage.md#the-hand-tracking-frame) modificare l'esperienza.
1. Se l'esperienza non ha un pulsante **Esci,** usa il gesto [Start](hololens2-basic-usage.md#start-gesture) per tornare a casa.

**Esempi WebXR consigliati**
- Visualizzatore 360 (vedere la sezione successiva)
- [Dinosauri XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Come usare visualizzatore 360

1. Passa a un video a 360 gradi su YouTube.
1. Nel fotogramma video seleziona il pulsante visore per realtà mista:

    ![Pulsante per attivare visualizzatore 360](images/enter-360-viewer.jpg)

1. La prima volta che provi ad avviare il visualizzatore 360 in un dominio specifico, il browser chiederà il consenso per accedere a una visualizzazione immersiva. Selezionare **Consenti**.
1. [Tocco dell'aria](hololens2-basic-usage.md#select-using-air-tap) per visualizzare i controlli di riproduzione. Usa [i raggi della mano](hololens2-basic-usage.md#select-using-air-tap) e il tocco dell'aria per riprodurre/sospendere, andare avanti/indietro, attivare/disattivare i sottotitoli o interrompere l'esperienza (che esce dalla visualizzazione immersiva). I controlli di riproduzione scompariranno dopo alcuni secondi di inattività.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principali problemi noti di WebXR e visualizzatore 360
- A seconda della complessità dell'esperienza WebXR, la frequenza dei fotogrammi può essere goccia o balbuzie.
- Il supporto per le giunzioni articolate della mano in WebXR non è abilitato per impostazione predefinita. Gli sviluppatori possono abilitare il supporto `edge://flags` attivando "Input mano WebXR".
- Quando si esce da un'esperienza WebXR o visualizzatore a 360, potrebbero essere necessario 30 secondi o più perché gli ologrammi nella casa di realtà mista riappariranno.
- 360 video da siti Web diversi da YouTube potrebbero non funzionare come previsto.
- I sottotitoli sono attualmente disabilitati nel visualizzatore 360 in HoloLens 2. Microsoft prevede di abilitare questa funzionalità in un aggiornamento futuro.
- La sospensione di un video nel visualizzatore a 360 interrompe il rendering del video (ma selezionando il pulsante di riproduzione viene ripresa correttamente la riproduzione).
- Il pulsante "video successivo" in Visualizzatore 360 non funziona attualmente.
- Puoi riprodurre video 2D in una modalità "cinema" immersiva, ma la frequenza dei fotogrammi può essere inferiore a 30 fps.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornire feedback su WebXR e visualizzatore 360

Condividere feedback e bug con il team tramite la **funzionalità Invia feedback** nel nuovo Microsoft Edge.

### <a name="new-settings-app"></a>Nuova app Impostazioni

Con questa versione, stiamo introducendo una nuova versione dell'app Impostazioni. La nuova app Impostazioni include nuove funzionalità e impostazioni espanse per HoloLens 2 nelle aree seguenti: Audio, Sospensione di Power &, Rete & Internet, App, Account, Accessibilità e altro ancora.

> [!NOTE]
> Poiché la nuova app Impostazioni è distinta dall'app Impostazioni legacy, tutte le finestre Impostazioni posizionate in precedenza nell'ambiente verranno rimosse al momento dell'aggiornamento.

![Home page dell'app Nuove impostazioni](images/new-settings-app.png)

**Nuove funzionalità e impostazioni**
- Ricerca impostazioni: cerca le impostazioni dalla home page Impostazioni usando parole chiave o il nome dell'impostazione.
- Suono > sistema:
  - Dispositivi audio di input e output: scegli in modo indipendente i dispositivi audio di input e output (ad esempio, ascolta l'audio tramite le cuffie Bluetooth o usa un microfono USB-C per l'input audio).
    > [!NOTE]
    > Bluetooth microfoni non sono supportati da HoloLens 2.
  - Volume dell'app: regola in modo indipendente il volume di ogni app. Vedi [controllo del volume per app.](#per-app-volume-control)
- Sistema > sospensione & alimentazione: scegli quando il dispositivo deve passare alla modalità sospensione dopo un periodo di inattività.
- Sistema > batteria: abilita manualmente la modalità risparmio batteria o imposta una soglia della batteria a cui la modalità risparmio batteria si attiva automaticamente.
- Dispositivi > USB: puoi disabilitare le connessioni USB per impostazione predefinita.
- Rete & Internet:
  - Le schede Ethernet USB-C verranno ora visualizzate in Rete & Internet.
  - Le impostazioni della scheda Ethernet USB-C sono ora disponibili, incluso il relativo indirizzo IP.
  - Ora puoi abilitare la modalità aereo in HoloLens 2.
- App: puoi reimpostare le app predefinite usate per i tipi di file e collegamenti. Per altre informazioni, vedi [Selezione app predefinita.](#default-app-picker)
- Account > Altri utenti: i proprietari dei dispositivi possono aggiungere utenti, aggiornare gli utenti standard ai proprietari dei dispositivi, declassare i proprietari dei dispositivi a utenti standard e rimuovere utenti.
- Accessibilità: modifica delle dimensioni del testo e di alcuni effetti visivi.

**Problemi noti**
- Le finestre Impostazioni posizionate in precedenza verranno rimosse (vedi nota precedente).
- Non puoi più rinominare il dispositivo con l'app Impostazioni. Gli amministratori IT possono rinominare i dispositivi usando il modello di nome del dispositivo [Windows Autopilot per HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) o il nodo MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- La pagina Ethernet mostra sempre un dispositivo Ethernet virtuale ("UsbNcm").
- L'utilizzo della batteria per il nuovo Microsoft Edge potrebbe non essere accurato, a causa della sua natura come applicazione desktop Win32 supportata da un livello di scheda UWP (nessuna correzione prevista a breve).

### <a name="display-color-calibration"></a>Calibrazione dei colori dello schermo

*Aggiunta in Windows Insider build 20293.1000*

Con questa nuova impostazione, è possibile selezionare un profilo colori alternativo per il display HoloLens 2. In questo modo i colori potrebbero risultare più accurati, soprattutto a livelli di luminosità dello schermo più bassi. La calibrazione dei colori dello schermo è disponibile nell'app Impostazioni nella pagina Calibrazione > sistema.

> [!NOTE]
> Poiché questa impostazione salva un nuovo profilo colori nel firmware dello schermo, si tratta di un'impostazione per dispositivo (e non univoca per ogni account utente).

#### <a name="how-to-use-display-color-calibration"></a>Come usare la calibrazione dei colori dello schermo

1. Avvia **l'app** Impostazioni e passa a **Calibrazione > sistema**.
1. In **Calibrazione colore visualizzazione**selezionare il pulsante Esegui **calibrazione** colori dello schermo.
1. L'esperienza di calibrazione del colore dello schermo verrà avviata e ti incoraggerà a verificare che la visiera sia nella posizione corretta.
1. Dopo aver proceduto attraverso le finestre di dialogo delle istruzioni, la luminosità dello schermo verrà automaticamente ridotta al 30%.
    > [!TIP]
    > Se hai problemi a vedere la scena in grigio nell'ambiente, puoi regolare manualmente il livello di luminosità di HoloLens 2 usando i pulsanti di luminosità sul lato sinistro del dispositivo.
1. Seleziona i pulsanti da 1 a 6 per provare istantaneamente ogni profilo di colore e trovarne uno che sia più adatto agli occhi (questo in genere significa che il profilo che consente alla scena di apparire più neutro, con il motivo in scala di grigi e i toni della pelle come previsto).

    ![Visualizzare la scena di calibrazione dei colori](images/color-cal-ui.png)
    
1. Quando sei soddisfatto del profilo selezionato, seleziona il pulsante Salva & **Esci**
1. Se si preferisce non apportare modifiche, selezionare il pulsante **Annulla & Esci** e le modifiche verranno ripristinate

> [!TIP]
> Ecco alcuni suggerimenti utili da tenere presenti durante l'uso dell'impostazione di calibrazione del colore dello schermo:
> - È possibile eseguire di nuovo la calibrazione del colore di visualizzazione da Impostazioni ogni volta che si desidera
> - Se qualcuno nel dispositivo ha usato in precedenza l'impostazione per modificare i profili colore, la data/ora della modifica più recente verrà visualizzata nella pagina Impostazioni
> - Quando si rieseguono le calibrazioni dei colori dello schermo, il profilo colori salvato in precedenza verrà evidenziato e il profilo 0 non verrà visualizzato (poiché il profilo 0 rappresenta il profilo colori originale dello schermo)
> - Se si desidera ripristinare il profilo colori originale dello schermo, è possibile farlo dalla pagina Impostazioni (vedere come reimpostare il [profilo colori)](#how-to-reset-color-profile)

#### <a name="how-to-reset-color-profile"></a>Come reimpostare il profilo colori

Se non sei soddisfatto del profilo colori personalizzato salvato in HoloLens 2, puoi ripristinare il profilo colori originale del dispositivo:
1. Avvia **l'app** Impostazioni e passa a **Calibrazione > sistema**.
1. In **Calibrazione colore visualizzazione**selezionare il pulsante Ripristina profilo **colori** predefinito.
1. Quando viene visualizzata la finestra di dialogo, selezionare **Riavvia** se si è pronti per riavviare HoloLens 2 e applicare le modifiche.

#### <a name="top-display-color-calibration-known-issues"></a>Problemi noti relativi alla calibrazione del colore dello schermo superiore

- Nella pagina Impostazioni, la stringa di stato che indica quando il profilo colori è stato modificato per l'ultima volta non sarà aggiornato fino a quando non si ricarica la pagina di Impostazioni.
    - Soluzione alternativa: selezionare un'altra pagina Impostazioni e quindi selezionare di nuovo la pagina Calibrazione.

### <a name="default-app-picker"></a>Selezione app predefinita

Quando attivi un collegamento ipertestuale o apri un tipo di file con più di un'app installata, che lo supporta, viene visualizzata una nuova finestra che ti chiede di selezionare quale app installata deve gestire il tipo di file o di collegamento. In questa finestra puoi anche scegliere di fare in modo che l'app selezionata gestirà il file o il tipo di collegamento "Una volta" o "Sempre".

![Finestra di selezione app](images/default-app-picker.png)

Se scegli "Sempre" ma in un secondo momento vuoi modificare quale app gestisce un determinato file o tipo di collegamento, puoi reimpostare le impostazioni predefinite salvate in Impostazioni **> App**. Scorri fino alla parte inferiore **** della pagina e seleziona il pulsante Cancella in "App predefinite per i tipi di file" e/o "App predefinite per i tipi di collegamento". A differenza dell'impostazione simile nei PC desktop, non è possibile reimpostare le impostazioni predefinite dei singoli tipi di file.

### <a name="per-app-volume-control"></a>Controllo del volume per app

Ora in questa build di Windows Insider gli utenti possono regolare manualmente il livello di volume di ogni app. In questo modo gli utenti possono concentrarsi meglio sulle app necessarie o ascoltare meglio quando usano più app. Ad esempio, se devi disattivare il volume di un'app mentre chiami un'altra persona per assistenza remota in un'altra.

Per impostare il volume di **** una singola app, passa a Impostazioni Suono di sistema e in Opzioni audio  ->  ****  ->  **** avanzate seleziona **Volume dell'app e preferenze del dispositivo.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office Web App

>[!NOTE]
>A causa della build 20325.1000 di Windows Insider, l'app Web di Office non verrà più preinstallato e non sarà preinstallato per la prossima versione pubblica dell'aggiornamento del sistema operativo. Per installare l'app Web di Office, visitare https://www.office.com e selezionare il pulsante App **disponibile** o Installa **Office** nella barra degli indirizzi. Selezionare **Installa** per confermare.

L'app Web di Office è stata aggiunta all'elenco "Tutte le app" del menu Start. Questa app Web può anche essere aggiunta a Start o disinstallata. Poiché si tratta di un'app Web, la relativa funzionalità corrisponde esattamente a quanto si potrebbe provare visitando https://www.office.com . La funzionalità dell'app Web di Office è disponibile solo quando HoloLens 2 dispone di una connessione Internet attiva.

**Problema noto**
- La reimpostazione del dispositivo rimuove l'app Web di Office

### <a name="swipe-to-type"></a>Scorrimento rapido verso il testo

Alcuni clienti trovano più veloce "digitare" sulle tastiere virtuali scorrendo la forma della parola che intendono digitare e stiamo visualizzando in anteprima questa funzionalità per la tastiera olografica. Puoi scorrere una parola alla volta passando la punta del dito attraverso il piano della tastiera olografica, scorrendo la forma della parola e quindi ritirando la punta del dito dal piano della tastiera. Puoi scorrere rapidamente le parole di follow-up senza dover premere la barra spaziatrice rimuovendo il dito dalla tastiera tra le parole. Saprai che la funzionalità funziona se vedi una traccia di scorrimento rapido che segue il movimento del dito sulla tastiera.

Nota che questa funzionalità può essere difficile da usare e master a causa della natura di una tastiera olografica in cui non si prova resistenza al dito (a differenza del display di un telefono cellulare). Stiamo valutando questa funzionalità per il rilascio pubblico, quindi il tuo feedback è importante; se ritieni utile la funzionalità o se hai un feedback positivo, contattaci tramite [Hub di Feedback.](hololens-feedback.md)

### <a name="power-menu-from-start"></a>Menu Alimentazione da Start

Un nuovo menu che consente all'utente di disconnettersi, arrestare e riavviare il dispositivo. Indicatore nella schermata Start di HoloLens che indica quando è disponibile un aggiornamento del sistema.

#### <a name="how-to-use"></a>Modalità di utilizzo

1. Apri la schermata Start di HoloLens usando il gesto [Start](hololens2-basic-usage.md#start-gesture) o pronunciando "Vai a Start".

2. Nota l'icona con i puntini di sospensione (...) accanto all'immagine del profilo utente:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Seleziona l'immagine del profilo utente usando le mani o il comando vocale "Power".

4. Viene visualizzato un menu con le opzioni Disconnetti, Riavvia o Arresta il dispositivo:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Seleziona le opzioni di menu per disconnettersi, riavviare o arrestare HoloLens. L'opzione Disconnei potrebbe non essere disponibile se il dispositivo è configurato per un singolo [account Microsoft (MSA) o un account locale.](hololens-identity.md)

6. Chiudi il menu toccando qualsiasi altro punto o chiudendo il menu Start con il gesto Start.

#### <a name="update-indicator"></a>Indicatore di aggiornamento

Quando è disponibile un aggiornamento, l'icona con i puntini di sospensione si accenderà per indicare che un riavvio installerà l'aggiornamento Le opzioni di menu cambiano anche per riflettere la presenza dell'aggiornamento.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Più utenti elencati nella schermata di accesso

In precedenza la schermata di accesso mostrava solo l'ultimo utente connesso, nonché un punto di ingresso "Altro utente". Abbiamo ricevuto il feedback dei clienti che questo non è sufficiente se più utenti hanno eseguito l'accesso al dispositivo. Era comunque necessario digitare di nuovo il nome utente e così via.

Introdotto in questa build di **** Windows Insider, quando selezioni Altro utente che si trova a destra del campo di immissione del PIN, nella schermata Di accesso verranno visualizzati più utenti con cui è stato eseguito l'accesso al dispositivo in precedenza. In questo modo gli utenti possono selezionare il proprio profilo utente e quindi accedere con le credenziali di Windows Hello. Un nuovo utente può anche essere aggiunto al dispositivo da questa pagina Altri utenti tramite il **pulsante Aggiungi account.**

Quando nel menu Altri utenti, il pulsante Altri utenti visualizza l'ultimo utente che ha eseguito l'accesso al dispositivo. Seleziona questo pulsante per tornare alla schermata Di accesso per questo utente.

![Impostazione predefinita della schermata di accesso](./images/multiusers1.jpg)

<br>

![Schermata di accesso di altri utenti](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Supporto microfono esterno USB-C

> [!IMPORTANT]
> Il plug-in di un microfono USB non **lo imposta automaticamente come dispositivo di input.** Quando si collega un set di cuffie USB-C, gli utenti osserveranno che l'audio della cuffia verrà reindirizzato automaticamente alle cuffie, ma il sistema operativo HoloLens assegna la priorità all'array di microfoni interni rispetto a qualsiasi altro dispositivo di input. **Per usare un microfono USB-C, segui la procedura seguente.**

Gli utenti possono selezionare i microfoni esterni connessi tramite USB-C usando il **pannello Impostazioni** audio. I microfoni USB-C possono essere usati per chiamare, registrare e così via.

Apri **l'app** Impostazioni e seleziona **Suono**  >  **di sistema.**

![Impostazioni audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Per usare i microfoni esterni con **Assistenza remota,** gli utenti dovranno fare clic sul collegamento ipertestuale "Gestisci dispositivi audio".
>
> Usa quindi l'elenco a discesa per impostare il microfono esterno come **Predefinito** o **Predefinito comunicazioni.** Se **si sceglie Predefinito,** il microfono esterno verrà utilizzato ovunque.
>
> La **scelta di Communications Default** significa che il microfono esterno verrà usato in Assistenza remota e in altre app di comunicazione, ma l'array di microfoni HoloLens può comunque essere usato per altre attività.

![Gestire i dispositivi audio](images/usbc-mic-2.png)

<br>

![Impostare il microfono predefinito](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Che dire del Bluetooth microfono?

Purtroppo Bluetooth microfoni non sono ancora supportati in HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Risoluzione dei problemi relativi ai microfoni USB-C

Tenere presente che alcuni microfoni USB-C segnalano erroneamente se stessi sia come microfono *che come* altoparlante. Si tratta di un problema con il microfono e non con HoloLens. Quando si collega uno di questi microfoni a HoloLens, il suono potrebbe essere perso. Fortunatamente c'è una semplice correzione.  

In **Impostazioni**Suono di sistema imposta esplicitamente gli altoparlanti incorporati (Driver audio funzionalità  ->  ****  ->  **** **analogica)** come **dispositivo predefinito.** HoloLens deve ricordare questa impostazione anche se il microfono viene rimosso e riconnesso in un secondo momento.

![Risoluzione dei problemi relativi ai microfoni USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Accesso automatico visitatore per chioschi multimediale

Questa nuova funzionalità consente di utilizzare l'accesso automatico sugli account dei visitatori per le modalità tutto schermo.

Per una configurazione non AAD, per configurare un dispositivo per l'accesso automatico dei visitatori:

1. Creare un pacchetto di provisioning che:
    1. Configura le **impostazioni di runtime/AssignedAccess per** consentire gli account dei visitatori.
    1. Facoltativamente, registra il dispositivo in MDM **(Impostazioni di runtime/Area di lavoro/Registrazioni)** in modo che possa essere gestito in un secondo momento.
    1. Non creare un account locale
1. [Applica il pacchetto di provisioning](hololens-provisioning.md).

Per una configurazione AAD, gli utenti possono ottenere un risultato simile a questo oggi senza questa modifica. I dispositivi aggiunti ad AAD configurati per la modalità tutto schermo possono accedere a un account visitatore con un solo tocco pulsante dalla schermata di accesso. Dopo aver effettuato l'accesso all'account del visitatore, il dispositivo non richiederà di nuovo l'accesso finché il visitatore non viene disconnesso esplicitamente dal menu Start o non viene riavviato il dispositivo.

L'accesso automatico dei visitatori può essere gestito tramite [criteri URI OMA](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) personalizzati:

- Valore URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Criterio  | Descrizione   | Configurazioni  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Consente a un visitatore di accedere automaticamente a un chiosco multimediale   | 1 (Sì), 0 (No, impostazione predefinita).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Usare le nuove app Impostazioni e Edge in modalità tutto schermo

Quando si includono app in [Chioschi,](hololens-kiosk.md)un amministratore IT spesso aggiunge l'app al chiosco multimediale ma usa il suo ID modello utente app (AUMID). Poiché sia l'app Impostazioni che l'app Microsoft Edge sono considerate nuove app e diverse rispetto alle app meno recenti che usano AUMID per tali app, sarà necessario aggiornarsi per usare il nuovo AUMID.

Quando si modifica un chiosco multimediale per includere le nuove app, è consigliabile aggiungere nel nuovo AUMID e lasciare quella precedente. Questo creerà una transizione semplice quando gli utenti aggiornano il sistema operativo e non dovranno ricevere nuovi criteri per continuare a usare il chiosco multimediale come previsto.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| App Impostazioni vecchie       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| App Nuove impostazioni       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Vecchia app Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nuova app Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifiche al comportamento della modalità tutto schermo per la gestione degli errori

Nelle build precedenti, se un dispositivo ha una configurazione tutto schermo, che è una combinazione di accesso assegnato globale e accesso assegnato al membro del gruppo AAD, se la determinazione dell'appartenenza al gruppo AAD non è riuscita, l'utente non visualizza " nulla nel menu[Start".](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)

A partire dalla versione Windows Insider, l'esperienza chiosco multimediale avrà il fallback alla configurazione globale del chiosco multimediale (se presente) in caso di errori durante la modalità tutto schermo del gruppo AAD.

### <a name="new-settingsuris-for-page-settings-visibility"></a>New SettingsURIs for Page Settings Visibility

In [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) è stato aggiunto il criterio [Impostazioni/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visibili nell'app Impostazioni. PageVisibilityList è un criterio che consente agli amministratori IT di impedire che pagine specifiche nelle impostazioni di sistema siano visibili o accessibili oppure di farlo per tutte le pagine ad accezioni di quelle specificate.

Se si visita [Visibilità impostazioni](settings-uri-list.md)pagina , è possibile trovare istruzioni per l'utilizzo di questo CSP e l'elenco degli URI disponibili nelle versioni precedenti.

Nelle build di Windows Insider stiamo espandendo l'elenco degli URI delle impostazioni disponibili, che gli amministratori IT possono gestire. Alcuni di questi URI sono per le nuove aree disponibili all'interno della nuova app Impostazioni. Se si utilizza il criterio Settings/PageVisibilityList, esaminare l'elenco seguente e modificare le pagine consentite o bloccate in base alle esigenze.

> [!NOTE]
> **Deprecato: ms-settings:network-proxy**
>
> Una pagina delle impostazioni è deprecata in queste build più nuove. La vecchia **pagina & proxy Internet**non è più disponibile come impostazione  >  **** globale. Le nuove impostazioni del proxy per connessione sono disponibili in Proprietà Wi-Fi di Rete **& Rete**o Rete  >  ****  >  **** & Proprietà ****  >  **Ethernet**  >  **Internet**.

<br>

| Pagina delle impostazioni                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| App > app & funzionalità                               | `ms-settings:appsfeatures`                         |
| App > App & funzionalità > opzioni avanzate          | `ms-settings:appsfeatures-app`                     |
| App > mappe offline                                  | `ms-settings:maps`                                 |
| App > mappe offline > Scarica mappe                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivi > Mouse                                      | `ms-settings:mouse`                                |
| Dispositivi > USB                                        | `ms-settings:usb`                                  |
| Modalità & Internet > aereo                   | `ms-settings:network-airplanemode`                 |
| Privacy > Generale                                    | `ms-settings:privacy-general`                      |
| Privacy > personalizzazione & input penna             | `ms-settings:privacy-speechtyping`                 |
| Privacy > Motion                                     | `ms-settings:privacy-motion`                       |
| Privacy > Bordi dello screenshot                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Privacy > screenshot e app                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batteria > di sistema                                     | `ms-settings:batterysaver`                         |
| Batteria > di sistema                                     | `ms-settings:batterysaver-settings`                |
| Suono > sistema                                       | `ms-settings:sound`                                |
| Sistema > audio > volume dell'app e preferenze del dispositivo | `ms-settings:apps-volume`                          |
| System > Sound > Gestire i dispositivi audio              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Time & Language > Date & time                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Ora & lingua > lingua                           | `ms-settings:language`                             |
| Ora & lingua > lingua                           | `ms-settings:regionlanguage-languageoptions`       |
| Aggiornamento & sicurezza > ripristino & ripristino               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URI aggiornati

In precedenza i due URI seguenti non portava un utente direttamente alle pagine indicate, ma bloccava solo la pagina degli aggiornamenti principali. Gli elementi seguenti sono stati aggiornati per indirizzare le pagine:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configurazione della diagnostica di fallback tramite l'app Impostazioni

Ora in Impostazioni App, un utente può configurare il comportamento di [Diagnostica fallback.](hololens-diagnostic-logs.md) Nell'app Impostazioni passa alla **pagina Risoluzione dei**problemi  ->  **relativi** alla privacy per configurare questa impostazione.

> [!NOTE]
> Se per il dispositivo sono configurati criteri MDM, l'utente non sarà in grado di ignorare tale comportamento.  

### <a name="share-things-with-nearby-devices"></a>Condividere elementi con i dispositivi nelle vicinanze

Condividere elementi con dispositivi Windows 10 vicini, inclusi PC e altri dispositivi HoloLens 2 che eseguono HoloLens Insider build 20279.1006+. Puoi provarlo **in**Impostazioni Esperienze condivise di sistema per condividere file o URL da un  ->  ****  ->  **** HoloLens a un PC. Per altri dettagli, leggi altre informazioni su come condividere [elementi con i dispositivi nelle vicinanze in Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Questa funzionalità può essere gestita tramite [Connectivity/AllowConnectedDevices.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-update-troubleshooter"></a>Nuovo strumento di risoluzione dei problemi di aggiornamento del sistema operativo

Oltre ai precedenti risoluzione dei problemi nell'app Impostazioni, è stato aggiunto un nuovo strumento di risoluzione dei problemi con l'aggiunta della nuova app Impostazioni per gli aggiornamenti del sistema operativo. Passare a **Impostazioni Aggiornamento**  ->  **sicurezza &amp; Risoluzione**  >  **dei problemi di**Windows  >  **Update** e selezionare **Avvia**. In questo modo è possibile raccogliere le tracce durante la riproduzione del problema con gli aggiornamenti del sistema operativo per facilitare la risoluzione dei problemi con l'IT o il supporto.

### <a name="delivery-optimization-preview"></a>Anteprima ottimizzazione recapito

Con questo aggiornamento di HoloLens Insider, Windows Holographic for Business consente un'anteprima anticipata delle impostazioni di ottimizzazione del recapito per ridurre il consumo di larghezza di banda per i download da più dispositivi HoloLens. Una descrizione più completa di questa funzionalità insieme alla configurazione di rete consigliata è disponibile qui: Ottimizzazione recapito [per gli aggiornamenti di Windows 10.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

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
- Windows Holographic for Business supporta solo le modalità di download HTTP e i download da un [endpoint della cache connessa Microsoft;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Le modalità di download peer-to-peer e le assegnazioni di gruppo non sono attualmente supportate per i dispositivi HoloLens.
- HoloLens non supporta l'ottimizzazione della distribuzione o del recapito per gli endpoint di Windows Server Update Services.
- La risoluzione dei problemi richiederà la diagnostica nel server della cache connessa o la raccolta di una traccia in HoloLens in HoloLens tramite Impostazioni ****  >  **Aggiornamento & Sicurezza**  >   **Risoluzione**dei problemi  >   **di Windows Update**.

### <a name="improvements-and-fixes-in-the-update"></a>Miglioramenti e correzioni nell'aggiornamento:

- [La diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics) includerà anche informazioni aggiuntive sul dispositivo per il numero di serie e la versione del sistema operativo.

### <a name="known-issues-and-work-around"></a>Problemi noti e risoluzione dei problemi

#### <a name="pairing-hololens-to-pc"></a>Associazione di HoloLens al PC

Prima della build 20325.1000 di Windows Insider, quando un utente aveva impostato le credenziali di associazione in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o [Windows Holographic, versione 2004](hololens-release-notes.md#windows-holographic-version-2004) e aggiornata alle build di Windows Insider, le credenziali del set precedente per l'associazione di HoloLens al PC per la distribuzione e il debug di app come tramite Visual Studio non hanno più funzionato. Windows Insider build 20325.1000 risolve questo problema e non richiede azioni aggiuntive per riprendere a usare device portal.

Gli utenti che hanno lampeggiato il dispositivo con una [build Insider](#ffu-download-and-flash-directions) dovranno ora riconseere i propri dispositivi (a 20325.1000+ o a una build GA) per associare i propri dispositivi al PC.

Gli utenti che non si sono iscritti a Windows Insider e che riceveranno l'aggiornamento delle funzionalità quando è disponibile in genere non sono interessati.


## <a name="start-receiving-insider-builds"></a>Iniziare a ricevere build Insider

> [!NOTE]
> Se non hai aggiornato di recente, riavvia il dispositivo per aggiornare lo stato e ottenere la build più recente.
> - Il comando vocale "Riavvia dispositivo" funziona correttamente. 
> - Puoi anche scegliere il pulsante di riavvio in Impostazioni/Programma Windows Insider.
>
> Si è verificato un bug nel back-end che potrebbe essere stato riscontrato e ciò consente di tornare in funzione.

In un dispositivo HoloLens 2 vai **a**Impostazioni Aggiornamento &  >  **Sicurezza Programma**  >  **Windows Insider e** seleziona **Introduzione.** Collega l'account usato per la registrazione come Windows Insider.

Windows Insider sta ora passando a Canali. **L'anello** Fast diventerà **dev Channel,** **l'anello Slow** diventerà il **Canale beta**e l'anello Release **Preview** diventerà il Canale di anteprima **del rilascio.** Ecco l'aspetto del mapping:

![Spiegazione dei canali Windows Insider](images/WindowsInsiderChannels.png)

Per altre informazioni, vedi [Introduzione ai canali Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nei blog di Windows.

Seleziona Quindi **Sviluppo attivo di Windows,** scegli se vuoi ricevere le build del canale **dev** o beta ed esamina le condizioni del programma. ****

Seleziona **Conferma > riavvia ora** per completare l'operazione. Dopo il riavvio del dispositivo, vai a Impostazioni **> aggiornamento & sicurezza > Verificare** la disponibilità di aggiornamenti per ottenere la build più recente.

### <a name="update-error-0x80070490-work-around"></a>Errore di aggiornamento 0x80070490 risolvere il problema
Se si verifica un errore di 0x80070490 durante l'aggiornamento nel canale Dev o Beta, provare a risolvere il problema a breve termine seguente. Si tratta di spostare il canale Insider, raccogliere l'aggiornamento e quindi spostare di nuovo il canale Insider.

#### <a name="stage-one---release-preview"></a>Fase 1 - Release Preview
1.  Impostazioni, Aggiornamento & Sicurezza, Programma Windows Insider, selezionare **Canale di anteprima rilascio.**
2.  Impostazioni, Aggiornamento & Sicurezza, Windows Update, **Controlla aggiornamenti**. Dopo l'aggiornamento, passare alla fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev Channel
1. Impostazioni, Aggiorna & Sicurezza, Programma Windows Insider, seleziona **Canale sviluppatore.**
2. Impostazioni, Aggiornamento & Sicurezza, Windows Update, **Controlla aggiornamenti**.

## <a name="ffu-download-and-flash-directions"></a>Indicazioni per il download e il flash FFU
Per testare con un volo firmato ffu, devi prima sbloccare in anteprima il dispositivo prima di lampeggiare il volo firmato ffu.
1. Su PC:

    1. Scarica ffu nel PC da [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installare ARC (Advanced Recovery Companion) da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. On HoloLens - Flight Unlock: Open **Settings**  >  **Update & Security Windows**Insider  >  **Program** then sign up, reboot device.

1. Flash FFU: ora puoi visualizzare il flash FFU firmato in anteprima usando ARC.

## <a name="provide-feedback-and-report-issues"></a>Fornire commenti e suggerimenti e segnalare i problemi

Usa [l'app Hub di Feedback](hololens-feedback.md) sul tuo HoloLens per fornire feedback e segnalare i problemi. L'uso di Hub di Feedback garantisce che tutte le informazioni di diagnostica necessarie siano incluse per aiutare i nostri tecnici a eseguire rapidamente il debug e risolvere il problema.  I problemi relativi alla versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurati di accettare il prompt che ti chiede se desideri che Hub di Feedback accedono alla cartella Documenti (seleziona **Sì** quando richiesto).

## <a name="note-for-developers"></a>Nota per gli sviluppatori

Sei benvenuto e incoraggiato a provare a sviluppare le tue applicazioni usando le build Insider di HoloLens.  Per iniziare, consulta la documentazione per [sviluppatori di HoloLens.](https://developer.microsoft.com/windows/mixed-reality/development) Queste stesse istruzioni funzionano con le build Insider di HoloLens.  Puoi usare le stesse build di Unity e Visual Studio già in uso per lo sviluppo di HoloLens.

## <a name="stop-receiving-insider-builds"></a>Interrompere la ricezione delle build Insider

Se non vuoi più ricevere build Insider di Windows Holographic, puoi rifiutare esplicitamente quando HoloLens esegue una build di produzione oppure puoi ripristinare il dispositivo usando Advanced Recovery Companion per ripristinare il dispositivo in una versione non Insider di Windows Holographic. [](hololens-recovery.md)

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che annullano la registrazione dalle build di Insider Preview dopo aver reinstallato manualmente una nuova build di anteprima potrebbero visualizzare una schermata blu. In seguito devono ripristinare manualmente il dispositivo. Per informazioni dettagliate sull'impatto o meno, vedere ulteriori informazioni su [questo problema noto.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Per verificare che HoloLens sia in esecuzione una build di produzione:

1. Vai a **Impostazioni > sistema > Informazioni su**e trova il numero di build.

1. [Vedi le note sulla versione per i numeri di build di produzione.](hololens-release-notes.md)

Per rifiutare esplicitamente le build Insider:

1. In un HoloLens che esegue una build di produzione, vai a Impostazioni **> Aggiornamento & Sicurezza > Programma Windows Insider e**seleziona Interrompi build **Insider.**

1. Segui le istruzioni per rifiutare esplicitamente il dispositivo.
