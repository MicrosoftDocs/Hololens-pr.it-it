---
title: Limitazione dell'uso delle password
description: limitazione dell'uso della password per HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, limiting password use, password, hololens password, sign-in, signing in, windows hello, hello, windows account manager, FIDO2 sign in, FIDO 2, WEBAUTHN, local account, hololens security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a4ceaa1a741ec63153cd9112d04547165b46b0fa72c32ee7f9580f15368a2f88
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665453"
---
# <a name="limiting-password-use"></a>Limitazione dell'uso delle password

La maggior parte dei sistemi di computer attualmente usa le credenziali utente come base per la sicurezza, rendendole dipendenti da password riutilizzabili create dall'utente. In questo modo le password sono diventate anche la causa più comune di compromissione dell'account e violazioni dei dati. Ad esempio, le password possono essere intercettate durante la trasmissione o rubate da un server (tramite attacchi di phishing o password spraying) e compromesse per ottenere l'accesso a un account utente.

Per migliorare la sicurezza e la protezione degli account, HoloLens 2 è in grado di abilitare credenziali "senza password" supportate da hardware (incluso Windows Hello) per l'accesso al dispositivo, offrendo un facile accesso al cloud Microsoft.

## <a name="signing-in-from-another-device"></a>Eseguendo l'accesso da un altro dispositivo

HoloLens 2 offre opzioni di accesso remoto ai dispositivi per gli account aziendali Azure Active Directory durante la configurazione iniziale del dispositivo e l'accesso utente per ridurre la necessità di digitare password complesse e ridurre al minimo la necessità di password come credenziali. Gli utenti e le organizzazioni che usano le smart card per l'autenticazione hanno difficoltà a usare tali credenziali in dispositivi come HoloLens 2 e spesso le organizzazioni sviluppano sistemi complessi e processi costosi per risolvere il problema. Per risolvere questo problema, Azure AD due opzioni per l'accesso senza password HoloLens 2.

Il primo metodo di autenticazione si basa sulle nuove funzionalità dell'app Microsoft Authenticator per fornire l'autenticazione basata su chiave che consente una credenziale utente associata a un dispositivo. Una volta abilitato in un tenant dall'amministratore, agli utenti verrà visualizzato un messaggio durante HoloLens configurazione del dispositivo che gli indica di toccare un numero nell'app. Devono quindi corrispondere al numero nell'app di autenticazione, scegliere Approva, fornire il PIN o un'autenticazione biometrica e completare l'HoloLens per continuare. Questa procedura è descritta in modo più dettagliato in Accesso senza [password.](/azure/active-directory/authentication/howto-authentication-passwordless-phone)

Il secondo è un flusso di codice del dispositivo intuitivo per gli utenti e che non richiede alcuna infrastruttura aggiuntiva.  Questo comportamento di accesso remoto si basa su un altro dispositivo attendibile che supporta il meccanismo di autenticazione preferito dell'organizzazione e, al termine, i token vengono rilasciati al HoloLens per completare l'accesso o la configurazione del dispositivo. I passaggi in questo flusso sono:

  1. Un utente che sta effettuando la configurazione iniziale del dispositivo o i flussi di accesso nella Configurazione guidata viene visualizzato con un collegamento "Accedi da un altro dispositivo" e tocca il dispositivo. Verrà avviata una sessione di accesso remoto.
  1. All'utente viene quindi visualizzata una pagina di polling, che contiene un URI breve ( ) che punta all'endpoint di autenticazione del dispositivo del servizio token di sicurezza Azure AD [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) secure. All'utente viene anche presentata una time code che viene generata in modo sicuro nel cloud e ha una durata massima di 15 minuti. Oltre alla generazione del codice, Azure AD crea anche una sessione crittografata all'avvio della richiesta di accesso remoto nel passaggio precedente e, insieme, l'URI e il codice vengono usati per approvare la richiesta di accesso remoto.
  1. L'utente passa quindi all'URI da un altro dispositivo e viene richiesto di immettere il codice visualizzato nel HoloLens 2 dispositivo.
  1. Dopo che l'utente ha immesso il codice, Azure AD STS visualizza una pagina che indica il dispositivo HoloLens 2 dell'utente che ha attivato la richiesta di accesso remoto e ha richiesto la generazione del codice. All'utente viene quindi richiesta la conferma per impedire eventuali attacchi di phishing.
  1. Se l'utente sceglie di continuare ad accedere all'applicazione visualizzata, Azure AD sts richiede all'utente le credenziali. Al completamento dell'autenticazione, Azure AD sts aggiorna la sessione remota memorizzata nella cache come "approvata" insieme a un codice di autorizzazione.
  1. Infine, la pagina di polling nel dispositivo HoloLens 2 dell'utente riceve una risposta "Authorized" da Azure AD e procede alla convalida del codice utente e del codice di autorizzazione archiviato associato e genera i token OAuth come richiesto per completare la configurazione del dispositivo. Il token di autenticazione creato è valido per 1 ora e il token di aggiornamento ha una durata di 90 giorni.

