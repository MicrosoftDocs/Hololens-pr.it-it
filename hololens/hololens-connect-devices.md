---
title: Connessione a dispositivi Bluetooth e USB-C
description: Questa guida illustra la connessione a dispositivi e accessori Bluetooth e USB-C.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 53d426b4319dafd0dd976e67111992020507f719
ms.sourcegitcommit: 563797405f7470f979a27718c604df920efbb368
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881246"
---
# <span data-ttu-id="3e0f4-103">Connessione a dispositivi Bluetooth e USB-C</span><span class="sxs-lookup"><span data-stu-id="3e0f4-103">Connect to Bluetooth and USB-C devices</span></span>

## <span data-ttu-id="3e0f4-104">Accoppiare dispositivi Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3e0f4-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="3e0f4-105">HoloLens 2 supporta le seguenti categorie di dispositivi Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="3e0f4-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="3e0f4-106">Mouse</span><span class="sxs-lookup"><span data-stu-id="3e0f4-106">Mouse</span></span>
- <span data-ttu-id="3e0f4-107">Tastiera</span><span class="sxs-lookup"><span data-stu-id="3e0f4-107">Keyboard</span></span>
- <span data-ttu-id="3e0f4-108">Dispositivi A2DP (Bluetooth audio output)</span><span class="sxs-lookup"><span data-stu-id="3e0f4-108">Bluetooth audio output (A2DP) devices</span></span>

> [!NOTE]
> <span data-ttu-id="3e0f4-109">I microfoni esterni non possono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-109">External microphones cannot be used.</span></span> <span data-ttu-id="3e0f4-110">HoloLens 2 usa il suo [](hololens2-hardware.md#audio-and-speech)gruppo microfoni[ incorporato.](hololens2-hardware.md#audio-and-speech)</span><span class="sxs-lookup"><span data-stu-id="3e0f4-110">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

