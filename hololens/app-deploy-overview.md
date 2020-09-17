---
title: Panoramica-gestione delle app
description: app, gestione, gestione app
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
ms.openlocfilehash: b0b7609f1caac20ff0c47251b1f85a26d7fe1de8
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016650"
---
# <span data-ttu-id="a519e-104">Gestione dell'app: panoramica</span><span class="sxs-lookup"><span data-stu-id="a519e-104">App Management: Overview</span></span>

<span data-ttu-id="a519e-105">È possibile distribuire le app in quattro percorsi diversi: **MDM (Mobile Device Management)**, **Microsoft Store per le aziende**, **Microsoft Store**o installarli tramite **provisioning**.</span><span class="sxs-lookup"><span data-stu-id="a519e-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span> 

## <span data-ttu-id="a519e-106">Gestione dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="a519e-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="a519e-107">Una soluzione MDM consente ai responsabili IT e agli amministratori di installare automaticamente le proprie app line-of-business in privato o di acquistare app tramite lo Store per un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="a519e-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="a519e-108">I dispositivi HoloLens funzionano meglio con Microsoft Endpoint Manager (Intune) per la [gestione delle applicazioni](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="a519e-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="a519e-109">Intune offre anche agli utenti un controllo più accurato sulle app gestite da IT tramite l'esperienza scaricabile del portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="a519e-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE] 
> <span data-ttu-id="a519e-110">Le istruzioni seguenti si riferiscono agli utenti che vogliono gestire le proprie applicazioni con Intune.</span><span class="sxs-lookup"><span data-stu-id="a519e-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="a519e-111">Microsoft consiglia di usare Intune per la gestione di applicazioni e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a519e-111">Microsoft recommends using Intune for application and device management.</span></span>
    
<span data-ttu-id="a519e-112">La gestione di dispositivi mobili (MDM) è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="a519e-112">Mobile Device Management (MDM) is applicable for:</span></span> 
* <span data-ttu-id="a519e-113">MDM distribuito + Portale aziendale</span><span class="sxs-lookup"><span data-stu-id="a519e-113">MDM deployed + Company Portal</span></span> 
* <span data-ttu-id="a519e-114">Linea di app business (non pubbliche)</span><span class="sxs-lookup"><span data-stu-id="a519e-114">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="a519e-115">Installazione manuale delle applicazioni disponibili tramite portale aziendale</span><span class="sxs-lookup"><span data-stu-id="a519e-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="a519e-116">Criteri di push-through MDM di amministrazione</span><span class="sxs-lookup"><span data-stu-id="a519e-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="a519e-117">Aggiornamento automatico tramite MDM</span><span class="sxs-lookup"><span data-stu-id="a519e-117">Auto update through MDM</span></span>

## <span data-ttu-id="a519e-118">Microsoft Store per le aziende</span><span class="sxs-lookup"><span data-stu-id="a519e-118">Microsoft Store for Business</span></span>

<span data-ttu-id="a519e-119">[Microsoft Store for business](app-deploy-store-business.md) offre ai responsabili decisionali e agli amministratori delle aziende di trovare, acquisire, gestire e distribuire app gratuite e a pagamento.</span><span class="sxs-lookup"><span data-stu-id="a519e-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="a519e-120">Gli amministratori IT possono gestire le app di Microsoft Store e le app line-of-business private in un unico inventario e assegnare e riutilizzare le licenze in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a519e-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and re-use licenses as needed.</span></span> <span data-ttu-id="a519e-121">Per altre informazioni, visitare [i prerequisiti per l'uso di Microsoft Store for business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="a519e-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>
    
<span data-ttu-id="a519e-122">Microsoft Store for business è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="a519e-122">The Microsoft Store for Business is applicable for:</span></span> 
* <span data-ttu-id="a519e-123">App pubbliche o line-of-business</span><span class="sxs-lookup"><span data-stu-id="a519e-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="a519e-124">Installazione automatica delle applicazioni necessarie tramite MDM Association</span><span class="sxs-lookup"><span data-stu-id="a519e-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="a519e-125">L'utente scarica manualmente le app</span><span class="sxs-lookup"><span data-stu-id="a519e-125">User manually downloads apps</span></span>
* <span data-ttu-id="a519e-126">Aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="a519e-126">Auto Update</span></span>

## <span data-ttu-id="a519e-127">App di Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a519e-127">Microsoft Store apps</span></span>

<span data-ttu-id="a519e-128">Microsoft Store offre ai responsabili decisionali e agli amministratori delle aziende la ricerca, l'acquisizione, la gestione e la distribuzione di app pubbliche.</span><span class="sxs-lookup"><span data-stu-id="a519e-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>
    
<span data-ttu-id="a519e-129">Questo Microsoft Store è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="a519e-129">This Microsoft Store is applicable for:</span></span> 
* <span data-ttu-id="a519e-130">Solo app pubbliche</span><span class="sxs-lookup"><span data-stu-id="a519e-130">Public apps only</span></span>
* <span data-ttu-id="a519e-131">L'utente scarica manualmente le app</span><span class="sxs-lookup"><span data-stu-id="a519e-131">User manually downloads apps</span></span>
* <span data-ttu-id="a519e-132">Aggiornamento automatico se connesso a Internet</span><span class="sxs-lookup"><span data-stu-id="a519e-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="a519e-133">Per altre informazioni, visita le [app dello Store olografico](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="a519e-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="a519e-134">Installare tramite provisioning Packages</span><span class="sxs-lookup"><span data-stu-id="a519e-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="a519e-135">I [pacchetti di provisioning](app-deploy-provisioning-package.md) consentono di installare app personalizzate o di linea di business, consentendo ai professionisti IT e agli amministratori di installare rapidamente le app in un dispositivo locale tramite USB.</span><span class="sxs-lookup"><span data-stu-id="a519e-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="a519e-136">Questa operazione può essere eseguita senza una connessione Internet e per qualsiasi tipo di identità.</span><span class="sxs-lookup"><span data-stu-id="a519e-136">This can be done without an internet connection and for any identity type.</span></span>
    
<span data-ttu-id="a519e-137">L'installazione tramite pacchetti di provisioning è applicabile per:</span><span class="sxs-lookup"><span data-stu-id="a519e-137">Installing via Provisioning Packages is applicable for:</span></span> 
* <span data-ttu-id="a519e-138">Linea di app business (non pubbliche)</span><span class="sxs-lookup"><span data-stu-id="a519e-138">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="a519e-139">App pubbliche (se è disponibile il programma di installazione offline)</span><span class="sxs-lookup"><span data-stu-id="a519e-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="a519e-140">Solo caricamento laterale USB</span><span class="sxs-lookup"><span data-stu-id="a519e-140">USB side-load only</span></span>
* <span data-ttu-id="a519e-141">Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite il pacchetto di provisioning)</span><span class="sxs-lookup"><span data-stu-id="a519e-141">No auto update (requires manual updates via Provisioning Package)</span></span>
