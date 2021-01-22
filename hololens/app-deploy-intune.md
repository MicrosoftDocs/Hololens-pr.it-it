---
title: Intune e portale aziendale
description: Informazioni su come configurare, assegnare e creare un'esperienza utente comoda con Intune, gestione di dispositivi mobili e il portale aziendale.
keywords: Intune, gestione app, app, portale aziendale, portale, hololens
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283717"
---
# <span data-ttu-id="60d04-104">Portale aziendale Intune</span><span class="sxs-lookup"><span data-stu-id="60d04-104">Intune & Company Portal</span></span>

<span data-ttu-id="60d04-105">Con la gestione di dispositivi mobili (MDM), puoi usare le tue app personalizzate tramite [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) per distribuirlo direttamente nei dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="60d04-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="60d04-106">Microsoft Intune è un servizio basato su cloud che si occupa di gestione di dispositivi mobili (MDM) e gestione di applicazioni mobili (MAM).</span><span class="sxs-lookup"><span data-stu-id="60d04-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="60d04-107">Intune è incluso nella [famiglia Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)di Microsoft e consente agli utenti di essere produttivi mantenendo i dati dell'organizzazione protetti.</span><span class="sxs-lookup"><span data-stu-id="60d04-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="60d04-108">Per altre informazioni su Intune, vedere [che cos'è Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="60d04-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="60d04-109">Installazione</span><span class="sxs-lookup"><span data-stu-id="60d04-109">Setup</span></span>

1. <span data-ttu-id="60d04-110">Caricare un'app in una riga di business o caricare un'app personalizzata nel tenant di Intune.</span><span class="sxs-lookup"><span data-stu-id="60d04-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="60d04-111">Vedere anche: [gestione delle app Enterprise](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="60d04-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="60d04-112">[Assegna la tua app a un gruppo](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="60d04-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="60d04-113">In base al tipo di attività che scegli, l'app può essere recapitata automaticamente o disponibile per essere facilmente abbattute se hai una selezione di app.</span><span class="sxs-lookup"><span data-stu-id="60d04-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="60d04-114">Quando crei il tuo bundle appx, assicurati di includere l'architettura per il dispositivo o i dispositivi a cui stai distribuendo.</span><span class="sxs-lookup"><span data-stu-id="60d04-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="60d04-115">HoloLens 2 è ARM64 e HoloLens (1a generazione) è x86.</span><span class="sxs-lookup"><span data-stu-id="60d04-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="60d04-116">Se si prevede di avere un ambiente con dispositivi misti, è possibile includere sia in un singolo bundle di appx.</span><span class="sxs-lookup"><span data-stu-id="60d04-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="60d04-117">Tipi di assegnazione</span><span class="sxs-lookup"><span data-stu-id="60d04-117">Assignment types</span></span>

<span data-ttu-id="60d04-118">Per installare automaticamente la tua app nel dispositivo dopo la registrazione, devi selezionare **obbligatoria** per i gruppi...</span><span class="sxs-lookup"><span data-stu-id="60d04-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="60d04-119">Per rendere la tua app disponibile per il download nei dispositivi registrati tramite il portale aziendale, seleziona **disponibile per i dispositivi registrati**.</span><span class="sxs-lookup"><span data-stu-id="60d04-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <span data-ttu-id="60d04-120">End-User esperienza</span><span class="sxs-lookup"><span data-stu-id="60d04-120">End-User Experience</span></span>

<span data-ttu-id="60d04-121">Dopo aver configurato la configurazione in Intune, si è pronti per gli utenti finali a ricevere le app selezionate.</span><span class="sxs-lookup"><span data-stu-id="60d04-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="60d04-122">Seguire questa procedura per ottenere automaticamente le app:</span><span class="sxs-lookup"><span data-stu-id="60d04-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="60d04-123">Registrare il dispositivo con il tenant.</span><span class="sxs-lookup"><span data-stu-id="60d04-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="60d04-124">Una volta che il dispositivo ha completato la registrazione, dovresti ricevere l'app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60d04-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="60d04-125">Se l'app non viene visualizzata immediatamente, passare a account **delle impostazioni**  >  \*\*\*\*  >  **o a scuola**  >  *le informazioni dell'account* e scorrere verso il basso per visualizzare le informazioni sullo stato dell'app installata.</span><span class="sxs-lookup"><span data-stu-id="60d04-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="60d04-126">Come passare alle app attraverso il portale aziendale:</span><span class="sxs-lookup"><span data-stu-id="60d04-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="60d04-127">Aprire il **menu Start** e selezionare **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="60d04-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="60d04-128">Cercare il **portale aziendale** e scaricare l'app.</span><span class="sxs-lookup"><span data-stu-id="60d04-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="60d04-129">Accedere al proprio account.</span><span class="sxs-lookup"><span data-stu-id="60d04-129">Sign into your account.</span></span>
4. <span data-ttu-id="60d04-130">Selezionare l'app che si vuole ricevere e scaricarla.</span><span class="sxs-lookup"><span data-stu-id="60d04-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="60d04-131">Leggi altre informazioni su come [installare automaticamente il portale aziendale](https://docs.microsoft.com/mem/intune/apps/company-portal-app) e [distribuire e gestire le app in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span><span class="sxs-lookup"><span data-stu-id="60d04-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
