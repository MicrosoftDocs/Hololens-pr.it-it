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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309482"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="5e1a2-104">Panoramica degli scenari comuni di distribuzione dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="5e1a2-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="5e1a2-105">Queste informazioni forniscono una panoramica generale dell'architettura per tre scenari comuni quando si distribuiscono e si gestiscono Microsoft HoloLens 2 dispositivi all'interno dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="5e1a2-106">Spesso il modo in cui si gestiscono i dispositivi e come accedere alle risorse dell'organizzazione è determinato in gran parte da fattori già presenti.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="5e1a2-107">In base all'infrastruttura esistente, è necessario esaminare lo stile di gestione dei dispositivi comune negli scenari seguenti e provare le guide per la distribuzione nello scenario in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="5e1a2-108">Scenari</span><span class="sxs-lookup"><span data-stu-id="5e1a2-108">Scenarios</span></span>

<span data-ttu-id="5e1a2-109">Il diagramma seguente rappresenta tre scenari tipici per HoloLens 2 distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
<span data-ttu-id="5e1a2-110">![Diagramma degli scenari](images/scenarios.jpg)</span><span class="sxs-lookup"><span data-stu-id="5e1a2-110">![Scenarios diagram](images/scenarios.jpg)</span></span>

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="5e1a2-111">Scenario A: Distribuire nei dispositivi cloud connect</span><span class="sxs-lookup"><span data-stu-id="5e1a2-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="5e1a2-112">HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="5e1a2-113">Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="5e1a2-114">Questa distribuzione è simile ai dispositivi mobili gestiti all'interno di un'azienda.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="5e1a2-115">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="5e1a2-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="5e1a2-116">Wi-Fi le reti sono in genere completamente aperte ai servizi Internet e Cloud.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="5e1a2-117">Azure AD aggiunta alla registrazione automatica mdm (Mobile Device Management) gestita da MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="5e1a2-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="5e1a2-118">Gli utenti a cui si accede con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="5e1a2-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="5e1a2-119">Supporto di uno o più utenti per dispositivo</span><span class="sxs-lookup"><span data-stu-id="5e1a2-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="5e1a2-120">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a Modalità tutto schermo per app singola.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="5e1a2-121">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="5e1a2-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="5e1a2-122">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="5e1a2-122">Common Challenges</span></span>
   * <span data-ttu-id="5e1a2-123">Determinazione delle configurazioni MDM da applicare al HoloLens 2 in base ai requisiti dello scenario.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="5e1a2-124">Per una guida alla distribuzione simile allo scenario A esaminare la guida per Cloud [connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5e1a2-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5e1a2-125">Guida alla distribuzione- Cloud connected HoloLens 2 with Remote Assist</span><span class="sxs-lookup"><span data-stu-id="5e1a2-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="5e1a2-126">Scenario B: Eseguire la distribuzione all'interno della rete dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5e1a2-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="5e1a2-127">HoloLens 2 viene distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="5e1a2-128">I servizi Internet e cloud possono essere limitati.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="5e1a2-129">Questa distribuzione è una distribuzione tipica per la maggior parte Windows 10 PC.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="5e1a2-130">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="5e1a2-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="5e1a2-131">Wi-Fi rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="5e1a2-132">Azure AD join con la registrazione automatica MDM</span><span class="sxs-lookup"><span data-stu-id="5e1a2-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="5e1a2-133">Mdm (Intune) Gestito</span><span class="sxs-lookup"><span data-stu-id="5e1a2-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="5e1a2-134">Gli utenti a cui si accede con il proprio account aziendale (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="5e1a2-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="5e1a2-135">Supporto di uno o più utenti per dispositivo</span><span class="sxs-lookup"><span data-stu-id="5e1a2-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="5e1a2-136">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a App singola in modalità tutto schermo.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="5e1a2-137">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="5e1a2-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="5e1a2-138">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="5e1a2-138">Common Challenges</span></span>
   * <span data-ttu-id="5e1a2-139">HoloLens 2 non supporta l'aggiunta ad AD locale o SCCM.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="5e1a2-140">Aggiungere Azure AD mdm.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="5e1a2-141">Molte aziende distribuiscono ancora PC Windows 10 in questo scenario come dispositivi aggiunti ad AD locali, gestiti da System Center Gestione configurazione (SCCM) e potrebbero non avere l'infrastruttura distribuita/configurata per la gestione dei dispositivi Windows 10 interni tramite soluzioni MDM basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="5e1a2-142">Poiché HoloLens 2 è un primo dispositivo cloud, si basa molto sui servizi connessi a Internet e cloud per l'autenticazione utente, gli aggiornamenti del sistema operativo, la gestione MDM e così via.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="5e1a2-143">Quando ci si connette a una rete aziendale, è molto probabile che sia necessario modificare le regole proxy/firewall per abilitare l'accesso per HoloLens 2 e le applicazioni in esecuzione su di essa.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="5e1a2-144">La Wi-Fi aziendale richiede in genere certificati per autenticare il dispositivo o l'utente nella rete.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="5e1a2-145">L'infrastruttura o le impostazioni necessarie per distribuire i certificati Windows 10 dispositivi tramite MDM possono essere difficili da configurare.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5e1a2-146">Guida alla distribuzione- Guida alla HoloLens 2 aziendale con le guide di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5e1a2-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="5e1a2-147">Scenario C: Distribuire in un ambiente offline sicuro</span><span class="sxs-lookup"><span data-stu-id="5e1a2-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="5e1a2-148">HoloLens 2 viene distribuito per l'uso principalmente offline senza accesso alla rete o a Internet.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="5e1a2-149">Si tratta di una distribuzione tipica per posizioni altamente sicure o riservate.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="5e1a2-150">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="5e1a2-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="5e1a2-151">Wi-Fi la connettività è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="5e1a2-152">Ethernet tramite USB può essere abilitato per la connettività LAN, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="5e1a2-153">Non gestito.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-153">Not Managed.</span></span>
   * <span data-ttu-id="5e1a2-154">Account utente locale per l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="5e1a2-155">HoloLens 2 supporta un solo account locale.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="5e1a2-156">I diversi livelli di configurazioni di blocco dei dispositivi vengono applicati tramite pacchetti di provisioning in base a casi d'uso specifici.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="5e1a2-157">Queste configurazioni sono in genere limitate a causa dei requisiti di ambiente sicuro.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="5e1a2-158">Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="5e1a2-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="5e1a2-159">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="5e1a2-159">Common Challenges</span></span>
   * <span data-ttu-id="5e1a2-160">È disponibile un set limitato di configurazioni tramite i pacchetti di provisioning</span><span class="sxs-lookup"><span data-stu-id="5e1a2-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="5e1a2-161">I servizi cloud non possono essere usati, limitando quindi le HoloLens 2 funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="5e1a2-162">Maggiore sovraccarico amministrativo perché questi dispositivi devono essere configurati, configurati e aggiornati manualmente.</span><span class="sxs-lookup"><span data-stu-id="5e1a2-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="5e1a2-163">Per una guida alla distribuzione simile a questo scenario, vedere la [Guida alla distribuzione sicura offline.](hololens-common-scenarios-offline-secure.md)</span><span class="sxs-lookup"><span data-stu-id="5e1a2-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5e1a2-164">Guida alla distribuzione - Sicurezza offline HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5e1a2-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
