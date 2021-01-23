---
title: Panoramica sulla configurazione di CSP e la gestione dei dispositivi
description: Informazioni su come configurare CSP, criteri e gestione dei dispositivi usando i pacchetti di gestione e provisioning dei dispositivi mobili.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283247"
---
# <span data-ttu-id="5d2c7-103">Panoramica sulla configurazione di CSP e la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="5d2c7-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="5d2c7-104">Gli amministratori IT possono definire e implementare le impostazioni dei criteri in HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="5d2c7-105">Le impostazioni di configurazione da usare varieranno in base allo scenario di distribuzione e i dispositivi aziendali offriranno al personale IT la più ampia gamma di opzioni di controllo.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="5d2c7-106">In Windows 10, i provider di servizi di configurazione (CSP) sono un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="5d2c7-107">Queste impostazioni corrispondono a chiavi del Registro di sistema o file.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="5d2c7-108">Alcuni provider di servizi di configurazione supportano il formato WAP, alcuni supportano SyncML e alcuni supportano entrambi.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="5d2c7-109">Per altre informazioni sui CSP per la gestione di dispositivi olografici di Windows 10, vedere l'elenco completo dei [CSP supportati nei dispositivi HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span><span class="sxs-lookup"><span data-stu-id="5d2c7-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="5d2c7-110">Gli amministratori IT possono anche gestire i criteri CSP nei dispositivi, vedere l'elenco completo dei [DSN sui criteri supportati da HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span><span class="sxs-lookup"><span data-stu-id="5d2c7-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="5d2c7-111">Metodi di configurazione</span><span class="sxs-lookup"><span data-stu-id="5d2c7-111">Configuration methods</span></span>

### <span data-ttu-id="5d2c7-112">Configurare con MDM</span><span class="sxs-lookup"><span data-stu-id="5d2c7-112">Configure with MDM</span></span>

<span data-ttu-id="5d2c7-113">I CSP e i criteri possono essere facilmente gestiti in qualsiasi dispositivo personale o aziendale registrato in un sistema MDM.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="5d2c7-114">Una volta che un dispositivo è stato registrato nella soluzione MDM, sarà possibile gestire il dispositivo o un set di dispositivi tramite le configurazioni di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="5d2c7-115">Leggi altre informazioni su come [gestire i dispositivi HoloLens tramite MDM](hololens-mdm-configure.md).</span><span class="sxs-lookup"><span data-stu-id="5d2c7-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="5d2c7-116">Configurare con i pacchetti di provisioning</span><span class="sxs-lookup"><span data-stu-id="5d2c7-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="5d2c7-117">HoloLens 2 supporta inoltre l'impostazione di un set limitato di configurazioni CSP per i dispositivi HoloLens 2 tramite pacchetti di provisioning personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="5d2c7-118">I pacchetti di provisioning vengono in genere sfruttati per i dispositivi gestiti non MDM e richiedono l'applicazione manuale a ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="5d2c7-119">Leggere informazioni sulla creazione [di pacchetti di provisioning personalizzati per HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="5d2c7-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="5d2c7-120">Configurazioni</span><span class="sxs-lookup"><span data-stu-id="5d2c7-120">Configurations</span></span>

### <span data-ttu-id="5d2c7-121">Restrizioni comuni per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="5d2c7-121">Common device restrictions</span></span>

<span data-ttu-id="5d2c7-122">Alcune restrizioni dei dispositivi sono semplici e disabilitano una funzionalità o una connessione al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="5d2c7-123">Per altre informazioni, vedere altre informazioni sulle [restrizioni dei dispositivi comuni.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="5d2c7-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="5d2c7-124">Modalità Kiosk</span><span class="sxs-lookup"><span data-stu-id="5d2c7-124">Kiosk modes</span></span>

<span data-ttu-id="5d2c7-125">Usa la modalità Kiosk per controllare le identità che hanno accesso alle app per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="5d2c7-126">I chioschi possono essere usati per una singola app o per un'esperienza dell'interfaccia utente per più app.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="5d2c7-127">Le configurazioni di Kiosk variano da una singola app per chiunque usi il dispositivo, a selezioni diverse di app per gruppi diversi.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="5d2c7-128">La modalità Kiosk non interrompe "app consentite" dall'avvio di altre app e non è stata progettata per sempre.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="5d2c7-129">Leggi altre informazioni [sulle modalità Kiosk e su come usarle](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="5d2c7-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="5d2c7-130">Visibilità pagina impostazioni</span><span class="sxs-lookup"><span data-stu-id="5d2c7-130">Settings Page Visibility</span></span>

<span data-ttu-id="5d2c7-131">Usare i criteri delle app impostazioni per controllare le identità che hanno accesso alle impostazioni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="5d2c7-132">Uso di questo criterio l'app impostazioni può essere configurata in modo da visualizzare solo le pagine di selezione oppure nascondere tutte le pagine selezionate.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="5d2c7-133">[Informazioni su come configurare le pagine disponibili](settings-uri-list.md).</span><span class="sxs-lookup"><span data-stu-id="5d2c7-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="5d2c7-134">Questa caratteristica è attualmente disponibile solo nelle [Build Insider di Windows](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="5d2c7-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="5d2c7-135">Verificare che i dispositivi a cui si intende usare questa funzionalità siano in Build 19041.1349 +.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="5d2c7-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="5d2c7-136">WDAC</span></span>

<span data-ttu-id="5d2c7-137">Usa la configurazione di WDAC per controllare quali app/processi sono consentiti/non consentiti per essere avviati indipendentemente dal fatto che il sistema sia in modalità Kiosk o meno.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="5d2c7-138">Vedere la panoramica per WDAC.</span><span class="sxs-lookup"><span data-stu-id="5d2c7-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
