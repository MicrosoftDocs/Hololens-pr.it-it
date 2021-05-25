---
title: Panoramica dei servizi connessi HoloLens 2 cloud con Remote Assist
description: Informazioni su come registrare HoloLens 2 dispositivi su una rete connessa al cloud usando Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397652"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="08cf1-104">Guida alla distribuzione - Cloud connected HoloLens 2 con Remote Assist - Panoramica</span><span class="sxs-lookup"><span data-stu-id="08cf1-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="08cf1-105">Questa guida consente ai professionisti IT di pianificare e distribuire Microsoft HoloLens 2 dispositivi all'organizzazione con l'obiettivo complessivo di avere questi dispositivi connessi al cloud all'organizzazione con Dynamics 365 Remote Assist pronti per l'uso.</span><span class="sxs-lookup"><span data-stu-id="08cf1-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="08cf1-106">Tenere presente che questo modello fungerà da modello per le distribuzioni di modelli di verifica per l'organizzazione in un'ampia gamma di HoloLens 2 casi d'uso.</span><span class="sxs-lookup"><span data-stu-id="08cf1-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="08cf1-107">Durante la guida verrà illustrato come registrare i dispositivi nella gestione dei dispositivi, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente Remote Assist durante la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08cf1-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="08cf1-108">A tale scopo, verranno trattate le importanti infrastrutture necessarie per la configurazione e l'esecuzione, ottenendo una distribuzione su larga scala con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="08cf1-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="08cf1-109">[![Scenario connesso al cloud ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="08cf1-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="08cf1-110">In questa guida</span><span class="sxs-lookup"><span data-stu-id="08cf1-110">In this Guide</span></span>

<span data-ttu-id="08cf1-111">Questa guida ha l'obiettivo specifico di configurare Remote Assist all'interno dell'organizzazione nei dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="08cf1-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="08cf1-112">Verranno trattati i necessari per raggiungere questo obiettivo.</span><span class="sxs-lookup"><span data-stu-id="08cf1-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="08cf1-113">Per mantenere l'attenzione su questo obiettivo, alcune configurazioni e preparazione verranno preseescente per ottimizzare questa distribuzione o ridurre gli elementi necessari per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="08cf1-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="08cf1-114">Si verrà informati di queste scelte e sarà possibile personalizzare la distribuzione in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="08cf1-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="08cf1-115">Si tratta di una configurazione simile a [Scenario A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Deploy to cloud connect devices , che è un'opzione valida per molte distribuzioni del modello di verifica, tra cui:</span><span class="sxs-lookup"><span data-stu-id="08cf1-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="08cf1-116">Wi-Fi reti sono in genere completamente aperte ai servizi Internet e cloud</span><span class="sxs-lookup"><span data-stu-id="08cf1-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="08cf1-117">Azure AD aggiunta alla registrazione automatica MDM - GESTIONE MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="08cf1-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="08cf1-118">Gli utenti a cui si accede con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="08cf1-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="08cf1-119">Supporto di uno o più utenti per dispositivo</span><span class="sxs-lookup"><span data-stu-id="08cf1-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="08cf1-120">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a App singola in modalità tutto schermo</span><span class="sxs-lookup"><span data-stu-id="08cf1-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="08cf1-121">In questa guida non verranno applicate altre restrizioni o configurazioni per i dispositivi, tuttavia si consiglia di esplorare tali opzioni al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="08cf1-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="08cf1-122">Informazioni sulle Remote Assist</span><span class="sxs-lookup"><span data-stu-id="08cf1-122">Learn about Remote Assist</span></span>

<span data-ttu-id="08cf1-123">Remote Assist la manutenzione e la riparazione collaborative, l'ispezione remota, nonché la condivisione delle conoscenze e la formazione.</span><span class="sxs-lookup"><span data-stu-id="08cf1-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="08cf1-124">Connettendo persone con ruoli e posizioni diversi, un tecnico Remote Assist può connettersi con un collaboratore remoto in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08cf1-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="08cf1-125">Possono combinare video, screenshot e annotazioni per risolvere i problemi in tempo reale anche quando&#39;nella stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="08cf1-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="08cf1-126">I collaboratori remoti possono inserire immagini di riferimento, schemi e altre informazioni utili che il tecnico&#39;ha nello spazio fisico in modo che possano fare riferimento allo schema mentre lavorano a testa alta e senza mani su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="08cf1-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="08cf1-127">Contenuto della guida:</span><span class="sxs-lookup"><span data-stu-id="08cf1-127">In this guide you will:</span></span>

<span data-ttu-id="08cf1-128">Preparazione:</span><span class="sxs-lookup"><span data-stu-id="08cf1-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="08cf1-129">Informazioni sui dati di base dell'infrastruttura HoloLens 2 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="08cf1-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="08cf1-130">Altre informazioni su Azure AD e su come configurarne una se&#39;non è già stata impostata.</span><span class="sxs-lookup"><span data-stu-id="08cf1-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="08cf1-131">Informazioni sulla gestione delle identità e su come configurare al meglio Azure AD account.</span><span class="sxs-lookup"><span data-stu-id="08cf1-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="08cf1-132">Altre informazioni su MDM e configurazione con Intune se non&#39;ne è già disponibile uno.</span><span class="sxs-lookup"><span data-stu-id="08cf1-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="08cf1-133">Informazioni sui requisiti di rete di Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="08cf1-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="08cf1-134">Facoltativamente: VPN per connettersi alle risorse aziendali</span><span class="sxs-lookup"><span data-stu-id="08cf1-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="08cf1-135">Configurare:</span><span class="sxs-lookup"><span data-stu-id="08cf1-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="08cf1-136">Come creare utenti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="08cf1-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="08cf1-137">Come configurare la registrazione automatica all'interno Azure AD.</span><span class="sxs-lookup"><span data-stu-id="08cf1-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="08cf1-138">Come assegnare le licenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="08cf1-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="08cf1-139">Distribuzione:</span><span class="sxs-lookup"><span data-stu-id="08cf1-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="08cf1-140">Configurare la registrazione HoloLens 2 convalidare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="08cf1-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="08cf1-141">Verificare che sia possibile effettuare una Remote Assist chiamata.</span><span class="sxs-lookup"><span data-stu-id="08cf1-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="08cf1-142">Gestione:</span><span class="sxs-lookup"><span data-stu-id="08cf1-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="08cf1-143">Come aggiornare i Remote Assist usando l'app Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="08cf1-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="08cf1-144">Creazione di un piano di supporto.</span><span class="sxs-lookup"><span data-stu-id="08cf1-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="08cf1-145">Piano di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="08cf1-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="08cf1-146">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="08cf1-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="08cf1-147">Distribuzione connessa al cloud - Preparare</span><span class="sxs-lookup"><span data-stu-id="08cf1-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

