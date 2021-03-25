---
title: Guida alla distribuzione - HoloLens 2 connesso all'azienda con guide di Dynamics 365 - Configurare
description: Scopri come configurare le configurazioni per distribuire i dispositivi HoloLens 2 su una rete connessa aziendale con le guide di Dynamics 365.
keywords: HoloLens, gestione, corporate connected, Guide dynamics 365, AAD, Azure AD, MDM, Gestione dispositivi mobili
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448572"
---
# <a name="configure---corporate-connected-guide"></a>Configure - Corporate Connected Guide

## <a name="azure-users-and-groups"></a>Utenti e gruppi di Azure

Azure e Intune tramite tale estensione, usa utenti e gruppi per assegnare configurazioni e licenze. Per convalidare questo flusso di distribuzione ed essere in grado di verificare che sia possibile creare e gestire una guida, è&#39;necessario un account utente.

Possiamo creare un singolo gruppo di utenti specifico per l'assegnazione delle licenze.

Se non si&#39;avere già accesso a due account Azure AD in un gruppo di utenti, è possibile usare; ecco le guide introduttive per:

- [Come creare un utente](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Come creare un gruppo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Aggiungere utenti a un gruppo:](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) aggiungere utenti creati per creare un gruppo
- [Configurare Azure AD per consentire a un gruppo di utenti](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) di aggiungere dispositivi: verificare che il nuovo gruppo di utenti abbia l'autorizzazione per registrare i dispositivi in Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Registrazione automatica in HoloLens 2

Per garantire un'esperienza senza problemi, è possibile configurare Azure Active Directory Join (AADJ) e La registrazione automatica in Intune per dispositivi HoloLens 2. In questo modo gli utenti possono immettere le credenziali di accesso dell'organizzazione durante la configurazione guidata e registrarsi automaticamente con Azure AD e registrare il dispositivo in MDM.

Usando [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)è possibile selezionare i servizi ed esplorare alcune pagine fino a quando non si seleziona Ottieni una versione di valutazione Premium. È possibile notare che azure Active Directory Premium 1 e 2 è sufficiente per la registrazione automatica P1. Possiamo selezionare Intune e selezionare l'ambito utente per la registrazione automatica e selezionare il gruppo creato in precedenza.

