---
title: Windows Supporto della registrazione di Autopilot per HoloLens 2
description: Informazioni su come ottenere il supporto per la registrazione per Autopilot HoloLens 2 dispositivi.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Pilota automatico
manager: ylempidakis
ms.openlocfilehash: 2304e7ec18eb531cce431fb93c7abf38f2c9a1cef30f0d6c6fcaac6c95281f8e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661782"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2 Supporto della registrazione per Autopilot

I clienti e i provider di soluzioni cloud Microsoft possono ora registrare HoloLens 2 dispositivi inviando direttamente le richieste Supporto tecnico Microsoft. Questa pagina illustra i requisiti per gli scenari di registrazione di Autopilot supportati seguenti:

- **HoloLens 2 registrazione di Device Autopilot**. Invia la richiesta di registrazione HoloLens 2 dispositivi in Windows Autopilot.
- **HoloLens 2 richiesta hash hardware del dispositivo**. Invia la richiesta Supporto tecnico Microsoft di fornire hash hardware che i clienti o i CSP possono usare per registrare automaticamente i dispositivi tramite Microsoft Intune o Microsoft Partner Center.
- **HoloLens 2 dispositivo Autopilot Deregistration**. Invia la richiesta di eliminazione dei dispositivi Windows Autopilot, in genere usata negli scenari di fine vita del dispositivo.

Nella tabella seguente vengono fornite informazioni dettagliate sulle informazioni che è necessario raccogliere prima *di* inviare richieste di registrazione Supporto tecnico Microsoft.

| Informazioni necessarie | Descrizione | Registrazione di Autopilot  | Richiesta hash hardware | Annullamento della registrazione di Autopilot |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory Tenant ID    |    L Azure Active Directory ID tenant è un identificatore univoco globale (GUID) diverso dal nome o dal dominio dell'organizzazione.    Per trovare l'ID tenant accedere al [portale di Azure.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Nome di dominio    |   Nome di dominio di primo livello. ad esempio, contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Prova di proprietà    |   Verificare la verifica della proprietà caricando la fattura o la fattura originale in formato PDF. Gli screenshot non vengono accettati. La fattura o la fattura deve includere quanto segue: Numeri di serie del dispositivo. Nome della società.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Numeri di serie del dispositivo    |   Upload Excel file in formato CSV con ogni numero di serie del dispositivo in una nuova riga.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Inviare richieste di supporto

> [!div class="nextstepaction"]
> [Inviare il supporto per la registrazione di Autopilot per HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
