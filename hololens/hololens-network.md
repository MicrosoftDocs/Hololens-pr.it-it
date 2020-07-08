---
title: Connettere HoloLens a una rete
description: Istruzioni su come connettersi a Internet con HoloLens e come identificare l'indirizzo IP del dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, wireless, Internet, IP, indirizzo IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 734176dcf8a789f130aa8b010f5f3c9ec1d22c72
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857794"
---
# <span data-ttu-id="8e26d-104">Connettere HoloLens a una rete</span><span class="sxs-lookup"><span data-stu-id="8e26d-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="8e26d-105">Per eseguire la maggior parte delle operazioni in HoloLens, è necessario essere connessi a una rete.</span><span class="sxs-lookup"><span data-stu-id="8e26d-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="8e26d-106">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="8e26d-106">This guide will help you:</span></span>

- <span data-ttu-id="8e26d-107">Connetterti a una rete tramite Wi-Fi o (solo per HoloLens 2) Ethernet tramite USB-C</span><span class="sxs-lookup"><span data-stu-id="8e26d-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="8e26d-108">Disabilitare e riabilitare il Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="8e26d-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="8e26d-109">Leggi altre informazioni sull'[uso di HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="8e26d-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="8e26d-110">Connessione per la prima volta</span><span class="sxs-lookup"><span data-stu-id="8e26d-110">Connecting for the first time</span></span>

<span data-ttu-id="8e26d-111">La prima volta che usi HoloLens, dovrai seguire le istruzioni per la connessione a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="8e26d-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="8e26d-112">In caso di problemi di connessione a una rete Wi-Fi durante l'installazione, verifica che la rete sia aperta, protetta da password o captive portal.</span><span class="sxs-lookup"><span data-stu-id="8e26d-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="8e26d-113">Verifica che la rete non richieda l'uso di un certificato per la connessione.</span><span class="sxs-lookup"><span data-stu-id="8e26d-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="8e26d-114">Dopo la configurazione, potrai connetterti ad altri tipi di reti Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="8e26d-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="8e26d-115">Connessione alla rete Wi-Fi dopo la configurazione</span><span class="sxs-lookup"><span data-stu-id="8e26d-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="8e26d-116">Seleziona **Start** > **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-116">Select **Start** > **Settings**.</span></span>
   - <span data-ttu-id="8e26d-117">*Solo HoloLens (prima generazione)*: usa lo sguardo per inserire l'app Impostazioni, quindi simula il tocco per posizionarla oppure pronuncia "Posizionare".</span><span class="sxs-lookup"><span data-stu-id="8e26d-117">*HoloLens (1st gen) only*: Use your gaze to position the Settings app, then air tap to place it, or say "Place."</span></span>
1. <span data-ttu-id="8e26d-118">Seleziona **Rete e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="8e26d-119">Se non vedi la tua rete, scorri in basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8e26d-119">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="8e26d-120">Seleziona una rete, quindi fai clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-120">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="8e26d-121">Se viene richiesto di digitare una password di rete, inseriscila, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-121">If you are prompted for a network password type it and then select **Next**.</span></span>

## <span data-ttu-id="8e26d-122">Connessione a una rete Wi-Fi su HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="8e26d-122">Connecting to Wi-Fi on HoloLens (1st gen)</span></span>

<span data-ttu-id="8e26d-123">HoloLens contiene una radio Wi-Fi 2x2, con supporto di 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="8e26d-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="8e26d-124">La connessione di HoloLens a una rete Wi-Fi avviene in modo simile alla connessione di un dispositivo desktop o mobile Windows 10 a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="8e26d-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Impostazioni Wi-Fi di HoloLens](./images/wifi-hololens-600px.jpg)

1. <span data-ttu-id="8e26d-126">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-126">Open the **Start** menu.</span></span>
1. <span data-ttu-id="8e26d-127">Seleziona l'app Impostazioni da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-127">Select the Settings app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="8e26d-128">L'app Impostazioni verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="8e26d-128">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="8e26d-129">Seleziona **Rete e Internet**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-129">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="8e26d-130">Verifica che il Wi-Fi sia attivato.</span><span class="sxs-lookup"><span data-stu-id="8e26d-130">Make sure Wi-Fi is turned on.</span></span>
1. <span data-ttu-id="8e26d-131">Seleziona una rete Wi-Fi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8e26d-131">Select a Wi-Fi network from the list.</span></span>
1. <span data-ttu-id="8e26d-132">Se necessario, digita la password della rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="8e26d-132">If needed, type in the Wi-Fi network password.</span></span>

