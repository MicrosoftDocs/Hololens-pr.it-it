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
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093236"
---
# <span data-ttu-id="6280c-103">Registrazione dei dispositivi HoloLens in ambienti Wi-Fi aziendali con accesso limitato in base all'indirizzo MAC</span><span class="sxs-lookup"><span data-stu-id="6280c-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="6280c-104">Questo documento descrive uno scenario comune identificato negli ambienti dei clienti in cui la rete Wi-Fi è limitata in base agli indirizzi MAC, oppure dei certificati sono richiesti per accedere alle reti wireless.</span><span class="sxs-lookup"><span data-stu-id="6280c-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="6280c-105">Scenario di esempio:</span><span class="sxs-lookup"><span data-stu-id="6280c-105">Example Scenario</span></span>

<span data-ttu-id="6280c-106">Molti clienti in ambienti sicuri hanno limitato l'accesso alle reti wireless o cablate solo per i dispositivi approvati, in base ai loro indirizzi MAC e tramite il filtro degli indirizzi MAC su un punto di accesso wireless o un server DHCP.</span><span class="sxs-lookup"><span data-stu-id="6280c-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="6280c-107">Inoltre, alcune reti wireless possono essere protette con PEAP, che richiede l'applicazione di un certificato ai dispositivi prima di potersi autenticare correttamente alla rete wireless.</span><span class="sxs-lookup"><span data-stu-id="6280c-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="6280c-108">Possono emergere due problematiche che causano ritardi e richiedono l'intervento manuale per accedere alla rete con i dispositivi HoloLens.  </span><span class="sxs-lookup"><span data-stu-id="6280c-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="6280c-109">Il certificato PEAP della rete wireless deve essere applicato al dispositivo prima che possa connettersi alla rete wireless.</span><span class="sxs-lookup"><span data-stu-id="6280c-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="6280c-110">L'indirizzo MAC della scheda Wi-Fi di HoloLens deve essere registrato.</span><span class="sxs-lookup"><span data-stu-id="6280c-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="6280c-111">Le principali sfide sono:</span><span class="sxs-lookup"><span data-stu-id="6280c-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="6280c-112">Al momento, l'indirizzo MAC può essere identificato soltanto tramite l'app Impostazioni nel dispositivo, o tramite Intune dopo essersi registrati su Intune.</span><span class="sxs-lookup"><span data-stu-id="6280c-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="6280c-113">Senza l'indirizzo MAC, il dispositivo non può accedere alla rete Wi-Fi per iniziare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="6280c-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="6280c-114">Le soluzioni manuali di questi problemi richiedono l'intervento tecnico sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6280c-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="6280c-115">Soluzioni</span><span class="sxs-lookup"><span data-stu-id="6280c-115">Solutions</span></span>

<span data-ttu-id="6280c-116">Esistono numerosi modi per migliorare questa situazione, a seconda dell'infrastruttura disponibile nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="6280c-116">There are a number of ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="6280c-117">Soluzione</span><span class="sxs-lookup"><span data-stu-id="6280c-117">Solution</span></span> | <span data-ttu-id="6280c-118">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="6280c-118">Benefits</span></span> | <span data-ttu-id="6280c-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6280c-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6280c-120">Pacchetto di provisioning con adattatore Ethernet</span><span class="sxs-lookup"><span data-stu-id="6280c-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="6280c-121">Migliora l'esperienza di configurazione guidata e consente interventi tecnici più rapidi.</span><span class="sxs-lookup"><span data-stu-id="6280c-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="6280c-122">Hub USB-C compatibile con HoloLensIl tecnico deve comunque interagire con il dispositivo per recuperare l'indirizzo MAC e finalizzare la configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="6280c-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalisation</span></span> |
| <span data-ttu-id="6280c-123">Registrazione di Autopilot con Intune tramite ethernet</span><span class="sxs-lookup"><span data-stu-id="6280c-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="6280c-124">Connessione a singolo passaggio e registrazione del dispositivo nell'ambiente del clienteIl recupero dell'indirizzo MAC può essere completato senza interagire con il dispositivo</span><span class="sxs-lookup"><span data-stu-id="6280c-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="6280c-125">Intune abilitato per il tenant AAD del clienteAdattatore di rete USB-C compatibile con HoloLens</span><span class="sxs-lookup"><span data-stu-id="6280c-125">Intune enabled for the customer AAD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="6280c-126">Rilevamento automatico degli indirizzi MAC</span><span class="sxs-lookup"><span data-stu-id="6280c-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="6280c-127">Quando i dispositivi sono stati registrati nel tenant di Intune, l'indirizzo MAC viene segnalato tramite script al tecnico.</span><span class="sxs-lookup"><span data-stu-id="6280c-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="6280c-128">Cmdlet di PowerShell in Intune</span><span class="sxs-lookup"><span data-stu-id="6280c-128">Intune Powershell Commandlets</span></span> |

