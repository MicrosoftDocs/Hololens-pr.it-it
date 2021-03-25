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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448494"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="d06ed-104">Panoramica degli scenari comuni di distribuzione dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="d06ed-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="d06ed-105">Queste informazioni seguenti forniscono una panoramica dell'architettura di alto livello per tre scenari comuni durante la distribuzione e la gestione dei dispositivi Microsoft HoloLens 2 all'interno dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="d06ed-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="d06ed-106">Spesso la modalità di gestione dei dispositivi e l'accesso alle risorse dell'organizzazione dipende in larga parte da fattori già in atto.</span><span class="sxs-lookup"><span data-stu-id="d06ed-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="d06ed-107">In base all'infrastruttura esistente, ti invitiamo a esaminare lo stile di gestione dei dispositivi comune negli scenari seguenti e provare le nostre guide per la distribuzione nello scenario in base alle tue esigenze.</span><span class="sxs-lookup"><span data-stu-id="d06ed-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="d06ed-108">Scenari</span><span class="sxs-lookup"><span data-stu-id="d06ed-108">Scenarios</span></span>

<span data-ttu-id="d06ed-109">Il diagramma seguente rappresenta tre scenari tipici per le distribuzioni di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d06ed-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Diagramma degli scenari](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="d06ed-111">Scenario A: Distribuire ai dispositivi di connessione cloud</span><span class="sxs-lookup"><span data-stu-id="d06ed-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="d06ed-112">HoloLens 2 viene distribuito per l'utilizzo principalmente in ambienti esterni a una rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="d06ed-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="d06ed-113">Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN.</span><span class="sxs-lookup"><span data-stu-id="d06ed-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="d06ed-114">Questa distribuzione è simile ai dispositivi mobili gestiti all'interno di un'azienda.</span><span class="sxs-lookup"><span data-stu-id="d06ed-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="d06ed-115">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="d06ed-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="d06ed-116">Wi-Fi di rete sono in genere completamente aperte a Internet e ai servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="d06ed-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="d06ed-117">Aggiunta ad Azure AD con registrazione automatica di Gestione dispositivi mobili (MDM) -MDM (Intune) Gestito</span><span class="sxs-lookup"><span data-stu-id="d06ed-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d06ed-118">Gli utenti a cui si accede con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d06ed-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d06ed-119">Supporto di uno o più utenti per dispositivo</span><span class="sxs-lookup"><span data-stu-id="d06ed-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d06ed-120">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi di uso specifici, da Completamente aperto a Chiosco app singola.</span><span class="sxs-lookup"><span data-stu-id="d06ed-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d06ed-121">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="d06ed-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="d06ed-122">Sfide comuni</span><span class="sxs-lookup"><span data-stu-id="d06ed-122">Common Challenges</span></span>
   * <span data-ttu-id="d06ed-123">Determinazione delle configurazioni MDM da applicare a HoloLens 2 in base ai requisiti dello scenario.</span><span class="sxs-lookup"><span data-stu-id="d06ed-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="d06ed-124">Per una guida alla distribuzione simile allo scenario A leggere la guida per [Cloud connected HoloLens 2 with Remote Assist.](hololens2-cloud-connected-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d06ed-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d06ed-125">Guida alla distribuzione - HoloLens 2 connesso al cloud con Assistenza remota</span><span class="sxs-lookup"><span data-stu-id="d06ed-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="d06ed-126">Scenario B: distribuire all'interno della rete dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d06ed-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="d06ed-127">HoloLens 2 viene distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne.</span><span class="sxs-lookup"><span data-stu-id="d06ed-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="d06ed-128">I servizi Internet e cloud potrebbero essere limitati.</span><span class="sxs-lookup"><span data-stu-id="d06ed-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="d06ed-129">Questa distribuzione è una distribuzione tipica per la maggior parte dei PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d06ed-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="d06ed-130">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="d06ed-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="d06ed-131">Wi-Fi è una rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="d06ed-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="d06ed-132">Aggiunta ad Azure AD con registrazione automatica MDM</span><span class="sxs-lookup"><span data-stu-id="d06ed-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="d06ed-133">Mdm (Intune) Gestito</span><span class="sxs-lookup"><span data-stu-id="d06ed-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d06ed-134">Gli utenti a cui si accede con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d06ed-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d06ed-135">Supporto di uno o più utenti per dispositivo</span><span class="sxs-lookup"><span data-stu-id="d06ed-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d06ed-136">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi di uso specifici, da Completamente aperto a Chiosco app singola.</span><span class="sxs-lookup"><span data-stu-id="d06ed-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d06ed-137">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="d06ed-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="d06ed-138">Sfide comuni</span><span class="sxs-lookup"><span data-stu-id="d06ed-138">Common Challenges</span></span>
   * <span data-ttu-id="d06ed-139">HoloLens 2 non supporta l'aggiunta ad ACTIVE locale o SCCM.</span><span class="sxs-lookup"><span data-stu-id="d06ed-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="d06ed-140">Solo l'aggiunta ad Azure AD con MDM.</span><span class="sxs-lookup"><span data-stu-id="d06ed-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="d06ed-141">Molte aziende ancora oggi distribuiscono PC Windows 10 in questo scenario come dispositivi aggiunti ad AD locali, gestiti da System Center Configuration Manager (SCCM) e potrebbero non disporre dell'infrastruttura distribuita/configurata per la gestione dei dispositivi Windows 10 interni tramite soluzioni MDM basate su cloud.</span><span class="sxs-lookup"><span data-stu-id="d06ed-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="d06ed-142">Poiché HoloLens 2 è un primo dispositivo cloud, si basa molto sui servizi connessi a Internet e cloud per l'autenticazione utente, gli aggiornamenti del sistema operativo, la gestione MDM e così via.</span><span class="sxs-lookup"><span data-stu-id="d06ed-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="d06ed-143">Quando ci si connette a una rete aziendale, è molto probabile che sia necessario modificare le regole proxy/firewall per consentire l'accesso a HoloLens 2 e alle applicazioni in esecuzione su di essa.</span><span class="sxs-lookup"><span data-stu-id="d06ed-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="d06ed-144">La Wi-Fi aziendale richiede in genere certificati per autenticare il dispositivo o l'utente nella rete.</span><span class="sxs-lookup"><span data-stu-id="d06ed-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="d06ed-145">L'infrastruttura o le impostazioni necessarie per distribuire i certificati nei dispositivi Windows 10 tramite MDM possono essere difficili da configurare.</span><span class="sxs-lookup"><span data-stu-id="d06ed-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d06ed-146">Guida alla distribuzione - HoloLens 2 connesso all'azienda con le guide di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d06ed-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="d06ed-147">Scenario C: Distribuire in un ambiente offline sicuro</span><span class="sxs-lookup"><span data-stu-id="d06ed-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="d06ed-148">HoloLens 2 viene distribuito per l'uso principalmente offline senza accesso alla rete o a Internet.</span><span class="sxs-lookup"><span data-stu-id="d06ed-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="d06ed-149">Si tratta di una distribuzione tipica per posizioni altamente sicure o riservate.</span><span class="sxs-lookup"><span data-stu-id="d06ed-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="d06ed-150">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="d06ed-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="d06ed-151">Wi-Fi connettività è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d06ed-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="d06ed-152">Ethernet tramite USB può essere abilitato per la connettività LAN, se necessario.</span><span class="sxs-lookup"><span data-stu-id="d06ed-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="d06ed-153">Non gestito.</span><span class="sxs-lookup"><span data-stu-id="d06ed-153">Not Managed.</span></span>
   * <span data-ttu-id="d06ed-154">Account utente locale per l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d06ed-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="d06ed-155">HoloLens 2 supporta un solo account locale.</span><span class="sxs-lookup"><span data-stu-id="d06ed-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="d06ed-156">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati tramite pacchetti di provisioning in base a casi di uso specifici.</span><span class="sxs-lookup"><span data-stu-id="d06ed-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="d06ed-157">Queste configurazioni sono in genere limitate a causa dei requisiti di ambiente sicuro.</span><span class="sxs-lookup"><span data-stu-id="d06ed-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="d06ed-158">Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="d06ed-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="d06ed-159">Sfide comuni</span><span class="sxs-lookup"><span data-stu-id="d06ed-159">Common Challenges</span></span>
   * <span data-ttu-id="d06ed-160">È disponibile un set limitato di configurazioni tramite pacchetti di provisioning</span><span class="sxs-lookup"><span data-stu-id="d06ed-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="d06ed-161">I servizi cloud non possono essere utilizzati, limitando quindi le funzionalità di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d06ed-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="d06ed-162">Sovraccarico amministrativo maggiore poiché questi dispositivi devono essere configurati, configurati e aggiornati manualmente.</span><span class="sxs-lookup"><span data-stu-id="d06ed-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="d06ed-163">Per una guida alla distribuzione simile a questo scenario, consultare la Guida [alla distribuzione sicura offline](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="d06ed-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d06ed-164">Guida alla distribuzione - Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d06ed-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
