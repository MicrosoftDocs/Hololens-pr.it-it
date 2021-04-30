---
title: Sbloccare Windows Holographic for Business funzionalità
description: Quando si esegue l'Windows Holographic for Business, HoloLens offre funzionalità aggiuntive progettate per le aziende.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309474"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="0e6f6-103">Sbloccare Windows Holographic for Business funzionalità</span><span class="sxs-lookup"><span data-stu-id="0e6f6-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e6f6-104">Questa pagina si applica solo a HoloLens di prima generazione.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="0e6f6-105">Microsoft HoloLens è disponibile in *Development Edition,* che esegue Windows Holographic (un'edizione di Windows 10 progettata per HoloLens) e in [Commercial Suite,](hololens-commercial-features.md)che offre funzionalità aggiuntive progettate per le aziende.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="0e6f6-106">Quando si acquista commercial suite, si riceve una licenza che aggiorna Windows Holographic a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="0e6f6-107">È possibile applicare questa licenza al dispositivo usando il provider di gestione dei dispositivi mobili [(MDM)](#edition-upgrade-by-using-mdm) dell'organizzazione o un pacchetto [di provisioning](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="0e6f6-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="0e6f6-108">In Windows 10, versione 1803, è possibile verificare che HoloLens sia stato aggiornato all'edizione Business selezionando **Settings**  >  **System (Sistema impostazioni).**</span><span class="sxs-lookup"><span data-stu-id="0e6f6-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="0e6f6-109">Aggiornamento dell'edizione tramite MDM</span><span class="sxs-lookup"><span data-stu-id="0e6f6-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="0e6f6-110">La licenza enterprise può essere applicata da qualsiasi provider MDM che supporta il [provider di servizi di configurazione (CSP) di WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span><span class="sxs-lookup"><span data-stu-id="0e6f6-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="0e6f6-111">La versione più recente dell'API MDM per Microsoft supporterà CSP WindowsLicensing.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="0e6f6-112">Per istruzioni dettagliate sull'aggiornamento di HoloLens con Microsoft Intune, vedere Aggiornare i dispositivi che eseguono [Windows Holographic a Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="0e6f6-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="0e6f6-113">In altri provider MDM, i passaggi specifici per la configurazione e la distribuzione dei criteri possono variare.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="0e6f6-114">Aggiornamento dell'edizione tramite un pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="0e6f6-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="0e6f6-115">I pacchetti di provisioning sono file creati dallo strumento Progettazione configurazione di Windows che applicano una configurazione specificata a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="0e6f6-116">Creare un pacchetto di provisioning che consente di aggiornare l'edizione di Windows Holographic</span><span class="sxs-lookup"><span data-stu-id="0e6f6-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="0e6f6-117">Creare un pacchetto di provisioning per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="0e6f6-118">Passare a **Impostazioni di runtime**  >  **EditionUpgrade** e selezionare **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Aggiornare l'edizione con le impostazioni di licenza selezionate](images/icd1.png)

1. <span data-ttu-id="0e6f6-120">Trovare il file di licenza XML fornito al momento dell'acquisto di Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0e6f6-121">È possibile configurare le [impostazioni aggiuntive nel pacchetto di provisioning](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="0e6f6-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="0e6f6-122">Scegliere **Save** (Salva) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="0e6f6-123">Leggere l'avviso che indica che i file di progetto possono contenere informazioni riservate e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="0e6f6-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0e6f6-124">Quando si compila un pacchetto di provisioning, è possibile includere informazioni riservate nei file di progetto e nel file del pacchetto di provisioning (con estensione ppkg).</span><span class="sxs-lookup"><span data-stu-id="0e6f6-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="0e6f6-125">Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="0e6f6-126">È consigliabile archiviare i file di progetto in un percorso sicuro ed eliminare i file di progetto quando non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="0e6f6-127">Scegli **Pacchetto di provisioning** dal menu **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="0e6f6-128">Impostare **Proprietario** su **Amministratore IT**, che imposta la precedenza di questo pacchetto di provisioning in modo che sia superiore ad altri applicati al dispositivo da origini diverse e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0e6f6-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="0e6f6-129">Imposta un valore per **Versione pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0e6f6-130">Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="0e6f6-131">In **Selezionare i dettagli di sicurezza per il pacchetto di provisioning** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0e6f6-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="0e6f6-132">Selezionare **Avanti** per specificare il percorso di output in cui si vuole che il pacchetto di provisioning vada dopo la compilazione.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="0e6f6-133">Per impostazione predefinita, Progettazione immagine e configurazione di Windows usa la cartella di progetto come percorso di output.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="0e6f6-134">Facoltativamente, è possibile selezionare **Sfoglia per** modificare il percorso di output predefinito.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="0e6f6-135">Selezionare **Next** (Avanti).</span><span class="sxs-lookup"><span data-stu-id="0e6f6-135">Select **Next**.</span></span>

1. <span data-ttu-id="0e6f6-136">Selezionare **Compila** per iniziare a compilare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="0e6f6-137">Nella pagina di compilazione vengono visualizzate le informazioni sul progetto e l'indicatore di stato indica lo stato della compilazione.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="0e6f6-138">Al termine della compilazione, selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="0e6f6-139">Applicare il pacchetto di provisioning a HoloLens</span><span class="sxs-lookup"><span data-stu-id="0e6f6-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="0e6f6-140">Usando il cavo USB, collegare il dispositivo a un PC.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="0e6f6-141">Avviare il dispositivo, ma non continuare oltre la **pagina di** adattamento dell'esperienza di configurazione iniziale (la prima pagina con la casella blu).</span><span class="sxs-lookup"><span data-stu-id="0e6f6-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="0e6f6-142">Nel PC HoloLens viene visualizzato come dispositivo in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0e6f6-143">Se il dispositivo HoloLens esegue Windows 10, versione 1607 o precedente, aprire Esplora file premendo brevemente e  rilasciando i pulsanti **Volume** Giù e Alimentazione contemporaneamente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="0e6f6-144">In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="0e6f6-145">Mentre HoloLens è ancora nella **pagina** adatta, premere brevemente e rilasciare di nuovo i pulsanti **Volume Down** e **Power** contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="0e6f6-146">HoloLens chiede se si considera attendibile il pacchetto e si vuole applicarlo.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="0e6f6-147">Confermare che consideri attendibile il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="0e6f6-148">Potrai vedere se il pacchetto è stato applicato correttamente o meno.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="0e6f6-149">Se non è stato applicato correttamente, è possibile correggere il pacchetto e riprovare.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="0e6f6-150">In caso di esito positivo, procedere con la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e6f6-150">If successful, proceed with device setup.</span></span>
