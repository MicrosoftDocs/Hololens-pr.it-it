---
title: Architettura di sicurezza di HoloLens
description: Architettura di sicurezza
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, hololens 2, sicurezza hololens2, panoramica della sicurezza, architettura di sicurezza, architettura, architettura hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253253"
---
# <span data-ttu-id="8bc6e-104">Panoramica e architettura di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8bc6e-104">Security overview and architecture</span></span>

<span data-ttu-id="8bc6e-105">L'architettura di sicurezza di HoloLens 2 è stata progettata da zero per evitare i problemi di sicurezza legacy e ridurre al minimo la superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="8bc6e-106">Questa architettura innovativa offre spazi di archiviazione sicura ed elementi di sicurezza avanzati, con meccanismi in grado di proteggere i sistemi operativi da potenziali minacce e vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="8bc6e-107">HoloLens 2 unisce hardware, software, rete e servizi per garantire la sicurezza end-to-end, fornendo all'utente un'esperienza ottimale.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="8bc6e-108">Con HoloLens 2, la maggior parte delle funzionalità di sicurezza è attivata automaticamente, riducendo al minimo lo sforzo richiesto per impostare e configurare correttamente il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="8bc6e-109">L'architettura di Windows HoloLens 2 e del sistema operativo offre le seguenti funzionalità di sicurezza innovative:</span><span class="sxs-lookup"><span data-stu-id="8bc6e-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="8bc6e-110">**Separazione dello stato e isolamento**: questa nuova architettura impedisce di modificare le parti fondamentali del sistema operativo HoloLens 2, ad esempio quelle necessarie per l'avvio del sistema operativo core in uno stato attendibile.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="8bc6e-111">La tecnologia di isolamento viene usata per confinare le app non attendibili all'interno di un'area sandbox, assicurando che non possano influire sulla sicurezza del sistema.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="8bc6e-112">L'intero sistema operativo è segmentato in sezioni sicure, in cui ogni sezione è protetta da una combinazione di tecnologie di sicurezza diverse.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="8bc6e-113">**Protezione dei dati**: se il dispositivo di un utente viene smarrito o rubato, HoloLens 2 impedisce alle applicazioni non autorizzate di leggere le informazioni sensibili grazie all’uso della crittografia dei dati BitLocker.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="8bc6e-114">**Sistema operativo senza password**: i sistemi operativi meno recenti con autenticazione basata su password potevano inavvertitamente esporre gli utenti a minacce di phishing e spesso erano responsabili della compromissione degli account.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="8bc6e-115">Windows Holographic for Business elimina l'uso delle password per l'accesso MSA e Azure AD e rafforza la protezione dell'identità degli utenti con l'accesso Windows Hello™ e FIDO2.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="8bc6e-116">Per disporre del supporto FIDO2, il dispositivo deve eseguire build 19041 o successive.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="8bc6e-117">**Sicurezza della rete**: HoloLens 2 offre all'utente una sicurezza di rete maggiore grazie a protocolli migliorati e impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="8bc6e-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
