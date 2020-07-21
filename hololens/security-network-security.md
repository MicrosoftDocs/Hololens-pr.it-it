---
title: Sicurezza della rete
description: sicurezza della rete
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, rete, sicurezza della rete
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 147401331cb6da732a6fe37e57964d61a10dce99
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883140"
---
# Sicurezza della rete

## Protocolli di rete

L'obsoleto sistema NetBIOS (Network Basic Input/Output System) era ampiamente usato in passato in scenari LAN, spesso per la risoluzione dei nomi in un computer e in cartelle condivise. Nel corso del tempo, infatti, NetBIOS si è rivelato vulnerabile a varie tipologie di attacchi e la sua rilevanza è diminuita in favore di altri protocolli più sicuri. Per rimuovere il problema della vulnerabilità, HoloLens 2 ha eliminato il codice correlato a NetBIOS dal sistema operativo.

I protocolli TLS (Transport Layer Security) si evolvono di continuo. Per stare al passo con i vari exploit di sicurezza che sono stati scoperti in quest'area, il settore informatico è passato a versioni più recenti ed efficaci. A causa del tempo necessario perché tutti gli ambienti server adottino le nuove versioni del protocollo TLS, è possibile implementare un meccanismo di fallback che consenta al client e ai server nelle diverse versioni del protocollo predefinite di comunicare ancora durante il periodo di transizione.

## Connettività sicura 

Windows Defender Firewall offre funzionalità importanti per garantire la connettività dei dispositivi. Con HoloLens 2, il firewall è sempre abilitato e non sono disponibili modi per disabilitarlo a livello di programmazione o tramite l'interfaccia utente.

L'accesso remoto e la privacy della connessione ai client per dispositivi mobili possono essere assicurate tramite la [piattaforma di plug-in VPN UWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041). I provider VPN di terze parti possono creare i loro plug-in usando le API WinRT, che verranno eseguite nel sandbox di AppContainer, eliminando la complessità e le problematiche spesso associate alla scrittura dei driver a livello di sistema.