## <span data-ttu-id="6280c-129">Pacchetto di provisioning con adattatore Ethernet</span><span class="sxs-lookup"><span data-stu-id="6280c-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="6280c-130">Se anche la rete cablata è sottoposta alle limitazioni MAC, l'indirizzo MAC dell'adattatore / hub ethernet USB-C dovrà essere approvato preventivamente.</span><span class="sxs-lookup"><span data-stu-id="6280c-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="6280c-131">Occorre prestare attenzione con l'hub, perché consentirà di accedere alla rete con altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6280c-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="6280c-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6280c-132">Requirements</span></span>

- <span data-ttu-id="6280c-133">Porta di rete cablata con accesso alla rete del cliente</span><span class="sxs-lookup"><span data-stu-id="6280c-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="6280c-134">Hub USB-C compatibile con HoloLens e contenente un adattatore ethernet. Qualsiasi hub che non richiede di installare applicazioni o driver aggiuntivi dovrebbe essere idoneo.</span><span class="sxs-lookup"><span data-stu-id="6280c-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="6280c-135">Pacchetto di provisioning contenente:</span><span class="sxs-lookup"><span data-stu-id="6280c-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="6280c-136">Informazioni e certificati per la rete wireless</span><span class="sxs-lookup"><span data-stu-id="6280c-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="6280c-137">Informazioni per la registrazione dell'app Azure AD aziendale (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="6280c-137">Optionally containing enrollment information for the Organisation&#39;s Azure AD</span></span>
  - <span data-ttu-id="6280c-138">Qualsiasi altra impostazione di provisioning necessaria</span><span class="sxs-lookup"><span data-stu-id="6280c-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="6280c-139">Process</span><span class="sxs-lookup"><span data-stu-id="6280c-139">Process</span></span>

