---
title: Scenari comuni di distribuzione dell'infrastruttura
description: Alcuni scenari di distribuzione comuni basati su infrastrutture comuni diverse
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: a7d847e2d2d335f2e2388535a5cf9d5246bb330b
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253073"
---
# <span data-ttu-id="5abcd-104">Panoramica degli scenari di distribuzione delle infrastrutture comuni</span><span class="sxs-lookup"><span data-stu-id="5abcd-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="5abcd-105">Queste informazioni seguenti forniscono una panoramica dell'architettura di alto livello per tre scenari comuni durante la distribuzione e la gestione dei dispositivi Microsoft HoloLens 2 all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5abcd-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="5abcd-106">Spesso il modo in cui Gestisci i tuoi dispositivi e come accedere alle risorse dell'organizzazione è in gran parte determinato da fattori già esistenti.</span><span class="sxs-lookup"><span data-stu-id="5abcd-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="5abcd-107">In base all'infrastruttura esistente invitiamo a esaminare lo stile di gestione dei dispositivi comuni negli scenari seguenti e provare le guide per la distribuzione nello scenario che soddisfa le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="5abcd-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="5abcd-108">Scenari</span><span class="sxs-lookup"><span data-stu-id="5abcd-108">Scenarios</span></span>

<span data-ttu-id="5abcd-109">Il diagramma seguente rappresenta tre scenari tipici per le distribuzioni di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5abcd-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Diagramma scenari](images/scenarios.jpg)

