---
title: Guida alla distribuzione - Guida alla HoloLens 2 aziendale con Dynamics 365 Guides - Panoramica
description: Informazioni su come registrare HoloLens 2 dispositivi con Dynamics 365 Guides su una rete connessa aziendale.
keywords: HoloLens, gestione, connessa aziendale, Dynamics 365 Guides, AAD, Azure AD, MDM, gestione dei dispositivi mobili
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309773"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="903f1-104">Guida alla distribuzione - Guida alla HoloLens 2 aziendale con Dynamics 365 Guides - Panoramica</span><span class="sxs-lookup"><span data-stu-id="903f1-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="903f1-105">Questa guida consente ai professionisti IT di pianificare e distribuire dispositivi Microsoft HoloLens 2 con guide di Dynamics 365 alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="903f1-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="903f1-106">Questa guida è ideale per i progetti pilota e le distribuzioni di produzione ed è simile alla guida [Scenario B: Distribuire all'interno della rete dell'organizzazione.](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network)</span><span class="sxs-lookup"><span data-stu-id="903f1-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="903f1-107">Dopo aver testato il modello di verifica, usare questa guida per procedere con l'integrazione di HoloLens nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="903f1-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="903f1-108">In questa guida verrà illustrato come registrare i dispositivi nella gestione dei dispositivi esistente, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare una guida di Dynamics 365, nonché usare app line-of-business personalizzate dopo la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="903f1-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="903f1-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="903f1-109">Prerequisites</span></span>

