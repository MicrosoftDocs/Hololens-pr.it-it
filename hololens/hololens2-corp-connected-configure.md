---
title: Guida alla distribuzione - Connessione aziendale HoloLens 2 con Dynamics 365 Guides - Configurare
description: Informazioni su come configurare le configurazioni per distribuire HoloLens 2 dispositivi su una rete connessa aziendale con Dynamics 365 Guides.
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
ms.openlocfilehash: 2b855f5891dfa4ca695e4ae3b2a2e82510c5b626f08b434643169be239b48291
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660182"
---
# <a name="configure---corporate-connected-guide"></a>Configurare - Guida alla connessione aziendale

## <a name="azure-users-and-groups"></a>Utenti e gruppi di Azure

Azure e Intune con tale estensione, usa utenti e gruppi per assegnare configurazioni e licenze. Per convalidare questo flusso di distribuzione ed essere in grado di verificare che sia possibile creare e gestire una guida, è&#39;necessario un account utente.

È possibile creare un singolo gruppo di utenti in modo specifico per l'assegnazione delle licenze.

Se non si&#39;avere già accesso a due account Azure AD in un gruppo di utenti, è possibile usare . Ecco le guide introduttive per:

- [Come creare un utente](/mem/intune/fundamentals/quickstart-create-user)
- [Come creare un gruppo](/mem/intune/fundamentals/quickstart-create-group)
- [Aggiungere utenti a un gruppo:](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) aggiungere utenti creati per creare un gruppo
- [Configurare Azure AD per consentire a un gruppo di utenti](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) di aggiungere dispositivi: assicurarsi che il nuovo gruppo di utenti abbia l'autorizzazione per registrare i dispositivi Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Registrazione automatica in HoloLens 2

Per un'esperienza semplice e semplice, è possibile configurare Azure Active Directory Join (AADJ) e La registrazione automatica in Intune per HoloLens 2 dispositivi. Ciò consente agli utenti di immettere le credenziali di accesso dell'organizzazione durante la configurazione guidata e di registrarsi automaticamente con Azure AD e registrare il dispositivo in MDM.

Usando [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), è possibile selezionare i servizi e spostarsi in alcune pagine fino a quando non è possibile selezionare Get a Premium trial (Ottieni una versione Premium versione di valutazione). È possibile notare che è Azure Active Directory Premium 1 e 2: per la registrazione automatica P1 è sufficiente. È possibile selezionare Intune, selezionare l'ambito utente per la registrazione automatica e selezionare il gruppo creato in precedenza.

