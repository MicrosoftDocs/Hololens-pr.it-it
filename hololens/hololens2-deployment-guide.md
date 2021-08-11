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
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659874"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Distribuzione di HoloLens 2 in client esterni con Remote Assist

Questa guida consente ai professionisti IT con gli obiettivi seguenti di distribuire Microsoft HoloLens 2 dispositivi nell'organizzazione:

1. Cloud Connect HoloLens 2 dispositivi
1. Prestito HoloLens 2 dispositivi a client esterni per l'uso
1. Proteggere i dispositivi in prestito

Questa guida fornirà indicazioni generali sulla [distribuzione](#general-deployment-recommendations-and-instructions) HoloLens 2 che sono applicabili alla [](#common-concerns) maggior parte degli scenari di distribuzione HoloLens 2 e ai problemi comuni che i clienti hanno quando distribuiscono Remote Assist per l'uso esterno.

## <a name="scenario-description"></a>Descrizione dello scenario

Ai fini di questo documento, Contoso Company vuole spedire un dispositivo HoloLens 2 allo stabilimento di un cliente esterno per un uso a breve o a lungo termine. Quando il client necessita di assistenza per i macchinari di manutenzione, il client accederà al dispositivo HoloLens 2 usando le credenziali fornite da Contoso Company e userà Remote Assist per contattare gli esperti di Contoso Company.

Altre informazioni sulle Remote Assist [qui.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Requisiti per questo scenario

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Gestione dispositivi mobili, ad esempio [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist licenza
    1. [Acquistare Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Versione di Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Problemi comuni

- [Come assicurarsi che i client esterni non possano comunicare tra loro](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Come assicurarsi che i client non hanno accesso alle risorse aziendali](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Come limitare le app](#how-to-restrict-apps)
- [Come gestire le password](#how-to-manage-passwords)
- [Come assicurarsi che i client non hanno accesso alla cronologia delle chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Come assicurarsi che i client esterni non possano comunicare tra loro

Poiché Remote Assist HoloLens le HoloLens non sono supportate, i client possono cercare, ma non possono, comunicare tra loro. Per limitare ulteriormente gli utenti che i client possono cercare e chiamare,  [le barriere alle informazioni](/microsoft-365/compliance/information-barriers) possono limitare gli utenti con cui un client può comunicare. Un'altra opzione da considerare è [l'uso di Ricerca directory con ambito](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Poiché l'accesso Single Sign-On è abilitato, è importante disabilitare il browser usando [**WDAC.**](/hololens/windows-defender-application-control-wdac) Se un client esterno apre il browser e usa la versione Web di Teams, il client avrà accesso alla cronologia chiamate/chat.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Come assicurarsi che i client non hanno accesso alle risorse aziendali

Esistono due opzioni da considerare.

La prima opzione è un approccio a più livelli:

1. Assegnare solo le licenze richieste dall'utente. Se non si assegnano OneDrive, Outlook, SharePoint, Yammer e così via all'utente, non avrà accesso a tali risorse. Le uniche licenze necessarie agli utenti sono Remote Assist, Intune e AAD per iniziare.
1. Bloccare le app (ad esempio la posta elettronica) a cui non si vuole che i client accedono (vedere [Come limitare le app).](#how-to-restrict-apps)
1. NON condividere nomi utente e password con i client. Per accedere al HoloLens 2, sono necessari un messaggio di posta elettronica e un PIN numerico.

La seconda opzione è creare un tenant separato che ospita i client (vedere Immagine 1.1).

**Immagine 1.1**

![Immagine del tenant del servizio](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Come limitare le app

[La modalità tutto](/hololens/hololens-kiosk) schermo e/o [WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) sono opzioni per limitare le applicazioni.

### <a name="how-to-manage-passwords"></a>Come gestire le password

1. Rimuovere la scadenza della password. Tuttavia, ciò aumenta la probabilità che un account venga compromesso. La raccomandazione per la password NIST è modificare le password ogni 30-90 giorni.
1. Estendere la scadenza della password per HoloLens 2 dispositivi per superare i 90 giorni.
1. I dispositivi devono essere restituiti a Contoso per modificare le password. Tuttavia, ciò può causare problemi se si prevede che i dispositivi siano nello stabilimento del client per più di 90 giorni.  
1. Per i dispositivi inviati a più client, reimpostare le password prima di inviare il dispositivo ai client.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Come assicurarsi che i client non hanno accesso alla cronologia delle chat

Remote Assist cancella la cronologia chat dopo ogni sessione. Tuttavia, la cronologia delle chat sarà disponibile per l'Microsoft Teams utente.

> [!NOTE]
> Poiché l'accesso Single Sign-On è abilitato, è importante disabilitare il browser usando [**WDAC.**](/hololens/windows-defender-application-control-wdac) Se un client esterno apre il browser e usa la versione Web di Teams, il client avrà accesso alla cronologia chiamate/chat.

## <a name="general-deployment-recommendations-and-instructions"></a>Istruzioni e Consigli distribuzione generale

È consigliabile seguire questa procedura per HoloLens 2 di distribuzione:

1. Usare la [versione HoloLens del sistema operativo più recente](https://aka.ms/hololens2download) come build di base.
1. Assegnare licenze basate su utente o su dispositivo:
    1. Entrambe le licenze basate su utenti e dispositivi seguono la procedura seguente:
        1. [Creare un gruppo in AAD e aggiungere membri per gli](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) utenti HoloLens/RA.
        1. [Assegnare licenze basate su dispositivo o basate su utente](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a questo gruppo.
        1. (Facoltativo) È possibile scegliere come destinazione i gruppi per i criteri MDM.

1. I dispositivi devono essere aggiunti ad AAD al tenant, [Registrato automaticamente](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configurati tramite [Pilota automatico.](/hololens/hololens2-autopilot)
    1. Si noti che il primo utente del dispositivo sarà il proprietario del dispositivo.
    1. Si noti che se il dispositivo è aggiunto ad AAD, l'utente che ha eseguito l'aggiunta viene reso proprietario del dispositivo.
    1. Per altre informazioni, vedere [Proprietario del dispositivo.](/hololens/security-adminless-os#device-owner)
1. [Il tenant blocca](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) il dispositivo in modo che possa essere aggiunto solo al tenant.
    1. **Collegamento aggiuntivo:** [CSP di blocco del tenant](/windows/client-management/mdm/tenantlockdown-csp).
1. Configurare la modalità tutto schermo usando l'accesso assegnato globale a [qui.](/hololens/hololens-global-assigned-access-kiosk)
1. È consigliabile disabilitare le funzionalità seguenti (facoltative):
    1. Possibilità di impostare il dispositivo in modalità sviluppatore [qui.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Possibilità di connettere il HoloLens a un PC per copiare data [disabilitare USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Se non si vuole disabilitare USB ma si vuole poter applicare un pacchetto di provisioning al dispositivo tramite USB, seguire le istruzioni elencate [**qui.**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Usare [WDAC](/hololens/windows-defender-application-control-wdac) per consentire o bloccare le app nel HoloLens 2 dispositivo.
1. Aggiornare Remote Assist alla versione più recente come parte dell'installazione. A tale scopo, sono disponibili due opzioni:
    1. Questa operazione può essere eseguita selezionando Windows **Microsoft Store --> Remote Assist --> e Aggiorna app**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) che consente gli aggiornamenti automatici delle app, è abilitato per impostazione predefinita. Mantenere il dispositivo collegato per ricevere gli aggiornamenti.
1. [Disabilitare tutte le pagine delle](/hololens/settings-uri-list) impostazioni ad eccezione delle impostazioni di rete per consentire agli utenti di connettersi alle reti guest nei siti client.
1. [Gestire HoloLens aggiornamenti](/hololens/hololens-updates)
    1. Opzione per [controllare gli aggiornamenti del sistema operativo](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) o consentire il flusso libero.
1. [Restrizioni comuni dei dispositivi](/hololens/hololens-common-device-restrictions).
