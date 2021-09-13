---
title: Configurare il HoloLens come chiosco multimediale
description: Informazioni su come configurare e usare una configurazione tutto schermo per bloccare le app HoloLens dispositivi.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e856ac74e959743e8d05ea6acf583700a6450373
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032559"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurare il HoloLens come chiosco multimediale

## <a name="what-is-kiosk-mode"></a>Che cos'è la modalità tutto schermo?

La modalità tutto schermo è una funzionalità in cui è possibile controllare quali applicazioni vengono visualizzate nel menu Start quando un utente accede a HoloLens. Esistono 2 scenari supportati:

1. **Modalità tutto schermo per app singola:** non viene visualizzato alcun menu Start e una singola app viene avviata automaticamente all'accesso dell'utente. <br> *Esempio usa*: un dispositivo che viene eseguito solo Dynamics 365 Guides app.
2. **Modalità tutto schermo per** più app: menu Start vengono visualizzate solo le applicazioni specificate nella configurazione della modalità tutto schermo quando un utente accede. Un'app può essere scelta per l'avvio automatico, se lo si desidera. <br> *Esempio usa*: un dispositivo che mostra solo l'app dello Store, Hub di Feedback e Impostazioni app nel menu Start.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Descrizione dell'esperienza in modalità tutto schermo quando un utente accede

La tabella seguente elenca le funzionalità delle diverse modalità tutto schermo.

| &nbsp; |Menu Start |Menu Azioni rapide |Fotocamera e video |Miracast |Cortana |Comandi vocali predefiniti |
| --- | --- | --- | --- | --- | --- | --- |
|Modalità tutto schermo per app singola |Disabled |Disabled |Disabled |Disabled   |Disabled |Abilitato* |
|Più app in modalità tutto schermo |Attivato |Abilitato*  |Disponibile*  |Disponibile* |Disponibile*   |Abilitato*  |

\*Per altre informazioni su come abilitare le funzionalità disabilitate o su come i comandi vocali interagiscono con le funzionalità disabilitate e Cortana vedere HoloLens [AUMIDs for apps](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids).

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Considerazioni generali principali prima di configurare la modalità tutto schermo

1. Determinare il tipo di account utente che accede HoloLens nel proprio ambiente: HoloLens supporta gli account Azure Active Directory (AAD), gli account Microsoft (MSA) e gli account locali. Inoltre, sono supportati anche gli account creati temporaneamente denominati guest/visitatori (solo per i dispositivi di aggiunta AAD). Per altre informazioni, [vedere Gestire l'identità utente e l'accesso per HoloLens](hololens-identity.md).
2. Determinare le destinazioni dell'esperienza in modalità tutto schermo: che si tratta di tutti, di un singolo utente, di determinati utenti o di utenti membri di gruppi di AAD e così via.
3. Per la modalità tutto schermo per più app, determinare le applicazioni da visualizzare nel menu Start. Per ogni applicazione, sarà necessario il relativo ID modello utente applicazione [(AUMID).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
4. Determinare se la modalità tutto schermo verrà applicata HoloLens tramite pacchetti di provisioning di runtime o server DIS (Mobile Device Management).

## <a name="security-considerations"></a>Considerazioni relative alla sicurezza

La modalità tutto schermo non deve essere considerata un metodo di sicurezza, ma come mezzo per controllare l'esperienza di avvio all'accesso utente. È possibile combinare l'esperienza in modalità tutto schermo con le opzioni indicate di seguito in caso di esigenze specifiche relative alla sicurezza:

- Quando Impostazioni'app è configurata per la visualizzazione in modalità tutto schermo e si vuole controllare quali pagine vengono visualizzate nell'app Impostazioni, vedere Visibilità Impostazioni [pagina](settings-uri-list.md)
- Quando si vuole controllare l'accesso a determinate funzionalità hardware, ad esempio fotocamera, Bluetooth e così via, per determinate app e così via, vedere Criteri in Policy CSP supported by HoloLens 2 - Windows Client Management ( Criteri in Policy [CSP](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)supportati da HoloLens 2 - Windows Client Management ). Per informazioni, vedere [Le restrizioni comuni per](hololens-common-device-restrictions.md) i dispositivi.
- La modalità tutto schermo non blocca l'avvio di altre app (configurate come parte dell'esperienza tutto schermo). Quando si vuole bloccare completamente l'avvio di determinate app/processi in HoloLens, vedere Usare il controllo delle applicazioni Windows Defender nei dispositivi HoloLens 2 [in Microsoft Intune - Azure](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Considerazioni tecniche chiave per la modalità tutto schermo per HoloLens

