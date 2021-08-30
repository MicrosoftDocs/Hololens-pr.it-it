---
title: Scenari di distribuzione comuni
description: Altre informazioni sulla distribuzione e sulla gestione dei HoloLens in ambienti aziendali, tra cui infrastruttura, Azure Active Directory e gestione dei dispositivi mobili.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189240"
---
# <a name="common-deployment-scenarios"></a>Scenari di distribuzione comuni

## <a name="overview"></a>Panoramica

Capire come distribuire un nuovo dispositivo può essere difficile quando lo si prova la prima volta. Qui vengono condivisi diversi modi per distribuire e gestire Microsoft HoloLens 2 dispositivi all'interno dell'organizzazione.

Si vogliono distribuire soluzioni su larga scala. Vogliamo arrivarci. Prima di tutto verranno descritti i passaggi per distribuire i dispositivi, quindi gli ologrammi, per ottenere valore per lo scenario di realtà mista di destinazione, indipendentemente dal fatto che si utilizzi D365 Remote Assist, Guide o un'applicazione abilitata per il servizio di realtà mista di Azure creata.

L'utente può essere un decisore aziendale, un professionista IT o un team di innovazione che sta cercando di adottare HoloLens all'interno dell'organizzazione. Durante la compilazione dal modello di verifica a una distribuzione con scalabilità, le guide alla distribuzione hanno senso HoloLens all'interno dell'infrastruttura IT, indipendentemente dalle dimensioni o dalle dimensioni. Gli scenari di distribuzione seguenti sono i più comuni:

