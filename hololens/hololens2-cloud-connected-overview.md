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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923534"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guida alla distribuzione - Cloud connected HoloLens 2 with Remote Assist – Overview

Questa guida consente ai professionisti IT di pianificare e distribuire Microsoft HoloLens 2 dispositivi con Remote Assist all'organizzazione. Verrà utilizzato come modello per le distribuzioni di modelli di verifica all'organizzazione in un'ampia gamma HoloLens 2 casi d'uso. La configurazione è simile allo [Scenario A: Distribuire nei dispositivi di connessione al cloud.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a) 

Durante la guida verrà illustrato come registrare i dispositivi nella gestione dei dispositivi, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente Remote Assist al momento della configurazione del dispositivo. A tale scopo, verranno trattate le parti importanti dell'infrastruttura necessarie per la configurazione e l'esecuzione, ottenendo una distribuzione su larga scala con HoloLens 2. In questa guida non verranno applicate altre restrizioni o configurazioni per i dispositivi, tuttavia è possibile esplorare tali opzioni al termine dell'operazione.

## <a name="prerequisites"></a>Prerequisiti

L'infrastruttura seguente deve essere presente per distribuire il HoloLens 2. In caso contrario, la configurazione di Azure e Intune è inclusa in questa guida:

- Wi-Fi
    - Le reti sono in genere aperte a Internet e ai servizi cloud
- Azure Active Directory (Azure AD) Partecipare alla registrazione automatica MDM (Azure AD[necessaria una sottoscrizione P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
- Mdm (Intune) Gestito
    - Una o più applicazioni vengono distribuite tramite MDM.
- Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
    - Sono supportati uno o più utenti per dispositivo.

:::image type="content" alt-text="Scenario connesso al cloud" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Informazioni sulle Remote Assist

Remote Assist manutenzione e riparazione collaborativa, l'ispezione remota, nonché la condivisione delle conoscenze e la formazione. Connettendo persone con ruoli e posizioni diversi, un tecnico Remote Assist connettersi con un collaboratore remoto in Microsoft Teams. Possono combinare video, screenshot e annotazioni per risolvere i problemi in tempo reale anche quando&#39;nella stessa posizione. I collaboratori remoti possono inserire immagini di riferimento, schemi e altre informazioni utili che il tecnico&#39;ha nello spazio fisico in modo che possano fare riferimento allo schema mentre lavorano a testa alta e senza mani su HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist licenze e requisiti

- Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione delle licenze)
- [Remote Assist sottoscrizione](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o versione [di Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist utente

- Remote Assist licenza
- Connettività di rete

#### <a name="microsoft-teams-user"></a>Utente di Microsoft Teams

- Microsoft Teams o [Teams Freemium.](https://products.office.com/microsoft-teams/free)
- Connettività di rete

Se si prevede di implementare questo [scenario tra tenant,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)potrebbe essere necessaria una licenza information barriers. Vedere [questo articolo per](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) determinare se è necessaria una licenza information barrier.

## <a name="in-this-guide-you-will"></a>Contenuto della guida:

Preparazione:

> [!div class="checklist"]
> - [Informazioni sui dati di base dell'infrastruttura HoloLens 2 dispositivi.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Altre informazioni su Azure AD e su come configurarne una se&#39;non è già stata impostata.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Informazioni sulla gestione delle identità e su come configurare al meglio Azure AD account.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Altre informazioni su MDM e configurazione con Intune se non&#39;ne è già disponibile uno.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Informazioni sui requisiti di rete di Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Facoltativamente: VPN per connettersi alle risorse aziendali](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

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

