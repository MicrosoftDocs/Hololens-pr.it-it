---
title: Scenari di distribuzione di infrastrutture comuni
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
keywords: HoloLens
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857891"
---
# <span data-ttu-id="3aacb-103">Scenari di distribuzione di infrastrutture comuni</span><span class="sxs-lookup"><span data-stu-id="3aacb-103">Common Infrastructure Deployment Scenarios</span></span>
<span data-ttu-id="3aacb-104">Queste informazioni seguenti forniscono una panoramica dell'architettura di alto livello per tre scenari comuni durante la distribuzione e la gestione dei dispositivi Microsoft HoloLens 2 all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3aacb-104">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

## <span data-ttu-id="3aacb-105">Scenari</span><span class="sxs-lookup"><span data-stu-id="3aacb-105">Scenarios</span></span>

<span data-ttu-id="3aacb-106">Il diagramma seguente rappresenta tre scenari tipici per le distribuzioni di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3aacb-106">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span> 
![scenari](images/scenarios.jpg)

### <span data-ttu-id="3aacb-108">Scenario A</span><span class="sxs-lookup"><span data-stu-id="3aacb-108">Scenario A</span></span>

<span data-ttu-id="3aacb-109">HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="3aacb-109">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="3aacb-110">Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN.</span><span class="sxs-lookup"><span data-stu-id="3aacb-110">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="3aacb-111">Si tratta di una distribuzione molto simile ai dispositivi mobili gestiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="3aacb-111">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="3aacb-112">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="3aacb-112">Basic Common Configurations</span></span>
   * <span data-ttu-id="3aacb-113">Le reti Wi-Fi sono in genere completamente aperte a Internet e ai servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="3aacb-113">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="3aacb-114">Join di Azure AD con registrazione automatica MDM--MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="3aacb-114">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="3aacb-115">Accesso degli utenti con il proprio account aziendale (AAD)</span><span class="sxs-lookup"><span data-stu-id="3aacb-115">Users sign in with their own corporate account (AAD)</span></span> 
     * <span data-ttu-id="3aacb-116">Singoli o più utenti per dispositivo supportati</span><span class="sxs-lookup"><span data-stu-id="3aacb-116">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="3aacb-117">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a specifici casi di utilizzo, da completamente aperti al chiosco di app singole.</span><span class="sxs-lookup"><span data-stu-id="3aacb-117">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="3aacb-118">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="3aacb-118">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="3aacb-119">Sfide comuni</span><span class="sxs-lookup"><span data-stu-id="3aacb-119">Common Challenges</span></span>
   * <span data-ttu-id="3aacb-120">Determinazione delle configurazioni MDM da applicare a HoloLens 2 in base ai requisiti dello scenario.</span><span class="sxs-lookup"><span data-stu-id="3aacb-120">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

### <span data-ttu-id="3aacb-121">Scenario B</span><span class="sxs-lookup"><span data-stu-id="3aacb-121">Scenario B</span></span>

