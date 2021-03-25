---
title: Scenari comuni di distribuzione dell'infrastruttura
description: Informazioni su alcuni degli scenari di distribuzione più comuni basati su diverse distribuzioni dell'infrastruttura per la realtà mista.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448494"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Panoramica degli scenari comuni di distribuzione dell'infrastruttura

Queste informazioni seguenti forniscono una panoramica dell'architettura di alto livello per tre scenari comuni durante la distribuzione e la gestione dei dispositivi Microsoft HoloLens 2 all'interno dell'azienda. Spesso la modalità di gestione dei dispositivi e l'accesso alle risorse dell'organizzazione dipende in larga parte da fattori già in atto. In base all'infrastruttura esistente, ti invitiamo a esaminare lo stile di gestione dei dispositivi comune negli scenari seguenti e provare le nostre guide per la distribuzione nello scenario in base alle tue esigenze.

## <a name="scenarios"></a>Scenari

Il diagramma seguente rappresenta tre scenari tipici per le distribuzioni di HoloLens 2.
![Diagramma degli scenari](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>Scenario A: Distribuire ai dispositivi di connessione cloud

HoloLens 2 viene distribuito per l'utilizzo principalmente in ambienti esterni a una rete aziendale. Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN. Questa distribuzione è simile ai dispositivi mobili gestiti all'interno di un'azienda.
 * Configurazioni comuni di base
   * Wi-Fi di rete sono in genere completamente aperte a Internet e ai servizi cloud.
   * Aggiunta ad Azure AD con registrazione automatica di Gestione dispositivi mobili (MDM) -MDM (Intune) Gestito
   * Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
     * Supporto di uno o più utenti per dispositivo
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi di uso specifici, da Completamente aperto a Chiosco app singola.
   * Una o più applicazioni vengono distribuite tramite MDM

* Sfide comuni
   * Determinazione delle configurazioni MDM da applicare a HoloLens 2 in base ai requisiti dello scenario.

Per una guida alla distribuzione simile allo scenario A leggere la guida per [Cloud connected HoloLens 2 with Remote Assist.](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Guida alla distribuzione - HoloLens 2 connesso al cloud con Assistenza remota](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenario B: distribuire all'interno della rete dell'organizzazione

HoloLens 2 viene distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne. I servizi Internet e cloud potrebbero essere limitati. Questa distribuzione è una distribuzione tipica per la maggior parte dei PC Windows 10.

 * Configurazioni comuni di base
   * Wi-Fi è una rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud.
   * Aggiunta ad Azure AD con registrazione automatica MDM
   * Mdm (Intune) Gestito
   * Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
     * Supporto di uno o più utenti per dispositivo
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi di uso specifici, da Completamente aperto a Chiosco app singola.
   * Una o più applicazioni vengono distribuite tramite MDM

 * Sfide comuni
   * HoloLens 2 non supporta l'aggiunta ad ACTIVE locale o SCCM. Solo l'aggiunta ad Azure AD con MDM. Molte aziende ancora oggi distribuiscono PC Windows 10 in questo scenario come dispositivi aggiunti ad AD locali, gestiti da System Center Configuration Manager (SCCM) e potrebbero non disporre dell'infrastruttura distribuita/configurata per la gestione dei dispositivi Windows 10 interni tramite soluzioni MDM basate su cloud.
   * Poiché HoloLens 2 è un primo dispositivo cloud, si basa molto sui servizi connessi a Internet e cloud per l'autenticazione utente, gli aggiornamenti del sistema operativo, la gestione MDM e così via. Quando ci si connette a una rete aziendale, è molto probabile che sia necessario modificare le regole proxy/firewall per consentire l'accesso a HoloLens 2 e alle applicazioni in esecuzione su di essa.
   * La Wi-Fi aziendale richiede in genere certificati per autenticare il dispositivo o l'utente nella rete. L'infrastruttura o le impostazioni necessarie per distribuire i certificati nei dispositivi Windows 10 tramite MDM possono essere difficili da configurare.

> [!div class="nextstepaction"]
> [Guida alla distribuzione - HoloLens 2 connesso all'azienda con le guide di Dynamics 365](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenario C: Distribuire in un ambiente offline sicuro

HoloLens 2 viene distribuito per l'uso principalmente offline senza accesso alla rete o a Internet. Si tratta di una distribuzione tipica per posizioni altamente sicure o riservate.
 * Configurazioni comuni di base
   * Wi-Fi connettività è disabilitata. Ethernet tramite USB può essere abilitato per la connettività LAN, se necessario.
   * Non gestito.
   * Account utente locale per l'accesso al dispositivo.
     * HoloLens 2 supporta un solo account locale.
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati tramite pacchetti di provisioning in base a casi di uso specifici. Queste configurazioni sono in genere limitate a causa dei requisiti di ambiente sicuro.
   * Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning

 * Sfide comuni
   * È disponibile un set limitato di configurazioni tramite pacchetti di provisioning
   * I servizi cloud non possono essere utilizzati, limitando quindi le funzionalità di HoloLens 2.
   * Sovraccarico amministrativo maggiore poiché questi dispositivi devono essere configurati, configurati e aggiornati manualmente.

Per una guida alla distribuzione simile a questo scenario, consultare la Guida [alla distribuzione sicura offline](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guida alla distribuzione - Offline Secure HoloLens 2](hololens-common-scenarios-offline-secure.md)
