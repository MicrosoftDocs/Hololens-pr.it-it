---
title: Guida alla distribuzione-cloud connected HoloLens 2 distribuzione in scala con assistenza remota-Mantieni
description: Tieniti aggiornato sui suggerimenti per il mantenimento e il supporto dei dispositivi HoloLens su una rete connessa al cloud.
keywords: HoloLens, gestione, cloud connected, Remote Assist, AAD, Azure AD, MDM, gestione di dispositivi mobili
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283897"
---
# Manutenzione-guida connessa al cloud

## Aggiornamenti

Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti.

Informazioni su come [gestire gli aggiornamenti di HoloLens](https://docs.microsoft.com/hololens/hololens-updates) , inclusi i giorni pianificati, l'ora pianificata e l'impostazione di ore attive nel dispositivo in modo che venga aggiornato al di fuori delle ore lavorative.

L'assistenza remota è un'app In-Box e può essere aggiornata tramite l'app Microsoft Store. Per tutte le app scaricate tramite Microsoft Store, è possibile [aggiornarle manualmente tramite l'app Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) .

## Piano di supporto

Un piano di supporto è un'ottima cosa da avere in posizione. È utile avere un utente o un gruppo addestrato alla risoluzione dei problemi del processo di registrazione sui dispositivi HoloLens e anche l'uso generale del dispositivo HoloLens all'interno dell'organizzazione. Per consentire agli utenti di avere la risoluzione più rapida dei loro problemi, suggeriamo che il processo di escalation venga gestito in modo simile a questo ordine:

1. Supporto tecnico.
2. Il team di esperti di HoloLens
3. [Documenti](https://docs.microsoft.com/hololens/)  /  di HoloLens [Risoluzione dei problemi di HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Supporto tecnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## Piano di sviluppo

Con il dispositivo registrato correttamente, ora sei pronto per distribuire le app line of business (app LOB) ai tuoi dispositivi. Queste sono app personalizzate create per le esigenze dell'organizzazione&#39;s.

Se hai già un'app line of business, puoi&#39;pronta a [distribuire la tua app tramite MDM](https://docs.microsoft.com/hololens/app-deploy-intune). Se si&#39;d preferisce un metodo diverso, rivedere la [Panoramica della distribuzione dell'applicazione per HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) per ottenere altri metodi di distribuzione dell'app LOB nei dispositivi.

Se si&#39;ancora per creare una propria app line-of-business o ancora in fase di creazione, rivedere i documenti di sviluppo di realtà mista per [iniziare a progettare e prototipare](https://docs.microsoft.com/windows/mixed-reality/design/design) o imparare i concetti fondamentali per iniziare a [sviluppare una realtà mista.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## Gestione dispositivi 

Mentre questa guida ha parlato della configurazione di gestione di dispositivi mobili (MDM), non è stato usato per applicare le restrizioni dei dispositivi o i criteri sono stati applicati alle periferiche. La gestione dei dispositivi può essere usata sia per consentire l'accesso premendo i certificati o limitare l'accesso con una varietà di restrizioni per i dispositivi. 

In molti casi i dispositivi possono avere restrizioni di connettività come Bluetooth, VPN, USB o disattivazione dell'accesso alla videocamera o al microfono. Se uno di questi interessi ti interessa, ti invitiamo a leggere la [pagina delle restrizioni dei dispositivi comuni](hololens-common-device-restrictions.md).

Ci sono altre restrizioni di dispositivi più complesse che puoi usare. Ad esempio:

- Limitare le pagine che possono essere visualizzate nell'app impostazioni usando [SettingsPageVisibility](settings-uri-list.md), consentendo agli utenti di accedere solo alle impostazioni necessarie per modificare la connessione Wi-Fi.
- Usa la [modalità Kiosk](hololens-kiosk.md) per limitare l'interfaccia utente presentata agli utenti in un dispositivo. Puoi impostare i chioschi per mostrare una singola app o più app con una pagina iniziale personalizzata. I chioschi possono anche presentare esperienze diverse a utenti diversi.  
- [Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) per consentire l'avvio totale di app o processi specifici.

Per informazioni sui metodi più diversi per la gestione di dispositivi o le restrizioni dei dispositivi, eseguire il passaggio successivo e leggere la panoramica sulla gestione di dispositivi.

## Passaggio successivo

> [!div class="nextstepaction"]
> [Leggere i DSN e la panoramica sulla gestione dei dispositivi](hololens-csp-policy-overview.md)