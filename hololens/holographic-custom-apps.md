---
title: Gestire app personalizzate per HoloLens (prima generazione)
description: Scopri come installare, disinstallare e caricare tramite side load app olografiche personalizzate nei dispositivi HoloLens tramite Device Portal e Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, sideload, sideload, store, uwp, app, install
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
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296989"
---
# <span data-ttu-id="c9f9c-104">Gestire app personalizzate per HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="c9f9c-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="c9f9c-105">HoloLens supporta molte attuali applicazioni disponibili su Microsoft Store, nonché nuove app create specificamente per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="c9f9c-106">Questo articolo si concentra sulle applicazioni olografiche personalizzate.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="c9f9c-107">Per altre informazioni sulle app dello Store, vedi [Gestire le app con lo Store.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="c9f9c-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9f9c-108">Le informazioni seguenti sono state create per HoloLens (prima generazione), chiamata anche HoloLens Developer Edition al momento.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="c9f9c-109">Di conseguenza, il sideload delle app tramite portale di dispositivi e l'installazione di app tramite Visual Studio erano all'ora comune.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="c9f9c-110">Per le distribuzioni aziendali non è consigliabile abilitare la modalità sviluppatore, che entrambi i metodi usano.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="c9f9c-111">Se sei interessato a un metodo di distribuzione delle app sicuro, leggi la nostra [panoramica sulla gestione delle app.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c9f9c-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="c9f9c-112">Se stai cercando uno dei due metodi di installazione delle app per i dispositivi HoloLens 2, fai riferimento a:</span><span class="sxs-lookup"><span data-stu-id="c9f9c-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="c9f9c-113">Device Portal: installazione di un'app</span><span class="sxs-lookup"><span data-stu-id="c9f9c-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="c9f9c-114">Uso di Visual Studio per distribuire ed eseguire il debug delle app</span><span class="sxs-lookup"><span data-stu-id="c9f9c-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="c9f9c-115">Installare app personalizzate</span><span class="sxs-lookup"><span data-stu-id="c9f9c-115">Install custom apps</span></span>

<span data-ttu-id="c9f9c-116">Puoi installare le tue applicazioni in HoloLens usando Device Portal o distribuendo le app da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="c9f9c-117">Installazione di un pacchetto dell'applicazione con Device Portal</span><span class="sxs-lookup"><span data-stu-id="c9f9c-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="c9f9c-118">Stabilire una connessione da [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) a HoloLens di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="c9f9c-119">Nel riquadro di spostamento sinistro passare alla **pagina** App.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="c9f9c-120">In **Pacchetto dell'app** passare al file con estensione appx associato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="c9f9c-121">Assicurati di fare riferimento a qualsiasi file di dipendenza e certificato associato.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="c9f9c-122">Selezionare **Vai.**</span><span class="sxs-lookup"><span data-stu-id="c9f9c-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Installare il modulo dell'app in Windows Device Portal in Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="c9f9c-124">Distribuzione da Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="c9f9c-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="c9f9c-125">Apri la soluzione Visual Studio della tua app (file con estensione sln).</span><span class="sxs-lookup"><span data-stu-id="c9f9c-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="c9f9c-126">Aprire le proprietà del **progetto.**</span><span class="sxs-lookup"><span data-stu-id="c9f9c-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="c9f9c-127">Selezionare la configurazione di compilazione seguente: **Master/x86/Computer remoto.**</span><span class="sxs-lookup"><span data-stu-id="c9f9c-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="c9f9c-128">Quando si seleziona **Computer remoto:**</span><span class="sxs-lookup"><span data-stu-id="c9f9c-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="c9f9c-129">Assicurati che l'indirizzo punti all'Wi-Fi IP del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="c9f9c-130">Impostare **l'autenticazione su Universale (protocollo non crittografato).**</span><span class="sxs-lookup"><span data-stu-id="c9f9c-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="c9f9c-131">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-131">Build your solution.</span></span>

1. <span data-ttu-id="c9f9c-132">Per distribuire l'app dal PC di sviluppo a HoloLens, seleziona **Computer remoto.**</span><span class="sxs-lookup"><span data-stu-id="c9f9c-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="c9f9c-133">Se hai già una build esistente in HoloLens, seleziona **Sì** per installare questa versione più recente.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Distribuzione di computer remoti per le app in Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="c9f9c-135">L'applicazione verrà installata e avviata automaticamente in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9f9c-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="c9f9c-136">Dopo aver installato un'app, la troverai **nell'elenco Tutte** le app (**Avvia**tutte  >  **le app**).</span><span class="sxs-lookup"><span data-stu-id="c9f9c-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
