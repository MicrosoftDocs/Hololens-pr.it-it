---
title: Problemi noti per HoloLens (prima generazione)
description: Tenere aggiornato l'elenco dei problemi noti e delle soluzioni alternative che possono interessare i clienti e gli sviluppatori di HoloLens che usano Unity e Portale di dispositivi di Windows.
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
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923551"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Problemi noti per HoloLens (prima generazione)

Ecco l'elenco corrente dei problemi noti per i dispositivi HoloLens. Verificare prima di tutto se viene visualizzato un comportamento dispari. Questo elenco verrà mantenuto aggiornato quando vengono individuati o segnalati nuovi problemi o quando i problemi verranno risolti nei futuri aggiornamenti software HoloLens.

>[!NOTE]
> - Se si rileva un problema che non blocca, segnalarlo nel dispositivo HoloLens [tramite Hub di Feedback](hololens-feedback.md).
> - Se il problema che si verifica sta bloccando l'utente, oltre a inviare commenti e suggerimenti, [inviare una richiesta di supporto.](https://aka.ms/hlsupport)


- [Problemi noti per tutte le generazioni HoloLens](#known-issues-for-all-hololens-generations)
- [Problemi noti per HoloLens (prima generazione)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Problemi noti per tutte le generazioni HoloLens

### <a name="unity"></a>Unity

- Vedere [Installare gli strumenti](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Unity consigliata per lo sviluppo HoloLens.
- I problemi noti con Unity HoloLens Technical Preview sono documentati nei forum di [HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Portale di dispositivi di Windows

- La funzionalità Anteprima dinamica nell'acquisizione di realtà mista può presentare alcuni secondi di latenza.

- Nella pagina Input virtuale i controlli Movimento e Scorrimento nella sezione Movimenti virtuali non sono funzionali. Il loro uso non avrà alcun effetto. La tastiera virtuale nella pagina di input virtuale funziona correttamente.

- Dopo l'abilitazione della modalità sviluppatore in Impostazioni, l'attivazione dell'Portale di dispositivi l'opzione potrebbe richiedere alcuni secondi.

### <a name="onedrive-camera-upload"></a>Caricamento della fotocamera di OneDrive

L'app OneDrive per HoloLens non supporta il caricamento automatico della fotocamera per gli account aziendali o dell'istituto di istruzione.

Soluzioni alternative:

- Se possibile per l'azienda, il caricamento automatico della fotocamera è supportato sugli account Microsoft consumer. È possibile accedere alla propria account Microsoft oltre all'account aziendale o dell'istituto di istruzione (l'app OneDrive supporta il doppio accesso). Dal profilo account Microsoft all'interno di OneDrive è possibile abilitare il caricamento automatico del rullino in background.

- Se non è possibile usare in modo sicuro un account Microsoft consumer per caricare automaticamente le foto, è possibile caricare manualmente le foto nell'account aziendale o dell'istituto di istruzione dall'app OneDrive. A tale scopo, assicurarsi di aver eseguito l'accesso all'account aziendale o dell'istituto di istruzione nell'app OneDrive. Selezionare il **+** pulsante e scegliere **Carica**. Trovare le foto o i video da caricare passando a **Immagini > Rullino.** Selezionare le foto o i video da caricare e quindi fare clic **sul pulsante** Apri.

## <a name="known-issues-for-hololens-1st-gen"></a>Problemi noti per HoloLens (prima generazione)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Non è possibile connettersi e distribuire in HoloLens tramite Visual Studio

> [!NOTE]
> Ultimo aggiornamento: 8/8 @ 17:11 - Visual Studio ha rilasciato VS 2019 versione 16.2 che include una correzione a questo problema. È consigliabile eseguire l'aggiornamento a questa versione più recente per evitare che si verifichi questo errore.

Visual Studio ha rilasciato VS 2019 versione 16.2, che include una correzione a questo problema. È consigliabile eseguire l'aggiornamento a questa versione più recente per evitare che si verifichi questo errore.

Causa radice del problema: verranno interessati gli utenti che hanno usato Visual Studio 2015 o versioni precedenti di Visual Studio 2017 per distribuire ed eseguire il debug di applicazioni in HoloLens e successivamente hanno usato le versioni più recenti di Visual Studio 2017 o Visual Studio 2019 con lo stesso HoloLens. Le versioni più recenti di Visual Studio una nuova versione di un componente, ma i file della versione precedente vengono lasciati nel dispositivo, causando l'esito negativo della versione più recente.  Ciò causa il seguente messaggio di errore: DEP0100: Assicurarsi che nel dispositivo di destinazione sia abilitata la modalità sviluppatore. Impossibile ottenere una licenza per sviluppatori in \<ip\> a causa dell'errore 80004005.

#### <a name="workaround"></a>Soluzione alternativa

Il team sta attualmente lavorando a una correzione. Nel frattempo, è possibile usare la procedura seguente per risolvere il problema e sbloccare la distribuzione e il debug:  

1. Aprire Visual Studio.

1. Selezionare **File** > **New** (Nuovo)  > **Project** (Progetto).

1. Selezionare **Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)**.

1. Assegnare un nome al progetto ,ad esempio "HoloLensDeploymentFix" e assicurarsi che Framework sia impostato almeno su .NET Framework 4.5, quindi selezionare **OK.**

1. Fare clic con il pulsante **destro del** mouse sul nodo Riferimenti Esplora soluzioni e aggiungere i riferimenti seguenti (selezionare la sezione **Sfoglia** e selezionare **Sfoglia**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Se non è installata la versione 10.0.18362.0, usare la versione più recente disponibile.

1. Fare clic con il pulsante destro del mouse sul progetto Esplora soluzioni selezionare **Aggiungi**  >  **elemento esistente**.

1. Passare a C:\Programmi (x86)\Windows Kits\10\bin\10.0.18362.0\x86 e modificare il filtro in Tutti i **file ( \* . \* )**.

1. Selezionare sia SirepClient.dll che SshClient.dll e selezionare **Aggiungi**.

1. Individuare e selezionare entrambi i file in Esplora soluzioni (dovrebbero essere nella parte inferiore dell'elenco  di file) e modificare Copia nella **directory di output** nella finestra Proprietà in **Copia sempre**.

1. Nella parte superiore del file aggiungere quanto segue all'elenco esistente `using` di istruzioni:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. All'interno `static void Main(...)` di aggiungere il codice seguente:

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

1. Aprire una finestra del prompt dei comandi e un cd nella cartella che contiene il file .exe compilato, ad esempio C:\MyProjects\HoloLensDeploymentFix\bin\Debug.

1. Eseguire il file eseguibile e specificare l'indirizzo IP del dispositivo come argomento della riga di comando. Se connesso tramite USB, è possibile usare 127.0.0.1, in caso contrario usare l'indirizzo IP Wi-Fi dispositivo.  Ad esempio, "HoloLensDeploymentFix 127.0.0.1".

1. Dopo che lo strumento è stato chiuso senza messaggi (l'operazione dovrebbe richiedere solo pochi secondi), sarà ora possibile eseguire la distribuzione e il debug da Visual Studio 2017 o versione più recente.  L'uso continuo dello strumento non è necessario.

Verranno forniti altri aggiornamenti non appena saranno disponibili.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemi di avvio del Microsoft Store e delle app in HoloLens

> [!NOTE]
> Ultimo aggiornamento: 4/2 @ 10:00 - Problema risolto.

È possibile che si verifichino problemi quando si tenta di avviare il Microsoft Store e le app in HoloLens. È stato determinato che il problema si verifica quando gli aggiornamenti delle app in background distribuiscono una versione più recente dei pacchetti del framework in sequenze specifiche mentre una o più app dipendenti sono ancora in esecuzione. In questo caso, un aggiornamento automatico dell'app ha recapitato una nuova versione di .NET Native Framework (versione da 10.0.25531 a 10.0.27413) ha causato l'aggiornamento non corretto delle app in esecuzione per tutte le app in esecuzione che utilizzano la versione precedente del framework.  Il flusso per l'aggiornamento del framework è il seguente:

1. Il nuovo pacchetto del framework viene scaricato dallo store e installato.

1. Tutte le app che usano il framework precedente vengono "aggiornate" per usare la versione più recente.

Se il passaggio 2 viene interrotto prima del completamento, tutte le app per cui non è stato registrato il framework più recente non verranno avviate dal menu Start.  Si ritiene che qualsiasi app in HoloLens potrebbe essere interessata da questo problema.

Alcuni utenti hanno segnalato che la chiusura delle app sospese e l'avvio di altre app, ad esempio Hub di Feedback, Visualizzatore 3D o Foto, risolve il problema per loro, ma questo non funziona al 100% del tempo.

È stato causato che questo problema non ha causato l'aggiornamento stesso, ma un bug nel sistema operativo che ha causato la gestione non corretta dell'aggiornamento del framework di .NET Native. Siamo lieti di annunciare che è stata identificata una correzione e che è stato rilasciato un aggiornamento (versione del sistema operativo 17763.380) contenente la correzione.  

Per verificare se il dispositivo può eseguire l'aggiornamento:

1. Passare all'app Impostazioni e aprire **Aggiorna & Sicurezza**.

1. Selezionare **Controlla aggiornamenti**.

1. Se è disponibile l'aggiornamento alla versione 17763.380, eseguire l'aggiornamento a questa build per ricevere la correzione del bug di blocco dell'app.

1. Dopo l'aggiornamento a questa versione del sistema operativo, le app dovrebbero funzionare come previsto.

Inoltre, come per ogni versione del sistema operativo HoloLens, l'immagine FFU è stata pubblicata [nell'Area download Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Se non si vuole eseguire l'aggiornamento, è stata rilasciata una nuova versione dell'app UWP Microsoft Store 3/29. Dopo aver aggiornato la versione dello Store:

1. Aprire lo Store e verificare che sia caricato.
1. Usare il movimento bloom per aprire il menu.
1. Provare ad aprire le app interrotte in precedenza.
1. Se non è ancora possibile avviarla, toccare e tenere premuta l'icona dell'app interrotta e selezionare Disinstalla.
1. Reinstallare queste app dallo Store.

Se il dispositivo non è ancora in grado di caricare le app, è possibile eseguire il sideload di una versione di .NET Native Framework e runtime tramite l'Area download seguendo questa procedura:

1. Scaricare questo [file ZIP dall'Area](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) download Microsoft. Decomprimendo verranno prodotti due file.  Microsoft .NET.Native.Runtime.1.7.appx e Microsoft .NET.Native.Framework.1.7.appx.

1. Verificare che il dispositivo sia sbloccato.  Se non è già stato fatto in precedenza, vedere Uso del [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) per istruzioni.

1. Si vuole quindi accedere al Portale di dispositivi di Windows. È consigliabile eseguire questa operazione tramite USB, digitando http://127.0.0.1:10080 nel browser.

1. Dopo aver creato Portale di dispositivi di Windows è necessario "caricare in side load" i due file scaricati. A tale scopo, è necessario passare verso il basso nella barra laterale sinistra fino a quando non si arriva alla **sezione** App e selezionare **App**.

1. Verrà quindi visualizzata una schermata simile alla seguente.  Passare alla sezione Installare **l'app** e passare alla posizione in cui sono stati decompressi i due file APPX. È possibile eseguire una sola operazione alla volta, quindi dopo aver selezionato il primo, fare clic su "Vai" nella sezione Distribuisci. Eseguire quindi questa operazione per il secondo file APPX.

   ![Portale di dispositivi di Windows installare l'app Side-Loaded](images/20190322-DevicePortal.png)

1. A questo punto si ritiene che le applicazioni dovrebbero iniziare a funzionare di nuovo e che sia anche possibile accedere allo Store.

1. In alcuni casi, è necessario eseguire il passaggio aggiuntivo di avvio dell'app Visualizzatore 3D prima dell'avvio delle app interessate.

La sua attenzione è stata apprezzata durante il processo di risoluzione del problema e non vediamo l'ora di continuare a lavorare con la community per creare esperienze di realtà mista di successo.

### <a name="device-update"></a>Aggiornamento del dispositivo

- 30 secondi dopo un nuovo aggiornamento, la shell potrebbe scomparire una volta. Eseguire il movimento **bloom** per riprendere la sessione.

### <a name="visual-studio"></a>Visual Studio

- Vedere [Installare gli strumenti](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Visual Studio consigliata per lo sviluppo di HoloLens.

- Quando si distribuisce un'app Visual Studio in HoloLens, è possibile che venga visualizzato l'errore: L'operazione richiesta non può essere eseguita su un file con una sezione mappata **dall'utente aperta. (Eccezione da HRESULT: 0x800704C8)**. In questo caso, riprovare e la distribuzione avrà in genere esito positivo.

### <a name="api"></a>API

- Se l'applicazione imposta il [punto](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) di messa a fuoco dietro l'utente o il normale su camera.forward, gli ologrammi non verranno visualizzati Acquisizione realtà mista foto o video. Fino a quando questo bug non viene [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) risolto in Windows, se le applicazioni impostano attivamente il punto di messa a fuoco, devono assicurarsi che la normale del piano sia impostata in avanti rispetto alla fotocamera (ad esempio, normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Controller wireless Xbox

- Il controller wireless Xbox S deve essere aggiornato prima di poter essere usato con HoloLens. Assicurarsi di essere [aggiornati prima](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) di tentare di associare il controller a un holoLens.

- Se si riavvia HoloLens mentre il controller wireless Xbox è connesso, il controller non si riconnette automaticamente a HoloLens. La luce del pulsante Guida lampeggia lentamente fino a quando il controller non si spegni dopo 3 minuti. Per riconnettere immediatamente il controller, spegnere il controller tenendo premuto il pulsante Guida fino a quando la luce non si spegne. Quando si riasscierà il controller, si riconnetterà a HoloLens.

- Se HoloLens entra in standby mentre il controller wireless Xbox è connesso, qualsiasi input nel controller riattiva HoloLens. È possibile evitare questo problema spegnendo il controller al termine dell'uso.

