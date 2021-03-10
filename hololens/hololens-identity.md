---
title: Gestire l'identità utente e l'accesso per HoloLens
description: Informazioni su come gestire l'identità utente, il supporto multi-utente, la sicurezza, l'autenticazione aziendale e l'accesso per i dispositivi HoloLens.
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
ms.openlocfilehash: 2d84658ef76ff2c5d8ef7dabe857892e7129a965
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400686"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gestire l'identità utente e l'accesso per HoloLens

> [!NOTE]
> Questo articolo è una guida di riferimento tecnico per professionisti IT e appassionati di tecnologia. Se stai cercando istruzioni per la configurazione di HoloLens, leggi " Configurazione di[HoloLens (prima generazione)](hololens1-start.md)" o " Configurazione di[HoloLens 2".](hololens2-start.md)

Come altri dispositivi Windows, HoloLens opera sempre in un contesto utente. Esiste sempre un'identità utente. HoloLens considera l'identità quasi come altri dispositivi Windows 10. Questo articolo è un riferimento approfondito per l'identità in HoloLens e illustra in che modo HoloLens differisce dagli altri dispositivi Windows 10.

HoloLens supporta diversi tipi di identità utente. È possibile utilizzare uno o più account utente per accedere. Ecco una panoramica dei tipi di identità e delle opzioni di autenticazione in HoloLens:

