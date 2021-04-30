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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309482"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Panoramica degli scenari comuni di distribuzione dell'infrastruttura

Queste informazioni forniscono una panoramica generale dell'architettura per tre scenari comuni quando si distribuiscono e si gestiscono Microsoft HoloLens 2 dispositivi all'interno dell'azienda. Spesso il modo in cui si gestiscono i dispositivi e come accedere alle risorse dell'organizzazione è determinato in gran parte da fattori già presenti. In base all'infrastruttura esistente, è necessario esaminare lo stile di gestione dei dispositivi comune negli scenari seguenti e provare le guide per la distribuzione nello scenario in base alle esigenze.

## <a name="scenarios"></a>Scenari

Il diagramma seguente rappresenta tre scenari tipici per HoloLens 2 distribuzione.
![Diagramma degli scenari](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>Scenario A: Distribuire nei dispositivi cloud connect

HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale. Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN. Questa distribuzione è simile ai dispositivi mobili gestiti all'interno di un'azienda.
 * Configurazioni comuni di base
   * Wi-Fi le reti sono in genere completamente aperte ai servizi Internet e Cloud.
   * Azure AD aggiunta alla registrazione automatica mdm (Mobile Device Management) gestita da MDM (Intune)
   * Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
     * Supporto di uno o più utenti per dispositivo
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a Modalità tutto schermo per app singola.
   * Una o più applicazioni vengono distribuite tramite MDM

* Problemi comuni
   * Determinazione delle configurazioni MDM da applicare al HoloLens 2 in base ai requisiti dello scenario.

Per una guida alla distribuzione simile allo scenario A esaminare la guida per Cloud [connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guida alla distribuzione- Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenario B: Eseguire la distribuzione all'interno della rete dell'organizzazione

HoloLens 2 viene distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne. I servizi Internet e cloud possono essere limitati. Questa distribuzione è una distribuzione tipica per la maggior parte Windows 10 PC.

 * Configurazioni comuni di base
   * Wi-Fi rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud.
   * Azure AD join con la registrazione automatica MDM
   * Mdm (Intune) Gestito
   * Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
     * Supporto di uno o più utenti per dispositivo
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a App singola in modalità tutto schermo.
   * Una o più applicazioni vengono distribuite tramite MDM

 * Problemi comuni
   * HoloLens 2 non supporta l'aggiunta ad AD locale o SCCM. Aggiungere Azure AD mdm. Molte aziende distribuiscono ancora PC Windows 10 in questo scenario come dispositivi aggiunti ad AD locali, gestiti da System Center Gestione configurazione (SCCM) e potrebbero non avere l'infrastruttura distribuita/configurata per la gestione dei dispositivi Windows 10 interni tramite soluzioni MDM basate sul cloud.
   * Poiché HoloLens 2 è un primo dispositivo cloud, si basa molto sui servizi connessi a Internet e cloud per l'autenticazione utente, gli aggiornamenti del sistema operativo, la gestione MDM e così via. Quando ci si connette a una rete aziendale, è molto probabile che sia necessario modificare le regole proxy/firewall per abilitare l'accesso per HoloLens 2 e le applicazioni in esecuzione su di essa.
   * La Wi-Fi aziendale richiede in genere certificati per autenticare il dispositivo o l'utente nella rete. L'infrastruttura o le impostazioni necessarie per distribuire i certificati Windows 10 dispositivi tramite MDM possono essere difficili da configurare.

> [!div class="nextstepaction"]
> [Guida alla distribuzione- Guida alla HoloLens 2 aziendale con le guide di Dynamics 365](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenario C: Distribuire in un ambiente offline sicuro

HoloLens 2 viene distribuito per l'uso principalmente offline senza accesso alla rete o a Internet. Si tratta di una distribuzione tipica per posizioni altamente sicure o riservate.
 * Configurazioni comuni di base
   * Wi-Fi la connettività è disabilitata. Ethernet tramite USB può essere abilitato per la connettività LAN, se necessario.
   * Non gestito.
   * Account utente locale per l'accesso al dispositivo.
     * HoloLens 2 supporta un solo account locale.
   * I diversi livelli di configurazioni di blocco dei dispositivi vengono applicati tramite pacchetti di provisioning in base a casi d'uso specifici. Queste configurazioni sono in genere limitate a causa dei requisiti di ambiente sicuro.
   * Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning

 * Problemi comuni
   * È disponibile un set limitato di configurazioni tramite i pacchetti di provisioning
   * I servizi cloud non possono essere usati, limitando quindi le HoloLens 2 funzionalità.
   * Maggiore sovraccarico amministrativo perché questi dispositivi devono essere configurati, configurati e aggiornati manualmente.

Per una guida alla distribuzione simile a questo scenario, vedere la [Guida alla distribuzione sicura offline.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Guida alla distribuzione - Sicurezza offline HoloLens 2](hololens-common-scenarios-offline-secure.md)
