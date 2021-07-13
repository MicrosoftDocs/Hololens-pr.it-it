---
title: Integrità supportata dall'hardware e attestazione di runtime
description: Integrità supportata dall'hardware e attestazione di runtime
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: sicurezza, hololens, integrità basata su hardware, attestazione di runtime, UEFI, avvio protetto UEFI, avvio protetto, TPM, protezione dalle minacce, Windows Anti-Persistence Assurance, integrità del codice, protezione del codice,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639336"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Integrità basata su hardware e attestazione di runtime

L'integrità basata su hardware e l'attestazione di runtime proteggono dalle minacce che hanno origine prima dell'avvio di un sistema operativo, durante il runtime, quando il dispositivo usa hardware e servizi di attestazione remota per garantire che l'integrità sia mantenuta all'avvio e per tutta la durata del runtime.

## <a name="uefi-secure-boot"></a>Avvio protetto UEFI

HoloLens 2 applica sempre l'avvio protetto UEFI (Unified Extensible Firmware Interface) e UEFI viene avviato Windows Holographic for Business.
L'avvio protetto garantisce che l'integrità dell'intera catena di avvio sia verificata e che Windows viene sempre avviato con i criteri di sicurezza corretti applicati. Altre informazioni [sull'avvio protetto.](/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>TPM

Il Trusted Platform Module (TPM) è un chip specializzato in un dispositivo endpoint. HoloLens 2 usa un TPM 2.0, che fornisce l'isolamento delle chiavi applicato dall'hardware. Altre informazioni sui [concetti fondamentali del TPM.](/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Protezione dalle minacce per l'accesso persistenza

L'obiettivo della maggior parte degli attacchi informatici è mantenere l'accesso permanente a un dispositivo. Per la cybercriminazione, il mantenimento di questa persistenza consente a un dispositivo Windows compromesso di aggiungersi a una botnet, vendere l'accesso al dispositivo o ad altri utenti nefarious o di consentire il furto di dati ripetuto. Nel mondo degli attacchi mirati, la persistenza è essenziale per un attacco informatico riuscito, sia in un dispositivo che (più comunemente) in un'intera rete.  

In realtà, gli attacchi mirati sono considerati "minacce persistenti avanzate", a causa della loro necessità strategica di mantenere l'accesso a un dispositivo o a una rete di destinazione. Per questo motivo, Windows Holographic for Business la difesa dalla persistenza è assolutamente fondamentale e usa la tecnologia anti-persistenza per realizzare una promessa di sicurezza dei clienti.

### <a name="secure-boot"></a>Avvio protetto

HoloLens 2 applica l'avvio protetto UEFI (Unified Extensible Firmware Interface) in tutti gli stati principali del sistema operativo. UEFI avvia solo le piattaforme attendibili Microsoft, assicurando che l'intera catena di avvio sia verificata per l'integrità e che Windows si avvia sempre con i criteri di sicurezza corretti applicati. HoloLens 2 avvio protetto non è disattivato, né consente caricatori di avvio di terze parti.

> [!Tip]
> Altre informazioni [sull'avvio protetto.](/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Garanzia di anti-persistenza

HoloLens 2 anti-persistenza garantisce agli utenti che anche nella rara situazione in cui si verificasse una compromissione di runtime del sistema, ad esempio un exploit remoto, tale evento verrebbe mitigato con tutto il codice dannoso rimosso dal sistema semplicemente spegnendo il dispositivo. Per rafforzare ulteriormente l'anti-persistenza, HoloLens 2 ha aggiunto una potente protezione dell'integrità e ha messo in atto protezioni di sola lettura.

La persistenza nei dati del sistema operativo sotto forma di dati è ancora possibile, a meno che l'utente non esegua la reimpostazione del pulsante di comando (PBR) del dispositivo che cancella tutte le partizioni modificabili. Anche se la persistenza nelle partizioni non modificabili è molto più difficile, l'utente deve eseguire il PBR del HoloLens 2 per rimuovere qualsiasi possibile persistenza delle minacce dalle parti modificabili.

## <a name="code-integrity-protection"></a>Protezione dell'integrità del codice

L'integrità del codice è una proprietà di sicurezza chiave di un sistema operativo moderno. L'applicazione di CI consente di prendere decisioni affidabili in fatto di sicurezza, perché garantisce che la provenienza del codice sia trasparente sia per l'utente che per il sistema operativo. L'integrità completa del codice deve estendere la firma di immagini binarie precedenti e includere l'imposizione di runtime, ad esempio l'integrità del flusso di controllo e le restrizioni del codice dinamico. L'integrazione continua è fondamentale per impedire più classi di attacchi, tra cui malware progettato socialmente, ad esempio ransomware, exploit di esecuzione remota del codice e varie altre classi di attacco.
