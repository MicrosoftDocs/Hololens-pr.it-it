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
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036236"
---
# <a name="network-security"></a>Sicurezza di rete

## <a name="network-protocols"></a>Protocolli di rete

Il NetBIOS obsoleto (Network Basic Input/Output System) è stato ampiamente usato in passato negli scenari LAN, spesso per fornire la risoluzione dei nomi a un computer e a cartelle condivise. Ma nel corso del tempo, NetBIOS si è dimostrato vulnerabile a più attacchi e la sua pertinenza è diminuita a favore di altri protocolli più sicuri. Per rimuovere questo problema di vulnerabilità, HoloLens 2 ha eliminato il codice correlato a NetBIOS dal sistema operativo.

I protocolli TLS (Transport Layer Security) sono in continua evoluzione. Per tenere il passo con i vari exploit di sicurezza scoperti in questa area, il settore informatico è diventato versioni più recenti ed efficaci. A causa del tempo necessario per tutte le distribuzioni del server per adottare le nuove versioni del protocollo TLS, è possibile implementata un meccanismo di fallback che consente al client e ai server in versioni del protocollo predefinite diverse di poter comunicare ancora durante il periodo di transizione.

## <a name="secure-connectivity"></a>Proteggere la connettività 

Il Windows Defender firewall offre funzionalità critiche per proteggere la connettività dei dispositivi. Con HoloLens 2, il firewall è sempre abilitato e non è possibile disabilitarlo a livello di codice o tramite l'interfaccia utente.

L'accesso remoto e la privacy delle connessioni per i client mobili possono essere garantiti tramite la piattaforma [plug-in VPN UWP](/uwp/api/Windows.Networking.Vpn?view=winrt-19041). I provider VPN di terze parti possono creare plug-in personalizzati usando API WinRT che verranno eseguite all'interno della sandbox AppContainer, eliminando la complessità e i problemi spesso associati alla scrittura di driver a livello di sistema.
