---
title: Scenari di distribuzione comuni
description: Altre informazioni sulla distribuzione e sulla gestione dei HoloLens in ambienti aziendali, tra cui infrastruttura, Azure Active Directory e gestione dei dispositivi mobili.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 72b9e61c52d6f4f08cf5a29baf7b01c29fae7489
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635467"
---
# <a name="common-deployment-scenarios"></a>Scenari di distribuzione comuni

## <a name="overview"></a>Panoramica

Questa pagina offre una panoramica generale dell'architettura per tre scenari comuni durante la distribuzione e la gestione di Microsoft HoloLens 2 dispositivi all'interno dell'azienda.

Spesso il modo in cui si gestiscono i dispositivi e si accede alle risorse dell'organizzazione è determinato in gran parte da fattori già in atto. In base all'infrastruttura esistente, è necessario esaminare lo stile di gestione dei dispositivi comune negli scenari seguenti e quindi leggere Planning [HoloLens 2 deployments in a commercial](hololens-core-components.md) environment (Pianificazione delle distribuzioni HoloLens 2 in un ambiente commerciale) per determinare quale scenario corrisponde alle proprie esigenze. Sono disponibili anche tre guide corrispondenti da usare durante la distribuzione.


 1. [Guida alla distribuzione dell'ambiente connesso al cloud](hololens2-cloud-connected-overview.md)
     1. [Guida alla distribuzione dell'ambiente connesso al cloud (client esterni)](hololens2-deployment-guide.md)
 1. [Guida alla distribuzione della rete aziendale](hololens2-corp-connected-overview.md)
 1. [Guida alla distribuzione dell'ambiente protetto offline](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenario A: Distribuire nei dispositivi connessi al cloud

Questo scenario è paragonabile alla distribuzione di dispositivi mobili gestiti all'interno di un'azienda. HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale. Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN. 
 * Configurazioni comuni di base
   * Wi-Fi le reti sono in genere completamente aperte ai servizi Internet e Cloud.
   * Azure AD aggiunta alla registrazione automatica mdm (Mobile Device Management) gestita da MDM (Intune)
   * Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
     * Supporto di uno o più utenti per dispositivo
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a Modalità tutto schermo per app singola.
   * Una o più applicazioni vengono distribuite tramite MDM

* Sfide comuni
   * Determinazione delle configurazioni MDM da applicare al HoloLens 2 in base ai requisiti dello scenario.

[![Diagramma dello scenario A ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

La guida connessa al cloud corrispondente illustra come registrare HoloLens 2 nella gestione dei dispositivi, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente Remote Assist durante la configurazione del dispositivo. Usare la guida Client esterni per distribuire i dispositivi in un sito remoto per un uso esterno a breve o a lungo termine.

> [!div class="nextstepaction"]
> [Guida alla distribuzione dell'ambiente connesso al cloud](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Guida alla distribuzione dell'ambiente connesso al cloud (client esterni)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenario B: Distribuire all'interno della rete dell'organizzazione

Questo scenario è identico a una distribuzione classica per la maggior parte Windows 10 PC. HoloLens 2 viene distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne. I servizi Internet e cloud possono essere limitati. 

 * Configurazioni comuni di base
   * Wi-Fi rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud.
   * Azure AD join con la registrazione automatica MDM
   * GESTIONE MDM (Intune)
   * Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
     * Supporto di uno o più utenti per dispositivo
   * Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a Modalità tutto schermo per app singola.
   * Una o più applicazioni vengono distribuite tramite MDM

 * Sfide comuni
   * HoloLens 2 non supporta l'aggiunta ad ACTIVE locale o SCCM. Solo Azure AD join con MDM. Molte aziende distribuiscono ancora Windows 10 PC in questo scenario come dispositivi aggiunti ad AD locali, gestiti da System Center Configuration Manager (SCCM) e potrebbero non avere l'infrastruttura distribuita/configurata per la gestione dei dispositivi Windows 10 interni tramite soluzioni MDM basate sul cloud.
   * Poiché HoloLens 2 è un primo dispositivo cloud, si basa molto sui servizi connessi a Internet e cloud per l'autenticazione utente, gli aggiornamenti del sistema operativo, la gestione MDM e così via. Quando ci si connette a una rete aziendale, è molto probabile che sia necessario modificare le regole proxy/firewall per abilitare l'accesso per HoloLens 2 e le applicazioni in esecuzione su di essa.
   * La Wi-Fi aziendale richiede in genere certificati per autenticare il dispositivo o l'utente nella rete. L'infrastruttura o le impostazioni necessarie per distribuire i certificati Windows 10 dispositivi tramite MDM possono essere difficili da configurare.

[![Diagramma dello scenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramma dello scenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

La guida alla rete aziendale corrispondente indica come registrare HoloLens 2 nella gestione dei dispositivi esistente, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare una guida dynamics 365, nonché usare app line-of-business personalizzate dopo la configurazione del dispositivo.

> [!div class="nextstepaction"]
> [Guida alla distribuzione della rete aziendale](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenario C: Distribuire in un ambiente offline sicuro

Si tratta di una distribuzione tipica per posizioni altamente sicure o riservate. HoloLens 2 viene distribuito per l'uso principalmente offline senza accesso alla rete o a Internet. 
 * Configurazioni comuni di base
   * Wi-Fi la connettività è disabilitata. Ethernet tramite USB può essere abilitato per la connettività LAN, se necessario.
   * Non gestito.
   * Account utente locale per l'accesso al dispositivo.
     * HoloLens 2 supporta un solo account locale.
   * I diversi livelli di configurazioni di blocco dei dispositivi vengono applicati tramite pacchetti di provisioning in base a casi d'uso specifici. Queste configurazioni sono in genere limitate a causa dei requisiti di ambiente sicuro.
   * Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning

 * Sfide comuni
   * È disponibile un set limitato di configurazioni tramite i pacchetti di provisioning
   * I servizi cloud non possono essere usati, limitando quindi le funzionalità HoloLens 2 cloud.
   * Maggiore sovraccarico amministrativo perché questi dispositivi devono essere configurati, configurati e aggiornati manualmente.

[![Diagramma della sicurezza offline 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

La guida alla sicurezza offline corrispondente fornisce istruzioni per l'applicazione di un pacchetto di provisioning di esempio che blocca un HoloLens 2 per l'uso in ambienti sicuri.

> [!div class="nextstepaction"]
> [Guida alla distribuzione dell'ambiente protetto offline](hololens-common-scenarios-offline-secure.md)


