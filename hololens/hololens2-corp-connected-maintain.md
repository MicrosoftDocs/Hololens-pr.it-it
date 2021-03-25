---
title: Guida alla distribuzione - HoloLens 2 connesso all'azienda con le guide di Dynamics 365 - Manutenzione
description: Informazioni su come gestire i dispositivi HoloLens 2 su una rete connessa aziendale con le guide di Dynamics 365.
keywords: HoloLens, gestione, corporate connected, Guide dynamics 365, AAD, Azure AD, MDM, Gestione dispositivi mobili
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448570"
---
# <a name="maintain---corporate-connected-guide"></a>Maintain - Guida aziendale connessa

## <a name="update-hololens"></a>Aggiornare HoloLens

Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti.

Un metodo comune per la gestione degli aggiornamenti è di eseguire un differimento delle funzionalità di 30 giorni. In questo modo gli amministratori possono aggiornare e visualizzare in anteprima le nuove funzionalità, acquisire conoscenze di prima mano e informare il supporto tecnico di eventuali nuove modifiche.

Scopri come gestire [gli aggiornamenti di HoloLens,](https://docs.microsoft.com/hololens/hololens-updates)inclusi i giorni pianificati, l'orario pianificato e l'impostazione dell'orario di attività nel dispositivo, in modo che si aggiornerà al di fuori dell'orario di lavoro.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Come aggiornare le guide di Dynamics 365 (e altre app dello Store)

Dynamics 365 Guides è un'app In-Box e può essere aggiornata tramite l'app di Microsoft Store. Per tutte le app scaricate tramite Microsoft Store, possono essere [aggiornate manualmente tramite l'app di Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) stessa.

## <a name="how-to-update-lob-apps"></a>Come aggiornare le app LOB

Le app LOB possono essere aggiornate nello stesso modo in cui sono state aggiunte a Intune. Le app possono essere aggiornate in Intune caricando la nuova app con un numero di versione superiore nella configurazione dell'app esistente. Quando il dispositivo viene sincronizzato con Intune, osserverà che esiste una versione più recente dell'app e che l'app più recente verrà scaricata e sostituirà l'app precedente.

1. Per caricare l'app più recente, passare al portale [MEM](https://endpoint.microsoft.com/#home)  ->  **Apps** -> All **apps**  ->  *TheNameOfYourApp*  ->  **Properties.**
2. Accanto a Informazioni sull'app seleziona **Modifica.**
3. Per il valore di &quot; Selezionare il file da &quot; aggiornare, selezionare il file.
4. Da qui, usa il menu di scelta rapida per aprire Esplora file e caricare la versione più recente dell'app LOB. Assicurati di includere le dipendenze in base alle esigenze.

Altre informazioni: [Distribuzione di app intune per HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Piano di sviluppo

Dopo aver registrato correttamente il dispositivo, ora sei pronto a distribuire altre app LOB nei dispositivi. Per tutta la durata di questa guida, usiamo un'app di esempio, ma è più probabile che tu voglia usare app personalizzate create per le esigenze dell'organizzazione.

Se hai già un'app LOB, sei pronto per [distribuire l'app tramite MDM.](https://docs.microsoft.com/hololens/app-deploy-intune) Se preferisci un metodo diverso, esamina la panoramica della distribuzione dell'applicazione per [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) per scoprire altri metodi di distribuzione dell'app LOB nei dispositivi.

Se devi ancora creare la tua app LOB o sei ancora in fase di creazione, leggi i documenti di sviluppo di realtà mista per iniziare a progettare e creare prototipi o scopri i concetti di base per iniziare a usare lo sviluppo di realtà [](https://docs.microsoft.com/windows/mixed-reality/design/design) mista. [](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Piano di supporto

Un piano di supporto è un'ottima cosa da avere in atto. È utile avere qualcuno o un gruppo in formazione sulla risoluzione dei problemi del processo di registrazione nei dispositivi HoloLens e sull'uso generale del dispositivo HoloLens all'interno dell'organizzazione. Per consentire agli utenti di ottenere una risoluzione più rapida dei problemi, è consigliabile che il processo di escalation sia gestito in modo simile a questo ordine:

1. Il supporto tecnico.
2. Il team holoLens Expert
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Supporto tecnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Gestione dispositivi

Questa guida ha parlato della configurazione di Gestione di dispositivi mobili (MDM) e l'ha usata per configurare alcune configurazioni dei dispositivi e applicare le impostazioni per consentire l'accesso in termini di certificati Wi-Fi e proxy. Tuttavia, MDM può essere usato anche per applicare restrizioni per i dispositivi tramite CSP e criteri.

In molti casi, i dispositivi possono avere restrizioni di connettività, ad esempio Bluetooth, VPN, USB o anche disattivare l'accesso alla fotocamera o al microfono. Se uno di questi interessi ti interessa, ti invitiamo a leggere la nostra [pagina delle restrizioni comuni per i dispositivi.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

Esistono altre restrizioni più complesse per i dispositivi che puoi usare. Ad esempio:

- Limitando le pagine che possono essere visualizzate nell'app Impostazioni usando [SettingsPageVisibility,](https://docs.microsoft.com/hololens/settings-uri-list)consentendo agli utenti di accedere solo alle impostazioni che devono modificare, ad esempio modificando la connessione Wi-Fi connessione.
- Usa [la modalità tutto](https://docs.microsoft.com/hololens/hololens-kiosk) schermo per limitare l'interfaccia utente presentata agli utenti in un dispositivo. Puoi impostare Chioschi in modo che mostri una singola app o più app con una pagina iniziale personalizzata. I chioschi multimediale possono inoltre presentare esperienze diverse a utenti diversi.
- [Windows Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) per evitare che app o processi specifici si avviano completamente.

Se vuoi informazioni sui metodi aggiuntivi di gestione dei dispositivi o sulle restrizioni dei dispositivi, fai il passaggio successivo e leggi la panoramica [di Gestione dispositivi](https://docs.microsoft.com/hololens/hololens-csp-policy-overview).





