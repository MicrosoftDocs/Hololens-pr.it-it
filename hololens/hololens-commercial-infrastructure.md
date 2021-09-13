---
title: Linee guida per l'infrastruttura HoloLens
description: Informazioni sulle linee guida sull'infrastruttura per HoloLens, tra cui il supporto di rete wireless, l'assistenza remota e la gestione dei dispositivi mobili.
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
ms.openlocfilehash: e23bd458e26668f1f4a9a361ffaadf8fc377933e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036052"
---
# <a name="configure-your-network-for-hololens"></a>Configurare la rete per HoloLens

Questa parte del documento richiederà le persone seguenti:

1. Amministratore di rete con autorizzazioni per apportare modifiche al proxy/firewall
2. Azure Active Directory Admin
3. Amministratore di Gestione dispositivi mobili

## <a name="infrastructure-requirements"></a>Requisiti dell'infrastruttura

HoloLens è, alla base, un dispositivo Windows mobile integrato con Azure.  Funziona meglio in ambienti commerciali con disponibilità di rete wireless (Wi-Fi) e accesso servizi Microsoft.

I servizi cloud critici includono:

- Azure active directory (Azure AD)
- Windows Update (WU)

I clienti commerciali necessitano di un'infrastruttura di gestione della mobilità aziendale (EMM) o di gestione di dispositivi mobili (MDM) per gestire i HoloLens su larga scala.  Questa guida usa [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) esempio, anche se qualsiasi provider con supporto completo per Criteri Microsoft può supportare HoloLens.  Chiedere al provider di gestione dei dispositivi mobili se supporta HoloLens 2.

HoloLens supporta un set limitato di esperienze disconnesse dal cloud.

### <a name="wireless-network-eap-support"></a>Supporto EAP della rete wireless

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens Requisiti di rete specifici

Assicurarsi che questo [elenco di](hololens-offline.md) endpoint sia consentito nel firewall di rete. In questo modo HoloLens funzioni correttamente.

### <a name="remote-assist-specific-network-requirements"></a>Remote Assist requisiti di rete specifici

