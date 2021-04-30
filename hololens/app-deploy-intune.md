---
title: Intune e Portale aziendale
description: Informazioni su come configurare, assegnare e creare un'esperienza utente comoda con Intune, la gestione dei dispositivi mobili e il portale aziendale.
keywords: intune, gestione delle app, app, portale aziendale, portale, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309732"
---
# <a name="intune--company-portal"></a><span data-ttu-id="99c7e-104">Intune & Portale aziendale</span><span class="sxs-lookup"><span data-stu-id="99c7e-104">Intune & Company Portal</span></span>

<span data-ttu-id="99c7e-105">Con Gestione dispositivi mobili è possibile usare le proprie app personalizzate tramite [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) per distribuirla direttamente nei dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="99c7e-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="99c7e-106">Microsoft Intune è un servizio basato sul cloud incentrato sulla gestione di dispositivi mobili (MDM, Mobile Device Management) e sulla gestione di applicazioni mobili (MAM, Mobile Application Management).</span><span class="sxs-lookup"><span data-stu-id="99c7e-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="99c7e-107">Intune è incluso nella [suite Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) di Microsoft e consente agli utenti di essere produttivi garantendo al tempo stesso la protezione dei dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="99c7e-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="99c7e-108">Per altre informazioni su Intune, vedere [Informazioni su Intune.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="99c7e-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="99c7e-109">Configurazione</span><span class="sxs-lookup"><span data-stu-id="99c7e-109">Setup</span></span>

1. <span data-ttu-id="99c7e-110">Caricare un'app in una line-of-business o caricare un'app personalizzata nel tenant di Intune.</span><span class="sxs-lookup"><span data-stu-id="99c7e-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="99c7e-111">Vedere anche: [Gestione delle app aziendali.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="99c7e-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="99c7e-112">[Assegnare l'app a un gruppo](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="99c7e-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="99c7e-113">In base al tipo di assegnazione scelto, l'app può essere recapitata automaticamente o disponibile per essere prontamente ritirata se si dispone di una selezione di app.</span><span class="sxs-lookup"><span data-stu-id="99c7e-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="99c7e-114">Quando si compila il bundle appx, assicurarsi di includere l'architettura per i dispositivi in cui si esegue la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="99c7e-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="99c7e-115">HoloLens 2 è ARM64 e HoloLens (prima generazione) è x86.</span><span class="sxs-lookup"><span data-stu-id="99c7e-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="99c7e-116">È possibile includere entrambi in un singolo bundle appx se si prevede di avere un ambiente con dispositivi misti.</span><span class="sxs-lookup"><span data-stu-id="99c7e-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="99c7e-117">Tipi di assegnazione</span><span class="sxs-lookup"><span data-stu-id="99c7e-117">Assignment types</span></span>

<span data-ttu-id="99c7e-118">Per fare in modo che l'app sia installata automaticamente nel dispositivo dopo la registrazione, è necessario selezionare **Obbligatorio** per i gruppi.</span><span class="sxs-lookup"><span data-stu-id="99c7e-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="99c7e-119">Per rendere disponibile l'app per il download nei dispositivi registrati tramite il portale aziendale, selezionare **Disponibile per i dispositivi registrati.**</span><span class="sxs-lookup"><span data-stu-id="99c7e-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="99c7e-120">Esperienza dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="99c7e-120">End-User Experience</span></span>

<span data-ttu-id="99c7e-121">Dopo aver configurato la configurazione in Intune, si è pronti per consentire agli utenti finali di ricevere le app selezionate.</span><span class="sxs-lookup"><span data-stu-id="99c7e-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="99c7e-122">Seguire questa procedura per ottenere automaticamente le app:</span><span class="sxs-lookup"><span data-stu-id="99c7e-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="99c7e-123">Registrare il dispositivo con il tenant.</span><span class="sxs-lookup"><span data-stu-id="99c7e-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="99c7e-124">Al termine della registrazione del dispositivo, si dovrebbe ricevere l'app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99c7e-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="99c7e-125">Se l'app non viene visualizzata immediatamente, passare a Impostazioni Account aziendali o dell'istituto di istruzione Informazioni sull'account e scorrere verso il basso per visualizzare informazioni sullo  >    >    >   stato dell'app installata.</span><span class="sxs-lookup"><span data-stu-id="99c7e-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="99c7e-126">Come accedere alle app tramite il Portale aziendale:</span><span class="sxs-lookup"><span data-stu-id="99c7e-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="99c7e-127">Aprire il **menu Start e** selezionare **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="99c7e-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="99c7e-128">Cercare **Portale aziendale** e scaricare l'app.</span><span class="sxs-lookup"><span data-stu-id="99c7e-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="99c7e-129">Accedere al proprio account.</span><span class="sxs-lookup"><span data-stu-id="99c7e-129">Sign into your account.</span></span>
4. <span data-ttu-id="99c7e-130">Selezionare l'app che si vuole ricevere e scaricarla.</span><span class="sxs-lookup"><span data-stu-id="99c7e-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="99c7e-131">Altre informazioni [sull'installazione automatica del Portale aziendale](https://docs.microsoft.com/mem/intune/apps/company-portal-app) distribuzione e gestione delle app in [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="99c7e-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
