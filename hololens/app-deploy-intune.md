---
title: Intune e portale aziendale
description: Intune, gestione app, app, portale aziendale, portale
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
ms.openlocfilehash: 7fcd65d5e49fa9cdd771828401749a0a41e50238
ms.sourcegitcommit: d319ac257b9ace484acf5dcfb16c9d4e19ea50a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247218"
---
# <span data-ttu-id="4346a-104">Portale aziendale Intune</span><span class="sxs-lookup"><span data-stu-id="4346a-104">Intune & Company Portal</span></span>

<span data-ttu-id="4346a-105">Con la gestione di dispositivi mobili (MDM), puoi usare le tue app personalizzate tramite [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) per distribuirlo direttamente nei dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4346a-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="4346a-106">Microsoft Intune è un servizio basato su cloud che si occupa di gestione di dispositivi mobili (MDM) e gestione di applicazioni mobili (MAM).</span><span class="sxs-lookup"><span data-stu-id="4346a-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="4346a-107">Intune è incluso nella [famiglia Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)di Microsoft e consente agli utenti di essere produttivi mantenendo i dati dell'organizzazione protetti.</span><span class="sxs-lookup"><span data-stu-id="4346a-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="4346a-108">Per altre informazioni su Intune, vedere [che cos'è Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="4346a-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="4346a-109">Installazione</span><span class="sxs-lookup"><span data-stu-id="4346a-109">Setup</span></span>

1. <span data-ttu-id="4346a-110">Caricare un'app in una riga di business o caricare un'app personalizzata nel tenant di Intune.</span><span class="sxs-lookup"><span data-stu-id="4346a-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="4346a-111">Vedere anche: [gestione delle app Enterprise](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="4346a-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="4346a-112">[Assegna la tua app a un gruppo](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="4346a-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="4346a-113">In base al tipo di assegnazione che scegli puoi far recapitare l'app automaticamente o disponibile per essere facilmente abbattute se hai una selezione di app.</span><span class="sxs-lookup"><span data-stu-id="4346a-113">Based on the assignment type you choose you can have the app delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span> 

> [!NOTE] 
> <span data-ttu-id="4346a-114">Quando crei il tuo bundle appx, assicurati di includere l'architettura per il dispositivo o i dispositivi a cui stai distribuendo.</span><span class="sxs-lookup"><span data-stu-id="4346a-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="4346a-115">HoloLens 2 è ARM64 e HoloLens (1a generazione) è x86.</span><span class="sxs-lookup"><span data-stu-id="4346a-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="4346a-116">Se si prevede di avere un ambiente con dispositivi misti, è possibile includere sia in un singolo bundle di appx.</span><span class="sxs-lookup"><span data-stu-id="4346a-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="4346a-117">Tipi di assegnazione</span><span class="sxs-lookup"><span data-stu-id="4346a-117">Assignment types</span></span>

<span data-ttu-id="4346a-118">Se preferisci che la tua app sia installata automaticamente nel dispositivo dopo l'iscrizione, devi selezionare **obbligatoria** per i gruppi.</span><span class="sxs-lookup"><span data-stu-id="4346a-118">If you prefer your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="4346a-119">Se preferisci rendere la tua app disponibile per il download a quelle iscritte nel portale aziendale, seleziona **disponibile per i dispositivi registrati**.</span><span class="sxs-lookup"><span data-stu-id="4346a-119">If you prefer to make your app available for download to those enrolled through the company portal, select **Available for enrolled devices**.</span></span>


## <span data-ttu-id="4346a-120">Esperienza utente finale</span><span class="sxs-lookup"><span data-stu-id="4346a-120">End User Experience</span></span>

<span data-ttu-id="4346a-121">Dopo aver configurato la configurazione su Intune, è possibile che gli utenti finali ricevano le app selezionate.</span><span class="sxs-lookup"><span data-stu-id="4346a-121">After you have set up configuration on Intune you are ready for end users to recieve your selected apps.</span></span>

<span data-ttu-id="4346a-122">Seguire questa procedura per ottenere automaticamente le app:</span><span class="sxs-lookup"><span data-stu-id="4346a-122">Follow these steps to automatically get your app(s):</span></span>
1. <span data-ttu-id="4346a-123">Registrare il dispositivo con il tenant.</span><span class="sxs-lookup"><span data-stu-id="4346a-123">Enroll your device with your tenant.</span></span> 
2. <span data-ttu-id="4346a-124">Una volta che il dispositivo ha completato la registrazione, dovresti ricevere l'app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4346a-124">Once your device has completed enrollment, you should receive the app on your device.</span></span> 
3. <span data-ttu-id="4346a-125">Se l'app non viene visualizzata immediatamente, passare a account **delle impostazioni**  >  \*\*\*\*  >  **o a School**  >  **paginaaccount** info e scorrere verso il basso per visualizzare le informazioni sullo stato dell'app installata.</span><span class="sxs-lookup"><span data-stu-id="4346a-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > **youraccount** Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="4346a-126">Come passare alle app attraverso il portale aziendale:</span><span class="sxs-lookup"><span data-stu-id="4346a-126">How to get to apps through the Company Portal:</span></span>
1. <span data-ttu-id="4346a-127">Aprire il **menu Start** e selezionare **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="4346a-127">Open the **Start Menu** and select **Microsoft Store**.</span></span> 
2. <span data-ttu-id="4346a-128">Cercare il **portale aziendale** e scaricare l'app.</span><span class="sxs-lookup"><span data-stu-id="4346a-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="4346a-129">Accedere al proprio account.</span><span class="sxs-lookup"><span data-stu-id="4346a-129">Sign into your account.</span></span>
4. <span data-ttu-id="4346a-130">Selezionare l'app che si vuole ricevere e scaricarla.</span><span class="sxs-lookup"><span data-stu-id="4346a-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="4346a-131">Leggi altre informazioni su come [installare automaticamente il portale aziendale](https://docs.microsoft.com/mem/intune/apps/company-portal-app) e [distribuire e gestire le app in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span><span class="sxs-lookup"><span data-stu-id="4346a-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
