---
title: Requisiti di licenza
description: ''
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3ac86512755620ebb6159dd4d845b488e203dbad
ms.sourcegitcommit: 238d41844116ab94d347a2ffd0fbfa18b8a81947
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2020
ms.locfileid: "10956762"
---
# <span data-ttu-id="a7a56-102">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="a7a56-102">License requirements</span></span>

## <span data-ttu-id="a7a56-103">Indicazioni sulle licenze di Gestione dei dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="a7a56-103">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="a7a56-104">Se si prevede di gestire i dispositivi HoloLens, saranno necessari Azure AD e un sistema MDM.</span><span class="sxs-lookup"><span data-stu-id="a7a56-104">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="a7a56-105">Active Director (AD) non può essere usato per gestire i dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7a56-105">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="a7a56-106">Se si prevede di usare un sistema MDM diverso da Intune, è necessaria una [licenza di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="a7a56-106">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="a7a56-107">Se si prevede di usare Intune come sistema MDM, [qui](https://docs.microsoft.com/intune/fundamentals/licenses) è riportato un elenco di suite che includono le licenze di Intune.</span><span class="sxs-lookup"><span data-stu-id="a7a56-107">If you plan on using Intune as your MDM,  [here](https://docs.microsoft.com/intune/fundamentals/licenses) are a list of suites that includes Intune licenses.</span></span> **<span data-ttu-id="a7a56-108">Si noti che Azure AD è incluso nella maggior parte delle famiglie di prodotti.</span><span class="sxs-lookup"><span data-stu-id="a7a56-108">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="a7a56-109">Identificare le licenze necessarie per lo scenario e i prodotti</span><span class="sxs-lookup"><span data-stu-id="a7a56-109">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="a7a56-110">Requisiti di licenza di HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="a7a56-110">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="a7a56-111">Potrebbe essere necessario aggiornare il dispositivo HoloLens (prima generazione) a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="a7a56-111">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="a7a56-112">(Per determinare se è necessario eseguire l'aggiornamento, vedere [Funzionalità commerciali di HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions)).</span><span class="sxs-lookup"><span data-stu-id="a7a56-112">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="a7a56-113">In tale caso, si dovranno eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7a56-113">If so, you will need to do the following:</span></span>

- <span data-ttu-id="a7a56-114">Acquistare un file XML di licenza HoloLens Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a7a56-114">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="a7a56-115">Applicare il file XML a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7a56-115">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="a7a56-116">È possibile eseguire questa operazione tramite un [pacchetto di provisioning](hololens-provisioning.md) o tramite il [Gestore di dispositivi mobili](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="a7a56-116">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="a7a56-117">Requisiti di licenza di Remote Assist</span><span class="sxs-lookup"><span data-stu-id="a7a56-117">Remote Assist License Requirements</span></span>

<span data-ttu-id="a7a56-118">Assicurarsi di avere le licenze e i dispositivi necessari.</span><span class="sxs-lookup"><span data-stu-id="a7a56-118">Make sure you have the required licensing and device.</span></span> <span data-ttu-id="a7a56-119">I requisiti di licenza e di prodotto aggiornati sono disponibili [qui](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span><span class="sxs-lookup"><span data-stu-id="a7a56-119">Updated licensing and product requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span></span>

1. [<span data-ttu-id="a7a56-120">Licenza di Remote Assist</span><span class="sxs-lookup"><span data-stu-id="a7a56-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="a7a56-121">Altrimenti, provare la [versione di valutazione di Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="a7a56-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="a7a56-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="a7a56-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="a7a56-123">Licenza di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a7a56-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="a7a56-124">Se si prevede di implementare **[questo scenario tra tenant](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, potrebbe essere necessaria una licenza Barriere informative.</span><span class="sxs-lookup"><span data-stu-id="a7a56-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="a7a56-125">Vedere [questo articolo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) per determinare se è necessaria una licenza Barriere informative.</span><span class="sxs-lookup"><span data-stu-id="a7a56-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="a7a56-126">Guide ai requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="a7a56-126">Guides License Requirements</span></span>

<span data-ttu-id="a7a56-127">I requisiti di licenza e di dispositivo aggiornati sono disponibili [qui](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span><span class="sxs-lookup"><span data-stu-id="a7a56-127">Updated licensing and device requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="a7a56-128">Licenza di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a7a56-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="a7a56-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="a7a56-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="a7a56-130">Guide</span><span class="sxs-lookup"><span data-stu-id="a7a56-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
