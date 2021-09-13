---
title: HoloLens di sicurezza
description: Architettura di sicurezza
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036245"
---
# <a name="security-overview-and-architecture"></a>Panoramica e architettura della sicurezza

L HoloLens 2 di sicurezza è stata progettata e progettata da zero per essere libera da problemi di sicurezza legacy, creando al tempo stesso una superficie di attacco ridotta al minimo. Questa nuova architettura innovative offre posizioni di archiviazione sicure ed elementi di sicurezza avanzati, con meccanismi in grado di schermare i sistemi operativi da potenziali minacce e vulnerabilità.

HoloLens 2 combina hardware, software, rete e servizi per garantire la sicurezza end-to-end, offrendo all'utente un'esperienza ottimale. Con HoloLens 2, la maggior parte delle funzionalità di sicurezza viene ora attivata automaticamente, riducendo al minimo il lavoro necessario per configurare correttamente il sistema operativo.

Windows HoloLens 2 e del sistema operativo offre queste funzionalità di sicurezza innovative:

  * **Separazione e** isolamento dello stato: questa nuova architettura protegge le parti critiche del sistema operativo HoloLens 2 dalle modifiche, ad esempio quelle necessarie per l'avvio del sistema operativo di base in uno stato attendibile. La tecnologia di isolamento viene usata per limitare le app non attendibili in un'area sandbox, assicurandosi che non influisca sulla sicurezza del sistema. L'intero sistema operativo è segmentato in sezioni sicure, con ogni sezione schermata da una combinazione di tecnologie di sicurezza diverse.
  
  * **Protezione dei dati:** se il dispositivo di un utente viene smarrito o rubato, HoloLens 2 impedisce alle applicazioni non autorizzate di leggere informazioni riservate basandosi sulla crittografia BitLocker dei dati. 
  
  * **Sistema operativo senza** password: i sistemi operativi meno recenti basati su password potrebbero inavvertitamente esporre gli utenti a minacce di phishing e spesso erano responsabili di account compromessi. Windows Holographic for Business l'uso delle password per l'account del servizio microsoft e l'accesso Azure AD e rafforzare la protezione delle identità utente con Windows Hello™ e l'accesso FIDO2. 
  
    > [!NOTE]
    > Per supportare FIDO2, il dispositivo deve essere in build 19041 o successiva. 

  * **Sicurezza di rete:** HoloLens 2 offre all'utente una maggiore sicurezza di rete tramite protocolli migliorati e impostazioni predefinite.
