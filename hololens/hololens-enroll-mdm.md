---
title: Registrare HoloLens in MDM
description: Informazioni su come iscriversi a HoloLens in gestione di dispositivi mobili (MDM) per semplificare la gestione di più dispositivi.
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
ms.openlocfilehash: b9473f4e80f6438ef4c438711ac0de342c5327e1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283187"
---
# <span data-ttu-id="f41c6-103">Registrare HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="f41c6-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="f41c6-104">Puoi gestire più dispositivi Microsoft HoloLens simultaneamente usando soluzioni come [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="f41c6-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="f41c6-105">Potrai gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f41c6-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="f41c6-106">Vedi [Gestire i dispositivi che eseguono Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), i [provider di servizi di configurazione (CSP) che sono supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e i [criteri supportati da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="f41c6-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="f41c6-107">Gestione di dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e della modalità tutto schermo, è disponibile solo quando [esegui l'aggiornamento a Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f41c6-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="f41c6-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f41c6-108">Requirements</span></span>

 <span data-ttu-id="f41c6-109">L'organizzazione dovrà configurare la gestione di dispositivi mobili (MDM) per la gestione dei dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f41c6-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="f41c6-110">Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.</span><span class="sxs-lookup"><span data-stu-id="f41c6-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="f41c6-111">Diversi modi per iscriversi</span><span class="sxs-lookup"><span data-stu-id="f41c6-111">Different ways to enroll</span></span>

<span data-ttu-id="f41c6-112">A seconda del tipo di identità scelto durante la configurazione OOBE o post-accesso sono disponibili diversi metodi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f41c6-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="f41c6-113">Per altre informazioni su ogni tipo di identità in HoloLens, visitare [Questa pagina](hololens-identity.md).</span><span class="sxs-lookup"><span data-stu-id="f41c6-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="f41c6-114">Se Identity è Azure ad, è possibile che sia durante l'accesso all'app OOBE o **le impostazioni**di  ->  **Access o**il pulsante School  ->  **Connect** .</span><span class="sxs-lookup"><span data-stu-id="f41c6-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="f41c6-115">Per Azure AD, la registrazione automatica MDM si verifica solo se Azure AD è stato configurato con gli URL di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f41c6-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="f41c6-116">Se Identity è Azure AD e Device è stato pre-registrato con il server di Intune MDM con il profilo di configurazione specifico assegnato, quindi Azure AD-Join e la registrazione si verificheranno automaticamente durante la configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="f41c6-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="f41c6-117">Chiamato anche [flusso Autopilot](hololens2-autopilot.md) disponibile in [19041.1103 + Build](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="f41c6-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="f41c6-118">Se l'identità è MSA, usare **le impostazioni**di  ->  **accesso all'app o al pulsante School**  ->  **Connect** .</span><span class="sxs-lookup"><span data-stu-id="f41c6-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="f41c6-119">Denominato anche flusso di Add work account (AWA).</span><span class="sxs-lookup"><span data-stu-id="f41c6-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="f41c6-120">Se l'identità è un utente locale, usare **le impostazioni**  ->  di accesso all'app**o dell'Istituto**  ->  **di istruzione per la registrazione solo in collegamento Gestione dispositivi** .</span><span class="sxs-lookup"><span data-stu-id="f41c6-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="f41c6-121">Chiamata anche flusso di registrazione MDM puro.</span><span class="sxs-lookup"><span data-stu-id="f41c6-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="f41c6-122">Una volta che il dispositivo è stato registrato con il server MDM, l'app Impostazioni rifletterà ora che il dispositivo è registrato in gestione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f41c6-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="f41c6-123">Registrazione automatica in MDM</span><span class="sxs-lookup"><span data-stu-id="f41c6-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="f41c6-124">Se l'organizzazione USA Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token di Azure AD per l'autenticazione (attualmente supportato solo in Microsoft Intune e nell'orologio), l'amministratore IT può configurare Azure AD per consentire automaticamente l'iscrizione a MDM dopo che l'utente ha eseguito l'accesso con il proprio account di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f41c6-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="f41c6-125">Informazioni su come configurare la registrazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f41c6-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="f41c6-126">Quando è abilitata la registrazione automatica, non è necessaria alcuna registrazione manuale aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="f41c6-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="f41c6-127">Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f41c6-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="f41c6-128">Quando un dispositivo è collegato AD Azure AD, può influire su chi ha considerato il [proprietario del dispositivo](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="f41c6-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="f41c6-129">Annullare la registrazione di HoloLens da Intune</span><span class="sxs-lookup"><span data-stu-id="f41c6-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="f41c6-130">Per ulteriori informazioni su come annullare la registrazione di un dispositivo, visitare [Questa pagina](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span><span class="sxs-lookup"><span data-stu-id="f41c6-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