<span data-ttu-id="3aacb-122">HoloLens 2 è distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne.</span><span class="sxs-lookup"><span data-stu-id="3aacb-122">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="3aacb-123">I servizi Internet e cloud possono essere limitati.</span><span class="sxs-lookup"><span data-stu-id="3aacb-123">Internet and cloud services may be limited.</span></span> <span data-ttu-id="3aacb-124">Si tratta di una distribuzione tipica per la maggior parte dei PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3aacb-124">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="3aacb-125">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="3aacb-125">Basic Common Configurations</span></span>
   * <span data-ttu-id="3aacb-126">La rete Wi-Fi è una rete aziendale interna con accesso a risorse interne e accesso limitato a Internet o ai servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="3aacb-126">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="3aacb-127">Join di Azure AD con registrazione automatica MDM</span><span class="sxs-lookup"><span data-stu-id="3aacb-127">Azure AD Join with MDM Auto Enrollment</span></span> 
   * <span data-ttu-id="3aacb-128">Gestito da MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="3aacb-128">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="3aacb-129">Accesso degli utenti con il proprio account aziendale (AAD)</span><span class="sxs-lookup"><span data-stu-id="3aacb-129">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="3aacb-130">Singoli o più utenti per dispositivo supportati</span><span class="sxs-lookup"><span data-stu-id="3aacb-130">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="3aacb-131">Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a specifici casi di utilizzo, da completamente aperti al chiosco di app singole.</span><span class="sxs-lookup"><span data-stu-id="3aacb-131">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="3aacb-132">Una o più applicazioni vengono distribuite tramite MDM</span><span class="sxs-lookup"><span data-stu-id="3aacb-132">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="3aacb-133">Sfide comuni</span><span class="sxs-lookup"><span data-stu-id="3aacb-133">Common Challenges</span></span>
   * <span data-ttu-id="3aacb-134">HoloLens 2 non supporta i locali AD join o SCCM.</span><span class="sxs-lookup"><span data-stu-id="3aacb-134">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="3aacb-135">Solo Azure AD join con MDM.</span><span class="sxs-lookup"><span data-stu-id="3aacb-135">Only Azure AD join with MDM.</span></span> <span data-ttu-id="3aacb-136">Molte aziende di oggi distribuiscono ancora Windows 10 PC in questo scenario, come i dispositivi di annunci collegati locali, gestiti da System Center Configuration Manager (SCCM) e potrebbero non avere l'infrastruttura distribuita/configurata per la gestione di dispositivi Windows 10 interni tramite soluzioni MDM basate su cloud.</span><span class="sxs-lookup"><span data-stu-id="3aacb-136">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="3aacb-137">Poiché HoloLens 2 è un dispositivo cloud First, si basa molto sui servizi Internet e cloud connected per l'autenticazione degli utenti, gli aggiornamenti del sistema operativo, la gestione MDM e così via. Quando ci si connette a una rete aziendale, è molto probabile che le regole proxy/firewall debbano essere modificate per consentire l'accesso a HoloLens 2 e alle applicazioni in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3aacb-137">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span> 
   * <span data-ttu-id="3aacb-138">La connettività Wi-Fi aziendale in genere richiede certificati per autenticare il dispositivo o l'utente alla rete.</span><span class="sxs-lookup"><span data-stu-id="3aacb-138">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="3aacb-139">L'infrastruttura o le impostazioni necessarie per distribuire i certificati in dispositivi Windows 10 tramite MDM può essere difficile da configurare.</span><span class="sxs-lookup"><span data-stu-id="3aacb-139">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="3aacb-140">Scenario C</span><span class="sxs-lookup"><span data-stu-id="3aacb-140">Scenario C</span></span>

<span data-ttu-id="3aacb-141">HoloLens 2 è distribuito per l'uso principalmente offline senza accesso di rete o Internet.</span><span class="sxs-lookup"><span data-stu-id="3aacb-141">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="3aacb-142">Si tratta di una distribuzione tipica per percorsi altamente sicuri o riservati.</span><span class="sxs-lookup"><span data-stu-id="3aacb-142">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="3aacb-143">Configurazioni comuni di base</span><span class="sxs-lookup"><span data-stu-id="3aacb-143">Basic Common Configurations</span></span>
   * <span data-ttu-id="3aacb-144">La connettività Wi-Fi è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="3aacb-144">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="3aacb-145">Ethernet tramite USB può essere abilitato per la connettività LAN, se necessario.</span><span class="sxs-lookup"><span data-stu-id="3aacb-145">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="3aacb-146">Non gestito.</span><span class="sxs-lookup"><span data-stu-id="3aacb-146">Not Managed.</span></span>
   * <span data-ttu-id="3aacb-147">Account utente locale per l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3aacb-147">Local user account for device sign in.</span></span>
     * <span data-ttu-id="3aacb-148">HoloLens 2 supporta solo un account locale.</span><span class="sxs-lookup"><span data-stu-id="3aacb-148">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="3aacb-149">I diversi livelli delle configurazioni di blocco dei dispositivi vengono applicati tramite i pacchetti di provisioning in base a casi di utilizzo specifici.</span><span class="sxs-lookup"><span data-stu-id="3aacb-149">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="3aacb-150">Queste configurazioni sono in genere molto limitate a causa di requisiti di ambiente sicuri.</span><span class="sxs-lookup"><span data-stu-id="3aacb-150">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="3aacb-151">Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="3aacb-151">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="3aacb-152">Sfide comuni</span><span class="sxs-lookup"><span data-stu-id="3aacb-152">Common Challenges</span></span>
   * <span data-ttu-id="3aacb-153">È disponibile un set limitato di configurazioni tramite il provisioning dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="3aacb-153">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="3aacb-154">I servizi cloud non possono essere sfruttati, quindi limitando le funzionalità di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3aacb-154">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="3aacb-155">Maggiore overhead amministrativo poiché questi dispositivi devono essere impostati, configurati e aggiornati manualmente.</span><span class="sxs-lookup"><span data-stu-id="3aacb-155">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>
