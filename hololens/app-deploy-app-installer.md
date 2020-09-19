---
title: Come caricare e installare le app tramite il programma di installazione di HoloLens 2 app
description: Caricare le app e installarle tramite interfaccia utente
keywords: gestione app, app, hololens, app Installer
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027474"
---
# <span data-ttu-id="32d82-104">Installare app in HoloLens 2 tramite il programma di installazione di app</span><span class="sxs-lookup"><span data-stu-id="32d82-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="32d82-105">Ora gli utenti possono installare le app tramite bundle appx, senza la necessità di abilitare la modalità sviluppatore o usare Device Portal.</span><span class="sxs-lookup"><span data-stu-id="32d82-105">Users can now install Apps via Appx Bundles now without the need to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="32d82-106">Questa esperienza è semplice per l'installazione di app su dispositivi locali o per la condivisione di un'app con un altro utente che non ha familiarità con altri metodi di installazione dell'app in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="32d82-106">This experience is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="32d82-107">Questa caratteristica è attualmente solo avalible in Windows Insider Build 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="32d82-107">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="32d82-108">[Altre informazioni su come iscriversi alle build di Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="32d82-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="32d82-109">La configurazione della soluzione della tua app deve essere **Master** o **Release** perché il programma di installazione dell'app userà le dipendenze dallo Store.</span><span class="sxs-lookup"><span data-stu-id="32d82-109">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="32d82-110">Vedere altre informazioni sulla [creazione di pacchetti di app](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="32d82-110">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

1.  <span data-ttu-id="32d82-111">Verificare che il dispositivo HoloLens 2 sia acceso e che sia stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="32d82-111">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="32d82-112">Nel PC passare all'app personalizzata e copiare YourApp. appxbundle in yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="32d82-112">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="32d82-113">Una volta completata la copia del file, è possibile scollegare il dispositivo e completare l'installazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="32d82-113">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="32d82-114">Dal dispositivo HoloLens 2 aprire il **menu Start**, selezionare **tutte le app** e avviare l'app **Esplora file** .</span><span class="sxs-lookup"><span data-stu-id="32d82-114">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="32d82-115">Passare alla cartella Downloads.</span><span class="sxs-lookup"><span data-stu-id="32d82-115">Navigate to the Downloads folder.</span></span> <span data-ttu-id="32d82-116">Potrebbe essere necessario nel pannello sinistro dell'app selezionare prima **questo dispositivo** , quindi passare a download.</span><span class="sxs-lookup"><span data-stu-id="32d82-116">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="32d82-117">Selezionare il file YourApp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="32d82-117">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="32d82-118">Verrà avviato il programma di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="32d82-118">The App Installer will launch.</span></span> <span data-ttu-id="32d82-119">Selezionare il pulsante **Installa** per installare la tua app.</span><span class="sxs-lookup"><span data-stu-id="32d82-119">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="32d82-120">L'app installata verrà avviata automaticamente dopo il completamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="32d82-120">The installed app will automatically launch upon the completion of installing.</span></span> 

![Installazione di esempi di MRTK tramite il programma di installazione dell'app](images/hololens-app-installer-picture.jpg)

<span data-ttu-id="32d82-122">Se l'app non è stata installata, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="32d82-122">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="32d82-123">La tua app è una build master o release.</span><span class="sxs-lookup"><span data-stu-id="32d82-123">Your app is either a Master or Release build.</span></span>
-   <span data-ttu-id="32d82-124">Si è [connessi a Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="32d82-124">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="32d82-125">Gli [endpoint per Microsoft Store](hololens-offline.md) sono configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="32d82-125">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  
