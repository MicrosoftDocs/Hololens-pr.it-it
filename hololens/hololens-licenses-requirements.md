---
title: Requisiti di licenza
description: È importante tenersi sempre aggiornati sui requisiti di licenza e sulle linee guida necessarie per la gestione di dispositivi mobili, HoloLens e assistenza remota.
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
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283967"
---
# <span data-ttu-id="83d5b-103">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="83d5b-103">License requirements</span></span>

## <span data-ttu-id="83d5b-104">Indicazioni sulle licenze di Gestione dei dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="83d5b-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="83d5b-105">Se si prevede di gestire i dispositivi HoloLens, saranno necessari Azure AD e un sistema MDM.</span><span class="sxs-lookup"><span data-stu-id="83d5b-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="83d5b-106">Active Director (AD) non può essere usato per gestire i dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83d5b-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="83d5b-107">Se si prevede di usare un sistema MDM diverso da Intune, è necessaria una [licenza di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="83d5b-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="83d5b-108">Se si prevede di usare Intune come MDM, leggere l'[elenco delle suite](https://docs.microsoft.com/intune/fundamentals/licenses) che includono le licenze di Intune.</span><span class="sxs-lookup"><span data-stu-id="83d5b-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> **<span data-ttu-id="83d5b-109">Si noti che Azure AD è incluso nella maggior parte delle famiglie di prodotti.</span><span class="sxs-lookup"><span data-stu-id="83d5b-109">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="83d5b-110">Identificare le licenze necessarie per lo scenario e i prodotti</span><span class="sxs-lookup"><span data-stu-id="83d5b-110">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="83d5b-111">Requisiti di licenza di HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="83d5b-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="83d5b-112">Potrebbe essere necessario aggiornare il dispositivo HoloLens (prima generazione) a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="83d5b-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="83d5b-113">(Per determinare se è necessario eseguire l'aggiornamento, vedere [Funzionalità commerciali di HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions)).</span><span class="sxs-lookup"><span data-stu-id="83d5b-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="83d5b-114">In tale caso, si dovranno eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83d5b-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="83d5b-115">Acquistare un file XML di licenza HoloLens Enterprise.</span><span class="sxs-lookup"><span data-stu-id="83d5b-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="83d5b-116">Applicare il file XML a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83d5b-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="83d5b-117">È possibile eseguire questa operazione tramite un [pacchetto di provisioning](hololens-provisioning.md) o tramite il [Gestore di dispositivi mobili](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="83d5b-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="83d5b-118">Requisiti di licenza di Remote Assist</span><span class="sxs-lookup"><span data-stu-id="83d5b-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="83d5b-119">Verificare di disporre della licenza e del dispositivo necessari nella documentazione relativa ai [requisiti](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span><span class="sxs-lookup"><span data-stu-id="83d5b-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="83d5b-120">Licenza di Remote Assist</span><span class="sxs-lookup"><span data-stu-id="83d5b-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="83d5b-121">Altrimenti, provare la [versione di valutazione di Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="83d5b-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="83d5b-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="83d5b-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="83d5b-123">Licenza di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="83d5b-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="83d5b-124">Se si prevede di implementare **[questo scenario tra tenant](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, potrebbe essere necessaria una licenza Barriere informative.</span><span class="sxs-lookup"><span data-stu-id="83d5b-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="83d5b-125">Vedere [questo articolo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) per determinare se è necessaria una licenza Barriere informative.</span><span class="sxs-lookup"><span data-stu-id="83d5b-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="83d5b-126">Guide ai requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="83d5b-126">Guides License Requirements</span></span>

<span data-ttu-id="83d5b-127">Verificare i [requisiti di licenze e dispositivi aggiornati](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span><span class="sxs-lookup"><span data-stu-id="83d5b-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="83d5b-128">Licenza di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="83d5b-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="83d5b-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="83d5b-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="83d5b-130">Guide</span><span class="sxs-lookup"><span data-stu-id="83d5b-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
