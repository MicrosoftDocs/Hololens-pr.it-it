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
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="89853-104">Problemi noti per HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="89853-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="89853-105">Ecco l'elenco corrente dei problemi noti per i dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="89853-106">Verificare prima di tutto se viene visualizzato un comportamento dispari.</span><span class="sxs-lookup"><span data-stu-id="89853-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="89853-107">Questo elenco verrà mantenuto aggiornato quando vengono individuati o segnalati nuovi problemi o quando i problemi verranno risolti nei futuri aggiornamenti software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="89853-108">Se si rileva un problema che non blocca, segnalarlo nel dispositivo HoloLens [tramite Hub di Feedback](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="89853-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="89853-109">Se il problema che si verifica sta bloccando l'utente, oltre a inviare commenti e suggerimenti, [inviare una richiesta di supporto.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="89853-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="89853-110">Problemi noti per tutte le generazioni HoloLens</span><span class="sxs-lookup"><span data-stu-id="89853-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="89853-111">Problemi noti per HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="89853-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="89853-112">Problemi noti per tutte le generazioni HoloLens</span><span class="sxs-lookup"><span data-stu-id="89853-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="89853-113">Unity</span><span class="sxs-lookup"><span data-stu-id="89853-113">Unity</span></span>

- <span data-ttu-id="89853-114">Vedere [Installare gli strumenti](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Unity consigliata per lo sviluppo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-114">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="89853-115">I problemi noti con Unity HoloLens Technical Preview sono documentati nei forum di [HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="89853-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="89853-116">Portale di dispositivi di Windows</span><span class="sxs-lookup"><span data-stu-id="89853-116">Windows Device Portal</span></span>

- <span data-ttu-id="89853-117">La funzionalità Anteprima dinamica nell'acquisizione di realtà mista può presentare alcuni secondi di latenza.</span><span class="sxs-lookup"><span data-stu-id="89853-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="89853-118">Nella pagina Input virtuale i controlli Movimento e Scorrimento nella sezione Movimenti virtuali non sono funzionali.</span><span class="sxs-lookup"><span data-stu-id="89853-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="89853-119">Il loro uso non avrà alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="89853-119">Using them will have no effect.</span></span> <span data-ttu-id="89853-120">La tastiera virtuale nella pagina di input virtuale funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="89853-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="89853-121">Dopo l'abilitazione della modalità sviluppatore in Impostazioni, l'attivazione dell'Portale di dispositivi l'opzione potrebbe richiedere alcuni secondi.</span><span class="sxs-lookup"><span data-stu-id="89853-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="89853-122">Caricamento della fotocamera di OneDrive</span><span class="sxs-lookup"><span data-stu-id="89853-122">OneDrive camera upload</span></span>

<span data-ttu-id="89853-123">L'app OneDrive per HoloLens non supporta il caricamento automatico della fotocamera per gli account aziendali o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="89853-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="89853-124">Soluzioni alternative:</span><span class="sxs-lookup"><span data-stu-id="89853-124">Workarounds:</span></span>

- <span data-ttu-id="89853-125">Se possibile per l'azienda, il caricamento automatico della fotocamera è supportato sugli account Microsoft consumer.</span><span class="sxs-lookup"><span data-stu-id="89853-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="89853-126">È possibile accedere alla propria account Microsoft oltre all'account aziendale o dell'istituto di istruzione (l'app OneDrive supporta il doppio accesso).</span><span class="sxs-lookup"><span data-stu-id="89853-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="89853-127">Dal profilo account Microsoft all'interno di OneDrive è possibile abilitare il caricamento automatico del rullino in background.</span><span class="sxs-lookup"><span data-stu-id="89853-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="89853-128">Se non è possibile usare in modo sicuro un account Microsoft consumer per caricare automaticamente le foto, è possibile caricare manualmente le foto nell'account aziendale o dell'istituto di istruzione dall'app OneDrive.</span><span class="sxs-lookup"><span data-stu-id="89853-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="89853-129">A tale scopo, assicurarsi di aver eseguito l'accesso all'account aziendale o dell'istituto di istruzione nell'app OneDrive.</span><span class="sxs-lookup"><span data-stu-id="89853-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="89853-130">Selezionare il **+** pulsante e scegliere **Carica**.</span><span class="sxs-lookup"><span data-stu-id="89853-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="89853-131">Trovare le foto o i video da caricare passando a **Immagini > Rullino.**</span><span class="sxs-lookup"><span data-stu-id="89853-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="89853-132">Selezionare le foto o i video da caricare e quindi fare clic **sul pulsante** Apri.</span><span class="sxs-lookup"><span data-stu-id="89853-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="89853-133">Problemi noti per HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="89853-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="89853-134">Non è possibile connettersi e distribuire in HoloLens tramite Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89853-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="89853-135">Ultimo aggiornamento: 8/8 @ 17:11 - Visual Studio ha rilasciato VS 2019 versione 16.2 che include una correzione a questo problema.</span><span class="sxs-lookup"><span data-stu-id="89853-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="89853-136">È consigliabile eseguire l'aggiornamento a questa versione più recente per evitare che si verifichi questo errore.</span><span class="sxs-lookup"><span data-stu-id="89853-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="89853-137">Visual Studio ha rilasciato VS 2019 versione 16.2, che include una correzione a questo problema.</span><span class="sxs-lookup"><span data-stu-id="89853-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="89853-138">È consigliabile eseguire l'aggiornamento a questa versione più recente per evitare che si verifichi questo errore.</span><span class="sxs-lookup"><span data-stu-id="89853-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="89853-139">Causa radice del problema: verranno interessati gli utenti che hanno usato Visual Studio 2015 o versioni precedenti di Visual Studio 2017 per distribuire ed eseguire il debug di applicazioni in HoloLens e successivamente hanno usato le versioni più recenti di Visual Studio 2017 o Visual Studio 2019 con lo stesso HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="89853-140">Le versioni più recenti di Visual Studio una nuova versione di un componente, ma i file della versione precedente vengono lasciati nel dispositivo, causando l'esito negativo della versione più recente.</span><span class="sxs-lookup"><span data-stu-id="89853-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="89853-141">Ciò causa il seguente messaggio di errore: DEP0100: Assicurarsi che nel dispositivo di destinazione sia abilitata la modalità sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="89853-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="89853-142">Impossibile ottenere una licenza per sviluppatori in \<ip\> a causa dell'errore 80004005.</span><span class="sxs-lookup"><span data-stu-id="89853-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="89853-143">Soluzione alternativa</span><span class="sxs-lookup"><span data-stu-id="89853-143">Workaround</span></span>

<span data-ttu-id="89853-144">Il team sta attualmente lavorando a una correzione.</span><span class="sxs-lookup"><span data-stu-id="89853-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="89853-145">Nel frattempo, è possibile usare la procedura seguente per risolvere il problema e sbloccare la distribuzione e il debug:</span><span class="sxs-lookup"><span data-stu-id="89853-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="89853-146">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89853-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="89853-147">Selezionare **File** > **New** (Nuovo)  > **Project** (Progetto).</span><span class="sxs-lookup"><span data-stu-id="89853-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="89853-148">Selezionare **Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="89853-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="89853-149">Assegnare un nome al progetto ,ad esempio "HoloLensDeploymentFix" e assicurarsi che Framework sia impostato almeno su .NET Framework 4.5, quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="89853-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="89853-150">Fare clic con il pulsante **destro del** mouse sul nodo Riferimenti Esplora soluzioni e aggiungere i riferimenti seguenti (selezionare la sezione **Sfoglia** e selezionare **Sfoglia**):</span><span class="sxs-lookup"><span data-stu-id="89853-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="89853-151">Se non è installata la versione 10.0.18362.0, usare la versione più recente disponibile.</span><span class="sxs-lookup"><span data-stu-id="89853-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="89853-152">Fare clic con il pulsante destro del mouse sul progetto Esplora soluzioni selezionare **Aggiungi**  >  **elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="89853-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="89853-153">Passare a C:\Programmi (x86)\Windows Kits\10\bin\10.0.18362.0\x86 e modificare il filtro in Tutti i **file ( \* . \* )**.</span><span class="sxs-lookup"><span data-stu-id="89853-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="89853-154">Selezionare sia SirepClient.dll che SshClient.dll e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="89853-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="89853-155">Individuare e selezionare entrambi i file in Esplora soluzioni (dovrebbero essere nella parte inferiore dell'elenco  di file) e modificare Copia nella **directory di output** nella finestra Proprietà in **Copia sempre**.</span><span class="sxs-lookup"><span data-stu-id="89853-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="89853-156">Nella parte superiore del file aggiungere quanto segue all'elenco esistente `using` di istruzioni:</span><span class="sxs-lookup"><span data-stu-id="89853-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="89853-157">All'interno `static void Main(...)` di aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="89853-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="89853-158">Selezionare **Compila** > **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="89853-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="89853-159">Aprire una finestra del prompt dei comandi e un cd nella cartella che contiene il file .exe compilato, ad esempio C:\MyProjects\HoloLensDeploymentFix\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="89853-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="89853-160">Eseguire il file eseguibile e specificare l'indirizzo IP del dispositivo come argomento della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="89853-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="89853-161">Se connesso tramite USB, è possibile usare 127.0.0.1, in caso contrario usare l'indirizzo IP Wi-Fi dispositivo.  Ad esempio, "HoloLensDeploymentFix 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="89853-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="89853-162">Dopo che lo strumento è stato chiuso senza messaggi (l'operazione dovrebbe richiedere solo pochi secondi), sarà ora possibile eseguire la distribuzione e il debug da Visual Studio 2017 o versione più recente.</span><span class="sxs-lookup"><span data-stu-id="89853-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="89853-163">L'uso continuo dello strumento non è necessario.</span><span class="sxs-lookup"><span data-stu-id="89853-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="89853-164">Verranno forniti altri aggiornamenti non appena saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="89853-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="89853-165">Problemi di avvio del Microsoft Store e delle app in HoloLens</span><span class="sxs-lookup"><span data-stu-id="89853-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="89853-166">Ultimo aggiornamento: 4/2 @ 10:00 - Problema risolto.</span><span class="sxs-lookup"><span data-stu-id="89853-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="89853-167">È possibile che si verifichino problemi quando si tenta di avviare il Microsoft Store e le app in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="89853-168">È stato determinato che il problema si verifica quando gli aggiornamenti delle app in background distribuiscono una versione più recente dei pacchetti del framework in sequenze specifiche mentre una o più app dipendenti sono ancora in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="89853-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="89853-169">In questo caso, un aggiornamento automatico dell'app ha recapitato una nuova versione di .NET Native Framework (versione da 10.0.25531 a 10.0.27413) ha causato l'aggiornamento non corretto delle app in esecuzione per tutte le app in esecuzione che utilizzano la versione precedente del framework.</span><span class="sxs-lookup"><span data-stu-id="89853-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="89853-170">Il flusso per l'aggiornamento del framework è il seguente:</span><span class="sxs-lookup"><span data-stu-id="89853-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="89853-171">Il nuovo pacchetto del framework viene scaricato dallo store e installato.</span><span class="sxs-lookup"><span data-stu-id="89853-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="89853-172">Tutte le app che usano il framework precedente vengono "aggiornate" per usare la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="89853-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="89853-173">Se il passaggio 2 viene interrotto prima del completamento, tutte le app per cui non è stato registrato il framework più recente non verranno avviate dal menu Start.</span><span class="sxs-lookup"><span data-stu-id="89853-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="89853-174">Si ritiene che qualsiasi app in HoloLens potrebbe essere interessata da questo problema.</span><span class="sxs-lookup"><span data-stu-id="89853-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="89853-175">Alcuni utenti hanno segnalato che la chiusura delle app sospese e l'avvio di altre app, ad esempio Hub di Feedback, Visualizzatore 3D o Foto, risolve il problema per loro, ma questo non funziona al 100% del tempo.</span><span class="sxs-lookup"><span data-stu-id="89853-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="89853-176">È stato causato che questo problema non ha causato l'aggiornamento stesso, ma un bug nel sistema operativo che ha causato la gestione non corretta dell'aggiornamento del framework di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="89853-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="89853-177">Siamo lieti di annunciare che è stata identificata una correzione e che è stato rilasciato un aggiornamento (versione del sistema operativo 17763.380) contenente la correzione.</span><span class="sxs-lookup"><span data-stu-id="89853-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="89853-178">Per verificare se il dispositivo può eseguire l'aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="89853-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="89853-179">Passare all'app Impostazioni e aprire **Aggiorna & Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="89853-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="89853-180">Selezionare **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="89853-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="89853-181">Se è disponibile l'aggiornamento alla versione 17763.380, eseguire l'aggiornamento a questa build per ricevere la correzione del bug di blocco dell'app.</span><span class="sxs-lookup"><span data-stu-id="89853-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="89853-182">Dopo l'aggiornamento a questa versione del sistema operativo, le app dovrebbero funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="89853-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="89853-183">Inoltre, come per ogni versione del sistema operativo HoloLens, l'immagine FFU è stata pubblicata [nell'Area download Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)</span><span class="sxs-lookup"><span data-stu-id="89853-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="89853-184">Se non si vuole eseguire l'aggiornamento, è stata rilasciata una nuova versione dell'app UWP Microsoft Store 3/29.</span><span class="sxs-lookup"><span data-stu-id="89853-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="89853-185">Dopo aver aggiornato la versione dello Store:</span><span class="sxs-lookup"><span data-stu-id="89853-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="89853-186">Aprire lo Store e verificare che sia caricato.</span><span class="sxs-lookup"><span data-stu-id="89853-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="89853-187">Usare il movimento bloom per aprire il menu.</span><span class="sxs-lookup"><span data-stu-id="89853-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="89853-188">Provare ad aprire le app interrotte in precedenza.</span><span class="sxs-lookup"><span data-stu-id="89853-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="89853-189">Se non è ancora possibile avviarla, toccare e tenere premuta l'icona dell'app interrotta e selezionare Disinstalla.</span><span class="sxs-lookup"><span data-stu-id="89853-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="89853-190">Reinstallare queste app dallo Store.</span><span class="sxs-lookup"><span data-stu-id="89853-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="89853-191">Se il dispositivo non è ancora in grado di caricare le app, è possibile eseguire il sideload di una versione di .NET Native Framework e runtime tramite l'Area download seguendo questa procedura:</span><span class="sxs-lookup"><span data-stu-id="89853-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="89853-192">Scaricare questo [file ZIP dall'Area](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89853-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="89853-193">Decomprimendo verranno prodotti due file.</span><span class="sxs-lookup"><span data-stu-id="89853-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="89853-194">Microsoft .NET.Native.Runtime.1.7.appx e Microsoft .NET.Native.Framework.1.7.appx.</span><span class="sxs-lookup"><span data-stu-id="89853-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="89853-195">Verificare che il dispositivo sia sbloccato.</span><span class="sxs-lookup"><span data-stu-id="89853-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="89853-196">Se non è già stato fatto in precedenza, vedere Uso del [Portale di dispositivi di Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) per istruzioni.</span><span class="sxs-lookup"><span data-stu-id="89853-196">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="89853-197">Si vuole quindi accedere al Portale di dispositivi di Windows.</span><span class="sxs-lookup"><span data-stu-id="89853-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="89853-198">È consigliabile eseguire questa operazione tramite USB, digitando http://127.0.0.1:10080 nel browser.</span><span class="sxs-lookup"><span data-stu-id="89853-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="89853-199">Dopo aver creato Portale di dispositivi di Windows è necessario "caricare in side load" i due file scaricati.</span><span class="sxs-lookup"><span data-stu-id="89853-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="89853-200">A tale scopo, è necessario passare verso il basso nella barra laterale sinistra fino a quando non si arriva alla **sezione** App e selezionare **App**.</span><span class="sxs-lookup"><span data-stu-id="89853-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="89853-201">Verrà quindi visualizzata una schermata simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="89853-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="89853-202">Passare alla sezione Installare **l'app** e passare alla posizione in cui sono stati decompressi i due file APPX.</span><span class="sxs-lookup"><span data-stu-id="89853-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="89853-203">È possibile eseguire una sola operazione alla volta, quindi dopo aver selezionato il primo, fare clic su "Vai" nella sezione Distribuisci.</span><span class="sxs-lookup"><span data-stu-id="89853-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="89853-204">Eseguire quindi questa operazione per il secondo file APPX.</span><span class="sxs-lookup"><span data-stu-id="89853-204">Then do this for the second APPX file.</span></span>

   ![Portale di dispositivi di Windows installare l'app Side-Loaded](images/20190322-DevicePortal.png)

1. <span data-ttu-id="89853-206">A questo punto si ritiene che le applicazioni dovrebbero iniziare a funzionare di nuovo e che sia anche possibile accedere allo Store.</span><span class="sxs-lookup"><span data-stu-id="89853-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="89853-207">In alcuni casi, è necessario eseguire il passaggio aggiuntivo di avvio dell'app Visualizzatore 3D prima dell'avvio delle app interessate.</span><span class="sxs-lookup"><span data-stu-id="89853-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="89853-208">La sua attenzione è stata apprezzata durante il processo di risoluzione del problema e non vediamo l'ora di continuare a lavorare con la community per creare esperienze di realtà mista di successo.</span><span class="sxs-lookup"><span data-stu-id="89853-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="89853-209">Aggiornamento del dispositivo</span><span class="sxs-lookup"><span data-stu-id="89853-209">Device Update</span></span>

- <span data-ttu-id="89853-210">30 secondi dopo un nuovo aggiornamento, la shell potrebbe scomparire una volta.</span><span class="sxs-lookup"><span data-stu-id="89853-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="89853-211">Eseguire il movimento **bloom** per riprendere la sessione.</span><span class="sxs-lookup"><span data-stu-id="89853-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="89853-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89853-212">Visual Studio</span></span>

- <span data-ttu-id="89853-213">Vedere [Installare gli strumenti](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Visual Studio consigliata per lo sviluppo di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-213">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="89853-214">Quando si distribuisce un'app Visual Studio in HoloLens, è possibile che venga visualizzato l'errore: L'operazione richiesta non può essere eseguita su un file con una sezione mappata **dall'utente aperta. (Eccezione da HRESULT: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="89853-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="89853-215">In questo caso, riprovare e la distribuzione avrà in genere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="89853-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="89853-216">API</span><span class="sxs-lookup"><span data-stu-id="89853-216">API</span></span>

- <span data-ttu-id="89853-217">Se l'applicazione imposta il [punto](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) di messa a fuoco dietro l'utente o il normale su camera.forward, gli ologrammi non verranno visualizzati Acquisizione realtà mista foto o video.</span><span class="sxs-lookup"><span data-stu-id="89853-217">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="89853-218">Fino a quando questo bug non viene [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) risolto in Windows, se le applicazioni impostano attivamente il punto di messa a fuoco, devono assicurarsi che la normale del piano sia impostata in avanti rispetto alla fotocamera (ad esempio, normal = -camera.forward).</span><span class="sxs-lookup"><span data-stu-id="89853-218">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="89853-219">Controller wireless Xbox</span><span class="sxs-lookup"><span data-stu-id="89853-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="89853-220">Il controller wireless Xbox S deve essere aggiornato prima di poter essere usato con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="89853-221">Assicurarsi di essere [aggiornati prima](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) di tentare di associare il controller a un holoLens.</span><span class="sxs-lookup"><span data-stu-id="89853-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="89853-222">Se si riavvia HoloLens mentre il controller wireless Xbox è connesso, il controller non si riconnette automaticamente a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="89853-223">La luce del pulsante Guida lampeggia lentamente fino a quando il controller non si spegni dopo 3 minuti.</span><span class="sxs-lookup"><span data-stu-id="89853-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="89853-224">Per riconnettere immediatamente il controller, spegnere il controller tenendo premuto il pulsante Guida fino a quando la luce non si spegne.</span><span class="sxs-lookup"><span data-stu-id="89853-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="89853-225">Quando si riasscierà il controller, si riconnetterà a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="89853-226">Se HoloLens entra in standby mentre il controller wireless Xbox è connesso, qualsiasi input nel controller riattiva HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89853-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="89853-227">È possibile evitare questo problema spegnendo il controller al termine dell'uso.</span><span class="sxs-lookup"><span data-stu-id="89853-227">You can prevent this by powering off your controller when you are done using it.</span></span>

