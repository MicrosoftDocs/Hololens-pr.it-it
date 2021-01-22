---
title: Panoramica-gestione delle app
description: Introduzione a una panoramica della gestione delle app di realtà mista con i pacchetti di gestione di dispositivi mobili, Microsoft Store per le aziende e provisioning.
keywords: HoloLens, utente, account, app, gestione applicazioni,
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283707"
---
# <span data-ttu-id="8fd29-104">Gestione dell'app: panoramica</span><span class="sxs-lookup"><span data-stu-id="8fd29-104">App Management: Overview</span></span>

<span data-ttu-id="8fd29-105">È possibile distribuire le app in quattro percorsi diversi: **MDM (Mobile Device Management)**, **Microsoft Store per le aziende**, **Microsoft Store**o installarli tramite **provisioning**.</span><span class="sxs-lookup"><span data-stu-id="8fd29-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="8fd29-106">Gestione dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="8fd29-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="8fd29-107">Una soluzione MDM consente ai responsabili IT e agli amministratori di installare automaticamente le proprie app line-of-business in privato o di acquistare app tramite lo Store per un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="8fd29-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="8fd29-108">I dispositivi HoloLens funzionano meglio con Microsoft Endpoint Manager (Intune) per la [gestione delle applicazioni](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="8fd29-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="8fd29-109">Intune offre anche agli utenti un controllo più accurato sulle app gestite da IT tramite l'esperienza scaricabile del portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="8fd29-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="8fd29-110">Le istruzioni seguenti si riferiscono agli utenti che vogliono gestire le proprie applicazioni con Intune.</span><span class="sxs-lookup"><span data-stu-id="8fd29-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="8fd29-111">Microsoft consiglia di usare Intune per la gestione di applicazioni e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8fd29-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="8fd29-112">La gestione di dispositivi mobili (MDM) è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="8fd29-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="8fd29-113">MDM distribuito + Portale aziendale</span><span class="sxs-lookup"><span data-stu-id="8fd29-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="8fd29-114">App line-of-business (non pubbliche)</span><span class="sxs-lookup"><span data-stu-id="8fd29-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="8fd29-115">Installazione manuale delle applicazioni disponibili tramite portale aziendale</span><span class="sxs-lookup"><span data-stu-id="8fd29-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="8fd29-116">Criteri di push-through MDM di amministrazione</span><span class="sxs-lookup"><span data-stu-id="8fd29-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="8fd29-117">Aggiornamento automatico tramite MDM</span><span class="sxs-lookup"><span data-stu-id="8fd29-117">Auto update through MDM</span></span>

## <span data-ttu-id="8fd29-118">Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="8fd29-118">Microsoft Store for Business</span></span>

<span data-ttu-id="8fd29-119">[Microsoft Store for business](app-deploy-store-business.md) offre ai responsabili decisionali e agli amministratori delle aziende di trovare, acquisire, gestire e distribuire app gratuite e a pagamento.</span><span class="sxs-lookup"><span data-stu-id="8fd29-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="8fd29-120">Gli amministratori IT possono gestire le app di Microsoft Store e le app line-of-business private in un unico inventario, oltre a assegnare e riutilizzare le licenze in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8fd29-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="8fd29-121">Per altre informazioni, visitare [i prerequisiti per l'uso di Microsoft Store for business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="8fd29-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="8fd29-122">Microsoft Store for business è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="8fd29-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="8fd29-123">App pubbliche o line-of-business</span><span class="sxs-lookup"><span data-stu-id="8fd29-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="8fd29-124">Installazione automatica delle applicazioni necessarie tramite MDM Association</span><span class="sxs-lookup"><span data-stu-id="8fd29-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="8fd29-125">L'utente scarica manualmente le app</span><span class="sxs-lookup"><span data-stu-id="8fd29-125">User manually downloads apps</span></span>
* <span data-ttu-id="8fd29-126">Aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="8fd29-126">Auto Update</span></span>

## <span data-ttu-id="8fd29-127">App di Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8fd29-127">Microsoft Store apps</span></span>

