---
title: Panoramica - Gestione delle app
description: Introduzione a una panoramica della gestione delle app di realtà mista con la gestione dei dispositivi mobili, Microsoft Store per le aziende e i pacchetti di provisioning.
keywords: HoloLens, utente, account, app, gestione delle applicazioni,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635552"
---
# <a name="app-management-overview"></a><span data-ttu-id="e6cb9-104">Gestione app: panoramica</span><span class="sxs-lookup"><span data-stu-id="e6cb9-104">App Management: Overview</span></span>

<span data-ttu-id="e6cb9-105">È possibile distribuire le app in quattro percorsi diversi: Gestione dispositivi mobili **(MDM),** **Microsoft Store per le aziende**, **Microsoft Store** o installandole tramite **provisioning**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="e6cb9-106">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="e6cb9-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="e6cb9-107">Una soluzione MDM consente ai decision maker e agli amministratori IT di installare (eseguire il push) in privato delle app line-of-business o di acquistare app tramite lo Store per un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="e6cb9-108">HoloLens i dispositivi funzionano meglio con Microsoft Endpoint Manager (Intune) per la [gestione delle applicazioni.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="e6cb9-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="e6cb9-109">Intune offre anche agli utenti un controllo più granulare sulle app gestite dall'IT Portale aziendale'esperienza scaricabile.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="e6cb9-110">Le istruzioni seguenti sono per gli utenti che vogliono gestire le applicazioni con Intune.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="e6cb9-111">Microsoft consiglia di usare Intune per la gestione di applicazioni e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="e6cb9-112">Gestione di dispositivi mobili (MDM) è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="e6cb9-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="e6cb9-113">MDM distribuito + Portale aziendale</span><span class="sxs-lookup"><span data-stu-id="e6cb9-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="e6cb9-114">App line-of-business (non pubbliche)</span><span class="sxs-lookup"><span data-stu-id="e6cb9-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="e6cb9-115">Installazione manuale delle applicazioni disponibili tramite Portale aziendale</span><span class="sxs-lookup"><span data-stu-id="e6cb9-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="e6cb9-116">Push dell'amministratore tramite i criteri MDM</span><span class="sxs-lookup"><span data-stu-id="e6cb9-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="e6cb9-117">Aggiornamento automatico tramite MDM</span><span class="sxs-lookup"><span data-stu-id="e6cb9-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="e6cb9-118">Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="e6cb9-118">Microsoft Store for Business</span></span>

<span data-ttu-id="e6cb9-119">Il [Microsoft Store per le aziende](app-deploy-store-business.md) fornisce ai decision maker IT e agli amministratori delle aziende la ricerca, l'acquisizione, la gestione e la distribuzione di app gratuite e a pagamento.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="e6cb9-120">Gli amministratori IT possono gestire Microsoft Store app e app line-of-business private in un unico inventario, oltre ad assegnare e riutilizzare le licenze in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="e6cb9-121">Per altre informazioni, vedere [Prerequisiti per l'uso dell'Microsoft Store per le aziende](/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="e6cb9-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="e6cb9-122">Il Microsoft Store per le aziende è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="e6cb9-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="e6cb9-123">App pubbliche o line-of-business</span><span class="sxs-lookup"><span data-stu-id="e6cb9-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="e6cb9-124">Installazione automatica delle applicazioni necessarie tramite l'associazione MDM</span><span class="sxs-lookup"><span data-stu-id="e6cb9-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="e6cb9-125">L'utente scarica manualmente le app</span><span class="sxs-lookup"><span data-stu-id="e6cb9-125">User manually downloads apps</span></span>
* <span data-ttu-id="e6cb9-126">Aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="e6cb9-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="e6cb9-127">App del Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e6cb9-127">Microsoft Store apps</span></span>

<span data-ttu-id="e6cb9-128">Il Microsoft Store fornisce ai decision maker IT e agli amministratori delle aziende la ricerca, l'acquisizione, la gestione e la distribuzione di app pubbliche.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="e6cb9-129">Questa Microsoft Store è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="e6cb9-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="e6cb9-130">Solo app pubbliche</span><span class="sxs-lookup"><span data-stu-id="e6cb9-130">Public apps only</span></span>
* <span data-ttu-id="e6cb9-131">L'utente scarica manualmente le app</span><span class="sxs-lookup"><span data-stu-id="e6cb9-131">User manually downloads apps</span></span>
* <span data-ttu-id="e6cb9-132">Aggiornamento automatico se connesso a Internet</span><span class="sxs-lookup"><span data-stu-id="e6cb9-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="e6cb9-133">Per altre informazioni, vedere [App di Holographic Store.](/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="e6cb9-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="e6cb9-134">Installare tramite pacchetti di provisioning</span><span class="sxs-lookup"><span data-stu-id="e6cb9-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="e6cb9-135">[I pacchetti](app-deploy-provisioning-package.md) di provisioning consentono di installare app personalizzate o line-of-business, consentendo ai professionisti IT e agli amministratori di installare rapidamente le app in uno o più dispositivi locali tramite USB.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="e6cb9-136">Questa installazione può essere eseguita senza una connessione Internet e per qualsiasi tipo di identità.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="e6cb9-137">L'installazione tramite pacchetti di provisioning è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="e6cb9-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="e6cb9-138">App line-of-business/auto-sviluppate (non pubbliche)</span><span class="sxs-lookup"><span data-stu-id="e6cb9-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="e6cb9-139">App pubbliche (se è disponibile il programma di installazione offline)</span><span class="sxs-lookup"><span data-stu-id="e6cb9-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="e6cb9-140">Solo side-loading USB</span><span class="sxs-lookup"><span data-stu-id="e6cb9-140">USB side-loading only</span></span>
* <span data-ttu-id="e6cb9-141">Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite il pacchetto di provisioning)</span><span class="sxs-lookup"><span data-stu-id="e6cb9-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="e6cb9-142">Installare app in HoloLens 2 tramite Programma di installazione app</span><span class="sxs-lookup"><span data-stu-id="e6cb9-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="e6cb9-143">L'uso Programma di installazione app utenti può avere un'esperienza semplice per l'installazione di app nei dispositivi locali o la condivisione di un'app con un altro utente che non ha familiarità con altri metodi di installazione dell'app HoloLens. [](app-deploy-app-installer.md)</span><span class="sxs-lookup"><span data-stu-id="e6cb9-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="e6cb9-144">Questa operazione può essere eseguita senza dover abilitare la modalità sviluppatore o usare Portale di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="e6cb9-145">Si tratta di un metodo semplice per distribuire un'app completamente compilata.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="e6cb9-146">Indipendentemente dal fatto che si voglia semplicemente eseguire la demo dell'app a un altro utente con un HoloLens o se si vuole distribuire l'app, questo metodo funziona facilmente.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="e6cb9-147">L'installazione tramite Programma di installazione app è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="e6cb9-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="e6cb9-148">App line-of-business/self-developed (non pubbliche)</span><span class="sxs-lookup"><span data-stu-id="e6cb9-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="e6cb9-149">Solo caricamento laterale</span><span class="sxs-lookup"><span data-stu-id="e6cb9-149">Side-load only</span></span>
* <span data-ttu-id="e6cb9-150">Non richiede la modalità sviluppatore o il portale dispositivi</span><span class="sxs-lookup"><span data-stu-id="e6cb9-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="e6cb9-151">Facile da installare per l'utente finale</span><span class="sxs-lookup"><span data-stu-id="e6cb9-151">Easy for end user to install</span></span>