Gli algoritmi di generazione del codice e di crittografia usati in questo flusso sono entrambi conformi a FIPS. HoloLens 2 usano il TPM per proteggere le chiavi del dispositivo e crittografare i token generati dopo l'autenticazione utente usando chiavi protette tramite hardware. Altre informazioni sulla sicurezza dei token HoloLens 2 sono condivise in [Che cos'è un token di aggiornamento primario (PRT)](/azure/active-directory/devices/concept-primary-refresh-token).

## <a name="device-sign-in-with-windows-hello"></a>Accesso del dispositivo con Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) offre opzioni senza password integrate direttamente nel sistema operativo che consentono agli utenti di accedere al dispositivo tramite Iris o PIN. Il PIN è sempre disponibile come credenziale ed è necessario per la configurazione del dispositivo, mentre Iris è facoltativo e può essere ignorato. Gli utenti possono accedere ai HoloLens usando il proprio account account Microsoft o Azure Active Directory aziendale [ *senza* immettere una password.](/azure/active-directory/authentication/concept-authentication-passwordless) Opzioni come queste offrono agli utenti l'accesso rapido e protetto all'esperienza completa Windows, alle app, ai dati, ai siti Web e ai servizi. La strategia di Microsoft per l'esperienza senza password è dettagliata qui.

Quando viene Windows Hello credenziali utente, stabilisce una relazione trusted con un provider di identità e crea una coppia di chiavi asimmetriche per l'autenticazione. Un Windows Hello,ad esempio iris o PIN, fornisce entropia per decrittografare una chiave privata supportata dal chip Trusted Platform Module (TPM) del dispositivo. Questa chiave privata viene quindi usata per firmare le richieste inviate a un server di autenticazione e, al completamento dell'autenticazione, all'utente viene concesso l'accesso alla posta elettronica, alle immagini e ad altre impostazioni dell'account.

Per altre informazioni, vedere l'infografica seguente:

  ![Windows Hello Accesso](images/security-hello-sign-in.png)
  