<span data-ttu-id="903f1-110">Dovrebbe essere già presente l'infrastruttura seguente:</span><span class="sxs-lookup"><span data-stu-id="903f1-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="903f1-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="903f1-111">Wi-Fi</span></span>
    - <span data-ttu-id="903f1-112">Rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud</span><span class="sxs-lookup"><span data-stu-id="903f1-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="903f1-113">Autenticazione del certificato basata su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="903f1-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="903f1-114">Azure Active Directory (Azure AD) Partecipare alla registrazione automatica MDM (Azure AD[necessaria una sottoscrizione P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="903f1-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="903f1-115">Mdm (Intune) Gestito</span><span class="sxs-lookup"><span data-stu-id="903f1-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="903f1-116">Una o più applicazioni vengono distribuite tramite MDM.</span><span class="sxs-lookup"><span data-stu-id="903f1-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="903f1-117">Rete</span><span class="sxs-lookup"><span data-stu-id="903f1-117">Network</span></span> 
    - <span data-ttu-id="903f1-118">Certificati (SCEP o PKCS)</span><span class="sxs-lookup"><span data-stu-id="903f1-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="903f1-119">Configurazione proxy</span><span class="sxs-lookup"><span data-stu-id="903f1-119">Proxy configuration</span></span>
- <span data-ttu-id="903f1-120">Gli utenti a cui si accede con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="903f1-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="903f1-121">Sono supportati uno o più utenti per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="903f1-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="903f1-122">Diversi livelli di configurazioni di blocco del dispositivo applicate in base a casi d'uso specifici, da Completamente aperto a App singola in modalità tutto schermo.</span><span class="sxs-lookup"><span data-stu-id="903f1-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="903f1-123">Guida alle licenze e ai requisiti</span><span class="sxs-lookup"><span data-stu-id="903f1-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="903f1-124">Account Azure AD</span><span class="sxs-lookup"><span data-stu-id="903f1-124">Azure AD account</span></span>
- <span data-ttu-id="903f1-125">Dynamics 365 Guides applications PC and HoloLens</span><span class="sxs-lookup"><span data-stu-id="903f1-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="903f1-126">Sottoscrizione di Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="903f1-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="903f1-127">Microsoft Dataverse (incluso)</span><span class="sxs-lookup"><span data-stu-id="903f1-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="903f1-128">Power Apps (incluso)</span><span class="sxs-lookup"><span data-stu-id="903f1-128">Power Apps (included)</span></span>
- <span data-ttu-id="903f1-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="903f1-129">Power BI Desktop</span></span>
- <span data-ttu-id="903f1-130">Connettività di rete</span><span class="sxs-lookup"><span data-stu-id="903f1-130">Network Connectivity</span></span>

![Diagramma della rete connessa Corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="903f1-132">Fasi della distribuzione</span><span class="sxs-lookup"><span data-stu-id="903f1-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="903f1-133">Preparare</span><span class="sxs-lookup"><span data-stu-id="903f1-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="903f1-134">Informazioni sulle informazioni di base sull'infrastruttura per HoloLens 2 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="903f1-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="903f1-135">Altre informazioni Azure AD e configurarne una, se non è necessario.</span><span class="sxs-lookup"><span data-stu-id="903f1-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="903f1-136">Informazioni sulla gestione delle identità e su come configurare al meglio Azure AD account.</span><span class="sxs-lookup"><span data-stu-id="903f1-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="903f1-137">Altre informazioni su MDM e configurazione con Intune se non ne è già disponibile una.</span><span class="sxs-lookup"><span data-stu-id="903f1-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="903f1-138">Acquisire familiarità con il Wi-Fi basato su certificati.</span><span class="sxs-lookup"><span data-stu-id="903f1-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="903f1-139">Acquisire familiarità con proxy.</span><span class="sxs-lookup"><span data-stu-id="903f1-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="903f1-140">Informazioni su come usare le app line-of-business.</span><span class="sxs-lookup"><span data-stu-id="903f1-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="903f1-141">Altre informazioni sul modo in cui è possibile usare le guide per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="903f1-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="903f1-142">Configurare</span><span class="sxs-lookup"><span data-stu-id="903f1-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="903f1-143">Come creare utenti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="903f1-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="903f1-144">Come configurare la registrazione automatica.</span><span class="sxs-lookup"><span data-stu-id="903f1-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="903f1-145">Come configurare certificati e profili Wi-Fi per la connettività Wi-Fi aziendale.</span><span class="sxs-lookup"><span data-stu-id="903f1-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="903f1-146">Caricare e assegnare pacchetti di app line-of-business (LOB).</span><span class="sxs-lookup"><span data-stu-id="903f1-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="903f1-147">Configurare le guide di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="903f1-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="903f1-148">Come configurare la modalità tutto schermo (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="903f1-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="903f1-149">Come configurare WDAC (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="903f1-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="903f1-150">Distribuisci</span><span class="sxs-lookup"><span data-stu-id="903f1-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="903f1-151">Convalidare la registrazione tramite dispositivo e MDM.</span><span class="sxs-lookup"><span data-stu-id="903f1-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="903f1-152">Convalidare Wi-Fi certificati.</span><span class="sxs-lookup"><span data-stu-id="903f1-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="903f1-153">Convalidare l'installazione dell'app LOB.</span><span class="sxs-lookup"><span data-stu-id="903f1-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="903f1-154">Convalidare le guide tramite creazione e funzionamento.</span><span class="sxs-lookup"><span data-stu-id="903f1-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="903f1-155">Effettuare la manutenzione</span><span class="sxs-lookup"><span data-stu-id="903f1-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="903f1-156">Aggiornare HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="903f1-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="903f1-157">Come aggiornare le guide (app dello Store).</span><span class="sxs-lookup"><span data-stu-id="903f1-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="903f1-158">Come aggiornare le app LOB.</span><span class="sxs-lookup"><span data-stu-id="903f1-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="903f1-159">Piano di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="903f1-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="903f1-160">Creazione di un piano di supporto.</span><span class="sxs-lookup"><span data-stu-id="903f1-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="903f1-161">Opzioni di gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="903f1-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="903f1-162">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="903f1-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="903f1-163">Distribuzione connessa aziendale - Preparare</span><span class="sxs-lookup"><span data-stu-id="903f1-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
