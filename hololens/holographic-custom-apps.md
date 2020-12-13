---
title: Gestire le app personalizzate per HoloLens
description: Caricamento laterale di app personalizzate in HoloLens. Leggi altre informazioni su come installare e disinstallare le app olografiche.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, trasferire localmente, carico laterale, carico laterale, Store, UWP, app, install
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218633"
---
# <span data-ttu-id="707a8-105">Gestire le app personalizzate per HoloLens</span><span class="sxs-lookup"><span data-stu-id="707a8-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="707a8-106">HoloLens supporta molte attuali applicazioni disponibili su Microsoft Store, nonché nuove app create specificamente per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="707a8-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="707a8-107">Questo articolo è dedicato alle applicazioni olografiche personalizzate.</span><span class="sxs-lookup"><span data-stu-id="707a8-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="707a8-108">Per altre informazioni sulle app dello Store, Vedi [gestire le app con lo Store](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="707a8-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="707a8-109">Le informazioni seguenti sono state create per HoloLens (1a generazione), detta anche HoloLens Developer Edition in quel momento.</span><span class="sxs-lookup"><span data-stu-id="707a8-109">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="707a8-110">In questo modo, le app sideload tramite Device Portal e l'installazione di app tramite Visual Studio erano comuni.</span><span class="sxs-lookup"><span data-stu-id="707a8-110">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="707a8-111">Per le distribuzioni aziendali, non è consigliabile abilitare la modalità sviluppatore, che usano entrambi i metodi.</span><span class="sxs-lookup"><span data-stu-id="707a8-111">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="707a8-112">Se si è interessati a un metodo di distribuzione delle app sicure, vedere la [sezione gestione delle app: Panoramica](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="707a8-112">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="707a8-113">Se stai cercando un metodo per gli sviluppatori per l'installazione di app per dispositivi HoloLens 2, consulta:</span><span class="sxs-lookup"><span data-stu-id="707a8-113">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="707a8-114">Device Portal: installare un'app</span><span class="sxs-lookup"><span data-stu-id="707a8-114">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="707a8-115">Uso di Visual Studio per la distribuzione e il debug delle app</span><span class="sxs-lookup"><span data-stu-id="707a8-115">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="707a8-116">Installare app personalizzate</span><span class="sxs-lookup"><span data-stu-id="707a8-116">Install custom apps</span></span>

<span data-ttu-id="707a8-117">Puoi installare le tue applicazioni in HoloLens usando il portale dispositivi o distribuendo le app da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="707a8-117">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="707a8-118">Installazione di un pacchetto di applicazione con Device Portal</span><span class="sxs-lookup"><span data-stu-id="707a8-118">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="707a8-119">Stabilire una connessione da [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) alla HoloLens di destinazione.</span><span class="sxs-lookup"><span data-stu-id="707a8-119">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="707a8-120">Nella barra di spostamento sinistra passare alla pagina **app** .</span><span class="sxs-lookup"><span data-stu-id="707a8-120">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="707a8-121">In **pacchetto dell'app** individuare il file con estensione appx associato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="707a8-121">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="707a8-122">Assicurarsi di fare riferimento a qualsiasi file di dipendenza e certificato associato.</span><span class="sxs-lookup"><span data-stu-id="707a8-122">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="707a8-123">Selezionare **Vai**.</span><span class="sxs-lookup"><span data-stu-id="707a8-123">Select **Go**.</span></span>
   ![Modulo di installazione dell'app in Windows Device Portal in Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="707a8-125">Distribuzione da Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="707a8-125">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="707a8-126">Aprire la soluzione Visual Studio (file con estensione sln) dell'app.</span><span class="sxs-lookup"><span data-stu-id="707a8-126">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="707a8-127">Aprire le **Proprietà**del progetto.</span><span class="sxs-lookup"><span data-stu-id="707a8-127">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="707a8-128">Selezionare la configurazione di compilazione seguente: **computer master/x86/Remote**.</span><span class="sxs-lookup"><span data-stu-id="707a8-128">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="707a8-129">Quando si seleziona **computer remoto**:</span><span class="sxs-lookup"><span data-stu-id="707a8-129">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="707a8-130">Verificare che l'indirizzo indichi l'indirizzo IP Wi-Fi del proprio HoloLens.</span><span class="sxs-lookup"><span data-stu-id="707a8-130">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="707a8-131">Impostare l'autenticazione su **universale (protocollo non crittografato)**.</span><span class="sxs-lookup"><span data-stu-id="707a8-131">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="707a8-132">Creare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="707a8-132">Build your solution.</span></span>
1. <span data-ttu-id="707a8-133">Per distribuire l'app dal PC di sviluppo alla HoloLens, selezionare **computer remoto**.</span><span class="sxs-lookup"><span data-stu-id="707a8-133">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="707a8-134">Se si dispone già di una build esistente in HoloLens, selezionare **Sì** per installare la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="707a8-134">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Distribuzione di computer remoti per le app in Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="707a8-136">L'applicazione verrà installata e avviata automaticamente in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="707a8-136">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="707a8-137">Dopo aver installato un'app, la troverai nell'elenco **tutte** le app (**Avvia**  >  **tutte le app**).</span><span class="sxs-lookup"><span data-stu-id="707a8-137">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
