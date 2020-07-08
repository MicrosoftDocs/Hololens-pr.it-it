---
title: Scenari di distribuzione di infrastrutture comuni
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
keywords: HoloLens
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857891"
---
# Scenari di distribuzione di infrastrutture comuni
Queste informazioni seguenti forniscono una panoramica dell'architettura di alto livello per tre scenari comuni durante la distribuzione e la gestione dei dispositivi Microsoft HoloLens 2 all'interno dell'organizzazione.

## Scenari

Il diagramma seguente rappresenta tre scenari tipici per le distribuzioni di HoloLens 2. 
![scenari](images/scenarios.jpg)

### Scenario A

HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale. Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN. Si tratta di una distribuzione molto simile ai dispositivi mobili gestiti all'interno di una società.
 * Configurazioni comuni di base
   * Le reti Wi-Fi sono in genere completamente aperte a Internet e ai servizi cloud.
   * Join di Azure AD con registrazione automatica MDM--MDM (Intune) Managed
   * Accesso degli utenti con il proprio account aziendale (AAD) 
     * Singoli o più utenti per dispositivo supportati
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a specifici casi di utilizzo, da completamente aperti al chiosco di app singole.
   * Una o più applicazioni vengono distribuite tramite MDM

* Sfide comuni
   * Determinazione delle configurazioni MDM da applicare a HoloLens 2 in base ai requisiti dello scenario.

### Scenario B

HoloLens 2 è distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne. I servizi Internet e cloud possono essere limitati. Si tratta di una distribuzione tipica per la maggior parte dei PC Windows 10.
 * Configurazioni comuni di base
   * La rete Wi-Fi è una rete aziendale interna con accesso a risorse interne e accesso limitato a Internet o ai servizi cloud.
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

### Scenario C

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
