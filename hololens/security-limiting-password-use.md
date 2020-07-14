---
title: Limitazione dell'uso delle password
description: limitazione dell'uso delle password per HoloLens
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, limitazione dell'uso delle password, password, password hololens, accesso, accedere, windows hello, hello, gestione account windows, accesso FIDO2, FIDO 2, WEBAUTHN, account locale, sicurezza hololens
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 61330e77bc3aca5b0b21b58f18d087f7d5c06f3b
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865840"
---
# Limitazione dell'uso delle password

Nella maggior parte dei casi, i sistemi informatici di oggi usano le credenziali utente come base per la sicurezza e quindi dipendono di fatto dalle password riutilizzabili create dall'utente. Di conseguenza, le password sono diventate anche la causa più comune della compromissione degli account e della violazione dei dati. Ad esempio, le password possono essere intercettate durante la trasmissione o sottratte da un server (mediante attacchi di phishing o di tipo password spray) e compromesse per accedere a un account utente.

Per aumentare la sicurezza e la protezione degli account, HoloLens 2 offre la possibilità di abilitare credenziali avanzate "senza password" basate su hardware (compreso Windows Hello) per l'accesso ai dispositivi, semplificando l'accesso al cloud Microsoft. 

## Accesso da un altro dispositivo

HoloLens 2 offre opzioni di accesso ai dispositivi remoti per gli account aziendali di Azure Active Directory durante la configurazione iniziale del dispositivo e l'accesso dell'utente per ridurre la necessità di digitare password complesse e di usare password come credenziali. Gli utenti e le organizzazioni che usano smart card per l'autenticazione hanno difficoltà a usare quelle credenziali in dispositivi come HoloLens 2 e spesso sviluppano sistemi complessi e processi costosi per affrontare il problema. Per risolvere il problema, Azure AD offre due opzioni per l'accesso senza password in HoloLens 2. 

Il primo metodo di autenticazione si basa sulle nuove funzionalità dell'app Microsoft Authenticator per fornire l'autenticazione basata su chiave che abilita una credenziale utente collegata a un dispositivo. Una volta abilitata in un tenant dall'amministratore, gli utenti riceveranno un messaggio durante la configurazione del dispositivo HoloLens che chiede di toccare un numero nell'app. Devono quindi selezionare lo stesso numero nell'app di autenticazione, scegliere Approva, inserire il proprio PIN o seguire una procedura di autenticazione biometrica completa per proseguire la configurazione di HoloLens. Questa procedura è descritta in modo più dettagliato in [Accesso senza password](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone).

Il secondo metodo è un flusso di codice del dispositivo che è intuitivo per gli utenti e non richiede altre infrastrutture.  Questo comportamento di accesso remoto si basa su un altro dispositivo attendibile che supporta il meccanismo di autenticazione preferito dell'organizzazione, al termine del quale vengono riemessi i token al dispositivo HoloLens per completare l'accesso o la configurazione del dispositivo. I passaggi di questo flusso sono:

  1.    Nelle fasi iniziali della configurazione del dispositivo o dell'accesso in Configurazione guidata, l'utente visualizza un collegamento "Accesso da un altro dispositivo" e lo tocca. Viene avviata una sessione di accesso remoto.
  2.    All'utente viene quindi presentata una pagina di polling che contiene un URI breve ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) che punta all'endpoint di autenticazione del dispositivo del servizio token di sicurezza di Azure AD. Viene anche visualizzato un codice monouso generato in modo sicuro nel cloud, che ha una durata massima di 15 minuti. Oltre a generare il codice, Azure AD crea anche una sessione crittografata all'avvio della richiesta di accesso remoto nel passaggio precedente e l'URI e il codice vengono usati insieme per approvare la richiesta di accesso remoto. 
  3.    L'utente passa quindi all'URI da un altro dispositivo e riceve la richiesta di immettere il codice visualizzato sul dispositivo HoloLens 2. 
  4.    Una volta immesso il codice, il servizio token di sicurezza di Azure AD visualizza una pagina che indica il dispositivo HoloLens 2 dell'utente che ha generato la richiesta di accesso remoto e ha richiesto la generazione del codice. L'utente riceve quindi una richiesta di conferma, per evitare attacchi di phishing. 
  5.    Se l'utente sceglie di proseguire l'accesso all'"applicazione" visualizzata, il servizio token di sicurezza di Azure AD chiede all'utente di fornire le proprie credenziali. Quando l'autenticazione viene eseguita correttamente, il servizio token di sicurezza di Azure Active aggiorna la sessione remota memorizzata nella cache come "approvata" insieme a un codice di autorizzazione.
  6.    Infine, la pagina di polling page sul dispositivo HoloLens 2 dell'utente riceve una risposta "Autorizzato" da Azure AD e procede alla convalida del codice utente e del codice di autorizzazione memorizzato associato e genera i token OAuth necessari per completare la configurazione del dispositivo. Il token di autenticazione creato è valido per 1 ora e il token di aggiornamento ha una durata di 90 giorni. 