| Scenario |Utilizzo | Punti chiave |
|---------|---------|---------|
| [Scenario A: Dispositivi connessi al cloud](hololens2-cloud-connected-overview.md) | Quando si inizia la distribuzione per la prima volta, è possibile avviare piccole dimensioni e distribuire un singolo dispositivo connesso al cloud solo per visualizzare il processo di base. | I dispositivi saranno connessi ai servizi cloud e a Internet pubblico. Si tratta della soluzione più adatta ai casi d'uso dei clienti, ai servizi sul campo e al modello di verifica.|
| [Scenario B: Rete dell'organizzazione](hololens2-corp-connected-overview.md) | Durante la distribuzione nell'ambiente di produzione su larga scala, potrebbe essere necessario eseguire l'integrazione con la rete dell'organizzazione. | I dispositivi verranno connessi a una rete Wi-Fi "Aziendale". Questa opzione è più adatta per gli utenti interni o per l'uso all'interno dell'ambiente aziendale.|
| [Scenario C: Ambiente protetto offline](hololens-common-scenarios-offline-secure.md) | Alcuni processi cruciali o alcuni criteri aziendali possono richiedere l'uso di ambienti offline. | I dispositivi verranno connessi a una rete altamente restrittiva o saranno esclusivamente dispositivi offline. Ciò è più adatto per ambienti altamente sicuri o restrizioni di connettività Internet in aree remote. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenario A: Distribuire nei dispositivi connessi al cloud

Questo scenario è paragonabile alla distribuzione di dispositivi mobili gestiti all'interno di un'azienda. HoloLens 2 viene distribuito per l'uso principalmente in ambienti esterni a una rete aziendale. Le risorse aziendali non sono accessibili o possono essere limitate tramite VPN.

[![Diagramma scenario A.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Utilizzo

Considerare questo modello di distribuzione per:

* Distribuzione del modello di verifica, dei progetti pilota e dei servizi sul campo
* Distribuzione di [Remote Assist](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Configurazioni comuni di base

* Wi-Fi reti sono in genere completamente aperte a Internet e ai servizi cloud
* Azure AD aggiunta alla registrazione automatica di Gestione dispositivi mobili (MDM), gestita da MDM (Intune)
* Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
  * Supporto di uno o più utenti per dispositivo
* Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a Modalità tutto schermo per app singola.
* Una o più applicazioni vengono distribuite tramite MDM

### <a name="common-challenges"></a>Problemi comuni

* Determinazione delle configurazioni MDM da applicare alla HoloLens 2 in base ai requisiti dello scenario

La guida cloud connessa corrispondente illustra come registrare HoloLens 2 nella gestione dei dispositivi, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente Remote Assist alla configurazione del dispositivo.

> [!div class="nextstepaction"]
> [Guida alla distribuzione di Cloud Connected](hololens2-cloud-connected-overview.md)

Usare la guida Client esterni per distribuire i dispositivi in un sito remoto per un uso esterno a breve o a lungo termine.

> [!div class="nextstepaction"]
> [Guida alla distribuzione di cloud connessi (client esterni)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenario B: Distribuire all'interno della rete dell'organizzazione

Questo scenario è identico a una distribuzione classica per la maggior parte Windows 10 PC. HoloLens 2 viene distribuito per l'uso principalmente nella rete aziendale con accesso alle risorse aziendali interne. I servizi Internet e cloud possono essere limitati. 

[![Diagramma dello scenario B1.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramma dello scenario B2.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Utilizzo

Considerare questo modello di distribuzione per:

* Utenti interni
* Distribuzione su larga scala (pilota e produzione) all'interno dell'ambiente aziendale

### <a name="basic-common-configurations"></a>Configurazioni comuni di base

* Wi-Fi rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud.
* Azure AD join con la registrazione automatica MDM
* GESTIONE MDM (Intune)
* Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
  * Supporto di uno o più utenti per dispositivo
* Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a Modalità tutto schermo per app singola.
* Una o più applicazioni vengono distribuite tramite MDM

### <a name="common-challenges"></a>Problemi comuni

* HoloLens 2 non supporta l'aggiunta ad ACTIVE locale o System Center Configuration Manager (SCCM). Solo Azure AD join con MDM. Molte aziende distribuiscono ancora Windows 10 PC in questo scenario come dispositivi aggiunti ad AD locali, gestiti da SCCM e potrebbero non avere l'infrastruttura distribuita/configurata per la gestione dei dispositivi Windows 10 interni tramite soluzioni MDM basate sul cloud.
* Poiché HoloLens 2 è un primo dispositivo cloud, si basa molto sui servizi connessi a Internet e cloud per l'autenticazione utente, gli aggiornamenti del sistema operativo, la gestione MDM e così via. Quando ci si connette a una rete aziendale, è molto probabile che sia necessario modificare le regole proxy/firewall per abilitare l'accesso per HoloLens 2 e le applicazioni in esecuzione su di essa.
* La Wi-Fi aziendale richiede in genere certificati per autenticare il dispositivo o l'utente nella rete. L'infrastruttura o le impostazioni necessarie per distribuire i certificati Windows 10 dispositivi tramite MDM possono essere difficili da configurare.

La guida aziendale connessa corrispondente indica come registrare HoloLens 2 nella gestione dei dispositivi esistente, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare una guida dynamics 365, nonché di usare app line-of-business personalizzate dopo la configurazione del dispositivo.

> [!div class="nextstepaction"]
> [Guida alla distribuzione aziendale connessa](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenario C: Distribuire in un ambiente offline sicuro

Si tratta di una distribuzione tipica per posizioni altamente sicure o riservate. HoloLens 2 viene distribuito per l'uso principalmente offline senza accesso alla rete o a Internet.

[![Diagramma di sicurezza offline 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Utilizzo

Considerare questo modello di distribuzione per:

* Ambienti altamente sicuri in cui i dati devono essere conservati all'interno
* "Esperienze" in cui il pubblico usa i dispositivi
* Problema di connettività Internet nell'area remota

### <a name="basic-common-configurations"></a>Configurazioni comuni di base

* Wi-Fi la connettività è disabilitata. Ethernet tramite USB può essere abilitato per la connettività LAN, se necessario
* Non gestito
* Account utente locale per l'accesso al dispositivo
  * HoloLens 2 supporta un solo account locale
* I diversi livelli di configurazioni di blocco dei dispositivi vengono applicati tramite pacchetti di provisioning in base a casi d'uso specifici. Queste configurazioni sono in genere limitate a causa dei requisiti di ambiente sicuro
* Una o più applicazioni vengono distribuite tramite il pacchetto di provisioning

### <a name="common-challenges"></a>Problemi comuni

* È disponibile un set limitato di configurazioni tramite i pacchetti di provisioning
* I servizi cloud non possono essere usati, limitando quindi le HoloLens 2 funzionalità.
* Maggiore sovraccarico amministrativo perché questi dispositivi devono essere configurati, configurati e aggiornati manualmente.

La guida alla sicurezza offline corrispondente fornisce istruzioni per l'applicazione di un pacchetto di provisioning di esempio che blocca un HoloLens 2 per l'uso in ambienti sicuri.

> [!div class="nextstepaction"]
> [Guida alla distribuzione dell'ambiente protetto offline](hololens-common-scenarios-offline-secure.md)