| Tipo di identità | Account per dispositivo | Opzioni di autenticazione |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (richiede Azure AD Premium) | 64 | <ul><li>Provider di credenziali Web di Azure</li><li>Azure Authenticator App</li><li>Biometrico (Iris) &ndash; HoloLens 2 solo <sup> 1</sup> </li><li>PIN &ndash; facoltativo per HoloLens (prima generazione), necessario per HoloLens 2</li><li>Password</li></ul> |
| [Account Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometrico (Iris) &ndash; Solo HoloLens 2</li><li>PIN &ndash; facoltativo per HoloLens (prima generazione), necessario per HoloLens 2</li><li>Password</li></ul> |
| [Account locale](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Password |

Gli account connessi al cloud (Azure AD e MSA) offrono più funzionalità perché possono usare i servizi di Azure.  

> [!NOTE]
> 1 - Mentre un dispositivo HoloLens 2 può supportare fino a 64 account Azure AD, solo 10 di questi account possono registrarsi nell'autenticazione Iris. Questo è allineato con altre opzioni [di autenticazione biometrica per Windows Hello for Business.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Configurazione degli utenti

Il modo più comune per configurare un nuovo utente è durante la configurazione guidata di HoloLens. Durante la configurazione, HoloLens richiede a un utente di accedere usando l'account che vuole usare nel dispositivo. Questo account può essere un account Microsoft consumer o un account aziendale configurato in Azure. Vedi Configurazione di [HoloLens (prima generazione)](hololens1-start.md) o [HoloLens 2.](hololens2-start.md)

Come Windows in altri dispositivi, l'accesso durante la configurazione crea un profilo utente nel dispositivo. Il profilo utente archivia app e dati. Lo stesso account fornisce anche single sign-on per app come Edge o Skype usando le API di Gestione account Di Windows.  

Se si usa un account aziendale o dell'organizzazione per accedere a HoloLens, HoloLens si registra nell'infrastruttura IT dell'organizzazione. Questa registrazione consente all'amministratore IT di configurare Gestione di dispositivi mobili (MDM) per inviare criteri di gruppo a HoloLens.

Per impostazione predefinita, come per gli altri dispositivi Windows 10, dovrai accedere di nuovo quando HoloLens viene riavviato o ripristinato dallo stato di standby. Puoi usare l'app Impostazioni per modificare questo comportamento oppure il comportamento può essere controllato da Criteri di gruppo.

### <a name="linked-accounts"></a>Account collegati

Come nella versione desktop di Windows, puoi collegare ulteriori credenziali dell'account Web al tuo account HoloLens. Questo tipo di collegamento semplifica l'accesso alle risorse all'interno o all'interno di app (ad esempio lo Store) o di combinare l'accesso alle risorse personali e di lavoro. Dopo aver connesso un account al dispositivo, puoi concedere l'autorizzazione per l'uso del dispositivo alle app in modo da non doverti accedere singolarmente a ogni app.

Il collegamento degli account non separa i dati utente creati nel dispositivo, ad esempio immagini o download.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configurazione del supporto multi-utente (solo Azure AD)

HoloLens supporta più utenti dallo stesso tenant di Azure AD. Per usare questa funzionalità, devi usare un account appartenente all'organizzazione per configurare il dispositivo. Successivamente, altri utenti dello stesso tenant possono accedere al dispositivo dalla schermata di accesso o toccando il riquadro utente nel pannello Start. È possibile accedere a un solo utente alla volta. Quando un utente esegue l'accesso, HoloLens esce dall'utente precedente. Il primo utente nel dispositivo è considerato il proprietario del dispositivo, tranne nel caso dell'aggiunta ad Azure AD, per altre [informazioni sui proprietari del dispositivo.](security-adminless-os.md#device-owner)

Tutti gli utenti possono usare le app installate nel dispositivo. Tuttavia, ogni utente ha i propri dati e preferenze dell'app. La rimozione di un'app dal dispositivo la rimuove per tutti gli utenti.  

I dispositivi impostati con account Azure AD non consentiranno l'accesso al dispositivo con un account Microsoft. Tutti gli account successivi usati devono essere account Azure AD dello stesso tenant del dispositivo. Puoi comunque accedere [con un account Microsoft alle app](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) che lo supportano (ad esempio Microsoft Store). Per passare dall'uso degli account Azure AD agli account Microsoft per l'accesso al dispositivo, devi [rifuscare il dispositivo.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (prima generazione)** ha iniziato a supportare più utenti di Azure AD in [Windows 10 Aprile 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) come parte di [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

## <a name="removing-users"></a>Rimozione di utenti

Per rimuovere un utente dal dispositivo, accedere **a**Impostazioni  >  **Account**  >  **altri utenti.** Questa azione recupera anche lo spazio rimuovendo tutti i dati dell'app dell'utente dal dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Uso di Single #A0 all'interno di un'app

Gli sviluppatori di app possono sfruttare le identità collegate in HoloLens usando le API di [Windows Account Manager,](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)proprio come in altri dispositivi Windows. Alcuni esempi di codice per queste API sono disponibili in GitHub: Esempio di [gestione degli account Web.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Qualsiasi interruzione dell'account che potrebbe verificarsi, ad esempio la richiesta del consenso dell'utente per le informazioni sull'account, l'autenticazione a due fattori e così via, deve essere gestita quando l'app richiede un token di autenticazione.

Se l'app richiede un tipo di account specifico che non è stato collegato in precedenza, l'app può chiedere al sistema di chiedere all'utente di aggiungerne uno. Questa richiesta attiva l'avvio del riquadro delle impostazioni dell'account come elemento figlio modale della tua app. Per le app 2D, il rendering di questa finestra viene eseguito direttamente al centro dell'app. Per le app Unity, questa richiesta consente all'utente di uscire dalla tua app olografica per eseguire il rendering della finestra figlio. Per informazioni sulla personalizzazione dei comandi e delle azioni in questo riquadro, vedere [Classe WebAccountCommand](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Autenticazione aziendale e di altro tipo

Se l'app usa altri tipi di autenticazione, ad esempio NTLM, Di base o Kerberos, puoi usare l'interfaccia utente delle credenziali di [Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) per raccogliere, elaborare e archiviare le credenziali dell'utente. L'esperienza utente per la raccolta di queste credenziali è molto simile ad altri interrupt dell'account basata sul cloud e viene visualizzata come app figlio sopra l'app 2D o sospende brevemente un'app Unity per mostrare l'interfaccia utente.

## <a name="deprecated-apis"></a>API deprecate

Uno dei modi in cui lo sviluppo per HoloLens differisce dallo sviluppo per desktop è che l'API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) non è completamente supportata. Anche se l'API restituisce un token se l'account principale è valido, interruzioni come quelle descritte in questo articolo non visualizzano alcuna interfaccia utente per l'utente e non riescono ad autenticare correttamente l'account.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Windows Hello for Business è supportato in HoloLens (prima generazione)?

Windows Hello for Business (che supporta l'uso di un PIN per l'accesso) è supportato per HoloLens (prima generazione). Per consentire l'accesso al PIN di Windows Hello for Business in HoloLens:

1. Il dispositivo HoloLens deve [essere gestito da MDM.](hololens-enroll-mdm.md)
1. Devi abilitare Windows Hello for Business per il dispositivo. ([Vedere le istruzioni per Microsoft Intune).](https://docs.microsoft.com/intune/windows-hello)
1. In HoloLens, l'utente può quindi usare **Impostazioni**Opzioni di accesso  >  ****  >  **Aggiungi PIN** per configurare un PIN.

> [!NOTE]
> Gli utenti che a questo punto a un utente a cui si accede con un account Microsoft possono anche configurare un PIN **in**Impostazioni  >  **Opzioni di accesso**  >  **Aggiungi PIN.** Questo PIN è associato a [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)anziché a Windows Hello [for Business.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Come viene implementata l'autenticazione biometrica Iris in HoloLens 2?

HoloLens 2 supporta l'autenticazione Iris. L'iride si basa sulla tecnologia Windows Hello ed è supportata per l'uso da parte di Azure Active Directory e degli account Microsoft. L'iride è implementata allo stesso modo delle altre tecnologie Di Windows Hello e ottiene la sicurezza biometrica FAR di 1/100K.

Per altre [informazioni, vedi i requisiti biometrici e](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) le specifiche per Windows Hello. Altre informazioni su [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) e Windows Hello [for Business.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>In che modo il tipo di account influisce sul comportamento di accesso?

Se applichi i criteri per l'accesso, il criterio è sempre rispettato. Se non viene applicato alcun criterio per l'accesso, questi sono i comportamenti predefiniti per ogni tipo di account:

- **Azure AD:** richiede l'autenticazione per impostazione predefinita e può essere configurato da **Impostazioni** per non richiedere più l'autenticazione.
- **Account Microsoft:** il comportamento di blocco è diverso consentendo lo sblocco automatico, ma l'autenticazione di accesso è comunque necessaria al riavvio.
- **Account locale:** richiede sempre l'autenticazione sotto forma di password, non configurabile in **Impostazioni**

> [!NOTE]
> I timer di inattività non sono attualmente supportati, il che significa che il criterio **AllowIdleReturnWithoutPassword** viene rispettato solo quando il dispositivo passa a StandBy.

## <a name="additional-resources"></a>Risorse aggiuntive

Per altre informazioni sulla protezione e l'autenticazione delle identità utente, vedere la documentazione sulla sicurezza e [l'identità di Windows 10.](https://docs.microsoft.com/windows/security/identity-protection/)

Ulteriori informazioni sulla configurazione dell'infrastruttura di gestione delle identità ibrida completano la [documentazione relativa all'identità ibrida di Azure.](https://docs.microsoft.com/azure/active-directory/hybrid/)
