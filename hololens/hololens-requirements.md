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
ms.openlocfilehash: 8aa8e0f679ad18a2e47f34c5f1233435a502dc0c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830130"
---
# <span data-ttu-id="5cbd3-103">Distribuire HoloLens in un ambiente commerciale</span><span class="sxs-lookup"><span data-stu-id="5cbd3-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="5cbd3-104">È possibile distribuire e configurare HoloLens in scala in un'impostazione commerciale.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="5cbd3-105">Questo articolo fornisce istruzioni per la distribuzione di dispositivi HoloLens in un ambiente commerciale.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="5cbd3-106">Questa guida presuppone familiarità di base con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="5cbd3-107">Seguire la [Guida introduttiva](hololens1-setup.md) per configurare HoloLens per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="5cbd3-108">Questo documento presuppone inoltre che HoloLens sia stato valutato da team di sicurezza come sicuro da usare nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span> <span data-ttu-id="5cbd3-109">Le domande di sicurezza più frequenti possono essere trovate [qui](hololens-faq-security.md)</span><span class="sxs-lookup"><span data-stu-id="5cbd3-109">Frequently asked security questions can be found [here](hololens-faq-security.md)</span></span>

## <span data-ttu-id="5cbd3-110">Panoramica dei passaggi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="5cbd3-110">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="5cbd3-111">Determinare le caratteristiche necessarie</span><span class="sxs-lookup"><span data-stu-id="5cbd3-111">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="5cbd3-112">Determinare le licenze necessarie</span><span class="sxs-lookup"><span data-stu-id="5cbd3-112">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="5cbd3-113">[Configurare la rete per HoloLens](hololens-commercial-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="5cbd3-113">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="5cbd3-114">Questa sezione include requisiti di larghezza di banda, URL e porte che devono essere consentiti nel firewall. Linee guida di Azure AD; Linee guida per la gestione di dispositivi mobili (MDM); Guida alla distribuzione/gestione delle app; e indicazioni per i certificati.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-114">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="5cbd3-115">Opzionale [Configurare HoloLens usando un pacchetto di provisioning](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="5cbd3-115">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="5cbd3-116">Dispositivo di registrazione</span><span class="sxs-lookup"><span data-stu-id="5cbd3-116">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="5cbd3-117">Configurare gli aggiornamenti basati su anello per HoloLens</span><span class="sxs-lookup"><span data-stu-id="5cbd3-117">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="5cbd3-118">Abilitare la crittografia dispositivo Bitlocker per HoloLens</span><span class="sxs-lookup"><span data-stu-id="5cbd3-118">Enable Bitlocker device encryption for HoloLens</span></span>](hololens-encryption.md)

## <span data-ttu-id="5cbd3-119">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-119">Step 1.</span></span> <span data-ttu-id="5cbd3-120">Determinare le informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="5cbd3-120">Determine what you need</span></span>

<span data-ttu-id="5cbd3-121">Prima di distribuire il HoloLens nell'ambiente, è importante determinare prima quali caratteristiche, app e tipo di identità sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-121">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="5cbd3-122">È anche importante assicurarsi che il team di sicurezza abbia approvato l'uso della HoloLens nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-122">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="5cbd3-123">Per altre informazioni sulla sicurezza, vedere [domande frequenti sulla sicurezza](hololens-faq-security.md) .</span><span class="sxs-lookup"><span data-stu-id="5cbd3-123">Please see [Frequently ask security questions](hololens-faq-security.md) for additional security information.</span></span>

### <span data-ttu-id="5cbd3-124">Tipo di identità</span><span class="sxs-lookup"><span data-stu-id="5cbd3-124">Type of Identity</span></span>

<span data-ttu-id="5cbd3-125">Determinare il tipo di identità che verrà usata per accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-125">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="5cbd3-126">**Account locali:** Questo account è locale per il dispositivo, ad esempio un account di amministratore locale in un PC Windows.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-126">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="5cbd3-127">In questo modo sarà possibile accedere al dispositivo solo 1 utente.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-127">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="5cbd3-128">**MSA:** Si tratta di un account personale (ad esempio Outlook, Hotmail, Gmail, Yahoo e così via) In questo modo sarà possibile accedere al dispositivo solo 1 utente.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-128">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="5cbd3-129">**Account di Azure Active Directory (Azure ad):** Si tratta di un account creato in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-129">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="5cbd3-130">Questo garantisce alla tua azienda la possibilità di gestire il dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-130">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="5cbd3-131">Ciò consentirà a più utenti di accedere alla HoloLens 1a gen Commercial Suite/il dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-131">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="5cbd3-132">Per informazioni più dettagliate sui tipi di identità, vedere l'articolo sull' [identità di HoloLens](hololens-identity.md) .</span><span class="sxs-lookup"><span data-stu-id="5cbd3-132">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="5cbd3-133">Tipo di funzionalità</span><span class="sxs-lookup"><span data-stu-id="5cbd3-133">Type of Features</span></span>

