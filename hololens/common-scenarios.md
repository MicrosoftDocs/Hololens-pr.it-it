---
title: Scenari comuni di distribuzione dell'infrastruttura
description: Informazioni su alcuni degli scenari di distribuzione più comuni basati su diverse distribuzioni dell'infrastruttura per la realtà mista.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397422"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="aca00-104">Panoramica degli scenari comuni di distribuzione dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="aca00-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="aca00-105">Le informazioni seguenti forniscono una panoramica generale dell'architettura per tre scenari comuni durante la distribuzione e la gestione di Microsoft HoloLens 2 all'interno dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="aca00-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="aca00-106">Spesso il modo in cui si gestiscono i dispositivi e come accedere alle risorse dell'organizzazione è determinato in gran parte da fattori già presenti.</span><span class="sxs-lookup"><span data-stu-id="aca00-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="aca00-107">In base all'infrastruttura esistente, è necessario esaminare lo stile di gestione dei dispositivi comune negli scenari seguenti e provare le guide per la distribuzione nello scenario in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="aca00-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="aca00-108">Scenari</span><span class="sxs-lookup"><span data-stu-id="aca00-108">Scenarios</span></span>

<span data-ttu-id="aca00-109">Il diagramma seguente rappresenta due scenari gestiti tipici per HoloLens 2 distribuzione.</span><span class="sxs-lookup"><span data-stu-id="aca00-109">The diagram below represents two typical managed scenarios for HoloLens 2 deployments.</span></span>
 

<span data-ttu-id="aca00-110">Esiste anche un terzo scenario che consente distribuzioni protette offline.</span><span class="sxs-lookup"><span data-stu-id="aca00-110">There is also third scenario that allows for offline secure deployments.</span></span>

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="aca00-111">Scenario A: Distribuire nei dispositivi connessi al cloud</span><span class="sxs-lookup"><span data-stu-id="aca00-111">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="aca00-112">HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="aca00-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="aca00-113">Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN.</span><span class="sxs-lookup"><span data-stu-id="aca00-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="aca00-114">Questa distribuzione è simile ai dispositivi mobili gestiti all'interno di un'azienda.</span><span class="sxs-lookup"><span data-stu-id="aca00-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="aca00-115">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="aca00-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="aca00-116">Wi-Fi reti virtuali sono in genere completamente aperte a Internet e ai servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="aca00-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="aca00-117">Azure AD aggiunta alla registrazione automatica di Gestione di dispositivi mobili (MDM) - Gestione MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="aca00-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="aca00-118">Gli utenti a cui si accede con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="aca00-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="aca00-119">Supporto di uno o più utenti per dispositivo</span><span class="sxs-lookup"><span data-stu-id="aca00-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="aca00-120">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a App singola in modalità tutto schermo.</span><span class="sxs-lookup"><span data-stu-id="aca00-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="aca00-121">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="aca00-121">One or more applications are deployed via MDM</span></span>



