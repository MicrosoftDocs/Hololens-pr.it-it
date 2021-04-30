---
title: Pacchetto di provisioning
description: Informazioni sulla creazione di pacchetti di app, il provisioning, la distribuzione e la distribuzione di app aziendali per i dispositivi HoloLens.
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309410"
---
# <a name="provisioning-package"></a><span data-ttu-id="3f7d5-104">Pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="3f7d5-104">Provisioning Package</span></span>

<span data-ttu-id="3f7d5-105">I pacchetti di provisioning possono essere usati per preparare e configurare i dispositivi in un ambiente senza accesso alla gestione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="3f7d5-106">Possono anche essere distribuiti in un dispositivo indipendentemente dall'identità dell'utente, dallo stato di registrazione, durante la configurazione predefinita o applicando un pacchetto di provisioning durante [l'installazione](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)di .</span><span class="sxs-lookup"><span data-stu-id="3f7d5-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="3f7d5-107">Considerazioni sul provisioning dei pacchetti:</span><span class="sxs-lookup"><span data-stu-id="3f7d5-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="3f7d5-108">App non pubbliche</span><span class="sxs-lookup"><span data-stu-id="3f7d5-108">Non-Public apps</span></span>
* <span data-ttu-id="3f7d5-109">Solo caricamento laterale USB</span><span class="sxs-lookup"><span data-stu-id="3f7d5-109">USB side-load only</span></span>
* <span data-ttu-id="3f7d5-110">Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite PPKG)</span><span class="sxs-lookup"><span data-stu-id="3f7d5-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="3f7d5-111">Le app installate tramite un pacchetto di provisioning devono essere firmate da un certificato nell'archivio del computer locale.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="3f7d5-112">I pacchetti di provisioning possono installare certificati solo nell'archivio del dispositivo (computer locale), pertanto un'app e un certificato possono essere installati tramite lo stesso pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="3f7d5-113">Se si distribuisce il certificato da MDM o si installa tramite [Gestione](certificate-manager.md)certificati, assicurarsi di distribuire il certificato nell'archivio computer locale per firmare le app installate in questo modo.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="3f7d5-114">Per informazioni di base sulla creazione di un pacchetto di provisioning per dispositivi HoloLens, vedere [Provisioning di HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="3f7d5-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="3f7d5-115">Per distribuire un'app, è necessario iniziare con il provisioning avanzato.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="3f7d5-116">HoloLens (prima generazione) ha un supporto limitato per l'installazione di app (**UniversalAppInstall**) usando un pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="3f7d5-117">I dispositivi HoloLens (prima generazione) supportano solo l'installazione di un'app tramite PPKG solo durante la configurazione guidata e solo con le installazioni del contesto utente.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="3f7d5-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="3f7d5-118">Setup</span></span>

<span data-ttu-id="3f7d5-119">In [Progettazione configurazione Windows seguire](https://www.microsoft.com/store/productId/9NBLGGH4TX22) questa procedura.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="3f7d5-120">Impostare ApplicationManagement/AllowAllTrustedApps su "Sì".</span><span class="sxs-lookup"><span data-stu-id="3f7d5-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="3f7d5-121">Vedere: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="3f7d5-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="3f7d5-122">Passare a **UniversalAppInstall**  >  **UserContextAppLicense (UniversalAppInstall UserContextAppLicense)** immettere **PackageFamilyName.**</span><span class="sxs-lookup"><span data-stu-id="3f7d5-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="3f7d5-123">Vedere [UniversalAppInstall.](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)</span><span class="sxs-lookup"><span data-stu-id="3f7d5-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="3f7d5-124">Vedere anche: [UserContextAppLicense.](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)</span><span class="sxs-lookup"><span data-stu-id="3f7d5-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="3f7d5-125">È possibile usare Portale di dispositivi in un dispositivo in cui è già installata l'app.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="3f7d5-126">Visitare la pagina App ed esaminare la riga PackageRelativeID, tutte le informazioni prima di "!" **PackageFamilyName** è .</span><span class="sxs-lookup"><span data-stu-id="3f7d5-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="3f7d5-127">Si noti quindi che è presente una nuova sezione, **ApplicationFile.**</span><span class="sxs-lookup"><span data-stu-id="3f7d5-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="3f7d5-128">Usare quest'area per caricare il bundle appx.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="3f7d5-129">A seconda che l'app sia stata acquistata o sia stata compilata una propria app LOB, sarà necessario caricare il file di licenza o il certificato di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="3f7d5-130">Per il file di licenza: passare a **UniversalAppInstall**  >  **UserContextAppLicence** e selezionare il percorso della licenza e caricarlo.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="3f7d5-131">Per il file di sicurezza, passare a **Certificati** e selezionare il certificato da installare insieme al bundle con estensione appx.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="3f7d5-132">Assicurarsi di salvare il progetto in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="3f7d5-133">Esportarlo quindi come pacchetto **di provisioning.** </span><span class="sxs-lookup"><span data-stu-id="3f7d5-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="3f7d5-134">Vedere anche: [Applicare il pacchetto di provisioning a HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="3f7d5-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
