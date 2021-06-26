---
title: HoloLens 2 sulla versione
description: Rimanere aggiornati con tutti gli aggiornamenti in ogni nuova HoloLens 2 versione.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 16aec0e60fde40f0a2bffefa871a7a3774b1eb2e
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924537"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sulla versione

Per garantire un'esperienza produttiva con i dispositivi HoloLens, microsoft continua a rilasciare aggiornamenti di funzionalità, bug e sicurezza. In questa pagina è possibile visualizzare le novità di HoloLens ogni mese. Per ottenere l'aggiornamento HoloLens 2, è [](hololens-update-hololens.md#check-for-updates-and-manually-update) possibile verificare la disponibilità di aggiornamenti e aggiornare manualmente o ottenere l'aggiornamento flash completo (FFU) per eseguire il flash del dispositivo tramite [Advanced Recovery Companion.](hololens-recovery.md#clean-reflash-the-device) Il [download](https://aka.ms/hololens2download) viene mantenuto aggiornato e fornisce la build disponibile a livello generale più recente.

> [!NOTE]
> Il recente annuncio di Windows 11 è stato incentrato sulla versione PC di Windows. Di recente è stato avviato un aggiornamento principale del sistema operativo per HoloLens 2 maggio 2021 e stiamo lavorando [a](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) una versione futura in base ai commenti e suggerimenti dei clienti per questo fallire.

> [!IMPORTANT]
> A causa di un problema noto nella [build 21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)che interessa gli utenti Remote Assist , è attualmente in corso la sospensione dell'offerta di aggiornamenti di Windows Holographic versione 21H1. È stata anche modificata la build predefinita di Advanced Recovery Companion in [Windows Holographic, versione 20H2 - Aggiornamento di giugno 2021,](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)che è la versione 20H2 più recente.
>
> Anche se si riduce la disponibilità di 21 ore su 21 per ridurre l'impatto di questo problema, è possibile che alcuni clienti vogliano comunque eseguire l'aggiornamento a 21H1. Per i clienti che vogliono eseguire l'aggiornamento alla versione 21H1 sono disponibili due percorsi diversi:
>
> - [Registrare i](hololens-insider.md#start-receiving-insider-builds) dispositivi come Windows Insider e selezionare il **Canale beta**, in modo da consentire a tali dispositivi di eseguire l'aggiornamento a 21H1 e avere build affidabili.
> - [Scaricare la versione più recente di FFU nel PC](https://aka.ms/hololens2download) e quindi [eseguire il flash del dispositivo tramite Advanced Recovery Companion.](hololens-recovery.md#clean-reflash-the-device)

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, versione 21H1 - Aggiornamento di giugno 2021
- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive for work or school Camera Roll upload

È stata aggiunta una nuova funzionalità all'app Impostazioni di HoloLens 2, che consente ai clienti di caricare automaticamente foto e video di realtà mista dalla cartella Pictures > Camera Roll del dispositivo alla cartella OneDrive for work o school corrispondente. Questa funzionalità risolve una lacune di funzionalità all'interno [dell'app OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) in HoloLens 2, che supporta solo il caricamento automatico del rullo della fotocamera nel account Microsoft personale di un cliente (e non nell'account aziendale o dell'istituto di istruzione).

**Funzionamento**

- Visitare **Impostazioni > sistema > Fotocamera realtà mista** per abilitare il caricamento della fotocamera.
- Impostando questa funzionalità  sulla posizione Attiva, tutte le foto o i video di realtà mista acquisiti nel dispositivo verranno automaticamente accodati per il caricamento nella cartella Pictures > Camera Roll dell'account OneDrive for work o school.
    >[!NOTE]
    >Foto e video acquisiti prima di abilitare questa funzionalità *non* verranno accodati per il caricamento e dovranno comunque essere caricati manualmente.
- Un messaggio di stato nella pagina Impostazioni visualizza il numero di file in attesa di caricamento (o legge "OneDrive è aggiornato" quando tutti i file in sospeso sono stati caricati).
- Se si è interessati alla larghezza di banda o si vuole "sospendere" il caricamento per qualsiasi motivo, è possibile impostare la funzionalità sulla **posizione Disattivato.** La disabilitazione temporanea della funzionalità garantisce che la coda di caricamento continui ad aumentare quando si aggiungono nuovi file alla cartella Camera Roll, ma i file non verranno caricati fino a quando non si ri enablerà la funzionalità.
- I file più recenti verranno caricati per primi (last in, first out).
- Se l'account OneDrive presenta problemi , ad  esempio dopo la modifica della password, nella pagina Impostazioni verrà visualizzato il pulsante Correggi ora.
- Non esistono dimensioni massime dei file, ma si noti che il caricamento di file di grandi dimensioni richiederà più tempo,soprattutto se la larghezza di banda del caricamento è limitata. Se si "sospende" o si disattiva il caricamento durante il caricamento di un file di grandi dimensioni, il caricamento parziale verrà mantenuto. Se il caricamento viene ri enabledato entro diverse ore dalla sospensione o dallo stato disattivato, il caricamento continuerà dal punto in cui è stato disattivato. Tuttavia, se il caricamento viene ri abilitato dopo diverse ore, il caricamento del file di grandi dimensioni verrà riavviato dall'inizio.

**Problemi noti e avvertenze**

- Questa impostazione non ha limitazioni predefinite in base all'utilizzo corrente della larghezza di banda. Se è necessario ottimizzare la larghezza di banda per un altro scenario, disattivare manualmente l'impostazione. Il caricamento verrà sospeso, ma la funzionalità continuerà a monitorare i file appena aggiunti al rullino. Abilitare nuovamente il caricamento quando si è pronti per continuare.
- Questa funzionalità deve essere abilitata per ogni account utente nel dispositivo e può caricare attivamente solo i file per l'utente che ha eseguito l'accesso al dispositivo.
- Se si stanno scattare foto o video mentre si guarda il numero di caricamenti nella pagina Impostazioni in tempo reale, si noti che il numero di file in sospeso potrebbe non cambiare fino al completamento del caricamento del file corrente.
- Il caricamento verrà sospeso se il dispositivo è in stato di sospensione o è spento. Per assicurarsi che i caricamenti in sospeso siano stati completati, usare attivamente il dispositivo fino a quando la pagina Impostazioni non legge "OneDrive è aggiornato" o modificare le impostazioni **di sospensione & Power** &.
### <a name="added-support-for-some-telemetry-policies"></a>Aggiunta del supporto per alcuni criteri di telemetria

I criteri di telemetria seguenti sono ora supportati nel HoloLens 2:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Sia System\AllowTelemetry che System\ConfigureTelemetryOptInSettingsUx devono essere usati insieme per avere il controllo completo sulla telemetria e sul comportamento nell'app Impostazioni.

Miglioramenti e correzioni nell'aggiornamento:
- Corregge i principali danneggiamenti video con la calibrazione dei colori.
- Risolve un problema a causa del quale il testo potrebbe essere troncato nel menu Risparmio energia.
- Abilita il supporto per i criteri RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, versione 20H2 - Aggiornamento di giugno 2021
- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Aggiunta del supporto per alcuni criteri di telemetria

I criteri di telemetria seguenti sono ora supportati nel HoloLens 2:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Sia System\AllowTelemetry che System\ConfigureTelemetryOptInSettingsUx devono essere usati insieme per avere il controllo completo sulla telemetria e sul comportamento nell'app Impostazioni.

Si consiglia di provare la build più recente, Windows Holographic, versione 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, versione 1903 - Aggiornamento di giugno 2021
- Build 18362.1116

Miglioramenti e correzioni nell'aggiornamento:
- Questo aggiornamento qualitativo mensile non contiene modifiche di primo piano. È quindi possibile provare la build più recente, Windows Holographic, versione 21H1.

>[!IMPORTANT]
> Questa compilazione non verrà più utilizzata.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, versione 21H1
- Build 20346.1002

Questo aggiornamento contiene funzionalità per due destinatari. funzionalità che possono essere usate da chiunque in un dispositivo dall'utente finale e nuove opzioni di gestione dei dispositivi che possono essere configurate dagli amministratori IT. La tabella seguente specifica le funzionalità rilevanti per ogni gruppo di destinatari. Gli amministratori IT possono consultare l'elenco di controllo per [l'aggiornamento dell'amministratore IT.](#it-admin---update-checklist)
>[!IMPORTANT]
>Per eseguire l'aggiornamento a questa build, HoloLens 2 dispositivi devono eseguire l'aggiornamento di febbraio 2021 (build 19041.1136) o versione più recente. Se questo aggiornamento della funzionalità non è disponibile, aggiornare prima il dispositivo e riprovare.

>[!NOTE]
>Attualmente, Microsoft HoloLens 2 supporta gli aggiornamenti di manutenzione mensili (correzioni di bug e sicurezza) per le versioni seguenti:
>- Windows Holographic versione 20H2 (build 19041.1128+)
>- Windows Holographic, versione 2004 (build 19041.1103+)
>- Windows Holographic, versione 1903 (build 18362+) 
>
> Con l'introduzione di Windows Holographic versione 21H1, gli aggiornamenti di manutenzione mensili per **Windows Holographic versione 1903 verranno sospesi.** In questo modo è possibile concentrarsi sulle versioni più recenti e continuare a offrire importanti miglioramenti. 


| Nome funzionalità                                              | Breve descrizione                                                                      | Destinatari | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nuovo Microsoft Edge](#introducing-the-new-microsoft-edge)  | Il nuovo modello basato su Chromium Microsoft Edge è ora disponibile per HoloLens 2. | Utente finale | 
[Visualizzatore WebXR e 360](#webxr-and-360-viewer) | Provare le esperienze Web immersive e la riproduzione di video a 360 minuti. | Utente finale | 
[Nuova app Impostazioni](#new-settings-app) | L'app Impostazioni legacy verrà sostituita da una versione aggiornata con nuove funzionalità e impostazioni. | Utente finale |
[Calibrazione dei colori dello schermo](#display-color-calibration) | Selezionare un profilo colori alternativo per la HoloLens 2 schermo. | Utente finale |
[Selezione app predefinita](#default-app-picker) | Scegliere l'app da avviare per ogni tipo di file o collegamento. | Utente finale |
[Controllo del volume per app](#per-app-volume-control) | Controllare il volume a livello di app indipendentemente dal volume di sistema. | Utente finale |
[Installare app Web](#install-web-apps) | Installare app Web in HoloLens 2, ad esempio Microsoft Office, con il nuovo browser Microsoft Edge web. | Utente finale |
[Scorrimento rapido verso il testo](#swipe-to-type) | Usare la punta del dito per "scorrere" le parole sulla tastiera olografica. | Utente finale |
[Menu Di alimentazione da Start](#power-menu-from-start) | Nel menu Start riavviare e arrestare il dispositivo HoloLens. | Utente finale |
[Più utenti elencati nella schermata di accesso](#multiple-users-listed-on-sign-in-screen) | Visualizzare più account utente nella schermata di accesso. | Utente finale |
[Supporto microfono esterno USB-C](#usb-c-external-microphone-support) | Usare i microfoni USB-C per app e/o Remote Assist. | Utente finale |
[Accesso automatico dei visitatori per chioschi in modalità tutto schermo](#visitor-auto-logon-for-kiosks) | Abilita l'accesso automatico sugli account Visitor da usare per le modalità tutto schermo. | Amministratore IT |
[Nuovi AUMID per le nuove app in modalità tutto schermo](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMID per le nuove impostazioni e le app Perimetrali. | Amministratore IT |
[Miglioramento della distribuzione degli errori in modalità tutto schermo](#kiosk-mode-behavior-changes-for-handling-of-failures) | La modalità tutto schermo cerca Accesso assegnato globale prima del menu start vuoto. | Amministratore IT |
[Nuove impostazioniURIs per la visibilità delle impostazioni di pagina](#new-settings-uris-for-page-settings-visibility) | Oltre 20 nuove impostazioniURI per i criteri Settings/PageVisibilityList. | Amministratore IT |
[Configurare la diagnostica di fallback](#configuring-fallback-diagnostics-via-settings-app) | Impostazione del comportamento di diagnostica di fallback nell'app Impostazioni. | Amministratore IT |
[Condividere elementi con i dispositivi vicini](#share-things-with-nearby-devices) | Condividere file o URL da un dispositivo HoloLens a un PC. | Tutti |
[Nuove tracce di diagnostica del sistema operativo](#new-os-diagnostic-traces) | Nuovo strumento di risoluzione dei problemi in Impostazioni per gli aggiornamenti del sistema operativo. | Amministratore IT |
[Ottimizzazione recapito anteprima](#delivery-optimization-preview) | Ridurre il consumo di larghezza di banda per i download da più dispositivi HoloLens. | Amministratore IT |

Vedere le note sulla versione correlate:

- [Visitare l'archivio dell'emulatore HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Guide di Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Introduzione al nuovo Microsoft Edge

![Animazione del logo Microsoft Edge legacy al nuovo logo Microsoft Edge logo](images/new-edge.gif)

Il nuovo Microsoft Edge adotta il progetto [Chromium open source](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) per creare una migliore compatibilità per i clienti e una minore frammentazione del Web per gli sviluppatori Web.

> [!IMPORTANT]
> Questo nuovo Microsoft Edge sostituisce automaticamente i Microsoft Edge legacy, che [non sono più supportati](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) nelle nuove versioni.

![Nuovo Microsoft Edge screenshot](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Avvio del nuovo Microsoft Edge

Il nuovo Microsoft Edge ![nuova Microsoft Edge icona](images/new_edge_logo.png) (rappresentato da un'icona a scorrimento blu e verde) viene aggiunto al menu Start e verrà avviato automaticamente quando si attiva un collegamento Web.

> [!NOTE]
> Quando si avvia per la prima volta la nuova Microsoft Edge in HoloLens 2, le impostazioni e i dati verranno importati da Microsoft Edge. Se si continua a usare i Microsoft Edge legacy dopo l'avvio del nuovo Microsoft Edge, i nuovi dati non verranno sincronizzati dai dati legacy Microsoft Edge al nuovo Microsoft Edge.

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
- Installazione delle estensioni (determinare se si usano estensioni che non funzionano correttamente HoloLens 2)
- Visualizzazione e contrassegno di un PDF
- Suono spaziale da una singola finestra del browser
- Aggiornamento automatico e manuale del browser
- Salvataggio di un PDF dal menu Stampa (con l'opzione "Salva in PDF")
- Estensione WebXR e 360 Viewer
- Ripristino del contenuto nella finestra corretta, quando si esplorano più finestre posizionate nell'ambiente

**Scenari e funzionalità non previsti:**
- Audio spaziale da più finestre con flussi audio simultanei
- "See it, say it"
- Stampa

**Principali problemi noti del browser:**

- L'anteprima della lente di ingrandimento nella tastiera olografica è stata disabilitata per il nuovo Microsoft Edge. Si spera di riabilitare questa funzionalità in un aggiornamento futuro, una volta che l'ingrandimento funziona correttamente.
- L'audio può essere riprodotto dalla finestra del browser errata se è aperta e attiva un'altra finestra del browser. È possibile risolvere questo problema chiudendo l'altra finestra attiva che non dovrebbe riprodurre l'audio.
- Quando si riproduce l'audio da una finestra del browser in modalità ["Seguimi",](hololens2-basic-usage.md#follow-me-stop-following)l'audio continuerà a essere riprodotto se si disabilita la modalità "Seguimi". È possibile risolvere questo problema interrompendo la riproduzione audio prima di disabilitare la modalità "Seguimi" o chiudendo la finestra con il **pulsante X.**
- L'interazione con le finestre Microsoft Edge attive può causare l'inattività imprevista di altre finestre dell'app 2D. È possibile riattivare queste finestre interagendo di nuovo con esse.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge insider

Il team Microsoft Edge rende disponibili tre canali di anteprima per la community di Edge Insider: Beta, Dev e Canary. L'installazione di un canale di anteprima non disinstalla la versione rilasciata di Microsoft Edge nel HoloLens 2 ed è possibile installarne più di una contemporaneamente. 

Visitare la [home Microsoft Edge Insider per](https://www.microsoftedgeinsider.com) altre informazioni sulla community Edge Insider. Per altre informazioni sui diversi canali Edge Insider e per iniziare, visitare la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)

Sono disponibili due metodi per installare i Microsoft Edge Insider per HoloLens 2:

**Installazione diretta nel dispositivo (attualmente disponibile solo per i dispositivi non gestiti)**
  1. Nel sito HoloLens 2 visitare la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Selezionare il **pulsante Download for HoloLens 2** per il canale Edge Insider che si vuole installare.
  1. Avviare il file msix scaricato dalla coda di download edge o dalla cartella "Download" del dispositivo (usando Esplora file).
  1. [Verrà avviato il programma](app-deploy-app-installer.md) di installazione dell'app.
  1. Selezionare il pulsante **Installa**.
  1. Al termine dell'installazione, sarà possibile trovare Microsoft Edge Beta, Dev o Canary come voce separata nell'elenco Tutte le app del menu Start. 

**Eseguire l'installazione tramite PC Portale di dispositivi di Windows (è [necessario che la modalità sviluppatore](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) sia abilitata HoloLens 2)**
  1. Nel PC visitare la pagina di [download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Selezionare il **pulsante freccia a discesa** accanto al pulsante "Download for Windows 10" (Scarica per Windows 10) per il canale Edge Insider che si vuole installare.
  1. Selezionare **HoloLens 2** nel menu a discesa.
  1. Salvare il file con estensione msix nella cartella "Download" del PC (o in un'altra cartella facilmente individuabile).
  1. Usare [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) nel PC per installare il file msix scaricato HoloLens 2.
  1. Al termine dell'installazione, sarà possibile trovare Microsoft Edge Beta, Dev o Canary come voce separata nell'elenco Tutte le app del menu Start. 

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso di WDAC per bloccare nuovi Microsoft Edge

Per gli amministratori IT che desiderano aggiornare i criteri [WDAC](windows-defender-application-control-wdac.md) per bloccare la nuova app Microsoft Edge, è necessario aggiungere quanto segue ai criteri.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gestione degli endpoint per il nuovo Microsoft Edge

Alcuni ambienti possono avere restrizioni di rete da tenere in considerazione. Per garantire un'esperienza uniforme con il nuovo edge, [abilitare questi endpoint Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Altre informazioni sugli endpoint attualmente [disponibili per HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Installare app Web
 > [!Note]
>A data [di Windows Holographic versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)l'app Web di Office non sarà più preinstallato.

È possibile usare il nuovo Edge per installare le app Web insieme Microsoft Store app. Ad esempio, è possibile installare l Microsoft Office app Web per visualizzare e modificare i file ospitati in SharePoint o OneDrive. Per installare l'app Web di Office, visitare https://www.office.com e selezionare il pulsante App **Disponibile** o **Installa Office** nella barra degli indirizzi. Selezionare **Installa per** confermare.

> [!IMPORTANT]
> La funzionalità app Web di Office è disponibile solo quando il HoloLens 2 ha una connessione Internet attiva.

### <a name="webxr-and-360-viewer"></a>Visualizzatore WebXR e 360

Il nuovo Microsoft Edge include il supporto per WebXR, che è il nuovo standard per la creazione di esperienze Web immersive (sostituendo WebVR). Molte esperienze Web immersive sono state progettate in base alla realtà virtuale (che sostituiscono il campo di visualizzazione con un ambiente virtuale), ma queste esperienze sono supportate anche da HoloLens 2. Lo standard WebXR consente anche esperienze Web immersive di realtà aumentata e mista che usano l'ambiente fisico. Con l'aumentare del tempo che gli sviluppatori dedicano a WebXR, si prevede che le nuove esperienze immersive di realtà aumentata e mista HoloLens 2 che i clienti possano provare.

L'estensione 360 Viewer è compilata su WebXR e viene installata automaticamente insieme al nuovo Microsoft Edge in HoloLens 2. Questa estensione Web offre la possibilità di guardare video a 360 gradi. YouTube offre la selezione più ampia di 360 video, quindi si consiglia di iniziare da qui.

#### <a name="how-to-use-webxr"></a>Come usare WebXR

1. Passare a un sito Web con supporto WebXR.
1. Selezionare il **pulsante Enter VR (Immetti** VR) nel sito Web. La posizione e la rappresentazione visiva di questo pulsante possono variare in base al sito Web, ma può essere simile a:

    ![Esempio di pulsante di immissione della realtà virtuale](images/75px-enter-vr.png)

1. La prima volta che si prova ad avviare un'esperienza WebXR in un dominio specifico, il browser chiederà il consenso per l'immissione di una visualizzazione immersiva e **selezionerà Consenti.**
1. Usare [HoloLens 2 per modificare](hololens2-basic-usage.md#the-hand-tracking-frame) l'esperienza.
1. Se l'esperienza non ha un pulsante **Esci,** usa il [movimento Avvia](hololens2-basic-usage.md#start-gesture) per tornare a casa.

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
- A seconda della complessità dell'esperienza WebXR, la frequenza dei fotogrammi può essere notevolmente più complessa.
- Il supporto per le giunzioni delle mani articolate in WebXR non è abilitato per impostazione predefinita. Gli sviluppatori possono abilitare il `edge://flags` supporto tramite attivando "WebXR Hand Input".
- 360 video da siti Web diversi da YouTube potrebbero non funzionare come previsto.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Commenti e suggerimenti su WebXR e visualizzatore 360

Condividere commenti e suggerimenti e bug con il team tramite la funzionalità **Invia commenti** e suggerimenti nel nuovo Microsoft Edge.

### <a name="new-settings-app"></a>Nuova app Impostazioni

Con questa versione verrà introdotto una nuova versione dell'app Impostazioni. La nuova app Impostazioni include nuove funzionalità e impostazioni espanse per HoloLens 2 nelle aree seguenti: Audio, Sospensione di Power &, Rete & Internet, App, Account, Accessibilità e altro ancora.

> [!NOTE]
> Poiché la nuova app Impostazioni è distinta dall'app Impostazioni legacy, tutte le finestre Impostazioni posizionate in precedenza nell'ambiente verranno rimosse al momento dell'aggiornamento.

![Home page dell'app Nuove impostazioni](images/new-settings-app.png)

**Nuove funzionalità e impostazioni**
- Ricerca delle impostazioni: cercare le impostazioni dalla home page Impostazioni usando parole chiave o il nome dell'impostazione.
- Suono > sistema:
  - Dispositivi audio di input e output: scegliere in modo indipendente i dispositivi audio di input e output( ad esempio, ascoltare l'audio tramite le cuffi Bluetooth o usare un microfono USB-C per l'input audio).
    > [!NOTE]
    > I microfoni Bluetooth non sono supportati da HoloLens 2.
  - Volume dell'app: regolare in modo indipendente il volume di ogni app. Vedere [controllo del volume per app.](#per-app-volume-control)
- Sistema > sospensione & sospensione: scegliere quando il dispositivo deve andare in sospensione dopo un periodo di inattività.
- Batteria > sistema: abilitare manualmente la risparmio batteria o impostare una soglia della batteria a quel punto risparmio batteria si attiva automaticamente.
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

#### <a name="display-color-calibration"></a>Calibrazione dei colori dello schermo



Con questa nuova impostazione è possibile selezionare un profilo colori alternativo per la HoloLens 2 schermo. In questo modo i colori possono risultare più accurati, in particolare a livelli di luminosità inferiori dello schermo. La calibrazione dei colori dello schermo è disponibile nell'app Impostazioni, nella pagina Calibrazione > sistema.

> [!NOTE]
> Poiché questa impostazione salva un nuovo profilo colori nel firmware dello schermo, si tratta di un'impostazione per dispositivo e non univoca per ogni account utente.

##### <a name="how-to-use-display-color-calibration"></a>Come usare la calibrazione dei colori dello schermo

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
> Ecco alcuni suggerimenti utili da tenere presenti durante l'uso dell'impostazione di calibrazione del colore di visualizzazione:
> - È possibile eseguire di nuovo la calibrazione del colore di visualizzazione da Impostazioni ogni volta che si desidera
> - Se qualcuno nel dispositivo ha usato in precedenza l'impostazione per modificare i profili colori, la data/ora della modifica più recente verrà riflessa nella pagina Impostazioni
> - Quando si esegue di nuovo la calibrazione dei colori dello schermo, il profilo colori salvato in precedenza verrà evidenziato e il profilo 0 non verrà visualizzato (poiché il profilo 0 rappresenta il profilo colori originale dello schermo)
> - Se si vuole ripristinare il profilo colori originale dello schermo, è possibile farlo dalla pagina Impostazioni (vedere come reimpostare il [profilo colori](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Come reimpostare il profilo colori 

Se non si è soddisfatti del profilo colori personalizzato salvato nel HoloLens 2, è possibile ripristinare il profilo colori originale del dispositivo:
1. Avviare **l'app Impostazioni** e passare a **Calibrazione > sistema**.
1. In **Calibrazione colori visualizzazione** selezionare il pulsante Ripristina profilo **colori** predefinito.
1. Quando si apre la  finestra di dialogo, selezionare Riavvia se si è pronti per riavviare il HoloLens 2 e applicare le modifiche.

#### <a name="top-display-color-calibration-known-issues"></a>Problemi noti relativi alla calibrazione dei colori dello schermo superiore

- Nella pagina Impostazioni la stringa di stato che indica quando è stata modificata l'ultima modifica del profilo colori non sarà aggiornata fino a quando non si ricarica la pagina impostazioni.
    - Soluzione alternativa: selezionare un'altra pagina Impostazioni e quindi selezionare nuovamente la pagina Calibrazione.

#### <a name="default-app-picker"></a>Selezione app predefinita

Quando si attiva un collegamento ipertestuale o si apre un tipo di file con più di un'app installata che lo supporta, viene visualizzata una nuova finestra aperta che richiede di selezionare l'app installata che deve gestire il tipo di file o collegamento. In questa finestra è anche possibile scegliere di fare in modo che l'app selezionata gestirà il file o il tipo di collegamento "Once" o "Always".

Se si sceglie "Sempre" ma in un secondo momento si vuole modificare l'app che gestisce un file o un tipo di collegamento specifico, è possibile reimpostare le impostazioni predefinite salvate in Impostazioni **> App**. Scorrere fino alla fine della  pagina e selezionare il pulsante Cancella in "App predefinite per i tipi di file" e/o "App predefinite per i tipi di collegamento". A differenza dell'impostazione simile nei PC desktop, non è possibile reimpostare le impostazioni predefinite dei singoli tipi di file.

#### <a name="per-app-volume-control"></a>Controllo del volume per app

Ora, in questa build di Windows, gli utenti possono modificare manualmente il livello di volume di ogni app. Ciò consente agli utenti di concentrarsi meglio sulle app necessarie o di ascoltare meglio quando usano più app. Ad esempio, la necessità di disattivare il volume di un'app chiamando un'altra persona per assistenza remota in un'altra.

Per impostare il volume di una singola app, passare a **Impostazioni** suono di sistema e in Opzioni audio  ->    ->  avanzate selezionare Volume app **e preferenze del dispositivo.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Scorrimento rapido verso il testo

Alcuni clienti trovano più veloce "digitare" sulle tastiere virtuali scorrendo la forma della parola che intende digitare e questa funzionalità è disponibile in anteprima per la tastiera olografica. È possibile scorrere una parola alla volta passando la punta del dito attraverso il piano della tastiera olografica, scorrendo la forma della parola e quindi ritirando la punta del dito dal piano della tastiera. È possibile scorrere rapidamente le parole di follow-up senza dover premere la barra spaziatrice rimuovendo il dito dalla tastiera tra le parole. Si saprà che la funzionalità funziona se viene visualizzata una traccia di scorrimento rapido che segue il movimento del dito sulla tastiera.

Si noti che questa funzionalità può essere difficile da usare e master a causa della natura di una tastiera olografica in cui non si prova resistenza contro il dito (a differenza di un display del telefono cellulare). 

### <a name="power-menu-from-start"></a>Menu Di alimentazione da Start

Nuovo menu che consente all'utente di disconnettersi, arrestare e riavviare il dispositivo. Indicatore nell'elenco di schermata Start HoloLens che indica quando è disponibile un aggiornamento del sistema.

#### <a name="how-to-use"></a>Uso

1. Aprire il schermata Start HoloLens usando il [movimento Start](hololens2-basic-usage.md#start-gesture) o pronunciando "Vai a Start".

2. Si noti l'icona con i puntini di sospensione (...) accanto all'immagine del profilo utente:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Selezionare l'immagine del profilo utente usando le mani o il comando vocale "Power".

4. Viene visualizzato un menu con le opzioni Disconnetti, Riavvia o Arresta il dispositivo:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Selezionare le opzioni di menu per disconnettersi, riavviare o arrestare HoloLens. L'opzione Disconnessione potrebbe non essere disponibile se il dispositivo è configurato per un singolo [account Microsoft (MSA)](hololens-identity.md)o un account locale.

6. Chiudere il menu toccando un altro punto o chiudendo il menu Start con il movimento Avvia.

#### <a name="update-indicator"></a>Indicatore di aggiornamento

Quando è disponibile un aggiornamento, l'icona con i puntini di sospensione si accende per indicare che un riavvio installerà l'aggiornamento Anche le opzioni di menu cambiano per riflettere la presenza dell'aggiornamento.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Più utenti elencati nella schermata di accesso

In precedenza la schermata di accesso mostrava solo l'utente connesso più di recente, nonché un punto di ingresso "Altro utente". Il feedback dei clienti non è sufficiente se più utenti hanno eseguito l'accesso al dispositivo. Era comunque necessario digitare nuovamente il nome utente e così via.

Introdotto in questa build  di Windows, quando si seleziona Altro utente che si trova a destra del campo di immissione PIN, nella schermata Di accesso verranno visualizzati più utenti con cui è stato eseguito l'accesso al dispositivo in precedenza. In questo modo gli utenti possono selezionare il proprio profilo utente e quindi accedere usando le Windows Hello credenziali. È anche possibile aggiungere un nuovo utente al dispositivo da questa pagina Altri utenti tramite il **pulsante Aggiungi account.**

Nel menu Altri utenti il pulsante Altri utenti visualizza l'ultimo utente che ha eseguito l'accesso al dispositivo. Selezionare questo pulsante per tornare alla schermata Di accesso per questo utente.

![Impostazione predefinita della schermata di accesso](./images/multiusers1.jpg)

<br>

![Schermata di accesso di altri utenti](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Supporto microfono esterno USB-C

> [!IMPORTANT]
> L'inserimento di **un microfono USB non lo imposta automaticamente come dispositivo di input.** Quando si collega un set di cuffia USB-C, gli utenti osserveranno che l'audio della cuffia verrà reindirizzato automaticamente alle cuffia, ma il sistema operativo HoloLens assegna la priorità all'array di microfoni interni sopra qualsiasi altro dispositivo di input. **Per usare un microfono USB-C, seguire questa procedura.**

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

Sfortunatamente i microfoni Bluetooth non sono ancora supportati in HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Risoluzione dei problemi relativi ai microfoni USB-C

Tenere presente che alcuni microfoni USB-C segnalano erroneamente se stessi sia come *microfono che come* altoparlante. Si tratta di un problema con il microfono e non con HoloLens. Quando si collega uno di questi microfoni a HoloLens, l'audio potrebbe essere perso. Fortunatamente è disponibile una semplice correzione.  

In **Impostazioni suono** di sistema impostare in modo esplicito gli altoparlanti predefiniti (driver audio della funzionalità  ->    ->   **analoga)** come **dispositivo predefinito.** HoloLens deve ricordare questa impostazione anche se il microfono viene rimosso e riconnesso in un secondo momento.

![Risoluzione dei problemi relativi ai microfoni USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Accesso automatico dei visitatori per chioschi in modalità tutto schermo

Questa nuova funzionalità consente l'accesso automatico agli account Visitor da usare per le modalità tutto schermo.

Per una configurazione non AAD, per configurare un dispositivo per l'accesso automatico dei visitatori:

1. Creare un pacchetto di provisioning che:
    1. Configura le **impostazioni di runtime/AssignedAccess per** consentire gli account Visitor.
    1. Facoltativamente, registra il dispositivo in MDM **(Impostazioni di runtime/Area di lavoro/Registrazioni)** in modo che possa essere gestito in un secondo momento.
    1. Non creare un account locale
1. [Applicare il pacchetto di provisioning](hololens-provisioning.md).

Per una configurazione di AAD, gli utenti possono ottenere un risultato simile a questo oggi senza questa modifica. I dispositivi aggiunti ad AAD configurati per la modalità tutto schermo possono accedere a un account Visitatore con un solo tocco pulsante dalla schermata di accesso. Dopo aver eseguito l'accesso all'account visitatore, il dispositivo non richiederà di nuovo l'accesso fino a quando il visitatore non viene disconnesso in modo esplicito dal menu Start o non viene riavviato il dispositivo.

L'accesso automatico del visitatore può essere gestito tramite [criteri URI OMA](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) personalizzati:

- Valore URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Criteri  | Descrizione   | Configurazioni  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Consente a un visitatore di accedere automaticamente a un chiosco multimediale   | 1 (Sì), 0 (No, impostazione predefinita).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Usare le nuove impostazioni e le nuove app edge in modalità tutto schermo

Quando si includono app in [chioschi](hololens-kiosk.md)in modalità tutto schermo, un amministratore IT spesso aggiunge l'app al chiosco multimediale ma usa l'ID modello utente dell'app (AUMID). Poiché sia l'app Impostazioni che l'app Microsoft Edge sono considerate nuove app e diverse rispetto alle app meno recenti che usano AUMID per tali app, sarà necessario aggiornare per usare la nuova app AUMID.

Quando si modifica un chiosco multimediale per includere le nuove app, è consigliabile aggiungere nel nuovo AUMID e lasciare quella precedente. In questo modo si creerà una transizione semplice quando gli utenti aggiornano il sistema operativo e non sarà necessario ricevere nuovi criteri per continuare a usare la modalità tutto schermo come previsto.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| App impostazioni precedente       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nuova app impostazioni       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| App Microsoft Edge precedente | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nuova app Microsoft Edge app | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifiche del comportamento della modalità tutto schermo per la gestione degli errori

Nelle build precedenti, se un dispositivo ha una configurazione tutto schermo, ovvero una combinazione di accesso assegnato a livello globale e accesso assegnato ai membri del gruppo AAD, se la determinazione dell'appartenenza al gruppo AAD non è riuscita, l'utente visualizza " nulla visualizzato nel menu[Start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)".

A partire da questa versione di Windows, l'esperienza tutto schermo verrà fallback alla configurazione globale della modalità tutto schermo (se presente) in caso di errori durante la modalità tutto schermo del gruppo AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nuovi URI delle impostazioni per la visibilità delle impostazioni di pagina

In [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) sono stati aggiunti i criteri [Impostazioni/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visibili all'interno dell'app Impostazioni. PageVisibilityList è un criterio che consente agli amministratori IT di impedire la visualizzazione o l'accessibilità di pagine specifiche nell'app Impostazioni di sistema oppure di eseguire questa operazione per tutte le pagine tranne quelle specificate.

Se si visita [Visibilità impostazioni pagina](settings-uri-list.md), è possibile trovare le istruzioni per usare questo provider di servizi di configurazione e l'elenco degli URI disponibili nelle versioni precedenti.

Si sta espandendo l'elenco degli URI delle impostazioni disponibili, che gli amministratori IT possono gestire. Alcuni di questi URI sono per le nuove aree disponibili all'interno della nuova app Impostazioni. Se si usano i criteri Settings/PageVisibilityList, esaminare l'elenco seguente e modificare le pagine consentite o bloccate in base alle esigenze.

> [!NOTE]
> **Deprecato: ms-settings:network-proxy**
>
> Una pagina delle impostazioni è deprecata in queste build più nuove. La vecchia **pagina & proxy Internet** non è più disponibile come impostazione  >   globale. Le nuove impostazioni del proxy per ogni connessione sono disponibili in **Proprietà** Wi-Fi di Rete & Internet o &  >    >   **Proprietà**  >  **Ethernet**  >  **Internet**.

<br>

| Pagina Impostazioni                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| App > app & funzionalità                               | `ms-settings:appsfeatures`                         |
| App > app & funzionalità > opzioni avanzate          | `ms-settings:appsfeatures-app`                     |
| App > mappe offline                                  | `ms-settings:maps`                                 |
| App > mappe offline > Mappe di download                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivi > mouse                                      | `ms-settings:mouse`                                |
| Dispositivi > USB                                        | `ms-settings:usb`                                  |
| Modalità & Internet > aereo                   | `ms-settings:network-airplanemode`                 |
| Privacy > Generale                                    | `ms-settings:privacy-general`                      |
| Privacy > input penna & personalizzazione della digitazione             | `ms-settings:privacy-speechtyping`                 |
| Privacy > Motion                                     | `ms-settings:privacy-motion`                       |
| Bordi dello screenshot > privacy                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Privacy > screenshot e app                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batteria > sistema                                     | `ms-settings:batterysaver`                         |
| Batteria > sistema                                     | `ms-settings:batterysaver-settings`                |
| Suono > sistema                                       | `ms-settings:sound`                                |
| System > Sound > volume app e preferenze del dispositivo | `ms-settings:apps-volume`                          |
| System > Sound > Gestire i dispositivi audio              | `ms-settings:sound-devices`                        |
| Configurazione > archiviazione > di Sensore memoria         | `ms-settings:storagepolicies`                      |
| Ora & lingua > data & ora                        | `ms-settings:dateandtime`                          |
| Tastiera & lingua > tempo                           | `ms-settings:keyboard`                             |
| Lingua & lingua > lingua                           | `ms-settings:language`                             |
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

Condividere le informazioni con i dispositivi Windows 10 vicino, inclusi i PC e altri HoloLens 2 dispositivi. È possibile provare in **Impostazioni** Esperienze condivise del sistema per condividere file o URL da un  ->    ->   HoloLens a un PC. Per altri dettagli, leggere altre informazioni su come condividere [elementi con i dispositivi vicini in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Questa funzionalità può essere gestita tramite [Connectivity/AllowConnectedDevices.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Nuove tracce di diagnostica del sistema operativo

Oltre ai precedenti strumento di risoluzione dei problemi all'interno dell'app Impostazioni, è stato aggiunto un nuovo strumento di risoluzione dei problemi con l'aggiunta della nuova app Impostazioni per gli aggiornamenti del sistema operativo. Passare a **Impostazioni Aggiorna** risoluzione dei  ->  **problemi &amp; di**  >    >  **Windows Update** e selezionare **Avvia**. In questo modo è possibile raccogliere tracce durante la riproduzione del problema con gli aggiornamenti del sistema operativo per facilitare la risoluzione dei problemi relativi all'IT o al supporto tecnico.

### <a name="delivery-optimization-preview"></a>Ottimizzazione recapito anteprima

Con questo aggiornamento di HoloLens, Windows Holographic for Business le impostazioni di ottimizzazione del recapito per ridurre il consumo di larghezza di banda per i download da più dispositivi HoloLens. Una descrizione più completa di questa funzionalità insieme alla configurazione di rete consigliata è disponibile qui: Ottimizzazione recapito [per Windows 10 aggiornamenti](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

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

### <a name="it-admin---update-checklist"></a>Amministratore IT - Elenco di controllo aggiornamenti

Questo elenco di controllo consente di conoscere i nuovi elementi aggiunti in questo aggiornamento delle funzionalità che possono influire sulle configurazioni di gestione dei dispositivi correnti o sulle nuove funzionalità che è possibile iniziare a usare.

#### <a name="updates-to-kiosk-mode"></a>Aggiornamenti alla modalità tutto schermo

✔️ nuovi [**AUMID per le nuove app in modalità tutto schermo:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Se in precedenza si usava l'app Impostazioni o Microsoft Edge app in modalità tutto schermo, queste app sono state sostituite con nuove app che usano un ID app diverso. Di seguito è consigliabile leggere [Le nuove app AUMID per le nuove app in modalità tutto schermo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) In questo modo si continuerà a avere l'app Impostazioni nel chiosco multimediale o si includerà la nuova app Microsoft Edge app. Queste modifiche possono essere eseguite ora e distribuite in tutti i dispositivi e consentono una transizione più agevole all'aggiornamento.

✔️ accesso [**automatico del visitatore per chioschi in modalità tutto schermo**](#visitor-auto-logon-for-kiosks): 

I visitatori possono ora accedere automaticamente a un chiosco multimediale. Questo comportamento è attiva per impostazione predefinita, ma può essere gestito e disabilitato.

✔️ [**errore di modalità tutto schermo migliorato:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Se l'appartenenza al gruppo AAD dell'utente di AAD connesso non viene determinata correttamente, viene usata la configurazione globale della modalità tutto schermo per il menu Start (se presente) in caso contrario all'utente viene visualizzato un menu Start vuoto. Anche se il menu Start vuoto non è una configurazione che è possibile impostare direttamente, questa nuova gestione potrebbe essere qualcosa di cui informare il reparto di supporto se si usano i chioschi in modalità tutto schermo, in quanto ciò potrebbe essere applicabile alle configurazioni o potrebbe essere necessario apportare nuove modifiche alle configurazioni di accesso assegnate.

#### <a name="updates-to-page-settings-visibility"></a>Aggiornamenti alla visibilità delle impostazioni di pagina

✔️ nuovi [**URI delle impostazioni per la visibilità delle impostazioni di pagina**](#new-settings-uris-for-page-settings-visibility)

Se si usa la [visibilità delle](settings-uri-list.md) impostazioni di pagina, è possibile apportare modifiche agli URI esistenti consentiti o bloccati.

#### <a name="updates-for-your-wdac-policy"></a>Aggiornamenti per i criteri WDAC
✔️ se in precedenza si bloccava Microsoft Edge tramite WDAC, è necessario aggiornare i criteri WDAC. Esaminare quanto segue e usare il codice di esempio fornito.
#### <a name="enable-new-endpoints-for-edge"></a>Abilitare nuovi endpoint per Edge
✔️ se si dispone di un'infrastruttura che prevede la configurazione di endpoint di rete, ad esempio proxy o firewall, abilitare questi nuovi endpoint per la nuova app Microsoft Edge rete.

#### <a name="newly-configurable-items"></a>Elementi appena configurabili

✔️ Configurare [la diagnostica di fallback:](#configuring-fallback-diagnostics-via-settings-app)è possibile configurare se e chi può raccogliere la diagnostica di fallback.

✔️ elementi[con i dispositivi vicini:](#share-things-with-nearby-devices)è possibile disabilitare la nuova funzionalità di condivisione nelle vicinanze.

✔️ configurazione [delle impostazioni dei criteri](#configuring-policy-settings-for-the-new-microsoft-edge)per il nuovo Microsoft Edge : esaminare le nuove configurazioni disponibili per Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nuovo strumento di diagnostica

✔️[nuove tracce di diagnostica del sistema operativo:](#new-os-diagnostic-traces)raccogliere i log correlati agli aggiornamenti del sistema operativo.

### <a name="improvements-and-fixes-in-the-update"></a>Miglioramenti e correzioni nell'aggiornamento:

- [La diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics) includerà anche informazioni aggiuntive sul dispositivo per il numero di serie e la versione del sistema operativo.
- Risolve un problema relativo alla distribuzione di applicazioni line-of-business tramite pacchetti di provisioning di runtime.
- Correzione di un problema relativo alla creazione di report sullo stato di installazione dell'applicazione line-of-business.
- Correzione di un problema relativo alla persistenza di nuovi pacchetti di app tra le reimpostazioni dei dispositivi.
- Correzione di un problema che potrebbe causare la digitazione di simboli non corretti in Edge per i clienti giapponesi.
- Migliora la resilienza degli aggiornamenti del sistema operativo per le app preinstallate, ad esempio Edge. 
- Risolve un problema di affidabilità degli aggiornamenti che influisce sull'installazione Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, versione 20H2 - Aggiornamento di maggio 2021
- Build 19041.1146

Miglioramenti e correzioni nell'aggiornamento:
- Questo aggiornamento qualitativo mensile non contiene modifiche di primo piano. È quindi necessario provare la build più recente, Windows Holographic, versione 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, versione 1903 - Aggiornamento di maggio 2021
- Build 18362.1110

Miglioramenti e correzioni nell'aggiornamento:
- Questo aggiornamento qualitativo mensile non contiene modifiche di valore. **Questa build non riceverà più aggiornamenti mensili del servizio**. Si consiglia di provare la build più recente, Windows Holographic, versione 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, versione 20H2 - Aggiornamento di aprile 2021
- Build 19041.1144

Miglioramenti e correzioni nell'aggiornamento:

- Correzione di un problema relativo alla creazione di report sullo stato di installazione dell'applicazione line-of-business.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, versione 1903 - Aggiornamento di aprile 2021
- Build 18362.1108

Miglioramenti e correzioni nell'aggiornamento:

- Risolve un problema a causa del quale l'app Impostazioni si arresta in modo anomalo quando si tenta di modificare una password per un account locale.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versione 20H2 - Aggiornamento di marzo 2021
- Build 19041.1140

Miglioramenti e correzioni nell'aggiornamento:

- I clienti che usano AdvancedPhotoCapture o LowLagPhotoCapture per acquisire foto con HoloLens 2 sono ora in grado di recuperare la posizione della fotocamera fino a 3 secondi dopo l'acquisizione della foto.
- Correzione di una perdita di memoria nel Portale di dispositivi, il problema ha causato un aumento dell'utilizzo della memoria da parte del servizio che ha causato l'allocazione della memoria da parte di altre applicazioni.
- È stato risolto un problema a causa del quale gli utenti registrati nell'implementazione a fasi non sono in grado di accedere al dispositivo.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, versione 1903 - Aggiornamento di marzo 2021
- Build 18362.1102

Miglioramenti e correzioni nell'aggiornamento:

- Correzione di una perdita di memoria nel Portale di dispositivi, il problema ha causato un aumento dell'utilizzo della memoria da parte del servizio che ha causato l'allocazione della memoria da parte di altre applicazioni.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, versione 20H2 - Aggiornamento di febbraio 2021
- Build 19041.1136

Miglioramenti e correzioni nell'aggiornamento:

- Correzione di un problema relativo alla configurazione iniziale del dispositivo e agli aggiornamenti delle app dello Store.
- Risolve un problema relativo agli aggiornamenti e ai voli per le versioni successive di HoloLens.
- Rimozione dei certificati preinstallati inutilizzati dall'archivio radice eSIM dai dispositivi HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versione 1903 - Aggiornamento di febbraio 2021
- Build 18362.1098

Questo aggiornamento qualitativo mensile non contiene modifiche di valore. È quindi necessario provare le build più recenti per Windows Holographic versione 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versione 20H2 - Aggiornamento di gennaio 2021
- Build 19041.1134

Miglioramenti e correzioni nell'aggiornamento:

- Prestazioni migliorate durante l'avvio, la ripresa e il cambio utente quando sono presenti molti utenti nel dispositivo.
- Aggiunta del supporto arm32 per [la modalità di ricerca](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versione 1903 - Aggiornamento di gennaio 2021
- Build 18362.1091

Questo aggiornamento qualitativo mensile non contiene modifiche di valore. È quindi necessario provare le build più recenti per Windows Holographic versione 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic versione 20H2 - Aggiornamento di dicembre 2020
- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Installare app in HoloLens 2 tramite Programma di installazione app

Verrà aggiunta **una nuova funzionalità (Programma di installazione app)** per consentire di installare le applicazioni in modo più semplice nei HoloLens 2 dispositivi. La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti.** Per evitare interruzioni per le aziende, il programma di installazione delle app non **sarà attualmente disponibile per** i dispositivi gestiti.  

Un dispositivo viene considerato "gestito" **se si** verifica una delle condizioni seguenti:
- MDM [registrato](hololens-enroll-mdm.md)
- Configurato con il [pacchetto di provisioning](hololens-provisioning.md)
- [L'identità utente](hololens-identity.md) Azure AD

È ora possibile installare le app senza dover abilitare la modalità sviluppatore o usare Portale di dispositivi.  È sufficiente scaricare (tramite USB o tramite Edge) il bundle Appx nel dispositivo e passare al bundle Appx nel Esplora file per chiedere di avviare l'installazione.  In alternativa, [avviare un'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Proprio come le app installate dal Microsoft Store o il sideload usando la funzionalità di distribuzione di [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) app LOB [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) MDM, le app devono essere firmate digitalmente con lo strumento di firma e il certificato usato per firmare deve essere considerato attendibile dal dispositivo HoloLens prima che l'app possa essere distribuita.

**Istruzioni di installazione dell'applicazione.**

1.  Assicurarsi che il dispositivo non sia considerato gestito
1.  Assicurarsi che il HoloLens 2 dispositivo sia acceso e connesso al PC
1.  Assicurarsi di aver eseguito l'accesso HoloLens 2 dispositivo
1.  Nel PC passare all'app personalizzata e copiare yourapp.appxbundle indevicename\Internal Storage\Downloads.   Dopo aver completato la copia del file, è possibile disconnettere il dispositivo
1.  Dal dispositivo HoloLens 2 aprire il menu Start, selezionare Tutte le app e avviare l Esplora file app.
1.  Passare alla cartella Download. Potrebbe essere necessario nel pannello sinistro dell'app selezionare Prima questo dispositivo, quindi passare a Download.
1.  Selezionare il file yourapp.appxbundle.
1.  Il Programma di installazione app verrà avviato. Selezionare il pulsante Installa per installare l'app.
L'app installata verrà avviata automaticamente al termine dell'installazione.

Per testare questo flusso, è possibile trovare app di esempio in [GitHub di](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) esempi universali di Windows.

Informazioni sul processo completo di [installazione delle app in HoloLens 2 con Programma di installazione app](app-deploy-app-installer.md).  

![Installazione di esempi MRTK tramite Programma di installazione app](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Miglioramenti e correzioni nell'aggiornamento:

- Il tracciamento manuale ora mantiene il rilevamento in molti nuovi casi in cui la mano in precedenza sarebbe stata persa.  In alcuni di questi nuovi casi, solo la posizione del palmo continua ad aggiornare in base alla mano reale dell'utente, mentre le altre giunzioni vengono dedote in base a una posizione precedente.  Questa modifica consente di migliorare la coerenza di rilevamento nei movimenti, ad esempio schiaffi, lanci, ambito e clapping.  È utile anche nei casi in cui la mano è vicina a una superficie o in cui è in possesso di un oggetto.  Quando vengono dedoscite le giunzioni della mano, il valore di accuratezza [per](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) giunzione verrà impostato su "Approximate" anziché su "High".
- Risolto un problema a causa del quale la reimpostazione del PIN Azure AD gli account visualizzavano un errore "Si è verificato un errore.
- Gli utenti dovrebbero vedere meno arresti anomali della configurazione guidata post-avvio quando avviano ET, Iris dall'app impostazioni, nuovo utente o avviso popup di notifica.
- Gli utenti devono avere un fuso orario corretto in uscita dalla Versione di OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di dicembre 2020
- Build 18362.1088

Questo aggiornamento qualitativo mensile non contiene modifiche di primo piano. Si consiglia di provare la versione più recente di Windows Holographic, versione 20H2 - Aggiornamento di dicembre 2020 e la nuova funzionalità Programma di installazione app aggiunta nella build.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versione 20H2
- Build 19041.1128

Windows Holographic versione 20H2 è ora disponibile e offre un'ottima serie di nuove funzionalità per HoloLens 2 utenti e professionisti IT. Dal posizionamento automatico degli occhi, a Gestione certificati in Impostazioni, alle funzionalità migliorate della modalità tutto schermo e alle nuove funzionalità di configurazione di Autopilot. Questo nuovo aggiornamento consente ai team IT di assumere un controllo più granulare per la configurazione e la gestione dei dispositivi HoloLens e offre agli utenti esperienze olografiche ancora più semplici. 

Questa versione più recente è un aggiornamento mensile alla versione 2004, ma questa volta sono incluse nuove funzionalità. Il numero di build principale rimarrà invariato e Windows Update una versione mensile alla versione 2004 (build 19041). È possibile esaminare il numero di build nella schermata Impostazioni > Informazioni su per verificare di essere nella build più recente disponibile 19041.1128+. Per eseguire l'aggiornamento alla versione più recente, aprire l'app Impostazioni, passare a Aggiorna & Sicurezza e toccare Controlla aggiornamenti. Per altre informazioni su come gestire gli aggiornamenti di HoloLens, visitare [questa pagina.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Novità di Windows Holographic, versione 20H2  

| Funzionalità                                              | Descrizione                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Supporto della posizione dell'occhio automatico](hololens-release-notes.md#auto-eye-position-support) | Calcola attivamente le posizioni degli occhi senza che gli utenti passano attraverso la calibrazione del tracciamento oculare.   |
| [Gestione certificati](hololens-release-notes.md#certificate-manager)   | Consente a nuovi metodi più semplici di installare e rimuovere certificati dall'app Impostazioni.     |
| [Avvio automatico del provisioning da USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Il provisioning dei pacchetti nelle unità USB richiede automaticamente la pagina di provisioning nella Configurazione automatica.                                                         |
| [Confermare automaticamente i pacchetti di provisioning nella Configurazione automatica](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | I pacchetti di provisioning vengono applicati automaticamente durante la configurazione automatica dalla pagina di provisioning.                                                         |
| [Provisioning automatico senza usare l'interfaccia utente](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Come combinare l'avvio automatico del provisioning e la conferma automatica insieme. |
| [Uso di Autopilot con Wi-Fi connessione](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Usare autopilot dai dispositivi Wi-Fi senza la necessità di una scheda ethernet. |
| [Tenantlockdown CSP e Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Dopo aver applicato la registrazione del tenant e i criteri, il dispositivo può essere registrato in tale tenant solo ogni volta che il dispositivo viene reimpostato o nuovamente lampeggiato. |
| [Accesso assegnato globale](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nuovo metodo di configurazione per la modalità tutto schermo per più app che applica la modalità tutto schermo a livello di sistema, rendendola applicabile a tutti.                  |
| [Avviare automaticamente un'app in modalità tutto schermo multi-app](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Imposta l'avvio automatico di un'applicazione quando si accede in modalità tutto schermo a più app.                                                        |
| [Modifiche del comportamento della modalità tutto schermo per la gestione degli errori](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | L'errore della modalità tutto schermo ha ora un fallback restrittivo.                                                                                                |
| [Criteri di HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nuovi criteri per HoloLens.     |
| [Memorizzare nella cache Azure AD appartenenza al gruppo per la modalità tutto schermo offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | I nuovi criteri consentono agli utenti di usare la cache delle appartenenze ai gruppi per usare la modalità tutto schermo offline per un numero di giorni impostato.                                        |
| [Nuovi criteri di restrizione dei dispositivi per HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | I criteri di gestione dei dispositivi sono stati abilitati HoloLens 2.                                                                                |
| [Nuovi criteri di risparmio energia per HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nuovi criteri supportati per le impostazioni di timeout di alimentazione.  |
| [Aggiornare i criteri](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Criteri appena abilitati che consentono il controllo degli aggiornamenti.           |
| [Visibilità della pagina Impostazioni abilitata per HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Criteri per selezionare le pagine da visualizzare nell'app Impostazioni.             |
| [Modalità di ricerca](hololens-release-notes.md#research-mode) | Uso della modalità di ricerca HoloLens 2. |
| [Lunghezza registrazione aumentata](hololens-release-notes.md#recording-length-increased) | Le registrazioni MRC non hanno più un massimo di 5 minuti. |
| [Miglioramenti e correzioni nell'aggiornamento](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correzioni aggiuntive nell'aggiornamento.   |

### <a name="auto-eye-position-support"></a>Supporto della posizione dell'occhio automatico

In HoloLens 2, le posizioni oculare consentono un posizionamento accurato dell'ologramma, una comoda esperienza di visualizzazione e una migliore qualità dello schermo. Le posizioni oculare vengono calcolate internamente come parte del calcolo del tracciamento oculare. Tuttavia, ciò richiede che ogni utente eserciti la calibrazione del tracciamento oculare, anche quando l'esperienza potrebbe non richiedere l'input dello sguardo fisso.

**Auto Eye Position (AEP)** abilita questi scenari con un modo senza interazione per calcolare le posizioni oculare per l'utente. Auto Eye Position inizia a lavorare automaticamente in background dal momento in cui l'utente attiva il dispositivo. Se l'utente non ha una calibrazione del tracciamento oculare precedente, La posizione oculare automatica inizierà a fornire le posizioni degli occhi dell'utente al sistema di visualizzazione dopo un tempo di elaborazione di 20-30 secondi. I dati utente non vengono resi persistenti nel dispositivo e quindi questo processo viene ripetuto se l'utente si disconnette e riattiva il dispositivo o se il dispositivo viene riavviato o riattivato dalla sospensione.

Esistono alcune modifiche al comportamento del sistema con la funzionalità Posizione oculare automatica quando un utente non bilanciato inserisce il dispositivo. In questo contesto, un utente non bilanciato fa riferimento a un utente che non ha mai passato il processo di calibrazione del tracciamento oculare nel dispositivo in precedenza.

| Applicazione attiva | Comportamento precedente | Comportamento da Windows Holographic, versione 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| App non abilitata per lo sguardo o Holographic Shell |Viene visualizzata la finestra di dialogo di richiesta di calibrazione del tracciamento oculare. | Non viene visualizzata alcuna richiesta. |
| App abilitata per lo sguardo | Viene visualizzata la finestra di dialogo di richiesta di calibrazione del tracciamento oculare. | La richiesta di calibrazione del tracciamento oculare viene visualizzata solo quando l'applicazione accede al flusso dello sguardo fisso. |

Se l'utente passa da un'applicazione non abilitata per lo sguardo a un'applicazione che accede ai dati dello sguardo, verrà visualizzata la richiesta di calibrazione. 

Tutti gli altri comportamenti del sistema saranno simili a quando l'utente corrente non ha una calibrazione del tracciamento oculare attiva. Ad esempio, il movimento Di avvio con una mano non verrà abilitato. Non verrà apportata alcuna modifica all'esperienza out-of-box per la configurazione iniziale.

Per le esperienze che richiedono dati dello sguardo fisso o un posizionamento ologramma molto preciso, è consigliabile che gli utenti non bilanciati esereranno la calibrazione del tracciamento oculare. È accessibile dal prompt di calibrazione del tracciamento oculare o avviando l'app Impostazioni dal menu Start e quindi selezionando Calibrazione > sistema > calibrazione **oculare > Esegui** calibrazione oculare .

Queste informazioni sono disponibili in un secondo momento con [altre informazioni di calibrazione.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Gestione certificati

- Strumenti di controllo, diagnosi e convalida migliorati per la sicurezza e la conformità dei dispositivi tramite il nuovo gestore di certificati. Questa funzionalità consentirà di distribuire, risolvere i problemi e convalidare i certificati su larga scala in ambienti commerciali.

In Windows Holographic versione 20H2 viene aggiunto un gestore di certificati nell'app HoloLens 2 impostazioni. Passare a **Impostazioni > aggiornamento & certificati > sicurezza**. Questa funzionalità offre un modo semplice e semplice per visualizzare, installare e rimuovere i certificati nel dispositivo. Con il nuovo gestore di certificati, gli amministratori e gli utenti hanno ora migliorato gli strumenti di controllo, diagnosi e convalida per garantire che i dispositivi rimangano sicuri e conformi. 

-   **Controllo:** Possibilità di convalidare che un certificato sia stato distribuito correttamente o di confermare che è stato rimosso in modo appropriato. 
-   **Diagnosi:** Quando si verificano problemi, la convalida dell'esistenza dei certificati appropriati nel dispositivo consente di risparmiare tempo e facilita la risoluzione dei problemi. 
-   **Convalida:** La verifica che un certificato venga utilizzato per lo scopo previsto e funzioni può risparmiare molto tempo, in particolare negli ambienti commerciali prima di distribuire i certificati su larga scala.

Per trovare rapidamente un certificato specifico nell'elenco, sono disponibili opzioni per l'ordinamento in base al nome, all'archivio o alla data di scadenza. Gli utenti possono anche cercare direttamente un certificato. Per visualizzare le proprietà dei singoli certificati, selezionare il certificato e fare clic su **Info**. 

L'installazione del certificato supporta attualmente i file con estensione cer e crt. I proprietari dei dispositivi possono installare i certificati nel computer locale e nell'utente corrente.  tutti gli altri utenti possono eseguire l'installazione solo in Utente corrente. Gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia utente impostazioni. Se un certificato è stato installato in altri mezzi, deve anche essere rimosso dallo stesso meccanismo.

#### <a name="to-install-a-certificate"></a>Per installare un certificato: 

1.  Connettere il HoloLens 2 a un PC.
1.  Inserire il file del certificato che si vuole installare in un percorso nel HoloLens 2.
1.  Passare a **Impostazioni App > Aggiorna & sicurezza > certificati** e selezionare Installa un certificato.
1.  Fare **clic su Importa** file e passare al percorso in cui è stato salvato il certificato.
1.  Selezionare **Store Location (Posizione punto vendita).**
1.  Selezionare **Archivio certificati.**
1.  Fare clic su **Installa**.

Il certificato dovrebbe ora essere installato nel dispositivo.

#### <a name="to-remove-a-certificate"></a>Per rimuovere un certificato: 
1. Passare a **Impostazioni App > aggiornamento e certificati > sicurezza**.
1. Cercare il certificato in base al nome nella casella di ricerca.
1. Selezionare il certificato.
1. Fare clic **su Rimuovi**
1. Selezionare **Sì** quando viene richiesta la conferma.

![Visualizzatore certificati nell'app Impostazioni](images/certificate-viewer-device.jpg)

![Immagine che illustra come usare l'interfaccia utente del certificato per installare un certificato](images/certificate-device-install.jpg)

Queste informazioni sono disponibili in un secondo [momento in una nuova pagina di Gestione certificati](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Avvio automatico del provisioning da USB

- Processi automatizzati che consentono una minore interazione da parte dell'utente, quando durante la Configurazione automatica vengono usate unità USB con pacchetti di provisioning.

Prima di questa versione, gli utenti dovevano avviare manualmente la schermata di provisioning durante la Configurazione manuale per eseguire il provisioning usando una combinazione di pulsanti. Gli utenti possono ora ignorare la combinazione di pulsanti usando un pacchetto di provisioning in un'unità di archiviazione USB. 

1. Collegare l'unità USB con il pacchetto di provisioning durante il primo momento di interazione della Configurazione guidata
1. Quando il dispositivo è pronto per il provisioning, apre automaticamente il prompt con la pagina di provisioning. 

Nota: se un'unità USB viene lasciata collegata durante l'avvio del dispositivo, la Configurazione guidata enumera il dispositivo di archiviazione USB esistente, nonché verifica la connessione di altri dispositivi.

Per altre informazioni sull'applicazione dei pacchetti di provisioning durante la Configurazione manuale, vedere la documentazione [sul provisioning di HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Altre informazioni sul [provisioning di avvio automatico da usb](hololens-provisioning.md#auto-launch-provisioning-from-usb) sono disponibili nella documentazione sul provisioning di HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confermare automaticamente i pacchetti di provisioning nella Configurazione automatica
- Processo automatizzato che consente una minore interazione dell'utente. Quando viene visualizzata la pagina Pacchetto di provisioning, vengono applicati automaticamente tutti i pacchetti elencati.

Quando viene visualizzata la schermata principale del provisioning, la Configurazione automatica del sistema operativo esegue il conto alla rovescia di 10 secondi prima di avviare automaticamente l'applicazione di tutti i pacchetti di provisioning. Gli utenti possono [comunque confermare o annullare](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) entro 10 secondi dalla verifica dei pacchetti previsti.

### <a name="automatic-provisioning-without-using-ui"></a>Provisioning automatico senza usare l'interfaccia utente
- Processi automatici combinati per ridurre le interazioni dei dispositivi per il provisioning. 

Combinando l'avvio automatico del provisioning dai dispositivi USB e la conferma automatica dei pacchetti di provisioning, un utente può effettuare automaticamente il provisioning dei dispositivi HoloLens 2 senza usare l'interfaccia utente del dispositivo o persino usarlo. È possibile continuare a usare la stessa unità USB e lo stesso pacchetto di provisioning per più dispositivi. Ciò è utile per la distribuzione di più dispositivi contemporaneamente nella stessa area. 

1. [Creare un pacchetto di provisioning](hololens-provisioning.md) usando Progettazione configurazione di [Windows.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Copiare il pacchetto in un'unità di archiviazione USB.
1. [Eseguire il flash HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) alla [build 19041.1361 o a una build più recente.](https://aka.ms/hololens2previewdownload) 
1. Quando [Advanced Recovery Companion ha](https://www.microsoft.com/store/productId/9P74Z35SFRS8) completato il flashing del dispositivo, scollegare il cavo USB-C. 
1. Collegare l'unità USB al dispositivo.
1. Quando il HoloLens 2 viene avviato nella Configurazione guidata, rileverà automaticamente il pacchetto di provisioning nell'unità USB e avvierà la pagina di provisioning.
1. Dopo 10 secondi il dispositivo applicherà automaticamente il pacchetto di provisioning. 

Il dispositivo è ora configurato e verrà [visualizzata la schermata Provisioning completato](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Uso di Autopilot con Wi-Fi connessione
- È stata rimossa la necessità di adattatori USB-C per ridurre le esigenze hardware ethernet, consentendo il funzionamento di Autopilot Wi-Fi dispositivi connessi.

A questo punto, durante la Configurazione HoloLens 2, dopo la connessione con il Wi-Fi, la Configurazione automatica verifica la presenza di un profilo di Autopilot per il dispositivo. Se ne viene trovato uno, verrà usato per completare il resto del flusso di iscrizione e registrazione di AAD. In altre parole, l'uso da ethernet a USB-C o da Wi-Fi all'adattatore USB-C non è più un requisito, ma continuano a funzionare se forniti all'inizio della configurazione. Altre informazioni su [Autopilot per HoloLens 2 dispositivi](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>Provider di servizi di configurazione Tenantlockdown e Autopilot
- Mantiene i dispositivi nel tenant dell'organizzazione bloccandoli nel tenant anche tramite la reimpostazione o la reflash del dispositivo. Con ulteriore sicurezza, non consentire la creazione di account in tramite provisioning. 

HoloLens 2 ora supportano il provider di servizi di configurazione TenantLockdown a livello [di Windows Holographic versione 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP consente HoloLens 2 essere associato alla registrazione MDM usando solo Autopilot. Quando il nodo RequireNetworkInOOBE del provider di servizi di configurazione TenantLockdown è impostato sul valore true o false (inizialmente impostato) su HoloLens 2, tale valore rimane nel dispositivo nonostante il nuovo flashing, gli aggiornamenti del sistema operativo e così via. 

Quando il nodo RequireNetworkInOOBE dei CSP TenantLockdown è impostato su true in HoloLens 2, la Configurazione remota attende per un periodo illimitato che il profilo autopilot sia scaricato e applicato correttamente, dopo la connettività di rete. 

Quando il nodo RequireNetworkInOOBE dei CSP TenantLockdown è impostato su true in HoloLens 2, le operazioni seguenti non sono consentite nella Configurazione operativa: 
- Creazione di un utente locale con il provisioning di runtime 
- Esecuzione di Azure AD join tramite il provisioning di runtime 
- Selezione del proprietario del dispositivo nell'esperienza di configurazione della configurazione 

#### <a name="how-to-set-this-using-intune"></a>Come si imposta questa impostazione con Intune? 
1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato e specificare true per il nodo RequireNetworkInOOBE, come illustrato di seguito.
Il valore URI OMA deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Impostazione del blocco del tennant tramite URI OMA](images/hololens-tenant-lockdown.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo a tale gruppo di dispositivi. 

1. Impostare il HoloLens 2 del dispositivo del gruppo creato nel passaggio precedente e attivare la sincronizzazione.  

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Dopo che la configurazione del dispositivo è stata applicata HoloLens 2 dispositivo, gli effetti di TenantLockdown saranno attivi.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Come si annulla l'installazione di RequireNetworkInOOBE di TenantLockdown HoloLens 2 con Intune? 
1. Rimuovere il HoloLens 2 dal gruppo di dispositivi a cui è stata assegnata in precedenza la configurazione del dispositivo creata in precedenza. 

1. Creare un profilo di configurazione del dispositivo personalizzato basato su URI OMA e specificare false per RequireNetworkInOOBE, come illustrato di seguito. Il valore URI OMA deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot dell'impostazione di RequireNetworkInOOBE su false tramite URI OMA in Intune](images/hololens-tenant-lockdown-false.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo a tale gruppo di dispositivi. 

1. Impostare il HoloLens 2 del dispositivo del gruppo creato nel passaggio precedente e attivare la sincronizzazione.

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Dopo che la configurazione del dispositivo è stata applicata HoloLens 2 dispositivo, gli effetti di TenantLockdown saranno inattivi. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Cosa accadrebbe durante la configurazione automatica, se il profilo di Autopilot non è assegnato in un HoloLens dopo che TenantLockdown è stato impostato su true? 
La Configurazione remota attenderà per un periodo illimitato il download del profilo autopilot e verrà visualizzata la finestra di dialogo seguente. Per rimuovere gli effetti di TenantLockdown, il dispositivo deve essere prima registrato con il tenant originale usando solo Autopilot e RequireNetworkInOOBE deve essere rimosso come descritto nel passaggio precedente prima di rimuovere le restrizioni introdotte dal provider di servizi di configurazione TenantLockdown. 

![Visualizzazione nel dispositivo per l'applicazione dei criteri nel dispositivo.](images/hololens-autopilot-lockdown.png)

Queste informazioni sono ora disponibili insieme al resto di Autopilot in [Tenantlockdown CSP e Autopilot.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Accesso assegnato globale - Modalità tutto schermo
- Riduzione della gestione delle identità per chiosco multimediale, abilitando il nuovo metodo Modalità tutto schermo che applica la modalità tutto schermo a livello di sistema.

Questa nuova funzionalità consente a un amministratore IT di configurare un dispositivo HoloLens 2 per più app in modalità tutto schermo, applicabile a livello di sistema, senza affinità con alcuna identità nel sistema e applicabile a tutti gli utenti che a loro volta apportare l'accesso al dispositivo. Per informazioni dettagliate su questa nuova funzionalità, vedere La modalità tutto schermo con accesso assegnato a livello globale di [HoloLens.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Avvio automatico di un'applicazione in modalità tutto schermo con più app 
- Esperienza mirata con l'avvio automatico dell'app, aumentando ulteriormente le selezioni di interfaccia utente e app scelte per le esperienze in modalità tutto schermo.

Si applica solo alla modalità tutto schermo con più app e solo 1 app può essere designata per l'avvio automatico usando l'attributo evidenziato riportato di seguito nella configurazione accesso assegnato. 

L'applicazione viene avviata automaticamente all'accesso dell'utente. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifiche del comportamento della modalità tutto schermo per la gestione degli errori
- Modalità tutto schermo più sicura eliminando le app disponibili in caso di errori della modalità tutto schermo. 

In precedenza in caso di errori nell'applicazione della modalità tutto schermo, HoloLens visualizzava tutte le applicazioni nel menu Start. Ora in Windows Holographic versione 20H2 in caso di errori non verrà visualizzata alcuna app nel menu Start come indicato di seguito: 

![Immagine dell'aspetto della modalità tutto schermo in caso di errore.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Criteri di HoloLens
- Opzioni di gestione dei dispositivi specifiche per HoloLens create per la gestione del dispositivo. 

Sono stati creati nuovi criteri di realtà mista per HoloLens 2 dispositivi in Windows Holographic versione 20H2. Le nuove impostazioni controllabili includono: impostazione della luminosità, impostazione del volume, disabilitazione della registrazione audio nelle acquisizioni di realtà mista, impostazione del momento in cui è possibile raccogliere la diagnostica e cache delle appartenenze ai gruppi di AAD.  

| Nuovi criteri di HoloLens                                | Descrizione                                                                               | Note                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Consente di disabilitare i pulsanti di luminosità in modo che la pressione non cambi la luminosità.       | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\VolumeButtonDisabled                  | Consente di disabilitare i pulsanti del volume in modo che la sua pressione non cambi il volume.               | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\MicrophoneDisabled                    | Disabilita il microfono in modo che non sia possibile registrare audio HoloLens 2.                      | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\FallbackDiagnostics                   | Controlla il comportamento di quando è possibile raccogliere i log di diagnostica.                               | 0 disabilitato, 1 abilitato per i proprietari di dispositivi, 2 abilitato per tutti (impostazione predefinita) |
| MixedReality\HeadTrackingMode                      | Riservato per utilizzi futuri.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controlla il numero di giorni Azure AD cache di appartenenza ai gruppi usata per la modalità tutto schermo Azure AD gruppi. | Vedere qui di seguito.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Memorizzare nella cache Azure AD gruppo per chiosco multimediale offline
- Abilitata la modalità tutto schermo offline per l'uso con i gruppi di AAD per un massimo di 60 giorni.

Questo criterio controlla per quanti giorni è consentito Azure AD cache di appartenenza ai gruppi per le configurazioni di Accesso assegnato che hanno come destinazione Azure AD gruppi per l'utente connesso. Quando questo valore dei criteri è impostato solo su un valore maggiore di 0, la cache viene usata in caso contrario.  

Nome: AADGroupMembershipCacheValidityInDays VALORE URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 giorni  
Max - 60 giorni 

Passaggi per usare correttamente questo criterio: 
1. Creare un profilo di configurazione del dispositivo per la modalità tutto schermo Azure AD gruppi di dispositivi e assegnarlo ai dispositivi HoloLens. 
1. Creare una configurazione personalizzata del dispositivo basata su URI OMA che imposta il valore del criterio sul numero di giorni desiderato (> 0) e assegnarlo ai dispositivi HoloLens. 
    1. Il valore URI deve essere immesso nella casella di testo URI OMA come ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Il valore può essere compreso tra min/max consentito.
1. Registrare i dispositivi HoloLens e verificare che entrambe le configurazioni siano applicate al dispositivo. 
1. Consentire Azure AD'accesso dell'utente 1 quando è disponibile Internet, dopo che l'utente ha eseguito l'accesso e Azure AD'appartenenza al gruppo è stata confermata correttamente, verrà creata la cache. 
1. Ora Azure AD'utente 1 può portare HoloLens offline e usarlo per la modalità tutto schermo, purché il valore dei criteri consenta X numero di giorni. 
1. I passaggi 4 e 5 possono essere ripetuti per qualsiasi altro utente di Azure AD N. Il punto chiave è che qualsiasi utente di Azure AD deve accedere al dispositivo tramite Internet in modo da poter determinare almeno una volta che è membro del gruppo Azure AD a cui è destinata la configurazione della modalità tutto schermo. 
 
> [!NOTE]
> Fino a quando non viene eseguito il passaggio 4 per un Azure AD si verifica un comportamento di errore indicato negli ambienti "disconnessi". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nuovi criteri di restrizione dei dispositivi per HoloLens 2
- Consente agli utenti di gestire criteri di gestione dei dispositivi specifici, ad esempio il blocco dell'aggiunta o della rimozione di pacchetti di provisioning.

Criteri appena abilitati che consentono più opzioni di gestione HoloLens 2 dispositivi. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Questi due nuovi criteri per AllowAddProvisioningPackage e AllowRemoveProvisioningPackage vengono aggiunti a [Restrizioni comuni sul dispositivo.](hololens-common-device-restrictions.md)

> [!NOTE]
> Per quanto riguarda [RemoteLock,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)HoloLens supporterà solo la configurazione ./Vendor/MSFT/RemoteLock/Lock. Le configurazioni che gestiscono il PIN, ad esempio la reimpostazione e il ripristino, non sono supportate.

### <a name="new-power-policies-for-hololens-2"></a>Nuovi criteri di risparmio energia per HoloLens 2
- Altre opzioni per la sospensione o il blocco di HoloLens tramite criteri di risparmio energia. 

Questi criteri appena aggiunti consentono agli amministratori di controllare gli stati di alimentazione, ad esempio il timeout di inattività. Per altre informazioni su ogni singolo criterio, fare clic sul collegamento per tale criterio.

|     Collegamento alla documentazione dei criteri                |     Note                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Questi due nuovi criteri per DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn vengono aggiunti a Restrizioni comuni [sul dispositivo.](hololens-common-device-restrictions.md)

> [!NOTE]
> Per un'esperienza HoloLens 2, assicurarsi che i valori per DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery siano impostati sullo stesso valore. Lo stesso vale per DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Per altri dettagli sulla modalità standby moderna, vedere Visualizzare, sospensione e [ibernare i timer](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) di inattività.

### <a name="newly-enabled-update-policies-for-hololens"></a>Criteri di aggiornamento appena abilitati per HoloLens
- Altre opzioni per l'installazione degli aggiornamenti o la disabilitazione del pulsante Sospendi aggiornamenti per garantire gli aggiornamenti.

Questi criteri di aggiornamento sono ora abilitati HoloLens 2 dispositivi:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Per informazioni dettagliate su questi criteri di aggiornamento e su come usarli per i dispositivi HoloLens, vedere [Gestire gli aggiornamenti di HoloLens.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Visibilità della pagina Impostazioni abilitata per HoloLens 2
- Maggiore controllo dell'interfaccia utente nell'app Impostazioni, che può essere confuso per mostrare una selezione limitata di pagine.

È stato ora abilitato un criterio che consente agli amministratori IT di impedire che pagine specifiche nell'app Impostazioni di sistema siano visibili o accessibili oppure di eseguire questa operazione per tutte le pagine ad eccezione di quelle specificate. Per informazioni su come personalizzare completamente questa funzionalità, fare clic sul collegamento seguente.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Per informazioni sulle impostazioni di pagina che è possibile personalizzare HoloLens 2, visitare la pagina URI [delle impostazioni.](settings-uri-list.md) 
 
![Screenshot delle ore attive modificate nell'app Impostazioni](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modalità di ricerca
In modalità di ricerca, il HoloLens 2 diventa uno strumento potente per la ricerca di visione computer. Rispetto alle edizioni precedenti, la modalità di HoloLens 2 offre i vantaggi seguenti:
-   Oltre ai sensori esposti in modalità di ricerca HoloLens (prima generazione), è ora disponibile l'accesso ai sensori IMU, tra cui un accelerometro, un giroscopio e un magnetometro.
-   HoloLens 2 offre nuove funzionalità che possono essere usate insieme alla modalità di ricerca. In particolare, l'accesso alle API di tracciamento manuale e di tracciamento oculare articolate in grado di offrire un set più completo di esperimenti.

I ricercatori hanno ora la possibilità di abilitare la modalità di ricerca nei dispositivi HoloLens per accedere a tutti questi flussi esterni di sensori di immagini non elaborati. Modalità di ricerca per HoloLens 2 fornisce anche l'accesso alle letture di accelerometro, giroscopio e magnetometro. Per proteggere la privacy degli utenti, le immagini non elaborate della fotocamera per il tracciamento oculare non sono disponibili tramite la modalità di ricerca, ma la direzione dello sguardo è disponibile tramite le API esistenti.

Per altri dettagli [tecnici, vedere](https://docs.microsoft.com/windows/mixed-reality/research-mode) la documentazione relativa alla modalità di ricerca.

### <a name="recording-length-increased"></a>Lunghezza registrazione aumentata
Grazie ai commenti e suggerimenti dei clienti, è stata aumentata la lunghezza di registrazione delle acquisizioni [di realtà mista.](holographic-photos-and-videos.md) Le acquisizioni di realtà mista non saranno più limitate a 5 minuti per impostazione predefinita, ma calcoleranno invece la lunghezza massima della registrazione in base allo spazio disponibile su disco. Il dispositivo stima la durata massima della registrazione video in base allo spazio disponibile su disco fino all'80% dello spazio totale su disco.

> [!NOTE]
> HoloLens userà la lunghezza di registrazione video predefinita (5 minuti) se si verifica una delle condizioni seguenti:
> - La durata massima stimata per la registrazione è inferiore ai 5 minuti predefiniti.
> - Lo spazio su disco disponibile è inferiore al 20% dello spazio totale su disco.

I requisiti completi sono disponibili nella documentazione [di foto e video olografici.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Miglioramenti e correzioni nell'aggiornamento:
- Altre schermate in OOBE sono ora in modalità scura.
- Per altre informazioni, vedere l'informativa sulla privacy più recente online.
- È stato risolto un problema a causa del quale gli utenti non potevano effettuare il provisioning dei profili VPN tramite pacchetti di provisioning.
- È stato risolto un problema di configurazione del proxy per la connessione VPN.
- Aggiornamento dei criteri per disabilitare l'enumerazione delle funzioni USB tramite MDM per NCM per AllowUsbConnection.
- È stato risolto un problema che impediva la visualizzazione di un dispositivo HoloLens in Esplora file tramite Media Transfer Protocol (MTP) quando il dispositivo è configurato come un chiosco multimediale a [app singola.](hololens-kiosk.md) Si noti che MTP (e la connessione USB in generale) possono comunque essere disabilitati usando il [criterio AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- È stato risolto un problema a causa del quale le icone menu Start sono state ridimensionate correttamente in modalità tutto schermo.
- È stato risolto un problema dovuto alla memorizzazione nella cache HTTP che interferiva con la modalità tutto schermo destinata Azure AD gruppi.
- È stato risolto un problema a causa del quale gli utenti non erano in grado di usare il pulsante Associa dopo aver abilitato la modalità sviluppatore con i pacchetti di provisioning, a meno che non fossero stati disabilitati e ri abilitati in modalità sviluppatore.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di novembre 2020
- Build 18362.1085

Questo aggiornamento qualitativo mensile non contiene alcuna modifica importante. Si consiglia di provare la versione più recente delle funzionalità di Windows Holographic, versione 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versione 2004 - Aggiornamento di ottobre 2020
- Build 19041.1124
 
Miglioramenti e correzioni nell'aggiornamento:

- Rimozione di un controllo non necessario che ha causato un errore di sistema di runtime.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di ottobre 2020
- Build 18362.1081

Questo aggiornamento qualitativo mensile non contiene modifiche di valore. È quindi necessario provare le build più recenti per Windows Holographic versione 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versione 2004 - Aggiornamento di settembre 2020
- Build 19041.1117

Miglioramenti e correzioni nell'aggiornamento:

- Risolve un problema che impediva Visual Studio di eseguire il debug di un'applicazione quando SupportsMultipleInstances="true" è presente in appxmanifest.
- Questa versione include la correzione di rilevamento proxy NCSI per risolvere il rilevamento Internet non riuscito tramite proxy di rete. NCSI può usare il proxy del computer e il proxy per profilo per il rilevamento della connettività Internet. Il proxy per utente sarà supportato da NCSI nella versione futura.
- Nella maggior Windows Mixed Reality, il vettore di direzione in avanti è parallelo al suolo quando la testa dell'utente si trova in una posizione neutra in attesa. Tuttavia, le versioni precedenti HoloLens 2 allineato il vettore in modo che sia perpendicolare ai pannelli di visualizzazione, che viene inclinato verso il basso di alcuni gradi rispetto all'orientamento ideale. Le versioni più recenti HoloLens 2 questo problema è stato corretto per garantire la coerenza semantica tra i fattori di forma.
- Maggiore affidabilità del tracciamento manuale che comporta un minor numero di perdite di rilevamento in scenari specifici.
- Questa versione contiene una correzione per migliorare la qualità del timestamp audio che potrebbe aver contribuito a problemi di acquisizione video.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di settembre 2020
- Build 18362.1079

Miglioramenti e correzioni nell'aggiornamento:

- Nella maggior Windows Mixed Reality, il vettore di direzione in avanti è parallelo al suolo quando la testa dell'utente si trova in una posizione neutra in attesa. Tuttavia, le versioni precedenti HoloLens 2 allineato il vettore in modo che sia perpendicolare ai pannelli di visualizzazione, che viene inclinato verso il basso di alcuni gradi rispetto all'orientamento ideale. Le versioni più recenti HoloLens 2 questo problema è stato corretto per garantire la coerenza semantica tra i fattori di forma.
- Maggiore affidabilità del tracciamento manuale che comporta un minor numero di perdite di rilevamento in scenari specifici.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versione 2004 - Aggiornamento di agosto 2020
- Build 19041.1113

Miglioramenti e correzioni nell'aggiornamento:

- L'app Impostazioni non seguirà più l'utente nelle esperienze di registrazione Iris o calibrazione del tracciamento oculare.
- Correzione di un bug per cui l'applicazione di un pacchetto di provisioning durante la configurazione guidata che rinomina il dispositivo ed esegue altre azioni (ad esempio la connessione a una rete) non eseguirebbe le altre azioni dopo il riavvio del dispositivo a causa della ridenominazione.
- Combinazione di colori modificata dei flussi di configurazione iniziale del dispositivo per migliorare la qualità visiva.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di agosto 2020
- Build 18362.1074

Questo aggiornamento qualitativo mensile non contiene modifiche di valore. È quindi necessario provare le build più recenti per Windows Holographic versione 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versione 2004 - Aggiornamento di luglio 2020
- Build 19041.1109

Miglioramenti e correzioni nell'aggiornamento:

- Gli sviluppatori possono ora scegliere tra l'abilitazione o la disabilitazione Portale di dispositivi richiede una connessione sicura.
- Miglioramento dell'affidabilità per l'avvio dell'applicazione dopo gli aggiornamenti del sistema operativo.
- La luminosità predefinita della posta in arrivo è stata modificata al 100%.
- È stato risolto un problema relativo all'inoltro HTTPS per Portale di dispositivi di Windows in HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di luglio 2020
- Build 18362.1071

Miglioramenti e correzioni nell'aggiornamento:

- È stato risolto un problema che causava la scomparsa degli ologrammi nelle applicazioni Unity quando si perdeva o si recuperava il rilevamento.
- È stato risolto un problema che causava l'arresto anomalo delle app HoloLens esclusive nella shell durante l'uso dell'emulatore HoloLens con accelerazione hardware in determinati dispositivi.
- È stato risolto un problema relativo all'inoltro HTTPS per Portale di dispositivi di Windows in HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versione 2004 - Aggiornamento di giugno 2020
- Build 19041.1106

Miglioramenti e correzioni nell'aggiornamento:

- I registratori MRC personalizzati hanno ora nuovi valori predefiniti per determinate proprietà, se non vengono specificati.
  - *Nell'effetto video MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (visore immersivo))
  - *Nell'effetto audio MRC*:
    - LoopbackGain (il valore corrente di "App Audio Gain" nella pagina Acquisizione realtà mista in Portale di dispositivi di Windows)
    - MicrophoneGain (il valore corrente di "Mic Audio Gain" nella pagina Acquisizione realtà mista in Portale di dispositivi di Windows)
- Correzione di un bug per migliorare la qualità audio negli scenari di acquisizione di realtà mista. In particolare, questa correzione dovrebbe eliminare gli errori audio nella registrazione quando **viene** visualizzato il menu Start.
- Miglioramento della stabilità dell'ologramma nei video registrati.
- Risolto un problema a causa del quale l'acquisizione di realtà mista non è riuscita a registrare video dopo che il dispositivo è stato lasciato in stato di standby per più giorni.
- L'API HolographicSpace.UserPresence è in genere disabilitata per le applicazioni Unity. Questo comportamento evita un problema che ha causato la sospensione di alcune app quando la visiera è stata capovolta, anche se è stata abilitata l'impostazione "Esegui in background". L'API è ora abilitata per Unity versioni 2018.4.18 e successive e 2019.3.4 e successive.
- Quando si accede Portale di dispositivi una connessione Wi-Fi, un Web browser potrebbe impedire l'accesso a a causa di un certificato non valido. Il browser potrebbe segnalare un errore, ad esempio "ERR_SSL_PROTOCOL_ERROR", anche se il certificato del dispositivo è stato considerato attendibile in precedenza. In questo caso, non è possibile andare a Portale di dispositivi, perché non è possibile ignorare gli avvisi di sicurezza. Questo aggiornamento ha risolto il problema. Se il certificato del dispositivo è stato scaricato in precedenza e considerato attendibile in un PC per rimuovere gli avvisi di sicurezza del browser e si verifica l'errore SSL, il nuovo certificato deve essere scaricato e considerato attendibile per risolvere gli avvisi di sicurezza del browser.
- È stata abilitata la possibilità di creare un pacchetto di provisioning di runtime in grado di installare un'app usando pacchetti MSIX.
- È stata aggiunta un'impostazione in Impostazioni  >  **ologrammi** di sistema che consente agli utenti di rimuovere automaticamente tutti gli ologrammi dalla home page di Realtà mista quando  >   il dispositivo si arresta.
- Risolto un problema che causava il rendering nero delle app HoloLens che modificano il formato pixel nell'emulatore HoloLens.
- Correzione di un bug che causava un arresto anomalo durante l'accesso a Iris.
- Risolto un problema relativo ai download ripetuti dello Store per le app già correnti.
- Correzione di un bug per impedire alle app immersive di aprire Microsoft Edge ripetutamente.
- Correzione di un problema relativo all'avvio dell'app Foto all'avvio iniziale dopo l'aggiornamento dalla versione 1903.
- Prestazioni e affidabilità migliorate.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di giugno 2020
- Build 18362.1064

Miglioramenti e correzioni nell'aggiornamento:

- I registratori MRC personalizzati hanno nuovi valori predefiniti per determinate proprietà, se non sono specificati.
  - *Nell'effetto video MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (visore VR immersive))
  - *Nell'effetto audio MRC*:
    - LoopbackGain (il valore corrente di "App Audio Gain" nella pagina Acquisizione realtà mista in Portale di dispositivi di Windows)
    - MicrophoneGain (il valore corrente di "Mic Audio Gain" (Guadagno audio microfono) nella pagina Acquisizione realtà mista in Portale di dispositivi di Windows)
- L'API HolographicSpace.UserPresence è in genere disabilitata per le applicazioni Unity. Questo comportamento evita un problema che causa la sospensione di alcune app quando il visore viene capovolto, anche se l'impostazione per l'esecuzione in background è abilitata. L'API è ora abilitata per Unity 2018.4.18 e versioni successive e 2019.3.4 e versioni successive.
- Risolto un problema che causava la modifica del formato pixel delle app HoloLens per il rendering nero nell'emulatore HoloLens.
- Risolto un problema relativo all'avvio dell'app Foto all'avvio iniziale dopo l'aggiornamento dalla versione 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versione 2004  
- Build - 19041.1103

L'aggiornamento software principale di maggio 2020 per HoloLens 2, *Windows Holographic versione 2004* include una serie di interessanti nuove funzionalità, ad esempio il supporto per Windows Autopilot, la modalità scura dell'app, il supporto Ethernet USB per hotspot 5G/LTE e molto altro ancora. Per eseguire l'aggiornamento alla versione più recente, aprire l'app Impostazioni, passare a Aggiorna & Sicurezza e selezionare   il pulsante Controlla **** **aggiornamenti.**   

|             Funzionalità                              |          Descrizione                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pre-configurare e configurare facilmente nuovi dispositivi per la produzione con Windows AutoPilot                 |
|       Supporto di FIDO 2                             |          Supporto per le chiavi di sicurezza FIDO2 per abilitare l'autenticazione rapida e sicura per i dispositivi condivisi            |
|       Provisioning migliorato                      |          Applicare facilmente un pacchetto di provisioning da un'unità USB a HoloLens                              |
|       Stato di installazione dell'applicazione                 |          Controllare lo stato di installazione nell'app Impostazioni per le app di cui è stato fatto il push HoloLens 2 tramite MDM               |
|       Provider di servizi di configurazione (CSP)   |          Aggiunta di nuovi provider di servizi di configurazione per migliorare le funzionalità di controllo dell'amministratore                 |
|       Supporto USB 5G/LTE                       |          La funzionalità Ethernet USB espansa abilita il supporto per 5G/LTE                                    |
|       Modalità app scura                              |          Modalità app scura disponibile per le app che supportano entrambe le modalità scuro e chiaro, migliorando l'esperienza di visualizzazione        |
|       Comandi vocali                             |          Supporto per comandi vocali di sistema aggiuntivi per controllare HoloLens senza mani                           |
|       Miglioramenti del tracciamento delle mani                 |          I miglioramenti del tracciamento delle mani rendono più accurate le interazioni con i pulsanti e gli slate 2D                        |
|       Miglioramenti e correzioni della qualità                 |          Vari miglioramenti delle prestazioni e dell'affidabilità del sistema in tutta la piattaforma                            |

### <a name="support-for-windows-autopilot"></a>Supporto per Windows Autopilot

Windows Autopilot per HoloLens 2 consente al canale di vendita dei dispositivi di pre-registrare HoloLens nel tenant di Intune. Quando arrivano, i dispositivi sono pronti per la distribuzione autonoma come dispositivi condivisi nel tenant. Per sfruttare i vantaggi della distribuzione automatica, il dispositivo deve connettersi a una rete durante la prima schermata della configurazione usando una connessione USB-C-Ethernet.

Dopo che un utente ha avviato il processo di distribuzione automatica di Autopilot, il processo completa i passaggi seguenti:

1. Aggiungere il dispositivo al Azure Active Directory (Azure AD).
1. Usare Azure AD per registrare il dispositivo in Microsoft Intune (o un altro servizio MDM).
1. Scaricare i criteri, i certificati e i profili di rete destinati ai dispositivi.
1. Effettuare il provisioning del dispositivo.
1. Presentare la schermata di accesso all'utente.

Per altre informazioni, [vedere Windows Autopilot per HoloLens 2 di valutazione.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Contattare l'account manager per partecipare all'anteprima di AutoPilot. I dispositivi pronti per Autopilot inizieranno a breve la spedizione.*

### <a name="fido2-security-key-support"></a>Supporto della chiave di sicurezza FIDO2

Alcuni utenti condividono un dispositivo HoloLens con altri in un ambiente aziendale o dell'istituto di istruzione. È quindi importante che gli utenti possano facilmente senza digitare nomi utente e password lunghi. Fast Identity Online (FIDO) consente a chiunque nell'organizzazione (tenant Azure AD) di accedere facilmente a HoloLens senza immettere un nome utente o una password.

Le chiavi di sicurezza FIDO2 sono un metodo di autenticazione senza password basato su standard "non phishable" che può essere utilizzato in qualsiasi fattore di forma. FIDO è uno standard aperto per l'autenticazione senza password. Consente a utenti e organizzazioni di accedere alle proprie risorse senza un nome utente o una password. Usano invece una chiave di sicurezza esterna o una chiave di piattaforma incorporata in un dispositivo.

Per iniziare, vedere Abilitare [l'accesso con chiave di sicurezza](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)senza password.

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Registrazione MDM migliorata tramite il pacchetto di provisioning

I pacchetti di provisioning consentono di impostare la configurazione di HoloLens tramite un file di configurazione anziché tramite l'esperienza predefinita di HoloLens. In precedenza, i pacchetti di provisioning dovevano essere copiati nella memoria interna di HoloLens. Ora possono essere su un'unità USB in modo che siano più facili da riutilizzare in più dispositivi HoloLens ed è possibile effettuare il provisioning dei dispositivi in parallelo. I pacchetti di provisioning ora supportano anche un campo per la registrazione nella gestione dei dispositivi, quindi non è disponibile alcuna configurazione manuale dopo il provisioning.

Per provare il servizio:

1. Scaricare la versione più recente di Progettazione configurazione di Windows da Windows Store nel PC.
1. Selezionare **Provision HoloLens Devices Provision** HoloLens 2 devices (Provisioning dispositivi HoloLens HoloLens 2  >  **dispositivi).**
2. Compilare il profilo di configurazione. Copiare quindi tutti i file creati in un dispositivo di archiviazione USB-C.
3. Collegare il dispositivo USB-C a qualsiasi dispositivo HoloLens appena lampeggiato. Premere quindi i pulsanti **di risparmio energia** del volume per applicare il pacchetto di  +   provisioning.

### <a name="line-of-business-application-install-status"></a>Stato di installazione dell'applicazione line-of-business

La distribuzione e la gestione di app MDM per le app line-of-business sono fondamentali per HoloLens. Gli amministratori e gli utenti devono visualizzare lo stato di installazione dell'app per il controllo e la diagnosi. In questa versione sono stati aggiunti altri dettagli **in** Impostazioni Account Di accesso aziendale o dell'istituto di istruzione  >    >    >  **Fare clic su Informazioni sull'account.**  >  

### <a name="additional-csps-and-policies"></a>Criteri e CSP aggiuntivi

Un [provider di servizi di configurazione (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) è un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione in un dispositivo. In questa versione viene aggiunto il supporto per altri criteri per aumentare il controllo degli amministratori rispetto ai dispositivi HoloLens distribuiti. Per l'elenco dei provider di servizi di configurazione supportati da HoloLens, vedere [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novità di questa versione:

**Provider di servizi di configurazione Policy** 

Il provider del servizio di configurazione dei criteri consente all'azienda di configurare i criteri nei dispositivi Windows. In questa versione sono stati aggiunti nuovi criteri per HoloLens, elencati qui. Per altre informazioni, vedere [Policy CPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**Provider di servizi di configurazione NetworkQoSPolicy**

Il provider del servizio di configurazione NetworkQoSPolicy crea criteri di qualità del servizio (QoS) di rete. I criteri QoS eseguono un set di azioni sul traffico di rete in base a un set di condizioni di corrispondenza. Per altre informazioni, vedere Provider di [servizi di configurazione NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Supporto Ethernet USB esteso per dispositivi con tethering 5G/LTE

È stato aggiunto il supporto per abilitare alcuni dispositivi mobile a banda larga, ad esempio telefoni 5G/LTE e hotspot Wi-Fi, quando sono collegati al HoloLens 2 tramite USB. Questi dispositivi vengono ora visualizzati nelle impostazioni **di rete** come un'altra connessione Ethernet. I dispositivi mobili a banda larga che richiedono un driver esterno non sono supportati. Questa funzionalità abilita connessioni a larghezza di banda elevata quando Wi-Fi non è disponibile e Wi-Fi il tethering non offre prestazioni sufficienti. Per altre informazioni sui dispositivi USB supportati, vedere [Connettersi a dispositivi Bluetooth e USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>Miglioramenti del tracciamento delle mani

Questa versione include diversi miglioramenti del tracciamento delle mani:

- **Stabilità della posizione di puntamento:** Il sistema ora si opporrà alla punta dell'indice quando viene occluso dal palmo. Questa modifica migliora l'accuratezza quando si preme pulsanti, si digita, si scorre il contenuto e altro ancora. 
- **Riduzione dei tocchi d'aria accidentali:** È stato migliorato il rilevamento del movimento di tocco dell'aria. Sono ora disponibili meno attivazioni accidentali in diversi scenari comuni, ad esempio quando si rilasciano le mani ai lati.
- **Affidabilità del cambio utente:** Il sistema è ora più veloce e affidabile per l'aggiornamento delle dimensioni della mano quando si condivide un dispositivo.
- **Sottramento delle mani ridotto:** È stata migliorata la gestione dei casi in cui sono presenti più di due mani in vista dei sensori. Se più persone lavorano insieme, è ora molto più bassa la probabilità che la mano tracciata "salti" dall'utente alla mano di un altro utente nella scena.
- **Affidabilità del sistema:** Correzione di un problema che causava l'interruzione del funzionamento del tracciamento della mano quando il dispositivo è in condizioni di carico elevato.

### <a name="dark-mode"></a>Modalità scura

Molte app di Windows supportano ora le modalità scura e leggera. HoloLens 2 utenti possono scegliere la modalità predefinita per le app che supportano entrambi. Dopo l'aggiornamento, la modalità app predefinita è "scura", ma è possibile modificare facilmente questa impostazione: Passare a Impostazioni Colori di sistema  >    >    >  **Scegliere la modalità app predefinita.** 

Queste app "predefinite" supportano la modalità scura: 

- Impostazioni 
- Microsoft Store 
- Posta 
- Calendario 
- Esplora file 
- Hub di Feedback 
- OneDrive 
- Foto 
- Visualizzatore 3D 
- Film e TV 

![Finestre in modalità scura affiancate](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandi vocali di sistema

È ora possibile usare i comandi vocali con qualsiasi app nel dispositivo. Per altre informazioni, vedi [Usare la voce per usare HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Vedere anche [Lingue supportate per HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Aggiornamenti di Cortana

L'app aggiornata si integra con Microsoft 365 per migliorare le attività nei dispositivi (attualmente solo US-English dispositivi). In HoloLens 2, Cortana non supporta più determinati comandi specifici del dispositivo, ad esempio la regolazione del volume o il riavvio. Queste opzioni sono ora supportate dai nuovi comandi vocali di sistema. Per altre informazioni sulla nuova app Cortana, vedere il [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Miglioramenti e correzioni della qualità

Miglioramenti e correzioni anche nell'aggiornamento:  
- È stato introdotto un sistema di calibrazione dello schermo attivo. Questa funzionalità migliora la stabilità e l'allineamento degli ologrammi. Ora rimangono sul posto quando si sposta la testa da un lato all'altro.
- Correzione di un bug a Wi-Fi lo streaming a HoloLens viene interrotto periodicamente. Se un'applicazione indica che è necessario un flusso a bassa latenza, implementare la correzione chiamando la [funzione SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Correzione di un blocco del dispositivo che si è verificato durante lo streaming in modalità di ricerca.
- Correzione di un bug per cui in alcuni casi l'utente corretto non viene visualizzato nella schermata di accesso quando si riprende una sessione.
- È stato risolto un problema a causa del quale gli utenti non potevano esportare i log MDM tramite **Impostazioni**.
- Risolto un problema a causa del quale l'accuratezza del tracciamento oculare immediatamente dopo la configurazione automatica potrebbe essere inferiore al previsto.
- Correzione di un problema a causa del quale il sottosistema di tracciamento oculare non è riuscito a inizializzare o eseguire la calibrazione in determinate condizioni.
- Risolto un problema a causa del quale la calibrazione oculare richiedeva un utente già calibrato.
- Risolto un problema a causa del quale un driver si arresta in modo anomalo durante la calibrazione oculare.
- Risolto un problema a causa del quale la pressione ripetuta di un pulsante di alimentazione può causare un timeout di sistema di 60 secondi e un arresto anomalo della shell.
- Maggiore stabilità per i buffer di profondità.
- È stato **aggiunto un pulsante** Condividi nella Hub di Feedback in modo che gli utenti possano condividere più facilmente commenti e suggerimenti.
- Correzione di un bug per cui RoboRaid wan non è installato correttamente.

### <a name="known-issues"></a>Problemi noti

- Un problema con il linguaggio di sistema zh-CN impedisce ai comandi vocali di acquisire una realtà mista o visualizzare l'indirizzo IP del dispositivo.
- Un problema richiede l'avvio dell'app Cortana dopo l'avvio del dispositivo per l'uso dell'attivazione vocale "Hey Cortana". Se è stato aggiornato da una build 18362, è anche possibile che venga visualizzato un secondo riquadro dell'app per la versione precedente dell'app Cortana che non funziona più in **Start.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di maggio 2020 
- Build 18362.1061

Questo aggiornamento qualitativo mensile non contiene alcuna modifica importante perché il team stava lavorando all'aggiornamento di maggio di Windows Holographic versione 2004, come descritto in precedenza.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di aprile 2020
- Build 18362.1059

**Modalità scura per le app supportate** 

Molte app di Windows supportano sia la modalità scura che la modalità chiaro. HoloLens 2 clienti possono ora scegliere la modalità predefinita per le app che supportano entrambe le combinazioni di colori. In base ai commenti e suggerimenti dei clienti, la modalità app predefinita è impostata su "scuro", ma è possibile modificare facilmente questa impostazione in qualsiasi momento: passare a Impostazioni **> Colori >** sistema per trovare "Scegliere la modalità app **predefinita".**

Queste app "predefinite" supportano la modalità scura:
- Impostazioni
- Microsoft Store
- Posta
- Calendario
- Esplora file
- Hub di Feedback
- OneDrive
- Foto
- Visualizzatore 3D
- Film e TV

**Miglioramenti e correzioni anche nell'aggiornamento:** 
- Assicurarsi che le sovrimpressione della shell siano incluse nelle acquisizioni di realtà mista.
- Gli sviluppatori Unreal possono ora usare la pagina 3D View (Visualizzazione 3D) Portale di dispositivi testare ed eseguire il debug delle applicazioni.
- Maggiore stabilità dell'ologramma nell'acquisizione di realtà mista quando viene usato *l'algoritmo HolographicDepthReprojectionMethod DepthReprojection.*
- Correzione dell'errore "Classe API IStreamSocketListener WinRT non registrata" nelle app ARM a 32 bit.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di marzo 2020 
- Build 18362.1056

Miglioramenti e correzioni nell'aggiornamento:

- Maggiore stabilità dell'ologramma nell'acquisizione di realtà mista quando viene *usato l'algoritmo AutoPlanar HolographicDepthReprojectionMethod.*
- È stato garantito che il sistema di coordinate collegato a un campione MF di profondità sia coerente con la documentazione pubblica.
- Miglioramento della produttività degli sviluppatori grazie alla possibilità per i clienti di incollare grandi quantità di testo tramite il portale per dispositivi.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di febbraio 2020 
- Build 18362.1053

Miglioramenti e correzioni nell'aggiornamento:

- Disabilita temporaneamente l'API HolographicSpace.UserPresence per le applicazioni Unity. Questa modifica evita un problema che ha causato la sospensione di alcune app quando il visore è stato capovolto, anche se è stata abilitata l'impostazione "Esegui in background".
- Correzione di un arresto anomalo hup casuale causato dal tracciamento delle mani, in cui l'utente ha notato un blocco dell'interfaccia utente e quindi torna alla shell dopo alcuni secondi.
- Miglioramento del tracciamento delle mani in modo che, quando si punta con il dito indice, la parte superiore di tale dito sia meno probabile che si arriccia in modo imprevisto.
- Maggiore affidabilità del rilevamento della testa, del mapping spaziale e di altri runtime.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versione 1903 - Aggiornamento di gennaio 2020 
- Build 18362.1043
 
Miglioramenti e correzioni nell'aggiornamento:

- Maggiore stabilità per le app esclusive quando si lavora con l HoloLens 2 emulatore.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versione 1903 - Aggiornamento di dicembre 2019 
- Build 18362.1042

Miglioramenti e correzioni nell'aggiornamento:

- Sono state introdotte correzioni di riproduzione dell'ultima fase (LSR). Miglioramento del rendering visivo degli ologrammi in modo che venga visualizzato in modo più stabile e preciso, in modo da valutarne la profondità in modo più accurato. Questo sintomo sarà più evidente dopo questo aggiornamento se le app non impostano correttamente la profondità degli ologrammi.
- Correzione della stabilità delle app esclusive e della navigazione tra app esclusive.
- Risolto un problema per cui l'acquisizione di realtà mista non poteva registrare video dopo che il dispositivo era in stato standby per diversi giorni.
- Maggiore stabilità dell'ologramma.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versione 1903 - Aggiornamento di novembre 2019 
- Build 18362.1039

Miglioramenti e correzioni nell'aggiornamento:

- Correzione della funzionalità **dei comandi** vocali Select durante la configurazione iniziale per en-CA e en-AU.
- Miglioramento della qualità visiva degli oggetti posizionati lontano nelle versioni più recenti di Unity e Mixed Reality Toolkit (MRTK).
- Correzione dei problemi di risoluzione dei problemi relativi alle applicazioni olografiche bloccate in uno stato di sospensione all'avvio fino all'apertura e alla chiusura menu Start'applicazione.
- Correzioni e miglioramenti della conformità al runtime OpenXR per HoloLens 2 e l'emulatore.
