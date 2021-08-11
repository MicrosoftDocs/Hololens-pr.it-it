---
title: Guida alla distribuzione - Connessione aziendale HoloLens 2 con Dynamics 365 Guides - Manutenzione
description: Informazioni su come gestire i HoloLens 2 su una rete connessa aziendale con Dynamics 365 Guides.
keywords: HoloLens, gestione, aziendale connesso, Dynamics 365 Guides, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.openlocfilehash: 2649e370e98747562591c031b8ae262674c831e071f4ef228557dda66d2dc768
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660264"
---
# <a name="maintain---corporate-connected-guide"></a>Manutenzione - Guida alla connessione aziendale

## <a name="update-hololens"></a>Aggiornare HoloLens

Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti.

Un metodo comune per la gestione degli aggiornamenti è quello di eseguire un rinvio delle funzionalità di 30 giorni. In questo modo gli amministratori possono aggiornare e visualizzare in anteprima le nuove funzionalità, acquisire conoscenze di prima mano e informare il supporto tecnico di eventuali nuove modifiche.

Informazioni su come [gestire gli HoloLens,](/hololens/hololens-updates)inclusi i giorni pianificati, l'ora pianificata e l'impostazione degli orari di attività nel dispositivo, in modo che si aggiornerà al di fuori dell'orario lavorativo.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Come aggiornare i Dynamics 365 Guides (e altre app dello Store)

Dynamics 365 Guides è un'app In-Box e può essere aggiornata tramite l'app Microsoft Store app. Per tutte le app scaricate tramite il Microsoft Store, possono essere aggiornate manualmente [tramite](/hololens/holographic-store-apps#update-apps) l Microsoft Store app stessa.

## <a name="how-to-update-lob-apps"></a>Come aggiornare le app lob

Le app lob possono essere aggiornate nello stesso modo in cui sono state aggiunte a Intune. Le app possono essere aggiornate in Intune caricando la nuova app con un numero di versione superiore nella configurazione dell'app esistente. Quando il dispositivo viene sincronizzato con Intune, si osserverà che è disponibile una versione più recente dell'app e che l'app più recente verrà scaricata e sostituita dall'app precedente.

1. Per caricare l'app più recente, passare al portale MEM Apps -> All apps TheNameOfYourApp Properties (App [MEM](https://endpoint.microsoft.com/#home)-> Tutte le app  ->     ->  *TheNameOfYourApp*  ->  **Properties).**
2. Accanto a Informazioni sull'app selezionare **Modifica.**
3. Per il valore Selezionare &quot; il file da &quot; aggiornare, selezionare il file.
4. A questo punto, usare il menu di scelta rapida per aprire Esplora file e caricare la versione più recente dell'app LOB. Assicurarsi di includere le dipendenze in base alle esigenze.

Vedere altre informazioni: [Distribuzione di app di Intune per HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Piano di sviluppo

Dopo aver registrato correttamente il dispositivo, si è pronti per distribuire più app LOB nei dispositivi. Per la durata di questa guida si userà un'app di esempio, ma è più probabile che si vogliano usare app personalizzate create per le esigenze dell'organizzazione.

Se si ha già un'app LOB, si è pronti per distribuire [l'app tramite MDM.](/hololens/app-deploy-intune) Se si preferisce un metodo diverso, vedere la panoramica della distribuzione dell'applicazione [per HoloLens 2](/hololens/app-deploy-overview) per altre informazioni sui metodi di distribuzione dell'app loB nei dispositivi.

Se non hai ancora creato un'app LOB o sei ancora in fase di creazione, consulta la documentazione sullo sviluppo di realtà mista per iniziare a progettare e creare prototipi o apprendere i concetti di base per iniziare a usare lo sviluppo di realtà [](/windows/mixed-reality/design/design) mista. [](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Piano di supporto

Un piano di supporto è un'ottima soluzione. È utile disporre di un utente o di un gruppo per la risoluzione dei problemi del processo di registrazione nei dispositivi HoloLens e anche dell'uso generale del dispositivo HoloLens all'interno dell'organizzazione. Per consentire agli utenti di risolvere più rapidamente i problemi, è consigliabile che il processo di escalation sia gestito in modo simile a questo ordine:

1. Il supporto tecnico.
2. Il team HoloLens Expert
3. [HoloLens Docs](/hololens/)  /  [HoloLens risoluzione dei problemi](/hololens/hololens-troubleshooting)
4. [Contattare il supporto tecnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Gestione dei dispositivi

In questa guida è stata trattata la configurazione della gestione dei dispositivi mobili (MDM) e la si è usata per configurare alcune configurazioni dei dispositivi e applicare le impostazioni per consentire l'accesso in termini di certificati Wi-Fi e proxy. È tuttavia possibile usare MDM anche per applicare le restrizioni dei dispositivi tramite CSP e criteri.

In molti casi, i dispositivi possono avere restrizioni di connettività, ad esempio Bluetooth, VPN, USB o anche disattivare l'accesso alla fotocamera o al microfono. Se uno di questi è di tuo interesse, ti invitiamo a leggere la pagina delle restrizioni [comuni per i dispositivi.](/hololens/hololens-common-device-restrictions)

Esistono altre restrizioni più complesse per i dispositivi che è possibile usare. Ad esempio:

- Limitazione delle pagine che possono essere visualizzate nell'app Impostazioni tramite [SettingsPageVisibility](/hololens/settings-uri-list), consentendo agli utenti di accedere solo alle impostazioni che devono modificare, ad esempio modificando la connessione Wi-Fi appliazione.
- Usare [la modalità tutto schermo](/hololens/hololens-kiosk) per limitare l'interfaccia utente presentata agli utenti in un dispositivo. È possibile impostare Chioschi in modo che mostri una singola app o più app con una pagina iniziale personalizzata. I chioschi possono anche presentare esperienze diverse a utenti diversi.
- [Windows controllo delle applicazioni (WDAC)](/hololens/windows-defender-application-control-wdac) per evitare l'avvio completo di app o processi specifici.

Per altre informazioni sui metodi aggiuntivi di gestione dei dispositivi o sulle restrizioni dei dispositivi, eseguire il passaggio successivo e leggere Panoramica [di Gestione dei dispositivi.](/hololens/hololens-csp-policy-overview)





