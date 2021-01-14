---
title: Insider Preview per Microsoft HoloLens
description: È semplice iniziare con le build Insider e dare un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.
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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 06c3faf573adabe158a72a66fc4b8a45afec48fb
ms.sourcegitcommit: e26aa9059a7d8e73914205e80a89ea9637926e74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269397"
---
# Insider Preview per Microsoft HoloLens

Benvenuti alle build di insider Preview più recenti per HoloLens! È facile [iniziare e dare](hololens-insider.md#start-receiving-insider-builds) un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.

## Note sulla versione di Windows Insider

Siamo entusiasti di iniziare a volare nuove funzionalità per i partecipanti al programma Windows Insider. Per gli aggiornamenti più recenti sarà possibile eseguire il volo per il canale dev. Continueremo ad aggiornare questa pagina man mano che aggiungiamo altre funzionalità e aggiornamenti alle nostre Build Insider di Windows.  Diventa entusiasta e pronto a combinare questi aggiornamenti nella tua realtà. 

| Nome caratteristica                                              | Descrizione breve                                                                      | Disponibile nella build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nuovo Microsoft Edge](#introducing-the-new-microsoft-edge) | Il nuovo Edge Microsoft basato su cromo è ora disponibile per HoloLens 2                         | 20279,1006 |
| [App nuove impostazioni](#new-settings-app)                     | L'app impostazioni legacy viene sostituita da una versione aggiornata con nuove funzionalità e impostazioni | 20279,1006 |
| [Selezione app predefinita](#default-app-picker)                 | Scegliere l'app che deve essere avviata per ogni file o tipo di collegamento                                      | 20279,1006 |
| [Office Web App](#office-web-app)                         | Un collegamento a Office Web App è ora elencato in "tutte le app"                                   | 20279,1006 |
| [Scorrere rapidamente verso il tipo](#swipe-to-type)                           | Usare la punta del dito per "scorrere rapidamente" le parole sulla tastiera olografica                        | 20279,1006 |

### Introduzione al nuovo Microsoft Edge

![Animazione del logo legacy Microsoft Edge con il nuovo logo Microsoft Edge](images/new-edge.gif)

Il nuovo Microsoft Edge [adotta il progetto open source Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) per creare una migliore compatibilità per i clienti e una minore frammentazione del Web per gli sviluppatori Web. 

Con questa anteprima Insider, il nuovo Microsoft Edge è disponibile per i clienti di HoloLens 2 per la prima volta. Mentre il nuovo Microsoft Edge rimpiazzerà Microsoft Edge legacy in HoloLens 2, entrambi i browser saranno attualmente disponibili per i partecipanti al programma Insider. Condividere feedback e bug con il team tramite la caratteristica **Invia feedback** nel nuovo Microsoft Edge o tramite [Hub feedback](hololens-feedback.md).

![Nuova schermata Microsoft Edge](images/new-edge-ui.png)

#### Avvio del nuovo Microsoft Edge

Esistono due versioni di Microsoft Edge disponibili per i partecipanti al programma Insider: la nuova icona Microsoft Edge ![ New Microsoft Edge ](images/new_edge_logo.png) (rappresentata da un'icona di turbinio blu e verde) e il bordo Microsoft legacy (rappresentato dall'icona "e" bianca). Il nuovo Microsoft Edge viene aggiunto al menu Start e viene avviato automaticamente quando si attiva un collegamento Web. Se si vuole ripristinare l'uso di Microsoft Edge legacy come Web browser predefinito, vedere le istruzioni seguenti per [reimpostare le app predefinite](#default-app-picker).

> [!NOTE]
> La prima volta che si avvia il nuovo Microsoft Edge in HoloLens 2, le impostazioni e i dati verranno importati da Microsoft Edge legacy. Se si continua a usare Microsoft Edge legacy dopo l'avvio del nuovo Microsoft Edge, i nuovi dati non verranno sincronizzati da Microsoft Edge legacy al nuovo Microsoft Edge.

#### Configurazione delle impostazioni dei criteri per il nuovo Microsoft Edge

Il nuovo Microsoft Edge offre ai professionisti IT un set molto più ampio di criteri per i browser in HoloLens 2 rispetto a quelli precedentemente disponibili con Microsoft Edge legacy. 

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
- Audio spaziale per più finestre con flussi audio simultanei
- Partecipare a una chiamata di Microsoft teams tramite il browser con video, acquisizione di realtà mista o condivisione dello schermo (partecipare alle chiamate con audio funziona bene)
- "Vedi, Dillo"
- Stampa

**Principali problemi noti del browser:**
- La reimpostazione del dispositivo rimuoverà il nuovo Microsoft Edge
- L'anteprima della lente di ingrandimento nella tastiera olografica Mostra contenuto non corretto

### App nuove impostazioni

Con questa versione, stiamo introducendo una nuova versione dell'app Impostazioni. L'app nuove impostazioni include le nuove caratteristiche e le impostazioni estese per HoloLens 2 nelle aree seguenti: dispositivi audio di input/output, volume dell'app individuale, alimentazione e sospensione, adattatore Ethernet, facilità di accesso, modalità aereo e app predefinite.

> [!NOTE]
> Dato che l'app nuove impostazioni è diversa dall'app impostazioni legacy, tutte le finestre delle impostazioni precedentemente inserite intorno all'ambiente verranno rimosse dopo l'aggiornamento.

![Home page dell'app nuove impostazioni](images/new-settings-app.png)

**Nuove funzionalità e impostazioni**
- Ricerca impostazioni: cercare le impostazioni dalla Home page delle impostazioni usando le parole chiave o il nome dell'impostazione
- Audio
  - Dispositivi audio di input e output: scegliere in modo indipendente i dispositivi audio di input e output, ad esempio ascoltare l'audio tramite auricolari Bluetooth o usare un microfono USB-C per l'input audio. Nota: i microfoni Bluetooth non sono supportati da HoloLens 2.
  - Volume dell'app: modificare in modo indipendente il volume di ogni app
- Risparmio batteria: abilitare manualmente la modalità risparmio batteria o impostare una soglia della batteria a cui si attiva automaticamente la modalità risparmio batteria
- Power & Sleep: scegliere quando il dispositivo deve andare a dormire dopo un periodo di inattività
- USB: è possibile disabilitare le connessioni USB per impostazione predefinita
- Rete & Internet:
  - Le schede Ethernet USB-C compariranno ora in rete & Internet
  - Le impostazioni della scheda Ethernet USB-C sono ora disponibili, incluso il relativo indirizzo IP
  - Ora è possibile abilitare la modalità aereo in HoloLens 2
- App: puoi reimpostare le app predefinite usate per i tipi di file e collegamenti. Per altre informazioni, vedere [selezione delle app predefinite](#default-app-picker) .
- Accesso facilitato: modificare le dimensioni del testo e alcuni effetti visivi

**Problemi noti**
- Le finestre delle impostazioni precedentemente inserite verranno rimosse (Vedi nota sopra)
- La visita alla pagina notifiche può arrestarsi in modo anomalo nell'app Impostazioni (analisi)
- La pagina Ethernet attualmente non viene visualizzata (per essere risolta a breve)
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
