---
title: Linee guida sull'infrastruttura per HoloLens
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1031eaeaf2767f8aa982d74bb282bc1fb086051b
ms.sourcegitcommit: 77eb85608066d9a4ed01b3862afe356f7e54d583
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "10940216"
---
# <span data-ttu-id="66b39-102">Configurare la rete per HoloLens</span><span class="sxs-lookup"><span data-stu-id="66b39-102">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="66b39-103">Questa parte del documento richiede la partecipazione degli utenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="66b39-103">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="66b39-104">Amministratore di rete con le autorizzazioni per modificare il proxy o il firewall</span><span class="sxs-lookup"><span data-stu-id="66b39-104">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="66b39-105">Amministratore di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="66b39-105">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="66b39-106">Amministratore di Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="66b39-106">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="66b39-107">Requisiti dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="66b39-107">Infrastructure Requirements</span></span>

<span data-ttu-id="66b39-108">HoloLens è, in sostanza, un dispositivo mobile di Windows integrato in Azure.</span><span class="sxs-lookup"><span data-stu-id="66b39-108">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="66b39-109">Funziona in modo ottimale in ambienti commerciali con disponibilità di rete wireless (Wi-Fi) e accesso ai servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66b39-109">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="66b39-110">I servizi cloud critici includono:</span><span class="sxs-lookup"><span data-stu-id="66b39-110">Critical cloud services include:</span></span>

- <span data-ttu-id="66b39-111">Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="66b39-111">Azure active directory (AAD)</span></span>
- <span data-ttu-id="66b39-112">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="66b39-112">Windows Update (WU)</span></span>

<span data-ttu-id="66b39-113">I clienti commerciali avranno bisogno di un'infrastruttura di gestione della mobilità aziendale (EMM, Enterprise Mobility Management) o gestione dei dispositivi mobili (MDM, Mobile Device Management) per gestire i dispositivi HoloLens in scala.</span><span class="sxs-lookup"><span data-stu-id="66b39-113">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="66b39-114">Questa guida usa [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) come esempio, anche se qualsiasi provider con supporto completo per Microsoft Policy può supportare HoloLens.</span><span class="sxs-lookup"><span data-stu-id="66b39-114">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="66b39-115">Chiedere al provider di gestione di dispositivi mobili se supporta HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="66b39-115">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="66b39-116">HoloLens supporta un set limitato di esperienze disconnesse dal cloud.</span><span class="sxs-lookup"><span data-stu-id="66b39-116">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="66b39-117">Supporto EAP di rete wireless</span><span class="sxs-lookup"><span data-stu-id="66b39-117">Wireless network EAP support</span></span>

- <span data-ttu-id="66b39-118">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="66b39-118">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="66b39-119">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="66b39-119">PEAP-TLS</span></span>
- <span data-ttu-id="66b39-120">TLS</span><span class="sxs-lookup"><span data-stu-id="66b39-120">TLS</span></span>
- <span data-ttu-id="66b39-121">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="66b39-121">TTLS-CHAP</span></span>
- <span data-ttu-id="66b39-122">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="66b39-122">TTLS-CHAPv2</span></span>
- <span data-ttu-id="66b39-123">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="66b39-123">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="66b39-124">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="66b39-124">TTLS-PAP</span></span>
- <span data-ttu-id="66b39-125">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="66b39-125">TTLS-TLS</span></span>

