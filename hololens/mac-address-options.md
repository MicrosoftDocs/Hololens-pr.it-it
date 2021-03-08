---
title: Registrazione dei dispositivi HoloLens in ambienti Wi-Fi aziendali con accesso limitato in base all'indirizzo MAC
description: Come recuperare gli indirizzi MAC dei dispositivi HoloLens 2 per le reti
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393840"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="49658-103">Registrazione dei dispositivi HoloLens in ambienti Wi-Fi aziendali con accesso limitato in base all'indirizzo MAC</span><span class="sxs-lookup"><span data-stu-id="49658-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="49658-104">Questo documento descrive uno scenario comune identificato negli ambienti dei clienti in cui la rete Wi-Fi è limitata in base agli indirizzi MAC, oppure dei certificati sono richiesti per accedere alle reti wireless.</span><span class="sxs-lookup"><span data-stu-id="49658-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="49658-105">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="49658-105">Example Scenario</span></span>

<span data-ttu-id="49658-106">Molti clienti in ambienti sicuri hanno restrizioni sulle reti wireless o cablate che consentiranno la connessione dei dispositivi approvati (in base agli indirizzi MAC).</span><span class="sxs-lookup"><span data-stu-id="49658-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="49658-107">Questo può essere applicato tramite il filtro degli indirizzi MAC su un punto di accesso wireless o tramite un server DHCP.</span><span class="sxs-lookup"><span data-stu-id="49658-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="49658-108">Inoltre, alcune reti wireless possono essere protette con PEAP, che richiede l'applicazione di un certificato al dispositivo prima dell'autenticazione nella rete wireless.</span><span class="sxs-lookup"><span data-stu-id="49658-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="49658-109">In questo scenario, due requisiti chiave possono introdurre ritardi o richiedere un intervento manuale quando si uniscono i dispositivi HoloLens alla rete:</span><span class="sxs-lookup"><span data-stu-id="49658-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="49658-110">Il certificato PEAP della rete wireless deve essere applicato al dispositivo prima che possa connettersi alla rete wireless.</span><span class="sxs-lookup"><span data-stu-id="49658-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="49658-111">L'indirizzo MAC della scheda Wi-Fi di HoloLens deve essere registrato.</span><span class="sxs-lookup"><span data-stu-id="49658-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="49658-112">Le sfide principali con i requisiti precedenti sono:</span><span class="sxs-lookup"><span data-stu-id="49658-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="49658-113">L'indirizzo MAC può attualmente essere identificato solo dall'app Impostazioni nel dispositivo o da Intune dopo una registrazione riuscita.</span><span class="sxs-lookup"><span data-stu-id="49658-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>
2. <span data-ttu-id="49658-114">Senza l'indirizzo MAC, il dispositivo non può accedere alla rete Wi-Fi per iniziare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="49658-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="49658-115">Le soluzioni alternative manuali a queste sfide richiedono a un tecnico di interagire con il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49658-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="49658-116">Soluzioni</span><span class="sxs-lookup"><span data-stu-id="49658-116">Solutions</span></span>

<span data-ttu-id="49658-117">Esistono molti modi per migliorare questa situazione, a seconda dell'infrastruttura disponibile nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="49658-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="49658-118">Soluzione</span><span class="sxs-lookup"><span data-stu-id="49658-118">Solution</span></span> | <span data-ttu-id="49658-119">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="49658-119">Benefits</span></span> | <span data-ttu-id="49658-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49658-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="49658-121">Pacchetto di provisioning con adattatore Ethernet</span><span class="sxs-lookup"><span data-stu-id="49658-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="49658-122">Migliora l'esperienza di configurazione guidata e consente interventi tecnici più rapidi.</span><span class="sxs-lookup"><span data-stu-id="49658-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="49658-123">Scheda Hub USB-C compatibile con HoloLens e il tecnico dovrà comunque interagire con il dispositivo per l'acquisizione MAC e la finalizzazione della Configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="49658-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalisation</span></span> |
| <span data-ttu-id="49658-124">Registrazione di Autopilot con Intune tramite ethernet</span><span class="sxs-lookup"><span data-stu-id="49658-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="49658-125">Si tratta di una connessione e registrazione passo a passo del dispositivo nell'ambiente del cliente.</span><span class="sxs-lookup"><span data-stu-id="49658-125">This is a single step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="49658-126">L'acquisizione MAC può essere completata senza dover interagire con il dispositivo</span><span class="sxs-lookup"><span data-stu-id="49658-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="49658-127">Intune abilitato per il tenant AAD del cliente e una scheda Ethernet USB-C compatibile con HoloLens</span><span class="sxs-lookup"><span data-stu-id="49658-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="49658-128">Rilevamento automatico degli indirizzi MAC</span><span class="sxs-lookup"><span data-stu-id="49658-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="49658-129">Quando i dispositivi vengono registrati con il tenant di Intune, uno script può segnalare l'indirizzo MAC al tecnico.</span><span class="sxs-lookup"><span data-stu-id="49658-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="49658-130">Cmdlet di PowerShell in Intune</span><span class="sxs-lookup"><span data-stu-id="49658-130">Intune Powershell Commandlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="49658-131">Pacchetto di provisioning con scheda Ethernet</span><span class="sxs-lookup"><span data-stu-id="49658-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="49658-132">Se anche la rete cablata è soggetta a restrizioni MAC, sarà necessario che sia pre-approvato anche l'indirizzo MAC della scheda Hub + Ethernet USB-C.</span><span class="sxs-lookup"><span data-stu-id="49658-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="49658-133">È necessario fare attenzione con questa scheda perché consentirà l'accesso alla rete da altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="49658-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="49658-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49658-134">Requirements</span></span>

