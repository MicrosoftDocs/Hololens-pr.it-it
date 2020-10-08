---
title: Gestire l'identità utente e l'accesso per HoloLens
description: Gestire l'identità, la sicurezza e l'accesso degli utenti per HoloLens.
keywords: HoloLens, utente, account, AAD, ADFS, account Microsoft, MSA, credenziali, riferimento
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
ms.openlocfilehash: 5963e71bd6fdd084ca442995b02d99fc40da9d43
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102335"
---
# Gestire l'identità utente e l'accesso per HoloLens

> [!NOTE]
> Questo articolo è un riferimento tecnico per professionisti IT e appassionati di tecnologia. Per informazioni sulle istruzioni per la configurazione di HoloLens, vedere "[configurazione della HoloLens (1a generazione)](hololens1-start.md)" o "[configurazione del HoloLens 2](hololens2-start.md)".

Come gli altri dispositivi Windows, HoloLens funziona sempre in un contesto utente. Esiste sempre un'identità utente. HoloLens tratta l'identità quasi allo stesso modo degli altri dispositivi Windows 10. Questo articolo è un riferimento di Deep-Dive per l'identità in HoloLens e si basa sul modo in cui HoloLens differisce da altri dispositivi Windows 10.

HoloLens supporta diversi tipi di identità utente. È possibile usare uno o più account utente per accedere. Ecco una panoramica dei tipi di identità e delle opzioni di autenticazione in HoloLens:

