---
title: Linee guida per l'infrastruttura HoloLens
description: Informazioni sulle linee guida dell'infrastruttura per HoloLens, tra cui il supporto di rete wireless, l'assistenza remota e la gestione dei dispositivi mobili.
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
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639285"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="c6ba3-103">Configurare la rete per HoloLens</span><span class="sxs-lookup"><span data-stu-id="c6ba3-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="c6ba3-104">Questa parte del documento richiederà le persone seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6ba3-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="c6ba3-105">Amministratore di rete con autorizzazioni per apportare modifiche al proxy/firewall</span><span class="sxs-lookup"><span data-stu-id="c6ba3-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="c6ba3-106">Azure Active Directory Admin</span><span class="sxs-lookup"><span data-stu-id="c6ba3-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="c6ba3-107">Amministratore di Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="c6ba3-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="c6ba3-108">Requisiti dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="c6ba3-108">Infrastructure Requirements</span></span>

<span data-ttu-id="c6ba3-109">HoloLens è, alla base, un dispositivo Windows dispositivo mobile integrato con Azure.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="c6ba3-110">Funziona meglio negli ambienti commerciali con disponibilità di rete wireless (wi-fi) e accesso a servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="c6ba3-111">I servizi cloud critici includono:</span><span class="sxs-lookup"><span data-stu-id="c6ba3-111">Critical cloud services include:</span></span>

- <span data-ttu-id="c6ba3-112">Azure active directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="c6ba3-113">Windows Aggiornamento (WU)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-113">Windows Update (WU)</span></span>

<span data-ttu-id="c6ba3-114">I clienti commerciali avranno bisogno di un'infrastruttura EMM (Enterprise Mobility Management) o MDM (Mobile Device Management) per gestire HoloLens dispositivi su larga scala.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="c6ba3-115">Questa guida [usa](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) Microsoft Intune esempio, anche se qualsiasi provider con supporto completo per Criteri Microsoft può supportare HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="c6ba3-116">Chiedere al provider di gestione dei dispositivi mobili se supporta HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="c6ba3-117">HoloLens supporta un set limitato di esperienze disconnesse dal cloud.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="c6ba3-118">Supporto EAP per la rete wireless</span><span class="sxs-lookup"><span data-stu-id="c6ba3-118">Wireless network EAP support</span></span>