<span data-ttu-id="5cbd3-134">I requisiti della funzionalità determineranno le HoloLens necessarie.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-134">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="5cbd3-135">Una caratteristica popolare che vediamo distribuita in ambienti cliente è spesso la modalità Kiosk.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-135">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="5cbd3-136">[Qui](hololens-commercial-features.md)è possibile trovare un elenco delle caratteristiche principali di HoloLens e le edizioni di HoloLens che le supportano.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-136">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="5cbd3-137">Che cos'è la modalità Kiosk?</span><span class="sxs-lookup"><span data-stu-id="5cbd3-137">What is Kiosk Mode?</span></span>**

<span data-ttu-id="5cbd3-138">La modalità Kiosk è un modo per limitare le app a cui un utente ha accesso.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-138">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="5cbd3-139">Questo significa che agli utenti sarà consentito accedere solo ad alcune app.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-139">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="5cbd3-140">Quale modalità Kiosk è necessaria?</span><span class="sxs-lookup"><span data-stu-id="5cbd3-140">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="5cbd3-141">Esistono due tipi di modalità Kiosk: Single app e multi-app.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-141">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="5cbd3-142">La modalità single app Kiosk consente all'utente di accedere a un'app solo mentre la modalità Kiosk multiapp consente agli utenti di accedere a più app specificate.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-142">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="5cbd3-143">Per determinare la modalità Kiosk appropriata per la propria società, è necessario rispondere alle due domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cbd3-143">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="5cbd3-144">Gli utenti diversi richiedono diverse esperienze/restrizioni?</span><span class="sxs-lookup"><span data-stu-id="5cbd3-144">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="5cbd3-145">Si consideri l'esempio seguente: l'utente A è un ingegnere del servizio di campo che deve solo accedere a Remote assist.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-145">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="5cbd3-146">L'utente B è un tirocinante che deve accedere solo alle guide.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-146">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="5cbd3-147">In caso affermativo, sarà necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5cbd3-147">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="5cbd3-148">Account di Azure AD come metodo di accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-148">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="5cbd3-149">Modalità Kiosk **multi-app** .</span><span class="sxs-lookup"><span data-stu-id="5cbd3-149">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="5cbd3-150">Se no, continuare a interrogare due</span><span class="sxs-lookup"><span data-stu-id="5cbd3-150">If no, continue to question two</span></span>
1. **<span data-ttu-id="5cbd3-151">Hai bisogno di un'esperienza multi-app?</span><span class="sxs-lookup"><span data-stu-id="5cbd3-151">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="5cbd3-152">Se sì, è necessaria la modalità chiosco **multi-app**</span><span class="sxs-lookup"><span data-stu-id="5cbd3-152">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="5cbd3-153">Se la risposta alla domanda 1 e 2 non è disponibile, è possibile usare la modalità chiosco **Single-app**</span><span class="sxs-lookup"><span data-stu-id="5cbd3-153">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="5cbd3-154">Come configurare la modalità Kiosk:</span><span class="sxs-lookup"><span data-stu-id="5cbd3-154">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="5cbd3-155">Esistono due modi principali ([provisioning Packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) e [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) per distribuire la modalità Kiosk per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-155">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="5cbd3-156">Queste opzioni verranno discusse più avanti nel documento; Tuttavia, è possibile usare i collegamenti descritti sopra per passare alle rispettive sezioni di questo documento.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-156">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="5cbd3-157">App e scenari specifici delle app</span><span class="sxs-lookup"><span data-stu-id="5cbd3-157">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="5cbd3-158">La maggior parte dei passaggi trovati in questo documento si applica anche alle app seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cbd3-158">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="5cbd3-159">App</span><span class="sxs-lookup"><span data-stu-id="5cbd3-159">App</span></span> | <span data-ttu-id="5cbd3-160">Scenari specifici dell'app</span><span class="sxs-lookup"><span data-stu-id="5cbd3-160">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="5cbd3-161">Assistenza remota</span><span class="sxs-lookup"><span data-stu-id="5cbd3-161">Remote Assist</span></span> | [<span data-ttu-id="5cbd3-162">Comunicazione tra tenant</span><span class="sxs-lookup"><span data-stu-id="5cbd3-162">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="5cbd3-163">Guide</span><span class="sxs-lookup"><span data-stu-id="5cbd3-163">Guides</span></span>  | *<span data-ttu-id="5cbd3-164">Prossimamente</span><span class="sxs-lookup"><span data-stu-id="5cbd3-164">Coming Soon</span></span>* |
|<span data-ttu-id="5cbd3-165">App personalizzate</span><span class="sxs-lookup"><span data-stu-id="5cbd3-165">Custom Apps</span></span> | *<span data-ttu-id="5cbd3-166">Prossimamente</span><span class="sxs-lookup"><span data-stu-id="5cbd3-166">Coming Soon</span></span>* |

### <span data-ttu-id="5cbd3-167">Determinare il metodo di registrazione</span><span class="sxs-lookup"><span data-stu-id="5cbd3-167">Determine your enrollment method</span></span>

1. <span data-ttu-id="5cbd3-168">Registrazione in blocco con un token di sicurezza in un pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-168">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="5cbd3-169">Vantaggi: questo è l'approccio più automatizzato </span><span class="sxs-lookup"><span data-stu-id="5cbd3-169">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="5cbd3-170">Svantaggi: richiede l'installazione iniziale sul lato server</span><span class="sxs-lookup"><span data-stu-id="5cbd3-170">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="5cbd3-171">Registrazione automatica all'accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-171">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="5cbd3-172">Vantaggi: approccio più semplice</span><span class="sxs-lookup"><span data-stu-id="5cbd3-172">Pros: easiest approach</span></span>  
  <span data-ttu-id="5cbd3-173">Svantaggi: gli utenti dovranno completare la configurazione dopo l'applicazione del pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="5cbd3-173">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="5cbd3-174">_sconsigliato: registrare_ manualmente la registrazione post-installazione.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-174">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="5cbd3-175">Vantaggi: possibile iscriversi dopo la configurazione</span><span class="sxs-lookup"><span data-stu-id="5cbd3-175">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="5cbd3-176">Svantaggi: la maggior parte degli approcci manuali e dei dispositivi non è gestibile centralmente fino a quando non viene registrato manualmente.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-176">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="5cbd3-177">Altre informazioni possono essere trovate [qui](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="5cbd3-177">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="5cbd3-178">Determinare se è necessario creare un pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="5cbd3-178">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="5cbd3-179">Esistono due metodi per configurare un dispositivo HoloLens (provisioning packages and MDMs).</span><span class="sxs-lookup"><span data-stu-id="5cbd3-179">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="5cbd3-180">Ti consigliamo di usare MDM per configurare il dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-180">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="5cbd3-181">Tuttavia, esistono alcuni scenari in cui l'uso di un pacchetto di provisioning è la scelta migliore:</span><span class="sxs-lookup"><span data-stu-id="5cbd3-181">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="5cbd3-182">Si vuole configurare HoloLens per ignorare l'esperienza della casella fuori sede (OOBE)</span><span class="sxs-lookup"><span data-stu-id="5cbd3-182">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="5cbd3-183">Si verificano problemi durante la distribuzione di certificati in una rete complessa.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-183">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="5cbd3-184">La maggior parte del tempo è possibile distribuire i certificati con MDM (anche in ambienti complessi).</span><span class="sxs-lookup"><span data-stu-id="5cbd3-184">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="5cbd3-185">Tuttavia, alcuni scenari richiedono la distribuzione di certificati tramite il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-185">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="5cbd3-186">Alcune delle configurazioni di HoloLens che è possibile applicare in un pacchetto di provisioning:</span><span class="sxs-lookup"><span data-stu-id="5cbd3-186">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="5cbd3-187">Applicare certificati al dispositivo</span><span class="sxs-lookup"><span data-stu-id="5cbd3-187">Apply certificates to the device</span></span>
- <span data-ttu-id="5cbd3-188">Configurare una connessione Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="5cbd3-188">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="5cbd3-189">Configurare le domande predefinite come lingua e impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="5cbd3-189">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="5cbd3-190">(HoloLens 2) Registrare in blocco la gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="5cbd3-190">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="5cbd3-191">(HoloLens V1) Applicare la chiave per attivare Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="5cbd3-191">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="5cbd3-192">Se si decide di usare i pacchetti di provisioning, seguire [questa guida](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="5cbd3-192">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="5cbd3-193">Ottieni supporto</span><span class="sxs-lookup"><span data-stu-id="5cbd3-193">Get support</span></span>

<span data-ttu-id="5cbd3-194">Ottenere supporto tramite il sito del supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5cbd3-194">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="5cbd3-195">Presentare una richiesta di supporto</span><span class="sxs-lookup"><span data-stu-id="5cbd3-195">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
