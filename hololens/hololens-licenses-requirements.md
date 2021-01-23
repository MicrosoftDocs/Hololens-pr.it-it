---
title: Requisiti di licenza
description: È importante tenersi sempre aggiornati sui requisiti di licenza e sulle linee guida necessarie per la gestione di dispositivi mobili, HoloLens e assistenza remota.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283967"
---
# Requisiti di licenza

## Indicazioni sulle licenze di Gestione dei dispositivi mobili (MDM)

Se si prevede di gestire i dispositivi HoloLens, saranno necessari Azure AD e un sistema MDM. Active Director (AD) non può essere usato per gestire i dispositivi HoloLens.
Se si prevede di usare un sistema MDM diverso da Intune, è necessaria una [licenza di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).
Se si prevede di usare Intune come MDM, leggere l'[elenco delle suite](https://docs.microsoft.com/intune/fundamentals/licenses) che includono le licenze di Intune. **Si noti che Azure AD è incluso nella maggior parte delle famiglie di prodotti.**

## Identificare le licenze necessarie per lo scenario e i prodotti

### Requisiti di licenza di HoloLens (prima generazione)

Potrebbe essere necessario aggiornare il dispositivo HoloLens (prima generazione) a Windows Holographic for Business. (Per determinare se è necessario eseguire l'aggiornamento, vedere [Funzionalità commerciali di HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions)).

 In tale caso, si dovranno eseguire le operazioni seguenti:

- Acquistare un file XML di licenza HoloLens Enterprise.
- Applicare il file XML a HoloLens. È possibile eseguire questa operazione tramite un [pacchetto di provisioning](hololens-provisioning.md) o tramite il [Gestore di dispositivi mobili](https://docs.microsoft.com/intune/configuration/holographic-upgrade).

### Requisiti di licenza di Remote Assist

Verificare di disporre della licenza e del dispositivo necessari nella documentazione relativa ai [requisiti](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).

1. [Licenza di Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Altrimenti, provare la [versione di valutazione di Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Licenza di Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Se si prevede di implementare **[questo scenario tra tenant](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, potrebbe essere necessaria una licenza Barriere informative. Vedere [questo articolo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) per determinare se è necessaria una licenza Barriere informative.

### Guide ai requisiti di licenza

Verificare i [requisiti di licenze e dispositivi aggiornati](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).

1. [Licenza di Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Guide](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
