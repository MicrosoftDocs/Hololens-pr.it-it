---
title: Guida alla distribuzione - Distribuzione di HoloLens 2 cloud su larga scala con Remote Assist - Manutenzione
description: Rimanere aggiornati con i suggerimenti per la gestione e il supporto dei dispositivi HoloLens tramite una rete connessa al cloud.
keywords: HoloLens, gestione, connessa al cloud, Remote Assist, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309783"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="a468f-104">Manutenzione - Guida connessa al cloud</span><span class="sxs-lookup"><span data-stu-id="a468f-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="a468f-105">Aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="a468f-105">Updates</span></span>

<span data-ttu-id="a468f-106">Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a468f-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="a468f-107">Informazioni su come [gestire gli aggiornamenti di HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) inclusi i giorni pianificati, l'ora pianificata e l'impostazione degli orari di attività nel dispositivo in modo che si aggiorneranno al di fuori dell'orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a468f-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="a468f-108">Remote Assist è un'app In-Box e può essere aggiornato tramite l Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="a468f-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="a468f-109">Per tutte le app scaricate tramite il Microsoft Store possono essere aggiornate manualmente [tramite](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) l Microsoft Store app stessa.</span><span class="sxs-lookup"><span data-stu-id="a468f-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="a468f-110">Piano di supporto</span><span class="sxs-lookup"><span data-stu-id="a468f-110">Support Plan</span></span>

<span data-ttu-id="a468f-111">Un piano di supporto è una cosa eccellente da avere in atto.</span><span class="sxs-lookup"><span data-stu-id="a468f-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="a468f-112">È utile avere un utente o un gruppo per la risoluzione dei problemi relativi al processo di registrazione nei dispositivi HoloLens e anche l'uso generale del dispositivo HoloLens all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a468f-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="a468f-113">Per consentire agli utenti di ottenere la risoluzione più rapida dei problemi, è consigliabile che il processo di escalation sia gestito in modo simile a questo ordine:</span><span class="sxs-lookup"><span data-stu-id="a468f-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="a468f-114">Il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="a468f-114">Your Support desk.</span></span>
2. <span data-ttu-id="a468f-115">Il team di esperti di HoloLens</span><span class="sxs-lookup"><span data-stu-id="a468f-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="a468f-116">[HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Documentazione sulla risoluzione dei problemi di HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="a468f-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="a468f-117">Contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="a468f-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="a468f-118">Piano di sviluppo</span><span class="sxs-lookup"><span data-stu-id="a468f-118">Development Plan</span></span>

<span data-ttu-id="a468f-119">Dopo aver registrato correttamente il dispositivo, è ora possibile distribuire app line-of-business (app line-of-business) nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a468f-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="a468f-120">Si tratta di app personalizzate create per l'organizzazione&#39;esigenze.</span><span class="sxs-lookup"><span data-stu-id="a468f-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="a468f-121">Se si ha già un'app line-of-business,&#39;è possibile distribuire [l'app tramite MDM.](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="a468f-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="a468f-122">Se si&#39;un metodo diverso, vedere la panoramica della distribuzione dell'applicazione [per](https://docs.microsoft.com/hololens/app-deploy-overview) HoloLens 2 per altre informazioni sui metodi di distribuzione dell'app LOB nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a468f-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="a468f-123">Se non si è ancora&#39;creare un'app LOB o si è ancora in fase [](https://docs.microsoft.com/windows/mixed-reality/design/design) di creazione, vedere la documentazione sullo sviluppo di realtà mista per iniziare a progettare e creare prototipi o apprendere i concetti di base per iniziare a usare lo sviluppo di realtà [mista.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="a468f-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="a468f-124">Gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="a468f-124">Device Management</span></span> 

<span data-ttu-id="a468f-125">Anche se questa guida ha parlato della configurazione della gestione dei dispositivi mobili (MDM), non è stata impiegata per applicare restrizioni o criteri ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a468f-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="a468f-126">La gestione dei dispositivi può essere usata sia per consentire l'accesso tramite il push dei certificati che per limitare l'accesso con un'ampia gamma di restrizioni dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a468f-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="a468f-127">In molti casi i dispositivi possono avere restrizioni di connettività, ad esempio Bluetooth, VPN, USB o anche disattivare l'accesso alla fotocamera o al microfono.</span><span class="sxs-lookup"><span data-stu-id="a468f-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="a468f-128">Se uno di questi interessi è di tuo interesse, ti invitiamo a leggere la pagina delle restrizioni [comuni per i dispositivi.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="a468f-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="a468f-129">Esistono altre restrizioni più complesse per i dispositivi che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="a468f-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="a468f-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a468f-130">Such as:</span></span>

- <span data-ttu-id="a468f-131">Limitazione delle pagine che possono essere visualizzate nell'app Impostazioni usando [SettingsPageVisibility](settings-uri-list.md), consentendo agli utenti di accedere solo alle impostazioni necessarie per modificare, ad esempio la modifica della Wi-Fi connessione.</span><span class="sxs-lookup"><span data-stu-id="a468f-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="a468f-132">Usare [la modalità tutto schermo](hololens-kiosk.md) per limitare l'interfaccia utente presentata agli utenti in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a468f-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="a468f-133">È possibile impostare Chioschi in modo che mostri una singola app o più app con una pagina iniziale personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a468f-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="a468f-134">I chioschi possono anche presentare esperienze diverse a utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="a468f-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="a468f-135">[Controllo delle applicazioni di Windows (WDAC)](windows-defender-application-control-wdac.md) per evitare l'avvio completo di app o processi specifici.</span><span class="sxs-lookup"><span data-stu-id="a468f-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="a468f-136">Per altre informazioni sui diversi metodi di gestione dei dispositivi o sulle restrizioni dei dispositivi, eseguire il passaggio successivo e leggere La panoramica sulla gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a468f-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="a468f-137">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a468f-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a468f-138">Leggere la panoramica dei CSP e della gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="a468f-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)