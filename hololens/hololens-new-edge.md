---
title: Introduzione al nuovo Microsoft Edge
description: Informazioni sulla nuova app Edge
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, Internet, browser
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 41978c626328903cf480a3315d56841f187bc123
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640186"
---
# <a name="introducing-the-new-microsoft-edge"></a>Introduzione al nuovo Microsoft Edge

![Animazione del logo Microsoft Edge legacy al nuovo logo Microsoft Edge](images/new-edge.gif)

Il nuovo Microsoft Edge [adotta il](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) progetto Chromium open source per creare una migliore compatibilità per i clienti e una minore frammentazione del Web per gli sviluppatori Web.

Con [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)il nuovo Microsoft Edge è disponibile per HoloLens 2 clienti per la prima volta. Condividere commenti e suggerimenti e bug con il team tramite la funzionalità **Invia commenti** e suggerimenti nel nuovo Microsoft Edge o [tramite Hub di Feedback](hololens-feedback.md).

> [!IMPORTANT]
> Questa nuova Microsoft Edge sostituisce automaticamente Microsoft Edge legacy, che non [è più supportata](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) nelle nuove versioni.

![Screenshot Microsoft Edge nuova versione](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Avvio del nuovo Microsoft Edge

Il nuovo Microsoft Edge ![icona Microsoft Edge nuova](images/new_edge_logo.png) (rappresentato da un'icona di scorrimento blu e verde) viene aggiunto al menu Start e verrà avviato automaticamente quando si attiva un collegamento Web.

> [!NOTE]
> Quando si avvia per la prima volta la nuova Microsoft Edge in HoloLens 2, le impostazioni e i dati verranno importati dalle versioni Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge

Il nuovo Microsoft Edge offre agli amministratori IT un set molto più ampio di criteri del browser HoloLens 2 rispetto a quelli disponibili in precedenza con i criteri Microsoft Edge.

Ecco alcune risorse utili per altre informazioni sulla gestione delle impostazioni dei criteri per il nuovo Microsoft Edge:

- [Configurare Microsoft Edge impostazioni dei criteri con Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Versione legacy di Microsoft Edge per Microsoft Edge mapping dei criteri](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapping dei criteri di Microsoft Edge google chrome](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentazione [Microsoft Edge Enterprise completa](/deployedge/)

> [!IMPORTANT]
> A causa del volume dei criteri del browser supportati dal nuovo Microsoft Edge, il team non è in grado di garantire che ogni nuovo criterio funzioni HoloLens 2. Tuttavia, è stato testato e confermato che il nuovo Microsoft Edge equivalente di ogni criterio di Microsoft Edge legacy supportato in precedenza HoloLens 2 funziona come previsto. Vedere [Versione legacy di Microsoft Edge per Microsoft Edge mapping](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) dei criteri per trovare il nuovo Microsoft Edge equivalente a ogni criterio del browser Microsoft Edge legacy in uso con HoloLens 2.
>
> Esistono almeno due nuovi criteri Microsoft Edge che non *funzionano* con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Cosa aspettarsi dalla nuova Microsoft Edge in HoloLens 2

Poiché il nuovo Microsoft Edge è un'app Win32 nativa con un nuovo livello di adattatore UWP che ne consente l'esecuzione su dispositivi solo UWP come HoloLens 2, alcune funzionalità potrebbero non essere immediatamente disponibili. Nei prossimi mesi verranno supportati nuovi scenari e funzionalità, quindi controllare questo spazio per informazioni aggiornate.

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
- L'anteprima della lente di ingrandimento nella tastiera olografica è stata disabilitata per il nuovo Microsoft Edge. Ci auguriamo di poter riabilitare questa funzionalità in un aggiornamento futuro, una volta che l'ingrandimento funziona correttamente.
- L'audio può essere riprodotto dalla finestra del browser errata se è aperta e attiva un'altra finestra del browser. È possibile risolvere questo problema chiudendo l'altra finestra attiva che non dovrebbe riprodurre audio.
- Quando si riproduce l'audio da una finestra del browser in modalità "Seguimi", l'audio continuerà a essere riprodotto se si disabilita la modalità "Seguimi". È possibile risolvere questo problema arrestando la riproduzione audio prima di disabilitare la modalità "Seguimi" o chiudendo la finestra con il pulsante X.
- L'interazione con finestre Microsoft Edge attive può causare l'inattività imprevista di altre finestre dell'app 2D. È possibile riattivare queste finestre interagendo di nuovo con esse.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Canali Insider

Il team Microsoft Edge rende disponibili tre canali di anteprima per la community edge Insider: Beta, Dev e Canary. L'installazione di un canale di anteprima non disinstalla la versione rilasciata di Microsoft Edge nel HoloLens 2 ed è possibile installarne più di una contemporaneamente. 

Visitare la [home Microsoft Edge Insider per](https://www.microsoftedgeinsider.com) altre informazioni sulla community Edge Insider. Per altre informazioni sui diversi canali Edge Insider e per iniziare, visitare la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)

Sono disponibili due metodi per installare i Microsoft Edge Insider per HoloLens 2:

**Installazione diretta nel dispositivo (attualmente disponibile solo per i dispositivi non gestiti)**
  1. Nel sito HoloLens 2 visitare la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Selezionare il **pulsante Download for HoloLens 2** per il canale Edge Insider che si vuole installare.
  1. Avviare il file msix scaricato dalla coda di download edge o dalla cartella "Download" del dispositivo (usando Esplora file).
  1. [Verrà avviato il programma](app-deploy-app-installer.md) di installazione dell'app.
  1. Selezionare il pulsante **Installa**.
  1. Al termine dell'installazione, sarà possibile trovare Microsoft Edge Beta, Dev o Canary come voce separata nell'elenco Tutte le app del menu Start. 

**Eseguire l'installazione tramite PC Windows Portale di dispositivi (è [necessario che la modalità sviluppatore](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) sia abilitata HoloLens 2)**
  1. Nel PC visitare la pagina [di download di Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Selezionare il **pulsante freccia a discesa** accanto al pulsante "Download for Windows 10" (Scarica per Windows 10) per il canale Edge Insider che si vuole installare.
  1. Selezionare **HoloLens 2** nel menu a discesa.
  1. Salvare il file con estensione msix nella cartella "Download" del PC (o in un'altra cartella facilmente individuabile).
  1. Usare [Windows Portale di dispositivi](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) nel PC per installare il file msix scaricato HoloLens 2.
  1. Al termine dell'installazione, sarà possibile trovare Microsoft Edge Beta, Dev o Canary come voce separata nell'elenco Tutte le app del menu Start. 

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso di WDAC per bloccare nuovi Microsoft Edge

Per gli amministratori IT che desiderano aggiornare i criteri [WDAC](windows-defender-application-control-wdac.md) per bloccare la nuova app Microsoft Edge, è necessario aggiungere quanto segue al criterio.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gestione degli endpoint per il nuovo Microsoft Edge

Alcuni ambienti possono avere restrizioni di rete da tenere in considerazione. Per garantire un'esperienza uniforme con il nuovo edge, [abilitare questi endpoint Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Altre informazioni sugli [endpoint](hololens-offline.md)attualmente disponibili per HoloLens .

## <a name="install-web-apps"></a>Installare app Web
 > [!Note]
> A Windows [Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)l'app Web Office non verrà più preinstallato. 

È possibile usare il nuovo Edge per installare le app Web insieme Microsoft Store app. Ad esempio, è possibile installare l Microsoft Office app Web per visualizzare e modificare i file ospitati SharePoint o OneDrive. Per installare l Office app Web, visitare e selezionare il pulsante App available (Disponibile per l'app) o https://www.office.com Install Office **(Installa** Office nella barra degli indirizzi).  Selezionare **Installa per** confermare.
> [!IMPORTANT]
> Office funzionalità dell'app Web è disponibile solo quando il HoloLens 2 ha una connessione Internet attiva.

## <a name="webxr-and-360-viewer"></a>Visualizzatore WebXR e 360


Il nuovo Microsoft Edge include il supporto per WebXR, che è il nuovo standard per la creazione di esperienze Web immersive (sostituendo WebVR). Molte esperienze Web immersive sono state progettate in base alla realtà virtuale (che sostituiscono il campo di visualizzazione con un ambiente virtuale), ma queste esperienze sono supportate anche da HoloLens 2. Lo standard WebXR consente anche esperienze Web immersive di realtà aumentata e mista che usano l'ambiente fisico. Con l'aumentare del tempo che gli sviluppatori dedicano a WebXR, si prevede che le nuove esperienze immersive di realtà aumentata e mista HoloLens 2 i clienti possano provare.

L'estensione 360 Viewer è compilata su WebXR e viene installata automaticamente insieme al nuovo Microsoft Edge in HoloLens 2. Questa estensione Web offre la possibilità di guardare video a 360 gradi. YouTube offre la selezione più ampia di 360 video, quindi si consiglia di iniziare da qui.

### <a name="how-to-use-webxr"></a>Come usare WebXR

1. Passare a un sito Web con supporto WebXR.
1. Selezionare il **pulsante Enter VR (Immetti** VR) nel sito Web. La posizione e la rappresentazione visiva di questo pulsante possono variare per ogni sito Web, ma può essere simile a:

    ![Esempio di pulsante di immissione della realtà virtuale](images/75px-enter-vr.png)

1. La prima volta che si prova ad avviare un'esperienza WebXR in un dominio specifico, il browser chiederà il consenso per l'immissione di una visualizzazione immersiva e **selezionerà Consenti.**
1. Usare [HoloLens 2 per modificare](hololens2-basic-usage.md#the-hand-tracking-frame) l'esperienza.
1. Se l'esperienza non ha un pulsante **Esci,** usa il [movimento Avvia](hololens2-basic-usage.md#start-gesture) per tornare a casa.

**Esempi di WebXR consigliati**
- Visualizzatore 360 (vedere la sezione successiva)
- [Dinosauri XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>Come usare il visualizzatore 360

1. Passare a un video a 360 gradi su YouTube.
1. Nel fotogramma video selezionare il pulsante visore VR di realtà mista:

    ![Pulsante per attivare il visualizzatore 360](images/enter-360-viewer.jpg)

1. La prima volta che si prova ad avviare 360 Viewer in un dominio specifico, il browser chiederà il consenso per l'immissione di una visualizzazione immersiva. selezionare **Consenti**.
1. [Tocco per](hololens2-basic-usage.md#select-using-air-tap) visualizzare i controlli di riproduzione. Usa [i raggi della](hololens2-basic-usage.md#select-using-air-tap) mano e il tocco dell'aria per riprodurre/sospendere, ignorare avanti/indietro, attivare/disattivare i sottotitoli o arrestare l'esperienza (che esce dalla visualizzazione immersiva). I controlli di riproduzione scompariranno dopo alcuni secondi di inattività.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Principali problemi noti di WebXR e 360 Viewer
- A seconda della complessità dell'esperienza WebXR, la frequenza dei fotogrammi può essere notevolmente più complessa.
- Il supporto per le giunzioni delle mani articolate in WebXR non è abilitato per impostazione predefinita. Gli sviluppatori possono abilitare il supporto tramite edge://flags attivando "WebXR Hand Input".
- 360 video da siti Web diversi da YouTube potrebbero non funzionare come previsto.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Commenti e suggerimenti su WebXR e visualizzatore 360

Condividere commenti e suggerimenti e bug con il team tramite la funzionalità **Invia commenti** e suggerimenti nel nuovo Microsoft Edge.
