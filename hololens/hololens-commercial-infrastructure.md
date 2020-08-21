---
title: Linee guida sull'infrastruttura per HoloLens
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1031eaeaf2767f8aa982d74bb282bc1fb086051b
ms.sourcegitcommit: 77eb85608066d9a4ed01b3862afe356f7e54d583
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "10940216"
---
# Configurare la rete per HoloLens

Questa parte del documento richiede la partecipazione degli utenti seguenti:

1. Amministratore di rete con le autorizzazioni per modificare il proxy o il firewall
2. Amministratore di Azure Active Directory
3. Amministratore di Mobile Device Manager

## Requisiti dell'infrastruttura

HoloLens è, in sostanza, un dispositivo mobile di Windows integrato in Azure.  Funziona in modo ottimale in ambienti commerciali con disponibilità di rete wireless (Wi-Fi) e accesso ai servizi Microsoft.

I servizi cloud critici includono:

- Azure Active Directory (AAD)
- Windows Update (WU)

I clienti commerciali avranno bisogno di un'infrastruttura di gestione della mobilità aziendale (EMM, Enterprise Mobility Management) o gestione dei dispositivi mobili (MDM, Mobile Device Management) per gestire i dispositivi HoloLens in scala.  Questa guida usa [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) come esempio, anche se qualsiasi provider con supporto completo per Microsoft Policy può supportare HoloLens.  Chiedere al provider di gestione di dispositivi mobili se supporta HoloLens 2.

HoloLens supporta un set limitato di esperienze disconnesse dal cloud.

### Supporto EAP di rete wireless

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### Requisiti di rete specifici di HoloLens

Assicurarsi che [questo elenco](hololens-offline.md) di endpoint sia consentito nel firewall di rete. Questo consentirà il funzionamento corretto di HoloLens.

### Requisiti di rete specifici di Remote Assist

