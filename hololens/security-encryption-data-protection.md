---
title: Crittografia e protezione dei dati
description: Informazioni sulla crittografia e la protezione dei dati nei dispositivi HoloLens 2, tra cui BitLocker e l'integrazione di Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, crittografia, protezione dei dati, dispositivo BitLocker, BitLocker, bitlocker, crittografia bitlocker, integrazione di azure
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e005f04088127a0e38a4dd978cd63e5d4e5c0ab9
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284107"
---
# Crittografia e protezione dei dati

Cittografia e protezione dei dati protegge i dati quando il dispositivo è stato smarrito o rubato e impedisce l'accesso alle informazioni sensibili da applicazioni non autorizzate.

## Crittografia dispositivo BitLocker

BitLocker è una funzionalità di crittografia di interi volumi per la protezione dell'integrità dei supporti di sola lettura e la protezione della privacy dei supporti scrivibili.  Fin dalla sua creazione ha dimostrato di essere uno scudo efficace contro l'accesso non autorizzato ai dati durante gli attacchi offline. Per impostazione predefinita, HoloLens 2 abilita Crittografia dispositivo Bitlocker per proteggere i dati da qualsiasi accesso fisico non autorizzato al dispositivo. Sempre in evoluzione per soddisfare le esigenze del futuro, Microsoft continua a investire e migliorare questa tecnologia.

BDE è una funzionalità di protezione dei dati che utilizza la crittografia AES-XTS-256 su tutti i volumi nel layout con separazione di stato del dispositivo. BDE fornisce la crittografia a livello di dispositivo in un layout con separazione di stato. Crittografia dispositivo BitLocker è abilitata automaticamente nel sistema operativo e nei volumi di dati fissi e non può essere disattivata, neanche dagli amministratori IT, per garantire la protezione costante del dispositivo.

Le chiavi di crittografia BDE vengono usate per decrittografare in modo trasparente i file binari e i dati necessari per l'avvio del dispositivo. Quando il volume del sistema operativo è sbloccato e un sistema è in fase di avvio, gli altri volumi diventano accessibili usando una versione specifica del volume della protezione di sblocco automatico. Non sono disponibili altri protettori per mantenere la privacy dell'utente e l'unità può essere sbloccata solo sullo stesso dispositivo. L'imposizione della sola lettura sui volumi richiesti viene applicata immediatamente, a partire dal primo avvio.

## Integrazione di Azure 

HoloLens 2 consente ai clienti di integrare i propri dispositivi con i servizi di Azure. Le comunicazioni tra i dispositivi HoloLens 2 e Azure usano il protocollo TLS (Transport Layer Security) per proteggere i dati in transito da e verso il cloud, con autenticazione avanzata, riservatezza dei messaggi e integrità. Tutti i servizi di Azure supportano pienamente TLS 1.2 e tutti i servizi in cui i clienti usano solo TLS 1.2 accettano solo il traffico TLS 1.2. Gli standard di crittografia di Azure per i dati in transito sono illustrati in dettaglio in [Panoramica della crittografia di Azure](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview). Nella documentazione di Azure sono disponibili altre informazioni sulle [pocedure consigliate per la crittografia e la sicurezza dei dati di Azure](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices). 

OneDrive, un esempio di integrazione cloud con HoloLens 2, dispone di una funzionalità di caricamento automatico con cui i file e i documenti possono essere caricati automaticamente nel cloud quando è connesso a internet. L'interruzione della sincronizzazione automatica dei file non può essere disattivata tramite criteri ma può essere configurata direttamente tramite l'esperienza utente. 