* <span data-ttu-id="aca00-122">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="aca00-122">Common Challenges</span></span>
   * <span data-ttu-id="aca00-123">Determinazione delle configurazioni MDM da applicare alla HoloLens 2 in base ai requisiti dello scenario.</span><span class="sxs-lookup"><span data-stu-id="aca00-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="aca00-124">[![Diagramma dello scenario A ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="aca00-124">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="aca00-125">Per una guida alla distribuzione simile a questo scenario, vedere la guida alla distribuzione dell'ambiente [connesso al cloud](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aca00-125">For a deployment guide that is similar to this scenario review our guide for [Cloud connected environment deployment guide](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="aca00-126">Guida alla distribuzione dell'ambiente connesso al cloud</span><span class="sxs-lookup"><span data-stu-id="aca00-126">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="aca00-127">Guida alla distribuzione dell'ambiente connesso al cloud (client esterni)</span><span class="sxs-lookup"><span data-stu-id="aca00-127">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="aca00-128">Scenario B: Distribuire all'interno della rete dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="aca00-128">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="aca00-129">HoloLens 2 viene distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne.</span><span class="sxs-lookup"><span data-stu-id="aca00-129">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="aca00-130">I servizi Internet e cloud possono essere limitati.</span><span class="sxs-lookup"><span data-stu-id="aca00-130">Internet and cloud services may be limited.</span></span> <span data-ttu-id="aca00-131">Questa distribuzione è una distribuzione tipica per la maggior Windows 10 PC.</span><span class="sxs-lookup"><span data-stu-id="aca00-131">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="aca00-132">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="aca00-132">Basic Common Configurations</span></span>
   * <span data-ttu-id="aca00-133">Wi-Fi rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="aca00-133">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="aca00-134">Azure AD join con la registrazione automatica MDM</span><span class="sxs-lookup"><span data-stu-id="aca00-134">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="aca00-135">GESTIONE MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="aca00-135">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="aca00-136">Gli utenti a cui si accede con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="aca00-136">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="aca00-137">Supporto di uno o più utenti per dispositivo</span><span class="sxs-lookup"><span data-stu-id="aca00-137">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="aca00-138">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a Modalità tutto schermo per app singola.</span><span class="sxs-lookup"><span data-stu-id="aca00-138">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="aca00-139">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="aca00-139">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="aca00-140">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="aca00-140">Common Challenges</span></span>
   * <span data-ttu-id="aca00-141">HoloLens 2 non supporta l'aggiunta ad ACTIVE locale o SCCM.</span><span class="sxs-lookup"><span data-stu-id="aca00-141">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="aca00-142">Aggiungere Azure AD mdm.</span><span class="sxs-lookup"><span data-stu-id="aca00-142">Only Azure AD join with MDM.</span></span> <span data-ttu-id="aca00-143">Molte aziende oggi distribuiscono ancora PC Windows 10 in questo scenario come dispositivi aggiunti ad AD locali, gestiti da System Center Gestione configurazione (SCCM) e potrebbero non avere l'infrastruttura distribuita/configurata per la gestione dei dispositivi Windows 10 interni tramite soluzioni MDM basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="aca00-143">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="aca00-144">Poiché HoloLens 2 è un dispositivo cloud first, si basa in larga parte sui servizi connessi a Internet e cloud per l'autenticazione utente, gli aggiornamenti del sistema operativo, la gestione MDM e così via.</span><span class="sxs-lookup"><span data-stu-id="aca00-144">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="aca00-145">Quando ci si connette a una rete aziendale, è molto probabile che sia necessario modificare le regole proxy/firewall per abilitare l'accesso per HoloLens 2 e le applicazioni in esecuzione su di essa.</span><span class="sxs-lookup"><span data-stu-id="aca00-145">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="aca00-146">La Wi-Fi aziendale richiede in genere certificati per autenticare il dispositivo o l'utente nella rete.</span><span class="sxs-lookup"><span data-stu-id="aca00-146">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="aca00-147">L'infrastruttura o le impostazioni necessarie per distribuire i certificati Windows 10 dispositivi tramite MDM possono essere difficili da configurare.</span><span class="sxs-lookup"><span data-stu-id="aca00-147">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="aca00-148">[![Diagramma dello scenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="aca00-148">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="aca00-149">[![Diagramma dello scenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="aca00-149">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="aca00-150">Per una guida alla distribuzione simile a questo scenario, vedere la guida alla [guida alla distribuzione della rete aziendale](hololens2-corp-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aca00-150">For a deployment guide that is similar to this scenario review our guide for [Corporate network deployment guide](hololens2-corp-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="aca00-151">Guida alla distribuzione della rete aziendale</span><span class="sxs-lookup"><span data-stu-id="aca00-151">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="aca00-152">Scenario C: Distribuire in un ambiente offline sicuro</span><span class="sxs-lookup"><span data-stu-id="aca00-152">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="aca00-153">HoloLens 2 viene distribuito per l'uso principalmente offline senza accesso alla rete o a Internet.</span><span class="sxs-lookup"><span data-stu-id="aca00-153">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="aca00-154">Si tratta di una distribuzione tipica per posizioni altamente sicure o riservate.</span><span class="sxs-lookup"><span data-stu-id="aca00-154">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="aca00-155">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="aca00-155">Basic Common Configurations</span></span>
   * <span data-ttu-id="aca00-156">Wi-Fi connettività è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="aca00-156">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="aca00-157">Ethernet tramite USB può essere abilitata per la connettività LAN, se necessario.</span><span class="sxs-lookup"><span data-stu-id="aca00-157">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="aca00-158">Non gestito.</span><span class="sxs-lookup"><span data-stu-id="aca00-158">Not Managed.</span></span>
   * <span data-ttu-id="aca00-159">Account utente locale per l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aca00-159">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="aca00-160">HoloLens 2 supporta un solo account locale.</span><span class="sxs-lookup"><span data-stu-id="aca00-160">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="aca00-161">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati tramite pacchetti di provisioning in base a casi d'uso specifici.</span><span class="sxs-lookup"><span data-stu-id="aca00-161">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="aca00-162">Queste configurazioni sono in genere limitate a causa dei requisiti dell'ambiente sicuro.</span><span class="sxs-lookup"><span data-stu-id="aca00-162">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="aca00-163">Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="aca00-163">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="aca00-164">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="aca00-164">Common Challenges</span></span>
   * <span data-ttu-id="aca00-165">È disponibile un set limitato di configurazioni tramite il provisioning dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="aca00-165">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="aca00-166">I servizi cloud non possono essere usati, limitando quindi le HoloLens 2 funzionalità.</span><span class="sxs-lookup"><span data-stu-id="aca00-166">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="aca00-167">Maggiore sovraccarico amministrativo perché questi dispositivi devono essere configurati, configurati e aggiornati manualmente.</span><span class="sxs-lookup"><span data-stu-id="aca00-167">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="aca00-168">[![Diagramma 1 ](images/deployment-guides-revised-scenario-c-01.png) della sicurezza offline](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="aca00-168">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="aca00-169">Per una guida alla distribuzione simile a questo scenario, vedere la guida [alla distribuzione dell'ambiente protetto offline](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="aca00-169">For a deployment guide that is similar to this scenario review our [Offline secure environment deployment guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="aca00-170">Guida alla distribuzione dell'ambiente protetto offline</span><span class="sxs-lookup"><span data-stu-id="aca00-170">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)
