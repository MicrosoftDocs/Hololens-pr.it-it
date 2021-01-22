---
title: Pacchetto di provisioning
description: Informazioni su come creare pacchetti di app, provisioning, distribuzione e distribuzione di app Enterprise per dispositivi HoloLens.
keywords: app, distribuzione di app, distribuzione di app Enterprise, provisioning
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283697"
---
# <span data-ttu-id="7c74c-104">Pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="7c74c-104">Provisioning Package</span></span>

<span data-ttu-id="7c74c-105">I pacchetti di provisioning possono essere usati per preparare e configurare i dispositivi in un ambiente senza accedere alla gestione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="7c74c-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="7c74c-106">Possono anche essere distribuiti in un dispositivo indipendentemente dall'identità dell'utente, dallo stato di registrazione, durante l'esperienza fuori sede (OOBE) o [applicando un pacchetto di provisioning durante l'installazione](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="7c74c-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="7c74c-107">Considerazioni sul provisioning di pacchetti:</span><span class="sxs-lookup"><span data-stu-id="7c74c-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="7c74c-108">App non pubbliche</span><span class="sxs-lookup"><span data-stu-id="7c74c-108">Non-Public apps</span></span>
* <span data-ttu-id="7c74c-109">Solo caricamento laterale USB</span><span class="sxs-lookup"><span data-stu-id="7c74c-109">USB side-load only</span></span>
* <span data-ttu-id="7c74c-110">Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite PPKGs)</span><span class="sxs-lookup"><span data-stu-id="7c74c-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="7c74c-111">Le app installate tramite un pacchetto di provisioning devono essere firmate da un certificato nell'archivio del computer locale.</span><span class="sxs-lookup"><span data-stu-id="7c74c-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="7c74c-112">Il provisioning dei pacchetti può installare solo i certificati nello Store del dispositivo (computer locale), quindi un'app e un certificato possono essere installati tramite lo stesso pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="7c74c-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="7c74c-113">Se si distribuisce il certificato da MDM o si esegue l'installazione tramite [Gestione certificati](certificate-manager.md), assicurarsi di distribuire il certificato nell'archivio del computer locale per firmare le app installate in questo modo.</span><span class="sxs-lookup"><span data-stu-id="7c74c-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="7c74c-114">Per informazioni sulle nozioni di base sulla creazione di un pacchetto di provisioning per i dispositivi HoloLens, visitare il [provisioning di HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="7c74c-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="7c74c-115">Per distribuire un'app, devi iniziare con il provisioning avanzato.</span><span class="sxs-lookup"><span data-stu-id="7c74c-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="7c74c-116">HoloLens (1a generazione) ha un supporto limitato per l'installazione di app (**UniversalAppInstall**) usando un pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="7c74c-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="7c74c-117">I dispositivi HoloLens (1a Gen) supportano solo l'installazione di un'app tramite PPKG solo durante la configurazione guidata e solo con le installazioni di contesto utente.</span><span class="sxs-lookup"><span data-stu-id="7c74c-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="7c74c-118">Installazione</span><span class="sxs-lookup"><span data-stu-id="7c74c-118">Setup</span></span>

<span data-ttu-id="7c74c-119">In [Windows Configuration designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) seguire quattro passaggi.</span><span class="sxs-lookup"><span data-stu-id="7c74c-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="7c74c-120">Impostare ApplicationManagement/AllowAllTrustedApps su "Sì".</span><span class="sxs-lookup"><span data-stu-id="7c74c-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="7c74c-121">Vedere: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="7c74c-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="7c74c-122">Passare a **UniversalAppInstall**  >  **UserContextAppLicense** immettere il **packageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="7c74c-123">Vedere [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="7c74c-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="7c74c-124">Vedere anche: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="7c74c-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="7c74c-125">Puoi usare Device Portal in un dispositivo a cui hai già installato l'app.</span><span class="sxs-lookup"><span data-stu-id="7c74c-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="7c74c-126">Visita la pagina delle app e guarda la linea PackageRelativeID, tutte le informazioni prima del "!" È il **packageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="7c74c-127">Si vedrà quindi che si ha una nuova sezione, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="7c74c-128">Usare questa area per caricare il bundle di appx.</span><span class="sxs-lookup"><span data-stu-id="7c74c-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="7c74c-129">A seconda di se l'app è stata acquistata o è stata creata una propria app LOB, sarà necessario caricare il file di licenza o il certificato di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7c74c-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="7c74c-130">Per il file di licenza: passare a **UniversalAppInstall**  >  **UserContextAppLicence** e passare al percorso della licenza e caricarlo.</span><span class="sxs-lookup"><span data-stu-id="7c74c-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="7c74c-131">Per il file di sicurezza, passare a **certificati** e selezionare il certificato da installare accanto al bundle appx.</span><span class="sxs-lookup"><span data-stu-id="7c74c-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="7c74c-132">Assicurarsi di salvare il progetto in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="7c74c-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="7c74c-133">Quindi **esportalo** come **pacchetto di provisioning**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="7c74c-134">Vedere anche: [applicare il pacchetto di provisioning a HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="7c74c-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
