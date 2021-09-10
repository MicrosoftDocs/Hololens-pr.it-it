---
title: Panoramica dei servizi connessi HoloLens 2 cloud con Remote Assist
description: Informazioni su come registrare HoloLens 2 dispositivi in una rete connessa al cloud usando Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 66e543dd699edbd54ab41474f3ea86fa313bf6ba
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427079"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guida alla distribuzione - Cloud connected HoloLens 2 con Remote Assist - Panoramica

Questa guida consente ai professionisti IT di pianificare e distribuire Microsoft HoloLens 2 dispositivi con Remote Assist all'organizzazione. Questo modello fungerà da modello per le distribuzioni di modelli di verifica per l'organizzazione in HoloLens 2 casi d'uso. La configurazione è simile allo [scenario A: Distribuire nei dispositivi cloud connect](common-scenarios.md#scenario-a). 

Durante la guida verrà illustrato come registrare i dispositivi nella gestione dei dispositivi, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente Remote Assist durante la configurazione del dispositivo. A tale scopo, verranno trattate le importanti parti dell'infrastruttura necessarie per la configurazione e l'esecuzione, ottenendo una distribuzione su larga scala con HoloLens 2. In questa guida non verranno applicate altre restrizioni o configurazioni per i dispositivi, tuttavia è necessario esplorare tali opzioni dopo il completamento.

## <a name="prerequisites"></a>Prerequisiti

Per distribuire il HoloLens 2, deve essere presente l'infrastruttura seguente. In caso contrario, la configurazione di Azure e Intune è inclusa in questa guida:

Si tratta di un'installazione simile a [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), che è un'opzione valida per molte distribuzioni del modello di verifica, tra cui:

- Wi-Fi reti sono in genere completamente aperte ai servizi Internet e cloud
- Azure AD aggiunta alla registrazione automatica MDM- Gestita da MDM (Intune)
- Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
    - Sono supportati uno o più utenti per dispositivo.

:::image type="content" alt-text="Scenario connesso al cloud." source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Informazioni sulle Remote Assist

Remote Assist consente la manutenzione e la riparazione collaborativa, l'ispezione remota, nonché la condivisione delle conoscenze e il training. Connettendo persone in ruoli e località diversi, un tecnico che usa Remote Assist può connettersi con un collaboratore remoto in Microsoft Teams. Possono combinare video, screenshot e annotazioni per risolvere i problemi in tempo reale anche quando non si sono nella stessa posizione. I collaboratori remoti possono inserire immagini di riferimento, schemi e altre informazioni utili per lo spazio fisico del tecnico in modo che possano fare riferimento allo schema mentre lavorano a testa in su e senza HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist licenze e requisiti

- Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione di licenze)
- [Remote Assist sottoscrizione](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o Remote Assist [versione di valutazione)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist utente

- Remote Assist licenza
- Connettività di rete

#### <a name="microsoft-teams-user"></a>Microsoft Teams utente

- Microsoft Teams o [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Connettività di rete

Se si prevede di implementare questo [scenario tra tenant,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)potrebbe essere necessaria una licenza Information Barriers. Per determinare se è necessaria una licenza Information Barrier, vedere [Vendor and customers use full Dynamics 365 Remote Assist capabilities](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).

## <a name="in-this-guide-you-will"></a>Contenuto della guida:

Preparazione:

> [!div class="checklist"]
> - [Informazioni sulle informazioni di base sull'infrastruttura per HoloLens 2 dispositivi.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Per altre informazioni Azure AD e configurarne uno,&#39;non è necessario.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Informazioni sulla gestione delle identità e su come configurare al meglio Azure AD account.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Altre informazioni su MDM e configurazione con Intune se non&#39;ne è già pronta una.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Informazioni sui requisiti di rete di Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Facoltativamente: VPN per connettersi alle risorse aziendali](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurare:

> [!div class="checklist"]
> - [Come creare utenti e gruppi.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Come configurare la registrazione automatica all'interno di Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
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

