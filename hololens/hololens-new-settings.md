---
title: Introduzione alla nuova app Impostazioni app
description: Informazioni sulla nuova app Impostazioni app
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, impostazioni, selezione app, volume
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: e6da84c180ef596b63b6d41229bd094354ab1221
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640169"
---
# <a name="new-settings-app"></a><span data-ttu-id="53b23-104">Nuova Impostazioni app</span><span class="sxs-lookup"><span data-stu-id="53b23-104">New Settings app</span></span>

<span data-ttu-id="53b23-105">Con [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)viene introdotto una nuova versione dell'app Impostazioni app.</span><span class="sxs-lookup"><span data-stu-id="53b23-105">With [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="53b23-106">La nuova app Impostazioni include nuove funzionalità e impostazioni espanse per HoloLens 2 nelle aree seguenti: Audio, Sospensione di Power &, Rete & Internet, App, Account, Accessibilità e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="53b23-106">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="53b23-107">Poiché la nuova app Impostazioni è distinta dall'app Impostazioni legacy, tutte le finestre Impostazioni precedentemente posizionate nell'ambiente verranno rimosse al momento dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="53b23-107">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![Home page Impostazioni nuova app](images/new-settings-app.png)

<span data-ttu-id="53b23-109">**Nuove funzionalità e impostazioni**</span><span class="sxs-lookup"><span data-stu-id="53b23-109">**New features and settings**</span></span>
- <span data-ttu-id="53b23-110">Impostazioni ricerca: cercare le impostazioni dalla home page Impostazioni usando parole chiave o il nome dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="53b23-110">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="53b23-111">Calibrazione > [colori del sistema](hololens2-display.md#how-to-use-display-color-calibration)</span><span class="sxs-lookup"><span data-stu-id="53b23-111">System > [Color calibration](hololens2-display.md#how-to-use-display-color-calibration)</span></span>
    - <span data-ttu-id="53b23-112">Selezionare un profilo colori alternativo per il HoloLens 2 schermo.</span><span class="sxs-lookup"><span data-stu-id="53b23-112">Select an alternative color profile for your HoloLens 2 display.</span></span>
- <span data-ttu-id="53b23-113">Suono > sistema:</span><span class="sxs-lookup"><span data-stu-id="53b23-113">System > Sound:</span></span>
  - <span data-ttu-id="53b23-114">Dispositivi audio di input e output: scegliere in modo indipendente i dispositivi audio di input e output( ad esempio, ascoltare l'audio tramite le cuffia Bluetooth o usare un microfono USB-C per l'input audio).</span><span class="sxs-lookup"><span data-stu-id="53b23-114">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="53b23-115">Bluetooth microfoni non sono supportati da HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="53b23-115">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="53b23-116">Volume dell'app: regolare in modo indipendente il volume di ogni app.</span><span class="sxs-lookup"><span data-stu-id="53b23-116">App volume: independently adjust the volume of each app.</span></span> <span data-ttu-id="53b23-117">Vedere [controllo del volume per ogni app.](holographic-home.md#per-app-volume-control)</span><span class="sxs-lookup"><span data-stu-id="53b23-117">See [per app volume control](holographic-home.md#per-app-volume-control).</span></span>
- <span data-ttu-id="53b23-118">Sistema > alimentazione & sospensione: scegliere quando il dispositivo deve andare in sospensione dopo un periodo di inattività.</span><span class="sxs-lookup"><span data-stu-id="53b23-118">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="53b23-119">Batteria > di sistema: abilitare manualmente la risparmio batteria o impostare una soglia della batteria a quel punto risparmio batteria attiva automaticamente.</span><span class="sxs-lookup"><span data-stu-id="53b23-119">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="53b23-120">Dispositivi > USB: è possibile disabilitare le connessioni USB per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="53b23-120">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="53b23-121">Rete & Internet:</span><span class="sxs-lookup"><span data-stu-id="53b23-121">Network & Internet:</span></span>
  - <span data-ttu-id="53b23-122">Le schede Ethernet USB-C verranno ora visualizzate in Rete & Internet.</span><span class="sxs-lookup"><span data-stu-id="53b23-122">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="53b23-123">Sono ora disponibili le impostazioni della scheda Ethernet USB-C, incluso il relativo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="53b23-123">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="53b23-124">È ora possibile abilitare la modalità aereo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="53b23-124">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="53b23-125">App: è possibile reimpostare le app predefinite usate per i tipi di file e collegamenti.</span><span class="sxs-lookup"><span data-stu-id="53b23-125">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="53b23-126">Per altre informazioni, vedere [Selezione app predefinita.](holographic-home.md#default-app-picker)</span><span class="sxs-lookup"><span data-stu-id="53b23-126">For more information see [Default app picker](holographic-home.md#default-app-picker).</span></span>
- <span data-ttu-id="53b23-127">Account > altri utenti: i proprietari dei dispositivi possono aggiungere utenti, aggiornare gli utenti standard ai proprietari dei dispositivi, eseguire il downgrade dei proprietari dei dispositivi agli utenti standard e rimuovere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="53b23-127">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="53b23-128">Accessibilità: modificare le dimensioni del testo e alcuni effetti visivi.</span><span class="sxs-lookup"><span data-stu-id="53b23-128">Ease of Access: change text size and some visual effects.</span></span>

<span data-ttu-id="53b23-129">**Problemi noti**</span><span class="sxs-lookup"><span data-stu-id="53b23-129">**Known issues**</span></span>
- <span data-ttu-id="53b23-130">Le finestre Impostazioni posizionate in precedenza verranno rimosse (vedere la nota precedente).</span><span class="sxs-lookup"><span data-stu-id="53b23-130">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="53b23-131">Non è più possibile rinominare il dispositivo con l Impostazioni app.</span><span class="sxs-lookup"><span data-stu-id="53b23-131">You can no longer rename your device with the Settings app.</span></span> <span data-ttu-id="53b23-132">Gli amministratori IT possono rinominare i dispositivi usando Windows [Autopilot](hololens2-autopilot.md) per il modello di nome del dispositivo HoloLens 2 o il nodo MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.</span><span class="sxs-lookup"><span data-stu-id="53b23-132">IT admins can rename devices by using the [Windows Autopilot for HoloLens 2](hololens2-autopilot.md) device name template or the MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName node.</span></span>
- <span data-ttu-id="53b23-133">La pagina Ethernet mostra sempre un dispositivo Ethernet virtuale ("UsbNcm").</span><span class="sxs-lookup"><span data-stu-id="53b23-133">The Ethernet page shows a virtual Ethernet device ("UsbNcm") at all times.</span></span>
- <span data-ttu-id="53b23-134">L'utilizzo della batteria per il nuovo Microsoft Edge potrebbe non essere accurato, a causa della natura di un'applicazione desktop Win32 supportata da un livello adattatore UWP (non è prevista alcuna correzione a breve).</span><span class="sxs-lookup"><span data-stu-id="53b23-134">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