Si applica solo se si prevede di usare pacchetti di provisioning di runtime o di creare manualmente configurazioni in modalità tutto schermo. La configurazione della modalità tutto schermo usa una struttura gerarchica basata su XML:

- Un profilo di accesso assegnato definisce le applicazioni visualizzate nel menu Start in modalità tutto schermo. È possibile definire più profili nella stessa struttura XML, a cui è possibile fare riferimento in un secondo momento.
- Una configurazione di accesso assegnata fa riferimento a un profilo e a uno o più utenti di destinazione del profilo, ad esempio un utente specifico, un gruppo o un visitatore di AAD e così via. È possibile definire più configurazioni nella stessa struttura XML a seconda della complessità degli scenari di utilizzo (vedere la sezione scenari supportati più avanti).
- Per altre informazioni, vedere [AssignedAccess CSP](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Scenari supportati per la modalità tutto schermo in base al tipo di identità

Vedere [i collegamenti di](hololens-kiosk-reference.md#kiosk-xml-code-samples) riferimento per esempi basati sullo scenario e sull'aggiornamento in base alle esigenze prima di copiare e incollare.

> [!NOTE]
> Usare XML solo se non si usa l'interfaccia utente di Intune per creare la configurazione della modalità tutto schermo.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Per gli utenti che affezionano l'accesso come account locale o come account del servizio clienti

| **Esperienza in modalità tutto schermo desiderata** | **Configurazione della modalità tutto schermo consigliata** | **Modalità di configurazione**  | **Osservazioni:** |
| --- | --- | --- | --- |
| Ogni utente che accede ottiene l'esperienza tutto schermo. | [Configurare un profilo di accesso assegnato globale per più app](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modello personalizzato](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisioning di runtime - App multipla](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | L'accesso assegnato globale [richiede 20H2 e build più nuove](hololens-release-notes.md#windows-holographic-version-20h2) |
| L'utente specifico che accede ottiene l'esperienza tutto schermo.  | [Configurare un profilo di accesso assegnato a una o più app (in base alle esigenze) specificando il nome di un utente specifico.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Vedere le opzioni supportate di seguito.](#steps-in-configuring-kiosk-mode-for-hololens) | Per la modalità tutto schermo per app singole, solo l'account utente locale o l'account MSA è supportato HoloLens. <br> Per la modalità tutto schermo per più app, solo l'account MSA o l'account AAD è supportato HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Per gli utenti che effettuano l'accesso come account AAD

| **Esperienza in modalità tutto schermo desiderata** | **Configurazione della modalità tutto schermo consigliata** | **Modalità di configurazione** | **Osservazioni:** |
| --- | --- | --- | --- |
| Ogni utente che accede ottiene l'esperienza tutto schermo. | [Configurare un profilo di accesso assegnato globale per più app](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modello personalizzato](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisioning di runtime - App multipla](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | L'accesso assegnato globale [richiede 20H2 e build più nuove](hololens-release-notes.md#windows-holographic-version-20h2) |
| Ogni utente che accede ottiene l'esperienza tutto schermo ad eccezione di determinati utenti. | [Configurare più profili di accesso assegnato globale dell'app escludendo determinati utenti (che devono essere proprietari dei dispositivi).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune modello personalizzato](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisioning di runtime - App multipla](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | L'accesso assegnato globale [richiede 20H2 e build più nuove](hololens-release-notes.md#windows-holographic-version-20h2) |
| Ogni utente di AAD ottiene un'esperienza in modalità tutto schermo separata specifica per tale utente. | [Configurare la configurazione dell'accesso assegnato per ogni utente specificando il nome dell'account AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune modello personalizzato](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisioning di runtime - App multipla](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Gli utenti in gruppi di AAD diversi possono sperimentare la modalità tutto schermo solo per il proprio gruppo. | [Configurare la configurazione dell'accesso assegnato per ogni gruppo AAD desiderato.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune modello personalizzato](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisioning di runtime - App multipla](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Quando un utente accede e HoloLens è connesso a Internet, se viene rilevato che tale utente è membro del gruppo AAD per cui esiste la configurazione della modalità tutto schermo, l'utente ottiene l'esperienza di chiosco multimediale per il gruppo AAD. <br> • [Se non è disponibile Internet quando l'utente](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) esegue l'accesso, l'utente HoloLens comportamento della modalità di errore. <br> • Se la disponibilità di Internet non è garantita quando l'utente esegue l'accesso e deve essere usato il chiosco multimediale basato su gruppi di AAD, è consigliabile usare [AADGroupMembershipCacheValidityInDayspolicy.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) <br> • Per un'esperienza ottimale con i gruppi di AAD durante l'accesso, è consigliabile usare [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
| Gli utenti che devono usare i HoloLens per scopi temporanei ottengono un'esperienza in modalità tutto schermo. | [Configurare la configurazione dell'accesso assegnato per i visitatori](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune modello personalizzato](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisioning in fase di esecuzione - App singola](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • L'account utente temporaneo viene creato automaticamente HoloLens all'accesso e viene rimosso quando l'utente temporaneo si disconnette. <br> • Valutare la possibilità di [abilitare i criteri di accesso automatico dei visitatori.](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Passaggi per la configurazione della modalità tutto schermo per HoloLens

Le configurazioni della modalità tutto schermo possono essere create e applicate nei modi seguenti:

1. Con l'interfaccia utente del server MDM, ad esempio i modelli in modalità tutto schermo di Intune o le configurazioni URI OMA personalizzate, che vengono quindi applicate in modalità remota HoloLens.
2. Con i pacchetti di provisioning di runtime, che vengono quindi applicati direttamente HoloLens.

Di seguito sono riportati i modi per configurare e selezionare la scheda corrispondente al processo che si desidera usare.

1. [Microsoft Intune app singola in modalità tutto schermo](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune di più app in modalità tutto schermo](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune modello personalizzato](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Provisioning in fase di esecuzione - App multipla](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Provisioning in fase di esecuzione - App singola](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>In che modo gli account dei visitatori possono accedere automaticamente all'esperienza in modalità tutto schermo?

Nelle build Windows [Holographic, versione 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e versioni successiva:

- Le configurazioni AAD e Non-ADD supportano entrambi gli account visitatore abilitati per l'accesso automatico per le modalità tutto schermo.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>L'esperienza in modalità tutto schermo HoloLens (prima generazione)?

La modalità tutto schermo è disponibile solo se il dispositivo ha Windows Holographic for Business. Tutti HoloLens 2 vengono forniti con Windows Holographic for Business e non sono presenti altre edizioni. Ogni HoloLens 2 dispositivo è in grado di eseguire la modalità tutto schermo predefinita.

HoloLens dispositivi di prima generazione devono essere aggiornati sia in termini di build del sistema operativo che di edizione del sistema operativo. Ecco altre informazioni sull'aggiornamento di un HoloLens (prima generazione) [alla Windows Holographic for Business](hololens1-upgrade-enterprise.md) edizione. Per aggiornare un dispositivo HoloLens (prima generazione) per l'uso della modalità tutto schermo, è prima di tutto necessario assicurarsi che il dispositivo venga eseguito Windows 10 versione 1803 o successiva. Se è stato usato lo strumento di ripristino dei dispositivi di Windows per ripristinare la build predefinita del dispositivo HoloLens (prima generazione) o se sono stati installati gli aggiornamenti più recenti, il dispositivo è pronto per la configurazione.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Come usare il portale di dispositivi per configurare la modalità tutto schermo in ambienti non di produzione?

Configurare il dispositivo [HoloLens usare il Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). Device Portal è un server Web in HoloLens a cui è possibile connettersi da un browser Web nel PC.

 > [!CAUTION]
 > Quando si configura HoloLens per l'uso Portale di dispositivi, è necessario abilitare la modalità sviluppatore nel dispositivo. Modalità sviluppatore in un dispositivo con Windows Holographic for Business consente di eseguire il side load delle app. Tuttavia, questa impostazione crea il rischio che un utente possa installare app che non sono state certificate dal Microsoft Store. Gli amministratori possono bloccare la possibilità di abilitare la modalità sviluppatore usando l'impostazione **ApplicationManagement/AllowDeveloper Unlock** nel provider di servizi di configurazione [Criteri.](/windows/client-management/mdm/policy-configuration-service-provider) [Ulteriori informazioni sulla modalità sviluppatore.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

La modalità tutto schermo può essere impostata tramite l'API REST di Portale di dispositivi eseguendo un'operazione POST su /api/holographic/kioskmode/settings con un parametro della stringa di query obbligatorio ("kioskModeEnabled" con un valore "true" o "false") e un parametro facoltativo ("startupApp" con un valore di un nome di pacchetto). Tenere presente che Portale di dispositivi è destinato solo agli sviluppatori e non deve essere abilitato nei dispositivi non sviluppatori. L'API REST è soggetta a modifiche negli aggiornamenti o nelle versioni future.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problema: nel menu Start non viene visualizzata alcuna app in modalità tutto schermo

**Sintomi**

Quando si verificano errori durante l'applicazione della modalità tutto schermo, viene visualizzato il comportamento seguente:

- Prima di Windows Holographic, la versione 20H2 - HoloLens mostra tutte le applicazioni nel menu Start.
- Windows Holographic versione 20H2: se un dispositivo ha una configurazione in modalità tutto schermo, ovvero una combinazione di accesso assegnato a livello globale e accesso assegnato ai membri del gruppo AAD, se la determinazione dell'appartenenza al gruppo AAD non riesce, l'utente non visualizza alcun elemento nel menu Start.

    ![Immagine dell'aspetto della modalità tutto schermo in caso di errore.](images/hololens-kiosk-failure-behavior.png )

- A partire [da Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)la modalità tutto schermo cerca Accesso assegnato globale prima di visualizzare un menu Start vuoto. Se si verificano errori durante la modalità tutto schermo del gruppo di AAD, l'esperienza della modalità tutto schermo verrà tornati a una configurazione globale per chiosco multimediale(se presente).

**Passaggi per la risoluzione dei problemi**

- Verificare che l'AUMID dell'app sia specificato correttamente e che non contenga versioni. Per [esempi, vedere HoloLens AUMID](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) per le app della posta in arrivo.
- Assicurarsi che l'applicazione sia installata nel dispositivo per tale utente.
- Se la configurazione della modalità tutto schermo è basata su gruppi di AAD, assicurarsi che la connettività Internet sia presente quando l'utente di AAD esegue l'accesso. Se si desidera, configurare i criteri [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) in modo che funzioni anche senza Internet.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problema - La compilazione di un pacchetto con la modalità tutto schermo non è riuscita

**Sintomi**

Viene visualizzata una finestra di dialogo simile alla seguente.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Passaggi per la risoluzione dei problemi**

1. Fare clic sull'hyper link visualizzato come nella finestra di dialogo precedente.
1. Aprire ICD.log in un editor di testo e il relativo contenuto dovrebbe indicare l'errore.

> [!NOTE]
> Se sono stati effettuati diversi tentativi, controllare i timestamp nel log. In questo modo sarà possibile controllare solo i problemi correnti.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problema: il pacchetto di provisioning è stato compilato correttamente ma non è stato possibile applicarlo.

**Sintomi**

Viene visualizzato un errore durante l'applicazione del pacchetto di provisioning in Hololens

**Passaggi per la risoluzione dei problemi**

1. Passare alla cartella in cui si trova Windows progetto di Progettazione configurazione per il pacchetto di provisioning di runtime.
1. Aprire ICD.log e assicurarsi che non siano presenti errori nel log durante la compilazione del pacchetto di provisioning. Alcuni errori non vengono visualizzati durante la compilazione, ma vengono comunque registrati in ICD.log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problema: l'accesso assegnato a più app al gruppo di AAD non funziona

**Sintomi**

All'accesso utente di AAD, il dispositivo non passa alla modalità tutto schermo

**Passaggi per la risoluzione dei problemi**

- Verificare che in Assigned Access configuration XML (XML configurazione accesso assegnato) sia usato il GUID del gruppo AAD di cui è membro l'utente connesso e non il GUID dell'utente AAD.
- Verificare che nel portale di Intune l'utente di AAD sia effettivamente visualizzato come membro del gruppo AAD di destinazione.
