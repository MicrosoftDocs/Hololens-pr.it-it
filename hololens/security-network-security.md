---
title: Sicurezza di rete
description: sicurezza di rete
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, rete, sicurezza di rete
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c5ac42ee272becfd404a1f00931fa05237e31993288fee16d79d73f79aade646
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665387"
---
# <a name="network-security"></a>Sicurezza di rete

## <a name="network-protocols"></a>Protocolli di rete

Il NetBIOS obsoleto (Network Basic Input/Output System) è stato ampiamente usato in passato negli scenari LAN, spesso per fornire la risoluzione dei nomi a un computer e a cartelle condivise. Nel corso del tempo, Tuttavia, NetBIOS si è dimostrato vulnerabile a più attacchi e la sua pertinenza è diminuita a favore di altri protocolli più sicuri. Per rimuovere questo problema di vulnerabilità, HoloLens 2 ha eliminato il codice correlato a NetBIOS dal sistema operativo.

I protocolli TLS (Transport Layer Security) sono in continua evoluzione. Per restare al passo con i vari exploit di sicurezza che sono stati scoperti in quest'area, il settore informatico è diventato una versione più recente e più efficace. A causa del tempo necessario a tutte le distribuzioni server per adottare le nuove versioni del protocollo TLS, è possibile implementazione di un meccanismo di fallback che consente al client e ai server in versioni del protocollo predefinite diverse di essere ancora in grado di comunicare durante il periodo di transizione.

## <a name="secure-connectivity"></a>Proteggere la connettività 

Il firewall Windows Defender offre funzionalità critiche per proteggere la connettività dei dispositivi. Con HoloLens 2, il firewall è sempre abilitato e non è possibile disabilitarlo a livello di codice o tramite l'interfaccia utente.

L'accesso remoto e la privacy della connessione per i client mobili possono essere garantiti tramite la [piattaforma plug-in VPN UWP.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041) I provider VPN di terze parti possono creare i propri plug-in usando le API WinRT che verranno eseguite all'interno della sandbox AppContainer, eliminando la complessità e i problemi spesso associati alla scrittura di driver a livello di sistema.
