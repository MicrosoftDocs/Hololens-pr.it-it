---
title: Guida alla distribuzione - Distribuzione HoloLens 2 cloud su larga scala con Remote Assist - Manutenzione
description: Rimanere aggiornati con i suggerimenti per la gestione e il supporto HoloLens dispositivi su una rete connessa al cloud.
keywords: HoloLens, gestione, connessa al cloud, Remote Assist, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033527"
---
# <a name="maintain---cloud-connected-guide"></a>Manutenzione - Guida connessa al cloud

## <a name="updates"></a>Aggiornamenti

Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti.

Informazioni su come [gestire HoloLens](/hololens/hololens-updates) aggiornamenti, inclusi i giorni pianificati, l'ora pianificata e l'impostazione delle ore attive nel dispositivo in modo che si aggiorneranno al di fuori dell'orario di lavoro.

Remote Assist è un'app In-Box e può essere aggiornato tramite l Microsoft Store app. Per tutte le app scaricate tramite il Microsoft Store possono essere aggiornate manualmente [tramite](/hololens/holographic-store-apps#update-apps) l Microsoft Store app stessa.

## <a name="support-plan"></a>Piano di supporto

Un piano di supporto è una cosa eccellente da avere in atto. La formazione di un utente o di un gruppo per la risoluzione dei problemi del processo di registrazione nei dispositivi HoloLens e l'uso generale del dispositivo HoloLens all'interno dell'organizzazione è utile. Per consentire agli utenti di ottenere la risoluzione più rapida dei problemi, è consigliabile che il processo di escalation sia gestito in modo simile a questo ordine:

1. Il supporto tecnico.
2. Il team HoloLens Expert
3. [HoloLens Docs](/hololens/)  /  [HoloLens Risoluzione dei problemi relativi a Docs](/hololens/hololens-troubleshooting)
4. [Contattare il supporto tecnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Piano di sviluppo

Dopo aver registrato correttamente il dispositivo, si è ora pronti per distribuire app line-of-business (app line-of-business) nei dispositivi. Si tratta di app personalizzate create per l'organizzazione&#39;esigenze.

Se si ha già un'app line-of-business,&#39;è possibile distribuire [l'app tramite MDM.](/hololens/app-deploy-intune) Se si&#39;un metodo diverso, vedere la panoramica della distribuzione dell'applicazione [per HoloLens 2](/hololens/app-deploy-overview) per altre informazioni sui metodi di distribuzione dell'app LOB nei dispositivi.

Se si&#39;creare un'app LOB o si è ancora in fase di creazione, [](/windows/mixed-reality/design/design) vedere la documentazione sullo sviluppo di realtà mista per iniziare a progettare e creare prototipi o apprendere i concetti di base per iniziare a usare lo sviluppo di realtà [mista.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Gestione dei dispositivi 

Anche se questa guida ha parlato della configurazione di Gestione dispositivi mobili (MDM), non è stata utilizzata per applicare restrizioni o criteri ai dispositivi. La gestione dei dispositivi può essere usata per consentire l'accesso tramite push dei certificati o limitare l'accesso con un'ampia gamma di restrizioni dei dispositivi. 

In molti casi i dispositivi possono avere restrizioni di connettività, ad esempio Bluetooth, VPN, USB o persino disattivare l'accesso alla fotocamera o al microfono. Se uno di questi interessi interessa l'utente, si consiglia di leggere la pagina [delle restrizioni dei dispositivi comuni](hololens-common-device-restrictions.md).

Esistono altre restrizioni dei dispositivi più complesse che è possibile usare. Ad esempio:

- Limitazione delle pagine che possono essere visualizzate nell'app Impostazioni usando [SettingsPageVisibility](settings-uri-list.md), consentendo agli utenti di accedere solo alle impostazioni che devono modificare, ad esempio modificando la Wi-Fi connessione.
- Usare [la modalità tutto](hololens-kiosk.md) schermo per limitare l'interfaccia utente presentata agli utenti in un dispositivo. È possibile impostare Chioschi in modo che mostri una singola app o più app con una pagina iniziale personalizzata. I chioschi in modalità tutto schermo possono anche presentare esperienze diverse a utenti diversi.  
- [Windows controllo delle applicazioni (WDAC)](windows-defender-application-control-wdac.md) per evitare l'avvio di app o processi specifici.

Per altre informazioni sui metodi più diversi di gestione dei dispositivi o sulle restrizioni dei dispositivi, eseguire il passaggio successivo e leggere Panoramica di Gestione dispositivi.

## <a name="next-step"></a>Passaggio successivo

> [!div class="nextstepaction"]
> [Leggere la panoramica dei CSP e della gestione dei dispositivi](hololens-csp-policy-overview.md)