1. La larghezza di banda consigliata per prestazioni ottimali di Remote Assist è di 1,5 Mbps. Per altre [informazioni, vedere i requisiti di](/MicrosoftTeams/prepare-network) rete dettagliati.
**Si noti che, se non si dispone di una rete con velocità di rete di almeno 1,5 Mbps, Remote Assist funzionerà ancora. Tuttavia, la qualità potrebbe risentirne).**
1. Assicurarsi che queste porte e URL siano consentiti nel firewall di rete per consentire Microsoft Teams funzionamento. Rimanere aggiornati con [l'elenco più recente di porte](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- Altre informazioni sui requisiti di [rete specifici per Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Altre informazioni su come preparare [la rete dell'organizzazione per l'Microsoft Teams](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Guide ai requisiti di rete specifici

Le guide richiedono solo l'accesso alla rete per scaricare e usare l'app.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Guida

> [!NOTE]
> Questo passaggio è necessario solo se l'azienda prevede di gestire il HoloLens.

1. Assicurarsi di avere una licenza Azure AD licenza.
Per [altre HoloLens, vedere Requisiti](hololens-licenses-requirements.md) per le licenze.

1. Se si prevede di usare la registrazione automatica, sarà necessario configurare [Azure AD registrazione.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Assicurarsi che gli utenti dell'azienda siano Azure Active Directory (Azure AD).
Vedere le istruzioni [seguenti per](/azure/active-directory/fundamentals/add-users-azure-active-directory) l'aggiunta di utenti.

1. È consigliabile che gli utenti che necessitano di licenze simili siano aggiunti allo stesso gruppo.
    1. [Creare un gruppo](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Aggiungere utenti ai gruppi](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Assicurarsi che agli utenti dell'azienda (o al gruppo di utenti) siano assegnate le licenze necessarie.
Se è necessario assegnare le licenze, seguire queste [istruzioni.](/azure/active-directory/fundamentals/license-users-groups)

1. Eseguire questo passaggio solo se gli utenti devono registrare il proprio dispositivo HoloLens/mobile (sono disponibili tre opzioni) Questi passaggi garantiscono che gli utenti dell'azienda (o un gruppo di utenti) possano aggiungere dispositivi.
    1. **Opzione 1:** Concedere a tutti gli utenti l'autorizzazione per aggiungere dispositivi Azure AD.
**Accedere al portale di Azure come amministratore**  >  **Azure Active Directory**  >  **Dispositivi**  >  **Gestione Impostazioni**  >
 **Impostare Gli utenti possono aggiungere dispositivi Azure AD su *Tutti***

    1. **Opzione 2:** Concedere a utenti/gruppi selezionati l'autorizzazione per aggiungere dispositivi Azure AD Azure AD Accedere al **portale di Azure** come amministratore Azure Active Directory Dispositivi Dispositivo Impostazioni Impostare Gli utenti possono aggiungere dispositivi a Azure AD su Immagine selezionata che mostra La configurazione dei dispositivi aggiunti  >    >    >    >
 **** 
 ![ Azure AD.](images/azure-ad-image.png)

    1. **Opzione 3:** È possibile impedire a tutti gli utenti di aggiungere i propri dispositivi al dominio. Ciò significa che tutti i dispositivi dovranno essere registrati manualmente.

## <a name="mobile-device-manager-guidance"></a>Linee guida per Gestione dispositivi mobili

### <a name="ongoing-device-management"></a>Gestione continua dei dispositivi

> [!NOTE]
> Questo passaggio è necessario solo se l'azienda prevede di gestire il HoloLens.

La gestione continua dei dispositivi dipenderà dall'infrastruttura di gestione dei dispositivi mobili.  La maggior parte ha la stessa funzionalità generale, ma l'interfaccia utente può variare notevolmente.

1. [I provider di servizi di configurazione (CSP)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) consentono di creare e distribuire le impostazioni di gestione per i dispositivi nella rete. Vedere [l'elenco dei HoloLens CSP per](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) informazioni di riferimento.

1. [I criteri di](/intune/device-compliance-get-started) conformità sono regole e impostazioni che i dispositivi devono soddisfare per essere conformi nell'infrastruttura aziendale. Usare questi criteri con l'accesso condizionale per bloccare l'accesso alle risorse aziendali per i dispositivi non conformi. È possibile ad esempio creare un criterio che richiede l'abilitazione di Bitlocker.

1. [Creare i criteri di conformità](/intune/protect/compliance-policy-create-windows).

1. L'accesso condizionale consente o nega ai dispositivi mobili e alle applicazioni per dispositivi mobili di accedere alle risorse aziendali. Due documenti che possono risultare utili sono [Pianificare la distribuzione della CA](/azure/active-directory/conditional-access/plan-conditional-access) e Procedure [consigliate.](/azure/active-directory/conditional-access/best-practices)

1. [Questo articolo](/intune/fundamentals/windows-holographic-for-business) illustra gli strumenti di gestione di Intune per HoloLens.

1. [Creare un profilo di dispositivo](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Gestire gli aggiornamenti

Intune include una funzionalità denominata Anelli di aggiornamento per i dispositivi Windows 10, tra cui HoloLens 2 e HoloLens v1 (con Holographic for Business). Gli anelli di aggiornamento includono un gruppo di impostazioni che determinano come e quando vengono installati gli aggiornamenti.

È possibile ad esempio creare una finestra di manutenzione per installare gli aggiornamenti o scegliere di riavviare dopo l'installazione degli aggiornamenti.  È anche possibile scegliere di sospendere gli aggiornamenti per un periodo illimitato fino a quando non si è pronti per l'aggiornamento.

Altre informazioni sulla [configurazione degli anelli di aggiornamento con Intune.](/intune/windows-update-for-business-configure)

### <a name="application-management"></a>Gestione delle applicazioni

Gestire HoloLens applicazioni tramite:

1. Microsoft Store  
  Il Microsoft Store è il modo migliore per distribuire e utilizzare le applicazioni HoloLens.  È disponibile un ottimo set di HoloLens applicazioni già disponibili nello Store oppure è possibile [pubblicare il proprio](/windows/uwp/publish/).  
  Tutte le applicazioni nello Store sono disponibili pubblicamente per tutti, ma se non è accettabile, vedere il Microsoft Store per le aziende.  

1. [Microsoft Store per le aziende](/microsoft-store/)  
  Microsoft Store per le aziende e Education è un archivio personalizzato per l'ambiente aziendale.  Consente di usare i Microsoft Store predefiniti Windows 10 e HoloLens per trovare, acquisire, distribuire e gestire le app per l'organizzazione.  Consente anche di distribuire app specifiche per l'ambiente commerciale, ma non per il mondo.

1. Distribuzione e gestione di applicazioni tramite Intune o un'altra soluzione di gestione dei dispositivi mobili  
  La maggior parte delle soluzioni di gestione dei dispositivi mobili, incluso Intune, offre un modo per distribuire le applicazioni line-of-business direttamente in un set di dispositivi registrati.  Vedere questo articolo per [l'installazione dell'app Intune.](/intune/apps-deploy)

1. _non consigliato_ Portale di dispositivi  
  Le applicazioni possono anche essere installate HoloLens usando direttamente il Windows Portale di dispositivi.  Questa operazione non è consigliata perché la modalità sviluppatore deve essere abilitata per l'uso del portale di dispositivi.

Altre informazioni [sull'installazione di app in HoloLens](hololens-install-apps.md).

### <a name="certificates"></a>Certificati

È possibile distribuire i certificati tramite il provider MDM. Se la società richiede certificati, Intune supporta PKCS, PFX e SCEP. È importante comprendere quale certificato è più giusto per l'azienda. Per determinare [il certificato](/intune/protect/certificates-configure) più adatto alle specifiche, vedere la documentazione relativa alle configurazioni dei certificati. Se si prevede di usare i certificati per HoloLens autenticazione, PFX o SCEP potrebbe essere la scelta giusta.

Vedere la procedura seguente per l'uso [di SCEP.](/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Come eseguire l'aggiornamento a Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (suite commerciale) è destinato solo HoloLens dispositivi di prima generazione. Il profilo non verrà applicato ai HoloLens 2 dispositivi.

Le istruzioni per l'aggiornamento alla suite commerciale sono disponibili nella documentazione [sull'aggiornamento olografico.](/intune/configuration/holographic-upgrade)

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Come configurare la modalità tutto schermo usando Microsoft Intune

1. Sincronizzare Microsoft Store con Intune (vedere le istruzioni [seguenti).](/intune/apps/windows-store-for-business)

1. Controllare le impostazioni dell'app
    1. Accedere all'account Microsoft Store Business
    1. **Manage > Products and Services > Apps and Software > Selezionare l'app da sincronizzare > Private Store Availability > Selezionare "Everyone" o "Specific Groups"**
        >[!NOTE]
        >Se l'app desiderata non viene visualizzata, sarà necessario "ottenere" l'app cercando l'app nell'Archivio. Fare clic sulla barra "Cerca" nell'angolo superiore destro > digitare il nome dell'app > fare clic **sull'app > selezionare "Ottieni".**
    1. Se le app in Intune non vengono > app **client >,** potrebbe essere necessario [sincronizzare di nuovo le](/intune/apps/windows-store-for-business#synchronize-apps) app.

1. [Creare un profilo di dispositivo per la modalità tutto schermo](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> È possibile configurare utenti diversi per esperienze diverse in modalità tutto schermo usando "Azure AD" come "Tipo di accesso utente". Questa opzione è tuttavia disponibile solo in modalità tutto schermo multi-app. La modalità tutto schermo multi-app funziona con una sola app e con più app.

![Immagine che mostra la configurazione della modalità tutto schermo in Intune.](images/aad-kioskmode.png)

Per altri servizi MDM, vedere la documentazione del provider per istruzioni. Fare riferimento alle istruzioni [HoloLens](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) chiosco multimediale se è necessario usare un'impostazione personalizzata e una configurazione XML completa per configurare un chiosco multimediale nel servizio MDM.

## <a name="certificates-and-authentication"></a>Certificati e autenticazione

I certificati possono essere distribuiti tramite MDM (vedere "certificati" nella [sezione MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) I certificati possono anche essere distribuiti nel HoloLens tramite il provisioning dei pacchetti. Per altre [informazioni, HoloLens provisioning.](hololens-provisioning.md)

### <a name="additional-intune-quick-links"></a>Collegamenti rapidi di Intune aggiuntivi

1. [Creare profili:](/intune/configuration/device-profile-create) I profili consentono di aggiungere e configurare le impostazioni di cui verrà inserito il push nei dispositivi dell'organizzazione.