Per informazioni dettagliate e passaggi completi, vedere la guida [su come abilitare la registrazione automatica per Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Connettività Wi-Fi aziendale

Le Wi-Fi aziendali richiedono in genere l'autenticazione basata su certificati per i clienti che usano HoloLens 2. È necessario distribuire questi certificati usando un'infrastruttura di certificati Simple Certificate Enrollment Protocol (SCEP) o PKCS (Public Key Cryptography Standard) integrata con la soluzione MDM. L'uso di Intune per Wi-Fi profili, certificati e impostazioni proxy consente di creare un'esperienza facile per gli utenti finali.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Distribuire certificati e profili Wi-Fi certificati

Per distribuire certificati e profili tramite Microsoft Endpoint Manager, seguire questa procedura:

1. Creare un profilo per ognuno dei certificati radice e intermedio (vedere [Creare profili certificato attendibili](/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Ognuno di questi profili deve avere una descrizione che includa una data di scadenza in formato GG/MM/AAAA.

    > [!CAUTION]
    > **I profili certificato senza una data di scadenza non verranno distribuiti.**

2. Creare un profilo per ogni certificato SCEP o PKCS (vedere Creare un profilo certificato SCEP o Creare un profilo certificato [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Ognuno di questi profili deve avere una descrizione che includa una data di scadenza in formato GG/MM/AAAA.

    > [!CAUTION]
    > **I profili certificato senza una data di scadenza non verranno distribuiti.**

    > [!Note]
    > Poiché il HoloLens 2 è considerato per molti un dispositivo condiviso, ad esempio più utenti per dispositivo, è consigliabile distribuire i certificati del dispositivo anziché i certificati utente per l'autenticazione Wi-Fi laddove possibile.

3. Creare un profilo per la rete Wi-Fi aziendale (vedere [Impostazioni Wi-Fi](/intune/wi-fi-settings-windows)per dispositivi Windows 10 e versioni successive). Nel profilo Wi-Fi, è possibile scegliere di usare le impostazioni proxy all'interno dell'organizzazione.

    Le opzioni disponibili sono:
    - **Nessuno**: non sono state configurate impostazioni proxy.
    - **Configurare manualmente**: immettere l'indirizzo **IP del server proxy e** il relativo numero di **porta.**
    - **Configura automaticamente**: immettere l'URL che punta a uno script di configurazione automatica del proxy. Ad esempio, immettere *http://proxy.contoso.com/proxy.pac* .

    Per altre informazioni, vedere l'articolo sul [file di configurazione automatica proxy (PAC)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (viene aperto un sito non Microsoft).
 
    > [!Note]
    > È consigliabile assegnare il Wi-Fi profilo a Gruppi di dispositivi anziché a Gruppi di utenti, se possibile.
     
    > [!Tip]
    > È anche possibile esportare un profilo Wi-Fi lavoro da un PC Windows 10 nella rete aziendale. Questa esportazione crea un file XML con tutte le impostazioni correnti. Importare quindi questo file in Intune e usarlo come profilo Wi-Fi per i HoloLens 2 dispositivi. Vedere [Esportare e importare impostazioni Wi-Fi per i dispositivi Windows](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Assegnare](/mem/intune/configuration/device-profile-assign) i profili di dispositivo HoloLens gruppo di dispositivi.

2.  [Monitorare](/mem/intune/configuration/device-profile-monitor) i profili di dispositivo in Intune.

In caso di problemi con i profili Wi-Fi, fare riferimento a [Risolvere Wi-Fi dei profili di configurazione dei dispositivi in Intune.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Risoluzione dei problemi di accesso a Internet esterno quando Corp Connesso
Quando i servizi tentano di non passare attraverso un proxy impostato, possono tentare di connettersi tramite il firewall. È possibile aggiungere un elenco di specifiche dell'endpoint alle regole del firewall per risolvere questi problemi.

Se si è bloccati alle porte del firewall, abilitare alcuni [endpoint comuni](/hololens/hololens-offline) per HoloLens.

È anche possibile abilitare le porte specifiche di Guides: URL accessibili a Internet necessari per [la connettività Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Distribuzione di app

La distribuzione di un'app LOB tramite MDM è un metodo facilmente scalabile che può essere distribuito automaticamente nei dispositivi al momento della registrazione in un gruppo creato.

Se si stanno ancora sviluppando le app o non se ne ha ancora una, è possibile usare un'app di esempio dell'hub degli esempi MRTK. Questa app di esempio è pronta per l'uso e non richiede l'uso di Unity o Visual Studio. [Scaricare l'app di esempio MRTK Examples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Se si preferisce usare la propria app o si è interessati allo sviluppo di app per la realtà mista, è possibile consultare la documentazione per sviluppatori [di Realtà mista](/windows/mixed-reality/design/design).

> [!NOTE]
> I requisiti di sistema per HoloLens dispositivi sono basati sull'architettura della compilazione dell'app. HoloLens 2 dispositivi usano l'architettura arm. Quando si compilano le app Visual Studio, assicurarsi di aver selezionato l'architettura corretta per il dispositivo e di includere le dipendenze necessarie.

> [!IMPORTANT]
> Quando si distribuiscono app LOB, è importante caricare anche il certificato in Intune e assegnarlo allo stesso gruppo destinato a usare l'app o che non verrà installato correttamente.

### <a name="upload-and-assign-the-app"></a>Upload e Assegnare l'app

1. Passare [all'interfaccia di amministrazione di MEM.](https://endpoint.microsoft.com/#home)

2. Selezionare **Tutte**  ->  **le app e** fare clic sul pulsante **+** Aggiungi.

3. In Altro selezionare **App line-of-business.** Fare clic **su selezionare**.

4. Selezionare il file del pacchetto dell'app, si tratta del file APPXBUNDLE o, nel caso di questo esempio, l'app è _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_.

5. Si riceverà una notifica delle dipendenze mancanti. In questo caso, è necessario caricare _Microsoft.VCLibs.ARM.14.00.appx_. Cercarlo in **Selezionare un file**.

6. Selezionare OK.

7. Nella schermata successiva i campi obbligatori verranno compilati automaticamente. Selezionare **Avanti**.

8. In Obbligatorio aggiungere il gruppo creato in precedenza per rendere l'app necessaria per il gruppo. In questo modo l'app verrà scaricata automaticamente nei dispositivi registrati nel gruppo. Selezionare **Avanti**.

9. Selezionare **Crea**.

Altre informazioni: [Assegnare app ai gruppi in Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guide all'installazione: licenze dell'applicazione, dataverse e creazione

Per usare Dynamics 365 Guides, è necessario eseguire una preparazione. Ci sono tre aree in cui è necessario prepararsi; utenti, dataverse e le guide stesse.

### <a name="users-and-application-licenses"></a>Utenti e licenze dell'applicazione

Per usare guide, un utente dovrà usare un account Azure AD, configurato in precedenza in questa guida.

Sarà anche necessario assegnare una Dynamics 365 Guides all'utente creato. Questa operazione verrà esere [dall'interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/AdminPortal/Home). Assegnare anche la licenza all'account Azure primario.

Seguire [questa breve guida con](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) le immagini per istruzioni dettagliate sull'applicazione delle licenze dell'applicazione.

### <a name="set-up-the-dataverse"></a>Configurare Dataverse

Per configurare [un ambiente di produzione,](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) è necessario soddisfare due prerequisiti. È necessario disporre del  [**ruolo Amministratore**](/power-platform/admin/database-security) di sistema ed è [](/dynamics365/mixed-reality/guides/setup-step-one) necessario avere una licenza [**Power Apps**](/power-platform/admin/signup-question-and-answer) (o una licenza Dynamics 365 Guides che include una licenza Power Apps licenza). Se seguendo questa guida è stata creata la Azure AD, si soddisfano i requisiti del ruolo per l'amministratore di sistema. Nel passaggio precedente è stata assegnata anche una licenza guides.

In questa guida per [creare un ambiente Microsoft Dataverse:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Per iniziare, usare il [interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/environments) e creare un nuovo ambiente.
2. Quando si crea **il nuovo ambiente**, per **Tipo**&#39;selezionerà **Produzione**.
3. È importante attivare o disattivare **Crea un database per questo ambiente?**  impostata su **Sì.**
4. Nella finestra  **di dialogo**  Aggiungi database impostare l'opzione Abilita app  **Dynamics 365**  su  **Sì.**

È necessario aumentare le dimensioni massime del file degli elementi nel dataverse. Aumentando le dimensioni massime del file sarà possibile caricare modelli 3D o file video più grandi che verranno utilizzati più avanti nelle guide. Seguire una breve guida [per modificare le dimensioni massime del file di caricamento.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Infine, è necessario installare e [configurare la soluzione](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). Nel [interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/environments)selezionare Risorse  \& >  **App Dynamics 365,** **selezionare** Dynamics 365 Guides nell'elenco e quindi selezionare **Installa**.  

È necessario [aggiungere un ruolo di sicurezza Guide](/dynamics365/mixed-reality/guides/assign-role) prima di poter usare le app.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Creare una guida di test nel PC tramite creazione

Quando si creano guide, si inizierà sempre dal PC. Creazione dei passaggi, selezione dei modelli e come ancorare la guida. A questo scopo, inserire il contenuto per la guida in un secondo momento in modalità di creazione nel dispositivo HoloLens dispositivo. Ai fini di questa guida, è consigliabile creare una breve guida di test con passaggi e modelli minimi.

Per iniziare a creare guide, iniziare da qui con la panoramica [della creazione.](/dynamics365/mixed-reality/guides/authoring-overview) Oppure, per ottenere una panoramica rapida, guardare questo breve video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Facoltativo: modalità tutto schermo

La modalità tutto schermo è una modalità che consente a un amministratore IT di configurare l'interfaccia utente del menu Start in modo da visualizzare solo una singola app o la selezione di app. Un chiosco multimediale può essere applicato anche a utenti, gruppi o a livello di dispositivo specifici. e in alcuni casi escludere determinati utenti dalla modalità tutto schermo consentendo comunque l'accesso al normale menu Start.

La modalità tutto schermo include molte variabili diverse, sia nell'ambito che nelle configurazioni che possono essere impostate, nonché nei metodi di distribuzione della modalità tutto schermo nel HoloLens. A causa di tutte queste variabili, la modalità tutto schermo viene lasciata come facoltativa _per_ questa guida e non verrà rivisitata. Se si ritiene di avere la necessità di limitare le app disponibili agli utenti o si vuole ottenere altre informazioni, è possibile imparare a configurare HoloLens come chiosco [multimediale.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Facoltativo: WDAC

WDAC consente a un amministratore IT di configurare i propri dispositivi per bloccare l'avvio delle app nei dispositivi. Questo è diverso rispetto ai metodi di restrizione del dispositivo, ad esempio la modalità tutto schermo, in cui all'utente viene visualizzata un'interfaccia utente che nasconde le app nel dispositivo, ma che possono comunque essere avviate. Mentre WDAC è implementato, le app sono ancora visibili nell'elenco Tutte le app, ma WDAC impedisce che tali app e processi possano essere avviati dall'utente del dispositivo.

Per altre informazioni, vedere [Usare WDAC e Windows PowerShell per](/mem/intune/configuration/custom-profile-hololens)consentire o bloccare le app HoloLens 2 dispositivi con Microsoft Intune .

[Windows Defender Controllo dell'applicazione - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Passaggio successivo 
> [!div class="nextstepaction"]
> [Distribuzione connessa aziendale - Distribuzione](hololens2-corp-connected-deploy.md)