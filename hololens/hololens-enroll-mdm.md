---
title: Registrare HoloLens in MDM
description: Informazioni su come registrare HoloLens nella gestione di dispositivi mobili (MDM) per semplificare la gestione di più dispositivi.
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
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640407"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="ddd1e-103">Registrare HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="ddd1e-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="ddd1e-104">È possibile gestire più Microsoft HoloLens contemporaneamente usando soluzioni come [Microsoft Intune](/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="ddd1e-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="ddd1e-105">Sarà possibile gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="ddd1e-106">Vedere Gestire i dispositivi che eseguono [Windows Holographic](/intune/windows-holographic-for-business)con Microsoft Intune , i provider di servizi di configurazione [supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)e i criteri supportati [da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="ddd1e-106">See [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="ddd1e-107">La gestione dei dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e in modalità tutto schermo, è disponibile solo quando si esegue l'aggiornamento [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ddd1e-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="ddd1e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ddd1e-108">Requirements</span></span>

 <span data-ttu-id="ddd1e-109">L'organizzazione dovrà avere la gestione dei dispositivi mobili (MDM) impostata per gestire i HoloLens mobili.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="ddd1e-110">Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="ddd1e-111">Diversi modi per eseguire la registrazione</span><span class="sxs-lookup"><span data-stu-id="ddd1e-111">Different ways to enroll</span></span>

<span data-ttu-id="ddd1e-112">A seconda del tipo di [identità](hololens-identity.md) scelto durante la Procedura guidata o dopo l'accesso, esistono diversi metodi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="ddd1e-113">Se l'opzione Identità è Azure AD, durante la Impostazioni o **l'accesso all'app** il Connessione aziendale  ->    ->  **o dell'istituto di** istruzione.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="ddd1e-114">Ad Azure AD, [la registrazione MDM automatica](hololens-enroll-mdm.md#auto-enrollment-in-mdm) viene eseguita solo se Azure AD è stato configurato con gli URL di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="ddd1e-115">Se l'identità è Azure AD e il dispositivo è stato preregistrato con il server MDM di Intune con un profilo di configurazione specifico assegnato, durante la configurazione guidata verrà eseguita la registrazione automatica di Azure AD-Join [e MDM.](hololens-enroll-mdm.md#auto-enrollment-in-mdm)</span><span class="sxs-lookup"><span data-stu-id="ddd1e-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="ddd1e-116">Chiamato anche [Flusso di Autopilot](hololens2-autopilot.md) disponibile nelle [build 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="ddd1e-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="ddd1e-117">Se Identity è MSA, usare il pulsante Impostazioni App Access Work or School (Accesso **all'app** aziendale  ->    ->  **Connessione dell'istituto di** istruzione).</span><span class="sxs-lookup"><span data-stu-id="ddd1e-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="ddd1e-118">Chiamato anche flusso Add Work Account (AWA).</span><span class="sxs-lookup"><span data-stu-id="ddd1e-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="ddd1e-119">Se Identity è Local User (Identità) è Local User (Utente locale), Impostazioni collegamento App Access Work or School Enroll only in device management (Registra solo per l'accesso **all'app** o all'istituto di  ->    ->  **istruzione) nel collegamento di gestione dei** dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="ddd1e-120">Chiamato anche flusso di registrazione MDM puro.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="ddd1e-121">Dopo aver registrato il dispositivo nel server MDM, l'app Impostazioni rifletterà che il dispositivo è registrato nella gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="ddd1e-122">Registrazione automatica in MDM</span><span class="sxs-lookup"><span data-stu-id="ddd1e-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="ddd1e-123">Se l'organizzazione ha una sottoscrizione di [Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token Azure AD per l'autenticazione (attualmente supportata solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD per consentire automaticamente la registrazione MDM dopo che l'utente accede con il proprio account Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="ddd1e-124">Informazioni su come configurare la registrazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-124">Learn how to configure Azure AD enrollment.</span></span>](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="ddd1e-125">Quando la registrazione automatica è abilitata, non è necessaria alcuna registrazione manuale aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="ddd1e-126">Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="ddd1e-127">Quando un dispositivo viene aggiunto Azure AD potrebbe influire su chi ha considerato il [proprietario del dispositivo.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="ddd1e-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="ddd1e-128">Annullare la registrazione HoloLens da Intune</span><span class="sxs-lookup"><span data-stu-id="ddd1e-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="ddd1e-129">A seconda del metodo di registrazione, l'annullamento della registrazione del dispositivo potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="ddd1e-130">Se il dispositivo è stato registrato con un account Azure AD o Autopilot, non è possibile annullarlo da Intune.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="ddd1e-131">Se si vuole annullare l'HoloLens da Azure AD o ricongiungerlo a un tenant diverso da Azure AD, è necessario [reimpostare/ripristinare](hololens-recovery.md#reset-the-device) il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](hololens-recovery.md#reset-the-device) the device.</span></span>

<span data-ttu-id="ddd1e-132">Se il dispositivo è stato registrato da un account msa che ha aggiunto un account aziendale o da un account locale registrato solo nella gestione dei dispositivi, è possibile annullare la registrazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ddd1e-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="ddd1e-133">Aprire il menu Start e quindi selezionare il Impostazioni **App**  ->  **Access Work or School**  ->  YourAccount Disconnect *(Disconnetti* account personale o dell'istituto  ->  **di** istruzione).</span><span class="sxs-lookup"><span data-stu-id="ddd1e-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>