### <span data-ttu-id="66b39-126">Requisiti di rete specifici di HoloLens</span><span class="sxs-lookup"><span data-stu-id="66b39-126">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="66b39-127">Assicurarsi che [questo elenco](hololens-offline.md) di endpoint sia consentito nel firewall di rete.</span><span class="sxs-lookup"><span data-stu-id="66b39-127">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="66b39-128">Questo consentirà il funzionamento corretto di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="66b39-128">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="66b39-129">Requisiti di rete specifici di Remote Assist</span><span class="sxs-lookup"><span data-stu-id="66b39-129">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="66b39-130">La larghezza di banda consigliata per prestazioni ottimali di Remote Assist è 1,5 Mbps.</span><span class="sxs-lookup"><span data-stu-id="66b39-130">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="66b39-131">È possibile trovare informazioni dettagliate sui requisiti di rete e altre informazioni [qui](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="66b39-131">Detailed network requirements and additional information can be found [here](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span></span>
**<span data-ttu-id="66b39-132">Se non si ha una rete con una velocità di rete di almeno 1,5 Mbps, Remote Assist funzionerà comunque.</span><span class="sxs-lookup"><span data-stu-id="66b39-132">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="66b39-133">Tuttavia, la qualità potrebbe soffrire.</span><span class="sxs-lookup"><span data-stu-id="66b39-133">However, quality may suffer).</span></span>**
1. <span data-ttu-id="66b39-134">Assicurarsi che le porte e gli URL seguenti siano consentiti nel firewall di rete.</span><span class="sxs-lookup"><span data-stu-id="66b39-134">Make sure that these ports and URLs are allowed on your network firewall.</span></span> <span data-ttu-id="66b39-135">Questo permetterà il funzionamento di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66b39-135">This will enable Microsoft Teams to function.</span></span> <span data-ttu-id="66b39-136">L'elenco più recente è disponibile [qui](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="66b39-136">The latest list can be found [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="66b39-137">Leggere altre informazioni sui requisiti di rete [specifici per assistenza remota t](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="66b39-137">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="66b39-138">Leggere altre informazioni su come[preparare la rete aziendale per Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="66b39-138">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <span data-ttu-id="66b39-139">Requisiti di rete specifici di Guides</span><span class="sxs-lookup"><span data-stu-id="66b39-139">Guides Specific Network Requirements</span></span>

