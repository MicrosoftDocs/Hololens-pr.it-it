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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923534"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="79ed9-104">Guida alla distribuzione - Cloud connected HoloLens 2 with Remote Assist – Overview</span><span class="sxs-lookup"><span data-stu-id="79ed9-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="79ed9-105">Questa guida consente ai professionisti IT di pianificare e distribuire Microsoft HoloLens 2 dispositivi con Remote Assist all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79ed9-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="79ed9-106">Verrà utilizzato come modello per le distribuzioni di modelli di verifica all'organizzazione in un'ampia gamma HoloLens 2 casi d'uso.</span><span class="sxs-lookup"><span data-stu-id="79ed9-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="79ed9-107">La configurazione è simile allo [Scenario A: Distribuire nei dispositivi di connessione al cloud.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="79ed9-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="79ed9-108">Durante la guida verrà illustrato come registrare i dispositivi nella gestione dei dispositivi, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente Remote Assist al momento della configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="79ed9-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="79ed9-109">A tale scopo, verranno trattate le parti importanti dell'infrastruttura necessarie per la configurazione e l'esecuzione, ottenendo una distribuzione su larga scala con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="79ed9-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="79ed9-110">In questa guida non verranno applicate altre restrizioni o configurazioni per i dispositivi, tuttavia è possibile esplorare tali opzioni al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="79ed9-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79ed9-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="79ed9-111">Prerequisites</span></span>

<span data-ttu-id="79ed9-112">L'infrastruttura seguente deve essere presente per distribuire il HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="79ed9-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="79ed9-113">In caso contrario, la configurazione di Azure e Intune è inclusa in questa guida:</span><span class="sxs-lookup"><span data-stu-id="79ed9-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="79ed9-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="79ed9-114">Wi-Fi</span></span>
    - <span data-ttu-id="79ed9-115">Le reti sono in genere aperte a Internet e ai servizi cloud</span><span class="sxs-lookup"><span data-stu-id="79ed9-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="79ed9-116">Azure Active Directory (Azure AD) Partecipare alla registrazione automatica MDM (Azure AD[necessaria una sottoscrizione P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="79ed9-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="79ed9-117">Mdm (Intune) Gestito</span><span class="sxs-lookup"><span data-stu-id="79ed9-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="79ed9-118">Una o più applicazioni vengono distribuite tramite MDM.</span><span class="sxs-lookup"><span data-stu-id="79ed9-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="79ed9-119">Gli utenti a cui si accede con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="79ed9-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="79ed9-120">Sono supportati uno o più utenti per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="79ed9-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Scenario connesso al cloud" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="79ed9-122">Informazioni sulle Remote Assist</span><span class="sxs-lookup"><span data-stu-id="79ed9-122">Learn about Remote Assist</span></span>

<span data-ttu-id="79ed9-123">Remote Assist manutenzione e riparazione collaborativa, l'ispezione remota, nonché la condivisione delle conoscenze e la formazione.</span><span class="sxs-lookup"><span data-stu-id="79ed9-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="79ed9-124">Connettendo persone con ruoli e posizioni diversi, un tecnico Remote Assist connettersi con un collaboratore remoto in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79ed9-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="79ed9-125">Possono combinare video, screenshot e annotazioni per risolvere i problemi in tempo reale anche quando&#39;nella stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="79ed9-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="79ed9-126">I collaboratori remoti possono inserire immagini di riferimento, schemi e altre informazioni utili che il tecnico&#39;ha nello spazio fisico in modo che possano fare riferimento allo schema mentre lavorano a testa alta e senza mani su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="79ed9-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="79ed9-127">Remote Assist licenze e requisiti</span><span class="sxs-lookup"><span data-stu-id="79ed9-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="79ed9-128">Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione delle licenze)</span><span class="sxs-lookup"><span data-stu-id="79ed9-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="79ed9-129">[Remote Assist sottoscrizione](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o versione [di Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="79ed9-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="79ed9-130">Dynamics 365 Remote Assist utente</span><span class="sxs-lookup"><span data-stu-id="79ed9-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="79ed9-131">Remote Assist licenza</span><span class="sxs-lookup"><span data-stu-id="79ed9-131">Remote Assist license</span></span>
- <span data-ttu-id="79ed9-132">Connettività di rete</span><span class="sxs-lookup"><span data-stu-id="79ed9-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="79ed9-133">Utente di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79ed9-133">Microsoft Teams user</span></span>

- <span data-ttu-id="79ed9-134">Microsoft Teams o [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="79ed9-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="79ed9-135">Connettività di rete</span><span class="sxs-lookup"><span data-stu-id="79ed9-135">Network connectivity</span></span>

<span data-ttu-id="79ed9-136">Se si prevede di implementare questo [scenario tra tenant,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)potrebbe essere necessaria una licenza information barriers.</span><span class="sxs-lookup"><span data-stu-id="79ed9-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="79ed9-137">Vedere [questo articolo per](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) determinare se è necessaria una licenza information barrier.</span><span class="sxs-lookup"><span data-stu-id="79ed9-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="79ed9-138">Contenuto della guida:</span><span class="sxs-lookup"><span data-stu-id="79ed9-138">In this guide you will:</span></span>

<span data-ttu-id="79ed9-139">Preparazione:</span><span class="sxs-lookup"><span data-stu-id="79ed9-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="79ed9-140">Informazioni sui dati di base dell'infrastruttura HoloLens 2 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="79ed9-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="79ed9-141">Altre informazioni su Azure AD e su come configurarne una se&#39;non è già stata impostata.</span><span class="sxs-lookup"><span data-stu-id="79ed9-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="79ed9-142">Informazioni sulla gestione delle identità e su come configurare al meglio Azure AD account.</span><span class="sxs-lookup"><span data-stu-id="79ed9-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="79ed9-143">Altre informazioni su MDM e configurazione con Intune se non&#39;ne è già disponibile uno.</span><span class="sxs-lookup"><span data-stu-id="79ed9-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="79ed9-144">Informazioni sui requisiti di rete di Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="79ed9-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="79ed9-145">Facoltativamente: VPN per connettersi alle risorse aziendali</span><span class="sxs-lookup"><span data-stu-id="79ed9-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="79ed9-146">Configurare:</span><span class="sxs-lookup"><span data-stu-id="79ed9-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="79ed9-147">Come creare utenti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="79ed9-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="79ed9-148">Come configurare la registrazione automatica all'interno Azure AD.</span><span class="sxs-lookup"><span data-stu-id="79ed9-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="79ed9-149">Come assegnare le licenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="79ed9-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="79ed9-150">Distribuzione:</span><span class="sxs-lookup"><span data-stu-id="79ed9-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="79ed9-151">Configurare la registrazione HoloLens 2 convalidare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="79ed9-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="79ed9-152">Verificare che sia possibile effettuare una Remote Assist chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ed9-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="79ed9-153">Gestione:</span><span class="sxs-lookup"><span data-stu-id="79ed9-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="79ed9-154">Come aggiornare i Remote Assist usando l'app Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="79ed9-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="79ed9-155">Creazione di un piano di supporto.</span><span class="sxs-lookup"><span data-stu-id="79ed9-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="79ed9-156">Piano di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="79ed9-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="79ed9-157">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="79ed9-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="79ed9-158">Distribuzione connessa al cloud - Preparare</span><span class="sxs-lookup"><span data-stu-id="79ed9-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