<span data-ttu-id="8e26d-133">Puoi anche verificare che la connessione a una rete Wi-Fi sia stabilita, controllando lo stato Wi-Fi nel menu **Start**:</span><span class="sxs-lookup"><span data-stu-id="8e26d-133">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="8e26d-134">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-134">Open the **Start** menu.</span></span>
1. <span data-ttu-id="8e26d-135">In alto a sinistra del menu **Start** controlla lo stato del Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="8e26d-135">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="8e26d-136">Verranno visualizzati stato del Wi-Fi e SSID della rete connessa.</span><span class="sxs-lookup"><span data-stu-id="8e26d-136">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="8e26d-137">Risoluzione dei problemi relativi alla connessione al Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="8e26d-137">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="8e26d-138">Se si verificano problemi di connessione al Wi-Fi, vedere [Non riesco a connettermi al Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="8e26d-138">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="8e26d-139">Quando si accede a un account aziendale o dell'organizzazione sul dispositivo, è possibile che vengano applicati anche criteri di gestione di dispositivi mobili (MDM), se i criteri sono configurati dall'amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="8e26d-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="8e26d-140">Disabilitazione della rete Wi-Fi in HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="8e26d-140">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="8e26d-141">Uso dell'app Impostazioni in HoloLens</span><span class="sxs-lookup"><span data-stu-id="8e26d-141">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="8e26d-142">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-142">Open the **Start** menu.</span></span>
1. <span data-ttu-id="8e26d-143">Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-143">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="8e26d-144">L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="8e26d-144">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="8e26d-145">Seleziona **Rete e Internet**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-145">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="8e26d-146">Seleziona il dispositivo di scorrimento Wi-Fi per spostarlo nella posizione **Off**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-146">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="8e26d-147">I componenti RF della radio Wi-Fi verranno disattivati e tutte le funzionalità Wi-Fi in HoloLens verranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="8e26d-147">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="8e26d-148">Quando la radio Wi-Fi è disabilitata, HoloLens non sarà in grado di caricare automaticamente gli [spazi](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="8e26d-148">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="8e26d-149">Sposta il dispositivo di scorrimento sulla posizione **Attivato** per attivare la radio Wi-Fi e ripristinare la funzionalità Wi-Fi su Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8e26d-149">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="8e26d-150">Lo stato della radio Wi-Fi selezionato (**Attivato** o **Disattivato**) verrà mantenuto a ogni riavvio.</span><span class="sxs-lookup"><span data-stu-id="8e26d-150">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="8e26d-151">Identificazione dell'indirizzo IP di HoloLens nella rete Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="8e26d-151">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="8e26d-152">Usando l'app Impostazioni</span><span class="sxs-lookup"><span data-stu-id="8e26d-152">By using the Settings app</span></span>

1. <span data-ttu-id="8e26d-153">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-153">Open the **Start** menu.</span></span>
1. <span data-ttu-id="8e26d-154">Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-154">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="8e26d-155">L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="8e26d-155">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="8e26d-156">Seleziona **Rete e Internet**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-156">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="8e26d-157">Scorri in basso verso la fine dell'elenco delle reti Wi-Fi disponibili e seleziona **Proprietà hardware**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-157">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Proprietà hardware nelle impostazioni Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="8e26d-159">L'indirizzo IP viene visualizzato accanto all'**indirizzo IPv4**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-159">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="8e26d-160">Usando Cortana</span><span class="sxs-lookup"><span data-stu-id="8e26d-160">By using Cortana</span></span>

<span data-ttu-id="8e26d-161">Pronunciare "Ehi Cortana, qual è il mio indirizzo IP?"</span><span class="sxs-lookup"><span data-stu-id="8e26d-161">Say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="8e26d-162">e Cortana visualizzerà e leggerà l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="8e26d-162">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="8e26d-163">Usando il Portale di dispositivi di Windows</span><span class="sxs-lookup"><span data-stu-id="8e26d-163">By using Windows Device Portal</span></span>

1. <span data-ttu-id="8e26d-164">In un Web browser nel PC apri il [portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="8e26d-164">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="8e26d-165">Passa alla sezione **Reti**.</span><span class="sxs-lookup"><span data-stu-id="8e26d-165">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="8e26d-166">In questa sezione vengono visualizzati l'indirizzo IP e altre informazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="8e26d-166">This section displays your IP address and other network information.</span></span> <span data-ttu-id="8e26d-167">Usando questo metodo, potrai copiare e incollare l'indirizzo IP nel PC di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8e26d-167">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
