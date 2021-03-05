---
title: Connessione a dispositivi Bluetooth e USB-C
description: Informazioni di base sulla connessione ai dispositivi e accessori Bluetooth e USB-C dai dispositivi di Realtà mista HoloLens.
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
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385484"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="cffd2-103">Connessione a dispositivi Bluetooth e USB-C</span><span class="sxs-lookup"><span data-stu-id="cffd2-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="cffd2-104">I microfoni esterni non possono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="cffd2-104">External microphones cannot be used.</span></span> <span data-ttu-id="cffd2-105">HoloLens 2 usa il suo [](hololens2-hardware.md#audio-and-speech)gruppo microfoni[ incorporato.](hololens2-hardware.md#audio-and-speech)</span><span class="sxs-lookup"><span data-stu-id="cffd2-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="cffd2-106">Accoppiare dispositivi Bluetooth</span><span class="sxs-lookup"><span data-stu-id="cffd2-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="cffd2-107">HoloLens 2 supporta le seguenti categorie di dispositivi Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="cffd2-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="cffd2-108">Mouse</span><span class="sxs-lookup"><span data-stu-id="cffd2-108">Mouse</span></span>
- <span data-ttu-id="cffd2-109">Tastiera</span><span class="sxs-lookup"><span data-stu-id="cffd2-109">Keyboard</span></span>
- <span data-ttu-id="cffd2-110">Dispositivi A2DP (Bluetooth audio output)</span><span class="sxs-lookup"><span data-stu-id="cffd2-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="cffd2-111">HoloLens (prima generazione) supporta le seguenti categorie di dispositivi Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="cffd2-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="cffd2-112">Mouse</span><span class="sxs-lookup"><span data-stu-id="cffd2-112">Mouse</span></span>
- <span data-ttu-id="cffd2-113">Tastiera</span><span class="sxs-lookup"><span data-stu-id="cffd2-113">Keyboard</span></span>
- [<span data-ttu-id="cffd2-114">Clicker HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="cffd2-114">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="cffd2-115">Altri tipi di dispositivi Bluetooth, come altoparlanti, cuffie, smartphone e game pad, potrebbero essere elencati come disponibili nelle impostazioni di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cffd2-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="cffd2-116">Tuttavia, questi dispositivi non sono supportati in HoloLens (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="cffd2-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="cffd2-117">Per maggiori dettagli, vedere [Le impostazioni di HoloLens indicano che i dispositivi sono disponibili, ma questi non funzionano](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="cffd2-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="cffd2-118">Accoppiare una tastiera o un mouse Bluetooth</span><span class="sxs-lookup"><span data-stu-id="cffd2-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="cffd2-119">Attivare la tastiera o il mouse e renderli individuabili.</span><span class="sxs-lookup"><span data-stu-id="cffd2-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="cffd2-120">Per informazioni su come rendere i dispositivi individuabili, cerca informazioni nel dispositivo (o nella documentazione) oppure visita il sito web del produttore.</span><span class="sxs-lookup"><span data-stu-id="cffd2-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="cffd2-121">Apri la mano a fiore (HoloLens prima generazione) o esegui il gesto iniziale (HoloLens 2) per passare a **Start**, e seleziona poi **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="cffd2-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="cffd2-122">Seleziona **Dispositivi**, e assicurati che il Bluetooth sia attivato.</span><span class="sxs-lookup"><span data-stu-id="cffd2-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="cffd2-123">Quando vedi il nome del dispositivo, seleziona **Associa**, e segui poi le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="cffd2-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="cffd2-124">Disattivare il Bluetooth</span><span class="sxs-lookup"><span data-stu-id="cffd2-124">Disable Bluetooth</span></span>

<span data-ttu-id="cffd2-125">Questa procedura disattiva i componenti RF della radio Bluetooth, e disabilita tutte le funzionalità Bluetooth di Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cffd2-125">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="cffd2-126">Apri la mano a fiore (HoloLens prima generazione) o esegui il gesto iniziale (HoloLens 2) per passare a **Start**, e seleziona poi **Impostazioni** > **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="cffd2-126">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="cffd2-127">Sposta il selettore del **Bluetooth** sulla posizione **Off**.</span><span class="sxs-lookup"><span data-stu-id="cffd2-127">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="cffd2-128">HoloLens 2: Connettere dispositivi USB-C</span><span class="sxs-lookup"><span data-stu-id="cffd2-128">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="cffd2-129">HoloLens 2 supporta le seguenti categorie di dispositivi USB-C:</span><span class="sxs-lookup"><span data-stu-id="cffd2-129">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="cffd2-130">Dispositivi di archiviazione di massa (come le penne USB)</span><span class="sxs-lookup"><span data-stu-id="cffd2-130">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="cffd2-131">Adattatori ethernet (inclusi dispositivi ethernet più ricarica)</span><span class="sxs-lookup"><span data-stu-id="cffd2-131">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="cffd2-132">Adattatori da USB-C a presa audio da 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="cffd2-132">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="cffd2-133">Auricolari digitali USB-C (inclusi gli adattatori e la ricarica)</span><span class="sxs-lookup"><span data-stu-id="cffd2-133">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="cffd2-134">Mouse cablati</span><span class="sxs-lookup"><span data-stu-id="cffd2-134">Wired mouse</span></span>
- <span data-ttu-id="cffd2-135">Tastiere cablate</span><span class="sxs-lookup"><span data-stu-id="cffd2-135">Wired keyboard</span></span>
- <span data-ttu-id="cffd2-136">Hub PD con combinazione (ricarica USB A più PD)</span><span class="sxs-lookup"><span data-stu-id="cffd2-136">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="cffd2-137">In risposta al feedback dei clienti, abbiamo abilitato un supporto limitato per la connettività cellulare con tethering direttamente a HoloLens tramite USB-C.</span><span class="sxs-lookup"><span data-stu-id="cffd2-137">In response to customer feedback we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="cffd2-138">Per altre informazioni, vedi [Connettersi alla rete cellulare e 5G.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="cffd2-138">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="cffd2-139">Hub USB-C</span><span class="sxs-lookup"><span data-stu-id="cffd2-139">USB-C Hubs</span></span>

<span data-ttu-id="cffd2-140">Alcuni utenti potrebbero avere la necessità di connettere più dispositivi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="cffd2-140">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="cffd2-141">Per gli utenti che desiderano visualizzare in anteprima una caratteristica Insider e [usare un microfono USB-C](hololens-insider.md#usb-c-external-microphone-support) insieme a un altro dispositivo connesso, gli hub USB-C possono rappresentare una soluzione adatta.</span><span class="sxs-lookup"><span data-stu-id="cffd2-141">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="cffd2-142">Microsoft non ha testato tali dispositivi, né è nella misura di consigliare un marchio specifico.</span><span class="sxs-lookup"><span data-stu-id="cffd2-142">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="cffd2-143">Requisiti per hub USB-C e dispositivi connessi:</span><span class="sxs-lookup"><span data-stu-id="cffd2-143">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="cffd2-144">I dispositivi connessi non possono richiedere un driver per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="cffd2-144">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="cffd2-145">Il consumo energetico totale di tutti i dispositivi connessi deve essere inferiore a 4,5 watt.</span><span class="sxs-lookup"><span data-stu-id="cffd2-145">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="cffd2-146">Connettersi a Miracast</span><span class="sxs-lookup"><span data-stu-id="cffd2-146">Connect to Miracast</span></span>

<span data-ttu-id="cffd2-147">Per usare Miracast, segui questa procedura:</span><span class="sxs-lookup"><span data-stu-id="cffd2-147">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="cffd2-148">Effettua una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="cffd2-148">Do one of the following:</span></span>  

   - <span data-ttu-id="cffd2-149">Apri il menu **Start** e seleziona l’icona del display.</span><span class="sxs-lookup"><span data-stu-id="cffd2-149">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="cffd2-150">Pronuncia “Connetti” mentre fissi il **menu Start**.</span><span class="sxs-lookup"><span data-stu-id="cffd2-150">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="cffd2-151">Seleziona un dispositivo disponibile dall’elenco di dispositivi mostrato.</span><span class="sxs-lookup"><span data-stu-id="cffd2-151">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="cffd2-152">Completa l'associazione per avviare la proiezione.</span><span class="sxs-lookup"><span data-stu-id="cffd2-152">Complete the pairing to begin projecting.</span></span>
