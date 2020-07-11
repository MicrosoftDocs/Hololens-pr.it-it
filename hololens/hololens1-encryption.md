---
title: Crittografia BitLocker di HoloLens
description: Abilitare la crittografia dispositivo Bitlocker per proteggere i file archiviati in HoloLens
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
ms.openlocfilehash: 5ab35f0804c6a906cb0bb262211e8ae5ab017459
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865776"
---
# <span data-ttu-id="49954-103">Crittografia BitLocker di HoloLens (1a generazione)</span><span class="sxs-lookup"><span data-stu-id="49954-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="49954-104">HoloLens (1a generazione) e HoloLens 2 supportano entrambe la crittografia del dispositivo tramite BitLocker, ma BitLocker è sempre abilitato in HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="49954-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="49954-105">Questo articolo consente di abilitare e gestire BitLocker in HoloLens (1a generazione).</span><span class="sxs-lookup"><span data-stu-id="49954-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="49954-106">In HoloLens (1a generazione) è possibile abilitare la crittografia dei dispositivi BitLocker manualmente o usando la gestione di dispositivi mobili (MDM).</span><span class="sxs-lookup"><span data-stu-id="49954-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="49954-107">Seguire queste istruzioni per abilitare la [crittografia dei dispositivi BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) per proteggere i file e le informazioni archiviate in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="49954-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="49954-108">La crittografia dei dispositivi consente di proteggere i dati usando il metodo di crittografia AES-CBC 128, che equivale al [Metodo EncryptionMethodByDriveType 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) nel provider del servizio di configurazione di BitLocker.</span><span class="sxs-lookup"><span data-stu-id="49954-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="49954-109">Il personale che ha la chiave di crittografia corretta, ad esempio una password, può decrittografarlo o eseguire un ripristino dei dati.</span><span class="sxs-lookup"><span data-stu-id="49954-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <span data-ttu-id="49954-110">Abilitare la crittografia del dispositivo tramite MDM</span><span class="sxs-lookup"><span data-stu-id="49954-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="49954-111">Puoi usare il provider di gestione di dispositivi mobili (MDM) per applicare un criterio che richiede la crittografia del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49954-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="49954-112">Il criterio da usare è l' [impostazione Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) nel CSP dei criteri.</span><span class="sxs-lookup"><span data-stu-id="49954-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="49954-113">Vedere le istruzioni per abilitare la crittografia dei dispositivi con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="49954-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="49954-114">Per altri strumenti MDM, vedi le istruzioni nella documentazione del tuo provider MDM.</span><span class="sxs-lookup"><span data-stu-id="49954-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="49954-115">Se il provider MDM richiede l'URI personalizzato per la crittografia del dispositivo, usare la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="49954-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="49954-116">**Nome**: un nome di tua scelta</span><span class="sxs-lookup"><span data-stu-id="49954-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="49954-117">**Descrizione**: facoltativa</span><span class="sxs-lookup"><span data-stu-id="49954-117">**Description**: optional</span></span>
- <span data-ttu-id="49954-118">**URI OMA**:</span><span class="sxs-lookup"><span data-stu-id="49954-118">**OMA-URI**:</span></span> `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- <span data-ttu-id="49954-119">**Tipo di dati:** intero</span><span class="sxs-lookup"><span data-stu-id="49954-119">**Data type**: integer</span></span>
- <span data-ttu-id="49954-120">**Valore**:</span><span class="sxs-lookup"><span data-stu-id="49954-120">**Value**:</span></span> `1`

## <span data-ttu-id="49954-121">Abilitare la crittografia del dispositivo usando un pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="49954-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="49954-122">I pacchetti di provisioning sono file creati dallo strumento Progettazione configurazione di Windows che applicano una configurazione specifica a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49954-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <span data-ttu-id="49954-123">Creare un pacchetto di provisioning che aggiorni l'edizione olografica di Windows e Abilita la crittografia</span><span class="sxs-lookup"><span data-stu-id="49954-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="49954-124">Creare un pacchetto di provisioning per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="49954-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="49954-125">Vai a **Impostazioni di runtime** > **Criteri** > **Sicurezza** e seleziona **RequireDeviceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="49954-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![L'impostazione di crittografia del dispositivo deve essere configurata su Sì](images/device-encryption.png)

1. <span data-ttu-id="49954-127">Trovare il file di licenza XML fornito quando è stata acquistata la famiglia di prodotti commerciali.</span><span class="sxs-lookup"><span data-stu-id="49954-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="49954-128">Individua e seleziona il file di licenza XML fornito al momento dell'acquisto di Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="49954-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="49954-129">È possibile configurare le [impostazioni aggiuntive nel pacchetto di provisioning](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="49954-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="49954-130">Scegli **Salva** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="49954-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="49954-131">Leggere l'avviso che spiega che i file di progetto possono contenere informazioni riservate e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="49954-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="49954-132">Quando si compila un pacchetto di provisioning, è possibile includere informazioni riservate nei file di progetto e nel pacchetto di provisioning (file con estensione ppkg).</span><span class="sxs-lookup"><span data-stu-id="49954-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="49954-133">Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati.</span><span class="sxs-lookup"><span data-stu-id="49954-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="49954-134">È consigliabile archiviare i file di progetto in un percorso sicuro ed eliminare i file di progetto quando non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="49954-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="49954-135">Fai clic su **Pacchetto di provisioning** nel menu **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="49954-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="49954-136">Modifica **Proprietario** in **Amministratore IT** per assegnare a questo pacchetto di provisioning una precedenza maggiore rispetto agli altri pacchetti di provisioning applicati al dispositivo da altre origini, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49954-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="49954-137">Imposta un valore per **Versione pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="49954-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="49954-138">Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="49954-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="49954-139">In **Seleziona i dettagli di sicurezza per il pacchetto di provisioning**, fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49954-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="49954-140">Fai clic su **Avanti** per specificare il percorso di output in cui vuoi posizionare il pacchetto di provisioning creato.</span><span class="sxs-lookup"><span data-stu-id="49954-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="49954-141">Per impostazione predefinita, Progettazione immagini e configurazione di Windows usa la cartella di progetto come percorso di output.</span><span class="sxs-lookup"><span data-stu-id="49954-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="49954-142">Facoltativamente, puoi fare clic su Sfoglia per modificare il percorso di output predefinito.</span><span class="sxs-lookup"><span data-stu-id="49954-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="49954-143">Fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49954-143">Click **Next**.</span></span>
1. <span data-ttu-id="49954-144">Fai clic su **Build** per iniziare a compilare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="49954-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="49954-145">Le informazioni del progetto vengono visualizzate nella pagina di compilazione e la barra di stato indica lo stato della compilazione.</span><span class="sxs-lookup"><span data-stu-id="49954-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="49954-146">Al termine della compilazione, fai clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="49954-146">When the build completes, click **Finish**.</span></span>

### <span data-ttu-id="49954-147">Applicare il pacchetto di provisioning a HoloLens</span><span class="sxs-lookup"><span data-stu-id="49954-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="49954-148">Connetti il dispositivo tramite USB a un PC e avvia il dispositivo, ma non proseguire oltre la pagina **adatta** di Configurazione guidata (la prima pagina con il riquadro blu).</span><span class="sxs-lookup"><span data-stu-id="49954-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="49954-149">Premi brevemente e rilascia i pulsanti di **abbassamento del volume** e **Arresta** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="49954-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="49954-150">HoloLens verrà visualizzato come un dispositivo in Esplora File nel PC.</span><span class="sxs-lookup"><span data-stu-id="49954-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="49954-151">In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49954-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="49954-152">Premi brevemente e rilascia nuovamente i pulsanti di **abbassamento del volume** e **Alimentazione** simultaneamente mentre sei nella pagina **adatta**.</span><span class="sxs-lookup"><span data-stu-id="49954-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="49954-153">Il dispositivo ti chiederà se consideri attendibile il pacchetto e vuoi applicarlo.</span><span class="sxs-lookup"><span data-stu-id="49954-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="49954-154">Confermare che consideri attendibile il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="49954-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="49954-155">Potrai vedere se il pacchetto è stato applicato correttamente o meno.</span><span class="sxs-lookup"><span data-stu-id="49954-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="49954-156">Se l'applicazione non è riuscita, puoi correggere il pacchetto e riprovare.</span><span class="sxs-lookup"><span data-stu-id="49954-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="49954-157">Se ha avuto esito positivo, continua con la Configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="49954-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="49954-158">Se il dispositivo è stato acquistato prima di agosto 2016, dovrai accedere con un account Microsoft, ottenere l'aggiornamento più recente del sistema operativo e quindi reimpostare il sistema operativo per applicare il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="49954-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <span data-ttu-id="49954-159">Verificare la crittografia dispositivo</span><span class="sxs-lookup"><span data-stu-id="49954-159">Verify device encryption</span></span>

<span data-ttu-id="49954-160">La crittografia è invisibile all'utente in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="49954-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="49954-161">Per verificare lo stato della crittografia del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="49954-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="49954-162">In HoloLens vai a **Impostazioni** > **Sistema** > **Informazioni su**.</span><span class="sxs-lookup"><span data-stu-id="49954-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="49954-163">**BitLocker** è **abilitato** se il dispositivo è crittografato.</span><span class="sxs-lookup"><span data-stu-id="49954-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Informazioni sulla schermata che mostra BitLocker Enabled](images/about-encryption.png)
