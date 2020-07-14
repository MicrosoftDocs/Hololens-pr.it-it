---
title: Architettura di sicurezza di HoloLens
description: Architettura di sicurezza
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, hololens 2, sicurezza hololens2, panoramica della sicurezza, architettura di sicurezza, architettura, architettura hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8045f534926e0719bd2f8e448809b5a2965346c4
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865796"
---
# Panoramica e architettura di sicurezza

L'architettura di sicurezza di HoloLens 2 è stata pensata e progettata da zero in modo da evitare i problemi di sicurezza legacy, riducendo al minimo la superficie di attacco. Questa nuova architettura innovativa offre posizioni di archiviazione sicura ed elementi di sicurezza avanzati, con meccanismi in grado di proteggere i sistemi operativi da potenziali minacce e vulnerabilità.

HoloLens 2 unisce hardware, software, rete e servizi per garantire la sicurezza end-to-end, fornendo all'utente un'esperienza ottimale. Con HoloLens 2, la maggior parte delle funzionalità di sicurezza è attivata automaticamente, riducendo al minimo lo sforzo richiesto per impostare e configurare correttamente il sistema operativo.

L'architettura di Windows HoloLens 2 e del sistema operativo offre le seguenti funzionalità di sicurezza innovative:

  * **Isolamento e separazione di stato**: questa nuova architettura impedisce la modifica delle parti fondamentali del sistema operativo HoloLens 2, ad esempio quelle necessarie per l'avvio del sistema operativo core in uno stato attendibile. La tecnologia di isolamento viene usata per confinare le app non attendibili all'interno di un'area sandbox, assicurando che non possano influire sulla sicurezza del sistema. L'intero sistema operativo è segmentato in sezioni sicure, in cui ogni sezione è protetta da una combinazione di tecnologie di sicurezza diverse.
  
  * **Protezione dei dati**: se il dispositivo di un utente viene smarrito o rubato, HoloLens 2 impedisce alle applicazioni non autorizzate di leggere le informazioni sensibili, affidandosi alla crittografia dei dati BitLocker. 
  
  * **Sistema operativo senza password**: i sistemi operativi meno recenti basati su password potevano inavvertitamente esporre gli utenti a minacce di phishing e spesso erano responsabili degli account compromessi. Windows Holographic for Business elimina l'uso delle password per l'accesso MSA e AAD e rafforza la protezione dell'identità dell'utente con l'accesso Windows Hello™ e FIDO2. 
  
    > [!NOTE]
    > Per avere il supporto FIDO2, è necessario che il dispositivo disponga della build 19041 o successive. 

  * **Sicurezza della rete**: HoloLens 2 offre all'utente una sicurezza di rete maggiore grazie a protocolli migliorati e impostazioni predefinite.