Gli algoritmi di crittografia e di generazione del codice utilizzati in questo flusso sono entrambi conformi allo standard FIPS. I dispositivi HoloLens 2 usano TPM per proteggere le chiavi dei dispositivi e crittografare i token generati dopo l'autenticazione dell'utente mediante chiavi con protezione hardware. Altre informazioni sulla sicurezza del token in HoloLens 2 sono disponibili in [Che cos'è un token di aggiornamento primario?](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token).

## Accesso al dispositivo con Windows Hello

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) offre opzioni senza password integrate direttamente nel sistema operativo che consentono agli utenti di accedere al dispositivo mediante Iris o PIN. Il PIN è sempre disponibile come credenziale ed è necessario per la configurazione del dispositivo, mentre il riconoscimento dell'iride è facoltativo e può essere saltato. Gli utenti possono accedere ai dispositivi HoloLens usando un account Microsoft personale o un [account aziendale di Azure Active Directory *senza* immettere una password](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless). Opzioni come queste offrono agli utenti un accesso rapido e protetto all'esperienza Windows completa, alle app, ai dati, ai siti Web e ai servizi. La strategia di Microsoft mirante alle esperienze senza password è illustrata in dettaglio qui.

Quando viene creata una credenziale Windows Hello, questa stabilisce una relazione attendibile con un provider di identità e crea una coppia di chiavi asimmetriche per l'autenticazione. Un movimento di Windows Hello, come l'iride o il PIN, fornisce l'entropia per decrittografare una chiave privata con il supporto del chip TPM (Trusted Platform Module) del dispositivo. Questa chiave privata viene quindi usata per firmare le richieste inviate a un server di autenticazione e, completata l'autenticazione, l'utente potrà accedere alla sua posta, alle sue immagini e ad altre impostazioni dell'account. 

Per altre informazioni, vedere l'infografica seguente:

  ![Accesso con Windows Hello](images/security-hello-sign-in.png)
  
Nell'immagine riportata sopra, nonce sta per "numero una volta" ed è un numero generato in modo casuale o semi-casuale. Una volta configurata la credenziale PIN o biometrica di Windows Hello, questa non lascia mai il dispositivo nel quale è stato eseguito il provisioning. Anche se il PIN di Windows Hello dell'utente viene sottratto, ad esempio con un attacco di phishing, è [inutile senza il dispositivo fisico dell'utente](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password). 

Per maggiore sicurezza, le credenziali di Windows Hello sono protette da TPM (Trusted Platform Module) per renderle resistenti alle manomissioni e corredate da protezioni anti-hammering contro più voci non corrette e da una protezione dal software dannoso per evitare l'esposizione. Per altre informazioni sul Single Sign-on (SSO), leggi questa [panoramica dei metodi SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

L'autenticazione tramite riconoscimento dell'iride utilizza il PIN. Per configurare un nuovo PIN (un autenticatore avanzato) nel dispositivo, è necessario che l'utente abbia effettuato di recente l'[autenticazione a più fattori](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) per completare il processo.

## Single Sign-on con Gestione account Web 

Single Sign-on (SSO) consente agli utenti senza password di accedere al dispositivo usando un account personale o un account aziendale o dell'Istituto di istruzione. L'utente viene autorizzato automaticamente con SSO per tutte le app e i servizi integrati tramite le [API di Gestione account Web](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041).

Dopo l'aggiunta di un'identità tramite una sola applicazione, con il consenso dell'utente potrà essere resa disponibile a tutte le app e a tutti i servizi usando l'integrazione a livello di sistema. Questo semplifica notevolmente la procedura di accesso alle app e offre agli utenti un'esperienza coerente per l'identità.

Per altre informazioni sull'implementazione delle API di Gestione account Web, passa a [Implementazione delle API di Gestione account Web](https://docs.microsoft.com/windows/uwp/security/web-account-manager).

  ![Accesso con Windows Hello](images/security-api-img.png)
  
Per le suite di app con requisiti di autenticazione specifici, il framework di Gestione account Web è estensibile ai provider di identità personalizzati. Gli utenti possono scaricare il provider di identità personalizzato, disponibile in pacchetto come app della piattaforma UWP (Universal Windows Platform) su Microsoft Store, per abilitare SSO su altre app integrate con quel provider di identità. 

Per altre informazioni sull'implementazione dei provider di identità WAM personalizzati, vedere la documentazione di [riferimento all'API del provider di identità WAM personalizzato](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041).

