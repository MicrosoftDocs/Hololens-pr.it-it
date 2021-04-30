---
title: Crittografia BitLocker di HoloLens
description: Informazioni su come abilitare la crittografia dei dispositivi Bitlocker per proteggere i file archiviati nei dispositivi di realtà mista HoloLens.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 268c3650b85e7e7f102618ccc5a94c25de54dcfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309064"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="5f012-103">Crittografia BitLocker di HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="5f012-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="5f012-104">HoloLens (prima generazione) e HoloLens 2 entrambi supportano la crittografia dei dispositivi con BitLocker, tuttavia BitLocker è sempre abilitato HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5f012-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="5f012-105">Questo articolo consente di abilitare e gestire BitLocker in HoloLens (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="5f012-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="5f012-106">In HoloLens (prima generazione) è possibile abilitare la crittografia dei dispositivi BitLocker manualmente o usando la gestione dei dispositivi mobili (MDM).</span><span class="sxs-lookup"><span data-stu-id="5f012-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="5f012-107">Seguire queste istruzioni per abilitare [la crittografia dei dispositivi BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) per proteggere i file e le informazioni archiviate in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5f012-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="5f012-108">La crittografia dei dispositivi consente di proteggere i dati usando il metodo di crittografia AES-CBC 128, equivalente al metodo [EncryptionMethodByDriveType 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) nel provider del servizio di configurazione BitLocker .</span><span class="sxs-lookup"><span data-stu-id="5f012-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="5f012-109">Il personale che dispone della chiave di crittografia corretta, ad esempio una password, può decrittografarla o eseguire un ripristino dei dati.</span><span class="sxs-lookup"><span data-stu-id="5f012-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="5f012-110">Abilitare la crittografia dei dispositivi tramite MDM</span><span class="sxs-lookup"><span data-stu-id="5f012-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="5f012-111">È possibile usare il provider di Gestione dispositivi mobili (MDM) per applicare un criterio che richiede la crittografia del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5f012-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="5f012-112">Il criterio da usare è [l'impostazione Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in Policy CSP.</span><span class="sxs-lookup"><span data-stu-id="5f012-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="5f012-113">Vedere le istruzioni per abilitare la crittografia dei dispositivi Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5f012-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="5f012-114">Per altri strumenti MDM, vedere la documentazione del provider MDM per istruzioni.</span><span class="sxs-lookup"><span data-stu-id="5f012-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="5f012-115">Se il provider MDM richiede UN URI personalizzato per la crittografia del dispositivo, usare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="5f012-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="5f012-116">**Nome**: un nome a scelta</span><span class="sxs-lookup"><span data-stu-id="5f012-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="5f012-117">**Descrizione:** facoltativo</span><span class="sxs-lookup"><span data-stu-id="5f012-117">**Description**: optional</span></span>
- <span data-ttu-id="5f012-118">**URI OMA**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="5f012-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="5f012-119">**Tipo di dati**: integer</span><span class="sxs-lookup"><span data-stu-id="5f012-119">**Data type**: integer</span></span>
- <span data-ttu-id="5f012-120">**Valore**: `1`</span><span class="sxs-lookup"><span data-stu-id="5f012-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="5f012-121">Abilitare la crittografia dei dispositivi usando un pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="5f012-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="5f012-122">I pacchetti di provisioning sono file creati dallo strumento Progettazione configurazione di Windows che applicano una configurazione specificata a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5f012-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="5f012-123">Creare un pacchetto di provisioning che aggiorna l'edizione Windows Holographic e abilita la crittografia</span><span class="sxs-lookup"><span data-stu-id="5f012-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="5f012-124">Creare un pacchetto di provisioning per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5f012-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="5f012-125">Passare a **Impostazioni di runtime**  >  **Criteri**  >  **Sicurezza** e **selezionare RichiediDispositivaCrittografia.**</span><span class="sxs-lookup"><span data-stu-id="5f012-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Richiedi l'impostazione di crittografia del dispositivo configurata su Sì](images/device-encryption.png)

