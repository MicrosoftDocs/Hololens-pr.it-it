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
# <a name="connect-to-cellular-and-5g"></a>Connessione a Cellulare e 5G

HoloLens 2 supporta due metodi per la connessione a reti cellulare e 5G:

- Una rete Wi-Fi ad hoc fornita dal dispositivo cellulare, comunemente definita "hotspot"
- Supporto limitato per i dispositivi con tethering USB-C

## <a name="hotspot-wifi"></a>Hotspot (Wi-Fi)

La maggior parte delle esigenze di connettività cellulare può essere soddisfatta con un hotspot. HoloLens 2 Il Wi-Fi supporta 802.11ac, che può fornire i requisiti di larghezza di banda e latenza necessari per i casi d'uso più comuni. Il Wi-Fi è anche privo di cavi e offre compatibilità con il maggior numero di dispositivi cellulari.

### <a name="connecting-to-a-hotspot"></a>Connessione a un hotspot

1. Consultare il manuale del dispositivo per informazioni su come abilitare la modalità hotspot.
1. Abilitare la modalità hotspot, fornendo un nome per la rete e una password nota.
1. Nelle HoloLens 2 Rete individuare la rete Wi-Fi creata nel passaggio 2 e aggiungerla.

## <a name="usb-c-tethering"></a>USB-C Tethering

Il tethering USB-C può fornire una latenza inferiore per i carichi di lavoro avanzati che ne hanno bisogno. [Rendering remoto di Azure,](https://azure.microsoft.com/services/remote-rendering)ad esempio, può trarre vantaggio dal tethering. Si noti che il tethering richiede un cavo tra il HoloLens cellulare e il tethering è supportato da un numero limitato di dispositivi.

### <a name="usb-c-compatibility"></a>Compatibilità USB-C

Un numero limitato di dispositivi che si presentano come adattatore ethernet può essere usato con Windows Holographic versione 2004 e successive.

I dispositivi che non si presentano come scheda Ethernet devono supportare il driver [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Microsoft generico. Tuttavia, solo un numero limitato di tali dispositivi è compatibile con HoloLens 2. Per informazioni dettagliate sul supporto del driver RNDIS Microsoft generico, consultare il produttore del dispositivo.

I dispositivi non compatibili con RNDIS o che richiedono l'installazione di un driver o di un'applicazione non sono supportati.

Anche se Microsoft non gestisce un elenco di dispositivi compatibili, è disponibile una discussione della community sull'argomento [qui](https://aka.ms/HLCommunityCell).

### <a name="connecting-to-a-tethered-device"></a>Connessione a un dispositivo con tethering

1. Consultare il manuale del dispositivo per informazioni su come abilitare la condivisione dei dati tramite USB. Questa impostazione viene spesso definita "Tethering USB", "Condivisione dati" o "Modem USB".
1. Abilitare la condivisione dei dati tramite USB.
1. Connessione il dispositivo alla HoloLens USB-C.
1. Nelle HoloLens 2 di rete il dispositivo verrà automaticamente visualizzato come connessione Ethernet.
