---
title: Requisiti relativi alle licenze
description: Tenersi aggiornati su tutti i requisiti di licenza e le linee guida necessari per la gestione dei dispositivi mobili, HoloLens e Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635892"
---
# <a name="license-requirements"></a><span data-ttu-id="e7d2f-103">Requisiti relativi alle licenze</span><span class="sxs-lookup"><span data-stu-id="e7d2f-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="e7d2f-104">HoloLens 2 Dispositivo (gestito)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="e7d2f-105">Azure AD Account</span><span class="sxs-lookup"><span data-stu-id="e7d2f-105">Azure AD Account</span></span>](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="e7d2f-106">Active Directory (AD) non può essere usato per gestire HoloLens dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="e7d2f-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) o un altro MDM.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="e7d2f-108">[Windows Autopilot per HoloLens 2:](hololens2-autopilot.md)semplifica l'esperienza di provisioning sia per gli amministratori IT che per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="e7d2f-109">Gli amministratori IT possono preconfigurare i HoloLens 2 e al primo avvio i dispositivi verranno distribuiti in stato business-ready senza interazione dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="e7d2f-110">Windows Autopilot richiede [che Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) e [la registrazione](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) automatica siano configurati per primi per la distribuzione del dispositivo e del flusso di Autopilot a tocco basso.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-110">Windows Autopilot requires [Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="e7d2f-111">Caso d'uso aziendale:</span><span class="sxs-lookup"><span data-stu-id="e7d2f-111">Business Use Case:</span></span> 

- <span data-ttu-id="e7d2f-112">[Scenario di distribuzione A:](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) modello di verifica o distribuzione pilota.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="e7d2f-113">[Scenario di distribuzione B:](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) distribuzione su larga scala.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="e7d2f-114">HoloLens 2 Solo dispositivo (non gestito)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="e7d2f-115">Quando si usa un account Microsoft (MSA) o un account locale, non sono necessarie licenze aggiuntive per questi account.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="e7d2f-116">Account locale</span><span class="sxs-lookup"><span data-stu-id="e7d2f-116">Local Account</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="e7d2f-117">Il provisioning di questo account deve [essere](hololens-provisioning.md#provisioning-package-hololens-wizard) eseguito in anticipo con Windows Configuration Designer (WCD).</span><span class="sxs-lookup"><span data-stu-id="e7d2f-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="e7d2f-118">Account Microsoft (MSA)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-118">Microsoft Account (MSA)</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="e7d2f-119">Non sono supportati più utenti per un dispositivo che usa uno di questi account.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="e7d2f-120">Caso d'uso aziendale:</span><span class="sxs-lookup"><span data-stu-id="e7d2f-120">Business Use Case:</span></span> 

- <span data-ttu-id="e7d2f-121">[Scenario di distribuzione C:](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) distribuzione offline o sicura.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="e7d2f-122">Licenze e requisiti di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e7d2f-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="e7d2f-123">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e7d2f-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="e7d2f-124">Amministrativi</span><span class="sxs-lookup"><span data-stu-id="e7d2f-124">Admin</span></span>

- <span data-ttu-id="e7d2f-125">Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione delle licenze)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="e7d2f-126">[Remote Assist sottoscrizione](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o versione [di Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-126">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="e7d2f-127">Dynamics 365 Remote Assist utente</span><span class="sxs-lookup"><span data-stu-id="e7d2f-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="e7d2f-128">Account Azure AD</span><span class="sxs-lookup"><span data-stu-id="e7d2f-128">Azure AD account</span></span>

- <span data-ttu-id="e7d2f-129">Remote Assist licenza</span><span class="sxs-lookup"><span data-stu-id="e7d2f-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="e7d2f-130">Microsoft Teams è in bundle con Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e7d2f-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="e7d2f-131">Connettività di rete</span><span class="sxs-lookup"><span data-stu-id="e7d2f-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="e7d2f-132">Microsoft Teams utente</span><span class="sxs-lookup"><span data-stu-id="e7d2f-132">Microsoft Teams user</span></span>

- <span data-ttu-id="e7d2f-133">Account Azure AD</span><span class="sxs-lookup"><span data-stu-id="e7d2f-133">Azure AD account</span></span>

- <span data-ttu-id="e7d2f-134">Microsoft Teams o [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="e7d2f-135">Connettività di rete</span><span class="sxs-lookup"><span data-stu-id="e7d2f-135">Network connectivity</span></span>

<span data-ttu-id="e7d2f-136">Se si prevede di implementare questo [scenario tra tenant,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)potrebbe essere necessaria una licenza information barriers.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="e7d2f-137">Vedere [questo articolo per](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) determinare se è necessaria una licenza information barrier.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="e7d2f-138">Guide di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e7d2f-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="e7d2f-139">Amministrativi</span><span class="sxs-lookup"><span data-stu-id="e7d2f-139">Admin</span></span>

- <span data-ttu-id="e7d2f-140">Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione delle licenze)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="e7d2f-141">Sottoscrizione di Dynamics 365 [Guides o versione di valutazione gratuita](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-141">Dynamics 365 [Guides subscription or free trial](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="e7d2f-142">Autore guide</span><span class="sxs-lookup"><span data-stu-id="e7d2f-142">Guides Author</span></span>

1. <span data-ttu-id="e7d2f-143">Account Azure AD</span><span class="sxs-lookup"><span data-stu-id="e7d2f-143">Azure AD account</span></span>
1. [<span data-ttu-id="e7d2f-144">Dynamics 365 Guides licenza</span><span class="sxs-lookup"><span data-stu-id="e7d2f-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="e7d2f-145">Dynamics 365 Guides'applicazione installata in un PC o in un HoloLens</span><span class="sxs-lookup"><span data-stu-id="e7d2f-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="e7d2f-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (usato per visualizzare il dashboard di Analytics)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="e7d2f-147">Ruolo Autore (per la creazione di guide)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="e7d2f-148">Connettività di rete</span><span class="sxs-lookup"><span data-stu-id="e7d2f-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="e7d2f-149">Guida l'utente</span><span class="sxs-lookup"><span data-stu-id="e7d2f-149">Guides User</span></span>

1. <span data-ttu-id="e7d2f-150">Account Azure AD</span><span class="sxs-lookup"><span data-stu-id="e7d2f-150">Azure AD account</span></span>
1. [<span data-ttu-id="e7d2f-151">Dynamics 365 Guides licenza</span><span class="sxs-lookup"><span data-stu-id="e7d2f-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="e7d2f-152">Dynamics 365 Guides'app installata in un HoloLens</span><span class="sxs-lookup"><span data-stu-id="e7d2f-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="e7d2f-153">Ruolo operatore (per il test o l'uso di guide)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="e7d2f-154">Connettività di rete</span><span class="sxs-lookup"><span data-stu-id="e7d2f-154">Network Connectivity</span></span>
