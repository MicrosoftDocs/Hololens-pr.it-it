---
title: Intune e portale aziendale
description: Intune, gestione app, app, portale aziendale, portale
keywords: Intune, gestione app, app, portale aziendale, portale, hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: 5fc369caa2e5e26c91c07f9270c3984177507dbd
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009464"
---
# Portale aziendale Intune

Con la gestione di dispositivi mobili (MDM), puoi usare le tue app personalizzate tramite [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) per distribuirlo direttamente nei dispositivi HoloLens. Microsoft Intune è un servizio basato su cloud che si occupa di gestione di dispositivi mobili (MDM) e gestione di applicazioni mobili (MAM). Intune è incluso nella[famiglia Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)di Microsoft e consente agli utenti di essere produttivi mantenendo i dati dell'organizzazione protetti. Per altre informazioni su Intune, leggere il contenuto di [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).

## Installazione

1. Caricare un'app in una riga di business o caricare un'app personalizzata nel tenant di Intune. Vedere anche: [gestione delle app Enterprise](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Assegna la tua app a un gruppo](https://docs.microsoft.com/mem/intune/apps/apps-deploy). In base al tipo di assegnazione che scegli puoi far recapitare l'app automaticamente o disponibile per essere facilmente abbattute se hai una selezione di app. 

> [!NOTE] 
> Quando crei il tuo bundle appx, assicurati di includere l'architettura per il dispositivo o i dispositivi a cui stai distribuendo. HoloLens 2 è ARM64 e HoloLens (1a generazione) è x86. Se si prevede di avere un ambiente con dispositivi misti, è possibile includere sia in un singolo bundle di appx.

## Tipi di assegnazione

Se preferisci che la tua app sia installata automaticamente nel dispositivo dopo l'iscrizione, devi selezionare **obbligatoria** per i gruppi.
Se preferisci rendere la tua app disponibile per il download a quelle iscritte nel portale aziendale, seleziona **disponibile per i dispositivi registrati**.


## Esperienza utente finale

Dopo aver configurato la configurazione su Intune, è possibile che gli utenti finali ricevano le app selezionate.

Seguire questa procedura per ottenere automaticamente le app:
1. Registrare il dispositivo con il tenant. 
2. Una volta che il dispositivo ha completato la registrazione, dovresti ricevere l'app nel dispositivo. 
3. Se l'app non viene visualizzata immediatamente, passare a account **delle impostazioni**  >  **Accounts**  >  **o a School**  >  **paginaaccount** info e scorrere verso il basso per visualizzare le informazioni sullo stato dell'app installata.

Come passare alle app attraverso il portale aziendale:
1. Aprire il **menu Start** e selezionare **Microsoft Store**. 
2. Cercare il **portale aziendale** e scaricare l'app.
3. Accedere al proprio account.
4. Selezionare l'app che si vuole ricevere e scaricarla.

> [!Tip]
> Leggi altre informazioni su come [installare automaticamente il portale aziendale](https://docs.microsoft.com/mem/intune/apps/company-portal-app) e [distribuire e gestire le app in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
