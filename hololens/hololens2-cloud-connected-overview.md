---
title: Guida alla distribuzione-cloud connected HoloLens 2 con Remote Assist-Panoramica
description: Registrare i dispositivi HoloLens tramite una rete connessa al cloud
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
ms.openlocfilehash: fe83333c99f8dbf23b211c9b5155db256dcd20b3
ms.sourcegitcommit: 50e4d61a31b94d5007776064b4012e26cf9ecbbb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271675"
---
# <span data-ttu-id="619d1-104">Guida alla distribuzione-cloud connected HoloLens 2 con Remote Assist-Panoramica</span><span class="sxs-lookup"><span data-stu-id="619d1-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="619d1-105">Questa guida aiuta i professionisti IT a pianificare e distribuire i dispositivi Microsoft HoloLens 2 alla propria organizzazione con l'obiettivo generale di consentire a questi dispositivi di essere connessi alla propria organizzazione con l'assistenza remota di Dynamics 365 pronta per l'uso.</span><span class="sxs-lookup"><span data-stu-id="619d1-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="619d1-106">Tieni presente che questo sarà un modello per le distribuzioni Proof-of-concept per la tua organizzazione in diversi casi di utilizzo di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="619d1-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="619d1-107">Durante la guida verrà illustrato come registrare i dispositivi nella gestione del dispositivo, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente l'assistenza remota alla configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="619d1-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="619d1-108">A questo scopo, rivediamo i principali componenti dell'infrastruttura necessari per la configurazione e l'uso, ottenendo la distribuzione in scala con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="619d1-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="619d1-109">In questa guida</span><span class="sxs-lookup"><span data-stu-id="619d1-109">In this Guide</span></span>

<span data-ttu-id="619d1-110">Questa guida ha l'obiettivo specifico di configurare l'assistenza remota all'interno dell'organizzazione nei dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="619d1-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="619d1-111">Riguarderemo le necessità necessarie per raggiungere questo obiettivo.</span><span class="sxs-lookup"><span data-stu-id="619d1-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="619d1-112">Per mantenere lo stato attivo su questo obiettivo, la preparazione e la configurazione verranno preselezionate in modo da ottimizzare la distribuzione o ridurre gli elementi necessari per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="619d1-112">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="619d1-113">Sarai informato di queste opzioni e potrai personalizzare la distribuzione in base alle tue esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="619d1-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="619d1-114">Si tratta di una configurazione simile allo [scenario a: distribuire ai dispositivi Cloud Connect](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), che è una buona opzione per molti strumenti di prova per le distribuzioni di concetti, che includono:</span><span class="sxs-lookup"><span data-stu-id="619d1-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="619d1-115">Le reti di Wi-Fi sono in genere completamente aperte a Internet e ai servizi cloud</span><span class="sxs-lookup"><span data-stu-id="619d1-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="619d1-116">Join di Azure AD con registrazione automatica MDM--MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="619d1-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="619d1-117">Accesso degli utenti con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="619d1-117">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="619d1-118">Singoli o più utenti per dispositivo supportati</span><span class="sxs-lookup"><span data-stu-id="619d1-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="619d1-119">I vari livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi di utilizzo specifici, dal chiosco completamente aperto al singolo app</span><span class="sxs-lookup"><span data-stu-id="619d1-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Scenario connesso al cloud](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="619d1-121">In questa guida non verranno applicate altre limitazioni o configurazioni di dispositivo, ma ti invitiamo ad esplorare queste opzioni dopo la fine.</span><span class="sxs-lookup"><span data-stu-id="619d1-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="619d1-122">Informazioni sull'assistenza remota</span><span class="sxs-lookup"><span data-stu-id="619d1-122">Learn about Remote Assist</span></span>

<span data-ttu-id="619d1-123">L'assistenza remota consente la manutenzione e il ripristino collaborativo, il controllo remoto e la condivisione delle conoscenze e la formazione.</span><span class="sxs-lookup"><span data-stu-id="619d1-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="619d1-124">Collegando persone in ruoli e posizioni diverse, un tecnico che usa l'assistenza remota può connettersi a un collaboratore remoto in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="619d1-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="619d1-125">Possono combinare video, screenshot e annotazioni per risolvere i problemi in tempo reale anche quando non sono&#39;t nella stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="619d1-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="619d1-126">I collaboratori remoti possono inserire immagini di riferimento, schemi e altre informazioni utili per lo spazio fisico del tecnico&#39;, in modo che possano riferirsi allo schema mentre si lavora a heads-up e Hands-Free su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="619d1-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="619d1-127">In questa guida verrà:</span><span class="sxs-lookup"><span data-stu-id="619d1-127">In this guide you will:</span></span>

<span data-ttu-id="619d1-128">Preparare</span><span class="sxs-lookup"><span data-stu-id="619d1-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="619d1-129">Informazioni sull'infrastruttura Essentials per i dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="619d1-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="619d1-130">Leggi altre informazioni su Azure AD e impostane una se non ne hai&#39;.</span><span class="sxs-lookup"><span data-stu-id="619d1-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="619d1-131">Informazioni sulla gestione delle identità e sulla configurazione ottimale degli account di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="619d1-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="619d1-132">Leggi altre informazioni su MDM e configura con Intune se Don&#39;t ne hai già uno pronto.</span><span class="sxs-lookup"><span data-stu-id="619d1-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="619d1-133">Informazioni sui requisiti di rete di Remote assist.</span><span class="sxs-lookup"><span data-stu-id="619d1-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="619d1-134">Facoltativamente: VPN per connettersi alle risorse dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="619d1-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="619d1-135">Configurare</span><span class="sxs-lookup"><span data-stu-id="619d1-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="619d1-136">Come creare utenti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="619d1-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="619d1-137">Come configurare la registrazione automatica in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="619d1-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="619d1-138">Come assegnare le licenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="619d1-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="619d1-139">Distribuire</span><span class="sxs-lookup"><span data-stu-id="619d1-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="619d1-140">Configurare la registrazione di HoloLens 2 e Validate.</span><span class="sxs-lookup"><span data-stu-id="619d1-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="619d1-141">Verificare che sia possibile effettuare una chiamata assistita remota.</span><span class="sxs-lookup"><span data-stu-id="619d1-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="619d1-142">Mantenere</span><span class="sxs-lookup"><span data-stu-id="619d1-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="619d1-143">Come aggiornare Remote Assist con l'app Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="619d1-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="619d1-144">Creazione di un piano di supporto.</span><span class="sxs-lookup"><span data-stu-id="619d1-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="619d1-145">Piano di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="619d1-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="619d1-146">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="619d1-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="619d1-147">Distribuzione connessa al cloud-preparare</span><span class="sxs-lookup"><span data-stu-id="619d1-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

