---
title: Problemi noti per HoloLens (prima generazione)
description: Rimanere aggiornati con l'elenco dei problemi noti e delle soluzioni alternative che possono interessare HoloLens clienti e sviluppatori che usano Unity e Windows Portale di dispositivi.
keywords: risoluzione dei problemi, problema noto, Guida
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 5c942bae91c7684f2c2d36aca6ace6306b5fed54
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032496"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Problemi noti per HoloLens (prima generazione)

Di seguito è riportato l'elenco corrente dei problemi noti HoloLens dispositivi. Controllare prima di tutto qui se si verifica un comportamento dispari. Questo elenco verrà mantenuto aggiornato quando vengono individuati o segnalati nuovi problemi o quando i problemi verranno risolti in HoloLens aggiornamenti software.

>[!NOTE]
> - Se si rileva un problema che non blocca, segnalarlo nel dispositivo HoloLens tramite [Hub di Feedback](hololens-feedback.md).
> - Se il problema che si verifica sta bloccando l'utente, oltre a inviare commenti e suggerimenti, [inviare una richiesta di supporto.](https://aka.ms/hlsupport)


- [Problemi noti per tutte le HoloLens generazioni](#known-issues-for-all-hololens-generations)
- [Problemi noti per HoloLens (prima generazione)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Problemi noti per tutte le HoloLens generazioni

### <a name="unity"></a>Unity

- Vedere [Installare gli strumenti](/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Unity consigliata per HoloLens sviluppo.
- I problemi noti di Unity HoloLens Technical Preview sono documentati nei [forum HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Portale di dispositivi di Windows

- La funzionalità anteprima live nell'acquisizione di realtà mista può presentare diversi secondi di latenza.

- Nella pagina Input virtuale i controlli Movimento e Scorrimento nella sezione Movimenti virtuali non sono funzionali. L'uso di questi strumenti non avrà alcun effetto. La tastiera virtuale nella pagina di input virtuale funziona correttamente.

- Dopo l'abilitazione della modalità sviluppatore Impostazioni, l'abilitazione del Portale di dispositivi potrebbe richiedere alcuni secondi.

### <a name="onedrive-camera-upload"></a>OneDrive caricamento della fotocamera

L'app OneDrive per HoloLens non supporta il caricamento automatico della fotocamera per gli account aziendali o dell'istituto di istruzione.

Soluzioni alternative:

- Se possibile per l'azienda, il caricamento automatico della fotocamera è supportato per gli account Microsoft consumer. È possibile accedere al proprio account Microsoft oltre all'account aziendale o dell'istituto di istruzione (l'app OneDrive supporta il doppio accesso. Dal profilo account Microsoft all'interno OneDrive è possibile abilitare il caricamento automatico del rullo della fotocamera in background.

- Se non è possibile usare in modo sicuro un account Microsoft consumer per caricare automaticamente le foto, è possibile caricare manualmente le foto nell'account aziendale o dell'istituto di istruzione dall'app OneDrive. A tale scopo, assicurarsi di aver eseguito l'accesso all'account aziendale o dell'istituto di istruzione nell'app OneDrive lavoro. Selezionare il **+** pulsante e scegliere **Upload**. Trovare le foto o i video da caricare passando a **Pictures (Immagini) > Camera Roll (Rullino).** Selezionare le foto o i video da caricare e quindi selezionare il **pulsante** Apri.

## <a name="known-issues-for-hololens-1st-gen"></a>Problemi noti per HoloLens (prima generazione)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Non è possibile connettersi e distribuirlo HoloLens tramite Visual Studio

> [!NOTE]
> Ultimo aggiornamento: 8/8 @ 17:11 - Visual Studio ha rilasciato Visual Studio 2019 versione 16.2 che include una correzione a questo problema. È consigliabile eseguire l'aggiornamento a questa versione più recente per evitare che si verifichi questo errore.

Visual Studio ha rilasciato Visual Studio 2019 versione 16.2, che include una correzione per questo problema. È consigliabile eseguire l'aggiornamento a questa versione più recente per evitare che si verifichi questo errore.

Causa radice del problema: gli utenti che hanno usato Visual Studio 2015 o le versioni precedenti di Visual Studio 2017 per distribuire ed eseguire il debug di applicazioni nel proprio HoloLens e successivamente hanno usato le versioni più recenti di Visual Studio 2017 o Visual Studio 2019 con lo stesso HoloLens saranno interessati. Le versioni più recenti Visual Studio distribuire una nuova versione di un componente, ma i file della versione precedente vengono lasciati nel dispositivo, causando l'errore della versione più recente.  Viene visualizzato il messaggio di errore seguente: DEP0100: Assicurarsi che nel dispositivo di destinazione sia abilitata la modalità sviluppatore. Impossibile ottenere una licenza per sviluppatori su \<ip\> a causa di un errore 80004005.

#### <a name="workaround"></a>Soluzione alternativa

Il team sta attualmente lavorando a una correzione. Nel frattempo, è possibile usare la procedura seguente per risolvere il problema e sbloccare la distribuzione e il debug:  

1. Aprire Visual Studio.

1. Selezionare **File** > **New** (Nuovo)  > **Project** (Progetto).

1. Selezionare **Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)**.

1. Assegnare un nome al progetto ,ad esempio "HoloLensDeploymentFix", assicurarsi che Framework sia impostato almeno su .NET Framework 4.5 e quindi selezionare **OK.**

1. Fare clic con il pulsante **destro del** mouse sul nodo Riferimenti Esplora soluzioni e aggiungere i riferimenti seguenti (selezionare la **sezione** Sfoglia e selezionare **Sfoglia):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Se non è installata la versione 10.0.18362.0, usare la versione più recente.

1. Fare clic con il pulsante destro del mouse sul progetto Esplora soluzioni selezionare **Aggiungi**  >  **elemento esistente.**

1. Passare a C:\Programmi (x86)\Windows Kits\10\bin\10.0.18362.0\x86 e modificare il filtro in Tutti i file **( \* . \* )**.

1. Selezionare sia SirepClient.dll che SshClient.dll e selezionare **Aggiungi.**

1. Individuare e selezionare entrambi i file in Esplora soluzioni (dovrebbero essere nella parte inferiore dell'elenco  dei file) e modificare Copia nella directory di **output** nella finestra Proprietà in **Copia sempre**.

1. All'inizio del file aggiungere quanto segue all'elenco esistente `using` di istruzioni :

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. `static void Main(...)`All'interno di aggiungere il codice seguente:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Selezionare **Compila** > **Compila soluzione**.

1. Aprire una finestra del prompt dei comandi e accedere alla cartella che contiene il file .exe compilato, ad esempio C:\MyProjects\HoloLensDeploymentFix\bin\Debug.

1. Eseguire il file eseguibile e specificare l'indirizzo IP del dispositivo come argomento della riga di comando. Se si è connessi tramite USB, è possibile usare 127.0.0.1. In caso contrario, usare l'indirizzo IP Wi-Fi dispositivo.  Ad esempio, "HoloLensDeploymentFix 127.0.0.1".

1. Dopo che lo strumento è stato chiuso senza messaggi (l'operazione dovrebbe richiedere solo pochi secondi), sarà possibile eseguire la distribuzione e il debug da Visual Studio 2017 o versione più recente.  Non è necessario continuare a usare lo strumento.

Verranno forniti altri aggiornamenti non appena saranno disponibili.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemi di avvio del Microsoft Store e delle app in HoloLens

> [!NOTE]
> Ultimo aggiornamento: 4/2 alle 10:00 - Problema risolto.

È possibile che si verifichino problemi quando si tenta di avviare il Microsoft Store e le app HoloLens. È stato determinato che il problema si verifica quando gli aggiornamenti delle app in background distribuiscono una versione più recente dei pacchetti del framework in sequenze specifiche mentre una o più app dipendenti sono ancora in esecuzione. In questo caso, un aggiornamento automatico delle app ha recapitato una nuova versione di .NET Native Framework (dalla versione 10.0.25531 alla 10.0.27413) ha causato l'aggiornamento non corretto delle app in esecuzione per tutte le app in esecuzione che utilizzano la versione precedente del framework.  Il flusso per l'aggiornamento del framework è il seguente:

1. Il nuovo pacchetto framework viene scaricato dallo Store e installato.

1. Tutte le app che usano il framework precedente vengono "aggiornate" per usare la versione più recente.

Se il passaggio 2 viene interrotto prima del completamento, tutte le app per cui non è stato registrato il framework più recente non verranno avviate dal menu Start.  Si ritiene che qualsiasi app HoloLens potrebbe essere interessata da questo problema.

Alcuni utenti hanno segnalato che la chiusura delle app bloccata e l'avvio di altre app, ad esempio Hub di Feedback, Visualizzatore 3D o Foto, consentono di risolvere il problema. Tuttavia, questo non funziona il 100% del tempo.

Questo problema non è stato causato dall'aggiornamento stesso, ma da un bug nel sistema operativo che ha causato la gestione non corretta dell'aggiornamento del framework .NET Native. Microsoft è lieta di annunciare che è stata identificata una correzione e che è stato rilasciato un aggiornamento (versione del sistema operativo 17763.380) contenente la correzione.  

Per verificare se il dispositivo può eseguire l'aggiornamento:

1. Passare all'app Impostazioni e aprire **Aggiorna & Sicurezza**.

1. Selezionare **Controlla aggiornamenti**.

1. Se è disponibile l'aggiornamento alla versione 17763.380, eseguire l'aggiornamento a questa build per ricevere la correzione del bug di blocco dell'app.

1. Dopo l'aggiornamento a questa versione del sistema operativo, le app dovrebbero funzionare come previsto.

Inoltre, come per ogni versione del HoloLens, l'immagine FFU è stata pubblicata [nell'Area download Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Se non si vuole eseguire l'aggiornamento, è stata rilasciata una nuova versione dell'app UWP Microsoft Store data 29/3. Dopo aver aggiornato la versione dello Store:

1. Aprire lo Store e verificare che sia caricato.
1. Usare il movimento di fiore per aprire il menu.
1. Provare ad aprire le app interrotte in precedenza.
1. Se non è ancora possibile avviarla, toccare e tenere premuta l'icona dell'app interrotta e selezionare Disinstalla.
1. Reinstallare queste app dallo Store.

Se il dispositivo non è ancora in grado di caricare le app, è possibile eseguire il sideload di una versione di .NET Native Framework e runtime tramite l'Area download seguendo questa procedura:

1. Scaricare questo [file ZIP dall'Area](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) download Microsoft. La decompressione produrrà due file.  Microsoft .NET.Native.Runtime.1.7.appx e Microsoft .NET.Native.Framework.1.7.appx.

1. Verificare che il dispositivo sia sbloccato per lo sviluppo.  Se non è già stato fatto in precedenza, vedere Uso [del Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal) per istruzioni.

1. Si vuole quindi accedere al Windows Portale di dispositivi. È consigliabile eseguire questa operazione tramite USB digitando http://127.0.0.1:10080 nel browser.

1. Dopo aver installato Windows Portale di dispositivi, è necessario eseguire il "side load" dei due file scaricati. A tale scopo, è necessario passare verso il basso nella barra laterale sinistra fino a visualizzare la **sezione** App e selezionare **App.**

1. Verrà quindi visualizzata una schermata simile alla seguente.  Si vuole passare alla sezione Installare **l'app** e passare alla posizione in cui sono stati decompressi i due file APPX. È possibile eseguire una sola operazione alla volta, quindi dopo aver selezionato il primo, fare clic su "Vai" nella sezione Distribuisci. Eseguire quindi questa operazione per il secondo file APPX.

   ![Windows Portale di dispositivi installare lSide-Loaded app.](images/20190322-DevicePortal.png)

1. A questo punto si ritiene che le applicazioni debbano ricominciare a funzionare e che sia anche possibile accedere allo Store.

1. In alcuni casi, è necessario eseguire il passaggio aggiuntivo di avvio dell'app Visualizzatore 3D prima dell'avvio delle app interessate.

Siamo molto apprezzati dal fatto che il processo di risoluzione del problema è stato completato e non vediamo l'ora di continuare a lavorare con la community per creare esperienze di realtà mista di successo.

### <a name="device-update"></a>Aggiornamento del dispositivo

- 30 secondi dopo un nuovo aggiornamento, la shell potrebbe scomparire una volta. Eseguire il movimento **di fiore** per riprendere la sessione.

### <a name="visual-studio"></a>Visual Studio

- Vedere [Installare gli strumenti](/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Visual Studio consigliata per lo sviluppo HoloLens applicazioni.

- Quando si distribuisce un'app da Visual Studio al HoloLens, è possibile che venga visualizzato l'errore: L'operazione richiesta non può essere eseguita su un file con una sezione mappata **all'utente aperta. (Eccezione da HRESULT: 0x800704C8)**. In questo caso, riprovare e la distribuzione avrà in genere esito positivo.

### <a name="api"></a>API

- Se l'applicazione [](/windows/mixed-reality/focus-point-in-unity) imposta il punto di messa a fuoco dietro l'utente o la normale su camera.forward, gli ologrammi non verranno visualizzati Acquisizione realtà mista foto o video. Fino a quando questo bug non viene risolto in [](/windows/mixed-reality/focus-point-in-unity) Windows, se le applicazioni impostano attivamente il punto di messa a fuoco, devono assicurarsi che la normale del piano sia impostata in avanti opposta (ad esempio, normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Controller wireless Xbox

- Il controller wireless Xbox S deve essere aggiornato prima di poter essere usato con HoloLens. Assicurarsi di essere [aggiornati prima di](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) provare ad associare il controller a un HoloLens.

- Se si riavvia il HoloLens mentre il controller wireless Xbox è connesso, il controller non si riconnette automaticamente a HoloLens. La luce del pulsante Guida lampeggia lentamente fino a quando il controller non si spegne dopo 3 minuti. Per riconnettere immediatamente il controller, spegnere il controller tenendo premuto il pulsante Guida fino a quando la luce non si spegne. Quando si rialleva il controller, si riconnetterà al HoloLens.

- Se il HoloLens entra in standby mentre il controller wireless Xbox è connesso, qualsiasi input sul controller riattiva il HoloLens. È possibile evitare questo problema spegnendo il controller al termine dell'uso.

