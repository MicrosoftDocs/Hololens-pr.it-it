---
title: Requisiti relativi alle licenze
description: Tenersi aggiornati su tutti i requisiti di licenza e le linee guida necessari per la gestione dei dispositivi mobili, HoloLens e Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: bd55edcc855e20d6709c7e535573f43785155d41
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2021
ms.locfileid: "114661713"
---
# <a name="license-requirements"></a>Requisiti relativi alle licenze

## <a name="overview"></a>Panoramica
Questa pagina offre una panoramica generale delle licenze e degli account necessari per distribuire dispositivi gestiti e non HoloLens 2 nell'organizzazione. Include anche informazioni per le licenze di Dynamics 365 [Remote Assist](#dynamics-365-remote-assist) e [Guides](#dynamics-365-guides).

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 requisiti di licenza e account

 
|       &nbsp;      | Gestione HoloLens | Non HoloLens |
|-------------------|-----------------|---------------------|
| **Caso d'uso aziendale** | | |
| [Distribuire nei dispositivi connessi al cloud: modello di verifica/distribuzione pilota](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Distribuire all'interno della rete dell'organizzazione: distribuzione su larga scala](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Eseguire la distribuzione in un ambiente offline sicuro](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licenses** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> o <sup>2)</sup> | ✔️  | |
| **Account** |  | |
| Azure AD account amministratore | ✔️ |  |
| Account utente di Azure AD | ✔️ | |
| [Account Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Account locale](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [Registrazione automatica durante](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) la configurazione iniziale del dispositivo, che registra e Azure Active Directory e consente la gestione del dispositivo con Intune.
- <sup>2</sup> [Windows Autopilot per HoloLens 2](hololens2-autopilot.md) semplifica l'esperienza di provisioning sia per gli amministratori IT che per gli utenti finali. Gli amministratori IT possono preconfigurare i HoloLens 2 e al primo avvio i dispositivi verranno distribuiti in stato business-ready senza interazione dell'utente finale.
- <sup>3</sup> Il provisioning di [questo](hololens-provisioning.md#provisioning-package-hololens-wizard) account deve essere eseguito in anticipo Windows Configuration Designer (WCD).

> [!IMPORTANT]
> Active Directory (AD) non può essere usato per gestire HoloLens dispositivi.
 
> [!WARNING]
> Più utenti non sono supportati per un dispositivo che usa un account del servizio microsoft o un account locale.

## <a name="dynamics-365-licensing-and-requirements"></a>Licenze e requisiti di Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Amministrativi

- Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione delle licenze)
- [Remote Assist sottoscrizione](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o versione [di Remote Assist)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist utente

- Account Azure AD

- Remote Assist licenza 

  > [!NOTE]
  > Microsoft Teams è in bundle con Remote Assist

- Connettività di rete

#### <a name="microsoft-teams-user"></a>Microsoft Teams utente

- Account Azure AD

- Microsoft Teams o [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Connettività di rete

Se si prevede di implementare questo [scenario tra tenant,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)potrebbe essere necessaria una licenza information barriers. Vedere [questo articolo per](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) determinare se è necessaria una licenza information barrier.

### <a name="dynamics-365-guides"></a>Guide di Dynamics 365 

#### <a name="admin"></a>Amministrativi

1. Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione delle licenze)
2. Sottoscrizione di Dynamics 365 [Guides o versione di valutazione gratuita](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Autore guide

1. Account Azure AD
1. [Dynamics 365 Guides licenza](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides'applicazione installata in un PC o in un HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (usato per visualizzare il dashboard di Analytics)
1. Ruolo Autore (per la creazione di guide)
1. Connettività di rete

#### <a name="guides-user"></a>Guida l'utente

1. Account Azure AD
1. [Dynamics 365 Guides licenza](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides'app installata in un HoloLens
1. Ruolo operatore (per il test o l'uso di guide)
1. Connettività di rete