Nel grafico presentato sopra si noti che nonce è l'acronimo di "number once" e è un numero casuale o semi-casuale generato. Dopo aver Windows Hello credenziali biometriche o PIN, non lascia mai il dispositivo in cui è stato effettuato il provisioning. Anche se il PIN Windows Hello dell'utente viene rubato, ad esempio tramite un attacco di phishing, è inutile senza il dispositivo fisico [dell'utente.](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)

Per una maggiore sicurezza, le credenziali Windows Hello sono protette dal Trusted Platform Module (TPM) per rendere le credenziali anti-manomissione e integrate con protezioni anti-attacco contro più voci non corrette e protezione da software dannoso per impedire l'esposizione. Per altre informazioni su Single Sign-On (SSO), vedere questa [panoramica dei metodi SSO.](/azure/active-directory/manage-apps/what-is-single-sign-on)

L'autenticazione Iris torna al PIN. Per configurare un nuovo PIN (un autenticatore sicuro) nel dispositivo, l'utente deve aver recentemente completato l'autenticazione a più fattori [(MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) per completare il processo.

## <a name="single-sign-on-with-web-account-manager"></a>Single Sign-On con Gestione account Web

Single Sign-On (SSO) consente agli utenti senza password di accedere al dispositivo, utilizzando l'account personale dell'utente o l'account aziendale o dell'istituto di istruzione. L'utente viene automaticamente autorizzato con l'accesso SSO in tutte le app e i servizi integrati [tramite le API Gestione account Web .](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

Dopo che un'identità è stata aggiunta tramite un'applicazione, può, con il consenso dell'utente, diventare disponibile per tutte le app e i servizi usando l'integrazione a livello di sistema. Questo riduce notevolmente il carico di accesso dell'app e offre agli utenti un'esperienza di gestione delle identità senza problemi.

Per altre informazioni sull'implementazione Gestione account Web API, vedere [Implementazione Gestione account Web API .](/windows/uwp/security/web-account-manager)

  ![API Sicurezza](images/security-api-img.png)
  
Per le suite di app con requisiti di autenticazione specializzati, il framework Gestione account Web (WAM) è estendibile per i provider di identità personalizzati. Gli utenti possono scaricare il provider di identità personalizzato, in pacchetto come app UWP (Universal Windows Platform) dal Microsoft Store, per abilitare l'accesso SSO in altre app integrate con tale provider di identità.

Per altre informazioni sull'implementazione di provider di identità WAM personalizzati, vedere Informazioni di riferimento sull'API del provider di identità [WAM personalizzato.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello e l'accesso FIDO2 con WebAuthn

HoloLens 2 possibile usare credenziali utente senza password(ad esempio, chiavi di sicurezza Windows Hello o FIDO2) per accedere in modo sicuro sul Web tramite Microsoft Edge e ai siti Web che supportano WebAuthn. FIDO2 consente alle credenziali utente di sfruttare i vantaggi dei dispositivi basati su standard per l'autenticazione Servizi online.

> [!Note]
> Le [specifiche WebAuthn](https://www.w3.org/TR/webauthn/) e FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) vengono implementate nei servizi. I metadati firmati specificati da WebAuthn e FIDO2 forniscono informazioni, ad esempio se l'utente era presente, e verificano l'autenticazione tramite il movimento locale.

Come con Windows Hello, quando l'utente crea e registra una credenziale FIDO2, il dispositivo (HoloLens 2 o la chiave di sicurezza FIDO2) genera una chiave privata e pubblica nel dispositivo. La chiave privata viene archiviata in modo sicuro nel dispositivo e può essere usata solo dopo che è stata sbloccata usando un movimento locale, ad esempio una biometria o un PIN. Quando la chiave privata viene archiviata, la chiave pubblica viene inviata al sistema account Microsoft nel cloud e registrata con l'account utente associato.

Dopo aver effettuato l'accesso con un account del servizio Azure AD microsoft, il sistema invia un numero o una variabile di dati generata al dispositivo HoloLens 2 o FIDO2. Il HoloLens 2 o il dispositivo usa la chiave privata per firmare l'identificazione. L'identificazione e i metadati firmati vengono inviati al account Microsoft e verificati usando la chiave pubblica.

Windows Hello e FIDO2 implementano le credenziali basate sul dispositivo HoloLens, in particolare l'enclave Trusted Platform Module sicuro. L'enclave TPM archivia la chiave privata e richiede un PIN o biometrico per sbloccarla. Analogamente, una chiave di sicurezza FIDO2 è un piccolo dispositivo esterno con un enclave sicuro incorporato che archivia la chiave privata e richiede un CODICE BIOMETRICO o PIN per sbloccarla.

Entrambe le opzioni offrono l'autenticazione a due fattori in un unico passaggio, richiedendo sia un dispositivo registrato che un biometria o un PIN per eseguire correttamente l'accesso. Per altre informazioni, vedere l'immagine e il processo dell'autenticazione avanzata con chiave di sicurezza FIDO2, riportato di seguito.

### <a name="strong-authentication-with-fido2-security-key"></a>Autenticazione avanzata con chiave di sicurezza FIDO2

  ![FIDO img](images/security-fido2-whfb-smaller.png)

1. L'utente collega la chiave di sicurezza FIDO2 HoloLens 2
1. Windows rileva la chiave di sicurezza FIDO2
1. HoloLens invia una richiesta di autenticazione
1. Azure AD restituisce un nonce
1. L'utente completa il movimento per sbloccare gli archivi di chiavi private nell'enclave sicuro della chiave di sicurezza
1. La chiave di sicurezza FIDO2 firma un nonce con la chiave privata
1. La richiesta di token PRT con nonce firmato viene inviata Azure AD
1. Azure AD verifica la chiave FIDO
1. Azure AD restituisce PRT e TGT per abilitare l'accesso alle risorse

MsA e Azure AD sono tra le prime relying party a supportare l'autenticazione senza password implementando WebAuthn.

Per altre informazioni sull'uso di WebAuthn con applicazioni e/o SDK, vedere API [WebAuthn](/windows/security/identity-protection/hello-for-business/webauthnapis)per l'autenticazione senza password in Windows 10 .

HoloLens 2 supporta i dispositivi di sicurezza FIDO2 implementati per specificare e soddisfare i requisiti elencati in Accesso senza password di Azure Active Directory. Le chiavi di sicurezza [FIDO2](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) devono essere supportate.

## <a name="local-accounts"></a>Account locali

È possibile configurare un singolo account locale per le distribuzioni in modalità offline. Gli account locali non sono abilitati per impostazione predefinita e devono essere configurati durante il provisioning dei dispositivi. Devono accedere usando una password e non supportano metodi di autenticazione alternativi, ad esempio [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-overview) o [Windows Hello](/windows-hardware/design/device-experiences/windows-hello).

Altre informazioni su HoloLens account utente sono disponibili in [HoloLens Identity](hololens-identity.md).

Gli amministratori IT regolano se l'utente è autorizzato a usare un account msa per l'autenticazione e i servizi di connessione non correlati alla posta elettronica tramite [AllowMicrosoftAccountConnection.](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) Per i criteri di configurazione delle password, i criteri di identificazione e i criteri della schermata di blocco, vedere [Blocco del dispositivo.](/windows/client-management/mdm/policy-csp-devicelock)