<span data-ttu-id="66b39-140">Guides richiede solo l'accesso di rete per scaricare e usare l'app.</span><span class="sxs-lookup"><span data-stu-id="66b39-140">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="66b39-141">Indicazioni per Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="66b39-141">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="66b39-142">Questo passaggio è necessario solo se la società prevede di gestire HoloLens.</span><span class="sxs-lookup"><span data-stu-id="66b39-142">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="66b39-143">Verificare di avere una licenza di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="66b39-143">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="66b39-144">Per altre informazioni, vedere i [requisiti di licenza di HoloLens](hololens-licenses-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66b39-144">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="66b39-145">Se si prevede di usare la registrazione automatica, sarà necessario [configurare la registrazione di Azure AD.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="66b39-145">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="66b39-146">Verificare che gli utenti della società siano in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="66b39-146">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="66b39-147">Le istruzioni per l'aggiunta di utenti sono disponibili [qui](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span><span class="sxs-lookup"><span data-stu-id="66b39-147">Instructions for adding users can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span></span>

1. <span data-ttu-id="66b39-148">È consigliabile aggiungere gli utenti che hanno bisogno di licenze simili allo stesso gruppo.</span><span class="sxs-lookup"><span data-stu-id="66b39-148">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="66b39-149">Creare un gruppo</span><span class="sxs-lookup"><span data-stu-id="66b39-149">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="66b39-150">Aggiungere utenti ai gruppi</span><span class="sxs-lookup"><span data-stu-id="66b39-150">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="66b39-151">Verificare che gli utenti (o il gruppo di utenti) della società abbiano le licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="66b39-151">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="66b39-152">Le istruzioni per assegnare le licenze sono disponibili [qui](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span><span class="sxs-lookup"><span data-stu-id="66b39-152">Directions for assigning licenses can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="66b39-153">Eseguire questa procedura solo se gli utenti devono registrare il proprio dispositivo HoloLens/mobile (sono disponibili tre opzioni). Questi passaggi assicurano che gli utenti (o un gruppo di utenti) della società possano aggiungere dispositivi.</span><span class="sxs-lookup"><span data-stu-id="66b39-153">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="66b39-154">**Opzione 1:** consentire a tutti gli utenti di aggiungere dispositivi in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="66b39-154">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="66b39-155">**Accedere al portale di Azure come amministratore** > **Azure Active Directory** > **Dispositivi** > **Impostazioni dei dispositivi** >
**Impostare Gli utenti possono aggiungere dispositivi ad Azure AD su\*Tutti**\*</span><span class="sxs-lookup"><span data-stu-id="66b39-155">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="66b39-156">**Opzione 2:** assegnare a utenti/gruppi selezionati l'autorizzazione per l'aggiunta di dispositivi ad Azure AD **Accedere al portale di Azure come amministratore** > **Azure Active Directory** > **Dispositivi** > **Impostazioni dei dispositivi** >
\*\*Impostare gli utenti possono aggiungere dispositivi ad Azure AD su \*Selezionati\*\*\*
![Immagine che mostra la configurazione dei dispositivi aggiunti ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="66b39-156">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="66b39-157">**Opzione 3:** è possibile impedire a tutti gli utenti di aggiungere i propri dispositivi al dominio.</span><span class="sxs-lookup"><span data-stu-id="66b39-157">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="66b39-158">Questo significa che tutti i dispositivi devono essere registrati manualmente.</span><span class="sxs-lookup"><span data-stu-id="66b39-158">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="66b39-159">Indicazioni per Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="66b39-159">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="66b39-160">Gestione continuativa di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="66b39-160">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="66b39-161">Questo passaggio è necessario solo se la società prevede di gestire HoloLens.</span><span class="sxs-lookup"><span data-stu-id="66b39-161">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="66b39-162">La gestione continuativa dei dispositivi dipenderà dall'infrastruttura di gestione dei dispositivi mobili in uso.</span><span class="sxs-lookup"><span data-stu-id="66b39-162">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="66b39-163">La maggior parte ha le stesse funzionalità generali, ma l'interfaccia utente può variare notevolmente.</span><span class="sxs-lookup"><span data-stu-id="66b39-163">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="66b39-164">[I provider di servizi di configurazione (CSP )](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) consentono di creare e distribuire impostazioni di gestione per i dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="66b39-164">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) allows you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="66b39-165">È possibile trovare un elenco di CPS per HoloLens [qui](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span><span class="sxs-lookup"><span data-stu-id="66b39-165">A list of CSPs for HoloLens can be found [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span>

1. <span data-ttu-id="66b39-166">I [criteri di conformità](https://docs.microsoft.com/intune/device-compliance-get-started) sono regole e impostazioni che i dispositivi devono soddisfare per essere conformi nell'infrastruttura aziendale.</span><span class="sxs-lookup"><span data-stu-id="66b39-166">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="66b39-167">Usare questi criteri insieme all'accesso condizionale per bloccare l'accesso alle risorse aziendali per i dispositivi non conformi.</span><span class="sxs-lookup"><span data-stu-id="66b39-167">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="66b39-168">Ad esempio, è possibile creare un criterio che richiede che BitLocker sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="66b39-168">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="66b39-169">[Creare criteri di conformità](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span><span class="sxs-lookup"><span data-stu-id="66b39-169">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="66b39-170">L'accesso condizionale consente/nega ai dispositivi mobili e alle applicazioni per dispositivi mobili l'accesso alle risorse aziendali.</span><span class="sxs-lookup"><span data-stu-id="66b39-170">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="66b39-171">Due documenti che possono essere utili sono [Procedura: pianificare la distribuzione dell'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) e [Procedure consigliate](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span><span class="sxs-lookup"><span data-stu-id="66b39-171">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="66b39-172">[Questo articolo](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) parla degli strumenti di gestione di Intune per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="66b39-172">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="66b39-173">Creare un profilo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="66b39-173">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="66b39-174">Gestire gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="66b39-174">Manage updates</span></span>

<span data-ttu-id="66b39-175">Intune include una caratteristica denominata Anelli di aggiornamento per i dispositivi Windows 10, tra cui HoloLens 2 e HoloLens V1 (con Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="66b39-175">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="66b39-176">Gli anelli di aggiornamento includono un gruppo di impostazioni che determinano come e quando vengono installati gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="66b39-176">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="66b39-177">Ad esempio, è possibile creare una finestra di manutenzione per installare gli aggiornamenti oppure scegliere di riavviare dopo l'installazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="66b39-177">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="66b39-178">Si può anche scegliere di sospendere gli aggiornamenti a tempo indeterminato finché non si è pronti per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="66b39-178">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="66b39-179">Seguire il link per altre informazioni sulla [configurazione degli anelli di aggiornamento con Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="66b39-179">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="66b39-180">Gestione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="66b39-180">Application management</span></span>

<span data-ttu-id="66b39-181">Gestire le applicazioni di HoloLens tramite:</span><span class="sxs-lookup"><span data-stu-id="66b39-181">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="66b39-182">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="66b39-182">Microsoft Store</span></span>  
  <span data-ttu-id="66b39-183">Microsoft Store è il mezzo migliore per distribuire e usare applicazioni su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="66b39-183">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="66b39-184">Nello Store è già disponibile un'ampia gamma di applicazioni di HoloLens oppure è possibile [pubblicare la propria](https://docs.microsoft.com/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="66b39-184">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="66b39-185">Tutte le applicazioni nello Store sono disponibili pubblicamente per tutti. Se questo non è accettabile, provare Microsoft Store per le aziende.</span><span class="sxs-lookup"><span data-stu-id="66b39-185">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="66b39-186">Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="66b39-186">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="66b39-187">Microsoft Store per le aziende e gli istituti di istruzione è un negozio personalizzato per gli ambienti aziendali.</span><span class="sxs-lookup"><span data-stu-id="66b39-187">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="66b39-188">Consente di usare Microsoft Store integrato in Windows 10 e HoloLens per trovare, acquisire, distribuire e gestire app per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="66b39-188">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="66b39-189">Consente anche di distribuire app specifiche per il proprio ambiente commerciale, ma non a tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="66b39-189">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="66b39-190">Distribuzione e gestione delle applicazioni con Intune o un'altra soluzione di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="66b39-190">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="66b39-191">La maggior parte delle soluzioni di gestione dei dispositivi mobili, tra cui Intune, offre un modo per distribuire applicazioni line-of-business direttamente in un set di dispositivi registrati.</span><span class="sxs-lookup"><span data-stu-id="66b39-191">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="66b39-192">Vedere questo articolo per l'[installazione di app con Intune](https://docs.microsoft.com/intune/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="66b39-192">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="66b39-193">_non consigliato_ Device Portal</span><span class="sxs-lookup"><span data-stu-id="66b39-193">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="66b39-194">Le applicazioni possono anche essere installate direttamente in HoloLens tramite Windows Device Portal.</span><span class="sxs-lookup"><span data-stu-id="66b39-194">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="66b39-195">Questa scelta non è consigliata, perché per usare il portale di dispositivi occorre abilitare la modalità di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="66b39-195">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="66b39-196">Seguire il link per altre informazioni sull[installazione di app in HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span><span class="sxs-lookup"><span data-stu-id="66b39-196">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="66b39-197">Certificati</span><span class="sxs-lookup"><span data-stu-id="66b39-197">Certificates</span></span>

<span data-ttu-id="66b39-198">È possibile distribuire i certificati tramite il provider MDM.</span><span class="sxs-lookup"><span data-stu-id="66b39-198">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="66b39-199">Se la società ha bisogno di certificati, Intune supporta PKCS, PFX e SCEP.</span><span class="sxs-lookup"><span data-stu-id="66b39-199">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="66b39-200">È importante comprendere quale sia il certificato appropriato per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="66b39-200">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="66b39-201">Visitare [questa pagina](https://docs.microsoft.com/intune/protect/certificates-configure) per determinare quale sia la soluzione più adatta alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="66b39-201">Please visit [here](https://docs.microsoft.com/intune/protect/certificates-configure) to determine which cert is best for you.</span></span> <span data-ttu-id="66b39-202">Se si prevede di usare certificati per l'autenticazione di HoloLens, PFX o SCEP può essere la scelta corretta.</span><span class="sxs-lookup"><span data-stu-id="66b39-202">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="66b39-203">La procedura per SCEP è disponibile [qui](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span><span class="sxs-lookup"><span data-stu-id="66b39-203">Steps for SCEP can be found [here](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="66b39-204">Come eseguire l'aggiornamento alla famiglia di prodotti commerciali Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="66b39-204">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="66b39-205">Windows Holographic for Business (famiglia di prodotti commerciali) è inteso solo per i dispositivi HoloLens di prima generazione.</span><span class="sxs-lookup"><span data-stu-id="66b39-205">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="66b39-206">Il profilo non verrà applicato ai dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="66b39-206">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="66b39-207">Le istruzioni per l'aggiornamento alla famiglia di prodotti commerciali sono disponibili [qui](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="66b39-207">Directions for upgrading to the commercial suite can be found [here](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span></span>

### <span data-ttu-id="66b39-208">Come configurare la modalità tutto schermo con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="66b39-208">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="66b39-209">Sincronizzare Microsoft Store con Intune ([vedere qui](https://docs.microsoft.com/intune/apps/windows-store-for-business))</span><span class="sxs-lookup"><span data-stu-id="66b39-209">Sync Microsoft Store to Intune ([Here](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="66b39-210">Controllare le impostazioni dell'app</span><span class="sxs-lookup"><span data-stu-id="66b39-210">Check your app settings</span></span>
    1. <span data-ttu-id="66b39-211">Accedere all'account di Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="66b39-211">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="66b39-212">Gestisci > Prodotti e servizi > App e software > Selezionare l'app che si vuole sincronizzare > Disponibilità archivio privato > Selezionare "Tutti" o "Gruppi specifici"</span><span class="sxs-lookup"><span data-stu-id="66b39-212">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="66b39-213">Se l'app desiderata non viene visualizzata, sarà necessario eseguire una ricerca nel punto vendita per l'app.</span><span class="sxs-lookup"><span data-stu-id="66b39-213">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="66b39-214">**Fare clic sulla barra di ricerca nell'angolo in alto a destra > digitare il nome dell'app > fare clic sull'app > selezionare Ottieni**.</span><span class="sxs-lookup"><span data-stu-id="66b39-214">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="66b39-215">Se le proprie app non sono visibili in **Intune > App client > App**, potrebbe essere necessario [sincronizzare le app](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) di nuovo.</span><span class="sxs-lookup"><span data-stu-id="66b39-215">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="66b39-216">Creare un profilo del dispositivo per la modalità tutto schermo</span><span class="sxs-lookup"><span data-stu-id="66b39-216">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="66b39-217">È possibile configurare utenti diversi per esperienze in modalità tutto schermo diverse usando "Azure AD" come "Tipo di accesso utente".</span><span class="sxs-lookup"><span data-stu-id="66b39-217">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="66b39-218">Tuttavia, questa opzione è disponibile solo in modalità Più app in modalità tutto schermo.</span><span class="sxs-lookup"><span data-stu-id="66b39-218">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="66b39-219">La modalità Più app in modalità tutto schermo funziona sia con una sola app, sia con più app.</span><span class="sxs-lookup"><span data-stu-id="66b39-219">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Immagine che mostra la configurazione della modalità tutto schermo in Intune](images/aad-kioskmode.png)

<span data-ttu-id="66b39-221">Per altri servizi MDM, vedere le istruzioni nella documentazione del provider.</span><span class="sxs-lookup"><span data-stu-id="66b39-221">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="66b39-222">Se è necessario usare un'impostazione personalizzata e una configurazione XML completa per configurare un chiosco nel dispositivo MDM, altre indicazioni sono disponibili [qui](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span><span class="sxs-lookup"><span data-stu-id="66b39-222">If you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service, additional directions can be found [here](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span></span>

## <span data-ttu-id="66b39-223">Certificati e autenticazione</span><span class="sxs-lookup"><span data-stu-id="66b39-223">Certificates and Authentication</span></span>

<span data-ttu-id="66b39-224">I certificati possono essere distribuiti tramite MDM (vedere "certificati" nella [sezione MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span><span class="sxs-lookup"><span data-stu-id="66b39-224">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="66b39-225">È anche possibile distribuire certificati al dispositivo HoloLens mediante il provisioning di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="66b39-225">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="66b39-226">Per altre informazioni, vedere [Provisioning di HoloLens](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="66b39-226">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="66b39-227">Altri collegamenti rapidi di Intune</span><span class="sxs-lookup"><span data-stu-id="66b39-227">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="66b39-228">[Creare profili:](https://docs.microsoft.com/intune/configuration/device-profile-create) i profili consentono di aggiungere e configurare impostazioni che verranno inviate ai dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="66b39-228">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

