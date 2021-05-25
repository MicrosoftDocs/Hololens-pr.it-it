---
title: Panoramica dei servizi connessi HoloLens 2 cloud con Remote Assist
description: Informazioni su come registrare HoloLens 2 dispositivi su una rete connessa al cloud usando Dynamics 365 Remote Assist.
keywords: HoloLens, gestione, connessa al cloud, Remote Assist, AAD, Azure AD, MDM, gestione dei dispositivi mobili
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397652"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guida alla distribuzione - Cloud connected HoloLens 2 con Remote Assist - Panoramica

Questa guida consente ai professionisti IT di pianificare e distribuire Microsoft HoloLens 2 dispositivi all'organizzazione con l'obiettivo complessivo di avere questi dispositivi connessi al cloud all'organizzazione con Dynamics 365 Remote Assist pronti per l'uso. Tenere presente che questo modello fungerà da modello per le distribuzioni di modelli di verifica per l'organizzazione in un'ampia gamma di HoloLens 2 casi d'uso.

Durante la guida verrà illustrato come registrare i dispositivi nella gestione dei dispositivi, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente Remote Assist durante la configurazione del dispositivo. A tale scopo, verranno trattate le importanti infrastrutture necessarie per la configurazione e l'esecuzione, ottenendo una distribuzione su larga scala con HoloLens 2.

[![Scenario connesso al cloud ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>In questa guida

Questa guida ha l'obiettivo specifico di configurare Remote Assist all'interno dell'organizzazione nei dispositivi HoloLens. Verranno trattati i necessari per raggiungere questo obiettivo. Per mantenere l'attenzione su questo obiettivo, alcune configurazioni e preparazione verranno preseescente per ottimizzare questa distribuzione o ridurre gli elementi necessari per la configurazione. Si verrà informati di queste scelte e sarà possibile personalizzare la distribuzione in base alle esigenze aziendali.

Si tratta di una configurazione simile a [Scenario A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Deploy to cloud connect devices , che è un'opzione valida per molte distribuzioni del modello di verifica, tra cui:

- Wi-Fi reti sono in genere completamente aperte ai servizi Internet e cloud
- Azure AD aggiunta alla registrazione automatica MDM - GESTIONE MDM (Intune)
- Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
  - Supporto di uno o più utenti per dispositivo
- Diversi livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi d'uso specifici, da Completamente aperto a App singola in modalità tutto schermo



In questa guida non verranno applicate altre restrizioni o configurazioni per i dispositivi, tuttavia si consiglia di esplorare tali opzioni al termine dell'operazione.

## <a name="learn-about-remote-assist"></a>Informazioni sulle Remote Assist

Remote Assist la manutenzione e la riparazione collaborative, l'ispezione remota, nonché la condivisione delle conoscenze e la formazione. Connettendo persone con ruoli e posizioni diversi, un tecnico Remote Assist può connettersi con un collaboratore remoto in Microsoft Teams. Possono combinare video, screenshot e annotazioni per risolvere i problemi in tempo reale anche quando&#39;nella stessa posizione. I collaboratori remoti possono inserire immagini di riferimento, schemi e altre informazioni utili che il tecnico&#39;ha nello spazio fisico in modo che possano fare riferimento allo schema mentre lavorano a testa alta e senza mani su HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>Contenuto della guida:

Preparazione:

> [!div class="checklist"]
> - [Informazioni sui dati di base dell'infrastruttura HoloLens 2 dispositivi.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Altre informazioni su Azure AD e su come configurarne una se&#39;non è già stata impostata.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Informazioni sulla gestione delle identità e su come configurare al meglio Azure AD account.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Altre informazioni su MDM e configurazione con Intune se non&#39;ne è già disponibile uno.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Informazioni sui requisiti di rete di Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Facoltativamente: VPN per connettersi alle risorse aziendali](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurare:

> [!div class="checklist"]
> - [Come creare utenti e gruppi.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Come configurare la registrazione automatica all'interno Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Come assegnare le licenze dell'applicazione.](hololens2-cloud-connected-configure.md#application-licenses)

Distribuzione:

> [!div class="checklist"]
> - [Configurare la registrazione HoloLens 2 convalidare la registrazione.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Verificare che sia possibile effettuare una Remote Assist chiamata.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Gestione:

> [!div class="checklist"]
> - [Come aggiornare i Remote Assist usando l'app Microsoft Store app.](hololens2-cloud-connected-maintain.md#updates)
> - [Creazione di un piano di supporto.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Piano di sviluppo.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud - Preparare](hololens2-cloud-connected-prepare.md)

