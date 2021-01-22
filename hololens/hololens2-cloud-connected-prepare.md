---
title: Guida alla distribuzione-cloud connected HoloLens 2 distribuzione in scala con assistenza remota-preparazione
description: Informazioni su come preparare la registrazione dei dispositivi HoloLens tramite una rete connessa al cloud con Azure Active Directory e gestione delle identità.
keywords: HoloLens, gestione, cloud connected, Remote Assist, AAD, Azure AD, MDM, gestione di dispositivi mobili
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283867"
---
# Preparare-guida connessa al cloud

Alla fine di questo articolo sarà necessario configurare Azure AD, MDM e altre informazioni sull'uso degli account di Azure AD e dei requisiti di rete. Questa sezione della guida aiuta l'utente e l'organizzazione a preparare la distribuzione di HoloLens 2 al cloud e a usare Dynamics 365 Remote assist. Verrà rilevata l'importanza di ogni parte dell'infrastruttura, oltre a fornire collegamenti alle guide che consentono di configurare i pezzi in base alle esigenze.

## Elementi essenziali dell'infrastruttura

Per gli scenari di distribuzione sia personali che aziendali, un sistema MDM è l'infrastruttura essenziale necessaria per distribuire e gestire dispositivi olografici di Windows 10. È consigliata una sottoscrizione ad Azure AD Premium come provider di identità, necessaria per supportare determinate funzionalità.

### Azure Active Directory

Azure AD è un servizio directory basato su cloud che offre funzionalità di gestione delle identità e dell'accesso. Le organizzazioni che usano Microsoft Office 365 o Intune stanno già usando Azure AD, che include tre edizioni: Free, Premium P1 e Premium P2 (Vedi [edizioni di Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Tutte le edizioni supportano la registrazione di Azure AD Device, ma è necessario Premium P1 per abilitare l'iscrizione automatica MDM che useremo in seguito in questa guida.

> [!IMPORTANT]
> È essenziale avere un Azure Active Directory come dispositivi HoloLens non supportano l'aggiunta di annunci locali. Se si Don&#39;t è già stata configurata una configurazione di Azure Active Directory, seguire le istruzioni in questo collegamento per iniziare e [creare un nuovo tenant in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## Gestione delle identità

I dipendenti possono usare un solo account per inizializzare un dispositivo in modo che&#39;s imperativo che l'organizzazione controlli per primo quale account è abilitato. L'account scelto determinerà chi controlla il dispositivo e influirà sulle funzionalità di gestione.

In questa guida abbiamo scelto che per l' [identità](https://docs.microsoft.com/hololens/hololens-identity) usata useremo gli account di Azure ad o gli account di Azure Active Directory. Ci sono diversi vantaggi per gli account di Azure AD da usare, ad esempio:

- I dipendenti usano l'account di Azure ad per registrare il dispositivo in Azure AD e registrarlo automaticamente con l'organizzazione&#39;la soluzione MDM (Azure AD + MDM-richiede Azure AD Premium).
- Gli account di Azure AD supportano [Single Sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on). Quando un utente accede a Remote Assist, la sua identità dall'utente firmato in Azure AD verrà riconosciuta e l'utente verrà connesso all'app per un'esperienza semplificata.
- Gli account di Azure AD hanno [Opzioni di autenticazione](https://docs.microsoft.com/hololens/hololens-identity) aggiuntive tramite [Windows Hello for business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Oltre agli utenti di log-in Iris, è possibile accedere da un altro dispositivo o usare le chiavi di sicurezza FIDO.

### Gestione dei dispositivi mobili

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), parte di Enterprise Mobility + Security, è un sistema MDM basato su cloud che gestisce i dispositivi connessi al tenant. Come Office 365, Intune USA Azure AD per la gestione delle identità, quindi i dipendenti usano le stesse credenziali per la registrazione dei dispositivi in Intune che usano per accedere a Office 365. Intune supporta anche i dispositivi che eseguono altri sistemi operativi, come iOS e Android, per ottenere una soluzione MDM completa. Ai fini di questa guida, ci&#39;concentrare sull'uso di Intune per abilitare una distribuzione cloud in scala con HoloLens 2.

> [!IMPORTANT]
> È essenziale avere la gestione di dispositivi mobili. Se Don&#39;t è già configurato, seguire questa guida e [iniziare a usare Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> Più sistemi MDM supportano Windows10 e la maggior parte supporta scenari di distribuzione con dispositivi personali e aziendali. I provider MDM che supportano Windows 10 olografico includono attualmente: MobileIron e altri. La maggior parte dei fornitori di soluzioni MDM leader del settore supporta già l'integrazione con Azure AD. Puoi trovare i fornitori MDM che supportano Azure AD in [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## Rete

In questa configurazione anticipiamo i dispositivi HoloLens 2 che si connettono a Internet da qualsiasi rete Open Wi-Fi disponibile. Dato che un utente potrebbe dover modificare la connessione di rete in base alla posizione, dovrebbe imparare a [connettere i dispositivi HoloLens a Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Per l'assistenza remota di Dynamics 365 è disponibile una varietà di condizioni di rete, tra cui larghezza di banda, latenza, jitter e perdita di pacchetti che possono influire sull'esperienza di videochiamata. Anche se le chiamate audio e video possono essere possibili in ambienti con larghezza di banda ridotta, potresti riscontrare una degradazione delle funzionalità. Quando si usa Dynamics 365 Remote assist in HoloLens Ecco i requisiti di rete da ricordare:

**Minimum** : è necessario 1,5 Mbps up/down per le chiamate video di qualità HD peer-to-peer con risoluzione di HD 1080p a 30 fps.

**Ottimale:** Per le videochiamate di qualità HD peer-to-peer con risoluzione di HD 1080p, dovrebbe essere previsto un massimo di 4-5 Mbps.

Altre informazioni:

- [Requisiti di rete](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Suggerimenti per l'ottimizzazione della rete](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### Facoltativo: connettere il proprio HoloLens alla VPN

I dispositivi collegati in questa guida si connetteranno alla rete via e alla rete cloud esterna. Può essere che per accedere alle risorse aziendali&#39;necessario connettere i dispositivi tramite VPN. Esistono diversi modi per connettere i dispositivi alla rete VPN, in cui l'utente finale può connettersi tramite l'interfaccia utente del dispositivo oppure i dispositivi possono essere gestiti e ricevere il profilo VPN da un PPKG o MDM. Come configurare la VPN vinta&#39;t essere trattati in questo articolo, quindi se si&#39;d come per saperne di più sui diversi protocolli VPN o modi per gestire la VPN, visitare [queste guide per informazioni su HoloLens e VPN.](https://docs.microsoft.com/hololens/hololens-network#vpn)

## Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud-configura](hololens2-cloud-connected-configure.md)