## Accesso Windows Hello e FIDO2 con WebAuthn

HoloLens 2 può usare le credenziali utente senza password (come le chiavi di sicurezza di Windows Hello o FIDO2) per accedere in modo sicuro sul Web tramite Microsoft Edge e ai siti Web che supportano WebAuthn. Con FIDO2, le credenziali utente possono sfruttare i dispositivi basati sugli standard per l'autenticazione ai servizi online.

> [!Note] 
> Le specifiche [WebAuthn](https://www.w3.org/TR/webauthn/) e FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) sono implementate nei servizi. I metadati firmati specificati da WebAuthn e FIDO2 forniscono informazioni, ad esempio sulla presenza dell'utente, e verificano l'autenticazione attraverso il movimento a livello locale.

Come per Windows Hello, quando l'utente crea e registra una credenziale FIDO2, il dispositivo (chiave di sicurezza HoloLens 2 o FIDO2) genera una chiave privata e pubblica nel dispositivo. La chiave privata viene archiviata in modo sicuro nel dispositivo e può essere usata solo dopo che è stata sbloccata con un movimento locale, ad esempio una biometria o un PIN. Una volta archiviata la chiave privata, la chiave pubblica viene inviata al sistema dell'account Microsoft nel cloud e registrata con l'account utente associato.

Dopo avere eseguito l'accesso con un account MSA e AAD, il sistema invia una variabile numerica o di dati generata al dispositivo HoloLens 2 o FIDO2. HoloLens 2 o il dispositivo usa la chiave privata per firmare l'identificazione. L'identificazione firmata e i metadati vengono inviati di nuovo al sistema dell'account Microsoft e verificati usando la chiave pubblica.

I dispositivi Windows Hello e FIDO2 implementano le credenziali in base al dispositivo HoloLens, in particolare un enclave sicuro Trusted Platform Module integrato. Il gruppo TPM archivia la chiave privata e richiede una biometria o un PIN per lo sblocco. Analogamente, una chiave di sicurezza FIDO2 è un piccolo dispositivo esterno con un enclave sicuro integrato che archivia la chiave privata e richiede una biometria o un PIN per lo sblocco.

Entrambe le opzioni offrono l'autenticazione a due fattori in un unico passaggio, che richiede sia un dispositivo registrato che una biometria o un PIN per eseguire correttamente l'accesso. Per altre informazioni, fare riferimento all'immagine relativa alla chiave di sicurezza FIDO2 riportata di seguito:

  ![FIDO img](images/security-fido2-whfb.png)

MSA e AAD sono tra le prime relying party a supportare l'autenticazione senza password implementando WebAuthn. 

Per altre informazioni sull'uso di WebAuthn con applicazioni e/o SDK, passare a [API WebAuthn per l'autenticazione senza password in Windows 10](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis).

## Account locali

È possibile configurare un singolo account locale per le distribuzioni in modalità offline. Gli account locali non sono abilitati per impostazione predefinita e devono essere configurati durante il provisioning del dispositivo. Devono eseguire l'accesso con una password e non supportano metodi di autenticazione alternativi, come [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) o [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello). 

Per altre informazioni sugli account utente di HoloLens, vedere [Identità HoloLens](https://docs.microsoft.com/hololens/hololens-identity). 

Gli amministratori IT definiscono se l'utente può usare un account MSA per l'autenticazione e i servizi di connessione non correlati all'e-mail tramite [AllowMicrosoftAccountConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection). Per i criteri di configurazione delle password, i criteri di inattività e i criteri della schermata di blocco, vedere [DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock). 