1. <span data-ttu-id="5f012-127">Trovare il file di licenza XML fornito al momento dell'acquisto di Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="5f012-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="5f012-128">Individua e seleziona il file di licenza XML fornito al momento dell'acquisto di Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="5f012-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="5f012-129">È possibile configurare le [impostazioni aggiuntive nel pacchetto di provisioning](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="5f012-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="5f012-130">Scegliere **Save** (Salva) dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="5f012-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="5f012-131">Leggere l'avviso che spiega che i file di progetto possono contenere informazioni riservate e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="5f012-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5f012-132">Quando si compila un pacchetto di provisioning, è possibile includere informazioni riservate nei file di progetto e nel file del pacchetto di provisioning (con estensione ppkg).</span><span class="sxs-lookup"><span data-stu-id="5f012-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="5f012-133">Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati.</span><span class="sxs-lookup"><span data-stu-id="5f012-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="5f012-134">È consigliabile archiviare i file di progetto in un percorso sicuro ed eliminare i file di progetto quando non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="5f012-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="5f012-135">Fai clic su **Pacchetto di provisioning** nel menu **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="5f012-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="5f012-136">Impostare **Proprietario** su **Amministratore IT,** che imposta la precedenza di questo pacchetto di provisioning su un valore superiore rispetto al provisioning dei pacchetti applicati al dispositivo da altre origini e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="5f012-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="5f012-137">Imposta un valore per **Versione pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="5f012-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="5f012-138">Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5f012-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="5f012-139">In **Seleziona i dettagli di sicurezza per il pacchetto di provisioning**, fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5f012-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="5f012-140">Fai clic su **Next** per specificare il percorso di output in cui vuoi posizionare il pacchetto di provisioning creato.</span><span class="sxs-lookup"><span data-stu-id="5f012-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="5f012-141">Per impostazione predefinita, Progettazione immagine e configurazione di Windows usa la cartella di progetto come percorso di output.</span><span class="sxs-lookup"><span data-stu-id="5f012-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="5f012-142">Facoltativamente, puoi fare clic su Sfoglia per modificare il percorso di output predefinito.</span><span class="sxs-lookup"><span data-stu-id="5f012-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="5f012-143">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5f012-143">Click **Next**.</span></span>
1. <span data-ttu-id="5f012-144">Fai clic su **Build** per iniziare a compilare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5f012-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="5f012-145">Le informazioni del progetto vengono visualizzate nella pagina di compilazione e la barra di stato indica lo stato della compilazione.</span><span class="sxs-lookup"><span data-stu-id="5f012-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="5f012-146">Al termine della compilazione, fai clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5f012-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="5f012-147">Applicare il pacchetto di provisioning a HoloLens</span><span class="sxs-lookup"><span data-stu-id="5f012-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="5f012-148">Connettere il dispositivo tramite USB a un PC e avviare  il dispositivo, ma non continuare oltre la pagina adatta dell'esperienza di configurazione iniziale (la prima pagina con la casella blu).</span><span class="sxs-lookup"><span data-stu-id="5f012-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="5f012-149">Premi brevemente e rilascia i pulsanti di **abbassamento del volume** e **Alimentazione** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="5f012-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="5f012-150">HoloLens verrà visualizzato come un dispositivo in Esplora File nel PC.</span><span class="sxs-lookup"><span data-stu-id="5f012-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="5f012-151">In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5f012-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="5f012-152">Premi brevemente e rilascia nuovamente i pulsanti di **abbassamento del volume** e **Alimentazione** simultaneamente mentre sei nella pagina **adatta**.</span><span class="sxs-lookup"><span data-stu-id="5f012-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="5f012-153">Il dispositivo ti chiederà se consideri attendibile il pacchetto e vuoi applicarlo.</span><span class="sxs-lookup"><span data-stu-id="5f012-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="5f012-154">Confermare che consideri attendibile il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5f012-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="5f012-155">Potrai vedere se il pacchetto è stato applicato correttamente o meno.</span><span class="sxs-lookup"><span data-stu-id="5f012-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="5f012-156">Se l'applicazione non è riuscita, è possibile correggere il pacchetto e riprovare.</span><span class="sxs-lookup"><span data-stu-id="5f012-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="5f012-157">Se l'operazione ha esito positivo, procedere con la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5f012-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="5f012-158">Se il dispositivo è stato acquistato prima di agosto 2016, è necessario accedere al dispositivo con un account Microsoft, ottenere l'aggiornamento più recente del sistema operativo e quindi reimpostare il sistema operativo per applicare il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="5f012-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="5f012-159">Verificare la crittografia del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5f012-159">Verify device encryption</span></span>

<span data-ttu-id="5f012-160">La crittografia è invisibile all'utente in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5f012-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="5f012-161">Per verificare lo stato di crittografia del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="5f012-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="5f012-162">In HoloLens passare a Impostazioni  >  **Sistema**  >  **Informazioni su**.</span><span class="sxs-lookup"><span data-stu-id="5f012-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="5f012-163">**BitLocker** è **abilitato** se il dispositivo è crittografato.</span><span class="sxs-lookup"><span data-stu-id="5f012-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Schermata Informazioni su che mostra BitLocker abilitato](images/about-encryption.png)