- <span data-ttu-id="49658-135">Porta di rete cablata con accesso alla rete del cliente</span><span class="sxs-lookup"><span data-stu-id="49658-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="49658-136">Hub USB-C compatibile holoLens con scheda Ethernet: qualsiasi scheda che&#39;non richieda driver aggiuntivi o installazioni di applicazioni dovrebbe essere adatta.</span><span class="sxs-lookup"><span data-stu-id="49658-136">HoloLens Compatible USB-C Hub with Ethernet adaptor – Any adapter that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="49658-137">Pacchetto di provisioning contenente:</span><span class="sxs-lookup"><span data-stu-id="49658-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="49658-138">Informazioni e certificati per la rete wireless</span><span class="sxs-lookup"><span data-stu-id="49658-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="49658-139">Informazioni per la registrazione dell'app Azure AD aziendale&#39;s (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="49658-139">Optionally containing enrollment information for the Organization&#39;s Azure AD</span></span>
  - <span data-ttu-id="49658-140">Qualsiasi altra impostazione di provisioning necessaria</span><span class="sxs-lookup"><span data-stu-id="49658-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="49658-141">Process</span><span class="sxs-lookup"><span data-stu-id="49658-141">Process</span></span>

<span data-ttu-id="49658-142">Il processo può variare in base al software del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49658-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="49658-143">Se sul dispositivo è installato l'[aggiornamento di maggio 2004](hololens-release-notes.md#windows-holographic-version-2004), seguire i passi sottostanti.</span><span class="sxs-lookup"><span data-stu-id="49658-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="49658-144">Mettere il pacchetto di provisioning nel percorso root di una chiavetta USB, e collegarla all'hub.</span><span class="sxs-lookup"><span data-stu-id="49658-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="49658-145">Collegare il cavo Ethernet alla scheda Hub + Ethernet.</span><span class="sxs-lookup"><span data-stu-id="49658-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="49658-146">Connettere l'hub USB-C al dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="49658-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="49658-147">Attivare HoloLens e posizionare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49658-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="49658-148">Premere **Volume - e il pulsante di accensione** per applicare il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="49658-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="49658-149">Il tecnico può ora seguire la Configurazione guidata e, al termine, aprire l'app Impostazioni per recuperare l'indirizzo MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49658-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="49658-150">Se sul dispositivo è installato un sistema operativo precedente all'[aggiornamento di maggio 2004](hololens-release-notes.md#windows-holographic-version-2004), seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="49658-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="49658-151">Attivare HoloLens e collegare il dispositivo a un PC.</span><span class="sxs-lookup"><span data-stu-id="49658-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="49658-152">Il dispositivo dovrebbe essere visualizzato nel PC come dispositivo di archiviazione di file.</span><span class="sxs-lookup"><span data-stu-id="49658-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="49658-153">Copiare il pacchetto di provisioning nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="49658-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="49658-154">Collegare il cavo ethernet all'hub.</span><span class="sxs-lookup"><span data-stu-id="49658-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="49658-155">Connettere l'hub USB-C al dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="49658-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="49658-156">Posizionare HoloLens</span><span class="sxs-lookup"><span data-stu-id="49658-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="49658-157">Premere **volume - e il tasto di accensione** per applicare il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="49658-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="49658-158">Il tecnico può ora seguire la Configurazione guidata e, al termine, aprire l'app Impostazioni per recuperare l'indirizzo MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49658-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="49658-159">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="49658-159">Benefits</span></span>

<span data-ttu-id="49658-160">Ciò consente il &quot;Tocco singolo&quot; sul dispositivo per applicare il pacchetto di provisioning corretto e recuperare l'indirizzo MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49658-160">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="49658-161">I pacchetti di provisioning possono essere creati seguendo queste indicazioni.</span><span class="sxs-lookup"><span data-stu-id="49658-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="49658-162">Autopilot con registrazione Intune</span><span class="sxs-lookup"><span data-stu-id="49658-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="49658-163">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49658-163">Requirements</span></span>

- <span data-ttu-id="49658-164">Porta di rete cablata con accesso alla rete del cliente</span><span class="sxs-lookup"><span data-stu-id="49658-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="49658-165">Dispositivi HoloLens su cui è installato Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="49658-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="49658-166">Scheda Ethernet USB-C compatibile HoloLens</span><span class="sxs-lookup"><span data-stu-id="49658-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="49658-167">Intune deve essere configurato e abilitato per il tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="49658-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="49658-168">Dispositivo registrato per Autopilot e importato nel tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="49658-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="49658-169">Criteri di Intune definiti per il dispositivo:</span><span class="sxs-lookup"><span data-stu-id="49658-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="49658-170">Informazioni e certificati per la rete wireless</span><span class="sxs-lookup"><span data-stu-id="49658-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="49658-171">Qualsiasi altra impostazione di provisioning necessaria</span><span class="sxs-lookup"><span data-stu-id="49658-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="49658-172">Ciò consente ai clienti con requisiti di connettività avanzati di registrare i dispositivi seguendo un approccio scalabile e flessibile</span><span class="sxs-lookup"><span data-stu-id="49658-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="49658-173">I prerequisiti aggiuntivi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="49658-173">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="49658-174">Abilitare il tenant per l'anteprima di Autopilot</span><span class="sxs-lookup"><span data-stu-id="49658-174">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="49658-175">Creare i criteri di HoloLens per sostituire il pacchetto di provisioning all'interno di Intune.</span><span class="sxs-lookup"><span data-stu-id="49658-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="49658-176">Creare i criteri di Intune per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="49658-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="49658-177">Assegnare i dispositivi al gruppo corretto.</span><span class="sxs-lookup"><span data-stu-id="49658-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="49658-178">Processo</span><span class="sxs-lookup"><span data-stu-id="49658-178">Process</span></span>

1. <span data-ttu-id="49658-179">Collegare il cavo ethernet alla scheda e collegarlo alla porta USB-C nel dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="49658-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>
2. <span data-ttu-id="49658-180">Attivare HoloLens.</span><span class="sxs-lookup"><span data-stu-id="49658-180">Turn on the HoloLens.</span></span>
3. <span data-ttu-id="49658-181">Il dispositivo deve connettersi automaticamente a Internet durante la configurazione guidata tramite la scheda Ethernet.</span><span class="sxs-lookup"><span data-stu-id="49658-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="49658-182">Dovrebbe rilevare la configurazione di Autopilot e registrarsi automaticamente con Azure AD e Intune</span><span class="sxs-lookup"><span data-stu-id="49658-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="49658-183">Il dispositivo applica le configurazioni e gli altri certificati Wi-Fi necessari tramite Intune</span><span class="sxs-lookup"><span data-stu-id="49658-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="49658-184">Al termine, il tecnico può caricare il portale di Intune (Endpoint Manager) ed eseguire il drill-down nella pagina delle proprietà del dispositivo in **Home -> Dispositivi -> DeviceName -> Hardware**</span><span class="sxs-lookup"><span data-stu-id="49658-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="49658-185">L'indirizzo MAC sarà visibile nel portale Intune</span><span class="sxs-lookup"><span data-stu-id="49658-185">The Wifi MAC address will be visible within the Intune Portal</span></span>

![Indirizzo MAC con Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="49658-187">Il tecnico aggiunge questo indirizzo MAC come un dispositivo autorizzato.</span><span class="sxs-lookup"><span data-stu-id="49658-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="49658-188">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="49658-188">Benefits</span></span>

<span data-ttu-id="49658-189">Ciò offre al tecnico un'esperienza di distribuzione &quot;diretta&quot;, in cui il dispositivo passa dalla scatola alla registrazione in Azure AD e Intune senza che il tecnico debba indossare il dispositivo o interagire manualmente con l'ambiente di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="49658-189">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="49658-190">Segnalazione degli indirizzi MAC al tecnico</span><span class="sxs-lookup"><span data-stu-id="49658-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="49658-191">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49658-191">Requirements</span></span>

- <span data-ttu-id="49658-192">Autorizzazione di &quot;Intune Graph PowerShell&quot; nel tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="49658-192">Authorization of the &quot;Intune Graph PowerShell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="49658-193">Installazione di Intune Graph PowerShell nel computer dei tecnici.</span><span class="sxs-lookup"><span data-stu-id="49658-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="49658-194">Accesso in lettura agli elementi &quot;Dispositivi gestiti&quot; di Intune.</span><span class="sxs-lookup"><span data-stu-id="49658-194">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="49658-195">(Operatore Help desk o superiore, oppure un ruolo su misura)</span><span class="sxs-lookup"><span data-stu-id="49658-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="49658-196">Al momento non esistono modi &quot;semplici&quot; per attivare un comando i base alla registrazione di un nuovo dispositivo con Intune.</span><span class="sxs-lookup"><span data-stu-id="49658-196">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="49658-197">Pertanto, questo comando fornisce al tecnico un modo semplice per recuperare l'indirizzo MAC senza dovere accedere al portale e recuperalo manualmente.</span><span class="sxs-lookup"><span data-stu-id="49658-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="49658-198">In questo modo, verranno restituiti il nome e l'indirizzo MAC di qualsiasi dispositivo HoloLens registrato nei 30 giorni precedenti.</span><span class="sxs-lookup"><span data-stu-id="49658-198">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Indirizzo MAC con PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="49658-200">Process</span><span class="sxs-lookup"><span data-stu-id="49658-200">Process</span></span>

<span data-ttu-id="49658-201">Una volta completata la registrazione su Intune, il tecnico esegue lo script sovrastante per recuperare l'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="49658-201">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
