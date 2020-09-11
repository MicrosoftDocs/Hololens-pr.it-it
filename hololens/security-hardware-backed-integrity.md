---
title: Integrità supportata dall'hardware e attestazione runtime
description: Integrità supportata dall'hardware e attestazione runtime
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, integrità supportata dall'hardware, attestazione runtime, UEFI, avvio protetto UEFI, avvio sicuro, TPM, protezione dalle minacce, garanzia anti-persistenza di Windows, integrità del codice, protezione del codice
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b3986d7310650c2fac20204488ae5f882754deab
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009474"
---
# Integrità supportata dall'hardware e attestazione runtime

L'integrità supportata dall'hardware e attestazione runtime protegge dalle minacce che hanno avuto origine prima dell'avvio di un sistema operativo, durante il runtime, quando il dispositivo usa l'hardware e i servizi di attestazione remota per garantire l'integrità in fase di avvio e per tutta la durata del runtime.

## Avvio protetto UEFI

HoloLens 2 applica sempre l'avvio protetto UEFI (Unified Extensible Firmware Interface) e UEFI avvia solo Windows Holographic for Business.
Avvio protetto garantisce il controllo dell'integrità nell'intera catena di avvio e che Windows venga avviato sempre con i criteri di sicurezza corretti applicati. Per altre informazioni sull'avvio protetto, vedere qui.

## TPM

Trusted Platform Module (TPM) è un chip specializzato su un dispositivo endpoint. HoloLens 2 usa TPM 2.0, che fornisce l'isolamento delle chiavi imposto dall'hardware.

## Protezione dalle minacce di accesso persistente

L'obiettivo della maggior parte dei cyberattacchi consiste nel mantenere un accesso persistente in un dispositivo. Dal punto di vista del crimine informatico, la persistenza consente a un dispositivo Windows compromesso di partecipare a una botnet, vendere l'accesso al dispositivo o ad altri utenti malintenzionati o permettere il furto ripetuto di dati. Nel mondo degli attacchi mirati, la persistenza è fondamentale per la riuscita di un cyberattacco, sia a un dispositivo che, più comunemente, a un'intera rete.  

Gli attacchi mirati, infatti, sono considerati "minacce persistenti avanzate", data la loro esigenza strategica di mantenere l'accesso al dispositivo o alla rete target. Per questo, Windows Holographic for Business ritiene che la difesa contro la persistenza sia assolutamente cruciale e usa la tecnologia anti-persistenza per offrire una garanzia di sicurezza ai clienti.

### Avvio protetto 

HoloLens 2 applica sempre l'avvio protetto UEFI (Unified Extensible Firmware Interface) su tutti gli stati del sistema operativo core. UEFI avvia solo le piattaforme attendibili Microsoft, garantendo il controllo dell'integrità nell'intera catena di avvio e che Windows venga avviato sempre con i criteri di sicurezza corretti applicati. HoloLens 2 non consente la disattivazione dell'avvio protetto, né consente caricatori di avvio di terze parti.

> [!Tip]
> Per altre informazioni, vedere [Avvio protetto](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### Garanzia anti-persistenza di Windows

La tecnologia anti-persistenza di HoloLens 2 garantisce agli utenti che, anche nella rara eventualità di una compromissione in fase di runtime del sistema, ad esempio un exploit remoto, tale evento verrebbe mitigato con la rimozione di tutto il codice dannoso dal sistema semplicemente spegnendo il dispositivo. Per rafforzare ulteriormente la sua anti-persistenza, in HoloLens 2 è stata aggiunta una protezione avanzata dell'integrità e sono state applicate protezioni di sola lettura.

La persistenza dei dati del sistema operativo sotto forma di dati è comunque possibile, a meno che l'utente non esegua la reimpostazione rapida del dispositivo, che cancella il contenuto di tutte le partizioni modificabili. Anche se la persistenza nelle partizioni non modificabili è resa molto più difficile, l'utente deve eseguire la reimpostazione rapida di HoloLens 2 per rimuovere ogni possibile persistenza delle minacce dalle parti modificabili.

## Protezione dell'integrità del codice 

L'integrità del codice è una proprietà di sicurezza chiave di un sistema operativo moderno. L'applicazione dell'integrità del codice consente di prendere decisioni valide in fatto di sicurezza perché garantisce la trasparenza della provenienza del codice sia per l'utente che per il sistema operativo. L'integrità del codice completa deve andare oltre la firma dell'immagine binaria e includere l'applicazione runtime, come l'integrità del flussi di controllo e le restrizioni del codice dinamico. È fondamentale per impedire più classi di attacchi, tra cui il malware basato su social engineering come il ransomware, gli exploit di esecuzione di codice remoto e varie altre classi di attacchi.
