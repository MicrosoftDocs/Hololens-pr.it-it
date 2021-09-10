---
title: Gestire l'identità utente e l'account di accesso per HoloLens
description: Informazioni su come gestire l'identità utente, il supporto multi-utente, la sicurezza, l'autenticazione aziendale e l'accesso per HoloLens dispositivi.
keywords: HoloLens, utente, account, AAD, Azure AD, adfs, account Microsoft, msa, credenziali, riferimento
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: qianw211
ms.author: v-qianwen
ms.date: 8/13/2021
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c2fd7c8ee82fbf70b9eaa2b5eee1d73e1235d8b5
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427905"
---
# <a name="manage-user-identity-and-login-for-hololens"></a>Gestire l'identità utente e l'account di accesso per HoloLens

> [!NOTE]
> Questo articolo è un riferimento tecnico per professionisti IT e appassionati di tecnologia. Se si stanno cercando istruzioni HoloLens configurazione, leggere "[Setting up your HoloLens (1st gen)](hololens1-start.md)" (Configurazione del HoloLens (prima generazione) " o " Setting up your[HoloLens 2](hololens2-start.md)".

## <a name="lets-talk-about-setting-up-user-identity-for-hololens-2"></a>Si esamini la configurazione dell'identità utente per HoloLens 2

Come altri Windows, HoloLens funziona sempre in un contesto utente. Esiste sempre un'identità utente. HoloLens considera l'identità quasi allo stesso modo di un Windows 10 dispositivo. L'accesso durante l'installazione crea un profilo utente in HoloLens che archivia app e dati. Lo stesso account fornisce anche l'accesso Single Sign-On per le app, ad esempio Edge o Dynamics 365 Remote Assist, usando le API Windows Account Manager. 

HoloLens supporta diversi tipi di identità utente. È possibile scegliere uno qualsiasi di questi tre tipi di account, ma è consigliabile Azure AD perché è ideale per la gestione dei dispositivi. Solo Azure AD account supportano più utenti. 

| Tipo di identità | Account per dispositivo | Opzioni di autenticazione |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Provider di credenziali Web di Azure</li><li>App Authenticator Azure</li><li>Dati biometrici (Iris) &ndash; HoloLens 2 solo<sup>2</sup> </li><li>Chiave di sicurezza FIDO2</li><li>PIN &ndash; facoltativo per HoloLens (prima generazione), obbligatorio per HoloLens 2</li><li>Password</li></ul> |
| [Account Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Solo dati biometrici (Iris) &ndash; HoloLens 2</li><li>PIN &ndash; facoltativo per HoloLens (prima generazione), obbligatorio per HoloLens 2</li><li>Password</li></ul> |
| [Account locale](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Password |

Gli account connessi al cloud (Azure AD e MSA) offrono più funzionalità perché possono usare i servizi di Azure.  
> [!IMPORTANT]
> 1 : Azure AD Premium non è necessario accedere al dispositivo. Tuttavia, è necessario per altre funzionalità di una distribuzione basata sul cloud a tocco ridotto, ad esempio la registrazione automatica e Autopilot.

> [!NOTE]
> 2 - Mentre un HoloLens 2 può supportare fino a 64 account Azure AD, solo 31 di questi account possono registrarsi nell'autenticazione Iris. Questo è allineato con altre opzioni [di autenticazione biometrica per Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

> [!IMPORTANT]
> 3 - Un account locale può essere configurato in un dispositivo solo tramite un pacchetto di provisioning durante la Configurazione [manuale](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)e non può essere aggiunto in un secondo momento nell'app impostazioni. Se si desidera usare un account locale in un dispositivo già configurato, è necessario eseguire il [reflash](hololens-recovery.md) o reimpostare il dispositivo.

## <a name="setting-up-users"></a>Configurazione degli utenti

Esistono due modi per configurare un nuovo utente nel HoloLens. Il modo più comune è durante HoloLens'esperienza di configurazione. Se si Azure Active Directory, [gli altri utenti possono accedere dopo](#setting-up-multi-user-support-azure-ad-only) la Configurazione Azure AD configurazione. HoloLens dispositivi che sono inizialmente impostati con un account del servizio gestiti o un account locale durante la Configurazione remota non supporteranno più utenti. Vedere Configurazione del [HoloLens (prima generazione)](hololens1-start.md) o [HoloLens 2](hololens2-start.md).

Se si usa un account aziendale o aziendale per accedere a HoloLens, HoloLens si iscrive all'infrastruttura IT dell'organizzazione. Questa registrazione consente all'amministratore IT di configurare gestione di dispositivi mobili (MDM) per inviare criteri di gruppo al HoloLens.

Come Windows in altri dispositivi, l'accesso durante l'installazione crea un profilo utente nel dispositivo. Il profilo utente archivia app e dati. Lo stesso account fornisce anche l'accesso Single Sign-On per le app, ad esempio Edge o Microsoft Store, usando le API Windows Account Manager.

Per impostazione predefinita, come per gli altri Windows 10, sarà necessario accedere di nuovo quando HoloLens riavvia o riprende dalla modalità standby. È possibile usare l Impostazioni app per modificare questo comportamento oppure il comportamento può essere controllato da Criteri di gruppo.

### <a name="linked-accounts"></a>Account collegati

Come nella versione desktop di Windows, è possibile collegare altre credenziali dell'account Web all'account HoloLens. Questo tipo di collegamento semplifica l'accesso alle risorse all'interno o all'interno delle app (ad esempio lo Store) o combina l'accesso alle risorse personali e di lavoro. Dopo aver connesso un account al dispositivo, è possibile concedere l'autorizzazione per usare il dispositivo alle app in modo che non sia necessario accedere singolarmente a ogni app.

Il collegamento degli account non separa i dati utente creati nel dispositivo, ad esempio immagini o download.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configurazione del supporto multi-utente (solo Azure AD)

HoloLens supporta più utenti dallo stesso tenant Azure AD. Per usare questa funzionalità, è necessario usare un account appartenente all'organizzazione per configurare il dispositivo. Successivamente, altri utenti dello stesso tenant possono accedere al dispositivo dalla schermata di accesso o toccando il riquadro utente nel pannello Start. È possibile accedere a un solo utente alla volta. Quando un utente esegue l'accesso, HoloLens l'utente precedente. 

>[!IMPORTANT]
> Il primo utente nel dispositivo è considerato il proprietario del dispositivo, tranne nel caso di Azure AD, altre informazioni sui [proprietari dei dispositivi.](security-adminless-os.md#device-owner)

Tutti gli utenti possono usare le app installate nel dispositivo. Tuttavia, ogni utente ha i propri dati e preferenze dell'app. La rimozione di un'app dal dispositivo la rimuove per tutti gli utenti.  

I dispositivi impostati con Azure AD non consentiranno l'accesso al dispositivo con un account Microsoft. Tutti gli account successivi usati devono Azure AD dallo stesso tenant del dispositivo. È comunque possibile [accedere con un account Microsoft](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) alle app che lo supportano, ad esempio il Microsoft Store. Per passare dall'Azure AD account utente agli account Microsoft per l'accesso al dispositivo, è necessario [eseguire il reflash del dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (prima generazione)** ha iniziato a supportare più utenti Azure AD nell'aggiornamento di Windows 10 aprile [2018](/windows/mixed-reality/release-notes-april-2018) come parte [di Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-are-listed-on-sign-in-screen"></a>Più utenti sono elencati nella schermata di accesso

In precedenza la schermata di accesso mostrava solo l'utente connesso più di recente e un punto di ingresso "Altro utente". Sono stati ricevuti commenti e suggerimenti dei clienti che non sono sufficienti se più utenti hanno eseguito l'accesso al dispositivo. Era comunque necessario digitare nuovamente il nome utente e così via.

Introdotto in [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)quando si seleziona Altro utente a destra del campo di immissione PIN, nella schermata di accesso verranno visualizzati più utenti che hanno eseguito l'accesso al dispositivo in precedenza.  In questo modo gli utenti possono selezionare il proprio profilo utente e quindi accedere usando le Windows Hello credenziali. È anche possibile aggiungere un nuovo utente al dispositivo da questa pagina **di altri** utenti tramite il pulsante **Aggiungi account.**

Nel menu **Altri utenti** il pulsante **Altri** utenti visualizza l'ultimo utente che ha eseguito l'accesso al dispositivo. Selezionare questo pulsante per tornare alla schermata di accesso dell'utente.

![Impostazione predefinita della schermata di accesso.](./images/multiusers1.jpg)

<br>

![Schermata di accesso per altri utenti.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Rimozione di utenti

È possibile rimuovere un utente dal dispositivo selezionando account **Impostazioni**  >    >  **Altre persone.** Questa azione recupera anche spazio rimuovendo tutti i dati dell'app dell'utente dal dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Uso dell'accesso Single Sign-On all'interno di un'app

Gli sviluppatori di app possono sfruttare le identità collegate in HoloLens usando le API di gestione account di [Windows](/uwp/api/Windows.Security.Authentication.Web.Core), esattamente come si farebbe con altri dispositivi Windows. Alcuni esempi di codice per queste API sono disponibili in GitHub: Esempio di [gestione degli account Web.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Qualsiasi interruzione dell'account che potrebbe verificarsi, ad esempio la richiesta del consenso dell'utente per le informazioni sull'account, l'autenticazione a due fattori e così via, deve essere gestita quando l'app richiede un token di autenticazione.

Se l'app richiede un tipo di account specifico che non è stato collegato in precedenza, l'app può chiedere al sistema di richiedere all'utente di aggiungerne uno. Questa richiesta attiva il riquadro delle impostazioni dell'account per l'avvio come elemento figlio modale dell'app. Per le app 2D, il rendering di questa finestra viene eseguito direttamente al centro dell'app. Per le app Unity, questa richiesta porta brevemente l'utente fuori dall'app olografica per eseguire il rendering della finestra figlio. Per informazioni sulla personalizzazione dei comandi e delle azioni in questo riquadro, vedere [Classe WebAccountCommand.](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Enterprise e altre autenticazioni

Se l'app usa altri tipi di autenticazione, ad esempio NTLM, Basic o Kerberos, è possibile usare l'interfaccia utente delle credenziali di [Windows](/uwp/api/Windows.Security.Credentials.UI) per raccogliere, elaborare e archiviare le credenziali dell'utente. L'esperienza utente per la raccolta di queste credenziali è simile ad altre interruzioni dell'account basato sul cloud e viene visualizzata come app figlio sopra l'app 2D o sospende brevemente un'app Unity per visualizzare l'interfaccia utente.

## <a name="deprecated-apis"></a>API deprecate

Uno dei modi in cui lo sviluppo per HoloLens è diverso dallo sviluppo per Desktop è che l'API [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) non è completamente supportata. Anche se l'API restituisce un token se l'account primario è valido, gli interrupt come quelli descritti in questo articolo non visualizzano alcuna interfaccia utente per l'utente e non riescono a autenticare correttamente l'account.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Windows Hello for Business è supportato in HoloLens (prima generazione)?

Windows Hello for Business (che supporta l'uso di un PIN per l'accesso) è supportato per HoloLens (prima generazione). Per consentire Windows Hello l'accesso al PIN aziendale HoloLens:

1. Il HoloLens deve essere [gestito da MDM.](hololens-enroll-mdm.md)
1. È necessario abilitare Windows Hello per le aziende per il dispositivo. ([Vedere le istruzioni per Microsoft Intune.](/intune/windows-hello))
1. In HoloLens l'utente può quindi usare Impostazioni Opzioni di accesso  >    >  **Aggiungi PIN** per configurare un PIN.

> [!NOTE]
> Gli utenti che a loro account Microsoft possono anche configurare un PIN **in** Impostazioni Opzioni di accesso  >    >  **Aggiungi PIN.** Questo PIN è associato a [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), anziché Windows Hello [for Business](/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Come viene implementata l'autenticazione biometrica Iris HoloLens 2?

HoloLens 2 supporta l'autenticazione Iris. Iris è basato sulla Windows Hello ed è supportato per l'uso sia da Azure Active Directory che dagli account Microsoft. Iris viene implementato come altre tecnologie Windows Hello e ottiene la sicurezza biometrica FAR di [1/100.000.](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)

Per altre [informazioni, vedere le](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) specifiche e i requisiti biometrici Windows Hello informazioni. Altre informazioni su [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) e [Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="where-is-iris-biometric-information-stored"></a>Dove vengono archiviate le informazioni biometriche Iris?

Le informazioni biometriche Iris vengono archiviate in locale in ogni HoloLens per [Windows Hello specifiche](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored). Non è condiviso ed è protetto da due livelli di crittografia. Non è accessibile ad altri utenti, nemmeno a un amministratore, perché non è presente alcun account amministratore in un HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>È necessario usare l'autenticazione Iris?
No, è possibile ignorare questo passaggio durante l'installazione. 

![Configurare Iris.](./images/setup-iris.png)

HoloLens 2 offre molte opzioni diverse per l'autenticazione, incluse le chiavi di sicurezza FIDO2.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Le informazioni Iris possono essere rimosse dal HoloLens?
Sì, è possibile rimuoverlo manualmente in Impostazioni.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>In che modo il tipo di account influisce sul comportamento di accesso?

Se si applicano criteri per l'accesso, i criteri vengono sempre rispettati. Se non viene applicato alcun criterio per l'accesso, questi sono i comportamenti predefiniti per ogni tipo di account:

- **Azure AD**: richiede l'autenticazione per impostazione predefinita  e può essere Impostazioni per non richiedere più l'autenticazione.
- **account Microsoft:** il comportamento del blocco è diverso consentendo lo sblocco automatico, ma l'autenticazione di accesso è ancora necessaria al riavvio.
- **Account locale:** richiede sempre l'autenticazione sotto forma di password, non **configurabile** in Impostazioni

> [!NOTE]
> I timer di inattività non sono attualmente supportati, pertanto il criterio **AllowIdleReturnWithoutPassword** viene rispettato solo quando il dispositivo passa a StandBy.

## <a name="additional-resources"></a>Risorse aggiuntive

Per altre informazioni sulla protezione e l'autenticazione delle identità utente, vedere la [documentazione Windows 10 sicurezza e identità.](/windows/security/identity-protection/)

Per altre informazioni sulla configurazione dell'infrastruttura di identità ibrida, vedere la [documentazione sulle identità di Azure Hybrid.](/azure/active-directory/hybrid/)