---
title: Guida alla distribuzione di client esterni
description: Guida alla distribuzione per HoloLens 2 per client esterni (ad esempio con Assistenza remota)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309338"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Distribuzione di HoloLens 2 a client esterni con Remote Assist

Questa guida consente ai professionisti IT con gli obiettivi seguenti di distribuire Microsoft HoloLens 2 dispositivi nell'organizzazione:

1. Cloud Connect HoloLens 2 dispositivi
1. Prestito HoloLens 2 dispositivi a client esterni per l'uso
1. Proteggere i dispositivi in prestito

Questa guida [](#general-deployment-recommendations-and-instructions) fornirà indicazioni HoloLens 2 di distribuzione generale applicabili alla maggior parte [](#common-concerns) degli scenari di distribuzione HoloLens 2 e ai problemi comuni che i clienti hanno quando distribuiscono Remote Assist per l'uso esterno.

## <a name="scenario-description"></a>Descrizione dello scenario

Ai fini di questo documento, Contoso Company vuole spedire un dispositivo HoloLens 2 allo stabilimento di un cliente esterno per un uso a breve o a lungo termine. Quando il client necessita di assistenza per i macchinari di manutenzione, il client accederà al dispositivo HoloLens 2 usando le credenziali fornite da Contoso Company e userà Remote Assist per contattare gli esperti di Contoso Company.

Altre informazioni sulle Remote Assist [qui.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Requisiti per questo scenario

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Gestione dispositivi mobili, ad esempio [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist licenza
    1. [Acquistare Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Versione di Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Problemi comuni

- [Come assicurarsi che i client esterni non siano in grado di comunicare tra loro](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Come assicurarsi che i client non hanno accesso alle risorse aziendali](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Come limitare le app](#how-to-restrict-apps)
- [Come gestire le password](#how-to-manage-passwords)
- [Come assicurarsi che i client non hanno accesso alla cronologia delle chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Come assicurarsi che i client esterni non siano in grado di comunicare tra loro

Poiché Remote Assist chiamate da HoloLens a HoloLens non sono supportate, i client sono in grado di cercare, ma non possono, comunicare tra loro. Per limitare ulteriormente gli utenti che i client possono cercare e chiamare,  [le barriere](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) di informazioni possono limitare gli utenti con cui un client può comunicare. Un'altra opzione da considerare è [l'uso della ricerca nella directory con ambito](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Poiché l'accesso Single Sign-On è abilitato, è importante disabilitare il browser usando [**WDAC.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Se un client esterno apre il browser e usa la versione Web di Teams, il client avrà accesso alla cronologia delle chiamate/chat.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Come assicurarsi che i client non hanno accesso alle risorse aziendali

È possibile prendere in considerazione due opzioni.

La prima opzione è un approccio a più livelli:

1. Assegnare solo le licenze richieste dall'utente. Se non si assegna OneDrive, Outlook, SharePoint, Yammer e così via all'utente, non avrà accesso a tali risorse. Le uniche licenze necessarie agli utenti sono Remote Assist, Intune e AAD per iniziare.
1. Bloccare le app (ad esempio la posta elettronica) a cui non si vuole che i client accedono (vedere [Come limitare le app).](#how-to-restrict-apps)
1. NON condividere nomi utente e password con i client. Per accedere al HoloLens 2, sono necessari un messaggio di posta elettronica e un PIN numerico.

La seconda opzione è creare un tenant separato che ospita i client (vedere l'immagine 1.1).

**Immagine 1.1**

![Immagine del tenant del servizio](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Come limitare le app

[La modalità tutto](https://docs.microsoft.com/hololens/hololens-kiosk) schermo e/o [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) sono opzioni per limitare le applicazioni.

### <a name="how-to-manage-passwords"></a>Come gestire le password

1. Rimuovere la scadenza della password. Tuttavia, ciò aumenta la probabilità che un account venga compromesso. La raccomandazione per le password NIST è modificare le password ogni 30-90 giorni.
1. Estendere la scadenza della password per HoloLens 2 dispositivi per superare i 90 giorni.
1. I dispositivi devono essere restituiti a Contoso per modificare le password. Tuttavia, ciò può causare problemi se si prevede che i dispositivi siano nello stabilimento del client per più di 90 giorni.  
1. Per i dispositivi inviati a più client, reimpostare le password prima di inviare il dispositivo ai client.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Come assicurarsi che i client non hanno accesso alla cronologia delle chat

Remote Assist cancella la cronologia chat dopo ogni sessione. Tuttavia, la cronologia delle chat sarà disponibile per l'utente di Microsoft Teams.

> [!NOTE]
> Poiché l'accesso Single Sign-On è abilitato, è importante disabilitare il browser usando [**WDAC.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Se un client esterno apre il browser e usa la versione Web di Teams, il client avrà accesso alla cronologia chiamate/chat.

## <a name="general-deployment-recommendations-and-instructions"></a>Indicazioni e istruzioni generali sulla distribuzione

È consigliabile seguire questa procedura per HoloLens 2 di distribuzione:

1. Usare la [versione più recente del sistema operativo HoloLens](https://aka.ms/hololens2download) come build di base.
1. Assegnare licenze basate su utente o basate su dispositivo:
    1. Entrambe le licenze basate su utenti e dispositivi seguono la procedura seguente:
        1. [Creare un gruppo in AAD e aggiungere membri per](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) gli utenti di HoloLens/RA.
        1. [Assegnare licenze basate su dispositivo o basate su utente](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a questo gruppo.
        1. (Facoltativo) È possibile specificare come destinazione i gruppi per i criteri MDM.

1. I dispositivi devono essere aggiunti ad AAD al tenant, [registrati automaticamente](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configurati tramite [la distribuzione pilota automatica.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Si noti che il primo utente del dispositivo sarà il proprietario del dispositivo.
    1. Si noti che se il dispositivo è aggiunto ad AAD, l'utente che ha eseguito l'aggiunta viene reso proprietario del dispositivo.
    1. Per altre informazioni, vedere [Proprietario del dispositivo.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [Il tenant blocca](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) il dispositivo in modo che possa essere aggiunto solo al tenant.
    1. **Collegamento aggiuntivo:** [Provider di servizi di configurazione per il blocco del tenant.](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)
1. Configurare la modalità tutto schermo usando l'accesso assegnato a livello globale [qui.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. È consigliabile disabilitare le funzionalità seguenti (facoltative):
    1. Possibilità di impostare il dispositivo in modalità sviluppatore [qui.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Possibilità di connettere HoloLens a un PC per copiare la data [disabilitando USB.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Se non si vuole disabilitare USB ma si vuole applicare un pacchetto di provisioning al dispositivo tramite USB, seguire le istruzioni elencate [**qui.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Usare [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) per consentire o bloccare le app nel HoloLens 2 dispositivo.
1. Aggiornare Remote Assist alla versione più recente come parte dell'installazione. A tale scopo, sono disponibili due opzioni:
    1. A tale scopo, accedere a Windows **Microsoft Store --> Remote Assist --> e Aggiornare l'app.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) che consente gli aggiornamenti automatici delle app, è abilitato per impostazione predefinita. Mantenere il dispositivo collegato per ricevere gli aggiornamenti.
1. [Disabilitare tutte le pagine delle](https://docs.microsoft.com/hololens/settings-uri-list) impostazioni ad eccezione delle impostazioni di rete per consentire agli utenti di connettersi alle reti guest nei siti client.
1. [Gestire gli aggiornamenti di HoloLens](https://docs.microsoft.com/hololens/hololens-updates)
    1. Opzione per [controllare gli aggiornamenti del sistema operativo](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) o consentire il flusso libero.
1. [Restrizioni comuni dei dispositivi](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).