1. La larghezza di banda consigliata per prestazioni ottimali di Remote Assist è 1,5 Mbps. È possibile trovare informazioni dettagliate sui requisiti di rete e altre informazioni [qui](https://docs.microsoft.com/MicrosoftTeams/prepare-network).
**Se non si ha una rete con una velocità di rete di almeno 1,5 Mbps, Remote Assist funzionerà comunque. Tuttavia, la qualità potrebbe soffrire.**
1. Assicurarsi che le porte e gli URL seguenti siano consentiti nel firewall di rete. Questo permetterà il funzionamento di Microsoft Teams. L'elenco più recente è disponibile [qui](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- Leggere altre informazioni sui requisiti di rete [specifici per assistenza remota t](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Leggere altre informazioni su come[preparare la rete aziendale per Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### Requisiti di rete specifici di Guides

Guides richiede solo l'accesso di rete per scaricare e usare l'app.

## Indicazioni per Azure Active Directory

> [!NOTE]
> Questo passaggio è necessario solo se la società prevede di gestire HoloLens.

1. Verificare di avere una licenza di Azure AD.
Per altre informazioni, vedere i [requisiti di licenza di HoloLens](hololens-licenses-requirements.md).

1. Se si prevede di usare la registrazione automatica, sarà necessario [configurare la registrazione di Azure AD.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Verificare che gli utenti della società siano in Azure Active Directory (Azure AD).
Le istruzioni per l'aggiunta di utenti sono disponibili [qui](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).

1. È consigliabile aggiungere gli utenti che hanno bisogno di licenze simili allo stesso gruppo.
    1. [Creare un gruppo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Aggiungere utenti ai gruppi](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Verificare che gli utenti (o il gruppo di utenti) della società abbiano le licenze necessarie.
Le istruzioni per assegnare le licenze sono disponibili [qui](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).

1. Eseguire questa procedura solo se gli utenti devono registrare il proprio dispositivo HoloLens/mobile (sono disponibili tre opzioni). Questi passaggi assicurano che gli utenti (o un gruppo di utenti) della società possano aggiungere dispositivi.
    1. **Opzione 1:** consentire a tutti gli utenti di aggiungere dispositivi in Azure AD.
**Accedere al portale di Azure come amministratore** > **Azure Active Directory** > **Dispositivi** > **Impostazioni dei dispositivi** >
**Impostare Gli utenti possono aggiungere dispositivi ad Azure AD su*Tutti***

    1. **Opzione 2:** assegnare a utenti/gruppi selezionati l'autorizzazione per l'aggiunta di dispositivi ad Azure AD **Accedere al portale di Azure come amministratore** > **Azure Active Directory** > **Dispositivi** > **Impostazioni dei dispositivi** >
**Impostare gli utenti possono aggiungere dispositivi ad Azure AD su *Selezionati***
![Immagine che mostra la configurazione dei dispositivi aggiunti ad Azure AD](images/azure-ad-image.png)

    1. **Opzione 3:** è possibile impedire a tutti gli utenti di aggiungere i propri dispositivi al dominio. Questo significa che tutti i dispositivi devono essere registrati manualmente.

## Indicazioni per Mobile Device Manager

### Gestione continuativa di dispositivi mobili

> [!NOTE]
> Questo passaggio è necessario solo se la società prevede di gestire HoloLens.

La gestione continuativa dei dispositivi dipenderà dall'infrastruttura di gestione dei dispositivi mobili in uso.  La maggior parte ha le stesse funzionalità generali, ma l'interfaccia utente può variare notevolmente.

1. [I provider di servizi di configurazione (CSP )](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) consentono di creare e distribuire impostazioni di gestione per i dispositivi della rete. È possibile trovare un elenco di CPS per HoloLens [qui](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).

1. I [criteri di conformità](https://docs.microsoft.com/intune/device-compliance-get-started) sono regole e impostazioni che i dispositivi devono soddisfare per essere conformi nell'infrastruttura aziendale. Usare questi criteri insieme all'accesso condizionale per bloccare l'accesso alle risorse aziendali per i dispositivi non conformi. Ad esempio, è possibile creare un criterio che richiede che BitLocker sia abilitato.

1. [Creare criteri di conformità](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).

1. L'accesso condizionale consente/nega ai dispositivi mobili e alle applicazioni per dispositivi mobili l'accesso alle risorse aziendali. Due documenti che possono essere utili sono [Procedura: pianificare la distribuzione dell'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) e [Procedure consigliate](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).

1. [Questo articolo](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) parla degli strumenti di gestione di Intune per HoloLens.

1. [Creare un profilo del dispositivo](https://docs.microsoft.com/intune/configuration/device-profile-create)

### Gestire gli aggiornamenti

Intune include una caratteristica denominata Anelli di aggiornamento per i dispositivi Windows 10, tra cui HoloLens 2 e HoloLens V1 (con Holographic for Business). Gli anelli di aggiornamento includono un gruppo di impostazioni che determinano come e quando vengono installati gli aggiornamenti.

Ad esempio, è possibile creare una finestra di manutenzione per installare gli aggiornamenti oppure scegliere di riavviare dopo l'installazione degli aggiornamenti.  Si può anche scegliere di sospendere gli aggiornamenti a tempo indeterminato finché non si è pronti per l'aggiornamento.

Seguire il link per altre informazioni sulla [configurazione degli anelli di aggiornamento con Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

### Gestione delle applicazioni

Gestire le applicazioni di HoloLens tramite:

1. Microsoft Store  
  Microsoft Store è il mezzo migliore per distribuire e usare applicazioni su HoloLens.  Nello Store è già disponibile un'ampia gamma di applicazioni di HoloLens oppure è possibile [pubblicare la propria](https://docs.microsoft.com/windows/uwp/publish/).  
  Tutte le applicazioni nello Store sono disponibili pubblicamente per tutti. Se questo non è accettabile, provare Microsoft Store per le aziende.  

1. [Microsoft Store per le aziende](https://docs.microsoft.com/microsoft-store/)  
  Microsoft Store per le aziende e gli istituti di istruzione è un negozio personalizzato per gli ambienti aziendali.  Consente di usare Microsoft Store integrato in Windows 10 e HoloLens per trovare, acquisire, distribuire e gestire app per l'organizzazione.  Consente anche di distribuire app specifiche per il proprio ambiente commerciale, ma non a tutto il mondo.

1. Distribuzione e gestione delle applicazioni con Intune o un'altra soluzione di gestione dei dispositivi mobili  
  La maggior parte delle soluzioni di gestione dei dispositivi mobili, tra cui Intune, offre un modo per distribuire applicazioni line-of-business direttamente in un set di dispositivi registrati.  Vedere questo articolo per l'[installazione di app con Intune](https://docs.microsoft.com/intune/apps-deploy).

1. _non consigliato_ Device Portal  
  Le applicazioni possono anche essere installate direttamente in HoloLens tramite Windows Device Portal.  Questa scelta non è consigliata, perché per usare il portale di dispositivi occorre abilitare la modalità di sviluppo.

Seguire il link per altre informazioni sull[installazione di app in HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

### Certificati

È possibile distribuire i certificati tramite il provider MDM. Se la società ha bisogno di certificati, Intune supporta PKCS, PFX e SCEP. È importante comprendere quale sia il certificato appropriato per l'azienda. Visitare [questa pagina](https://docs.microsoft.com/intune/protect/certificates-configure) per determinare quale sia la soluzione più adatta alle proprie esigenze. Se si prevede di usare certificati per l'autenticazione di HoloLens, PFX o SCEP può essere la scelta corretta.

La procedura per SCEP è disponibile [qui](https://docs.microsoft.com/intune/protect/certificates-profile-scep).

### Come eseguire l'aggiornamento alla famiglia di prodotti commerciali Holographic for Business

> [!NOTE]
> Windows Holographic for Business (famiglia di prodotti commerciali) è inteso solo per i dispositivi HoloLens di prima generazione. Il profilo non verrà applicato ai dispositivi HoloLens 2.

Le istruzioni per l'aggiornamento alla famiglia di prodotti commerciali sono disponibili [qui](https://docs.microsoft.com/intune/configuration/holographic-upgrade).

### Come configurare la modalità tutto schermo con Microsoft Intune

1. Sincronizzare Microsoft Store con Intune ([vedere qui](https://docs.microsoft.com/intune/apps/windows-store-for-business))

1. Controllare le impostazioni dell'app
    1. Accedere all'account di Microsoft Store per le aziende
    1. **Gestisci > Prodotti e servizi > App e software > Selezionare l'app che si vuole sincronizzare > Disponibilità archivio privato > Selezionare "Tutti" o "Gruppi specifici"**
        >[!NOTE]
        >Se l'app desiderata non viene visualizzata, sarà necessario eseguire una ricerca nel punto vendita per l'app. **Fare clic sulla barra di ricerca nell'angolo in alto a destra > digitare il nome dell'app > fare clic sull'app > selezionare Ottieni**.
    1. Se le proprie app non sono visibili in **Intune > App client > App**, potrebbe essere necessario [sincronizzare le app](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) di nuovo.

1. [Creare un profilo del dispositivo per la modalità tutto schermo](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> È possibile configurare utenti diversi per esperienze in modalità tutto schermo diverse usando "Azure AD" come "Tipo di accesso utente". Tuttavia, questa opzione è disponibile solo in modalità Più app in modalità tutto schermo. La modalità Più app in modalità tutto schermo funziona sia con una sola app, sia con più app.

![Immagine che mostra la configurazione della modalità tutto schermo in Intune](images/aad-kioskmode.png)

Per altri servizi MDM, vedere le istruzioni nella documentazione del provider. Se è necessario usare un'impostazione personalizzata e una configurazione XML completa per configurare un chiosco nel dispositivo MDM, altre indicazioni sono disponibili [qui](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

## Certificati e autenticazione

I certificati possono essere distribuiti tramite MDM (vedere "certificati" nella [sezione MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). È anche possibile distribuire certificati al dispositivo HoloLens mediante il provisioning di pacchetti. Per altre informazioni, vedere [Provisioning di HoloLens](hololens-provisioning.md).

### Altri collegamenti rapidi di Intune

1. [Creare profili:](https://docs.microsoft.com/intune/configuration/device-profile-create) i profili consentono di aggiungere e configurare impostazioni che verranno inviate ai dispositivi dell'organizzazione.

