---
title: Connettersi a dispositivi Bluetooth e USB-C
description: Inizia a connetterti a dispositivi e accessori Bluetooth e USB-C dai dispositivi di realtà mista HoloLens.
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
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397852"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="df5e9-103">Connettersi a dispositivi Bluetooth e USB-C</span><span class="sxs-lookup"><span data-stu-id="df5e9-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="df5e9-104">Associare dispositivi Bluetooth</span><span class="sxs-lookup"><span data-stu-id="df5e9-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="df5e9-105">HoloLens 2 supporta le classi seguenti di dispositivi Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="df5e9-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="df5e9-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span><span class="sxs-lookup"><span data-stu-id="df5e9-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="df5e9-107">Mouse</span><span class="sxs-lookup"><span data-stu-id="df5e9-107">Mouse</span></span>
    - <span data-ttu-id="df5e9-108">Tastiera</span><span class="sxs-lookup"><span data-stu-id="df5e9-108">Keyboard</span></span>
- <span data-ttu-id="df5e9-109">Dispositivi di output audio (A2DP)</span><span class="sxs-lookup"><span data-stu-id="df5e9-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="df5e9-110">HoloLens 2 supporta le API Bluetooth seguenti:</span><span class="sxs-lookup"><span data-stu-id="df5e9-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="df5e9-111">[Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) e [client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client) GATT</span><span class="sxs-lookup"><span data-stu-id="df5e9-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="df5e9-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="df5e9-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="df5e9-113">Potrebbe essere necessario installare le app complementari corrispondenti Microsoft Store usare effettivamente i dispositivi HID e GATT.</span><span class="sxs-lookup"><span data-stu-id="df5e9-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="df5e9-114">HoloLens (prima generazione) supporta le classi seguenti di dispositivi Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="df5e9-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="df5e9-115">Mouse</span><span class="sxs-lookup"><span data-stu-id="df5e9-115">Mouse</span></span>
- <span data-ttu-id="df5e9-116">Tastiera</span><span class="sxs-lookup"><span data-stu-id="df5e9-116">Keyboard</span></span>
- [<span data-ttu-id="df5e9-117">Clicker HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="df5e9-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="df5e9-118">Altri tipi di dispositivi Bluetooth, ad esempio altoparlanti, visori VR, smartphone e game pad, possono essere elencati come disponibili nelle impostazioni di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="df5e9-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="df5e9-119">Tuttavia, questi dispositivi non sono supportati in HoloLens (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="df5e9-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="df5e9-120">Per altre informazioni, vedi [Impostazioni di HoloLens](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)che elenca i dispositivi come disponibili, ma i dispositivi non funzionano.</span><span class="sxs-lookup"><span data-stu-id="df5e9-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="df5e9-121">Associare una tastiera o un mouse Bluetooth</span><span class="sxs-lookup"><span data-stu-id="df5e9-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="df5e9-122">Accendere la tastiera o il mouse e renderla individuabile.</span><span class="sxs-lookup"><span data-stu-id="df5e9-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="df5e9-123">Per informazioni su come rendere individuabile il dispositivo, cercare informazioni sul dispositivo (o sulla relativa documentazione) o visitare il sito Web del produttore.</span><span class="sxs-lookup"><span data-stu-id="df5e9-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="df5e9-124">Usa il movimento di fiore (HoloLens (prima generazione)) o il movimento di avvio (HoloLens 2) per passare a **Start** e quindi seleziona **Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="df5e9-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="df5e9-125">Selezionare **Dispositivi** e verificare che Bluetooth sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="df5e9-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="df5e9-126">Quando viene visualizzato il nome del dispositivo, selezionare **Associa** e quindi seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="df5e9-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="df5e9-127">Disabilitare Bluetooth</span><span class="sxs-lookup"><span data-stu-id="df5e9-127">Disable Bluetooth</span></span>

<span data-ttu-id="df5e9-128">Questa procedura disattiva i componenti RF della radio Bluetooth e disabilita tutte le funzionalità Bluetooth Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="df5e9-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="df5e9-129">Usare il movimento bloom (HoloLens (prima generazione)) o il movimento start (HoloLens 2) per passare a **Start** e quindi selezionare Settings Devices   >  **(Impostazioni dispositivi).**</span><span class="sxs-lookup"><span data-stu-id="df5e9-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="df5e9-130">Spostare l'interruttore del **dispositivo di scorrimento per Bluetooth** nella posizione **Off.**</span><span class="sxs-lookup"><span data-stu-id="df5e9-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="df5e9-131">HoloLens 2: Connettere dispositivi USB-C</span><span class="sxs-lookup"><span data-stu-id="df5e9-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="df5e9-132">HoloLens 2 supporta le classi seguenti di dispositivi USB-C:</span><span class="sxs-lookup"><span data-stu-id="df5e9-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="df5e9-133">Dispositivi di archiviazione di massa (ad esempio unità di scorrimento)</span><span class="sxs-lookup"><span data-stu-id="df5e9-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="df5e9-134">Schede Ethernet (inclusa ethernet e ricarica)</span><span class="sxs-lookup"><span data-stu-id="df5e9-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="df5e9-135">Adattatori audio digitali USB da C a 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="df5e9-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="df5e9-136">Visori audio digitali USB-C (inclusi gli adattatori visore e la ricarica)</span><span class="sxs-lookup"><span data-stu-id="df5e9-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="df5e9-137">Microfoni esterni USB-C[(Windows Holographic, versione 21H1 e](hololens-release-notes.md#windows-holographic-version-21h1) successive)</span><span class="sxs-lookup"><span data-stu-id="df5e9-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="df5e9-138">Mouse cablato</span><span class="sxs-lookup"><span data-stu-id="df5e9-138">Wired mouse</span></span>
- <span data-ttu-id="df5e9-139">Tastiera cablata</span><span class="sxs-lookup"><span data-stu-id="df5e9-139">Wired keyboard</span></span>
- <span data-ttu-id="df5e9-140">Hub PD combinato (ricarica USB A e PD)</span><span class="sxs-lookup"><span data-stu-id="df5e9-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="df5e9-141">In risposta ai commenti e suggerimenti dei clienti, è stato abilitato il supporto limitato per la connettività cellulare collegata direttamente a HoloLens tramite USB-C.</span><span class="sxs-lookup"><span data-stu-id="df5e9-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="df5e9-142">Per [altre informazioni, vedere Connettersi a Cellulare e 5G.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="df5e9-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="df5e9-143">Supporto microfono esterno USB-C</span><span class="sxs-lookup"><span data-stu-id="df5e9-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df5e9-144">L'inserimento di **un microfono USB non lo imposta automaticamente come dispositivo di input.**</span><span class="sxs-lookup"><span data-stu-id="df5e9-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="df5e9-145">Quando si collega un set di cuffia USB-C, gli utenti osserveranno che l'audio della cuffia verrà reindirizzato automaticamente alle cuffia, ma il sistema operativo HoloLens assegna la priorità all'array di microfoni interni rispetto a qualsiasi altro dispositivo di input.</span><span class="sxs-lookup"><span data-stu-id="df5e9-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="df5e9-146">**Per usare un microfono USB-C, seguire questa procedura.**</span><span class="sxs-lookup"><span data-stu-id="df5e9-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="df5e9-147">Non è possibile usare microfoni esterni nelle build precedenti [a Windows Holographic versione 21H1 e](hololens-release-notes.md#windows-holographic-version-21h1) successive.</span><span class="sxs-lookup"><span data-stu-id="df5e9-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="df5e9-148">Gli utenti possono selezionare microfoni esterni connessi tramite USB-C usando il **pannello Impostazioni** audio.</span><span class="sxs-lookup"><span data-stu-id="df5e9-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="df5e9-149">I microfoni USB-C possono essere usati per chiamare, registrare e così via.</span><span class="sxs-lookup"><span data-stu-id="df5e9-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="df5e9-150">Aprire **l'app Impostazioni** e selezionare **Suono di**  >  **sistema.**</span><span class="sxs-lookup"><span data-stu-id="df5e9-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Impostazioni audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="df5e9-152">Per usare microfoni esterni con **Remote Assist**, gli utenti dovranno fare clic sul collegamento ipertestuale "Gestisci dispositivi audio".</span><span class="sxs-lookup"><span data-stu-id="df5e9-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="df5e9-153">Usare quindi l'elenco a discesa per impostare il microfono esterno su **Predefinito** o **Predefinito comunicazioni.**</span><span class="sxs-lookup"><span data-stu-id="df5e9-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="df5e9-154">Se **si sceglie Predefinito,** il microfono esterno verrà usato ovunque.</span><span class="sxs-lookup"><span data-stu-id="df5e9-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="df5e9-155">Se **si sceglie** Comunicazioni predefinite, il microfono esterno verrà usato in Remote Assist e in altre app di comunicazione, ma l'array di microfoni HoloLens può comunque essere usato per altre attività.</span><span class="sxs-lookup"><span data-stu-id="df5e9-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Gestire i dispositivi audio](images/usbc-mic-2.png)

<br>

![Impostare il microfono predefinito](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="df5e9-158">Informazioni sul supporto del microfono Bluetooth</span><span class="sxs-lookup"><span data-stu-id="df5e9-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="df5e9-159">Sfortunatamente, i microfoni Bluetooth non sono ancora supportati in HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="df5e9-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <a name="troubleshooting-usb-c-microphones"></a><span data-ttu-id="df5e9-160">Risoluzione dei problemi relativi ai microfoni USB-C</span><span class="sxs-lookup"><span data-stu-id="df5e9-160">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="df5e9-161">Tenere presente che alcuni microfoni USB-C segnalano erroneamente se stessi sia come microfono *che come* altoparlante.</span><span class="sxs-lookup"><span data-stu-id="df5e9-161">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="df5e9-162">Si tratta di un problema con il microfono e non con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="df5e9-162">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="df5e9-163">Quando si collega uno di questi microfoni a HoloLens, l'audio potrebbe essere perso.</span><span class="sxs-lookup"><span data-stu-id="df5e9-163">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="df5e9-164">Fortunatamente è disponibile una semplice correzione.</span><span class="sxs-lookup"><span data-stu-id="df5e9-164">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="df5e9-165">In **Settings** System Sound (Impostazioni audio sistema) impostare in modo esplicito gli altoparlanti  ->    ->   **predefiniti (Analog Feature Audio Driver)** come **dispositivo predefinito.**</span><span class="sxs-lookup"><span data-stu-id="df5e9-165">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="df5e9-166">HoloLens deve ricordare questa impostazione anche se il microfono viene rimosso e riconnesso in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="df5e9-166">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Risoluzione dei problemi relativi ai microfoni USB-C](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a><span data-ttu-id="df5e9-168">Hub USB-C</span><span class="sxs-lookup"><span data-stu-id="df5e9-168">USB-C Hubs</span></span>

<span data-ttu-id="df5e9-169">Alcuni utenti potrebbero dover connettere più dispositivi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="df5e9-169">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="df5e9-170">Per gli utenti che desiderano usare un [microfono USB-C](#usb-c-external-microphone-support) insieme a un altro dispositivo connesso, gli hub USB-C possono soddisfare le esigenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="df5e9-170">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="df5e9-171">Microsoft non ha testato questi dispositivi, né è possibile consigliare marchi specifici.</span><span class="sxs-lookup"><span data-stu-id="df5e9-171">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="df5e9-172">**Requisiti per l'hub USB-C e i dispositivi connessi:**</span><span class="sxs-lookup"><span data-stu-id="df5e9-172">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="df5e9-173">I dispositivi connessi non devono richiedere l'installazione di un driver.</span><span class="sxs-lookup"><span data-stu-id="df5e9-173">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="df5e9-174">Il risparmio energia totale di tutti i dispositivi connessi deve essere inferiore a 4,5 Watt.</span><span class="sxs-lookup"><span data-stu-id="df5e9-174">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="df5e9-175">Connettersi a Miracast</span><span class="sxs-lookup"><span data-stu-id="df5e9-175">Connect to Miracast</span></span>

<span data-ttu-id="df5e9-176">Per usare Miracast, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="df5e9-176">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="df5e9-177">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="df5e9-177">Do one of the following:</span></span>  

   - <span data-ttu-id="df5e9-178">Aprire il menu **Start** e selezionare **l'icona** Visualizza.</span><span class="sxs-lookup"><span data-stu-id="df5e9-178">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="df5e9-179">Pronunciare "Connetti" mentre si guarda il menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="df5e9-179">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="df5e9-180">Nell'elenco dei dispositivi visualizzato selezionare un dispositivo disponibile.</span><span class="sxs-lookup"><span data-stu-id="df5e9-180">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="df5e9-181">Completare l'associazione per iniziare a proiettare.</span><span class="sxs-lookup"><span data-stu-id="df5e9-181">Complete the pairing to begin projecting.</span></span>
