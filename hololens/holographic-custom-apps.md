---
title: Gestire le app personalizzate per HoloLens
description: Caricamento laterale di app personalizzate in HoloLens. Leggi altre informazioni su come installare e disinstallare le app olografiche.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828861"
---
# <span data-ttu-id="62200-105">Gestire le app personalizzate per HoloLens</span><span class="sxs-lookup"><span data-stu-id="62200-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="62200-106">HoloLens supporta molte applicazioni esistenti provenienti da Microsoft Store, nonché nuove app create appositamente per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="62200-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="62200-107">Questo articolo è dedicato alle applicazioni olografiche personalizzate.</span><span class="sxs-lookup"><span data-stu-id="62200-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="62200-108">Per altre informazioni sulle app dello Store, Vedi [gestire le app con lo Store](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="62200-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

## <span data-ttu-id="62200-109">Installare app personalizzate</span><span class="sxs-lookup"><span data-stu-id="62200-109">Install custom apps</span></span>

<span data-ttu-id="62200-110">Puoi installare le tue applicazioni in HoloLens usando il portale dispositivi o distribuendo le app da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="62200-110">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="62200-111">Installazione di un pacchetto di applicazione con Device Portal</span><span class="sxs-lookup"><span data-stu-id="62200-111">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="62200-112">Stabilire una connessione da [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) alla HoloLens di destinazione.</span><span class="sxs-lookup"><span data-stu-id="62200-112">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="62200-113">Nella barra di spostamento sinistra passare alla pagina **app** .</span><span class="sxs-lookup"><span data-stu-id="62200-113">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="62200-114">In **pacchetto dell'app** individuare il file con estensione appx associato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62200-114">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="62200-115">Assicurarsi di fare riferimento a qualsiasi file di dipendenza e certificato associato.</span><span class="sxs-lookup"><span data-stu-id="62200-115">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="62200-116">Selezionare **Vai**.</span><span class="sxs-lookup"><span data-stu-id="62200-116">Select **Go**.</span></span>
   ![Modulo di installazione dell'app in Windows Device Portal in Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="62200-118">Distribuzione da Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="62200-118">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="62200-119">Aprire la soluzione Visual Studio (file con estensione sln) dell'app.</span><span class="sxs-lookup"><span data-stu-id="62200-119">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="62200-120">Aprire le **Proprietà**del progetto.</span><span class="sxs-lookup"><span data-stu-id="62200-120">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="62200-121">Selezionare la configurazione di compilazione seguente: **computer master/x86/Remote**.</span><span class="sxs-lookup"><span data-stu-id="62200-121">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="62200-122">Quando si seleziona **computer remoto**:</span><span class="sxs-lookup"><span data-stu-id="62200-122">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="62200-123">Verificare che l'indirizzo indichi l'indirizzo IP Wi-Fi del proprio HoloLens.</span><span class="sxs-lookup"><span data-stu-id="62200-123">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="62200-124">Impostare l'autenticazione su **universale (protocollo non crittografato)**.</span><span class="sxs-lookup"><span data-stu-id="62200-124">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="62200-125">Creare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="62200-125">Build your solution.</span></span>
1. <span data-ttu-id="62200-126">Per distribuire l'app dal PC di sviluppo alla HoloLens, selezionare **computer remoto**.</span><span class="sxs-lookup"><span data-stu-id="62200-126">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="62200-127">Se si dispone già di una build esistente in HoloLens, selezionare **Sì** per installare la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="62200-127">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Distribuzione di computer remoti per le app in Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="62200-129">L'applicazione verrà installata e avviata automaticamente in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="62200-129">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="62200-130">Dopo aver installato un'app, la troverai nell'elenco **tutte** le app (**Avvia**  >  **tutte le app**).</span><span class="sxs-lookup"><span data-stu-id="62200-130">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
