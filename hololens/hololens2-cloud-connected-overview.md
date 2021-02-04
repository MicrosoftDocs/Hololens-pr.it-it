---
title: Panoramica della connessione cloud connessa a HoloLens 2 con assistenza remota
description: Informazioni su come registrare i dispositivi HoloLens 2 in una rete connessa tramite cloud con l'assistenza remota di Dynamics 365.
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: 39424078a75feaf6a1e9b0547cb7d5de9847faf3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312636"
---
# <span data-ttu-id="22ed8-104">Guida alla distribuzione: HoloLens 2 con Remote Assist nel cloud - Panoramica</span><span class="sxs-lookup"><span data-stu-id="22ed8-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="22ed8-105">Questa guida aiuta i professionisti IT a pianificare e distribuire i dispositivi Microsoft HoloLens 2 alla propria organizzazione con l'obiettivo generale di consentire a questi dispositivi di essere connessi alla propria organizzazione con l'assistenza remota di Dynamics 365 pronta per l'uso.</span><span class="sxs-lookup"><span data-stu-id="22ed8-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="22ed8-106">Tieni presente che questo sarà un modello per le distribuzioni Proof-of-concept per la tua organizzazione in diversi casi di utilizzo di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="22ed8-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="22ed8-107">Durante la guida verrà illustrato come registrare i dispositivi nella gestione del dispositivo, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente l'assistenza remota alla configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22ed8-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="22ed8-108">A questo scopo, rivediamo i principali componenti dell'infrastruttura necessari per la configurazione e l'uso, ottenendo la distribuzione in scala con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="22ed8-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

![Banner connesso al cloud](./images/cloud-connected-hololens-large.png)

## <span data-ttu-id="22ed8-110">In questa guida</span><span class="sxs-lookup"><span data-stu-id="22ed8-110">In this Guide</span></span>

<span data-ttu-id="22ed8-111">Questa guida ha l'obiettivo specifico di configurare l'assistenza remota all'interno dell'organizzazione nei dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="22ed8-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="22ed8-112">Riguarderemo le necessità necessarie per raggiungere questo obiettivo.</span><span class="sxs-lookup"><span data-stu-id="22ed8-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="22ed8-113">Per mantenere lo stato attivo su questo obiettivo, la preparazione e la configurazione verranno preselezionate in modo da ottimizzare la distribuzione o ridurre gli elementi necessari per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="22ed8-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="22ed8-114">Sarai informato di queste opzioni e potrai personalizzare la distribuzione in base alle tue esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="22ed8-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="22ed8-115">Si tratta di una configurazione simile allo [scenario a: distribuire ai dispositivi Cloud Connect](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), che è una buona opzione per molti strumenti di prova per le distribuzioni di concetti, che includono:</span><span class="sxs-lookup"><span data-stu-id="22ed8-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="22ed8-116">Le reti di Wi-Fi sono in genere completamente aperte a Internet e ai servizi cloud</span><span class="sxs-lookup"><span data-stu-id="22ed8-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="22ed8-117">Join di Azure AD con registrazione automatica MDM--MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="22ed8-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="22ed8-118">Accesso degli utenti con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="22ed8-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="22ed8-119">Singoli o più utenti per dispositivo supportati</span><span class="sxs-lookup"><span data-stu-id="22ed8-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="22ed8-120">I vari livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi di utilizzo specifici, dal chiosco completamente aperto al singolo app</span><span class="sxs-lookup"><span data-stu-id="22ed8-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Scenario connesso al cloud](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="22ed8-122">In questa guida non verranno applicate altre limitazioni o configurazioni di dispositivo, ma ti invitiamo ad esplorare queste opzioni dopo la fine.</span><span class="sxs-lookup"><span data-stu-id="22ed8-122">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="22ed8-123">Informazioni sull'assistenza remota</span><span class="sxs-lookup"><span data-stu-id="22ed8-123">Learn about Remote Assist</span></span>

<span data-ttu-id="22ed8-124">L'assistenza remota consente la manutenzione e il ripristino collaborativo, il controllo remoto e la condivisione delle conoscenze e la formazione.</span><span class="sxs-lookup"><span data-stu-id="22ed8-124">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="22ed8-125">Collegando persone in ruoli e posizioni diverse, un tecnico che usa l'assistenza remota può connettersi a un collaboratore remoto in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="22ed8-125">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="22ed8-126">Possono combinare video, screenshot e annotazioni per risolvere i problemi in tempo reale anche quando non sono&#39;t nella stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="22ed8-126">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="22ed8-127">I collaboratori remoti possono inserire immagini di riferimento, schemi e altre informazioni utili per lo spazio fisico del tecnico&#39;, in modo che possano riferirsi allo schema mentre si lavora a heads-up e Hands-Free su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="22ed8-127">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="22ed8-128">In questa guida verrà:</span><span class="sxs-lookup"><span data-stu-id="22ed8-128">In this guide you will:</span></span>

<span data-ttu-id="22ed8-129">Preparare</span><span class="sxs-lookup"><span data-stu-id="22ed8-129">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="22ed8-130">Informazioni sull'infrastruttura Essentials per i dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="22ed8-130">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="22ed8-131">Leggi altre informazioni su Azure AD e impostane una se non ne hai&#39;.</span><span class="sxs-lookup"><span data-stu-id="22ed8-131">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="22ed8-132">Informazioni sulla gestione delle identità e sulla configurazione ottimale degli account di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="22ed8-132">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="22ed8-133">Leggi altre informazioni su MDM e configura con Intune se Don&#39;t ne hai già uno pronto.</span><span class="sxs-lookup"><span data-stu-id="22ed8-133">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="22ed8-134">Informazioni sui requisiti di rete di Remote assist.</span><span class="sxs-lookup"><span data-stu-id="22ed8-134">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="22ed8-135">Facoltativamente: VPN per connettersi alle risorse dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="22ed8-135">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="22ed8-136">Configurare</span><span class="sxs-lookup"><span data-stu-id="22ed8-136">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="22ed8-137">Come creare utenti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="22ed8-137">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="22ed8-138">Come configurare la registrazione automatica in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="22ed8-138">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="22ed8-139">Come assegnare le licenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="22ed8-139">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="22ed8-140">Distribuire</span><span class="sxs-lookup"><span data-stu-id="22ed8-140">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="22ed8-141">Configurare la registrazione di HoloLens 2 e Validate.</span><span class="sxs-lookup"><span data-stu-id="22ed8-141">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="22ed8-142">Verificare che sia possibile effettuare una chiamata assistita remota.</span><span class="sxs-lookup"><span data-stu-id="22ed8-142">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="22ed8-143">Mantenere</span><span class="sxs-lookup"><span data-stu-id="22ed8-143">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="22ed8-144">Come aggiornare Remote Assist con l'app Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="22ed8-144">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="22ed8-145">Creazione di un piano di supporto.</span><span class="sxs-lookup"><span data-stu-id="22ed8-145">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="22ed8-146">Piano di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="22ed8-146">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="22ed8-147">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="22ed8-147">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="22ed8-148">Distribuzione connessa al cloud-preparare</span><span class="sxs-lookup"><span data-stu-id="22ed8-148">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

