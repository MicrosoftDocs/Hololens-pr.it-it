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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397422"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Panoramica degli scenari comuni di distribuzione dell'infrastruttura

Le informazioni seguenti forniscono una panoramica generale dell'architettura per tre scenari comuni durante la distribuzione e la gestione di Microsoft HoloLens 2 all'interno dell'azienda. Spesso il modo in cui si gestiscono i dispositivi e come accedere alle risorse dell'organizzazione è determinato in gran parte da fattori già presenti. In base all'infrastruttura esistente, è necessario esaminare lo stile di gestione dei dispositivi comune negli scenari seguenti e provare le guide per la distribuzione nello scenario in base alle esigenze.

## <a name="scenarios"></a>Scenari

Il diagramma seguente rappresenta due scenari gestiti tipici per HoloLens 2 distribuzione.
 

Esiste anche un terzo scenario che consente distribuzioni protette offline.

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenario A: Distribuire nei dispositivi connessi al cloud

HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale. Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN. Questa distribuzione è simile ai dispositivi mobili gestiti all'interno di un'azienda.
 * Configurazioni comuni di base
   * Wi-Fi reti virtuali sono in genere completamente aperte a Internet e ai servizi cloud.
   * Azure AD aggiunta alla registrazione automatica di Gestione di dispositivi mobili (MDM) - Gestione MDM (Intune)
   * Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
     * Supporto di uno o più utenti per dispositivo
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a App singola in modalità tutto schermo.
   * Una o più applicazioni vengono distribuite tramite MDM



* Problemi comuni
   * Determinazione delle configurazioni MDM da applicare alla HoloLens 2 in base ai requisiti dello scenario.

[![Diagramma dello scenario A ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

Per una guida alla distribuzione simile a questo scenario, vedere la guida alla distribuzione dell'ambiente [connesso al cloud](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guida alla distribuzione dell'ambiente connesso al cloud](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [Guida alla distribuzione dell'ambiente connesso al cloud (client esterni)](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenario B: Distribuire all'interno della rete dell'organizzazione

HoloLens 2 viene distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne. I servizi Internet e cloud possono essere limitati. Questa distribuzione è una distribuzione tipica per la maggior Windows 10 PC.

 * Configurazioni comuni di base
   * Wi-Fi rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud.
   * Azure AD join con la registrazione automatica MDM
   * GESTIONE MDM (Intune)
   * Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
     * Supporto di uno o più utenti per dispositivo
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a Modalità tutto schermo per app singola.
   * Una o più applicazioni vengono distribuite tramite MDM

 * Problemi comuni
   * HoloLens 2 non supporta l'aggiunta ad ACTIVE locale o SCCM. Aggiungere Azure AD mdm. Molte aziende oggi distribuiscono ancora PC Windows 10 in questo scenario come dispositivi aggiunti ad AD locali, gestiti da System Center Gestione configurazione (SCCM) e potrebbero non avere l'infrastruttura distribuita/configurata per la gestione dei dispositivi Windows 10 interni tramite soluzioni MDM basate sul cloud.
   * Poiché HoloLens 2 è un dispositivo cloud first, si basa in larga parte sui servizi connessi a Internet e cloud per l'autenticazione utente, gli aggiornamenti del sistema operativo, la gestione MDM e così via. Quando ci si connette a una rete aziendale, è molto probabile che sia necessario modificare le regole proxy/firewall per abilitare l'accesso per HoloLens 2 e le applicazioni in esecuzione su di essa.
   * La Wi-Fi aziendale richiede in genere certificati per autenticare il dispositivo o l'utente nella rete. L'infrastruttura o le impostazioni necessarie per distribuire i certificati Windows 10 dispositivi tramite MDM possono essere difficili da configurare.

[![Diagramma dello scenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramma dello scenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Per una guida alla distribuzione simile a questo scenario, vedere la guida alla [guida alla distribuzione della rete aziendale](hololens2-corp-connected-overview.md).

> [!div class="nextstepaction"]
> [Guida alla distribuzione della rete aziendale](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenario C: Distribuire in un ambiente offline sicuro

HoloLens 2 viene distribuito per l'uso principalmente offline senza accesso alla rete o a Internet. Si tratta di una distribuzione tipica per posizioni altamente sicure o riservate.
 * Configurazioni comuni di base
   * Wi-Fi connettività è disabilitata. Ethernet tramite USB può essere abilitata per la connettività LAN, se necessario.
   * Non gestito.
   * Account utente locale per l'accesso al dispositivo.
     * HoloLens 2 supporta un solo account locale.
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati tramite pacchetti di provisioning in base a casi d'uso specifici. Queste configurazioni sono in genere limitate a causa dei requisiti dell'ambiente sicuro.
   * Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning

 * Problemi comuni
   * È disponibile un set limitato di configurazioni tramite il provisioning dei pacchetti
   * I servizi cloud non possono essere usati, limitando quindi le HoloLens 2 funzionalità.
   * Maggiore sovraccarico amministrativo perché questi dispositivi devono essere configurati, configurati e aggiornati manualmente.

[![Diagramma 1 ](images/deployment-guides-revised-scenario-c-01.png) della sicurezza offline](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Per una guida alla distribuzione simile a questo scenario, vedere la guida [alla distribuzione dell'ambiente protetto offline](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guida alla distribuzione dell'ambiente protetto offline](hololens-common-scenarios-offline-secure.md)
