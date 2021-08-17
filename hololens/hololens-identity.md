---
title: Gestire l'identità utente e l'accesso per HoloLens
description: Informazioni su come gestire l'identità utente, il supporto multi-utente, la sicurezza, l'autenticazione aziendale e l'accesso per HoloLens dispositivi.
keywords: HoloLens, utente, account, AAD, Azure AD, adfs, account Microsoft, msa, credenziali, riferimento
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 11a5680ea2b27a277bc4eb5b1dc0e62a2c602312
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858438"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gestire l'identità utente e l'accesso per HoloLens

> [!NOTE]
> Questo articolo è un riferimento tecnico per professionisti IT e appassionati di tecnologia. Se si sta cercando HoloLens istruzioni di configurazione, vedere " Configurazione del HoloLens[(prima generazione)](hololens1-start.md)" o " Configurazione del[HoloLens 2](hololens2-start.md)".

Come altri Windows, HoloLens funziona sempre in un contesto utente. Esiste sempre un'identità utente. HoloLens tratta l'identità in modo quasi identico a quello di altri Windows dispositivi. Questo articolo è un riferimento approfondito per l'identità HoloLens e illustra le differenze tra HoloLens e altri Windows dispositivi.

HoloLens supporta diversi tipi di identità utente. È possibile usare uno o più account utente per accedere. Ecco una panoramica dei tipi di identità e delle opzioni di autenticazione HoloLens:

| Tipo di identità | Account per dispositivo | Opzioni di autenticazione |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Provider di credenziali Web di Azure</li><li>App Authenticator Azure</li><li>Biometrico (Iris) &ndash; HoloLens 2 solo<sup>2</sup> </li><li>Chiave di sicurezza FIDO2</li><li>PIN &ndash; Facoltativo per HoloLens (prima generazione), necessario per HoloLens 2</li><li>Password</li></ul> |
| [Account Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Solo dati biometrici (Iris) &ndash; HoloLens 2</li><li>PIN &ndash; Facoltativo per HoloLens (prima generazione), necessario per HoloLens 2</li><li>Password</li></ul> |
| [Account locale](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Password |

Gli account connessi al cloud (Azure AD e MSA) offrono più funzionalità perché possono usare i servizi di Azure.  
> [!IMPORTANT]
> 1: Azure AD Premium non è necessario accedere al dispositivo. Tuttavia, è necessario per altre funzionalità di una distribuzione basata sul cloud a basso tocco, ad esempio la registrazione automatica e Autopilot.

> [!NOTE]
> 2- Mentre un dispositivo HoloLens 2 può supportare fino a 64 account Azure AD, solo 31 di questi account possono registrarsi nell'autenticazione Iris. Questo è allineato con altre opzioni [di autenticazione biometrica per Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

> [!IMPORTANT]
> 3 - Un account locale può essere configurato solo in un dispositivo tramite un pacchetto di [provisioning](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)durante la configurazione di , non può essere aggiunto in un secondo momento nell'app delle impostazioni. Se si desidera usare un account locale in un dispositivo già configurato, è necessario eseguire il [reflash o](hololens-recovery.md) reimpostare il dispositivo.

## <a name="setting-up-users"></a>Configurazione degli utenti

Esistono due modi per configurare un nuovo utente nel HoloLens. Il modo più comune è durante HoloLens'esperienza di configurazione. Se si Azure Active Directory, [altri utenti possono accedere dopo](#setting-up-multi-user-support-azure-ad-only) la configurazione del sistema operativo usando le Azure AD credenziali. HoloLens i dispositivi che vengono inizialmente impostati con un account msa o locale durante la configurazione non supporteranno più utenti. Vedere Configurazione del HoloLens [(prima generazione)](hololens1-start.md) [o HoloLens 2](hololens2-start.md).

Se si usa un account aziendale o aziendale per accedere a HoloLens, HoloLens si registra nell'infrastruttura IT dell'organizzazione. Questa registrazione consente all'amministratore IT di configurare Gestione dispositivi mobili (MDM) per inviare criteri di gruppo al HoloLens.

Come Windows in altri dispositivi, l'accesso durante la configurazione crea un profilo utente nel dispositivo. Il profilo utente archivia app e dati. Lo stesso account fornisce anche l'accesso Single Sign-On per le app, ad esempio Edge o Microsoft Store, usando le API Windows Account Manager.

Per impostazione predefinita, come per altri Windows 10, sarà necessario accedere di nuovo quando HoloLens riavvio o ripresa dalla modalità standby. È possibile usare l'app Impostazioni per modificare questo comportamento oppure il comportamento può essere controllato da Criteri di gruppo.

### <a name="linked-accounts"></a>Account collegati

Come nella versione Desktop di Windows, è possibile collegare credenziali aggiuntive dell'account Web all'account HoloLens desktop. Questo tipo di collegamento semplifica l'accesso alle risorse all'interno o all'interno di app (ad esempio lo Store) o di combinare l'accesso alle risorse personali e di lavoro. Dopo aver connesso un account al dispositivo, è possibile concedere l'autorizzazione per usare il dispositivo alle app in modo che non sia necessario accedere a ogni app singolarmente.

Il collegamento di account non separa i dati utente creati nel dispositivo, ad esempio immagini o download.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configurazione del supporto multi-utente (solo Azure AD)

HoloLens supporta più utenti dello stesso tenant Azure AD tenant. Per usare questa funzionalità, è necessario usare un account appartenente all'organizzazione per configurare il dispositivo. Successivamente, altri utenti dello stesso tenant possono accedere al dispositivo dalla schermata di accesso o toccando il riquadro utente nel pannello Start. È possibile accedere a un solo utente alla volta. Quando un utente esegue l'accesso, HoloLens l'utente precedente. 

>[!IMPORTANT]
> Il primo utente del dispositivo è considerato il proprietario del dispositivo, ad eccezione del caso di Azure AD join, per altre informazioni sui [proprietari del dispositivo.](security-adminless-os.md#device-owner)

Tutti gli utenti possono usare le app installate nel dispositivo. Tuttavia, ogni utente ha i propri dati e preferenze dell'app. La rimozione di un'app dal dispositivo la rimuove per tutti gli utenti.  

I dispositivi impostati con Azure AD non consentiranno l'accesso al dispositivo con un account Microsoft. Tutti gli account successivi usati Azure AD dallo stesso tenant del dispositivo. È comunque possibile [accedere con un account Microsoft](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) alle app che lo supportano, ad esempio il Microsoft Store. Per passare dall'uso Azure AD account microsoft agli account Microsoft per l'accesso al dispositivo, è necessario [eseguire il reflash del dispositivo.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (prima generazione)** ha iniziato a supportare più utenti Azure AD nell'aggiornamento di [Windows 10 aprile 2018](/windows/mixed-reality/release-notes-april-2018) come parte di [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Più utenti elencati nella schermata di accesso

In precedenza la schermata di accesso mostrava solo l'utente connesso più di recente, nonché un punto di ingresso "Altro utente". Il feedback dei clienti non è sufficiente se più utenti hanno eseguito l'accesso al dispositivo. Era comunque necessario digitare nuovamente il nome utente e così via.

Introdotto [in Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)quando si seleziona Altro utente che si trova a destra del campo di immissione PIN, nella schermata di accesso verranno visualizzati più utenti che hanno eseguito l'accesso al dispositivo in precedenza.  In questo modo gli utenti possono selezionare il proprio profilo utente e quindi accedere usando le Windows Hello credenziali. È anche possibile aggiungere un nuovo utente al dispositivo da questa pagina Altri utenti tramite il **pulsante Aggiungi account.**

Nel menu Altri utenti il pulsante Altri utenti visualizza l'ultimo utente che ha eseguito l'accesso al dispositivo. Selezionare questo pulsante per tornare alla schermata Di accesso per questo utente.

![Impostazione predefinita della schermata di accesso](./images/multiusers1.jpg)

<br>

![Schermata di accesso di altri utenti](./images/multiusers2.jpg)

## <a name="removing-users"></a>Rimozione di utenti

È possibile rimuovere un utente dal dispositivo selezionando account **Impostazioni**  >    >  **altri utenti**. Questa azione recupera anche spazio rimuovendo tutti i dati dell'app dell'utente dal dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Uso dell'accesso Single Sign-On in un'app

Gli sviluppatori di app possono sfruttare le identità collegate in HoloLens usando le API di [Windows Account Manager,](/uwp/api/Windows.Security.Authentication.Web.Core)esattamente come in altri dispositivi Windows. Alcuni esempi di codice per queste API sono disponibili in GitHub: Esempio di [gestione degli account Web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Qualsiasi interruzione dell'account che potrebbe verificarsi, ad esempio la richiesta del consenso dell'utente per le informazioni sull'account, l'autenticazione a due fattori e così via, deve essere gestita quando l'app richiede un token di autenticazione.

Se l'app richiede un tipo di account specifico che non è stato collegato in precedenza, l'app può chiedere al sistema di richiedere all'utente di aggiungerne uno. Questa richiesta attiva il riquadro delle impostazioni dell'account per l'avvio come figlio modale dell'app. Per le app 2D, il rendering di questa finestra viene eseguito direttamente al centro dell'app. Per le app Unity, questa richiesta consente all'utente di uscire dall'app olografica per eseguire il rendering della finestra figlio. Per informazioni sulla personalizzazione dei comandi e delle azioni in questo riquadro, vedere [Classe WebAccountCommand](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise e altre autenticazioni

Se [l'app](/uwp/api/Windows.Security.Credentials.UI) usa altri tipi di autenticazione, ad esempio NTLM, Basic o Kerberos, è possibile usare l'interfaccia utente delle credenziali di Windows per raccogliere, elaborare e archiviare le credenziali dell'utente. L'esperienza utente per la raccolta di queste credenziali è molto simile ad altre interruzioni dell'account basato sul cloud e viene visualizzata come app figlio sopra l'app 2D o sospende brevemente un'app Unity per visualizzare l'interfaccia utente.

## <a name="deprecated-apis"></a>API deprecate

Uno dei modi in cui lo sviluppo per HoloLens differisce dallo sviluppo per Desktop è che l'API [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) non è completamente supportata. Anche se l'API restituisce un token se l'account primario è valido, gli interrupt come quelli descritti in questo articolo non visualizzano alcuna interfaccia utente per l'utente e non riescono a autenticare correttamente l'account.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Windows Hello for Business è supportato in HoloLens (prima generazione)?

Windows Hello for Business , che supporta l'uso di un PIN per l'accesso, è supportato per HoloLens (prima generazione). Per consentire Windows Hello'accesso al PIN di HoloLens:

1. Il HoloLens deve essere [gestito da MDM.](hololens-enroll-mdm.md)
1. È necessario abilitare Windows Hello for Business per il dispositivo. ([Vedere le istruzioni per Microsoft Intune.](/intune/windows-hello))
1. In HoloLens l'utente può quindi usare Impostazioni opzioni di accesso  >    >  **Aggiungi PIN** per configurare un PIN.

> [!NOTE]
> Gli utenti che a loro account Microsoft possono anche configurare un PIN **in** Impostazioni Opzioni di accesso  >    >  **Aggiungi PIN.** Questo PIN è associato a [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), anziché [Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Come viene implementata l'autenticazione biometrica Iris HoloLens 2?

HoloLens 2 supporta l'autenticazione Iris. Iris si basa sulla tecnologia Windows Hello ed è supportato per l'uso da parte di account Azure Active Directory e Microsoft. Iris viene implementato come altre tecnologie Windows Hello e ottiene la sicurezza biometrica fino a [1/100.000.](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)

Per altre [informazioni, vedere i](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) requisiti biometrici e le Windows Hello per altre informazioni. Altre informazioni su [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) e [Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="where-is-iris-biometric-information-stored"></a>Dove vengono archiviate le informazioni biometriche Iris?

Le informazioni biometriche Iris vengono archiviate in locale in ogni HoloLens per [Windows Hello specifiche](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored). Non è condiviso ed è protetto da due livelli di crittografia. Non è accessibile ad altri utenti, anche a un amministratore, perché non esiste alcun account amministratore in un HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>È necessario usare l'autenticazione Iris?
No, è possibile ignorare questo passaggio durante l'installazione. 

![Configurare i dati Iris](./images/setup-iris.png)

HoloLens 2 offre molte opzioni diverse per l'autenticazione, incluse le chiavi di sicurezza FIDO2.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Le informazioni Iris possono essere rimosse dal HoloLens?
Sì, è possibile rimuoverlo manualmente in Impostazioni.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>In che modo il tipo di account influisce sul comportamento di accesso?

Se si applicano criteri per l'accesso, i criteri vengono sempre rispettati. Se non viene applicato alcun criterio per l'accesso, questi sono i comportamenti predefiniti per ogni tipo di account:

- **Azure AD**: richiede l'autenticazione per impostazione predefinita e può essere Impostazioni **per** non richiedere più l'autenticazione.
- **account Microsoft:** il comportamento del blocco è diverso consentendo lo sblocco automatico, ma l'autenticazione di accesso è ancora necessaria al riavvio.
- **Account locale:** richiede sempre l'autenticazione sotto forma di password, non configurabile in **Impostazioni**

> [!NOTE]
> I timer di inattività non sono attualmente supportati, il che significa che i criteri **AllowIdleReturnWithoutPassword** vengono rispettati solo quando il dispositivo passa a StandBy.

## <a name="additional-resources"></a>Risorse aggiuntive

Per altre informazioni sulla protezione e l'autenticazione delle identità utente, vedere la [documentazione Windows 10 sicurezza e identità.](/windows/security/identity-protection/)

Per altre informazioni sulla configurazione dell'infrastruttura di gestione delle identità ibrida, vedere la [documentazione sulle identità ibride di Azure.](/azure/active-directory/hybrid/)
