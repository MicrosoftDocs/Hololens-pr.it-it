---
title: Distribuire applicazioni connesse HoloLens 2 cloud a client esterni
description: Guida alla distribuzione HoloLens 2 per client esterni (con Assistenza remota come esempio)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 476ea17dfad114741191595fa0ce3bd1c7bca28d
ms.sourcegitcommit: 7b666c63a0367032a4a3f366b7f9029b2613e345
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2021
ms.locfileid: "122401134"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Distribuire applicazioni connesse HoloLens 2 cloud a client esterni

Questa guida è un supplemento alla [Guida alla distribuzione connessa al cloud.](hololens2-cloud-connected-overview.md) Viene usato nelle situazioni in cui l'organizzazione vuole spedire HoloLens 2 dispositivi alla struttura di un cliente esterno per un uso a breve o a lungo termine. Il client esterno accederà al dispositivo HoloLens 2 usando le credenziali fornite dall'organizzazione e userà Remote Assist [per](/dynamics365/mixed-reality/remote-assist/ra-overview) contattare gli esperti. Questa guida fornisce [indicazioni generali HoloLens 2](#general-deployment-recommendations) distribuzione di applicazioni che sono applicabili [](#common-external-client-deployment-concerns) alla maggior parte degli scenari di distribuzione di HoloLens 2 esterni e i problemi comuni che i clienti hanno quando distribuiscono Remote Assist per l'uso esterno. 

## <a name="prerequisites"></a>Prerequisiti

L'infrastruttura seguente deve essere presente in base alla [Guida alla](hololens2-cloud-connected-overview.md) distribuzione connessa al cloud per distribuire il HoloLens 2 esternamente.

- Azure AD aggiunta con la registrazione automatica MDM: gestita da MDM (Intune)
- Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
    - Sono supportati uno o più utenti per dispositivo.

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist licenze e requisiti

- Azure AD account (obbligatorio per l'acquisto della sottoscrizione e l'assegnazione delle licenze)
- [Remote Assist sottoscrizione](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o versione [Remote Assist valutazione)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

Vedere [Altre informazioni su Remote Assist](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist utente

- Remote Assist licenza
- Connettività di rete

### <a name="microsoft-teams-user"></a>Microsoft Teams utente

- Microsoft Teams o [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Connettività di rete

## <a name="general-deployment-recommendations"></a>Raccomandazioni generali per la distribuzione

È consigliabile seguire questa procedura per la distribuzione HoloLens 2 esterna:

1. Usare la [versione HoloLens versione del sistema operativo come](https://aka.ms/hololens2download) build di base.
1. Assegnare licenze basate su utente o su dispositivo seguendo questa procedura:
    1. [Creare un gruppo in AAD e aggiungere membri per gli](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) utenti HoloLens/RA.
    1. [Assegnare licenze basate su dispositivo o basate su utente](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a questo gruppo.
    1. (Facoltativo) Gruppi di destinazione per i criteri di gestione dei dispositivi mobili [(MDM).](hololens-enroll-mdm.md)

1. Aggiungere i dispositivi AAD al tenant, [registrare automaticamente](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configurare tramite [Autopilot.](/hololens/hololens2-autopilot) Per altre informazioni, vedere proprietario [del dispositivo.](/hololens/security-adminless-os#device-owner)
    1. Il primo utente del dispositivo sarà il proprietario del dispositivo.
    1. Se il dispositivo è aggiunto ad AAD, l'utente che ha eseguito l'aggiunta viene reso proprietario del dispositivo.
    
1. [Il tenant blocca](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) il dispositivo in modo che possa essere aggiunto solo dal tenant.
    1. Vedere anche [Provider di servizi di configurazione per il blocco del tenant.](/windows/client-management/mdm/tenantlockdown-csp)

1. [Configurare la modalità tutto schermo usando l'accesso assegnato a livello globale.](/hololens/hololens-global-assigned-access-kiosk)

1. Disabilitare le funzionalità (facoltative) seguenti:
    1. Possibilità di impostare il dispositivo in modalità sviluppatore [qui.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Possibilità di connettere il HoloLens a un PC per copiare la data [e disabilitare USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Se non si vuole disabilitare USB ma si vuole applicare un pacchetto di provisioning al dispositivo tramite USB, seguire le istruzioni su come consentire [l'installazione del pacchetto di provisioning.](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Usare [Windows Defender controllo delle applicazioni (WDAC)](/hololens/windows-defender-application-control-wdac) per consentire o bloccare le app nel HoloLens 2 dispositivo.
1. Aggiornare Remote Assist alla versione più recente come parte dell'installazione. Considerare le due opzioni seguenti:
    1. Passare a Windows **Microsoft Store --> Remote Assist --> e Aggiorna app**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) che consente gli aggiornamenti automatici delle app, è abilitato per impostazione predefinita. Mantenere il dispositivo collegato per ricevere gli aggiornamenti.
1. [Disabilitare tutte le pagine di](/hololens/settings-uri-list) impostazioni ad eccezione delle impostazioni di rete per consentire agli utenti di connettersi alle reti guest nei siti client.
1. [Gestire HoloLens aggiornamenti](/hololens/hololens-updates)
    1. Opzione per [controllare gli aggiornamenti del sistema operativo](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) o consentire il flusso libero.
1. Impostare [restrizioni comuni per i dispositivi](/hololens/hololens-common-device-restrictions).

A questo punto i client esterni sono pronti per l'uso delle HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Problemi comuni di distribuzione di client esterni

- [Garantire che i client non possano comunicare tra loro](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Garantire che i client non possano accedere alle risorse aziendali](#ensure-that-clients-wont-have-access-to-company-resources)
- [Nascondere o limitare le app](#hidden-or-restricted-apps)
- [Gestione delle password per i client](#password-management-for-your-clients) 
- [Garantire che i client non possano accedere alla cronologia delle chat](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Assicurarsi che i client esterni non possano comunicare tra loro

Remote Assist HoloLens per HoloLens chiamate non sono supportate. I client possono cercare, ma non possono comunicare tra loro. [Le barriere di informazioni Microsoft 365](/microsoft-365/compliance/information-barriers) possono limitare ulteriormente gli utenti con cui un client può eseguire ricerche e chiamate. Un'altra opzione è usare Microsoft Teams [ricerca nella directory con ambito](/MicrosoftTeams/teams-scoped-directory-search).

 > [!NOTE]
> Poiché l'accesso Single Sign-On è abilitato, è importante disabilitare il browser [usando Windows Defender Application Control (WDAC).](/hololens/windows-defender-application-control-wdac) Se un client esterno apre il browser e usa la versione Web di Teams, il client avrà accesso alla cronologia delle chat.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Assicurarsi che i client non hanno accesso alle risorse aziendali

È possibile prendere in considerazione due opzioni.

La prima opzione è un approccio a più livelli:

1. Assegnare solo le licenze richieste dall'utente. Se non si assegnano OneDrive, Outlook, SharePoint, Yammer e così via, l'utente non avrà accesso a tali risorse. Le uniche licenze necessarie per gli utenti sono Remote Assist, Intune e AAD per iniziare.
1. Bloccare le app (ad esempio la posta elettronica) a cui non si vuole che i client accedono (vedere App [nascoste o con restrizioni).](#apps are hidden or restricted)
1. Non condividere nomi utente e password con i client. Per accedere al HoloLens 2, sono necessari un messaggio di posta elettronica e un PIN numerico.

La seconda opzione è creare un tenant separato che ospita i client (vedere l'immagine 1.1).

**Immagine 1.1**

![Immagine del tenant del servizio](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>App nascoste o con restrizioni

[La modalità tutto](/hololens/hololens-kiosk) schermo e/o Windows Defender controllo delle applicazioni [(WDAC)](/hololens/windows-efender-application-control-wdac) sono opzioni per nascondere e/o limitare le applicazioni.

### <a name="password-management-for-your-clients"></a>Gestione delle password per i client

1. Rimuovere la scadenza della password. Tuttavia, questa opzione può aumentare la probabilità che un account venga compromesso. La raccomandazione per le password NIST è modificare le password ogni 30-90 giorni.
1. Estendere la scadenza della password per HoloLens 2 dispositivi in modo che superino i 90 giorni.
1. I dispositivi devono essere restituiti all'organizzazione per modificare le password. Tuttavia, questa opzione può causare problemi se si prevede che i dispositivi siano nello stabilimento del cliente per più di 90 giorni.  
1. Per i dispositivi inviati a più client, reimpostare le password prima di inviare il dispositivo ai client.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Assicurarsi che i client non hanno accesso alla cronologia delle chat

Remote Assist cancella la cronologia delle chat dopo ogni sessione. Tuttavia, la cronologia delle chat sarà disponibile per Microsoft Teams utenti.

> [!NOTE]
> Poiché l'accesso Single Sign-On è abilitato, è importante disabilitare il browser [usando Windows Defender Application Control (WDAC).](/hololens/windows-defender-application-control-wdac)  Se un client esterno apre il browser e usa la versione Web di Teams, il client avrà accesso alla cronologia delle chiamate/chat.