Per i dettagli e i passaggi completi, leggere la guida [su come abilitare la registrazione automatica per Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Connettività Wi-Fi aziendale

Le Wi-Fi aziendali richiedono in genere l'autenticazione basata su certificato per i clienti che usano HoloLens 2. Sarà necessario distribuire tali certificati utilizzando un'infrastruttura di certificato SCEP (Simple Certificate Enrollment Protocol) o PKCS (Public Key Cryptography Standard) integrata con la soluzione MDM. L'uso di Intune per Wi-Fi profili, certificati e impostazioni proxy consente di creare un'esperienza senza problemi per gli utenti finali.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Distribuire certificati e Wi-Fi certificati

Per distribuire certificati e profili tramite Microsoft Endpoint Manager, eseguire la procedura seguente:

1. Creare un profilo per ognuno dei certificati radice e intermedio (vedere [Create trusted certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Ognuno di questi profili deve avere una descrizione che includa una data di scadenza nel formato GG/MM/AAAA. 

    > [!CAUTION]
    > **I profili certificato senza una data di scadenza non verranno distribuiti.**

2.  Creare un profilo per ognuno dei certificati SCEP o PKCS. vedere [Creare un profilo di certificato SCEP attendibile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile). Ognuno di questi profili deve contenere una descrizione che includa una data di scadenza nel formato gg/MM/AAAA. 

    > [!CAUTION]
    > **I profili di certificato senza data di scadenza non verranno distribuiti.**

    > [!Note]
    > Poiché HoloLens 2 è considerato per molti come un dispositivo condiviso, ad esempio più utenti per dispositivo, è consigliabile distribuire certificati dispositivo anziché certificati utente per l'autenticazione Wi-Fi ove possibile.

3.  Crea un profilo per la rete Wi-Fi aziendale (vedi Impostazioni [Wi-Fi per i dispositivi Windows 10 e versioni successive).](https://docs.microsoft.com/intune/wi-fi-settings-windows) All'interno Wi-Fi, è possibile scegliere di utilizzare le impostazioni proxy all'interno dell'organizzazione.
 
    Opzioni:
    - **Nessuno:** nessuna impostazione proxy configurata.
    - **Configurazione manuale:** immettere l'indirizzo **IP del server proxy** e il relativo numero di **porta.**
    - **Configurazione automatica:** immettere l'URL che punta a uno script di configurazione automatica del proxy (PAC). Ad esempio, immettere *http://proxy.contoso.com/proxy.pac* .

    Per ulteriori informazioni sui file PAC, vedere [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opens a non-Microsoft site).
 
    > [!Note]
    > Se possibile, è consigliabile il profilo Wi-Fiassegnato ai gruppi di dispositivi anziché ai gruppi di utenti.
     
    > [!Tip]
    > È anche possibile esportare un profilo Wi-Fi funzionante da un PC con Windows 10 nella rete aziendale. Questa esportazione crea un file XML con tutte le impostazioni correnti. Quindi, importare il file in Intune e usarlo come profilo Wi-Fi per i dispositivi HoloLens 2. Vedi [Esportare e importare Wi-Fi per i dispositivi Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

1.  [Assegna](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) i profili di dispositivo al gruppo di dispositivi HoloLens.

2.  [Monitorare](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) i profili dei dispositivi in Intune.

In caso di problemi con i Wi-Fi, fare riferimento a Risolvere Wi-Fi profili di configurazione dei [dispositivi in Intune.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Risoluzione dei problemi di accesso a Internet esterno quando Corp è connesso
Quando i servizi tentano di non passare attraverso un proxy impostato, possono tentare di connettersi attraverso il firewall. Puoi aggiungere un elenco di specifiche degli endpoint alle regole del firewall per risolvere questi problemi.

Se sei bloccato alle porte del firewall, abilita alcuni [endpoint comuni](https://docs.microsoft.com/hololens/hololens-offline) per HoloLens.

È inoltre possibile abilitare le porte specifiche delle Guide: URL accessibili da Internet necessari per [la connettività Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Distribuzione di app

La distribuzione di un'app LOB tramite MDM è un metodo facilmente scalabile che può essere distribuito automaticamente nei dispositivi al momento della registrazione in un gruppo creato.

Se stai ancora sviluppando le tue app o non ne hai ancora una, puoi usare un'app di esempio dell'hub degli esempi MRTK. Questa app di esempio è pronta per l'uso e non richiede l'uso di Unity o Visual Studio. [Scarica l'app Esempi MRTK .](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Se preferisci usare la tua app o sei interessato allo sviluppo di app per la realtà mista, puoi consultare la documentazione per sviluppatori [mixed reality.](https://docs.microsoft.com/windows/mixed-reality/design/design)

> [!NOTE]
> I requisiti di sistema per i dispositivi HoloLens si basano sull'architettura della build dell'app. I dispositivi HoloLens 2 usano ARM architettura. Durante la compilazione delle app in Visual Studio, assicurati di aver selezionato l'architettura corretta per il dispositivo e di includere le dipendenze necessarie.

> [!IMPORTANT]
> Quando si distribuiscono app LOB, è importante caricare anche il certificato in Intune e assegnarlo allo stesso gruppo destinato all'uso dell'app o che non verrà installato correttamente.

### <a name="upload-and-assign-the-app"></a>Caricare e assegnare l'app

1. Passare [all'interfaccia di amministrazione di MEM](https://endpoint.microsoft.com/#home).

2. Seleziona **App**  ->  **Tutte le app** e seleziona il pulsante **+** Aggiungi.

3. In Altro seleziona **App line-of-business.** Fare **clic su seleziona**.

4. Seleziona il file del pacchetto dell'app, questo è il file APPXBUNDLE o nel nostro caso di questo esempio l'app è _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.

5. Si riceverà una notifica delle dipendenze mancanti. In questo caso, è necessario caricare _Microsoft.VCLibs.ARM.14.00.appx_. Cercarlo in **Selezionare un file**.

6. Seleziona OK.

7. Nella schermata successiva, i campi obbligatori verranno compilati automaticamente. Seleziona **Avanti**.

8. In Obbligatorio aggiungi il gruppo creato in precedenza per rendere l'app necessaria per il gruppo. In questo modo l'app verrà scaricata automaticamente nei dispositivi registrati nel gruppo. Seleziona **Avanti**.

9. Seleziona **Crea**.

Altre informazioni: [Assegnare app ai gruppi in Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guide all'installazione: licenze dell'applicazione, dataverse e creazione

Per usare le guide di Dynamics 365, è necessario eseguire alcune operazioni di preparazione. Ci sono tre aree in cui è necessario prepararsi; utenti, dataverse e le guide stesse.

### <a name="users-and-application-licenses"></a>Utenti e licenze applicazioni

Per usare guide, gli utenti dovranno usare un account Azure AD, configurato in precedenza in questa guida.

Dovrai anche assegnare la licenza Dynamics 365 Guides all'utente che hai creato. Eseguire questa operazione dall'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/AdminPortal/Home) Assegnare inoltre la licenza all'account Azure principale.

Segui [questa breve guida con](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) le immagini per istruzioni dettagliate sull'applicazione delle licenze dell'applicazione.

### <a name="set-up-the-dataverse"></a>Configurare Dataverse

Per configurare [un ambiente di produzione,](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) è necessario soddisfare due prerequisiti. È necessario disporre del [**ruolo amministratore**](https://docs.microsoft.com/power-platform/admin/database-security) di  **sistema**  e disporre di una licenza di [**Power Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (o di una licenza di [**Dynamics 365 Guides**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) che include una licenza di Power Apps). Se seguendo questa guida hai creato Azure AD, soddisfi i requisiti dei ruoli per l'amministratore di sistema. Nel passaggio precedente è stata assegnata anche una licenza guide.

All'interno di questa [guida per creare un ambiente Microsoft Dataverse:](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)

1. Iniziare usando [l'interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/environments) e creando un nuovo ambiente.
2. Quando si crea **il nuovo ambiente**, per il **tipo**&#39;verrà selezionato **Produzione**.
3. È importante attivare o disattivare **Crea un database per questo ambiente?**  su **Sì.**
4. Nella finestra  **di dialogo**  Aggiungi database imposta l'opzione Abilita app  **Dynamics 365**  su  **Sì.**

È necessario aumentare le dimensioni massime dei file degli elementi nel dataverse. L'aumento delle dimensioni massime dei file ti consentirà di caricare modelli 3D o file video più grandi che userai più avanti nelle guide. Seguire una breve guida [per modificare le dimensioni massime del file di caricamento.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Infine, è necessario installare e [configurare la soluzione](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). [Nell'interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/environments)seleziona **Risorse**App   \ &gt; **Dynamics 365,** seleziona **Guide dynamics 365** nell'elenco e quindi seleziona **Installa**.  

Devi aggiungere [un ruolo di sicurezza Guide](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) prima di poter usare le app.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Creare una guida di test nel PC tramite creazione

Quando crei guide, inizi sempre sul PC. Creazione dei passaggi, selezione dei modelli e come ancorare la guida. A questo verrà seguito l'inserimento del contenuto per la guida in un secondo momento in modalità di creazione e modifica nel dispositivo HoloLens. Ai fini di questa guida, è consigliabile creare una breve guida di test con passaggi e modelli minimi.

Se vuoi iniziare a imparare a creare guide, inizia da qui con la [panoramica della creazione.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview) In caso contrario, guardare questo breve video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Facoltativo: modalità tutto schermo

La modalità tutto schermo è una modalità che consente a un amministratore IT di configurare l'interfaccia utente del menu Start in modo da visualizzare solo una singola app o una selezione di app. Un chiosco multimediale può essere applicato anche a utenti, gruppi o a livello di dispositivo specifici. e in alcuni casi escludere determinati utenti dal chiosco multimediale consentendo loro comunque l'accesso al normale menu start.

La modalità tutto schermo ha molte variabili diverse, sia nell'ambito che nelle configurazioni che possono essere impostate, nonché nei metodi di distribuzione del chiosco multimediale in HoloLens. A causa di tutte queste variabili, la modalità tutto schermo viene lasciata facoltativa _per_ questa guida e non verrà rivisitata. Se si ritiene che l'azienda abbia la necessità di limitare le app disponibili agli utenti o di saperne di più, è possibile imparare a configurare [HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)come chiosco multimediale.

## <a name="optional-wdac"></a>Facoltativo: WDAC

WDAC consente a un amministratore IT di configurare i propri dispositivi per bloccare l'avvio delle app nei dispositivi. Questo è diverso rispetto ai metodi di restrizione del dispositivo, ad esempio la modalità tutto schermo, in cui all'utente viene presentata un'interfaccia utente che nasconde le app nel dispositivo, ma può comunque essere avviata. Mentre WDAC è implementato, le app sono ancora visibili nell'elenco Tutte le app, ma WDAC impedisce che tali app e processi possano essere avviati dall'utente del dispositivo.

Per ulteriori informazioni, vedere Usare WDAC e Windows PowerShell per consentire o bloccare le app nei dispositivi [HoloLens 2 con Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

[Controllo applicazioni di Windows Defender](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Passaggio successivo 
> [!div class="nextstepaction"]
> [Distribuzione connessa aziendale - Distribuzione](hololens2-corp-connected-deploy.md)