| Tipo di identità | Account per dispositivo | Opzioni di autenticazione |
| --- | --- | --- |
| [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Provider di credenziali Web di Azure</li><li>App Azure Authenticator</li><li>Solo HoloLens 2 (Iris) biometrico &ndash;</li><li>PIN &ndash; facoltativo per HoloLens (1a generazione), obbligatorio per HoloLens 2</li><li>Password</li></ul> |
| [Account Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Solo HoloLens 2 (Iris) biometrico &ndash;</li><li>PIN &ndash; facoltativo per HoloLens (1a generazione), obbligatorio per HoloLens 2</li><li>Password</li></ul> |
| [Account locale](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Password |

Gli account connessi al cloud (AAD e MSA) offrono più funzionalità perché possono usare i servizi di Azure.  

## Configurazione degli utenti

Il modo più comune per configurare un nuovo utente è durante l'esperienza di HoloLens out-of-box (OOBE). Durante l'installazione, HoloLens chiede all'utente di eseguire l'accesso usando l'account che vuole usare nel dispositivo. Questo account può essere un account Microsoft Consumer o un account aziendale configurato in Azure. Vedere Configurazione di [HoloLens (1a generazione)](hololens1-start.md) o [HoloLens 2](hololens2-start.md).

Come Windows in altri dispositivi, l'accesso durante la configurazione crea un profilo utente nel dispositivo. Il profilo utente archivia le app e i dati. Lo stesso account offre anche Single Sign-on per app come Edge o Skype tramite le API di gestione account di Windows.  

Se si usa un account aziendale o dell'organizzazione per accedere a HoloLens, HoloLens si iscrive nell'infrastruttura IT della società. Questa registrazione consente all'amministratore IT di configurare la gestione di dispositivi mobili (MDM) per inviare criteri di gruppo a HoloLens.

Per impostazione predefinita, come per altri dispositivi Windows 10, è necessario eseguire di nuovo l'accesso quando HoloLens si riavvia o riprende dalla modalità standby. Puoi usare l'app impostazioni per modificare questo comportamento oppure il comportamento può essere controllato da criteri di gruppo.

### Account collegati

Come nella versione desktop di Windows, è possibile collegare altre credenziali dell'account Web al proprio account di HoloLens. Questo tipo di collegamento semplifica l'accesso alle risorse in tutte le app (come lo Store) o per combinare l'accesso a risorse personali e lavorative. Dopo aver connesso un account al dispositivo, è possibile concedere l'autorizzazione per l'uso del dispositivo alle app, in modo da non dover accedere individualmente a ogni app.

Il collegamento degli account non separa i dati utente creati nel dispositivo, ad esempio immagini o download.  

### Configurazione del supporto multi-utente (solo AAD)

HoloLens supporta più utenti dello stesso tenant di AAD. Per usare questa caratteristica, devi usare un account che appartiene all'organizzazione per configurare il dispositivo. Successivamente, gli altri utenti dello stesso tenant possono accedere al dispositivo dalla schermata di accesso o toccando il riquadro dell'utente nel pannello Start. È possibile eseguire l'accesso a un solo utente alla volta. Quando un utente accede, HoloLens firma l'utente precedente. Il primo utente nel dispositivo è considerato il proprietario del dispositivo, tranne nel caso di AAD join, [Leggi altre informazioni sui proprietari di dispositivi](security-adminless-os.md#device-owner).

Tutti gli utenti possono usare le app installate nel dispositivo. Tuttavia, ogni utente ha i propri dati e preferenze dell'app. La rimozione di un'app dal dispositivo lo rimuove per tutti gli utenti.  

I dispositivi impostati con gli account AAD non consentiranno l'accesso al dispositivo con un account Microsoft. Tutti gli account successivi usati devono essere account AAD dello stesso tenant del dispositivo. È comunque possibile [accedere con un account Microsoft alle app](hololens-identity.md#setting-up-multi-user-support-aad-only) che la supportano, ad esempio Microsoft Store. Per passare dall'uso degli account AAD agli account Microsoft per l'accesso al dispositivo, è necessario [reflashare il dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1a generazione)** ha iniziato a supportare più utenti AAD nell' [aggiornamento di windows 10 aprile 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) come parte di [Windows olografico for business](hololens-upgrade-enterprise.md).

## Rimozione di utenti

È possibile rimuovere un utente dal dispositivo accedendo agli account **delle impostazioni**di  >  **Accounts**  >  **altri utenti**. Questa azione recupera anche lo spazio rimuovendo tutti i dati dell'app dell'utente dal dispositivo.  

## Uso di Single Sign-on all'interno di un'app

Come sviluppatore di app, puoi sfruttare le identità collegate in HoloLens usando le [API di Windows account manager](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core), proprio come in altri dispositivi Windows. Alcuni esempi di codice per queste API sono disponibili in GitHub: [esempio di gestione degli account Web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Eventuali interruzioni di account che potrebbero verificarsi, ad esempio per richiedere il consenso dell'utente per informazioni sull'account, l'autenticazione a due fattori e così via, devono essere gestite quando l'app richiede un token di autenticazione.

Se l'app richiede un tipo di account specifico che non è stato collegato in precedenza, l'app può chiedere al sistema di richiedere all'utente di aggiungerne uno. Questa richiesta attiva il riquadro Impostazioni account per avviarlo come elemento figlio modale della tua app. Per le app 2D, questa finestra esegue il rendering direttamente sopra il centro della tua app. Per le app Unity, questa richiesta estrae brevemente l'utente dall'app olografica per eseguire il rendering della finestra figlio. Per informazioni sulla personalizzazione dei comandi e delle azioni in questo riquadro, vedere la [classe WebAccountCommand](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## Organizzazione e altra autenticazione

Se l'app usa altri tipi di autenticazione, ad esempio NTLM, Basic o Kerberos, puoi usare l' [interfaccia utente delle credenziali di Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) per raccogliere, elaborare e archiviare le credenziali dell'utente. L'esperienza utente per la raccolta di queste credenziali è molto simile ad altri interrupt per gli account basati sul cloud e viene visualizzata come app figlio all'inizio dell'app 2D o sospende brevemente un'app Unity per mostrare l'interfaccia utente.

## API deprecate

Uno dei modi in cui lo sviluppo per HoloLens differisce dallo sviluppo per il desktop è che l'API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) non è completamente supportata. Anche se l'API restituisce un token se l'account principale è in buona posizione, gli interrupt, ad esempio quelli descritti in questo articolo, non visualizzano alcuna interfaccia utente e non riescono ad autenticare correttamente l'account.

## Domande frequenti

### Windows Hello for business è supportato in HoloLens (1a generazione)?

Windows Hello for business (che supporta l'uso di un PIN per l'accesso) è supportato per HoloLens (1a generazione). Per consentire l'accesso al PIN di Windows Hello for business in HoloLens:

1. Il dispositivo HoloLens deve essere [gestito da MDM](hololens-enroll-mdm.md).
1. Devi abilitare Windows Hello for business per il dispositivo. [Vedere le istruzioni per Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello)
1. In HoloLens l'utente può quindi usare **le**  >  **Opzioni**  >  di accesso alle impostazioni**Aggiungi pin** per configurare un PIN.

> [!NOTE]
> Gli utenti che accedono tramite un account Microsoft possono anche configurare un PIN nelle opzioni di accesso **delle impostazioni**per l'  >  **Sign-in Options**  >  **aggiunta di pin**. Questo PIN è associato a [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), invece che [a Windows Hello for business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### Come viene implementata l'autenticazione biometrica di Iris in HoloLens 2?

HoloLens 2 supporta l'autenticazione Iris. Iris si basa sulla tecnologia Windows Hello ed è supportata per l'uso sia dagli account di Azure Active Directory che da Microsoft. Iris viene implementata allo stesso modo delle altre tecnologie Windows Hello e consente di ottenere la sicurezza biometrica di oltre 1/100K.

Per altre informazioni sui requisiti e le specifiche biometriche per Windows [, vedere Ciao.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) Leggi altre informazioni su [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) e [Windows Hello for business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### In che modo il tipo di account ha effetto sul comportamento di accesso?

Se applichi i criteri per l'accesso, il criterio è sempre rispettato. Se non viene applicato alcun criterio per l'accesso, questi sono i comportamenti predefiniti per ogni tipo di account:

- **Azure ad**: richiede l'autenticazione per impostazione predefinita e configurabile tramite **le impostazioni** per non richiedere più l'autenticazione.
- **Account Microsoft**: il comportamento di blocco è diverso, consentendo l'apertura automatica, tuttavia l'autenticazione di accesso è ancora necessaria al riavvio.
- **Account locale**: richiede sempre l'autenticazione sotto forma di password, non configurabile nelle **Impostazioni**

> [!NOTE]
> I timer di inattività non sono attualmente supportati, quindi il criterio **AllowIdleReturnWithoutPassword** viene rispettato solo quando il dispositivo entra in standby.

## Risorse aggiuntive

Per altre informazioni, vedere protezione e autenticazione delle identità degli utenti nella [documentazione di sicurezza e identità di Windows 10](https://docs.microsoft.com/windows/security/identity-protection/).

Altre informazioni sulla configurazione dell'infrastruttura di identità ibrida completano la [documentazione dell'identità di Azure Hybrid](https://docs.microsoft.com/azure/active-directory/hybrid/).
