---
title: Pacchetto di provisioning
description: app, distribuzione di app, demployment dell'app Enterprise, provisioning
keywords: app, distribuzione di app, demployment dell'app Enterprise, provisioning
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0803b5f1b77ac7f123d534d101cd24903b87094c
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052583"
---
# <span data-ttu-id="9058f-104">Pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="9058f-104">Provisioning Package</span></span>

<span data-ttu-id="9058f-105">I pacchetti di provisioning possono essere usati per preparare e configurare i dispositivi in un ambiente senza accedere alla gestione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="9058f-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="9058f-106">Possono anche essere distribuiti in un dispositivo indipendentemente dall'identità dell'utente, dallo stato di registrazione, durante l'esperienza fuori sede (OOBE) o [applicando un pacchetto di provisioning durante l'installazione](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="9058f-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="9058f-107">Considerazioni sul provisioning di pacchetti:</span><span class="sxs-lookup"><span data-stu-id="9058f-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="9058f-108">App non pubbliche</span><span class="sxs-lookup"><span data-stu-id="9058f-108">Non-Public apps</span></span>
* <span data-ttu-id="9058f-109">Solo caricamento laterale USB</span><span class="sxs-lookup"><span data-stu-id="9058f-109">USB side-load only</span></span>
* <span data-ttu-id="9058f-110">Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite PPKGs)</span><span class="sxs-lookup"><span data-stu-id="9058f-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="9058f-111">Per informazioni sulle nozioni di base sulla creazione di un pacchetto di provisioning per i dispositivi HoloLens, visitare il [provisioning di HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="9058f-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="9058f-112">Per distribuire un'app, devi iniziare con il provisioning avanzato.</span><span class="sxs-lookup"><span data-stu-id="9058f-112">To deploy an app, you must start with advanced provisioning.</span></span> 

> [!NOTE] 
> <span data-ttu-id="9058f-113">HoloLens (1a generazione) ha un supporto limitato per l'installazione di app (**UniversalAppInstall**) usando un pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="9058f-113">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="9058f-114">I dispositivi HoloLens (1a Gen) supportano solo l'installazione di un'app tramite PPKG solo durante la configurazione guidata e solo con le installazioni di contesto utente.</span><span class="sxs-lookup"><span data-stu-id="9058f-114">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="9058f-115">Installazione</span><span class="sxs-lookup"><span data-stu-id="9058f-115">Setup</span></span>

<span data-ttu-id="9058f-116">In [Windows Configuration designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) seguire 4 passaggi.</span><span class="sxs-lookup"><span data-stu-id="9058f-116">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="9058f-117">Impostare ApplicationManagement/AllowAllTrustedApps su "Sì".</span><span class="sxs-lookup"><span data-stu-id="9058f-117">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="9058f-118">Vedere: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="9058f-118">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="9058f-119">In **UniversalAppInstall**  >  **UserContextAppLicense** immettere il **packageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="9058f-119">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="9058f-120">Vedere [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="9058f-120">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="9058f-121">Vedere anche: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="9058f-121">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="9058f-122">Se non si conosce questa operazione, è possibile usare Device Portal in un dispositivo a cui è già stata installata l'app.</span><span class="sxs-lookup"><span data-stu-id="9058f-122">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="9058f-123">Visita la pagina delle app e guarda la linea PackageRelativeID, tutte le informazioni prima del "!" È il **packageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="9058f-123">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="9058f-124">Si vedrà quindi che si ha una nuova sezione, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="9058f-124">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="9058f-125">Usare questa area per caricare il bundle di appx.</span><span class="sxs-lookup"><span data-stu-id="9058f-125">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="9058f-126">A seconda di se l'app è stata acquistata o è stata creata una propria app LOB, sarà necessario caricare il file di licenza o il certificato di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9058f-126">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="9058f-127">Per il file di licenza: in **UniversalAppInstall**  >  **UserContextAppLience** e passare al percorso della licenza e caricarlo.</span><span class="sxs-lookup"><span data-stu-id="9058f-127">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="9058f-128">Per file di sicurezza, passare a **certificati** e selezionare il certificato da installare insieme al bundle. appx.</span><span class="sxs-lookup"><span data-stu-id="9058f-128">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="9058f-129">Assicurarsi di salvare il progetto in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="9058f-129">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="9058f-130">Quindi **esportalo** come **pacchetto di provisioning**.</span><span class="sxs-lookup"><span data-stu-id="9058f-130">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="9058f-131">Vedere anche: [applicare il pacchetto provisiong a HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="9058f-131">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
