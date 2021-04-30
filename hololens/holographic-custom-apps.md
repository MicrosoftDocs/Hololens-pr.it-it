---
title: Gestire app personalizzate per HoloLens (prima generazione)
description: Informazioni su come installare, disinstallare e eseguire il side load di app olografiche personalizzate nei dispositivi HoloLens usando il Portale di dispositivi e Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, sideload, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309307"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="de480-104">Gestire app personalizzate per HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="de480-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="de480-105">HoloLens supporta molte applicazioni esistenti dal Microsoft Store, nonché nuove app create in modo specifico per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="de480-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="de480-106">Questo articolo è in particolare sulle applicazioni olografiche personalizzate.</span><span class="sxs-lookup"><span data-stu-id="de480-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="de480-107">Per altre informazioni sulle app dello Store, vedere [Gestire le app con lo Store.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="de480-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de480-108">Le informazioni seguenti sono state create per HoloLens (prima generazione), chiamata anche HoloLens Developer Edition al momento.</span><span class="sxs-lookup"><span data-stu-id="de480-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="de480-109">Di conseguenza, il sideload delle app tramite il portale di dispositivi e l'installazione di app tramite Visual Studio erano comuni.</span><span class="sxs-lookup"><span data-stu-id="de480-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="de480-110">Per le distribuzioni aziendali non è consigliabile abilitare la modalità sviluppatore, che viene utilizzata da entrambi questi metodi.</span><span class="sxs-lookup"><span data-stu-id="de480-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="de480-111">Se si è interessati a un metodo di distribuzione dell'app sicuro, vedere Gestione [delle app: Panoramica.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="de480-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="de480-112">Se si sta cercando uno dei due metodi di installazione delle app per HoloLens 2, fare riferimento a:</span><span class="sxs-lookup"><span data-stu-id="de480-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="de480-113">Portale di dispositivi: Installazione di un'app</span><span class="sxs-lookup"><span data-stu-id="de480-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="de480-114">Uso di Visual Studio per distribuire ed eseguire il debug di app</span><span class="sxs-lookup"><span data-stu-id="de480-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="de480-115">Installare app personalizzate</span><span class="sxs-lookup"><span data-stu-id="de480-115">Install custom apps</span></span>

<span data-ttu-id="de480-116">Puoi installare le tue applicazioni in HoloLens usando il Portale di dispositivi o distribuendo le app da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="de480-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="de480-117">Installazione di un pacchetto dell'applicazione con il Portale di dispositivi</span><span class="sxs-lookup"><span data-stu-id="de480-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="de480-118">Stabilire una connessione dal [Portale di dispositivi](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) al dispositivo HoloLens di destinazione.</span><span class="sxs-lookup"><span data-stu-id="de480-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="de480-119">Nel riquadro di spostamento a sinistra passare alla **pagina** App.</span><span class="sxs-lookup"><span data-stu-id="de480-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="de480-120">In **Pacchetto dell'app** passare al file con estensione appx associato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="de480-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="de480-121">Assicurarsi di fare riferimento a eventuali dipendenze e file di certificato associati.</span><span class="sxs-lookup"><span data-stu-id="de480-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="de480-122">Selezionare **Vai**.</span><span class="sxs-lookup"><span data-stu-id="de480-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de480-123">![Installare il modulo dell'app Portale di dispositivi di Windows in Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="de480-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="de480-124">Distribuzione da Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="de480-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="de480-125">Aprire la soluzione di Visual Studio dell'app (file con estensione sln).</span><span class="sxs-lookup"><span data-stu-id="de480-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="de480-126">Aprire proprietà del **progetto**.</span><span class="sxs-lookup"><span data-stu-id="de480-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="de480-127">Selezionare la configurazione di compilazione seguente: **Master/x86/Computer remoto**.</span><span class="sxs-lookup"><span data-stu-id="de480-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="de480-128">Quando si seleziona **Computer remoto**:</span><span class="sxs-lookup"><span data-stu-id="de480-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="de480-129">Assicurarsi che l'indirizzo punti Wi-Fi'indirizzo IP di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="de480-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="de480-130">Impostare **l'autenticazione su Universal (Unencrypted Protocol)**.</span><span class="sxs-lookup"><span data-stu-id="de480-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="de480-131">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="de480-131">Build your solution.</span></span>

1. <span data-ttu-id="de480-132">Per distribuire l'app dal PC di sviluppo in HoloLens, selezionare **Computer remoto**.</span><span class="sxs-lookup"><span data-stu-id="de480-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="de480-133">Se si ha già una build esistente in HoloLens, selezionare **Sì** per installare questa versione più recente.</span><span class="sxs-lookup"><span data-stu-id="de480-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Distribuzione di computer remoti per le app da Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="de480-135">L'applicazione verrà installata e avviata automaticamente in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="de480-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="de480-136">Dopo aver installato un'app, è possibile trovarla nell'elenco **Tutte** le app (**Avvia**  >  **tutte le app**).</span><span class="sxs-lookup"><span data-stu-id="de480-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
