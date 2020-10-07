---
title: Enroll HoloLens in MDM
description: Enroll HoloLens in mobile device management (MDM) for easier management of multiple devices.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5adc1b48c4603f3a9d3145bef4f1d8aa1867a9d1
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102325"
---
# <span data-ttu-id="d9486-103">Enroll HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="d9486-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="d9486-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="d9486-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="d9486-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span><span class="sxs-lookup"><span data-stu-id="d9486-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="d9486-106">Vedi [Gestire i dispositivi che eseguono Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), i [provider di servizi di configurazione (CSP) che sono supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e i [criteri supportati da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="d9486-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="d9486-107">Gestione di dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e della modalità tutto schermo, è disponibile solo quando [esegui l'aggiornamento a Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d9486-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="d9486-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="d9486-108">Requirements</span></span>

 <span data-ttu-id="d9486-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span><span class="sxs-lookup"><span data-stu-id="d9486-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="d9486-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span><span class="sxs-lookup"><span data-stu-id="d9486-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="d9486-111">Different ways to enroll</span><span class="sxs-lookup"><span data-stu-id="d9486-111">Different ways to enroll</span></span>

<span data-ttu-id="d9486-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span><span class="sxs-lookup"><span data-stu-id="d9486-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="d9486-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span><span class="sxs-lookup"><span data-stu-id="d9486-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="d9486-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span><span class="sxs-lookup"><span data-stu-id="d9486-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="d9486-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span><span class="sxs-lookup"><span data-stu-id="d9486-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="d9486-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span><span class="sxs-lookup"><span data-stu-id="d9486-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="d9486-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="d9486-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="d9486-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span><span class="sxs-lookup"><span data-stu-id="d9486-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="d9486-119">Also called Add Work Account (AWA) flow.</span><span class="sxs-lookup"><span data-stu-id="d9486-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="d9486-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span><span class="sxs-lookup"><span data-stu-id="d9486-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="d9486-121">Also called pure MDM enrollment flow.</span><span class="sxs-lookup"><span data-stu-id="d9486-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="d9486-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span><span class="sxs-lookup"><span data-stu-id="d9486-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="d9486-123">Auto-enrollment in MDM</span><span class="sxs-lookup"><span data-stu-id="d9486-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="d9486-124">Se l'organizzazione usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token AAD per l'autenticazione (attualmente supportato solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD in modo da consentire automaticamente la registrazione MDM dopo l'accesso dell'utente con l'account Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d9486-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="d9486-125">Informazioni su come configurare la registrazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d9486-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="d9486-126">Quando è abilitata la registrazione automatica, non è necessaria alcuna registrazione manuale aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d9486-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="d9486-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span><span class="sxs-lookup"><span data-stu-id="d9486-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="d9486-128">When a device is AAD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="d9486-128">When a device is AAD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="d9486-129">Unenroll HoloLens from Intune</span><span class="sxs-lookup"><span data-stu-id="d9486-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="d9486-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span><span class="sxs-lookup"><span data-stu-id="d9486-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
