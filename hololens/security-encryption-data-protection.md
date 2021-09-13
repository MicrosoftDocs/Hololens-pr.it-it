---
title: Crittografia e protezione dei dati
description: Informazioni sulla crittografia e la protezione dei dati nei HoloLens 2, tra cui BitLocker e l'integrazione di Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, crittografia, protezione dei dati, dispositivo BitLocker, BitLocker, bitlocker, crittografia bitlocker, integrazione di Azure,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036242"
---
# <a name="encryption-and-data-protection"></a>Crittografia e protezione dei dati

La crittografia e la protezione dei dati proteggono i dati quando il dispositivo viene smarrito o rubato e impedisce alle applicazioni non autorizzate di accedere a informazioni riservate.

## <a name="bitlocker-device-encryption"></a>Crittografia del dispositivo BitLocker

BitLocker è una funzionalità di crittografia del volume completo per la protezione dell'integrità dei supporti di sola lettura (RO) e la protezione della privacy dei supporti scrivibili.  Fin dall'inizio, è stato uno strumento di protezione efficace contro l'accesso non autorizzato ai dati durante gli attacchi offline. HoloLens 2 abilita Bitlocker Crittografia dispositivo (BDE) per impostazione predefinita per proteggere i dati da qualsiasi accesso fisico non autorizzato al dispositivo. In continua evoluzione per soddisfare le esigenze del futuro, Microsoft continua a investire e migliorare questa tecnologia.

BDE è una funzionalità di protezione dei dati che usa la crittografia AES-XTS-256 in tutti i volumi nel layout separato dallo stato del dispositivo. BDE fornisce la crittografia a livello di dispositivo in un layout separato dallo stato. BitLocker Crittografia dispositivo viene abilitato automaticamente nel sistema operativo e nei volumi di dati fissi e non può essere disattivato, anche dagli amministratori IT, in modo che il dispositivo sia sempre protetto.

Le chiavi di crittografia BDE vengono quindi usate per decrittografare in modo trasparente i file binari e i dati necessari per avviare il dispositivo. Quando il volume del sistema operativo viene sbloccato e un sistema viene avviato, gli altri volumi diventano accessibili usando una versione specifica del volume della protezione per lo sblocco automatico. Non sono disponibili altre protezione per mantenere la privacy dell'utente e l'unità può essere sbloccata solo sullo stesso dispositivo. L'imposizione di sola lettura (RO) sui volumi necessari viene applicata e applicata immediatamente, a partire dal primo avvio. La chiave di ripristino di BitLocker non è necessaria nel ciclo HoloLens 2 vita.

## <a name="azure-integration"></a>Integrazione con Azure 

HoloLens 2 consente ai clienti di integrare i propri dispositivi con i servizi di Azure. Le comunicazioni tra HoloLens 2 e Azure usano il protocollo TLS (Transport Layer Security) per proteggere i dati in viaggio tra se stesso e i servizi cloud che offrono autenticazione avanzata, privacy dei messaggi e integrità. Tutti i servizi di Azure supportano completamente TLS 1.2 e tutti i servizi in cui i clienti usano solo TLS 1.2 accettano solo traffico TLS 1.2. Gli standard di crittografia di Azure per i dati in transito sono dettagliati in Panoramica [della crittografia di Azure.](/azure/security/fundamentals/encryption-overview) Per altre informazioni sulle procedure consigliate per la sicurezza e la crittografia dei dati di Azure, vedere [la documentazione di Azure.](/azure/security/fundamentals/data-encryption-best-practices) 

OneDrive, un esempio di integrazione cloud con HoloLens 2, include una funzionalità di caricamento automatico in cui i file e i documenti possono essere caricati automaticamente nel cloud quando si è connessi a Internet. La sospensione della sincronizzazione automatica dei file non può essere disattivata tramite criteri, ma è configurabile direttamente tramite l'esperienza utente. 
