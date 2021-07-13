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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635501"
---
# <a name="intune--company-portal"></a><span data-ttu-id="2d473-104">Intune & Portale aziendale</span><span class="sxs-lookup"><span data-stu-id="2d473-104">Intune & Company Portal</span></span>

<span data-ttu-id="2d473-105">Con Gestione dispositivi mobili è possibile usare le proprie app personalizzate [tramite Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) per distribuirla direttamente nei dispositivi HoloLens mobili.</span><span class="sxs-lookup"><span data-stu-id="2d473-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="2d473-106">Microsoft Intune è un servizio basato sul cloud incentrato sulla gestione di dispositivi mobili (MDM, Mobile Device Management) e sulla gestione di applicazioni mobili (MAM, Mobile Application Management).</span><span class="sxs-lookup"><span data-stu-id="2d473-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="2d473-107">Intune è incluso nella [suite Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) di Microsoft e consente agli utenti di essere produttivi garantendo al tempo stesso la protezione dei dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2d473-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="2d473-108">Per altre informazioni su Intune, vedere [Informazioni su Intune.](/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="2d473-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="2d473-109">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2d473-109">Setup</span></span>

1. <span data-ttu-id="2d473-110">Upload un'app in una line-of-business o caricare un'app personalizzata nel tenant di Intune.</span><span class="sxs-lookup"><span data-stu-id="2d473-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="2d473-111">Vedere anche: Gestione [Enterprise app](/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="2d473-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="2d473-112">[Assegnare l'app a un gruppo](/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="2d473-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="2d473-113">In base al tipo di assegnazione scelto, l'app può essere recapitata automaticamente o disponibile per essere prontamente ritirata se si dispone di una selezione di app.</span><span class="sxs-lookup"><span data-stu-id="2d473-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="2d473-114">Quando si compila il bundle appx, assicurarsi di includere l'architettura per i dispositivi in cui si esegue la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2d473-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="2d473-115">HoloLens 2 è ARM64 e HoloLens (prima generazione) è x86.</span><span class="sxs-lookup"><span data-stu-id="2d473-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="2d473-116">È possibile includere entrambi in un singolo bundle appx se si prevede di avere un ambiente con dispositivi misti.</span><span class="sxs-lookup"><span data-stu-id="2d473-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="2d473-117">Tipi di assegnazione</span><span class="sxs-lookup"><span data-stu-id="2d473-117">Assignment types</span></span>

<span data-ttu-id="2d473-118">Per fare in modo che l'app sia installata automaticamente nel dispositivo dopo la registrazione, è necessario selezionare **Obbligatorio** per i gruppi.</span><span class="sxs-lookup"><span data-stu-id="2d473-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="2d473-119">Per rendere disponibile l'app per il download nei dispositivi registrati tramite il portale aziendale, selezionare **Disponibile per i dispositivi registrati.**</span><span class="sxs-lookup"><span data-stu-id="2d473-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="2d473-120">Esperienza dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="2d473-120">End-User Experience</span></span>

<span data-ttu-id="2d473-121">Dopo aver configurato la configurazione in Intune, gli utenti finali possono ricevere le app selezionate.</span><span class="sxs-lookup"><span data-stu-id="2d473-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="2d473-122">Seguire questa procedura per ottenere automaticamente le app:</span><span class="sxs-lookup"><span data-stu-id="2d473-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="2d473-123">Registrare il dispositivo con il tenant.</span><span class="sxs-lookup"><span data-stu-id="2d473-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="2d473-124">Al termine della registrazione del dispositivo, si dovrebbe ricevere l'app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d473-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="2d473-125">Se l'app non viene visualizzata immediatamente, passare **Impostazioni** Accounts Work or School your account Info (Account aziendali o dell'istituto di istruzione) e scorrere verso il basso per visualizzare le informazioni sullo  >    >    >   stato dell'app installata.</span><span class="sxs-lookup"><span data-stu-id="2d473-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="2d473-126">Come accedere alle app tramite il Portale aziendale:</span><span class="sxs-lookup"><span data-stu-id="2d473-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="2d473-127">Aprire il **menu Start e** selezionare **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="2d473-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="2d473-128">Cercare **Portale aziendale** e scaricare l'app.</span><span class="sxs-lookup"><span data-stu-id="2d473-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="2d473-129">Accedere al proprio account.</span><span class="sxs-lookup"><span data-stu-id="2d473-129">Sign into your account.</span></span>
4. <span data-ttu-id="2d473-130">Selezionare l'app che si vuole ricevere e scaricarla.</span><span class="sxs-lookup"><span data-stu-id="2d473-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="2d473-131">Altre informazioni [sull'installazione automatica del Portale aziendale](/mem/intune/apps/company-portal-app) e sulla distribuzione e la gestione delle app in [Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="2d473-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
