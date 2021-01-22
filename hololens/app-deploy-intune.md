---
title: Intune e portale aziendale
description: Informazioni su come configurare, assegnare e creare un'esperienza utente comoda con Intune, gestione di dispositivi mobili e il portale aziendale.
keywords: Intune, gestione app, app, portale aziendale, portale, hololens
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283717"
---
# Portale aziendale Intune

Con la gestione di dispositivi mobili (MDM), puoi usare le tue app personalizzate tramite [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) per distribuirlo direttamente nei dispositivi HoloLens. Microsoft Intune è un servizio basato su cloud che si occupa di gestione di dispositivi mobili (MDM) e gestione di applicazioni mobili (MAM). Intune è incluso nella [famiglia Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)di Microsoft e consente agli utenti di essere produttivi mantenendo i dati dell'organizzazione protetti. Per altre informazioni su Intune, vedere [che cos'è Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).

## Installazione

1. Caricare un'app in una riga di business o caricare un'app personalizzata nel tenant di Intune. Vedere anche: [gestione delle app Enterprise](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Assegna la tua app a un gruppo](https://docs.microsoft.com/mem/intune/apps/apps-deploy). In base al tipo di attività che scegli, l'app può essere recapitata automaticamente o disponibile per essere facilmente abbattute se hai una selezione di app.

> [!NOTE]
> Quando crei il tuo bundle appx, assicurati di includere l'architettura per il dispositivo o i dispositivi a cui stai distribuendo. HoloLens 2 è ARM64 e HoloLens (1a generazione) è x86. Se si prevede di avere un ambiente con dispositivi misti, è possibile includere sia in un singolo bundle di appx.

## Tipi di assegnazione

Per installare automaticamente la tua app nel dispositivo dopo la registrazione, devi selezionare **obbligatoria** per i gruppi...
Per rendere la tua app disponibile per il download nei dispositivi registrati tramite il portale aziendale, seleziona **disponibile per i dispositivi registrati**.

## End-User esperienza

Dopo aver configurato la configurazione in Intune, si è pronti per gli utenti finali a ricevere le app selezionate.

Seguire questa procedura per ottenere automaticamente le app:

1. Registrare il dispositivo con il tenant.
2. Una volta che il dispositivo ha completato la registrazione, dovresti ricevere l'app nel dispositivo.
3. Se l'app non viene visualizzata immediatamente, passare a account **delle impostazioni**  >  ****  >  **o a scuola**  >  *le informazioni dell'account* e scorrere verso il basso per visualizzare le informazioni sullo stato dell'app installata.

Come passare alle app attraverso il portale aziendale:

1. Aprire il **menu Start** e selezionare **Microsoft Store**.
2. Cercare il **portale aziendale** e scaricare l'app.
3. Accedere al proprio account.
4. Selezionare l'app che si vuole ricevere e scaricarla.

> [!Tip]
> Leggi altre informazioni su come [installare automaticamente il portale aziendale](https://docs.microsoft.com/mem/intune/apps/company-portal-app) e [distribuire e gestire le app in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
