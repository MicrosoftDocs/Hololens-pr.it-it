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
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635892"
---
# <a name="license-requirements"></a>Requisiti relativi alle licenze

## <a name="hololens-2-device-managed"></a>HoloLens 2 Dispositivo (gestito)

[Azure AD Account](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) non può essere usato per gestire HoloLens dispositivi.

[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) o un altro MDM.
- [Windows Autopilot per HoloLens 2:](hololens2-autopilot.md)semplifica l'esperienza di provisioning sia per gli amministratori IT che per gli utenti finali. Gli amministratori IT possono preconfigurare i HoloLens 2 e al primo avvio i dispositivi verranno distribuiti in stato business-ready senza interazione dell'utente finale. 

  > [!NOTE]
  > Windows Autopilot richiede [che Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) e [la registrazione](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) automatica siano configurati per primi per la distribuzione del dispositivo e del flusso di Autopilot a tocco basso. 

### <a name="business-use-case"></a>Caso d'uso aziendale: 

- [Scenario di distribuzione A:](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) modello di verifica o distribuzione pilota.

- [Scenario di distribuzione B:](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) distribuzione su larga scala.

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 Solo dispositivo (non gestito)

Quando si usa un account Microsoft (MSA) o un account locale, non sono necessarie licenze aggiuntive per questi account.

[Account locale](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- Il provisioning di questo account deve [essere](hololens-provisioning.md#provisioning-package-hololens-wizard) eseguito in anticipo con Windows Configuration Designer (WCD).

[Account Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Non sono supportati più utenti per un dispositivo che usa uno di questi account.

### <a name="business-use-case"></a>Caso d'uso aziendale: 

- [Scenario di distribuzione C:](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) distribuzione offline o sicura.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Licenze e requisiti di Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Amministrativi

- Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione delle licenze)
- [Remote Assist sottoscrizione](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o versione [di Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist utente

- Account Azure AD

- Remote Assist licenza 

  > [!NOTE]
  > Microsoft Teams è in bundle con Remote Assist

- Connettività di rete

#### <a name="microsoft-teams-user"></a>Microsoft Teams utente

- Account Azure AD

- Microsoft Teams o [Teams Freemium.](https://products.office.com/microsoft-teams/free)

- Connettività di rete

Se si prevede di implementare questo [scenario tra tenant,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)potrebbe essere necessaria una licenza information barriers. Vedere [questo articolo per](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) determinare se è necessaria una licenza information barrier.

### <a name="dynamics-365-guides"></a>Guide di Dynamics 365 

#### <a name="admin"></a>Amministrativi

- Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione delle licenze)
- Sottoscrizione di Dynamics 365 [Guides o versione di valutazione gratuita](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)

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