<span data-ttu-id="8fd29-128">Microsoft Store offre ai responsabili decisionali e agli amministratori delle aziende la ricerca, l'acquisizione, la gestione e la distribuzione di app pubbliche.</span><span class="sxs-lookup"><span data-stu-id="8fd29-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="8fd29-129">Questo Microsoft Store è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="8fd29-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="8fd29-130">Solo app pubbliche</span><span class="sxs-lookup"><span data-stu-id="8fd29-130">Public apps only</span></span>
* <span data-ttu-id="8fd29-131">L'utente scarica manualmente le app</span><span class="sxs-lookup"><span data-stu-id="8fd29-131">User manually downloads apps</span></span>
* <span data-ttu-id="8fd29-132">Aggiornamento automatico se connesso a Internet</span><span class="sxs-lookup"><span data-stu-id="8fd29-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="8fd29-133">Per altre informazioni, visita le [app dello Store olografico](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="8fd29-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="8fd29-134">Installare tramite provisioning Packages</span><span class="sxs-lookup"><span data-stu-id="8fd29-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="8fd29-135">I [pacchetti di provisioning](app-deploy-provisioning-package.md) consentono di installare app personalizzate o di linea di business, consentendo ai professionisti IT e agli amministratori di installare rapidamente le app in un dispositivo locale tramite USB.</span><span class="sxs-lookup"><span data-stu-id="8fd29-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="8fd29-136">Questa installazione può essere eseguita senza una connessione Internet e per qualsiasi tipo di identità.</span><span class="sxs-lookup"><span data-stu-id="8fd29-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="8fd29-137">L'installazione tramite pacchetti di provisioning è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="8fd29-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="8fd29-138">App line-of-business/self-developed (non pubbliche)</span><span class="sxs-lookup"><span data-stu-id="8fd29-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="8fd29-139">App pubbliche (se è disponibile il programma di installazione offline)</span><span class="sxs-lookup"><span data-stu-id="8fd29-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="8fd29-140">Solo caricamento laterale USB</span><span class="sxs-lookup"><span data-stu-id="8fd29-140">USB side-loading only</span></span>
* <span data-ttu-id="8fd29-141">Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite il pacchetto di provisioning)</span><span class="sxs-lookup"><span data-stu-id="8fd29-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="8fd29-142">Installare app in HoloLens 2 tramite il programma di installazione di app</span><span class="sxs-lookup"><span data-stu-id="8fd29-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="8fd29-143">L'uso degli utenti del [programma di installazione dell'app](app-deploy-app-installer.md) può avere un'esperienza semplice per l'installazione di app nei dispositivi locali o per la condivisione di un'app con un altro utente che non ha familiarità con altri metodi di installazione dell'app in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8fd29-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="8fd29-144">Questa operazione può essere eseguita senza la necessità di abilitare la modalità sviluppatore o usare Device Portal.</span><span class="sxs-lookup"><span data-stu-id="8fd29-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="8fd29-145">Si tratta di un metodo semplice per distribuire un'app completamente integrata.</span><span class="sxs-lookup"><span data-stu-id="8fd29-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="8fd29-146">Indipendentemente dal fatto che tu voglia semplicemente provare la tua app a un altro utente con un HoloLens o desideri distribuire l'app, questo metodo funziona facilmente.</span><span class="sxs-lookup"><span data-stu-id="8fd29-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="8fd29-147">L'installazione tramite App Installer è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="8fd29-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="8fd29-148">App line-of-business/self-developed (non pubbliche)</span><span class="sxs-lookup"><span data-stu-id="8fd29-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="8fd29-149">Solo caricamento laterale</span><span class="sxs-lookup"><span data-stu-id="8fd29-149">Side-load only</span></span>
* <span data-ttu-id="8fd29-150">Non richiede la modalità sviluppatore o Device Portal</span><span class="sxs-lookup"><span data-stu-id="8fd29-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="8fd29-151">Facile da installare per l'utente finale</span><span class="sxs-lookup"><span data-stu-id="8fd29-151">Easy for end user to install</span></span>
