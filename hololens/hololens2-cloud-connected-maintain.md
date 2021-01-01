---
title: Guida alla distribuzione-cloud connected HoloLens 2 distribuzione in scala con assistenza remota-Mantieni
description: Suggerimenti per la gestione dei dispositivi HoloLens tramite una rete connessa al cloud
keywords: HoloLens, gestione, cloud connected, Remote Assist, AAD, Azure AD, MDM, gestione di dispositivi mobili
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252697"
---
# <span data-ttu-id="a52f5-104">Manutenzione-guida connessa al cloud</span><span class="sxs-lookup"><span data-stu-id="a52f5-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="a52f5-105">Aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="a52f5-105">Updates</span></span>

<span data-ttu-id="a52f5-106">Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a52f5-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="a52f5-107">Informazioni su come [gestire gli aggiornamenti di HoloLens](https://docs.microsoft.com/hololens/hololens-updates) , inclusi i giorni pianificati, l'ora pianificata e l'impostazione di ore attive nel dispositivo in modo che venga aggiornato al di fuori delle ore lavorative.</span><span class="sxs-lookup"><span data-stu-id="a52f5-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="a52f5-108">L'assistenza remota è un'app In-Box e può essere aggiornata tramite l'app Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="a52f5-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="a52f5-109">Per tutte le app scaricate tramite Microsoft Store, è possibile [aggiornarle manualmente tramite l'app Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) .</span><span class="sxs-lookup"><span data-stu-id="a52f5-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="a52f5-110">Piano di supporto</span><span class="sxs-lookup"><span data-stu-id="a52f5-110">Support Plan</span></span>

<span data-ttu-id="a52f5-111">Un piano di supporto è un'ottima cosa da avere in posizione.</span><span class="sxs-lookup"><span data-stu-id="a52f5-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="a52f5-112">È utile avere un utente o un gruppo addestrato alla risoluzione dei problemi del processo di registrazione sui dispositivi HoloLens e anche l'uso generale del dispositivo HoloLens all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a52f5-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="a52f5-113">Per consentire agli utenti di avere la risoluzione più rapida dei loro problemi, suggeriamo che il processo di escalation venga gestito in modo simile a questo ordine:</span><span class="sxs-lookup"><span data-stu-id="a52f5-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="a52f5-114">Supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="a52f5-114">Your Support desk.</span></span>
2. <span data-ttu-id="a52f5-115">Il team di esperti di HoloLens</span><span class="sxs-lookup"><span data-stu-id="a52f5-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="a52f5-116">[Documenti](https://docs.microsoft.com/hololens/)  /  di HoloLens [Risoluzione dei problemi di HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="a52f5-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="a52f5-117">Supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="a52f5-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="a52f5-118">Piano di sviluppo</span><span class="sxs-lookup"><span data-stu-id="a52f5-118">Development Plan</span></span>

<span data-ttu-id="a52f5-119">Con il dispositivo registrato correttamente, ora sei pronto per distribuire le app line of business (app LOB) ai tuoi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a52f5-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="a52f5-120">Queste sono app personalizzate create per le esigenze dell'organizzazione&#39;s.</span><span class="sxs-lookup"><span data-stu-id="a52f5-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="a52f5-121">Se hai già un'app line of business, puoi&#39;pronta a [distribuire la tua app tramite MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span><span class="sxs-lookup"><span data-stu-id="a52f5-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="a52f5-122">Se si&#39;d preferisce un metodo diverso, rivedere la [Panoramica della distribuzione dell'applicazione per HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) per ottenere altri metodi di distribuzione dell'app LOB nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a52f5-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="a52f5-123">Se si&#39;ancora per creare una propria app line-of-business o ancora in fase di creazione, rivedere i documenti di sviluppo di realtà mista per [iniziare a progettare e prototipare](https://docs.microsoft.com/windows/mixed-reality/design/design) o imparare i concetti fondamentali per iniziare a [sviluppare una realtà mista.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="a52f5-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="a52f5-124">Gestione dispositivi</span><span class="sxs-lookup"><span data-stu-id="a52f5-124">Device Management</span></span> 

<span data-ttu-id="a52f5-125">Mentre questa guida ha parlato della configurazione di gestione di dispositivi mobili (MDM), non è stato usato per applicare le restrizioni dei dispositivi o i criteri sono stati applicati alle periferiche.</span><span class="sxs-lookup"><span data-stu-id="a52f5-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="a52f5-126">La gestione dei dispositivi può essere usata sia per consentire l'accesso premendo i certificati o limitare l'accesso con una varietà di restrizioni per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a52f5-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="a52f5-127">In molti casi i dispositivi possono avere restrizioni di connettività come Bluetooth, VPN, USB o disattivazione dell'accesso alla videocamera o al microfono.</span><span class="sxs-lookup"><span data-stu-id="a52f5-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="a52f5-128">Se uno di questi interessi ti interessa, ti invitiamo a leggere la [pagina delle restrizioni dei dispositivi comuni](hololens-common-device-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="a52f5-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="a52f5-129">Ci sono altre restrizioni di dispositivi più complesse che puoi usare.</span><span class="sxs-lookup"><span data-stu-id="a52f5-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="a52f5-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a52f5-130">Such as:</span></span>

- <span data-ttu-id="a52f5-131">Limitare le pagine che possono essere visualizzate nell'app impostazioni usando [SettingsPageVisibility](settings-uri-list.md), consentendo agli utenti di accedere solo alle impostazioni necessarie per modificare la connessione Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a52f5-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="a52f5-132">Usa la [modalità Kiosk](hololens-kiosk.md) per limitare l'interfaccia utente presentata agli utenti in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a52f5-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="a52f5-133">Puoi impostare i chioschi per mostrare una singola app o più app con una pagina iniziale personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a52f5-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="a52f5-134">I chioschi possono anche presentare esperienze diverse a utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="a52f5-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="a52f5-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) per consentire l'avvio totale di app o processi specifici.</span><span class="sxs-lookup"><span data-stu-id="a52f5-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="a52f5-136">Per informazioni sui metodi più diversi per la gestione di dispositivi o le restrizioni dei dispositivi, eseguire il passaggio successivo e leggere la panoramica sulla gestione di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a52f5-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="a52f5-137">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a52f5-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a52f5-138">Leggere i DSN e la panoramica sulla gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="a52f5-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)