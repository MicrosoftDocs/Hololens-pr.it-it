---
title: Registrare HoloLens in MDM
description: Scopri come registrare HoloLens nella gestione di dispositivi mobili (MDM) per una gestione più semplice di più dispositivi.
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
ms.openlocfilehash: 4042cce40bea2c3d52d6ffc5d2908f6fde7cf222
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400676"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="78d20-103">Registrare HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="78d20-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="78d20-104">Puoi gestire più dispositivi Microsoft HoloLens contemporaneamente usando soluzioni come [Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business)</span><span class="sxs-lookup"><span data-stu-id="78d20-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="78d20-105">Potrai gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78d20-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="78d20-106">Vedi [Gestire i dispositivi che eseguono Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), i [provider di servizi di configurazione (CSP) che sono supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e i [criteri supportati da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="78d20-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="78d20-107">Gestione di dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e della modalità tutto schermo, è disponibile solo quando [esegui l'aggiornamento a Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="78d20-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="78d20-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78d20-108">Requirements</span></span>

 <span data-ttu-id="78d20-109">Per gestire i dispositivi HoloLens, l'organizzazione dovrà configurare Gestione di dispositivi mobili (MDM, Mobile Device Management).</span><span class="sxs-lookup"><span data-stu-id="78d20-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="78d20-110">Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.</span><span class="sxs-lookup"><span data-stu-id="78d20-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="78d20-111">Diversi modi per eseguire la registrazione</span><span class="sxs-lookup"><span data-stu-id="78d20-111">Different ways to enroll</span></span>

<span data-ttu-id="78d20-112">A seconda del tipo di [identità](hololens-identity.md) scelto durante la Procedura guidata o dopo l'accesso, esistono diversi metodi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="78d20-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="78d20-113">Se l'identità è Azure AD, allora durante la configurazione predefinita o il pulsante **Impostazioni accesso app**lavoro o  ->  **School**  ->  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="78d20-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="78d20-114">Per Azure AD, [la registrazione automatica di MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) si verifica solo se Azure AD è stato configurato con gli URL di registrazione.</span><span class="sxs-lookup"><span data-stu-id="78d20-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span> 
     
- <span data-ttu-id="78d20-115">Se l'identità è Azure AD e il dispositivo è stato preregistrato con il server MDM intune a cui è assegnato un profilo di configurazione specifico, Azure AD-Join e la registrazione [automatica di MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) verrà eseguita durante la configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="78d20-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="78d20-116">Denominato anche [flusso Autopilot](hololens2-autopilot.md) disponibile nelle [build 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="78d20-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="78d20-117">Se l'identità è MSA, usa il pulsante Impostazioni **accesso app**lavoro  ->  **o School**  ->  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="78d20-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="78d20-118">Denominato anche flusso Add Work Account (AWA).</span><span class="sxs-lookup"><span data-stu-id="78d20-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="78d20-119">Se l'identità è Utente locale, usare Impostazioni **accesso app**Lavoro o  ->  **Iscrizione**  ->  **all'istituto di istruzione solo nel collegamento di gestione dei** dispositivi.</span><span class="sxs-lookup"><span data-stu-id="78d20-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="78d20-120">Chiamato anche flusso di registrazione MDM pura.</span><span class="sxs-lookup"><span data-stu-id="78d20-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="78d20-121">Dopo la registrazione del dispositivo con il server MDM, l'app Impostazioni rifletterà che il dispositivo è registrato nella gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="78d20-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="78d20-122">Registrazione automatica in MDM</span><span class="sxs-lookup"><span data-stu-id="78d20-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="78d20-123">Se l'organizzazione ha una sottoscrizione [di Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token Azure AD per l'autenticazione (attualmente supportato solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD per consentire automaticamente la registrazione MDM dopo l'accesso dell'utente con il proprio account Azure AD.</span><span class="sxs-lookup"><span data-stu-id="78d20-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="78d20-124">Informazioni su come configurare la registrazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="78d20-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="78d20-125">Quando è abilitata la registrazione automatica, non è necessaria alcuna registrazione manuale aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="78d20-125">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="78d20-126">Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="78d20-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="78d20-127">Quando un dispositivo è aggiunto ad Azure AD, può influire su chi considera il proprietario [del dispositivo.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="78d20-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="78d20-128">Annullare la registrazione di HoloLens da Intune</span><span class="sxs-lookup"><span data-stu-id="78d20-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="78d20-129">Anche se HoloLens 2 è un dispositivo Windows 10, non può essere semplicemente rimosso da Intune.</span><span class="sxs-lookup"><span data-stu-id="78d20-129">Although HoloLens 2 is Windows 10 device, it cannot be simply unenrolled from Intune.</span></span> <span data-ttu-id="78d20-130">Se vuoi scollegare HoloLens da Azure AD o ricongiungerlo a un [](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) tenant diverso da quello di Azure AD, devi reimpostare/riequiliminare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="78d20-130">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>