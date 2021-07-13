---
title: Connessione a Cellulare e 5G
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
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635841"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="bb16a-103">Connessione a Cellulare e 5G</span><span class="sxs-lookup"><span data-stu-id="bb16a-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="bb16a-104">HoloLens 2 supporta due metodi per la connessione a reti cellulare e 5G:</span><span class="sxs-lookup"><span data-stu-id="bb16a-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="bb16a-105">Una rete Wi-Fi ad hoc fornita dal dispositivo cellulare, comunemente definita "hotspot"</span><span class="sxs-lookup"><span data-stu-id="bb16a-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="bb16a-106">Supporto limitato per i dispositivi con tethering USB-C</span><span class="sxs-lookup"><span data-stu-id="bb16a-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="bb16a-107">Hotspot (Wi-Fi)</span><span class="sxs-lookup"><span data-stu-id="bb16a-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="bb16a-108">La maggior parte delle esigenze di connettività cellulare può essere soddisfatta con un hotspot.</span><span class="sxs-lookup"><span data-stu-id="bb16a-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="bb16a-109">HoloLens 2 Il Wi-Fi supporta 802.11ac, che può fornire i requisiti di larghezza di banda e latenza necessari per i casi d'uso più comuni.</span><span class="sxs-lookup"><span data-stu-id="bb16a-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="bb16a-110">Il Wi-Fi è anche privo di cavi e offre compatibilità con il maggior numero di dispositivi cellulari.</span><span class="sxs-lookup"><span data-stu-id="bb16a-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="bb16a-111">Connessione a un hotspot</span><span class="sxs-lookup"><span data-stu-id="bb16a-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="bb16a-112">Consultare il manuale del dispositivo per informazioni su come abilitare la modalità hotspot.</span><span class="sxs-lookup"><span data-stu-id="bb16a-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="bb16a-113">Abilitare la modalità hotspot, fornendo un nome per la rete e una password nota.</span><span class="sxs-lookup"><span data-stu-id="bb16a-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="bb16a-114">Nelle HoloLens 2 Rete individuare la rete Wi-Fi creata nel passaggio 2 e aggiungerla.</span><span class="sxs-lookup"><span data-stu-id="bb16a-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="bb16a-115">USB-C Tethering</span><span class="sxs-lookup"><span data-stu-id="bb16a-115">USB-C Tethering</span></span>

<span data-ttu-id="bb16a-116">Il tethering USB-C può fornire una latenza inferiore per i carichi di lavoro avanzati che ne hanno bisogno.</span><span class="sxs-lookup"><span data-stu-id="bb16a-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="bb16a-117">[Rendering remoto di Azure,](https://azure.microsoft.com/services/remote-rendering)ad esempio, può trarre vantaggio dal tethering.</span><span class="sxs-lookup"><span data-stu-id="bb16a-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="bb16a-118">Si noti che il tethering richiede un cavo tra il HoloLens cellulare e il tethering è supportato da un numero limitato di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bb16a-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="bb16a-119">Compatibilità USB-C</span><span class="sxs-lookup"><span data-stu-id="bb16a-119">USB-C compatibility</span></span>

<span data-ttu-id="bb16a-120">Un numero limitato di dispositivi che si presentano come adattatore ethernet può essere usato con Windows Holographic versione 2004 e successive.</span><span class="sxs-lookup"><span data-stu-id="bb16a-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="bb16a-121">I dispositivi che non si presentano come scheda Ethernet devono supportare il driver [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Microsoft generico.</span><span class="sxs-lookup"><span data-stu-id="bb16a-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="bb16a-122">Tuttavia, solo un numero limitato di tali dispositivi è compatibile con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bb16a-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="bb16a-123">Per informazioni dettagliate sul supporto del driver RNDIS Microsoft generico, consultare il produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bb16a-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="bb16a-124">I dispositivi non compatibili con RNDIS o che richiedono l'installazione di un driver o di un'applicazione non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="bb16a-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="bb16a-125">Anche se Microsoft non gestisce un elenco di dispositivi compatibili, è disponibile una discussione della community sull'argomento [qui](https://aka.ms/HLCommunityCell).</span><span class="sxs-lookup"><span data-stu-id="bb16a-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="bb16a-126">Connessione a un dispositivo con tethering</span><span class="sxs-lookup"><span data-stu-id="bb16a-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="bb16a-127">Consultare il manuale del dispositivo per informazioni su come abilitare la condivisione dei dati tramite USB.</span><span class="sxs-lookup"><span data-stu-id="bb16a-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="bb16a-128">Questa impostazione viene spesso definita "Tethering USB", "Condivisione dati" o "Modem USB".</span><span class="sxs-lookup"><span data-stu-id="bb16a-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="bb16a-129">Abilitare la condivisione dei dati tramite USB.</span><span class="sxs-lookup"><span data-stu-id="bb16a-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="bb16a-130">Connessione il dispositivo alla HoloLens USB-C.</span><span class="sxs-lookup"><span data-stu-id="bb16a-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="bb16a-131">Nelle HoloLens 2 di rete il dispositivo verrà automaticamente visualizzato come connessione Ethernet.</span><span class="sxs-lookup"><span data-stu-id="bb16a-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
