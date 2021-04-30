---
title: Intune e Portale aziendale
description: Informazioni su come configurare, assegnare e creare un'esperienza utente comoda con Intune, la gestione dei dispositivi mobili e il portale aziendale.
keywords: intune, gestione delle app, app, portale aziendale, portale, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309732"
---
# <a name="intune--company-portal"></a>Intune & Portale aziendale

Con Gestione dispositivi mobili è possibile usare le proprie app personalizzate tramite [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) per distribuirla direttamente nei dispositivi HoloLens. Microsoft Intune è un servizio basato sul cloud incentrato sulla gestione di dispositivi mobili (MDM, Mobile Device Management) e sulla gestione di applicazioni mobili (MAM, Mobile Application Management). Intune è incluso nella [suite Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) di Microsoft e consente agli utenti di essere produttivi garantendo al tempo stesso la protezione dei dati dell'organizzazione. Per altre informazioni su Intune, vedere [Informazioni su Intune.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Configurazione

1. Caricare un'app in una line-of-business o caricare un'app personalizzata nel tenant di Intune. Vedere anche: [Gestione delle app aziendali.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)

2. [Assegnare l'app a un gruppo](https://docs.microsoft.com/mem/intune/apps/apps-deploy). In base al tipo di assegnazione scelto, l'app può essere recapitata automaticamente o disponibile per essere prontamente ritirata se si dispone di una selezione di app.

> [!NOTE]
> Quando si compila il bundle appx, assicurarsi di includere l'architettura per i dispositivi in cui si esegue la distribuzione. HoloLens 2 è ARM64 e HoloLens (prima generazione) è x86. È possibile includere entrambi in un singolo bundle appx se si prevede di avere un ambiente con dispositivi misti.

## <a name="assignment-types"></a>Tipi di assegnazione

Per fare in modo che l'app sia installata automaticamente nel dispositivo dopo la registrazione, è necessario selezionare **Obbligatorio** per i gruppi.
Per rendere disponibile l'app per il download nei dispositivi registrati tramite il portale aziendale, selezionare **Disponibile per i dispositivi registrati.**

## <a name="end-user-experience"></a>Esperienza dell'utente finale

Dopo aver configurato la configurazione in Intune, si è pronti per consentire agli utenti finali di ricevere le app selezionate.

Seguire questa procedura per ottenere automaticamente le app:

1. Registrare il dispositivo con il tenant.
2. Al termine della registrazione del dispositivo, si dovrebbe ricevere l'app nel dispositivo.
3. Se l'app non viene visualizzata immediatamente, passare a Impostazioni Account aziendali o dell'istituto di istruzione Informazioni sull'account e scorrere verso il basso per visualizzare informazioni sullo  >    >    >   stato dell'app installata.

Come accedere alle app tramite il Portale aziendale:

1. Aprire il **menu Start e** selezionare **Microsoft Store**.
2. Cercare **Portale aziendale** e scaricare l'app.
3. Accedere al proprio account.
4. Selezionare l'app che si vuole ricevere e scaricarla.

> [!Tip]
> Altre informazioni [sull'installazione automatica del Portale aziendale](https://docs.microsoft.com/mem/intune/apps/company-portal-app) distribuzione e gestione delle app in [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
