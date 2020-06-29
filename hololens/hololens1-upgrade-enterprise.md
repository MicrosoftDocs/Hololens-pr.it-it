---
title: Sbloccare le funzionalità di Windows Holographic for Business
description: Quando si esegue l'aggiornamento a Windows olografico for business, HoloLens offre funzionalità aggiuntive progettate per le aziende.
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829335"
---
# <span data-ttu-id="87186-103">Sbloccare le funzionalità di Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="87186-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87186-104">Questa pagina si applica solo a HoloLens 1st Gen.</span><span class="sxs-lookup"><span data-stu-id="87186-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="87186-105">Microsoft HoloLens è disponibile in *Development Edition*, che esegue Windows olografico (un'edizione di Windows 10 progettata per HoloLens) e nella [suite commerciale](hololens-commercial-features.md), che offre funzionalità aggiuntive progettate per le aziende.</span><span class="sxs-lookup"><span data-stu-id="87186-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="87186-106">Quando acquisti la versione Commercial Suite, ricevi una licenza che aggiorna Windows Holographic a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="87186-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="87186-107">Puoi applicare questa licenza al dispositivo usando il [provider di gestione di dispositivi mobili (MDM)](#edition-upgrade-by-using-mdm) dell'organizzazione o un pacchetto di [provisioning](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="87186-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="87186-108">In Windows 10, versione 1803, è possibile verificare che HoloLens sia stato aggiornato all'edizione aziendale selezionando sistema di **Impostazioni**  >  **System**.</span><span class="sxs-lookup"><span data-stu-id="87186-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <span data-ttu-id="87186-109">Aggiornamento dell'edizione tramite MDM</span><span class="sxs-lookup"><span data-stu-id="87186-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="87186-110">La licenza enterprise può essere applicata da qualsiasi provider MDM che supporta il [provider di servizi di configurazione (CSP) di WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span><span class="sxs-lookup"><span data-stu-id="87186-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="87186-111">La versione più recente dell'API MDM per Microsoft supporterà CSP WindowsLicensing.</span><span class="sxs-lookup"><span data-stu-id="87186-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="87186-112">Per istruzioni dettagliate sull'aggiornamento di HoloLens con Microsoft Intune, vedere [aggiornare i dispositivi che eseguono Windows olografico in Windows olografico for business](https://docs.microsoft.com/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="87186-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="87186-113">In altri provider MDM, i passaggi specifici per la configurazione e la distribuzione dei criteri possono variare.</span><span class="sxs-lookup"><span data-stu-id="87186-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <span data-ttu-id="87186-114">Aggiornamento dell'edizione con un pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="87186-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="87186-115">I pacchetti di provisioning sono file creati dallo strumento Progettazione configurazione di Windows che applicano una configurazione specifica a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="87186-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <span data-ttu-id="87186-116">Creare un pacchetto di provisioning che consente di aggiornare l'edizione di Windows Holographic</span><span class="sxs-lookup"><span data-stu-id="87186-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="87186-117">Creare un pacchetto di provisioning per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="87186-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="87186-118">Vai a **Impostazioni di runtime** > **EditionUpgrade** e seleziona **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="87186-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Aggiornare l'edizione con le impostazioni di licenza selezionate](images/icd1.png)

1. <span data-ttu-id="87186-120">Trovare il file di licenza XML fornito quando è stata acquistata la famiglia di prodotti commerciali.</span><span class="sxs-lookup"><span data-stu-id="87186-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87186-121">È possibile configurare le [impostazioni aggiuntive nel pacchetto di provisioning](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="87186-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="87186-122">Scegliere **Salva**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="87186-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="87186-123">Leggere l'avviso che i file di progetto possono contenere informazioni riservate e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="87186-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="87186-124">Quando si compila un pacchetto di provisioning, è possibile includere informazioni riservate nei file di progetto e nel pacchetto di provisioning (file con estensione ppkg).</span><span class="sxs-lookup"><span data-stu-id="87186-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="87186-125">Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati.</span><span class="sxs-lookup"><span data-stu-id="87186-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="87186-126">È consigliabile archiviare i file di progetto in un percorso sicuro ed eliminare i file di progetto quando non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="87186-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="87186-127">Scegli **Pacchetto di provisioning** dal menu **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="87186-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="87186-128">Modificare il **proprietario** dell' **amministratore IT**, impostando la precedenza del pacchetto di provisioning su un valore superiore rispetto ad altri applicati a questo dispositivo da origini diverse e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="87186-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="87186-129">Imposta un valore per **Versione pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="87186-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="87186-130">Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="87186-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="87186-131">In **selezionare dettagli di sicurezza per il pacchetto di provisioning**selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="87186-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="87186-132">Selezionare **Avanti** per specificare la posizione di output in cui si vuole inserire il pacchetto di provisioning dopo la compilazione.</span><span class="sxs-lookup"><span data-stu-id="87186-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="87186-133">Per impostazione predefinita, Progettazione immagini e configurazione di Windows usa la cartella di progetto come percorso di output.</span><span class="sxs-lookup"><span data-stu-id="87186-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="87186-134">Facoltativamente, è possibile selezionare **Sfoglia** per modificare la posizione di output predefinita.</span><span class="sxs-lookup"><span data-stu-id="87186-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="87186-135">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="87186-135">Select **Next**.</span></span>

1. <span data-ttu-id="87186-136">Selezionare **Compila** per iniziare a creare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="87186-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="87186-137">La pagina di compilazione Visualizza le informazioni sul progetto e la barra di stato indica lo stato della compilazione.</span><span class="sxs-lookup"><span data-stu-id="87186-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="87186-138">Al termine della compilazione, selezionare **fine**.</span><span class="sxs-lookup"><span data-stu-id="87186-138">When the build completes, select **Finish**.</span></span>

### <span data-ttu-id="87186-139">Applicare il pacchetto di provisioning a HoloLens</span><span class="sxs-lookup"><span data-stu-id="87186-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="87186-140">Usando il cavo USB, connettere il dispositivo a un PC.</span><span class="sxs-lookup"><span data-stu-id="87186-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="87186-141">Avviare il dispositivo, ma non continuare oltre la pagina **adatta** dell'esperienza di configurazione iniziale (la prima pagina con la casella blu).</span><span class="sxs-lookup"><span data-stu-id="87186-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="87186-142">Nel PC HoloLens viene visualizzato come dispositivo in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="87186-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87186-143">Se il dispositivo HoloLens è in esecuzione in Windows 10, versione 1607 o precedente, aprire Esplora file premendo brevemente e rilasciando contemporaneamente i pulsanti **volume giù** e **alimentazione** nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="87186-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="87186-144">In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="87186-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="87186-145">Mentre HoloLens è ancora nella pagina **Fit** , premere brevemente e rilasciare di nuovo contemporaneamente i pulsanti **volume giù** e **Power** .</span><span class="sxs-lookup"><span data-stu-id="87186-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="87186-146">HoloLens chiede se si ritiene attendibile il pacchetto e si desidera applicarlo.</span><span class="sxs-lookup"><span data-stu-id="87186-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="87186-147">Confermare che consideri attendibile il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="87186-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="87186-148">Potrai vedere se il pacchetto è stato applicato correttamente o meno.</span><span class="sxs-lookup"><span data-stu-id="87186-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="87186-149">Se non è stata applicata correttamente, è possibile correggere il pacchetto e riprovare.</span><span class="sxs-lookup"><span data-stu-id="87186-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="87186-150">In caso di esito positivo, procedere con la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="87186-150">If successful, proceed with device setup.</span></span>
