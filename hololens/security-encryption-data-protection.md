---
title: Crittografia e protezione dei dati
description: Informazioni sulla crittografia e sulla protezione dei dati HoloLens 2 dispositivi, tra cui BitLocker e l'integrazione di Azure.
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
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639370"
---
# <a name="encryption-and-data-protection"></a>Crittografia e protezione dei dati

La crittografia e la protezione dei dati proteggono i dati quando il dispositivo viene smarrito o rubato e impedisce ad applicazioni non autorizzate di accedere a informazioni riservate.

## <a name="bitlocker-device-encryption"></a>Crittografia dei dispositivi BitLocker

BitLocker è una funzionalità di crittografia a volume completo per la protezione dell'integrità dei supporti di sola lettura e la protezione della privacy dei supporti scrivibili.  Fin dalla sua creazione, è stato uno strumento efficace contro l'accesso non autorizzato ai dati durante gli attacchi offline. HoloLens 2 abilita Bitlocker Crittografia dispositivo (BDE) per impostazione predefinita per proteggere i dati da qualsiasi accesso fisico non autorizzato al dispositivo. In continua evoluzione per soddisfare le esigenze del futuro, Microsoft continua a investire e migliorare questa tecnologia.

BDE è una funzionalità di protezione dei dati che usa la crittografia AES-XTS-256 in tutti i volumi nel layout separato dallo stato del dispositivo. BDE fornisce la crittografia a livello di dispositivo in un layout separato dallo stato. BitLocker Crittografia dispositivo viene abilitato automaticamente nei volumi di dati fissi e del sistema operativo e non può essere disattivato, neanche dagli amministratori IT, in modo che il dispositivo sia sempre protetto.

Le chiavi di crittografia BDE vengono quindi usate per decrittografare in modo trasparente i file binari e i dati necessari per avviare il dispositivo. Quando il volume del sistema operativo viene sbloccato e un sistema viene avviato, altri volumi diventano accessibili usando una versione specifica del volume della protezione di sblocco automatico. Non sono disponibili altre protezione per mantenere la privacy dell'utente e l'unità può essere sbloccata solo nello stesso dispositivo. L'imposizione ro di sola lettura nei volumi necessari viene applicata e applicata immediatamente, a partire dal primo avvio. La chiave di ripristino di Bitlocker non è necessaria nel ciclo HoloLens 2 vita.

## <a name="azure-integration"></a>Integrazione con Azure 

HoloLens 2 consente ai clienti di integrare i propri dispositivi con i servizi di Azure. Le comunicazioni tra HoloLens 2 e Azure usano il protocollo TLS (Transport Layer Security) per proteggere i dati in viaggio tra se stesso e i servizi cloud che forniscono autenticazione avanzata, privacy dei messaggi e integrità. Tutti i servizi di Azure supportano completamente TLS 1.2 e tutti i servizi in cui i clienti usano solo TLS 1.2 accettano solo il traffico TLS 1.2. Gli standard di crittografia di Azure per i dati in transito sono dettagliati nella panoramica [della crittografia di Azure.](/azure/security/fundamentals/encryption-overview) Per altre informazioni sulle procedure consigliate per la sicurezza e la crittografia dei dati di [Azure,](/azure/security/fundamentals/data-encryption-best-practices)vedere la documentazione di Azure. 

OneDrive, un esempio di integrazione cloud con HoloLens 2, include una funzionalità di caricamento automatico in cui i file e i documenti possono essere caricati automaticamente nel cloud quando sono connessi a Internet. La sospensione della sincronizzazione automatica dei file non può essere disattivata tramite criteri, ma è configurabile direttamente tramite l'esperienza utente. 