### <span data-ttu-id="5abcd-111">Scenario A: distribuire ai dispositivi di connessione cloud</span><span class="sxs-lookup"><span data-stu-id="5abcd-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="5abcd-112">HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="5abcd-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="5abcd-113">Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN.</span><span class="sxs-lookup"><span data-stu-id="5abcd-113">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="5abcd-114">Questa distribuzione è simile ai dispositivi mobili gestiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="5abcd-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="5abcd-115">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="5abcd-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="5abcd-116">Le reti di Wi-Fi sono in genere completamente aperte a Internet e ai servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="5abcd-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="5abcd-117">Join di Azure AD con registrazione automatica MDM--MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="5abcd-117">Azure AD Join with MDM Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="5abcd-118">Accesso degli utenti con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="5abcd-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="5abcd-119">Singoli o più utenti per dispositivo supportati</span><span class="sxs-lookup"><span data-stu-id="5abcd-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="5abcd-120">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a specifici casi di utilizzo, da completamente aperti al chiosco di app singole.</span><span class="sxs-lookup"><span data-stu-id="5abcd-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="5abcd-121">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="5abcd-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="5abcd-122">Sfide comuni</span><span class="sxs-lookup"><span data-stu-id="5abcd-122">Common Challenges</span></span>
   * <span data-ttu-id="5abcd-123">Determinazione delle configurazioni MDM da applicare a HoloLens 2 in base ai requisiti dello scenario.</span><span class="sxs-lookup"><span data-stu-id="5abcd-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="5abcd-124">Per una guida alla distribuzione simile allo scenario A rivedere la nostra guida per [cloud connected HoloLens 2 con Remote Assist](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5abcd-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5abcd-125">Guida alla distribuzione-cloud connected HoloLens 2 con assistenza remota</span><span class="sxs-lookup"><span data-stu-id="5abcd-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="5abcd-126">Scenario B: distribuire all'interno della rete dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5abcd-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="5abcd-127">HoloLens 2 è distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne.</span><span class="sxs-lookup"><span data-stu-id="5abcd-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="5abcd-128">I servizi Internet e cloud possono essere limitati.</span><span class="sxs-lookup"><span data-stu-id="5abcd-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="5abcd-129">Questa distribuzione è una distribuzione tipica per la maggior parte dei PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5abcd-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="5abcd-130">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="5abcd-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="5abcd-131">Wi-Fi Network è una rete aziendale interna con accesso a risorse interne e accesso limitato a Internet o ai servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="5abcd-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="5abcd-132">Join di Azure AD con registrazione automatica MDM</span><span class="sxs-lookup"><span data-stu-id="5abcd-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="5abcd-133">Gestito da MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="5abcd-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="5abcd-134">Accesso degli utenti con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="5abcd-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="5abcd-135">Singoli o più utenti per dispositivo supportati</span><span class="sxs-lookup"><span data-stu-id="5abcd-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="5abcd-136">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a specifici casi di utilizzo, da completamente aperti al chiosco di app singole.</span><span class="sxs-lookup"><span data-stu-id="5abcd-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="5abcd-137">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="5abcd-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="5abcd-138">Sfide comuni</span><span class="sxs-lookup"><span data-stu-id="5abcd-138">Common Challenges</span></span>
   * <span data-ttu-id="5abcd-139">HoloLens 2 non supporta i locali AD join o SCCM.</span><span class="sxs-lookup"><span data-stu-id="5abcd-139">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="5abcd-140">Solo Azure AD join con MDM.</span><span class="sxs-lookup"><span data-stu-id="5abcd-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="5abcd-141">Molte aziende di oggi distribuiscono ancora Windows 10 PC in questo scenario, come nei dispositivi Uniti AD un locale, gestiti da System Center Configuration Manager (SCCM) e potrebbero non avere l'infrastruttura distribuita/configurata per la gestione di dispositivi Windows 10 interni tramite soluzioni MDM basate su cloud.</span><span class="sxs-lookup"><span data-stu-id="5abcd-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="5abcd-142">Poiché HoloLens 2 è un dispositivo cloud First, si basa molto sui servizi Internet e cloud connected per l'autenticazione degli utenti, gli aggiornamenti del sistema operativo, la gestione MDM e così via. Quando ci si connette a una rete aziendale, è molto probabile che le regole proxy/firewall debbano essere modificate per consentire l'accesso a HoloLens 2 e alle applicazioni in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5abcd-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="5abcd-143">La connettività Wi-Fi aziendale in genere richiede certificati per autenticare il dispositivo o l'utente alla rete.</span><span class="sxs-lookup"><span data-stu-id="5abcd-143">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="5abcd-144">L'infrastruttura o le impostazioni necessarie per distribuire i certificati in dispositivi Windows 10 tramite MDM può essere difficile da configurare.</span><span class="sxs-lookup"><span data-stu-id="5abcd-144">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="5abcd-145">Scenario C: distribuire in un ambiente offline sicuro</span><span class="sxs-lookup"><span data-stu-id="5abcd-145">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="5abcd-146">HoloLens 2 è distribuito per l'uso principalmente offline senza accesso di rete o Internet.</span><span class="sxs-lookup"><span data-stu-id="5abcd-146">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="5abcd-147">Si tratta di una distribuzione tipica per percorsi altamente sicuri o riservati.</span><span class="sxs-lookup"><span data-stu-id="5abcd-147">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="5abcd-148">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="5abcd-148">Basic Common Configurations</span></span>
   * <span data-ttu-id="5abcd-149">La connettività Wi-Fi è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="5abcd-149">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="5abcd-150">Ethernet tramite USB può essere abilitato per la connettività LAN, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5abcd-150">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="5abcd-151">Non gestito.</span><span class="sxs-lookup"><span data-stu-id="5abcd-151">Not Managed.</span></span>
   * <span data-ttu-id="5abcd-152">Account utente locale per l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5abcd-152">Local user account for device sign in.</span></span>
     * <span data-ttu-id="5abcd-153">HoloLens 2 supporta un solo account locale.</span><span class="sxs-lookup"><span data-stu-id="5abcd-153">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="5abcd-154">I diversi livelli delle configurazioni di blocco dei dispositivi vengono applicati tramite i pacchetti di provisioning in base a casi di utilizzo specifici.</span><span class="sxs-lookup"><span data-stu-id="5abcd-154">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="5abcd-155">Queste configurazioni sono in genere molto limitate a causa di requisiti di ambiente sicuri.</span><span class="sxs-lookup"><span data-stu-id="5abcd-155">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="5abcd-156">Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="5abcd-156">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="5abcd-157">Sfide comuni</span><span class="sxs-lookup"><span data-stu-id="5abcd-157">Common Challenges</span></span>
   * <span data-ttu-id="5abcd-158">È disponibile un set limitato di configurazioni tramite il provisioning dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="5abcd-158">There is a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="5abcd-159">I servizi cloud non possono essere sfruttati, quindi limitando le funzionalità di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5abcd-159">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="5abcd-160">Maggiore overhead amministrativo poiché questi dispositivi devono essere impostati, configurati e aggiornati manualmente.</span><span class="sxs-lookup"><span data-stu-id="5abcd-160">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>

<span data-ttu-id="5abcd-161">Per una guida alla distribuzione simile a questo scenario, vedere la [Guida alla distribuzione sicura offline](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="5abcd-161">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5abcd-162">Guida alla distribuzione-offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5abcd-162">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
