---
title: Scenari comuni di distribuzione dell'infrastruttura
description: Alcuni scenari di distribuzione comuni basati su infrastrutture comuni diverse
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: e9e91535bb49b5076547e8b9934bdc86808d41fc
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195569"
---
# Panoramica degli scenari di distribuzione delle infrastrutture comuni

Queste informazioni seguenti forniscono una panoramica dell'architettura di alto livello per tre scenari comuni durante la distribuzione e la gestione dei dispositivi Microsoft HoloLens 2 all'interno dell'organizzazione. Spesso come Gestisci i tuoi dispositivi e come l'accesso alle risorse dell'organizzazione sia in gran parte determinato da fattori già esistenti. In base all'infrastruttura esistente invitiamo a esaminare lo stile di gestione dei dispositivi comuni negli scenari seguenti e provare le guide per la distribuzione nello scenario che soddisfa le proprie esigenze.

## Scenari

Il diagramma seguente rappresenta tre scenari tipici per le distribuzioni di HoloLens 2.
![Diagramma scenari](images/scenarios.jpg)

### Scenario A: distribuire ai dispositivi di connessione cloud

HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale. Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN. Si tratta di una distribuzione molto simile ai dispositivi mobili gestiti all'interno di una società.
 * Configurazioni comuni di base
   * Le reti di Wi-Fi sono in genere completamente aperte a Internet e ai servizi cloud.
   * Join di Azure AD con registrazione automatica MDM--MDM (Intune) Managed
   * Accesso degli utenti con il proprio account aziendale (AAD)
     * Singoli o più utenti per dispositivo supportati
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a specifici casi di utilizzo, da completamente aperti al chiosco di app singole.
   * Una o più applicazioni vengono distribuite tramite MDM

* Sfide comuni
   * Determinazione delle configurazioni MDM da applicare a HoloLens 2 in base ai requisiti dello scenario.

Per una guida alla distribuzione simile a questo scenario, vedere la guida relativa a [cloud connected HoloLens 2 con Remote Assist](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guida alla distribuzione-cloud connected HoloLens 2 con assistenza remota](hololens2-cloud-connected-overview.md)

### Scenario B: distribuire all'interno della rete dell'organizzazione

HoloLens 2 è distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne. I servizi Internet e cloud possono essere limitati. Si tratta di una distribuzione tipica per la maggior parte dei PC Windows 10.
 * Configurazioni comuni di base
   * Wi-Fi Network è una rete aziendale interna con accesso a risorse interne e accesso limitato a Internet o ai servizi cloud.
   * Join di Azure AD con registrazione automatica MDM
   * Gestito da MDM (Intune)
   * Accesso degli utenti con il proprio account aziendale (AAD)
     * Singoli o più utenti per dispositivo supportati
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a specifici casi di utilizzo, da completamente aperti al chiosco di app singole.
   * Una o più applicazioni vengono distribuite tramite MDM

 * Sfide comuni
   * HoloLens 2 non supporta i locali AD join o SCCM. Solo Azure AD join con MDM. Molte aziende di oggi distribuiscono ancora Windows 10 PC in questo scenario, come i dispositivi di annunci collegati locali, gestiti da System Center Configuration Manager (SCCM) e potrebbero non avere l'infrastruttura distribuita/configurata per la gestione di dispositivi Windows 10 interni tramite soluzioni MDM basate su cloud.
   * Poiché HoloLens 2 è un dispositivo cloud First, si basa molto sui servizi Internet e cloud connected per l'autenticazione degli utenti, gli aggiornamenti del sistema operativo, la gestione MDM e così via. Quando ci si connette a una rete aziendale, è molto probabile che le regole proxy/firewall debbano essere modificate per consentire l'accesso a HoloLens 2 e alle applicazioni in esecuzione.
   * La connettività Wi-Fi aziendale in genere richiede certificati per autenticare il dispositivo o l'utente alla rete. L'infrastruttura o le impostazioni necessarie per distribuire i certificati in dispositivi Windows 10 tramite MDM può essere difficile da configurare.

### Scenario C: distribuire in un ambiente offline sicuro

HoloLens 2 è distribuito per l'uso principalmente offline senza accesso di rete o Internet. Si tratta di una distribuzione tipica per percorsi altamente sicuri o riservati.
 * Configurazioni comuni di base
   * La connettività Wi-Fi è disabilitata. Ethernet tramite USB può essere abilitato per la connettività LAN, se necessario.
   * Non gestito.
   * Account utente locale per l'accesso al dispositivo.
     * HoloLens 2 supporta solo un account locale.
   * I diversi livelli delle configurazioni di blocco dei dispositivi vengono applicati tramite i pacchetti di provisioning in base a casi di utilizzo specifici. Queste configurazioni sono in genere molto limitate a causa di requisiti di ambiente sicuri.
   * Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning

 * Sfide comuni
   * È disponibile un set limitato di configurazioni tramite il provisioning dei pacchetti
   * I servizi cloud non possono essere sfruttati, quindi limitando le funzionalità di HoloLens 2.
   * Maggiore overhead amministrativo poiché questi dispositivi devono essere impostati, configurati e aggiornati manualmente.

Per una guida alla distribuzione simile a questo scenario, consultare la [Guida alla distribuzione sicura offline](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guida alla distribuzione-offline Secure HoloLens 2](hololens-common-scenarios-offline-secure.md)