<span data-ttu-id="6280c-140">Il processo può variare in base al software del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6280c-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="6280c-141">Se sul dispositivo è installato l'[aggiornamento di maggio 2004](hololens-release-notes.md#windows-holographic-version-2004), seguire i passi sottostanti.</span><span class="sxs-lookup"><span data-stu-id="6280c-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="6280c-142">Mettere il pacchetto di provisioning nel percorso root di una chiavetta USB, e collegarla all'hub.</span><span class="sxs-lookup"><span data-stu-id="6280c-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="6280c-143">Collegare il cavo ethernet all'hub.</span><span class="sxs-lookup"><span data-stu-id="6280c-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="6280c-144">Collegare il cavo USB-C al dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6280c-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="6280c-145">Accendere l'HoloLens e indossare il dispositivo. </span><span class="sxs-lookup"><span data-stu-id="6280c-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="6280c-146">Premere **volume - e il pulsante di accensione** per applicare il pacchetto di provisioning. </span><span class="sxs-lookup"><span data-stu-id="6280c-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="6280c-147">Il tecnico può ora seguire OOBE e, una volta finito, aprire l'app Impostazioni e recuperare l'indirizzo MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6280c-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="6280c-148">Se sul dispositivo è installato un sistema operativo precedente all'[aggiornamento di maggio 2004](hololens-release-notes.md#windows-holographic-version-2004), seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6280c-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="6280c-149">Attivare il dispositivo HoloLens e collegarlo a un PC.</span><span class="sxs-lookup"><span data-stu-id="6280c-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="6280c-150">Il dispositivo dovrebbe essere visualizzato nel PC come dispositivo di archiviazione di file.</span><span class="sxs-lookup"><span data-stu-id="6280c-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="6280c-151">Copiare il pacchetto di provisioning nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="6280c-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="6280c-152">Collegare il cavo ethernet all'hub.</span><span class="sxs-lookup"><span data-stu-id="6280c-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="6280c-153">Collegare il cavo USB-C al dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6280c-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="6280c-154">Indossare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6280c-154">Wear the device.</span></span>
7. <span data-ttu-id="6280c-155">Premere **volume - e il tasto di accensione** per applicare il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="6280c-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="6280c-156">Il tecnico può ora seguire OOBE e, una volta finito, aprire l'app Impostazioni e recuperare l'indirizzo MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6280c-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="6280c-157">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="6280c-157">Benefits</span></span>

<span data-ttu-id="6280c-158">Ciò consente il &quot;Tocco singolo&quot; sul dispositivo per applicare il pacchetto di provisioning corretto e recuperare l'indirizzo MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6280c-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="6280c-159">I pacchetti di provisioning possono essere creati seguendo queste indicazioni.</span><span class="sxs-lookup"><span data-stu-id="6280c-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="6280c-160">Registrazione per Autopilot con Intune</span><span class="sxs-lookup"><span data-stu-id="6280c-160">Autopilot with Intune Enrolment</span></span>

### <span data-ttu-id="6280c-161">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6280c-161">Requirements</span></span>

- <span data-ttu-id="6280c-162">Porta di rete cablata con accesso alla rete del cliente</span><span class="sxs-lookup"><span data-stu-id="6280c-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="6280c-163">Dispositivi HoloLens su cui è installato Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="6280c-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="6280c-164">Hub USB-C compatibile con HoloLens</span><span class="sxs-lookup"><span data-stu-id="6280c-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="6280c-165">Intune deve essere configurato e abilitato per il tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="6280c-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="6280c-166">Dispositivo registrato per Autopilot e importato nel tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="6280c-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="6280c-167">Criteri di Intune definiti per il dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6280c-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="6280c-168">Informazioni e certificati per la rete wireless</span><span class="sxs-lookup"><span data-stu-id="6280c-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="6280c-169">Qualsiasi altra impostazione di provisioning necessaria</span><span class="sxs-lookup"><span data-stu-id="6280c-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="6280c-170">Ciò consente ai clienti con requisiti di connettività avanzati di registrare i dispositivi seguendo un approccio scalabile e flessibile</span><span class="sxs-lookup"><span data-stu-id="6280c-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="6280c-171">I prerequisiti aggiuntivi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6280c-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="6280c-172">Abilitare il tenant per l'anteprima di Autopilot</span><span class="sxs-lookup"><span data-stu-id="6280c-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="6280c-173">Creare i criteri di HoloLens per sostituire il pacchetto di provisioning all'interno di Intune.</span><span class="sxs-lookup"><span data-stu-id="6280c-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="6280c-174">Creare i criteri di Intune per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6280c-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="6280c-175">Assegnare i dispositivi al gruppo corretto.</span><span class="sxs-lookup"><span data-stu-id="6280c-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="6280c-176">Processo</span><span class="sxs-lookup"><span data-stu-id="6280c-176">Process</span></span>

1. <span data-ttu-id="6280c-177">Collegare l'hub USB-C e il cavo ethernet al dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6280c-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="6280c-178">Accendere HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6280c-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="6280c-179">Il dispositivo dovrebbe connettersi automaticamente a internet tramite configurazione attraverso l'adattatore ethernet, rilevare la configurazione di Autopilot, e registrarsi automaticamente in Azure AD e Intune</span><span class="sxs-lookup"><span data-stu-id="6280c-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="6280c-180">Il dispositivo applica le configurazioni e gli altri certificati Wi-Fi necessari tramite Intune</span><span class="sxs-lookup"><span data-stu-id="6280c-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="6280c-181">Al termine, il tecnico potrà caricare il portale Intune (Endpoint Manager) e accedere alla pagine delle proprietà del dispositivo passando a **Home -> Dispositivi -> Nome dispositivo -> Hardware**</span><span class="sxs-lookup"><span data-stu-id="6280c-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="6280c-182">L'indirizzo MAC sarà visibile nel portale Intune</span><span class="sxs-lookup"><span data-stu-id="6280c-182">The Wifi MAC address will be visible within the Intune Portal</span></span>

![Indirizzo MAC con Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="6280c-184">Il tecnico aggiunge questo indirizzo MAC come un dispositivo autorizzato.</span><span class="sxs-lookup"><span data-stu-id="6280c-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="6280c-185">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="6280c-185">Benefits</span></span>

<span data-ttu-id="6280c-186">Offre al tecnico un'esperienza di distribuzione &quot;senza intervento manuale&quot;, in cui il dispositivo passa dalla cassetta alla registrazione in AAD e Intune senza che il tecnico debba indossare il dispositivo o interagire manualmente on l'ambiente di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6280c-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in AAD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="6280c-187">Segnalazione degli indirizzi MAC al tecnico</span><span class="sxs-lookup"><span data-stu-id="6280c-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="6280c-188">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6280c-188">Requirements</span></span>

- <span data-ttu-id="6280c-189">Autorizzazione di &quot;Intune Graph Powershell&quot; nel tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="6280c-189">Authorisation of the &quot;Intune Graph Powershell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="6280c-190">Installazione di Intune Graph PowerShell nella macchine dei tecnici.</span><span class="sxs-lookup"><span data-stu-id="6280c-190">Installation of the Intune Graph Powershell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="6280c-191">Accesso in lettura agli elementi &quot;Dispositivi gestiti&quot; di Intune.</span><span class="sxs-lookup"><span data-stu-id="6280c-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="6280c-192">(Operatore Help desk o superiore, oppure un ruolo su misura)</span><span class="sxs-lookup"><span data-stu-id="6280c-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="6280c-193">Al momento non esistono modi &quot;semplici&quot; per attivare un comando i base alla registrazione di un nuovo dispositivo con Intune.</span><span class="sxs-lookup"><span data-stu-id="6280c-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="6280c-194">Pertanto, questo comando fornisce al tecnico un modo semplice per recuperare l'indirizzo MAC senza dovere accedere al portale e recuperalo manualmente.</span><span class="sxs-lookup"><span data-stu-id="6280c-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="6280c-195">In questo modo, verranno restituiti il nome e l'indirizzo MAC di qualsiasi dispositivo HoloLens registrato nei 30 giorni precedenti.</span><span class="sxs-lookup"><span data-stu-id="6280c-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Indirizzo MAC con PowerShell](images/mac-address-powershell.jpg)

### <span data-ttu-id="6280c-197">Process</span><span class="sxs-lookup"><span data-stu-id="6280c-197">Process</span></span>

<span data-ttu-id="6280c-198">Una volta completata la registrazione su Intune, il tecnico esegue lo script sovrastante per recuperare l'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="6280c-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
