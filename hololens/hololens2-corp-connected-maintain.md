---
title: Guida alla distribuzione - Connessione aziendale HoloLens 2 con Dynamics 365 Guides - Manutenzione
description: Informazioni su come gestire HoloLens 2 dispositivi su una rete connessa aziendale con Dynamics 365 Guides.
keywords: HoloLens, gestione, aziendale connessa, Dynamics 365 Guides, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636997"
---
# <a name="maintain---corporate-connected-guide"></a>Manutenzione - Guida connessa aziendale

## <a name="update-hololens"></a>Aggiornare HoloLens

Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti.

Un metodo comune per la gestione degli aggiornamenti è quello di eseguire un rinvio delle funzionalità di 30 giorni. In questo modo gli amministratori possono aggiornare e visualizzare in anteprima le nuove funzionalità, acquisire informazioni di prima mano e informare il supporto tecnico di eventuali nuove modifiche.

Informazioni su come [gestire HoloLens](/hololens/hololens-updates)aggiornamenti, inclusi i giorni pianificati, l'ora pianificata e l'impostazione degli orari di attività nel dispositivo, in modo che si aggiornerà al di fuori dell'orario di lavoro.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Come aggiornare i Dynamics 365 Guides (e altre app dello Store)

Dynamics 365 Guides è un'app In-Box e può essere aggiornata tramite l Microsoft Store app. Per tutte le app scaricate tramite il Microsoft Store, possono essere [aggiornate](/hololens/holographic-store-apps#update-apps) tramite l'app Microsoft Store app stessa manualmente.

## <a name="how-to-update-lob-apps"></a>Come aggiornare le app LOB

Le app LOB possono essere aggiornate nello stesso modo in cui sono state aggiunte a Intune. Le app possono essere aggiornate in Intune caricando la nuova app con un numero di versione più alto nella configurazione dell'app esistente. Quando il dispositivo viene sincronizzato con Intune, si osserverà che è disponibile una versione più recente dell'app e che l'app più recente verrà scaricata e sostituita dall'app precedente.

1. Per caricare l'app più recente, passare al portale [MEM](https://endpoint.microsoft.com/#home)  ->  **Apps** -> All **apps** TheNameOfYourApp Properties (App MEM -> Proprietà  ->  *TheNameOfYourApp).*  ->  
2. Accanto a Informazioni sull'app selezionare **Modifica.**
3. Per il valore Selezionare &quot; il file da &quot; aggiornare, selezionare il file.
4. Da qui usare il menu di scelta rapida per aprire Esplora file e caricare la versione più recente dell'app LOB. Assicurarsi di includere le dipendenze in base alle esigenze.

Vedere altre informazioni: [Distribuzione di app di Intune per HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Piano di sviluppo

Dopo aver registrato correttamente il dispositivo, si è ora pronti per distribuire altre app LOB nei dispositivi. Per tutta la durata di questa guida si usa un'app di esempio, ma è più probabile che si vogliano usare app personalizzate create in base alle esigenze dell'organizzazione.

Se si ha già un'app LOB, si è pronti per [distribuire l'app tramite MDM.](/hololens/app-deploy-intune) Se si preferisce un metodo diverso, vedere la panoramica della distribuzione dell'applicazione [HoloLens 2](/hololens/app-deploy-overview) per altre informazioni sui metodi di distribuzione dell'app LOB nei dispositivi.

Se è ancora necessario creare un'app LOB o si è ancora in fase di [](/windows/mixed-reality/design/design) creazione, vedere la documentazione sullo sviluppo di realtà mista per iniziare a progettare e creare prototipi o apprendere i concetti di base per iniziare a usare lo sviluppo di realtà [mista.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Piano di supporto

Un piano di supporto è una cosa eccellente da avere in atto. È utile avere un utente o un gruppo per la risoluzione dei problemi del processo di registrazione nei dispositivi HoloLens e anche l'uso generale del dispositivo HoloLens all'interno dell'organizzazione. Per consentire agli utenti di ottenere la risoluzione più rapida dei problemi, è consigliabile che il processo di escalation sia gestito in modo simile a questo ordine:

1. Il supporto tecnico.
2. Il team HoloLens Expert
3. [HoloLens Docs](/hololens/)  /  [HoloLens Risoluzione dei problemi relativi a Docs](/hololens/hololens-troubleshooting)
4. [Contattare il supporto tecnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Gestione dei dispositivi

Questa guida ha parlato della configurazione di Gestione dispositivi mobili (MDM) e l'ha usata per configurare alcune configurazioni dei dispositivi e applicare le impostazioni per consentire l'accesso in termini di certificati Wi-Fi e proxy. È tuttavia possibile usare MDM anche per applicare restrizioni ai dispositivi tramite CSP e criteri.

In molti casi, i dispositivi possono avere restrizioni di connettività, ad esempio Bluetooth, VPN, USB o persino disattivare l'accesso alla fotocamera o al microfono. Se uno di questi elementi è di tuo interesse, ti invitiamo a leggere la pagina delle restrizioni [dei dispositivi comuni](/hololens/hololens-common-device-restrictions).

Esistono altre restrizioni dei dispositivi più complesse che è possibile usare. Ad esempio:

- Limitazione delle pagine che possono essere visualizzate nell'app Impostazioni usando [SettingsPageVisibility](/hololens/settings-uri-list), consentendo agli utenti di accedere solo alle impostazioni che devono modificare, ad esempio modificando la connessione Wi-Fi connessione.
- Usare [la modalità tutto schermo](/hololens/hololens-kiosk) per limitare l'interfaccia utente presentata agli utenti in un dispositivo. È possibile impostare Chioschi in modo che mostri una singola app o più app con una pagina iniziale personalizzata. I chioschi in modalità tutto schermo possono anche presentare esperienze diverse a utenti diversi.
- [Windows controllo delle applicazioni (WDAC)](/hololens/windows-defender-application-control-wdac) per evitare l'avvio di app o processi specifici.

Per altre informazioni sui metodi aggiuntivi di gestione dei dispositivi o sulle restrizioni dei dispositivi, eseguire il passaggio successivo e leggere Panoramica [di Gestione dispositivi](/hololens/hololens-csp-policy-overview).





