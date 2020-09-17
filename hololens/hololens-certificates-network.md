---
title: Preparare certificati e profili di rete per HoloLens 2
description: Come configurare e usare certificati per la rete nei dispositivi HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 460b6f42de7413e77eaec041a5ab6141ed959cf4
ms.sourcegitcommit: 9944fd2040fc1267ace1da1bd62ef36b68c7f318
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015523"
---
# <span data-ttu-id="b914d-103">Preparare certificati e profili di rete per HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b914d-103">Prepare certificates and network profiles for HoloLens 2</span></span>

<span data-ttu-id="b914d-104">L'autenticazione basata su certificato è un requisito comune per i clienti che usano HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b914d-104">Certificate-based authentication is a common requirement for customers using HoloLens 2.</span></span> <span data-ttu-id="b914d-105">Potrebbe essere necessario disporre di certificati per accedere alla rete Wi-Fi, per connettersi a soluzioni VPN o per accedere alle risorse interne dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b914d-105">You might require certificates to access Wi-Fi, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>

<span data-ttu-id="b914d-106">Poiché i dispositivi HoloLens 2 sono in genere collegati a Azure Active Directory (Azure AD) e gestiti da Intune o da un altro provider MDM, sarà necessario distribuire tali certificati con un'infrastruttura SCEP (Simple Certification Protocol) o PKCS (Public Key Cryptography Standard) integrate con la soluzione MDM.</span><span class="sxs-lookup"><span data-stu-id="b914d-106">Because HoloLens 2 devices are typically joined to Azure Active Directory (Azure AD) and managed by Intune or other MDM provider, you will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span>

## <span data-ttu-id="b914d-107">Requisiti dei certificati</span><span class="sxs-lookup"><span data-stu-id="b914d-107">Certificate requirements</span></span>
<span data-ttu-id="b914d-108">I certificati radice sono necessari per distribuire i certificati tramite un'infrastruttura SCEP o PKCS.</span><span class="sxs-lookup"><span data-stu-id="b914d-108">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="b914d-109">Anche altre applicazioni e servizi dell'organizzazione possono richiedere la distribuzione dei certificati radice ai dispositivi di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b914d-109">Other applications and services in your organization might require root certificates to be deployed to your HoloLens 2 devices as well.</span></span> 

## <span data-ttu-id="b914d-110">Requisiti di connettività di rete Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="b914d-110">Wi-Fi connectivity requirements</span></span>
<span data-ttu-id="b914d-111">Per consentire la configurazione automatica di un dispositivo con la configurazione Wi-Fi necessaria per la rete aziendale, è necessario un profilo di configurazione Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b914d-111">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you will need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="b914d-112">È possibile configurare Intune o un altro provider MDM per distribuire questi profili nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b914d-112">You can configure Intune or other MDM provider to deploy these profiles to your devices.</span></span> <span data-ttu-id="b914d-113">Se la sicurezza della rete richiede che i dispositivi facciano parte del dominio locale, potrebbe anche essere necessario valutare l'infrastruttura di rete Wi-Fi per assicurarsi che sia compatibile con i dispositivi di HoloLens 2 (i dispositivi HoloLens 2 sono collegati solo AD Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b914d-113">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with HoloLens 2 devices (HoloLens 2 devices are Azure AD-joined only).</span></span>

## <span data-ttu-id="b914d-114">Distribuire infrastruttura di certificato.</span><span class="sxs-lookup"><span data-stu-id="b914d-114">Deploy certificate infrastructure</span></span>
<span data-ttu-id="b914d-115">Se non è già presente un'infrastruttura SCEP o PKCS, è necessario prepararne una.</span><span class="sxs-lookup"><span data-stu-id="b914d-115">If no SCEP or PKCS infrastructure already exists, you'll need to prepare one.</span></span> <span data-ttu-id="b914d-116">Per supportare l'uso dei certificati SCEP o PKCS per l'autenticazione, Intune richiede l'uso di un [connettore di certificato](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).</span><span class="sxs-lookup"><span data-stu-id="b914d-116">To support the use of SCEP or PKCS certificates for authentication, Intune requires the use of a [certificate connector](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).</span></span>

