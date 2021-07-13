---
title: Enterprise Registrazione di dispositivi HoloLens nell'indirizzo MAC con restrizioni Wi-Fi ambiente
description: Come determinare l'indirizzo MAC per la rete HoloLens 2 dispositivi
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
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639438"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="f0062-103">Enterprise Registrazione di dispositivi HoloLens nell'indirizzo MAC con restrizioni Wi-Fi ambiente</span><span class="sxs-lookup"><span data-stu-id="f0062-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="f0062-104">Questo documento descrive uno scenario comune identificato negli ambienti dei clienti in cui il Wi-Fi è limitato da indirizzi MAC o i certificati sono necessari per l'aggiunta a reti wireless.</span><span class="sxs-lookup"><span data-stu-id="f0062-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="f0062-105">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="f0062-105">Example Scenario</span></span>

<span data-ttu-id="f0062-106">Molti clienti in ambienti sicuri hanno restrizioni sulle reti wireless o cablate che consentono la connessione dei soli dispositivi approvati (in base agli indirizzi MAC).</span><span class="sxs-lookup"><span data-stu-id="f0062-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="f0062-107">Questa operazione può essere applicata tramite il filtro degli indirizzi MAC in un punto di accesso wireless o tramite un server DHCP.</span><span class="sxs-lookup"><span data-stu-id="f0062-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="f0062-108">Inoltre, alcune reti wireless possono essere protette con PEAP, che richiede l'applicazione di un certificato al dispositivo prima di eseguire l'autenticazione nella rete wireless.</span><span class="sxs-lookup"><span data-stu-id="f0062-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="f0062-109">In questo scenario, due requisiti chiave possono introdurre ritardi o richiedere un intervento manuale quando si HoloLens dispositivi alla rete:</span><span class="sxs-lookup"><span data-stu-id="f0062-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="f0062-110">Il certificato PEAP wireless deve essere applicato al dispositivo prima che il dispositivo si unirà correttamente alla rete wireless.</span><span class="sxs-lookup"><span data-stu-id="f0062-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="f0062-111">L'indirizzo MAC dell'adattatore HoloLens Wi-Fi deve essere registrato.</span><span class="sxs-lookup"><span data-stu-id="f0062-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="f0062-112">I principali problemi relativi ai requisiti precedenti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0062-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="f0062-113">L'indirizzo MAC può attualmente essere identificato solo dall'app Impostazioni nel dispositivo o da Intune dopo una registrazione riuscita.</span><span class="sxs-lookup"><span data-stu-id="f0062-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="f0062-114">Senza l'indirizzo MAC, il dispositivo non può essere Wi-Fi rete per iniziare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="f0062-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="f0062-115">Le soluzioni alternative manuali a questi problemi richiedono che un tecnico interagisca con il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0062-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="f0062-116">Soluzioni</span><span class="sxs-lookup"><span data-stu-id="f0062-116">Solutions</span></span>

<span data-ttu-id="f0062-117">Esistono diversi modi per migliorare questa situazione, a seconda dell'infrastruttura disponibile all'interno dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f0062-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="f0062-118">Soluzione</span><span class="sxs-lookup"><span data-stu-id="f0062-118">Solution</span></span> | <span data-ttu-id="f0062-119">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="f0062-119">Benefits</span></span> | <span data-ttu-id="f0062-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0062-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f0062-121">Pacchetto di provisioning con adattatore Ethernet</span><span class="sxs-lookup"><span data-stu-id="f0062-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="f0062-122">Migliora l'esperienza di Gestione guidata e consente un'esperienza di tecnico più rapida.</span><span class="sxs-lookup"><span data-stu-id="f0062-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="f0062-123">HoloLens adattatore USB-C Hub + Ethernet compatibile e il tecnico dovrà comunque interagire con il dispositivo per l'acquisizione MAC e la finalizzazione della Configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="f0062-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="f0062-124">Autopilot con registrazione di Intune su Ethernet</span><span class="sxs-lookup"><span data-stu-id="f0062-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="f0062-125">Si tratta di una connessione in un unico passaggio e della registrazione del dispositivo nell'ambiente del cliente.</span><span class="sxs-lookup"><span data-stu-id="f0062-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="f0062-126">L'acquisizione MAC può essere completata senza dover interagire con il dispositivo</span><span class="sxs-lookup"><span data-stu-id="f0062-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="f0062-127">Intune abilitato per il tenant AAD del cliente e HoloLens adattatore USB-C Ethernet compatibile</span><span class="sxs-lookup"><span data-stu-id="f0062-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="f0062-128">Creazione automatica di report degli indirizzi MAC</span><span class="sxs-lookup"><span data-stu-id="f0062-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="f0062-129">Quando i dispositivi vengono registrati con il tenant di Intune, uno script può segnalare l'indirizzo MAC al tecnico.</span><span class="sxs-lookup"><span data-stu-id="f0062-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="f0062-130">Cmdlet di PowerShell per Intune</span><span class="sxs-lookup"><span data-stu-id="f0062-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="f0062-131">Pacchetto di provisioning con adattatore Ethernet</span><span class="sxs-lookup"><span data-stu-id="f0062-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="f0062-132">Se anche la rete cablata è soggetta a restrizioni MAC, sarà necessario pre-approvato anche l'indirizzo MAC dell'adattatore USB-C Hub + Ethernet.</span><span class="sxs-lookup"><span data-stu-id="f0062-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="f0062-133">È necessario fare attenzione con questa scheda perché consentirà l'accesso alla rete da altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f0062-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="f0062-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0062-134">Requirements</span></span>

