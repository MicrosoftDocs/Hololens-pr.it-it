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
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009524"
---
# <span data-ttu-id="25a22-104">Connettere HoloLens a una rete</span><span class="sxs-lookup"><span data-stu-id="25a22-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="25a22-105">Per eseguire la maggior parte delle operazioni in HoloLens, è necessario essere connessi a una rete.</span><span class="sxs-lookup"><span data-stu-id="25a22-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="25a22-106">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="25a22-106">This guide will help you:</span></span>

- <span data-ttu-id="25a22-107">Connetterti a una rete tramite Wi-Fi o (solo per HoloLens 2) Ethernet tramite USB-C</span><span class="sxs-lookup"><span data-stu-id="25a22-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="25a22-108">Disabilitare e riabilitare il Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="25a22-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="25a22-109">Leggi altre informazioni sull'[uso di HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="25a22-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="25a22-110">Connessione per la prima volta</span><span class="sxs-lookup"><span data-stu-id="25a22-110">Connecting for the first time</span></span>

<span data-ttu-id="25a22-111">La prima volta che usi HoloLens, dovrai seguire le istruzioni per la connessione a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="25a22-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="25a22-112">In caso di problemi di connessione a una rete Wi-Fi durante l'installazione, verifica che la rete sia aperta, protetta da password o captive portal.</span><span class="sxs-lookup"><span data-stu-id="25a22-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="25a22-113">Verifica che la rete non richieda l'uso di un certificato per la connessione.</span><span class="sxs-lookup"><span data-stu-id="25a22-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="25a22-114">Dopo la configurazione, potrai connetterti ad altri tipi di reti Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="25a22-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="25a22-115">Sui dispositivi HoloLens 2 un utente potrebbe anche [usare un adattatore USB-C per Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) per collegarsi direttamente al Wi-Fi e facilitare la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25a22-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="25a22-116">Dopo aver configurato il dispositivo, l'utente può continuare a usare l'adattatore, oppure potrebbe scollegare il dispositivo dalla scheda e [connettersi a una rete Wi-Fi dopo la configurazione](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="25a22-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="25a22-117">Connessione alla rete Wi-Fi dopo la configurazione</span><span class="sxs-lookup"><span data-stu-id="25a22-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="25a22-118">Eseguire il **gesto Start** e selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="25a22-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="25a22-119">L'app Impostazioni verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="25a22-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="25a22-120">Seleziona **Rete e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="25a22-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="25a22-121">Verifica che il Wi-Fi sia attivato.</span><span class="sxs-lookup"><span data-stu-id="25a22-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="25a22-122">Se non vedi la tua rete, scorri in basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="25a22-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="25a22-123">Seleziona una rete, quindi fai clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="25a22-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="25a22-124">Se viene richiesto di digitare una password di rete, inseriscila, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="25a22-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="25a22-125">HoloLens contiene una radio Wi-Fi 2x2, con supporto di 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="25a22-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="25a22-126">La connessione di HoloLens a una rete Wi-Fi avviene in modo simile alla connessione di un dispositivo desktop o mobile Windows 10 a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="25a22-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Impostazioni Wi-Fi di HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="25a22-128">Puoi anche verificare che la connessione a una rete Wi-Fi sia stabilita, controllando lo stato Wi-Fi nel menu **Start**:</span><span class="sxs-lookup"><span data-stu-id="25a22-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="25a22-129">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="25a22-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="25a22-130">In alto a sinistra del menu **Start** controlla lo stato del Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="25a22-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="25a22-131">Verranno visualizzati stato del Wi-Fi e SSID della rete connessa.</span><span class="sxs-lookup"><span data-stu-id="25a22-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="25a22-132">Risoluzione dei problemi relativi alla connessione al Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="25a22-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="25a22-133">Se si verificano problemi di connessione al Wi-Fi, vedere [Non riesco a connettermi al Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="25a22-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="25a22-134">Quando si accede a un account aziendale o dell'organizzazione sul dispositivo, è possibile che vengano applicati anche criteri di gestione di dispositivi mobili (MDM), se i criteri sono configurati dall'amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="25a22-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="25a22-135">VPN</span><span class="sxs-lookup"><span data-stu-id="25a22-135">VPN</span></span>
<span data-ttu-id="25a22-136">Una connessione VPN può essere utile per garantire una connessione più sicura e l'accesso alla rete aziendale e a Internet.</span><span class="sxs-lookup"><span data-stu-id="25a22-136">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="25a22-137">HoloLens 2 supporta il client VPN predefinito e il plug-in VPN UWP (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="25a22-137">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="25a22-138">Protocolli VPN predefiniti supportati:</span><span class="sxs-lookup"><span data-stu-id="25a22-138">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="25a22-139">IKEv2</span><span class="sxs-lookup"><span data-stu-id="25a22-139">IKEv2</span></span>
- <span data-ttu-id="25a22-140">L2TP</span><span class="sxs-lookup"><span data-stu-id="25a22-140">L2TP</span></span>
- <span data-ttu-id="25a22-141">PPTP</span><span class="sxs-lookup"><span data-stu-id="25a22-141">PPTP</span></span>

