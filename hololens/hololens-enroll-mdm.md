---
title: Registrare HoloLens in MDM
description: Registrare HoloLens nella gestione di dispositivi mobili (MDM) per una gestione più semplice di più dispositivi.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828691"
---
# <span data-ttu-id="a62a7-103">Registrare HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="a62a7-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="a62a7-104">Puoi gestire più dispositivi Microsoft HoloLens simultaneamente usando soluzioni come [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="a62a7-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="a62a7-105">Potrai gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a62a7-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="a62a7-106">Vedi [Gestire i dispositivi che eseguono Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), i [provider di servizi di configurazione (CSP) che sono supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e i [criteri supportati da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="a62a7-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="a62a7-107">Gestione di dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e della modalità tutto schermo, è disponibile solo quando [esegui l'aggiornamento a Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a62a7-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="a62a7-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a62a7-108">Requirements</span></span>

 <span data-ttu-id="a62a7-109">L'organizzazione dovrà configurare la gestione di dispositivi mobili (MDM) per la gestione dei dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a62a7-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="a62a7-110">Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.</span><span class="sxs-lookup"><span data-stu-id="a62a7-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>

## <span data-ttu-id="a62a7-111">Registrazione automatica in MDM</span><span class="sxs-lookup"><span data-stu-id="a62a7-111">Auto-enrollment in MDM</span></span>

<span data-ttu-id="a62a7-112">Se l'organizzazione usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token AAD per l'autenticazione (attualmente supportato solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD in modo da consentire automaticamente la registrazione MDM dopo l'accesso dell'utente con l'account Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a62a7-112">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="a62a7-113">Informazioni su come configurare la registrazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a62a7-113">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="a62a7-114">Quando è abilitata la registrazione automatica, non è necessaria alcuna registrazione manuale aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="a62a7-114">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="a62a7-115">Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a62a7-115">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="a62a7-116">Effettuare la registrazione tramite l'app Impostazioni</span><span class="sxs-lookup"><span data-stu-id="a62a7-116">Enroll through Settings app</span></span>

 <span data-ttu-id="a62a7-117">Quando il dispositivo non è registrato in MDM durante l'esperienza di prima esecuzione, l'utente può registrare manualmente il dispositivo con il server MDM dell'organizzazione mediante l'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a62a7-117">When the device is not enrolled in MDM during the first-run experience, the user can manually enroll the device with the organization's MDM server using the Settings app.</span></span>

1. <span data-ttu-id="a62a7-118">Andare a **Impostazioni** > **Account** > **Accesso società**.</span><span class="sxs-lookup"><span data-stu-id="a62a7-118">Go to **Settings** > **Accounts** > **Work access**.</span></span>
1. <span data-ttu-id="a62a7-119">Selezionare **Registrati per la gestione dei dispositivi** e immettere l'account dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a62a7-119">Select **Enroll into device management** and enter your organizational account.</span></span> <span data-ttu-id="a62a7-120">Si verrà reindirizzati nella pagina di accesso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a62a7-120">You will be redirected to your organization's sign in page.</span></span>
1. <span data-ttu-id="a62a7-121">Dopo l'autenticazione riuscita al server MDM, viene visualizzato un messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="a62a7-121">Upon successful authentication to the MDM server, a success message is shown.</span></span>

<span data-ttu-id="a62a7-122">Il dispositivo è ora registrato nel server MDM.</span><span class="sxs-lookup"><span data-stu-id="a62a7-122">Your device is now enrolled with your MDM server.</span></span> <span data-ttu-id="a62a7-123">L'app Impostazioni rifletterà ora la registrazione del dispositivo nella gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a62a7-123">The Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="a62a7-124">Annullare la registrazione di HoloLens da Intune</span><span class="sxs-lookup"><span data-stu-id="a62a7-124">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="a62a7-125">Non puoi [annullare la registrazione](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens da Intune in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="a62a7-125">You cannot [unenroll](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens from Intune remotely.</span></span> <span data-ttu-id="a62a7-126">Se l'amministratore annulla la registrazione del dispositivo tramite MDM, il dispositivo verrà eliminato dal dashboard di Intune.</span><span class="sxs-lookup"><span data-stu-id="a62a7-126">If the administrator unenrolls the device using MDM, the device will age out of the Intune dashboard.</span></span>
