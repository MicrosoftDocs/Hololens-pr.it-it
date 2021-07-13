---
title: Pacchetto di provisioning
description: Informazioni sulla creazione di pacchetti di app, il provisioning, la distribuzione e la distribuzione di app aziendali per HoloLens dispositivi.
keywords: app, distribuzione di app, distribuzione di app aziendali, provisioning
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635518"
---
# <a name="provisioning-package"></a><span data-ttu-id="faa30-104">Pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="faa30-104">Provisioning Package</span></span>

<span data-ttu-id="faa30-105">I pacchetti di provisioning possono essere usati per preparare e configurare i dispositivi in un ambiente senza accesso alla gestione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="faa30-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="faa30-106">Possono anche essere distribuiti in un dispositivo indipendentemente dall'identità dell'utente, dallo stato di registrazione, durante l'esperienza predefinita o applicando un pacchetto di provisioning durante [l'installazione](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)di .</span><span class="sxs-lookup"><span data-stu-id="faa30-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="faa30-107">Considerazioni sul provisioning dei pacchetti:</span><span class="sxs-lookup"><span data-stu-id="faa30-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="faa30-108">App non pubbliche</span><span class="sxs-lookup"><span data-stu-id="faa30-108">Non-Public apps</span></span>
* <span data-ttu-id="faa30-109">Solo caricamento laterale USB</span><span class="sxs-lookup"><span data-stu-id="faa30-109">USB side-load only</span></span>
* <span data-ttu-id="faa30-110">Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite PPKG)</span><span class="sxs-lookup"><span data-stu-id="faa30-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="faa30-111">Le app installate tramite un pacchetto di provisioning devono essere firmate da un certificato nell'archivio del computer locale.</span><span class="sxs-lookup"><span data-stu-id="faa30-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="faa30-112">I pacchetti di provisioning possono installare certificati solo nell'archivio del dispositivo (computer locale), pertanto un'app e un certificato possono essere installati tramite lo stesso pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="faa30-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="faa30-113">Se si distribuisce il certificato da MDM o si esegue l'installazione tramite [Gestione](certificate-manager.md)certificati, assicurarsi di distribuire il certificato nell'archivio computer locale per firmare le app installate in questo modo.</span><span class="sxs-lookup"><span data-stu-id="faa30-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="faa30-114">Per informazioni di base sulla creazione di un pacchetto di provisioning per HoloLens dispositivi, vedere HoloLens [Provisioning](/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="faa30-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](/hololens/hololens-provisioning).</span></span> <span data-ttu-id="faa30-115">Per distribuire un'app, è necessario iniziare con il provisioning avanzato.</span><span class="sxs-lookup"><span data-stu-id="faa30-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="faa30-116">HoloLens (prima generazione) ha un supporto limitato per l'installazione di app (**UniversalAppInstall**) usando un pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="faa30-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="faa30-117">HoloLens (prima generazione) i dispositivi supportano solo l'installazione di un'app tramite PPKG solo durante la configurazione guidata e solo con le installazioni del contesto utente.</span><span class="sxs-lookup"><span data-stu-id="faa30-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="faa30-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="faa30-118">Setup</span></span>

<span data-ttu-id="faa30-119">In [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="faa30-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="faa30-120">Impostare ApplicationManagement/AllowAllTrustedApps su "Sì".</span><span class="sxs-lookup"><span data-stu-id="faa30-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="faa30-121">Vedere: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="faa30-121">See: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="faa30-122">Passare a **UniversalAppInstall**  >  **UserContextAppLicense** immettere **PackageFamilyName.**</span><span class="sxs-lookup"><span data-stu-id="faa30-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="faa30-123">Vedere [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="faa30-123">See [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="faa30-124">Vedere anche: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="faa30-124">See also: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="faa30-125">È possibile usare Portale di dispositivi in un dispositivo in cui è già installata l'app.</span><span class="sxs-lookup"><span data-stu-id="faa30-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="faa30-126">Visitare la pagina App e esaminare la riga PackageRelativeID, tutte le informazioni prima di "!" **PackageFamilyName** è .</span><span class="sxs-lookup"><span data-stu-id="faa30-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="faa30-127">Si noti quindi che è presente una nuova sezione, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="faa30-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="faa30-128">Usare questa area per caricare il bundle appx.</span><span class="sxs-lookup"><span data-stu-id="faa30-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="faa30-129">A seconda che l'app sia stata acquistata o creata una propria app LOB, sarà necessario caricare il file di licenza o il certificato di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="faa30-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="faa30-130">Per il file di licenza: passare a **UniversalAppInstall**  >  **UserContextAppLicence** e passare al percorso della licenza e caricarlo.</span><span class="sxs-lookup"><span data-stu-id="faa30-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="faa30-131">Per il file di sicurezza, passare a **Certificati** e selezionare il certificato da installare insieme al bundle .appx.</span><span class="sxs-lookup"><span data-stu-id="faa30-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="faa30-132">Assicurarsi di salvare il progetto in un percorso sicuro.</span><span class="sxs-lookup"><span data-stu-id="faa30-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="faa30-133">Esportarlo come pacchetto **di provisioning.** </span><span class="sxs-lookup"><span data-stu-id="faa30-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="faa30-134">Vedere anche: [Applicare il pacchetto di provisioning HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="faa30-134">See also: [Apply your provisioning package to HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