- <span data-ttu-id="f0062-135">Porta di rete cablata con accesso alla rete del cliente</span><span class="sxs-lookup"><span data-stu-id="f0062-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="f0062-136">HoloLens Hub USB-C compatibile con adattatore Ethernet: qualsiasi scheda che non richiede driver aggiuntivi o installazioni di applicazioni deve essere adatta.</span><span class="sxs-lookup"><span data-stu-id="f0062-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="f0062-137">Pacchetto di provisioning contenente:</span><span class="sxs-lookup"><span data-stu-id="f0062-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="f0062-138">Contenente le informazioni sulla rete wireless e il certificato</span><span class="sxs-lookup"><span data-stu-id="f0062-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="f0062-139">Facoltativamente, contiene le informazioni di registrazione per l'Azure AD</span><span class="sxs-lookup"><span data-stu-id="f0062-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="f0062-140">Contenente tutte le altre impostazioni di provisioning necessarie</span><span class="sxs-lookup"><span data-stu-id="f0062-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="f0062-141">Processo</span><span class="sxs-lookup"><span data-stu-id="f0062-141">Process</span></span>

<span data-ttu-id="f0062-142">Il processo può variare a seconda del livello software del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0062-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="f0062-143">Se il dispositivo ha [l'aggiornamento di maggio 2004,](hololens-release-notes.md#windows-holographic-version-2004)seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f0062-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="f0062-144">Posizionare il pacchetto di provisioning nella radice di una chiavetta USB e collegarlo all'hub.</span><span class="sxs-lookup"><span data-stu-id="f0062-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="f0062-145">Connessione Cavo Ethernet per la scheda Hub + Ethernet.</span><span class="sxs-lookup"><span data-stu-id="f0062-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="f0062-146">Connessione Hub USB-C per HoloLens dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0062-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="f0062-147">Accendere il HoloLens e posizionare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0062-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="f0062-148">Premere il **pulsante Volume down (Volume in basso) e Power** (Alimentazione) per applicare il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="f0062-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="f0062-149">Il tecnico può ora seguire la Configurazione guidata e, al termine, aprire l'app Impostazioni per recuperare l'indirizzo MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0062-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="f0062-150">Se il dispositivo ha una build del sistema operativo prima dell'aggiornamento di maggio [2004,](hololens-release-notes.md#windows-holographic-version-2004)seguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f0062-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="f0062-151">Accendere il HoloLens collegare il dispositivo a un PC.</span><span class="sxs-lookup"><span data-stu-id="f0062-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="f0062-152">Il dispositivo dovrebbe essere visualizzato nel PC come dispositivo di archiviazione file.</span><span class="sxs-lookup"><span data-stu-id="f0062-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="f0062-153">Copiare il pacchetto di provisioning nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="f0062-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="f0062-154">Connessione Cavo Ethernet all'hub.</span><span class="sxs-lookup"><span data-stu-id="f0062-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="f0062-155">Connessione Hub USB-C per HoloLens dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0062-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="f0062-156">Inserire nella HoloLens</span><span class="sxs-lookup"><span data-stu-id="f0062-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="f0062-157">Premere il **pulsante Volume down (Volume in** basso) e Power (Alimentazione) per applicare il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="f0062-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="f0062-158">Il tecnico può ora seguire la Configurazione guidata e, al termine, aprire l'app Impostazioni per recuperare l'indirizzo MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0062-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="f0062-159">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="f0062-159">Benefits</span></span>

<span data-ttu-id="f0062-160">In questo modo sarà possibile applicare il pacchetto di provisioning corretto e raccogliere l'indirizzo MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0062-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="f0062-161">I pacchetti di provisioning possono essere creati seguendo le indicazioni riportate qui.</span><span class="sxs-lookup"><span data-stu-id="f0062-161">Provisioning packages can be created following the guidance here.</span></span>](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="f0062-162">Autopilot con registrazione di Intune</span><span class="sxs-lookup"><span data-stu-id="f0062-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="f0062-163">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0062-163">Requirements</span></span>

- <span data-ttu-id="f0062-164">Porta di rete cablata con accesso alla rete del cliente</span><span class="sxs-lookup"><span data-stu-id="f0062-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="f0062-165">HoloLens dispositivi che eseguono Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="f0062-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="f0062-166">HoloLens Scheda Ethernet USB-C compatibile</span><span class="sxs-lookup"><span data-stu-id="f0062-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="f0062-167">Intune configurato e abilitato per il tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="f0062-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="f0062-168">Dispositivo registrato per Autopilot e importato nel tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="f0062-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="f0062-169">Criteri di Intune definiti per il dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f0062-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="f0062-170">Contenente le informazioni sulla rete wireless e il certificato</span><span class="sxs-lookup"><span data-stu-id="f0062-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="f0062-171">Contenente tutte le altre impostazioni di provisioning necessarie</span><span class="sxs-lookup"><span data-stu-id="f0062-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="f0062-172">Ciò consentirà a un cliente con requisiti di rete avanzati di registrare i dispositivi in un approccio scalabile e hands-off</span><span class="sxs-lookup"><span data-stu-id="f0062-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="f0062-173">Saranno necessari altri prerequisiti, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0062-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="f0062-174">[Abilitare il tenant per l'anteprima di Autopilot.](hololens2-autopilot.md)</span><span class="sxs-lookup"><span data-stu-id="f0062-174">[Enable the Tenant for the Autopilot preview](hololens2-autopilot.md).</span></span>
1. <span data-ttu-id="f0062-175">Creare i criteri HoloLens per sostituire il pacchetto di provisioning in Intune.</span><span class="sxs-lookup"><span data-stu-id="f0062-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="f0062-176">Creare il HoloLens criteri di Intune.</span><span class="sxs-lookup"><span data-stu-id="f0062-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="f0062-177">Assegnare i dispositivi al gruppo corretto.</span><span class="sxs-lookup"><span data-stu-id="f0062-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="f0062-178">Processo</span><span class="sxs-lookup"><span data-stu-id="f0062-178">Process</span></span>

1. <span data-ttu-id="f0062-179">Connessione il cavo ethernet all'adattatore e collegare l'adattatore alla porta USB-C sul HoloLens 2 dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f0062-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="f0062-180">Attivare il HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f0062-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="f0062-181">Il dispositivo deve connettersi automaticamente a Internet durante la Configurazione guidata tramite l'adattatore Ethernet.</span><span class="sxs-lookup"><span data-stu-id="f0062-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="f0062-182">Dovrebbe rilevare la configurazione di Autopilot e registrarsi automaticamente con Azure AD e Intune.</span><span class="sxs-lookup"><span data-stu-id="f0062-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="f0062-183">Il dispositivo applicherà i certificati Wi-Fi e altre configurazioni necessarie tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="f0062-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="f0062-184">Al termine, il tecnico può caricare il portale di Intune (Endpoint Manager) ed esaminare la pagina delle proprietà del dispositivo in **Home -> Devices -> DeviceName -> Hardware**.</span><span class="sxs-lookup"><span data-stu-id="f0062-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="f0062-185">Il Wi-Fi MAC sarà visibile all'interno del portale di Intune.</span><span class="sxs-lookup"><span data-stu-id="f0062-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Indirizzo MAC tramite Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="f0062-187">Il tecnico aggiungerà questo indirizzo MAC come dispositivo consentito.</span><span class="sxs-lookup"><span data-stu-id="f0062-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="f0062-188">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="f0062-188">Benefits</span></span>

<span data-ttu-id="f0062-189">Ciò consentirà un'esperienza di distribuzione "Heads off" per il tecnico, con il dispositivo in grado di passare dalla casella alla registrazione in Azure AD e Intune senza che il tecnico abbia la necessità di portare il dispositivo o interagire manualmente con l'ambiente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f0062-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="f0062-190">Segnalazione di indirizzi MAC al tecnico</span><span class="sxs-lookup"><span data-stu-id="f0062-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="f0062-191">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0062-191">Requirements</span></span>

- <span data-ttu-id="f0062-192">Autorizzazione di "Intune Graph PowerShell" per il tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="f0062-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="f0062-193">Installazione di Intune Graph PowerShell nel computer dei tecnici.</span><span class="sxs-lookup"><span data-stu-id="f0062-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="f0062-194">Accesso in lettura agli elementi "Dispositivi gestiti" di Intune.</span><span class="sxs-lookup"><span data-stu-id="f0062-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="f0062-195">(Operatore help desk o versione superiore o un ruolo personalizzato)</span><span class="sxs-lookup"><span data-stu-id="f0062-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="f0062-196">Al momento non esiste un modo "semplice" per attivare un comando di automazione basato sulla registrazione di un nuovo dispositivo in Intune.</span><span class="sxs-lookup"><span data-stu-id="f0062-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="f0062-197">Di conseguenza, questo comando fornirà al tecnico un modo semplice per recuperare l'indirizzo MAC senza dover accedere al portale e recuperarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="f0062-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="f0062-198">Verranno restituiti il nome e l'indirizzo MAC HoloLens dispositivi registrati negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f0062-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![Indirizzo MAC tramite PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="f0062-200">Processo</span><span class="sxs-lookup"><span data-stu-id="f0062-200">Process</span></span>

<span data-ttu-id="f0062-201">Al termine della registrazione di Intune, il tecnico eseguirebbe lo script precedente per recuperare l'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="f0062-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
