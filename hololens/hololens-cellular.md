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
# <a name="connect-to-cellular-and-5g"></a>Connettersi alla rete cellulare e 5G

HoloLens 2 supporta due modalità di connessione alle reti cellulare e 5G:

- Una rete WiFi ad hoc fornita dal dispositivo cellulare, comunemente definita "Hotspot"
- Supporto limitato per i dispositivi con tethering USB-C

## <a name="hotspot-wifi"></a>Hotspot (WiFi)

La maggior parte delle esigenze di connettività cellulare può essere soddisfatta con un hotspot. HoloLens 2 WiFi supporta 802.11ac, che può fornire i requisiti di larghezza di banda e latenza necessari per gli usi più comuni. WiFi è inoltre privo di cavi ed è compatibile con la maggior parte dei dispositivi cellulari.

### <a name="connecting-to-a-hotspot"></a>Connessione a un hotspot

1. Consulta il manuale del dispositivo per informazioni su come abilitare la modalità hotspot.
1. Abilita la modalità hotspot fornendo un nome per la rete e una password nota.
1. Nelle impostazioni di rete di HoloLens 2, individua la rete WiFi creata nel passaggio 2 e connettiti.

## <a name="usb-c-tethering"></a>Tethering USB-C

Il tethering USB-C fornisce una latenza inferiore per i carichi di lavoro avanzati a cui occorre. Il [Rendering remoto di Azure](https://azure.microsoft.com/services/remote-rendering), ad esempio, può trarre vantaggio dal tethering. Tieni presente che il tethering richiede un cavo tra il dispositivo cellulare e HoloLens ed è supportato da un numero limitato di dispositivi.

### <a name="usb-c-compatibility"></a>Compatibilità USB-C

I dispositivi che si presentano come scheda Ethernet possono essere usati con Windows Holographic versione 2004 e successive.

I dispositivi che non si presentano come scheda Ethernet devono supportare il driver [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Microsoft generico. Per informazioni dettagliate sulla possibilità che il dispositivo supporti il driver RNDIS Microsoft generico, contatta il produttore del dispositivo.

I dispositivi non compatibili con RNDIS o che richiedono l'installazione di un driver o di un'applicazione non sono supportati.

Anche se Microsoft non mantiene un elenco di dispositivi compatibili, esiste una discussione della community sull'argomento [qui](https://aka.ms/HLCommunityCell).

### <a name="connecting-to-a-tethered-device"></a>Connessione a un dispositivo con tethering

1. Consulta il manuale del dispositivo su come abilitare la condivisione dei dati tramite USB. Questa impostazione viene spesso definita "Tethering USB", "Condivisione dati" o "Modem USB".
1. Abilitare la condivisione dei dati tramite USB.
1. Connettere il dispositivo alla porta USB-C di HoloLens.
1. Nelle impostazioni di rete di HoloLens 2, il dispositivo verrà visualizzato automaticamente come connessione Ethernet.