<span data-ttu-id="3e0f4-111">HoloLens (prima generazione) supporta le seguenti categorie di dispositivi Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="3e0f4-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="3e0f4-112">Mouse</span><span class="sxs-lookup"><span data-stu-id="3e0f4-112">Mouse</span></span>
- <span data-ttu-id="3e0f4-113">Tastiera</span><span class="sxs-lookup"><span data-stu-id="3e0f4-113">Keyboard</span></span>
- <span data-ttu-id="3e0f4-114">Clicker HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="3e0f4-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="3e0f4-115">Altri tipi di dispositivi Bluetooth, come altoparlanti, cuffie, smartphone e game pad, potrebbero essere elencati come disponibili nelle impostazioni di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="3e0f4-116">Tuttavia, questi dispositivi non sono supportati in HoloLens (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="3e0f4-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="3e0f4-117">Per maggiori dettagli, vedere [Le impostazioni di HoloLens indicano che i dispositivi sono disponibili, ma questi non funzionano](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="3e0f4-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="3e0f4-118">Accoppiare una tastiera o un mouse Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3e0f4-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="3e0f4-119">Attivare la tastiera o il mouse e renderli individuabili.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="3e0f4-120">Per informazioni su come rendere i dispositivi individuabili, cerca informazioni nel dispositivo (o nella documentazione) oppure visita il sito web del produttore.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="3e0f4-121">Apri la mano a fiore (HoloLens prima generazione) o esegui il gesto iniziale (HoloLens 2) per passare a **Start**, e seleziona poi **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="3e0f4-122">Seleziona **Dispositivi**, e assicurati che il Bluetooth sia attivato.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="3e0f4-123">Quando vedi il nome del dispositivo, seleziona **Associa**, e segui poi le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="3e0f4-124">HoloLens (prima generazione): Associare il clicker</span><span class="sxs-lookup"><span data-stu-id="3e0f4-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="3e0f4-125">Usa il gesto della mano a fiore per andare a **Start**, quindi seleziona **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="3e0f4-126">Seleziona **Dispositivi**, e assicurati che il Bluetooth sia attivato.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="3e0f4-127">Usa la punta di una penna per tenere premuto il pulsante di associazione del clicker finché la lunce bianca si accende sull’indicatore del clicker.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="3e0f4-128">Assicurati di tenere premuto il pulsante finché la luce comincia a lampeggiare. </span><span class="sxs-lookup"><span data-stu-id="3e0f4-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="3e0f4-129">Il pulsante di associazione si trova sul lato inferiore del clicker, accanto all’anello per il dito.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![Il pulsante di associazione si trova accanto all’anello](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="3e0f4-131">Nella schermata di associazione, seleziona **Clicker** > **Associa**.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="3e0f4-132">HoloLens 2: Connettere dispositivi USB-C</span><span class="sxs-lookup"><span data-stu-id="3e0f4-132">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="3e0f4-133">HoloLens 2 supporta le seguenti categorie di dispositivi USB-C:</span><span class="sxs-lookup"><span data-stu-id="3e0f4-133">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="3e0f4-134">Dispositivi di archiviazione di massa (come le penne USB)</span><span class="sxs-lookup"><span data-stu-id="3e0f4-134">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="3e0f4-135">Adattatori ethernet (inclusi dispositivi ethernet più ricarica)</span><span class="sxs-lookup"><span data-stu-id="3e0f4-135">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="3e0f4-136">Adattatori da USB-C a presa audio da 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="3e0f4-136">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="3e0f4-137">Auricolari digitali USB-C (inclusi gli adattatori e la ricarica)</span><span class="sxs-lookup"><span data-stu-id="3e0f4-137">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="3e0f4-138">Mouse cablati</span><span class="sxs-lookup"><span data-stu-id="3e0f4-138">Wired mouse</span></span>
- <span data-ttu-id="3e0f4-139">Tastiere cablate</span><span class="sxs-lookup"><span data-stu-id="3e0f4-139">Wired keyboard</span></span>
- <span data-ttu-id="3e0f4-140">Hub PD con combinazione (ricarica USB A più PD)</span><span class="sxs-lookup"><span data-stu-id="3e0f4-140">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="3e0f4-141">Alcuni dispositivi mobili con connessioni USB-C si mostrano a HoloLens come adattatori ethernet, e possono perciò essere usati in configurazioni con hotspor personali, a cominciare da Windows Holographic versione 2004.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-141">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="3e0f4-142">I modem USB LTE che richiedono driver separati e/o l’installazione di applicazioni per la configurazione non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-142">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

## <span data-ttu-id="3e0f4-143">Connettersi a Miracast</span><span class="sxs-lookup"><span data-stu-id="3e0f4-143">Connect to Miracast</span></span>

<span data-ttu-id="3e0f4-144">Per usare Miracast, segui questa procedura:</span><span class="sxs-lookup"><span data-stu-id="3e0f4-144">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="3e0f4-145">Effettua una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="3e0f4-145">Do one of the following:</span></span>  

   - <span data-ttu-id="3e0f4-146">Apri il menu **Start** e seleziona l’icona del display.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-146">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="3e0f4-147">Pronuncia “Connetti” mentre fissi il **menu Start**.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-147">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="3e0f4-148">Seleziona un dispositivo disponibile dall’elenco di dispositivi mostrato.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-148">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="3e0f4-149">Completa l'associazione per avviare la proiezione.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-149">Complete the pairing to begin projecting.</span></span>

## <span data-ttu-id="3e0f4-150">Disattivare il Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3e0f4-150">Disable Bluetooth</span></span>

<span data-ttu-id="3e0f4-151">Questa procedura disattiva i componenti RF della radio Bluetooth, e disabilita tutte le funzionalità Bluetooth di Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-151">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="3e0f4-152">Apri la mano a fiore (HoloLens prima generazione) o esegui il gesto iniziale (HoloLens 2) per passare a **Start**, e seleziona poi **Impostazioni** > **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-152">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="3e0f4-153">Sposta il selettore del **Bluetooth** sulla posizione **Off**.</span><span class="sxs-lookup"><span data-stu-id="3e0f4-153">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>