- <span data-ttu-id="c6ba3-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="c6ba3-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="c6ba3-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="c6ba3-120">PEAP-TLS</span></span>
- <span data-ttu-id="c6ba3-121">TLS</span><span class="sxs-lookup"><span data-stu-id="c6ba3-121">TLS</span></span>
- <span data-ttu-id="c6ba3-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="c6ba3-122">TTLS-CHAP</span></span>
- <span data-ttu-id="c6ba3-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="c6ba3-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="c6ba3-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="c6ba3-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="c6ba3-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="c6ba3-125">TTLS-PAP</span></span>
- <span data-ttu-id="c6ba3-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="c6ba3-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="c6ba3-127">HoloLens Requisiti di rete specifici</span><span class="sxs-lookup"><span data-stu-id="c6ba3-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="c6ba3-128">Assicurarsi che [questo elenco di](hololens-offline.md) endpoint sia consentito nel firewall di rete.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="c6ba3-129">In questo modo HoloLens funzionerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="c6ba3-130">Remote Assist requisiti di rete specifici</span><span class="sxs-lookup"><span data-stu-id="c6ba3-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="c6ba3-131">La larghezza di banda consigliata per prestazioni ottimali Remote Assist è di 1,5 Mbps.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="c6ba3-132">Per altre [informazioni, vedere i requisiti di](/MicrosoftTeams/prepare-network) rete dettagliati.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-132">See the [detailed network requirements](/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="c6ba3-133">**Si noti che se non si ha una velocità di rete di almeno 1,5 Mbps, Remote Assist funzionerà ancora. Tuttavia, la qualità può risentire).**</span><span class="sxs-lookup"><span data-stu-id="c6ba3-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="c6ba3-134">Assicurarsi che queste porte e URL siano consentiti nel firewall di rete per consentire Microsoft Teams funzionamento.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="c6ba3-135">Rimanere aggiornati con [l'elenco più recente delle porte](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="c6ba3-135">Stay up to date with the [latest list of ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="c6ba3-136">Altre informazioni sui requisiti di [rete specifici per Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="c6ba3-136">Learn more about the specific [Network Requirements for Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="c6ba3-137">Altre informazioni su come [preparare la rete dell'organizzazione per l'Microsoft Teams](/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-137">Learn more about how to [prepare your organization's network for Microsoft Teams](/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="c6ba3-138">Guide requisiti di rete specifici</span><span class="sxs-lookup"><span data-stu-id="c6ba3-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="c6ba3-139">Le guide richiedono solo l'accesso alla rete per scaricare e usare l'app.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="c6ba3-140">Azure Active Directory Guida</span><span class="sxs-lookup"><span data-stu-id="c6ba3-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="c6ba3-141">Questo passaggio è necessario solo se l'azienda prevede di gestire il HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="c6ba3-142">Assicurarsi di avere una licenza Azure AD licenza.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="c6ba3-143">Per [altre informazioni, HoloLens requisiti](hololens-licenses-requirements.md) per le licenze.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="c6ba3-144">Se si prevede di usare la registrazione automatica, sarà necessario configurare Azure AD [registrazione automatica.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="c6ba3-145">Assicurarsi che gli utenti dell'azienda siano Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c6ba3-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="c6ba3-146">Vedere le istruzioni [seguenti per](/azure/active-directory/fundamentals/add-users-azure-active-directory) l'aggiunta di utenti.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-146">See the following [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="c6ba3-147">È consigliabile aggiungere utenti che necessitano di licenze simili allo stesso gruppo.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="c6ba3-148">Creare un gruppo</span><span class="sxs-lookup"><span data-stu-id="c6ba3-148">Create a Group</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="c6ba3-149">Aggiungere utenti ai gruppi</span><span class="sxs-lookup"><span data-stu-id="c6ba3-149">Add users to groups</span></span>](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="c6ba3-150">Assicurarsi che agli utenti dell'azienda (o al gruppo di utenti) siano assegnate le licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="c6ba3-151">Se è necessario assegnare licenze, seguire queste [istruzioni.](/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-151">If you need to assign licenses, follow these [directions](/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="c6ba3-152">Eseguire questo passaggio solo se si prevede che gli utenti enroll their HoloLens/Mobile device into you (There are three options) Questi passaggi garantiscono che gli utenti dell'azienda (o un gruppo di utenti) possano aggiungere dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="c6ba3-153">**Opzione 1:** Concedere a tutti gli utenti l'autorizzazione per aggiungere dispositivi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="c6ba3-154">**Accedere al portale di Azure come amministratore**  >  **Azure Active Directory**  >  **Dispositivi**  >  **Dispositivi Impostazioni**  >
 **Impostare Utenti che possono aggiungere dispositivi Azure AD su *Tutti***</span><span class="sxs-lookup"><span data-stu-id="c6ba3-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="c6ba3-155">**Opzione 2:** Concedere a utenti/gruppi selezionati l'autorizzazione per aggiungere dispositivi a Azure AD Accedere al **portale di Azure** come amministratore  >  **Azure Active Directory**  >  **Dispositivi** dispositivo  >  **Impostazioni**  >
 **Impostare** 
 ![ gli utenti possono aggiungere dispositivi a Azure AD a Immagine selezionata che mostra La configurazione dei dispositivi aggiunti Azure AD](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="c6ba3-156">**Opzione 3:** È possibile impedire a tutti gli utenti di aggiungere i propri dispositivi al dominio.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="c6ba3-157">Ciò significa che tutti i dispositivi dovranno essere registrati manualmente.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="c6ba3-158">Linee guida per Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="c6ba3-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="c6ba3-159">Gestione continua dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="c6ba3-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="c6ba3-160">Questo passaggio è necessario solo se l'azienda prevede di gestire il HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="c6ba3-161">La gestione continua dei dispositivi dipende dall'infrastruttura di gestione dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="c6ba3-162">La maggior parte ha la stessa funzionalità generale, ma l'interfaccia utente può variare notevolmente.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="c6ba3-163">[I provider di servizi di](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) configurazione (Provider di servizi di configurazione) consentono di creare e distribuire le impostazioni di gestione per i dispositivi nella rete.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-163">[CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="c6ba3-164">Vedere [l'elenco di HoloLens CSP per](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) informazioni di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-164">See the [list of HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="c6ba3-165">[I criteri di](/intune/device-compliance-get-started) conformità sono regole e impostazioni che i dispositivi devono soddisfare per essere conformi nell'infrastruttura aziendale.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-165">[Compliance policies](/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="c6ba3-166">Usare questi criteri con l'accesso condizionale per bloccare l'accesso alle risorse aziendali per i dispositivi non conformi.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="c6ba3-167">È possibile ad esempio creare un criterio che richiede l'abilitazione di Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="c6ba3-168">[Creare criteri di conformità](/intune/protect/compliance-policy-create-windows).</span><span class="sxs-lookup"><span data-stu-id="c6ba3-168">[Create Compliance Policy](/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="c6ba3-169">L'accesso condizionale consente o nega ai dispositivi mobili e alle applicazioni mobili di accedere alle risorse aziendali.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="c6ba3-170">Due documenti che possono risultare utili sono [Pianificare la distribuzione della CA](/azure/active-directory/conditional-access/plan-conditional-access) e Procedure [consigliate.](/azure/active-directory/conditional-access/best-practices)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-170">Two documents you may find helpful are [Plan your CA Deployment](/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="c6ba3-171">[Questo articolo](/intune/fundamentals/windows-holographic-for-business) illustra gli strumenti di gestione di Intune per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-171">[This article](/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="c6ba3-172">Creare un profilo di dispositivo</span><span class="sxs-lookup"><span data-stu-id="c6ba3-172">Create a device profile</span></span>](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="c6ba3-173">Gestire gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="c6ba3-173">Manage updates</span></span>

<span data-ttu-id="c6ba3-174">Intune include una funzionalità denominata Anelli di aggiornamento per Windows 10 dispositivi, tra cui HoloLens 2 e HoloLens v1 (con Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="c6ba3-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="c6ba3-175">Gli anelli di aggiornamento includono un gruppo di impostazioni che determinano come e quando vengono installati gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="c6ba3-176">È possibile ad esempio creare una finestra di manutenzione per installare gli aggiornamenti o scegliere di riavviare dopo l'installazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="c6ba3-177">È anche possibile scegliere di sospendere gli aggiornamenti a tempo indeterminato fino a quando non si è pronti per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="c6ba3-178">Altre informazioni sulla [configurazione degli anelli di aggiornamento con Intune.](/intune/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-178">Read more about [configuring update rings with Intune](/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="c6ba3-179">Gestione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="c6ba3-179">Application management</span></span>

<span data-ttu-id="c6ba3-180">Gestire HoloLens applicazioni tramite:</span><span class="sxs-lookup"><span data-stu-id="c6ba3-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="c6ba3-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="c6ba3-181">Microsoft Store</span></span>  
  <span data-ttu-id="c6ba3-182">Il Microsoft Store è il modo migliore per distribuire e usare le applicazioni HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="c6ba3-183">È disponibile un ottimo set di HoloLens di base già disponibili nello store oppure è possibile [pubblicare il proprio](/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="c6ba3-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="c6ba3-184">Tutte le applicazioni nello Store sono disponibili pubblicamente per tutti, ma se non è accettabile, eseguire il check-Microsoft Store per le aziende.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="c6ba3-185">Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="c6ba3-185">Microsoft Store for Business</span></span>](/microsoft-store/)  
  <span data-ttu-id="c6ba3-186">Microsoft Store per le aziende e Education è un archivio personalizzato per l'ambiente aziendale.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="c6ba3-187">Consente di usare i Microsoft Store predefiniti Windows 10 e HoloLens per trovare, acquisire, distribuire e gestire le app per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="c6ba3-188">Consente anche di distribuire app specifiche per l'ambiente commerciale, ma non per il mondo.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="c6ba3-189">Distribuzione e gestione di applicazioni tramite Intune o un'altra soluzione di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c6ba3-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="c6ba3-190">La maggior parte delle soluzioni di gestione dei dispositivi mobili, tra cui Intune, offre un modo per distribuire le applicazioni line-of-business direttamente in un set di dispositivi registrati.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="c6ba3-191">Vedere questo articolo per [l'installazione dell'app Intune.](/intune/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-191">See this article for [Intune app install](/intune/apps-deploy).</span></span>

1. <span data-ttu-id="c6ba3-192">_sconsigliato_ Portale di dispositivi</span><span class="sxs-lookup"><span data-stu-id="c6ba3-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="c6ba3-193">Le applicazioni possono anche essere installate HoloLens direttamente usando il Windows Portale di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="c6ba3-194">Questa operazione non è consigliata perché la modalità sviluppatore deve essere abilitata per l'uso del portale dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="c6ba3-195">Altre informazioni [sull'installazione di app in HoloLens](hololens-install-apps.md).</span><span class="sxs-lookup"><span data-stu-id="c6ba3-195">Read more about [installing apps on HoloLens](hololens-install-apps.md).</span></span>

### <a name="certificates"></a><span data-ttu-id="c6ba3-196">Certificati</span><span class="sxs-lookup"><span data-stu-id="c6ba3-196">Certificates</span></span>

<span data-ttu-id="c6ba3-197">È possibile distribuire i certificati tramite il provider MDM.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="c6ba3-198">Se l'azienda richiede certificati, Intune supporta PKCS, PFX e SCEP.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="c6ba3-199">È importante comprendere quale certificato è più giusto per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="c6ba3-200">Visitare la documentazione [relativa alle configurazioni](/intune/protect/certificates-configure) dei certificati per determinare quale certificato è più adatto alle specifiche.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-200">Please visit the [certificate configurations](/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="c6ba3-201">Se si prevede di usare i certificati per HoloLens autenticazione, PFX o SCEP potrebbe essere la scelta giusta.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="c6ba3-202">Per l'uso di [SCEP,](/intune/protect/certificates-profile-scep)vedere la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-202">See the following steps for using [SCEP](/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="c6ba3-203">Come eseguire l'aggiornamento a Holographics for Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="c6ba3-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="c6ba3-204">Windows Holographics for Business (suite commerciale) è destinato solo HoloLens dispositivi di prima generazione.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="c6ba3-205">Il profilo non verrà applicato ai HoloLens 2 mobili.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="c6ba3-206">Le istruzioni per l'aggiornamento alla suite commerciale sono disponibili nella documentazione [sull'aggiornamento olografico.](/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="c6ba3-207">Come configurare la modalità tutto schermo usando Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c6ba3-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="c6ba3-208">Sincronizzare Microsoft Store con Intune (vedere le istruzioni [seguenti).](/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-208">Sync Microsoft Store to Intune (See the following [instructions](/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="c6ba3-209">Controllare le impostazioni dell'app</span><span class="sxs-lookup"><span data-stu-id="c6ba3-209">Check your app settings</span></span>
    1. <span data-ttu-id="c6ba3-210">Accedere all'account Microsoft Store Business</span><span class="sxs-lookup"><span data-stu-id="c6ba3-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="c6ba3-211">**Manage > Products and Services > Apps and Software > Selezionare l'app da sincronizzare > Private Store Availability > Select "Everyone" (Tutti) o "Gruppi specifici"**</span><span class="sxs-lookup"><span data-stu-id="c6ba3-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="c6ba3-212">Se l'app desiderata non è visualizzata, sarà necessario "ottenere" l'app cercando l'app nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="c6ba3-213">Fare clic sulla barra "Cerca" nell'angolo superiore destro > digitare il nome dell'app > fare clic **sull'app > selezionare "Ottieni".**</span><span class="sxs-lookup"><span data-stu-id="c6ba3-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="c6ba3-214">Se le app in **Intune** non vengono > app client >, potrebbe essere necessario [sincronizzare di nuovo le](/intune/apps/windows-store-for-business#synchronize-apps) app.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="c6ba3-215">Creare un profilo di dispositivo per la modalità tutto schermo</span><span class="sxs-lookup"><span data-stu-id="c6ba3-215">Create a device profile for Kiosk mode</span></span>](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="c6ba3-216">È possibile configurare utenti diversi in modo da avere esperienze diverse in modalità tutto schermo usando "Azure AD" come "Tipo di accesso utente".</span><span class="sxs-lookup"><span data-stu-id="c6ba3-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="c6ba3-217">Questa opzione è tuttavia disponibile solo in modalità tutto schermo multi-app.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="c6ba3-218">La modalità tutto schermo multi-app funzionerà con una sola app e con più app.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Immagine che mostra la configurazione della modalità tutto schermo in Intune](images/aad-kioskmode.png)

<span data-ttu-id="c6ba3-220">Per altri servizi MDM, consultare la documentazione del provider per istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="c6ba3-221">Fare riferimento alle istruzioni [HoloLens chiosco](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) multimediale se è necessario usare un'impostazione personalizzata e una configurazione XML completa per configurare un chiosco multimediale nel servizio MDM.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="c6ba3-222">Certificati e autenticazione</span><span class="sxs-lookup"><span data-stu-id="c6ba3-222">Certificates and Authentication</span></span>

<span data-ttu-id="c6ba3-223">I certificati possono essere distribuiti tramite MDM (vedere "certificati" nella [sezione MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span><span class="sxs-lookup"><span data-stu-id="c6ba3-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="c6ba3-224">I certificati possono anche essere distribuiti nell'HoloLens tramite il provisioning dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="c6ba3-225">Per altre [informazioni, HoloLens provisioning.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="c6ba3-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="c6ba3-226">Collegamenti rapidi di Intune aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="c6ba3-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="c6ba3-227">[Creare profili:](/intune/configuration/device-profile-create) I profili consentono di aggiungere e configurare le impostazioni di cui verrà inserito il push nei dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6ba3-227">[Create Profiles:](/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

