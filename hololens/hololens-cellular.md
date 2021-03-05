---
title: Connettersi alla rete cellulare e 5G
description: Connessione alle reti cellulari dai dispositivi HoloLens di realtà mista.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385643"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="4da5e-103">Connettersi alla rete cellulare e 5G</span><span class="sxs-lookup"><span data-stu-id="4da5e-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="4da5e-104">HoloLens 2 supporta due modalità di connessione alle reti cellulare e 5G:</span><span class="sxs-lookup"><span data-stu-id="4da5e-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="4da5e-105">Una rete WiFi ad hoc fornita dal dispositivo cellulare, comunemente definita "Hotspot"</span><span class="sxs-lookup"><span data-stu-id="4da5e-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="4da5e-106">Supporto limitato per i dispositivi con tethering USB-C</span><span class="sxs-lookup"><span data-stu-id="4da5e-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="4da5e-107">Hotspot (WiFi)</span><span class="sxs-lookup"><span data-stu-id="4da5e-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="4da5e-108">La maggior parte delle esigenze di connettività cellulare può essere soddisfatta con un hotspot.</span><span class="sxs-lookup"><span data-stu-id="4da5e-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="4da5e-109">HoloLens 2 WiFi supporta 802.11ac, che può fornire i requisiti di larghezza di banda e latenza necessari per gli usi più comuni.</span><span class="sxs-lookup"><span data-stu-id="4da5e-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="4da5e-110">WiFi è inoltre privo di cavi ed è compatibile con la maggior parte dei dispositivi cellulari.</span><span class="sxs-lookup"><span data-stu-id="4da5e-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="4da5e-111">Connessione a un hotspot</span><span class="sxs-lookup"><span data-stu-id="4da5e-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="4da5e-112">Consulta il manuale del dispositivo per informazioni su come abilitare la modalità hotspot.</span><span class="sxs-lookup"><span data-stu-id="4da5e-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="4da5e-113">Abilita la modalità hotspot fornendo un nome per la rete e una password nota.</span><span class="sxs-lookup"><span data-stu-id="4da5e-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="4da5e-114">Nelle impostazioni di rete di HoloLens 2, individua la rete WiFi creata nel passaggio 2 e connettiti.</span><span class="sxs-lookup"><span data-stu-id="4da5e-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="4da5e-115">Tethering USB-C</span><span class="sxs-lookup"><span data-stu-id="4da5e-115">USB-C Tethering</span></span>

<span data-ttu-id="4da5e-116">Il tethering USB-C fornisce una latenza inferiore per i carichi di lavoro avanzati a cui occorre.</span><span class="sxs-lookup"><span data-stu-id="4da5e-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="4da5e-117">Il [Rendering remoto di Azure](https://azure.microsoft.com/services/remote-rendering), ad esempio, può trarre vantaggio dal tethering.</span><span class="sxs-lookup"><span data-stu-id="4da5e-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="4da5e-118">Tieni presente che il tethering richiede un cavo tra il dispositivo cellulare e HoloLens ed è supportato da un numero limitato di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4da5e-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="4da5e-119">Compatibilità USB-C</span><span class="sxs-lookup"><span data-stu-id="4da5e-119">USB-C compatibility</span></span>

<span data-ttu-id="4da5e-120">I dispositivi che si presentano come scheda Ethernet possono essere usati con Windows Holographic versione 2004 e successive.</span><span class="sxs-lookup"><span data-stu-id="4da5e-120">Devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="4da5e-121">I dispositivi che non si presentano come scheda Ethernet devono supportare il driver [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Microsoft generico.</span><span class="sxs-lookup"><span data-stu-id="4da5e-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="4da5e-122">Per informazioni dettagliate sulla possibilità che il dispositivo supporti il driver RNDIS Microsoft generico, contatta il produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4da5e-122">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="4da5e-123">I dispositivi non compatibili con RNDIS o che richiedono l'installazione di un driver o di un'applicazione non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="4da5e-123">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="4da5e-124">Anche se Microsoft non mantiene un elenco di dispositivi compatibili, esiste una discussione della community sull'argomento [qui](https://aka.ms/HLCommunityCell).</span><span class="sxs-lookup"><span data-stu-id="4da5e-124">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="4da5e-125">Connessione a un dispositivo con tethering</span><span class="sxs-lookup"><span data-stu-id="4da5e-125">Connecting to a tethered device</span></span>

1. <span data-ttu-id="4da5e-126">Consulta il manuale del dispositivo su come abilitare la condivisione dei dati tramite USB.</span><span class="sxs-lookup"><span data-stu-id="4da5e-126">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="4da5e-127">Questa impostazione viene spesso definita "Tethering USB", "Condivisione dati" o "Modem USB".</span><span class="sxs-lookup"><span data-stu-id="4da5e-127">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="4da5e-128">Abilitare la condivisione dei dati tramite USB.</span><span class="sxs-lookup"><span data-stu-id="4da5e-128">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="4da5e-129">Connettere il dispositivo alla porta USB-C di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4da5e-129">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="4da5e-130">Nelle impostazioni di rete di HoloLens 2, il dispositivo verrà visualizzato automaticamente come connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="4da5e-130">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