> [!NOTE]
> <span data-ttu-id="b914d-117">Se si usa SCEP con una CA Microsoft, è necessario configurare anche il [servizio di registrazione dei dispositivi di rete (registrazione dispositivi)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span><span class="sxs-lookup"><span data-stu-id="b914d-117">When you use SCEP with a Microsoft CA, you must also configure the [Network Device Enrollment Service (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span></span>

<span data-ttu-id="b914d-118">Per altre informazioni, vedere [Configurare il profilo di un certificato per i dispositivi in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="b914d-118">For more information, see [Configure a certificate profile for your devices in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)</span></span>

## <span data-ttu-id="b914d-119">Distribuire certificati e profilo Wi-Fi/VPN</span><span class="sxs-lookup"><span data-stu-id="b914d-119">Deploy certificates and Wi-Fi/VPN profile</span></span>
<span data-ttu-id="b914d-120">Per distribuire certificati e profili, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b914d-120">To deploy certificates and profiles, follow these steps:</span></span>
1.  <span data-ttu-id="b914d-121">Creare un profilo per ognuno dei certificati radice e intermedi. vedere [Creare profili di certificati attendibili](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles). Ognuno di questi profili deve contenere una descrizione che includa una data di scadenza nel formato gg/MM/AAAA.</span><span class="sxs-lookup"><span data-stu-id="b914d-121">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> **<span data-ttu-id="b914d-122">I profili di certificato senza data di scadenza non verranno distribuiti.</span><span class="sxs-lookup"><span data-stu-id="b914d-122">Certificate profiles without an expiration date will not be deployed.</span></span>**
1.  <span data-ttu-id="b914d-123">Creare un profilo per ognuno dei certificati SCEP o PKCS. vedere [Creare un profilo di certificato SCEP attendibile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile). Ognuno di questi profili deve contenere una descrizione che includa una data di scadenza nel formato gg/MM/AAAA.</span><span class="sxs-lookup"><span data-stu-id="b914d-123">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> **<span data-ttu-id="b914d-124">I profili di certificato senza data di scadenza non verranno distribuiti.</span><span class="sxs-lookup"><span data-stu-id="b914d-124">Certificate profiles without an expiration date will not be deployed.</span></span>**

> [!NOTE]
> <span data-ttu-id="b914d-125">Quando HoloLens 2 viene considerato come un dispositivo condiviso, più utenti per dispositivo, è consigliabile distribuire i certificati per dispositivi anziché i certificati utente per l'autenticazione Wi-Fi, se possibile.</span><span class="sxs-lookup"><span data-stu-id="b914d-125">As the HoloLens 2 is considered for many to be a shared device, multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible</span></span>

3.  <span data-ttu-id="b914d-126">Creare un profilo per ogni rete Wi-Fi aziendale (vedere [le impostazioni Wi-Fi per Windows 10 e i dispositivi successivi](https://docs.microsoft.com/intune/wi-fi-settings-windows)).</span><span class="sxs-lookup"><span data-stu-id="b914d-126">Create a profile for each corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](https://docs.microsoft.com/intune/wi-fi-settings-windows)).</span></span> 
> [!NOTE]
> <span data-ttu-id="b914d-127">Se possibile, è consigliabile il profilo Wi-Fi[assegnato](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) ai gruppi di dispositivi anziché ai gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="b914d-127">It is recommended that the Wi-Fi profile be [assigned](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) to Device groups rather than User groups where possible.</span></span> 

> [!TIP]
> <span data-ttu-id="b914d-128">È anche possibile esportare un profilo Wi-Fi funzionante da un PC con Windows 10 nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="b914d-128">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="b914d-129">Questa esportazione crea un file XML con tutte le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="b914d-129">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="b914d-130">Quindi, importare il file in Intune e usarlo come profilo Wi-Fi per i dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b914d-130">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="b914d-131">Per i dispositivi Windows, vedere [Esportare e importare le impostazioni di Wi-Fi.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span><span class="sxs-lookup"><span data-stu-id="b914d-131">See [Export and import Wi-Fi settings for Windows devices.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span></span>

4.  <span data-ttu-id="b914d-132">Creare un profilo per ogni VPN aziendale (vedere [Impostazioni dei dispositivi olografici per Windows 10 e Windows per aggiungere connessioni VPN con Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).</span><span class="sxs-lookup"><span data-stu-id="b914d-132">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).</span></span>




