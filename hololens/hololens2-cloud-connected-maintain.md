---
title: Guida alla distribuzione - Distribuzione di applicazioni HoloLens 2 cloud su larga scala con Remote Assist - Manutenzione
description: È possibile rimanere sempre aggiornati con i suggerimenti per la gestione e il supporto HoloLens dispositivi su una rete connessa al cloud.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427404"
---
# <a name="maintain---cloud-connected-guide"></a>Manutenzione - Guida alla connessione al cloud

## <a name="updates"></a>Aggiornamenti

Microsoft ha progettato il servizio Windows Update for Business per fornire agli amministratori IT altre funzionalità di gestione basate su Windows Update, ad esempio la possibilità di distribuire gli aggiornamenti a gruppi di dispositivi e di definire finestre di manutenzione per l'installazione degli aggiornamenti.

Informazioni su come [gestire gli HoloLens](/hololens/hololens-updates) inclusi i giorni pianificati, l'ora pianificata e l'impostazione degli orari di attività nel dispositivo in modo che si aggiorneranno al di fuori dell'orario di lavoro.

Remote Assist è unIn-Box app e può essere aggiornato tramite l'app Microsoft Store. Per tutte le app scaricate tramite il Microsoft Store possono essere aggiornate manualmente [tramite](/hololens/holographic-store-apps#update-apps) l Microsoft Store app stessa.

## <a name="support-plan"></a>Piano di supporto

Un piano di supporto è un'ottima soluzione. È utile avere a che fare con un utente o un gruppo per la risoluzione dei problemi del processo di registrazione nei dispositivi HoloLens e anche l'uso generale del dispositivo HoloLens all'interno dell'organizzazione. Per consentire agli utenti di risolvere più rapidamente i problemi, è consigliabile che il processo di escalation sia gestito in modo simile a questo ordine:

1. Il supporto tecnico.
2. Il team HoloLens Expert
3. [HoloLens Docs](/hololens/)  /  [HoloLens risoluzione dei problemi](/hololens/hololens-troubleshooting)
4. [Contattare il supporto tecnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Piano di sviluppo

Dopo aver registrato correttamente il dispositivo, è ora possibile distribuire app line-of-business (app line-of-business) nei dispositivi. Si tratta di app personalizzate create per l'organizzazione&#39;esigenze specifiche.

Se si ha già un'app line-of-business,&#39;è possibile distribuire [l'app tramite MDM.](/hololens/app-deploy-intune) Se si&#39;un metodo diverso, vedere la panoramica della distribuzione dell'applicazione [per HoloLens 2](/hololens/app-deploy-overview) per altre informazioni sui metodi di distribuzione dell'app lob nei dispositivi.

Se non&#39;ancora creato un'app LOB o è ancora in corso la creazione, [](/windows/mixed-reality/design/design) vedere la documentazione sullo sviluppo di realtà mista per iniziare a progettare e creare prototipi o apprendere i concetti di base per iniziare a usare lo sviluppo di realtà [mista.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Gestione dei dispositivi 

Anche se questa guida ha parlato della configurazione della gestione dei dispositivi mobili (MDM), non è stata impiegata per applicare restrizioni o criteri ai dispositivi. La gestione dei dispositivi può essere usata sia per consentire l'accesso tramite il push dei certificati che per limitare l'accesso con un'ampia gamma di restrizioni dei dispositivi. 

In molti casi i dispositivi possono avere restrizioni di connettività, ad esempio Bluetooth, VPN, USB o anche disattivare l'accesso alla fotocamera o al microfono. Se uno di questi interessi è di tuo interesse, ti invitiamo a leggere la pagina [delle restrizioni dei dispositivi comuni.](hololens-common-device-restrictions.md)

Esistono altre restrizioni più complesse per i dispositivi che è possibile usare. Ad esempio:

- Limitazione delle pagine che possono essere visualizzate nell'app Impostazioni usando [SettingsPageVisibility,](settings-uri-list.md)consentendo agli utenti di accedere solo alle impostazioni necessarie per modificare, ad esempio modificando la connessione Wi-Fi connessione.
- Usare [la modalità tutto schermo](hololens-kiosk.md) per limitare l'interfaccia utente presentata agli utenti in un dispositivo. È possibile impostare Chioschi in modo che mostri una singola app o più app con una pagina iniziale personalizzata. I chioschi possono anche presentare esperienze diverse a utenti diversi.  
- [Windows controllo delle applicazioni (WDAC)](windows-defender-application-control-wdac.md) per evitare l'avvio completo di app o processi specifici.

Per altre informazioni sui diversi metodi di gestione dei dispositivi o sulle restrizioni dei dispositivi, eseguire il passaggio successivo e leggere La panoramica sulla gestione dei dispositivi.

## <a name="next-step"></a>Passaggio successivo

> [!div class="nextstepaction"]
> [Leggere la panoramica dei CSP e della gestione dei dispositivi](hololens-csp-policy-overview.md)