<span data-ttu-id="25a22-142">Se il certificato viene usato per l'autenticazione per il client VPN predefinito, è necessario aggiungere il certificato client necessario all'archivio certificati utente.</span><span class="sxs-lookup"><span data-stu-id="25a22-142">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="25a22-143">Per scoprire se un plug-in VPN di terze parti supporta HoloLens 2, passare allo Store per individuare l'app VPN e controllare se HoloLens compare tra i dispositivi supportati e se nella pagina dei requisiti di sistema l'app supporta l'architettura ARM o ARM64.</span><span class="sxs-lookup"><span data-stu-id="25a22-143">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="25a22-144">HoloLens supporta solo le applicazioni della piattaforma UWP per la rete VPN di terze parti.</span><span class="sxs-lookup"><span data-stu-id="25a22-144">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="25a22-145">Per impostazione predefinita, la VPN non è abilitata, ma può essere abilitata manualmente andando l'app **Impostazioni**, quindi **Rete e internet > VPN**.</span><span class="sxs-lookup"><span data-stu-id="25a22-145">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="25a22-146">La rete VPN può essere gestita da MDM tramite [Impostazioni/ConsentiVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) e impostata con il [criterio Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="25a22-146">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="25a22-147">Scoprire ulteriori informazioni su [come configurare la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [queste guide](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="25a22-147">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="25a22-148">Disabilitazione della rete Wi-Fi in HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="25a22-148">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="25a22-149">Uso dell'app Impostazioni in HoloLens</span><span class="sxs-lookup"><span data-stu-id="25a22-149">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="25a22-150">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="25a22-150">Open the **Start** menu.</span></span>
1. <span data-ttu-id="25a22-151">Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="25a22-151">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="25a22-152">L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="25a22-152">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="25a22-153">Seleziona **Rete e Internet**.</span><span class="sxs-lookup"><span data-stu-id="25a22-153">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="25a22-154">Seleziona il dispositivo di scorrimento Wi-Fi per spostarlo nella posizione **Off**.</span><span class="sxs-lookup"><span data-stu-id="25a22-154">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="25a22-155">I componenti RF della radio Wi-Fi verranno disattivati e tutte le funzionalità Wi-Fi in HoloLens verranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="25a22-155">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="25a22-156">Quando la radio Wi-Fi è disabilitata, HoloLens non sarà in grado di caricare automaticamente gli [spazi](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="25a22-156">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="25a22-157">Sposta il dispositivo di scorrimento sulla posizione **Attivato** per attivare la radio Wi-Fi e ripristinare la funzionalità Wi-Fi su Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="25a22-157">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="25a22-158">Lo stato della radio Wi-Fi selezionato (**Attivato** o **Disattivato**) verrà mantenuto a ogni riavvio.</span><span class="sxs-lookup"><span data-stu-id="25a22-158">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="25a22-159">Identificazione dell'indirizzo IP di HoloLens nella rete Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="25a22-159">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="25a22-160">Usando l'app Impostazioni</span><span class="sxs-lookup"><span data-stu-id="25a22-160">By using the Settings app</span></span>

1. <span data-ttu-id="25a22-161">Apri il menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="25a22-161">Open the **Start** menu.</span></span>
1. <span data-ttu-id="25a22-162">Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="25a22-162">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="25a22-163">L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.</span><span class="sxs-lookup"><span data-stu-id="25a22-163">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="25a22-164">Seleziona **Rete e Internet**.</span><span class="sxs-lookup"><span data-stu-id="25a22-164">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="25a22-165">Scorri in basso verso la fine dell'elenco delle reti Wi-Fi disponibili e seleziona **Proprietà hardware**.</span><span class="sxs-lookup"><span data-stu-id="25a22-165">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Proprietà hardware nelle impostazioni Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="25a22-167">L'indirizzo IP viene visualizzato accanto all'**indirizzo IPv4**.</span><span class="sxs-lookup"><span data-stu-id="25a22-167">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="25a22-168">Tramite i comandi vocali</span><span class="sxs-lookup"><span data-stu-id="25a22-168">By using voice commands</span></span>

<span data-ttu-id="25a22-169">A seconda del tipo di dispositivo in uso, è possibile usare il comando vocale predefinito o Cortana per visualizzare l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="25a22-169">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="25a22-170">Nelle build successive a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) dire "Qual è il mio indirizzo IP?"</span><span class="sxs-lookup"><span data-stu-id="25a22-170">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="25a22-171">e verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="25a22-171">and it will be displayed.</span></span> <span data-ttu-id="25a22-172">Per le build precedenti o per HoloLens (prima generazione) dire "Ehi Cortana, qual è il mio indirizzo IP?"</span><span class="sxs-lookup"><span data-stu-id="25a22-172">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="25a22-173">e Cortana visualizzerà e leggerà l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="25a22-173">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="25a22-174">Usando il Portale di dispositivi di Windows</span><span class="sxs-lookup"><span data-stu-id="25a22-174">By using Windows Device Portal</span></span>

1. <span data-ttu-id="25a22-175">In un Web browser nel PC apri il [portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="25a22-175">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="25a22-176">Passa alla sezione **Reti**.</span><span class="sxs-lookup"><span data-stu-id="25a22-176">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="25a22-177">In questa sezione vengono visualizzati l'indirizzo IP e altre informazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="25a22-177">This section displays your IP address and other network information.</span></span> <span data-ttu-id="25a22-178">Usando questo metodo, potrai copiare e incollare l'indirizzo IP nel PC di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="25a22-178">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
