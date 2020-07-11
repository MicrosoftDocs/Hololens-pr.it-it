---
title: Configurare HoloLens in un ambiente commerciale
description: Leggi altre informazioni su come distribuire e gestire HoloLens in ambienti aziendali.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865565"
---
# <span data-ttu-id="d49ba-103">Distribuire HoloLens in un ambiente commerciale</span><span class="sxs-lookup"><span data-stu-id="d49ba-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="d49ba-104">È possibile distribuire e configurare HoloLens in scala in un'impostazione commerciale.</span><span class="sxs-lookup"><span data-stu-id="d49ba-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="d49ba-105">Questo articolo fornisce istruzioni per la distribuzione di dispositivi HoloLens in un ambiente commerciale.</span><span class="sxs-lookup"><span data-stu-id="d49ba-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="d49ba-106">Questa guida presuppone familiarità di base con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d49ba-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="d49ba-107">Seguire la [Guida introduttiva](hololens1-setup.md) per configurare HoloLens per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="d49ba-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="d49ba-108">Questo documento presuppone inoltre che HoloLens sia stato valutato da team di sicurezza come sicuro da usare nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="d49ba-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span>  
> [!Tip]
> <span data-ttu-id="d49ba-109">Leggi altre informazioni sulla [sicurezza di HoloLens](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d49ba-109">Learn more about [HoloLens security](security-overview.md).</span></span>
> <span data-ttu-id="d49ba-110">Per la sicurezza di HoloLens (1a generazione), consultare le [domande frequenti](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="d49ba-110">For HoloLens (1st Gen) security please review [this FAQ](hololens1-faq-security.md).</span></span>

## <span data-ttu-id="d49ba-111">Panoramica dei passaggi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="d49ba-111">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="d49ba-112">Determinare le caratteristiche necessarie</span><span class="sxs-lookup"><span data-stu-id="d49ba-112">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="d49ba-113">Determinare le licenze necessarie</span><span class="sxs-lookup"><span data-stu-id="d49ba-113">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="d49ba-114">[Configurare la rete per HoloLens](hololens-commercial-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="d49ba-114">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="d49ba-115">Questa sezione include requisiti di larghezza di banda, URL e porte che devono essere consentiti nel firewall. Linee guida di Azure AD; Linee guida per la gestione di dispositivi mobili (MDM); Guida alla distribuzione/gestione delle app; e indicazioni per i certificati.</span><span class="sxs-lookup"><span data-stu-id="d49ba-115">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="d49ba-116">Opzionale [Configurare HoloLens usando un pacchetto di provisioning](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="d49ba-116">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="d49ba-117">Dispositivo di registrazione</span><span class="sxs-lookup"><span data-stu-id="d49ba-117">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="d49ba-118">Configurare gli aggiornamenti basati su anello per HoloLens</span><span class="sxs-lookup"><span data-stu-id="d49ba-118">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="d49ba-119">Abilitare la crittografia dispositivo Bitlocker per HoloLens</span><span class="sxs-lookup"><span data-stu-id="d49ba-119">Enable Bitlocker device encryption for HoloLens</span></span>](security-encryption-data-protection.md)

## <span data-ttu-id="d49ba-120">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d49ba-120">Step 1.</span></span> <span data-ttu-id="d49ba-121">Determinare le informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="d49ba-121">Determine what you need</span></span>

<span data-ttu-id="d49ba-122">Prima di distribuire il HoloLens nell'ambiente, è importante determinare prima quali caratteristiche, app e tipo di identità sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="d49ba-122">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="d49ba-123">È anche importante assicurarsi che il team di sicurezza abbia approvato l'uso della HoloLens nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="d49ba-123">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="d49ba-124">Per altre informazioni sulla sicurezza, vedere [sicurezza di HoloLens2](security-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="d49ba-124">Please see [HoloLens2 security](security-overview.md) for additional security information.</span></span>

### <span data-ttu-id="d49ba-125">Tipo di identità</span><span class="sxs-lookup"><span data-stu-id="d49ba-125">Type of Identity</span></span>

<span data-ttu-id="d49ba-126">Determinare il tipo di identità che verrà usata per accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d49ba-126">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="d49ba-127">**Account locali:** Questo account è locale per il dispositivo, ad esempio un account di amministratore locale in un PC Windows.</span><span class="sxs-lookup"><span data-stu-id="d49ba-127">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="d49ba-128">In questo modo sarà possibile accedere al dispositivo solo 1 utente.</span><span class="sxs-lookup"><span data-stu-id="d49ba-128">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="d49ba-129">**MSA:** Si tratta di un account personale (ad esempio Outlook, Hotmail, Gmail, Yahoo e così via) In questo modo sarà possibile accedere al dispositivo solo 1 utente.</span><span class="sxs-lookup"><span data-stu-id="d49ba-129">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="d49ba-130">**Account di Azure Active Directory (Azure ad):** Si tratta di un account creato in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d49ba-130">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="d49ba-131">Questo garantisce alla tua azienda la possibilità di gestire il dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d49ba-131">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="d49ba-132">Ciò consentirà a più utenti di accedere alla HoloLens 1a gen Commercial Suite/il dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d49ba-132">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="d49ba-133">Per informazioni più dettagliate sui tipi di identità, vedere l'articolo sull' [identità di HoloLens](hololens-identity.md) .</span><span class="sxs-lookup"><span data-stu-id="d49ba-133">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="d49ba-134">Tipo di funzionalità</span><span class="sxs-lookup"><span data-stu-id="d49ba-134">Type of Features</span></span>

<span data-ttu-id="d49ba-135">I requisiti della funzionalità determineranno le HoloLens necessarie.</span><span class="sxs-lookup"><span data-stu-id="d49ba-135">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="d49ba-136">Una caratteristica popolare che vediamo distribuita in ambienti cliente è spesso la modalità Kiosk.</span><span class="sxs-lookup"><span data-stu-id="d49ba-136">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="d49ba-137">[Qui](hololens-commercial-features.md)è possibile trovare un elenco delle caratteristiche principali di HoloLens e le edizioni di HoloLens che le supportano.</span><span class="sxs-lookup"><span data-stu-id="d49ba-137">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="d49ba-138">Che cos'è la modalità Kiosk?</span><span class="sxs-lookup"><span data-stu-id="d49ba-138">What is Kiosk Mode?</span></span>**

<span data-ttu-id="d49ba-139">La modalità Kiosk è un modo per limitare le app a cui un utente ha accesso.</span><span class="sxs-lookup"><span data-stu-id="d49ba-139">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="d49ba-140">Questo significa che agli utenti sarà consentito accedere solo ad alcune app.</span><span class="sxs-lookup"><span data-stu-id="d49ba-140">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="d49ba-141">Quale modalità Kiosk è necessaria?</span><span class="sxs-lookup"><span data-stu-id="d49ba-141">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="d49ba-142">Esistono due tipi di modalità Kiosk: Single app e multi-app.</span><span class="sxs-lookup"><span data-stu-id="d49ba-142">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="d49ba-143">La modalità single app Kiosk consente all'utente di accedere a un'app solo mentre la modalità Kiosk multiapp consente agli utenti di accedere a più app specificate.</span><span class="sxs-lookup"><span data-stu-id="d49ba-143">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="d49ba-144">Per determinare la modalità Kiosk appropriata per la propria società, è necessario rispondere alle due domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="d49ba-144">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="d49ba-145">Gli utenti diversi richiedono diverse esperienze/restrizioni?</span><span class="sxs-lookup"><span data-stu-id="d49ba-145">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="d49ba-146">Si consideri l'esempio seguente: l'utente A è un ingegnere del servizio di campo che deve solo accedere a Remote assist.</span><span class="sxs-lookup"><span data-stu-id="d49ba-146">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="d49ba-147">L'utente B è un tirocinante che deve accedere solo alle guide.</span><span class="sxs-lookup"><span data-stu-id="d49ba-147">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="d49ba-148">In caso affermativo, sarà necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d49ba-148">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="d49ba-149">Account di Azure AD come metodo di accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d49ba-149">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="d49ba-150">Modalità Kiosk **multi-app** .</span><span class="sxs-lookup"><span data-stu-id="d49ba-150">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="d49ba-151">Se no, continuare a interrogare due</span><span class="sxs-lookup"><span data-stu-id="d49ba-151">If no, continue to question two</span></span>
1. **<span data-ttu-id="d49ba-152">Hai bisogno di un'esperienza multi-app?</span><span class="sxs-lookup"><span data-stu-id="d49ba-152">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="d49ba-153">Se sì, è necessaria la modalità chiosco **multi-app**</span><span class="sxs-lookup"><span data-stu-id="d49ba-153">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="d49ba-154">Se la risposta alla domanda 1 e 2 non è disponibile, è possibile usare la modalità chiosco **Single-app**</span><span class="sxs-lookup"><span data-stu-id="d49ba-154">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="d49ba-155">Come configurare la modalità Kiosk:</span><span class="sxs-lookup"><span data-stu-id="d49ba-155">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="d49ba-156">Esistono due modi principali ([provisioning Packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) e [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) per distribuire la modalità Kiosk per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d49ba-156">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="d49ba-157">Queste opzioni verranno discusse più avanti nel documento; Tuttavia, è possibile usare i collegamenti descritti sopra per passare alle rispettive sezioni di questo documento.</span><span class="sxs-lookup"><span data-stu-id="d49ba-157">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="d49ba-158">App e scenari specifici delle app</span><span class="sxs-lookup"><span data-stu-id="d49ba-158">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="d49ba-159">La maggior parte dei passaggi trovati in questo documento si applica anche alle app seguenti:</span><span class="sxs-lookup"><span data-stu-id="d49ba-159">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="d49ba-160">App</span><span class="sxs-lookup"><span data-stu-id="d49ba-160">App</span></span> | <span data-ttu-id="d49ba-161">Scenari specifici dell'app</span><span class="sxs-lookup"><span data-stu-id="d49ba-161">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="d49ba-162">Assistenza remota</span><span class="sxs-lookup"><span data-stu-id="d49ba-162">Remote Assist</span></span> | [<span data-ttu-id="d49ba-163">Comunicazione tra tenant</span><span class="sxs-lookup"><span data-stu-id="d49ba-163">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="d49ba-164">Guide</span><span class="sxs-lookup"><span data-stu-id="d49ba-164">Guides</span></span>  | *<span data-ttu-id="d49ba-165">Prossimamente</span><span class="sxs-lookup"><span data-stu-id="d49ba-165">Coming Soon</span></span>* |
|<span data-ttu-id="d49ba-166">App personalizzate</span><span class="sxs-lookup"><span data-stu-id="d49ba-166">Custom Apps</span></span> | *<span data-ttu-id="d49ba-167">Prossimamente</span><span class="sxs-lookup"><span data-stu-id="d49ba-167">Coming Soon</span></span>* |

### <span data-ttu-id="d49ba-168">Determinare il metodo di registrazione</span><span class="sxs-lookup"><span data-stu-id="d49ba-168">Determine your enrollment method</span></span>

1. <span data-ttu-id="d49ba-169">Registrazione in blocco con un token di sicurezza in un pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="d49ba-169">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="d49ba-170">Vantaggi: questo è l'approccio più automatizzato </span><span class="sxs-lookup"><span data-stu-id="d49ba-170">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="d49ba-171">Svantaggi: richiede l'installazione iniziale sul lato server</span><span class="sxs-lookup"><span data-stu-id="d49ba-171">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="d49ba-172">Registrazione automatica all'accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d49ba-172">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="d49ba-173">Vantaggi: approccio più semplice</span><span class="sxs-lookup"><span data-stu-id="d49ba-173">Pros: easiest approach</span></span>  
  <span data-ttu-id="d49ba-174">Svantaggi: gli utenti dovranno completare la configurazione dopo l'applicazione del pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="d49ba-174">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="d49ba-175">_sconsigliato: registrare_ manualmente la registrazione post-installazione.</span><span class="sxs-lookup"><span data-stu-id="d49ba-175">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="d49ba-176">Vantaggi: possibile iscriversi dopo la configurazione</span><span class="sxs-lookup"><span data-stu-id="d49ba-176">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="d49ba-177">Svantaggi: la maggior parte degli approcci manuali e dei dispositivi non è gestibile centralmente fino a quando non viene registrato manualmente.</span><span class="sxs-lookup"><span data-stu-id="d49ba-177">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="d49ba-178">Altre informazioni possono essere trovate [qui](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="d49ba-178">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="d49ba-179">Determinare se è necessario creare un pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="d49ba-179">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="d49ba-180">Esistono due metodi per configurare un dispositivo HoloLens (provisioning packages and MDMs).</span><span class="sxs-lookup"><span data-stu-id="d49ba-180">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="d49ba-181">Ti consigliamo di usare MDM per configurare il dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d49ba-181">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="d49ba-182">Tuttavia, esistono alcuni scenari in cui l'uso di un pacchetto di provisioning è la scelta migliore:</span><span class="sxs-lookup"><span data-stu-id="d49ba-182">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="d49ba-183">Si vuole configurare HoloLens per ignorare l'esperienza della casella fuori sede (OOBE)</span><span class="sxs-lookup"><span data-stu-id="d49ba-183">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="d49ba-184">Si verificano problemi durante la distribuzione di certificati in una rete complessa.</span><span class="sxs-lookup"><span data-stu-id="d49ba-184">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="d49ba-185">La maggior parte del tempo è possibile distribuire i certificati con MDM (anche in ambienti complessi).</span><span class="sxs-lookup"><span data-stu-id="d49ba-185">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="d49ba-186">Tuttavia, alcuni scenari richiedono la distribuzione di certificati tramite il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="d49ba-186">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="d49ba-187">Alcune delle configurazioni di HoloLens che è possibile applicare in un pacchetto di provisioning:</span><span class="sxs-lookup"><span data-stu-id="d49ba-187">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="d49ba-188">Applicare certificati al dispositivo</span><span class="sxs-lookup"><span data-stu-id="d49ba-188">Apply certificates to the device</span></span>
- <span data-ttu-id="d49ba-189">Configurare una connessione Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d49ba-189">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="d49ba-190">Configurare le domande predefinite come lingua e impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="d49ba-190">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="d49ba-191">(HoloLens 2) Registrare in blocco la gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="d49ba-191">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="d49ba-192">(HoloLens V1) Applicare la chiave per attivare Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="d49ba-192">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="d49ba-193">Se si decide di usare i pacchetti di provisioning, seguire [questa guida](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="d49ba-193">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="d49ba-194">Ottieni supporto</span><span class="sxs-lookup"><span data-stu-id="d49ba-194">Get support</span></span>

<span data-ttu-id="d49ba-195">Ottenere supporto tramite il sito del supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d49ba-195">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="d49ba-196">Presentare una richiesta di supporto</span><span class="sxs-lookup"><span data-stu-id="d49ba-196">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
