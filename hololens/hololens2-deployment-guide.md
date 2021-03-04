---
title: Guida alla distribuzione di client esterni
description: Guida alla distribuzione di HoloLens 2 per client esterni (con assistenza remota come esempio)
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
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385592"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Distribuzione di HoloLens 2 a client esterni con assistenza remota

Questa guida consente ai professionisti IT con gli obiettivi seguenti di distribuire i dispositivi Microsoft HoloLens 2 nell'organizzazione:

1. Cloud connect HoloLens 2 devices
1. Prestito di dispositivi HoloLens 2 a client esterni per l'uso
1. Proteggere i dispositivi in prestito

Questa guida fornirà consigli generali sulla distribuzione di [HoloLens 2](#general-deployment-recommendations-and-instructions) applicabili alla [](#common-concerns) maggior parte degli scenari di distribuzione di HoloLens 2 e problemi comuni che i clienti hanno quando distribuiscono Assistenza remota per uso esterno.

## <a name="scenario-description"></a>Descrizione scenario

Ai fini di questo documento, la società Contoso desidera spedire un dispositivo HoloLens 2 alla centrale di un cliente esterno per un uso a breve o a lungo termine. Quando il client necessita di assistenza per i computer di manutenzione, il client accederà al dispositivo HoloLens 2 utilizzando le credenziali fornite dalla società Contoso e utilizzerà Assistenza remota per contattare gli esperti della società Contoso.

Altre informazioni su Assistenza remota [sono qui.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Requisiti per questo scenario

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Gestione dispositivi mobili, ad esempio [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Licenza di Remote Assist
    1. [Acquistare Assistenza remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Assistenza remota di prova](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Problemi comuni

- [Come assicurarsi che i client esterni non siano in grado di comunicare tra loro](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Come assicurarsi che i client non hanno accesso alle risorse aziendali](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Come limitare le app](#how-to-restrict-apps)
- [Come gestire le password](#how-to-manage-passwords)
- [Come assicurarsi che i client non siano in grado di accedere alla cronologia chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Come assicurarsi che i client esterni non siano in grado di comunicare tra loro

Poiché le chiamate da HoloLens ad HoloLens di Assistenza remota non sono supportate, i client sono in grado di cercare, ma non di comunicare tra loro. Per limitare ulteriormente gli utenti che i client possono cercare e chiamare,  [le barriere](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) delle informazioni possono limitare gli utenti con cui un client può comunicare. Un'altra opzione da considerare è [l'utilizzo della ricerca nella directory con ambito](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Poiché l'accesso Single #A0 è abilitato, è importante disabilitare il browser tramite [**WDAC.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Se un client esterno apre il browser e usa la versione Web di Teams, il client avrà accesso alla cronologia delle chiamate/chat.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Come assicurarsi che i client non hanno accesso alle risorse aziendali

Esistono due opzioni da considerare.

La prima opzione è un approccio multistrato:

1. Assegnare solo le licenze richieste dall'utente. Se non si assegna OneDrive, Outlook, SharePoint, Yammer e così via all'utente, non avrà accesso a tali risorse. Le uniche licenze necessarie agli utenti sono Assistenza remota, Intune e AAD per iniziare.
1. Bloccare le app (ad esempio la posta elettronica) a cui non si desidera consentire l'accesso dei client (vedere [Come limitare le app).](#how-to-restrict-apps)
1. NON condividere nomi utente e password con i client. Per accedere a HoloLens 2, sono necessari un messaggio di posta elettronica e un PIN numerico.

La seconda opzione è creare un tenant separato che ospita i client (vedere l'immagine 1.1).

**Immagine 1.1**

![Immagine del tenant del servizio](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Come limitare le app

[La modalità tutto](https://docs.microsoft.com/hololens/hololens-kiosk) schermo e/o [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) sono opzioni per limitare le applicazioni.

### <a name="how-to-manage-passwords"></a>Come gestire le password

1. Rimuovere la scadenza della password. Tuttavia, ciò aumenta la probabilità che un account venga compromesso. Il suggerimento per le password NIST è modificare le password ogni 30-90 giorni.
1. Estendere la scadenza della password per i dispositivi HoloLens 2 per superare i 90 giorni.
1. I dispositivi devono essere restituiti a Contoso per cambiare le password. Tuttavia, ciò può causare problemi se si prevede che i dispositivi siano nella centrale del client per oltre 90 giorni.  
1. Per i dispositivi inviati a più client, reimpostare le password prima di inviare il dispositivo ai client.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Come assicurarsi che i client non siano in grado di accedere alla cronologia chat

Assistenza remota cancella la cronologia chat dopo ogni sessione. Tuttavia, la cronologia delle chat sarà disponibile per l'utente di Microsoft Teams.

> [!NOTE]
> Poiché l'accesso Single #A0 è abilitato, è importante disabilitare il browser tramite [**WDAC.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Se un client esterno apre il browser e usa la versione Web di Teams, il client avrà accesso alla cronologia delle chiamate/chat.

## <a name="general-deployment-recommendations-and-instructions"></a>Indicazioni e istruzioni generali sulla distribuzione

Per i passaggi di distribuzione di HoloLens 2, è consigliabile eseguire le operazioni seguenti:

1. Usa la [versione più recente del sistema operativo HoloLens](https://aka.ms/hololens2download) come build di base.
1. Assegnare licenze basate sull'utente o sul dispositivo:
    1. Entrambe le licenze basate sull'utente e sul dispositivo seguono i passaggi seguenti:
        1. [Creare un gruppo in AAD e aggiungere membri](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) per gli utenti di HoloLens/RA.
        1. [Assegna licenze basate sul dispositivo o basate sull'utente](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a questo gruppo.
        1. (Facoltativo) Puoi scegliere come destinazione i gruppi per i criteri MDM.

1. I dispositivi devono essere aggiunti ad AAD al tenant, registrati [automaticamente](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configurati tramite [Auto Pilot.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Tieni presente che il primo utente nel dispositivo sarà il proprietario del dispositivo.
    1. Tieni presente che se il dispositivo è aggiunto ad AAD, l'utente che ha eseguito l'aggiunta viene reso proprietario del dispositivo.
    1. Per altre informazioni, vedi [Proprietario del dispositivo.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [Il tenant blocca](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) il dispositivo in modo che possa essere aggiunto solo al tenant.
    1. **Collegamento aggiuntivo:** [CSP di blocco tenant.](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)
1. Configurare il chiosco multimediale con l'accesso assegnato globale [a questa pagina.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. È consigliabile disabilitare le seguenti funzionalità (facoltative):
    1. Possibilità di impostare il dispositivo in modalità sviluppatore [qui.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Possibilità di connettere HoloLens a un PC per copiare la data [disabilitare USB.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Se non vuoi disabilitare USB ma vuoi poter applicare un pacchetto di provisioning al dispositivo tramite USB, segui le istruzioni [**elencate qui.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Usa [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) per consentire o bloccare le app nel dispositivo HoloLens 2.
1. Aggiornare Assistenza remota all'ultima versione durante l'installazione. Esistono due opzioni per eseguire questa operazione:
    1. Questa operazione può essere eseguita in **Windows Microsoft Store --> Assistenza remota --> e Aggiorna app.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) che consente gli aggiornamenti automatici delle app, è abilitato per impostazione predefinita. Mantieni il dispositivo collegato per ricevere gli aggiornamenti.
1. [Disabilitare tutte le pagine delle](https://docs.microsoft.com/hololens/settings-uri-list) impostazioni ad eccezione delle impostazioni di rete per consentire agli utenti di connettersi alle reti guest nei siti client.
1. [Gestire gli aggiornamenti di HoloLens](https://docs.microsoft.com/hololens/hololens-updates)
    1. Opzione per [controllare gli aggiornamenti del sistema operativo](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) o consentire il flusso libero.
1. [Restrizioni comuni per i dispositivi.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)
