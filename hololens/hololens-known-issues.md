---
title: Problemi noti di HoloLens
description: Questo è l'elenco dei problemi noti che possono influire sugli sviluppatori di HoloLens.
keywords: risoluzione dei problemi, problema noto, guida
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 6947fe2232701fb9451291bd07e1c896979861d5
ms.sourcegitcommit: 77eb85608066d9a4ed01b3862afe356f7e54d583
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "10940196"
---
# Problemi noti di HoloLens

Questo è l'elenco corrente dei problemi noti per i dispositivi HoloLens. Controlla prima di tutto se viene visualizzato un comportamento strano. Questo elenco verrà mantenuto aggiornato man mano che vengono rilevati o segnalati nuovi problemi o quando vengono risolti problemi nei futuri aggiornamenti software di HoloLens.

>[!NOTE]
> - Se viene individuato un problema che non sta bloccando, è necessario segnalarlo nel dispositivo HoloLens tramite [Hub di feedback](hololens-feedback.md).
> - Se il problema che si sta affrontando sta bloccando l'utente, in aggiunta a presentare un feedback, inviare  [una richiesta di supporto](https://aka.ms/hlsupport).

- [Problemi noti per tutte le generazioni HoloLens](#known-issues-for-all-hololens-generations)
- [Problemi noti per i dispositivi HoloLens 2](#known-issues-for-hololens-2-devices)
- [Problemi noti di HoloLens (1a generazione)](#known-issues-for-hololens-1st-gen)
- [Problemi noti per l'emulatore HoloLens](#known-issues-for-hololens-emulator)

## Problemi noti per tutte le generazioni HoloLens

### Unity

- Vedere [installare gli strumenti](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Unity consigliata per lo sviluppo di HoloLens.
- I problemi noti relativi all'anteprima tecnica Unity HoloLens sono documentati nei [Forum di Unity di HoloLens](https://forum.unity3d.com/threads/known-issues.394627/).

### Windows Device Portal

- La caratteristica Anteprima live nell'acquisizione di realtà mista può presentare diversi secondi di latenza.
- Nella pagina Virtual input i controlli gesture e scroll nella sezione movimenti virtuali non sono funzionali. L'uso di questi elementi non avrà alcun effetto. La tastiera virtuale nella stessa pagina funziona correttamente.
- Dopo l'abilitazione della modalità sviluppatore in impostazioni, potrebbe essere necessario qualche secondo prima che l'opzione attiva il portale del dispositivo sia abilitata.

### Caricamento della fotocamera OneDrive

L'app OneDrive per HoloLens non supporta il caricamento automatico della videocamera per gli account aziendali o dell'Istituto di istruzione.

Soluzioni alternative
- Se possibile per la tua azienda, il caricamento automatico della videocamera è supportato sugli account Microsoft Consumer. È possibile accedere al proprio account Microsoft oltre al proprio account di lavoro o dell'Istituto di istruzione (l'app OneDrive supporta l'accesso Dual). Dal profilo dell'account Microsoft in OneDrive è possibile abilitare il caricamento automatico del rotolo della fotocamera in background.
- Se non è possibile usare in modo sicuro un account Microsoft Consumer per caricare automaticamente le foto, è possibile caricare manualmente le foto nell'account dell'ufficio o dell'Istituto di istruzione dall'app OneDrive. Per farlo, assicurati di avere effettuato l'accesso all'account di lavoro o dell'Istituto di istruzione nell'app OneDrive. Selezionare il **+** pulsante e scegliere **carica**. Trovare le foto o i video da caricare passando alle **immagini > rullo della fotocamera**. Selezionare le foto o i video che si desidera caricare e quindi selezionare il pulsante **Apri** .

## Problemi noti per i dispositivi HoloLens 2

### La tastiera non passa ai caratteri speciali

Si è verificato un problema durante la configurazione guidata, in cui quando l'utente ha scelto un account dell'ufficio o dell'Istituto di istruzione e sta immettendo la password, provando a passare ai caratteri speciali sulla tastiera toccando il pulsante &123 non viene modificato in caratteri speciali. 

Work-intorno:
-   Chiudere la tastiera e riaprirla toccando il campo di testo.
-   Immettere erroneamente la password. Quando la tastiera viene riavviata la prossima volta, il lavoro verrà eseguito come previsto.
- Autenticazione Web, chiudere la tastiera e selezionare **Accedi da un altro dispositivo**. 
-   Se si immettono solo numeri, un utente può tenere premuti alcuni tasti per aprire un menu espanso.
-   Uso di una tastiera USB.

Questo non ha effetto:
- Utenti che scelgono di usare un account personale.

### Schermata blu visualizzata dopo la disattivazione della registrazione dalle compilazioni di anteprima insider su un dispositivo reflashed con una build Insider

Si tratta di un problema che interessa gli utenti che si trovano in una build di anteprima Insider, ha reflashato la HoloLens 2 con una nuova build di anteprima Insider e quindi non è stata effettuata la registrazione dal programma Insider. 

Questo non ha effetto:
- Utenti non iscritti a Windows Insider 
- Insider
    - Se un dispositivo è stato registrato in quanto la versione di insider Builds è 18362. x
    - Se lampeggiano un insider firmato 19041. x Build e restano iscritti al programma Insider 

Work-intorno: 
- Evitare il problema 
    - Creare un flash non Insider Build. Uno degli aggiornamenti mensili regolari. 
    - Rimanere in anteprima Insider
- Reflash del dispositivo
    1. Inserire manualmente il [HoloLens 2 in modalità di lampeggio](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) attivando completamente il sistema mentre non si connette. Quindi, mentre si tiene premuto il volume, toccare il pulsante di alimentazione.
    1. Connettersi al PC e aprire il compagno di ripristino avanzato. 
    1. Flash HoloLens 2 alla Build predefinita.   

## Problemi noti di HoloLens (1a generazione)

### Non è possibile connettersi e distribuire in HoloLens tramite Visual Studio

> [!NOTE]
> Ultimo aggiornamento: 8/8 @ 5:23:00-Visual Studio è stato rilasciato VS 2019 versione 16,2 che include una correzione per questo problema. È consigliabile eseguire l'aggiornamento a questa versione più recente per evitare di provare questo errore.

Visual Studio è stato rilasciato rispetto a 2019 versione 16,2 che include una correzione per questo problema. È consigliabile eseguire l'aggiornamento a questa versione più recente per evitare di provare questo errore.

Causa principale di un problema: gli utenti che hanno usato Visual Studio 2015 o le versioni precedenti di Visual Studio 2017 per distribuire e eseguire il debug delle applicazioni nel proprio HoloLens e successivamente hanno usato le versioni più recenti di Visual Studio 2017 o Visual Studio 2019 con lo stesso HoloLens saranno interessate. Le versioni più recenti di Visual Studio distribuiscono una nuova versione di un componente, ma i file della versione precedente vengono lasciati nel dispositivo, causando il fallimento della versione più recente.  In questo modo viene visualizzato il messaggio di errore seguente: DEP0100: verificare che il dispositivo di destinazione abbia abilitato la modalità sviluppatore. Impossibile ottenere una licenza per sviluppatore a \<ip\> causa di un errore 80004005.

#### Soluzione alternativa

Il nostro team sta attualmente lavorando a una correzione. Nel frattempo, è possibile usare la procedura seguente per aggirare il problema e aiutare a sbloccare la distribuzione e il debug:  

1. Aprire Visual Studio
1. Selezionare **file**  >  **nuovo**  >  **progetto**.
1. Selezionare l'app console desktop di **Visual C#**  >  **Windows**  >  **(.NET Framework)**.
1. Assegnare un nome al progetto (ad esempio "HoloLensDeploymentFix") e verificare che il Framework sia impostato su almeno .NET Framework 4,5, quindi scegliere **OK**.
1. Fare clic con il pulsante destro del mouse sul nodo **riferimenti** in Esplora soluzioni e aggiungere i riferimenti seguenti (selezionare la sezione **Sfoglia** e selezionare **Sfoglia**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Se 10.0.18362.0 non è installato, usare la versione più recente. 

1. Fare clic con il pulsante destro del mouse sul progetto in Esplora soluzioni e scegliere **Aggiungi**  >  **elemento esistente**.
1. Passare a C:\Programmi (x86) \Windows Kits\10\bin\10.0.18362.0\x86 e cambiare il filtro in **tutti i file (\ *. \ *)**.
1. Selezionare sia SirepClient.dll che SshClient.dll e quindi scegliere **Aggiungi**.
1. Individuare e selezionare entrambi i file in Esplora soluzioni (dovrebbero essere nella parte inferiore dell'elenco dei file) e modificare la **copia nella directory di output** nella finestra **Proprietà** per **copiare sempre**.
1. Nella parte superiore del file aggiungere il codice seguente all'elenco di `using` istruzioni esistente:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. All'interno di `static void Main(...)` aggiungere il codice seguente:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Selezionare **Build**  >  **Build Solution**.
1. Aprire una finestra del prompt dei comandi e un CD nella cartella che contiene il file exe compilato, ad esempio C:\MyProjects\HoloLensDeploymentFix\bin\Debug.
1. Esegui l'eseguibile e fornisci l'indirizzo IP del dispositivo come argomento della riga di comando. Se si è connessi tramite USB, è possibile usare 127.0.0.1, altrimenti usare l'indirizzo IP Wi-Fi del dispositivo.  Ad esempio, "HoloLensDeploymentFix 127.0.0.1"

1. Dopo l'uscita dello strumento senza messaggi (solo pochi secondi), sarà possibile eseguire la distribuzione e il debug da Visual Studio 2017 o versioni successive.  L'uso continuo dello strumento non è necessario.

Verranno forniti ulteriori aggiornamenti man mano che diventano disponibili.

### Problemi con l'avvio di Microsoft Store e le app in HoloLens

> [!NOTE]
> Ultimo aggiornamento: 4/2 @ 10 AM-problema risolto. 

Si potrebbero riscontrare problemi quando si prova a avviare Microsoft Store e le app in HoloLens. Abbiamo stabilito che il problema si verifica quando gli aggiornamenti delle app in background distribuiscono una versione più recente dei pacchetti del Framework in sequenze specifiche, mentre una o più delle loro app dipendenti sono ancora in esecuzione. In questo caso, un aggiornamento automatico delle app ha recapitato una nuova versione di .NET native Framework (versione 10.0.25531 in 10.0.27413) per le app in esecuzione per l'aggiornamento non corretto per tutte le app in esecuzione che consumano la versione precedente del Framework.  Il flusso per l'aggiornamento del Framework è il seguente: 

1. Il nuovo pacchetto di Framework viene scaricato dallo Store e installato
1. Tutte le app che usano il Framework precedente sono "aggiornate" per usare la versione più recente

Se il passaggio 2 viene interrotto prima del completamento, le app per cui il Framework più recente non è stato registrato non verranno avviate dal menu Start.  Crediamo che qualsiasi app su HoloLens potrebbe essere interessata da questo problema.

Alcuni utenti hanno riferito che la chiusura delle app appese e l'avvio di altre app come hub di feedback, visualizzatore 3D o foto risolve il problema per loro &mdash; , tuttavia, non funziona il 100% del tempo.

La radice ha causato il fatto che il problema non è stato causato dall'aggiornamento stesso, ma un bug nel sistema operativo che ha generato l'aggiornamento del Framework .NET native che viene gestito in modo non corretto. Siamo lieti di annunciare che è stata individuata una correzione e che è stato rilasciato un aggiornamento (OS versione 17763,380) che contiene la correzione.  

Per vedere se il dispositivo può eseguire l'aggiornamento, per cortesia:

1. Accedere all'app Impostazioni e aprire **aggiornamento & sicurezza**.
1. Selezionare **Controlla aggiornamenti**.
1. Se l'aggiornamento a 17763,380 è disponibile, eseguire l'aggiornamento a questa build per ricevere la correzione per il bug di blocco dell'app
1. Dopo l'aggiornamento a questa versione del sistema operativo, le app dovrebbero funzionare come previsto.

Inoltre, come facciamo con ogni versione del sistema operativo HoloLens, abbiamo pubblicato l'immagine FFU nell' [area download Microsoft](https://aka.ms/hololensdownload/10.0.17763.380).

Se non si vuole eseguire l'aggiornamento, è stata rilasciata una nuova versione dell'app Microsoft Store UWP da 3/29. Dopo aver completato la versione aggiornata dello Store:

1. Aprire lo Store e verificare che venga caricato.
1. Usare il gesto Bloom per aprire il menu.
1. Provare ad aprire le app interrotte in precedenza.
1. Se non è ancora possibile avviarla, toccare e tenere premuto l'icona dell'app interrotta e selezionare Disinstalla.
1. Resinstall queste app dallo Store.

Se il dispositivo non è ancora in grado di caricare le app, è possibile trasferire localmente una versione del Framework e del runtime di .NET native tramite Download Center seguendo questa procedura:

1. Scaricare il [file zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) dall'area download Microsoft. La decompressione produrrà due file.  Microsoft. NET. native. Runtime. 1.7. appx e Microsoft. NET. native. Framework. 1.7. appx
1. Verificare che il dispositivo sia sbloccato da dev.  Se l'operazione [non è stata](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)eseguita prima delle istruzioni.
1. Si vuole quindi accedere a Windows Device Portal. La nostra raccomandazione è di eseguire questa operazione tramite USB e farlo digitando http://127.0.0.1:10080 nel browser.
1. Dopo aver installato Windows Device Portal, devi "caricare lateralmente" i due file scaricati. Per eseguire questa operazione, devi scendere dalla barra laterale sinistra fino ad accedere alla sezione **app** e selezionare **app**.
1. Verrà visualizzata una schermata simile alla seguente.  Si vuole passare alla sezione che indica l' **app install** e individuare la posizione in cui sono stati decompressi i due file di appx. È possibile eseguire una sola operazione alla volta, quindi selezionare la prima, quindi fare clic su "Vai" nella sezione Distribuisci. Quindi eseguire questa operazione per il secondo file APPX.

   ![Windows Device Portal per installare l'app con caricamento laterale](images/20190322-DevicePortal.png)
1. A questo punto riteniamo che le applicazioni debbano ricominciare a funzionare e che si possa anche arrivare allo Store.
1. In alcuni casi, è necessario eseguire il passaggio aggiuntivo per avviare l'app visualizzatore 3D prima che vengano avviate le app interessate. 

Apprezziamo la tua pazienza mentre abbiamo attraversato il processo per risolvere il problema e siamo ansiosi di continuare a collaborare con la nostra community per creare esperienze di realtà miste di successo.

### Aggiornamento del dispositivo

- 30 secondi dopo un nuovo aggiornamento, la shell può scomparire una sola volta. Per riprendere la sessione, eseguire il gesto di **Bloom** .

### Visual Studio

- Vedere [installare gli strumenti](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Visual Studio consigliata per lo sviluppo di HoloLens.
- Quando si distribuisce un'app da Visual Studio a HoloLens, è possibile che venga visualizzato l'errore: **non è possibile eseguire l'operazione richiesta su un file con una sezione mappata dall'utente aperta. (Eccezione da HRESULT: 0x800704C8)**. In questo caso, riprovare e la distribuzione in genere avrà esito positivo.

### API

- Se l'applicazione imposta il [punto focale](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) dietro l'utente o la normale alla fotocamera. avanti, gli ologrammi non verranno visualizzati in foto o video di acquisizione di realtà mista. Finché questo bug non viene risolto in Windows, se le applicazioni attivano attivamente lo [stato attivo](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) devono garantire che il piano normale sia impostato in avanti rispetto alla videocamera, ad esempio Normal =-camera. forward.

### Controller wireless Xbox

- Il controller wireless Xbox S deve essere aggiornato prima che possa essere usato con HoloLens. Verificare [di essere aggiornati prima di tentare](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) di associare il controller a un HoloLens.
- Se si riavvia il HoloLens mentre il controller Xbox wireless è connesso, il controller non si riconnette automaticamente a HoloLens. La spia del pulsante di guida lampeggerà lentamente fino a quando il controller non si spegnerà dopo 3 minuti. Per riconnettere immediatamente il controller, spegnere il controller tenendo premuto il pulsante Guida finché la luce non si spegne. Quando si accende di nuovo il controller, si riconnetterà a HoloLens.
- Se il HoloLens entra in standby mentre il controller wireless Xbox è connesso, qualsiasi input del controller risveglierà HoloLens. Puoi evitare questo problema spegnendo il controller quando hai finito di usarlo.

## Problemi noti per l'emulatore HoloLens

- Non tutte le app di Microsoft Store sono compatibili con l'emulatore. Ad esempio, i giovani Conker e i frammenti non sono riproducibili nell'emulatore.
- Non è possibile usare la webcam PC nell'emulatore.
- La caratteristica Anteprima live di Windows Device Portal non funziona con l'emulatore. È ancora possibile acquisire video e immagini di realtà miste.
