---
title: Guida alla distribuzione di client esterni
description: Guida alla distribuzione di HoloLens 2 per client esterni (ad esempio, con assistenza remota)
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
ms.openlocfilehash: 7658ace4879fef401accabb95ca22e307e5f80a8
ms.sourcegitcommit: 50e4d61a31b94d5007776064b4012e26cf9ecbbb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271660"
---
# Distribuzione di HoloLens 2 a client esterni con assistenza remota

Questa guida consente ai professionisti IT con gli obiettivi seguenti di distribuire i dispositivi Microsoft HoloLens 2 nell'organizzazione:

1. Dispositivi Cloud Connect HoloLens 2
1. Prestito HoloLens 2 dispositivi ai client esterni per l'uso
1. Dispositivi in prestito sicuro

Questa guida fornirà [consigli generali per la distribuzione di HoloLens 2](#general-deployment-recommendations-and-instructions) applicabili alla maggior parte degli scenari di distribuzione di HoloLens 2 e alle [preoccupazioni comuni](#common-concerns) che i clienti hanno quando si distribuisce assistenza remota per l'uso esterno.

## Descrizione scenario

Ai fini del presente documento, Contoso Company vuole spedire un dispositivo HoloLens 2 a un impianto client esterno per l'uso a breve o lungo termine. Quando il client necessita di assistenza tecnica, il client accede al dispositivo HoloLens 2 usando le credenziali fornite dalla società Contoso e USA assistenza remota per contattare gli esperti della società Contoso.

Leggi altre informazioni su assistenza remota [qui](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### Requisiti per questo scenario

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Gestione di dispositivi mobili, ad esempio [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Licenza di Remote Assist
    1. [Acquistare assistenza remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Assistenza remota di valutazione](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## Preoccupazioni comuni

- [Come assicurarsi che i client esterni non abbiano la possibilità di comunicare tra loro](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Come assicurarsi che i client non abbiano accesso alle risorse aziendali](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Come limitare le app](#how-to-restrict-apps)
- [Come gestire le password](#how-to-manage-passwords)
- [Come assicurarsi che i client non abbiano accesso alla cronologia chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### Come assicurarsi che i client esterni non abbiano la possibilità di comunicare tra loro

Poiché l'assistenza remota HoloLens alle chiamate HoloLens non è supportata, i client sono in grado di cercare, ma non sono in grado di comunicare tra loro. Per limitare ulteriormente gli utenti che possono cercare e chiamare i clienti,  [le barriere informative](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) possono limitare l'utente con cui può comunicare un client. Un'altra opzione da considerare consiste nell'usare la [ricerca di directory con ambito](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Dato che Single Sign-on è abilitato, è importante disabilitare il browser usando [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Se un client esterno apre il browser e usa la versione Web di teams, il client potrà accedere alla cronologia delle chiamate/chat.

### Come assicurarsi che i client non abbiano accesso alle risorse aziendali

Ci sono due opzioni da prendere in considerazione.

La prima opzione è un approccio multilivello:

1. Assegna solo le licenze necessarie per l'utente. Se non si assegna OneDrive, Outlook, SharePoint, Yammer e così via all'utente, non avrà accesso a tali risorse. Le licenze solo per gli utenti dovranno essere le licenze remote Assist, Intune e AAD per iniziare.
1. Blocca le app (ad esempio la posta elettronica) a cui non vuoi che i client accedano (Vedi [come limitare le app](#how-to-restrict-apps)).
1. NON condividere nomi utente né password con i client. Per accedere al HoloLens 2, è necessario un messaggio di posta elettronica e un PIN numerico.

La seconda opzione consiste nel creare un tenant separato che ospita i client (Vedi immagine 1,1).

**Immagine 1,1**

![Immagine del tenant del servizio](./images/hololens-service-tenant-image.png)

### Come limitare le app

La [modalità Kiosk](https://docs.microsoft.com/hololens/hololens-kiosk) e/o [WDAC (controllo applicazione Windows Defender)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) sono opzioni per limitare le applicazioni.

### Come gestire le password

1. Rimuovi scadenza password. Tuttavia, questo aumenta la probabilità che un account venga compromesso. La raccomandazione per la password NIST cambia le password ogni 30-90 giorni.
1. Estendere la scadenza della password per i dispositivi HoloLens 2 per superare i 90 giorni.
1. I dispositivi devono essere restituiti a Contoso per modificare le password. Tuttavia, questo problema può causare problemi se i dispositivi sono previsti nell'impianto del cliente per 90 + giorni.  
1. Per i dispositivi inviati a più client, reimpostare le password prima di spedire il dispositivo ai client.

### Come assicurarsi che i client non abbiano accesso alla cronologia chat

Assistenza remota Cancella la cronologia chat dopo ogni sessione. Tuttavia, la cronologia chat sarà disponibile per l'utente di Microsoft teams.

> [!NOTE]
> Dato che Single Sign-on è abilitato, è importante disabilitare il browser usando [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Se un client esterno apre il browser e usa la versione Web di teams, il client potrà accedere alla cronologia delle chiamate/chat.

## Raccomandazioni e istruzioni generali per la distribuzione

È consigliabile seguire i passaggi per la distribuzione di HoloLens 2:

1. Usa la [versione più recente del sistema operativo HoloLens](https://aka.ms/hololens2download) come configurazione di base.
1. Assegnare licenze basate su utenti o basate su dispositivi:
    1. Le licenze basate su utente e basate su dispositivi seguono i passaggi seguenti:
        1. [Creare un gruppo in AAD e aggiungere membri](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) per gli utenti di HOLOLENS/ra.
        1. [Assegnare licenze basate su dispositivi o basate su utenti](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a questo gruppo.
        1. Opzionale Puoi scegliere come destinazione i gruppi per i criteri di MDM.

1. I dispositivi devono essere associati ad AAD al tenant, [registrati automaticamente](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configurati tramite il [pilota automatico](https://docs.microsoft.com/hololens/hololens2-autopilot).
    1. Tieni presente che il primo utente del dispositivo sarà il proprietario del dispositivo.
    1. Tieni presente che se il dispositivo è collegato a AAD, l'utente che ha eseguito il join è proprietario del dispositivo.
    1. Per altre informazioni, Vedi [proprietario del dispositivo](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).
1. Il [tenant blocca](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) il dispositivo in modo che possa essere Unito solo al tenant.
    1. **Collegamento aggiuntivo:** [DSN di blocco del tenant](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).
1. Configurare Kiosk usando l'accesso assegnato a livello [globale.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. È consigliabile disabilitare le funzionalità follow (facoltative):
    1. Possibilità di inserire il dispositivo [in modalità sviluppatore](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).
    1. Possibilità di connettere il HoloLens a un PC per copiare data [Disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Se non si vuole disabilitare l'interfaccia USB, ma si vuole che la possibilità di applicare un pacchetto di provisioning al dispositivo tramite USB, seguire le istruzioni elencate [**qui**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. USA [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) per consentire o le app nere nel dispositivo HoloLens 2.
1. Aggiornare Remote assist alla versione più recente come parte della configurazione. Per eseguire questa operazione, sono disponibili due opzioni:
    1. Questa operazione può essere eseguita accedendo a Windows **Microsoft Store--> Remote Assist--> e Update app**.
    1. Abilitare gli aggiornamenti automatici usando il CSP di [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) e far connettere il dispositivo per ricevere gli aggiornamenti.
1. [Disabilitare tutte le pagine delle impostazioni](https://docs.microsoft.com/hololens/settings-uri-list) , ad eccezione delle impostazioni di rete, per consentire agli utenti di connettersi alle reti guest nei siti client.
1. [Gestire gli aggiornamenti di HoloLens](https://docs.microsoft.com/hololens/hololens-updates)
    1. Opzione per [controllare gli aggiornamenti del sistema operativo](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) o consentire il flusso gratuito.
1. [Restrizioni comuni](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)per i dispositivi.
