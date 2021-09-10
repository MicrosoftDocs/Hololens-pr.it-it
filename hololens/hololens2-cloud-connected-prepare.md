---
title: Guida alla distribuzione - Distribuzione HoloLens 2 cloud su larga scala con Remote Assist - Preparare
description: Informazioni su come preparare la registrazione HoloLens dispositivi in una rete connessa al cloud usando Azure Active Directory e gestione delle identità.
keywords: HoloLens, gestione, connessa al cloud, Remote Assist, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428766"
---
# <a name="prepare---cloud-connected-guide"></a>Preparazione - Guida connessa al cloud

Alla fine di questo articolo si avrà configurato Azure AD, MDM e si avranno altre informazioni sull'uso degli account Azure AD e dei requisiti di rete. Questa sezione della guida consente all'utente e all'organizzazione di prepararsi a distribuire HoloLens 2 nel cloud e a Dynamics 365 Remote Assist. Verrà inoltre illustrata l'importanza di ogni parte dell'infrastruttura e verranno forniti collegamenti alle guide che consentono di configurare tali componenti in base alle esigenze.

## <a name="infrastructure-essentials"></a>Informazioni di base sulle infrastrutture

Per scenari di distribuzione sia personali che aziendali, un sistema MDM è l'infrastruttura essenziale necessaria per distribuire e gestire i Windows 10 Holographic mobili. È consigliata una sottoscrizione ad Azure AD Premium come provider di identità, necessaria per supportare determinate funzionalità.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD è un servizio directory basato su cloud che offre funzionalità di gestione delle identità e dell'accesso. Le organizzazioni che usano Microsoft Office 365 o Intune usano già Azure AD, che include tre edizioni: Gratuito, Premium P1 e Premium P2 (vedere Azure Active Directory [edition).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Tutte le edizioni Azure AD la registrazione del dispositivo, ma Premium P1 è necessaria per abilitare la registrazione automatica MDM che verrà utilizzata in questa guida più avanti.

> [!IMPORTANT]
> È essenziale disporre di un Azure Active Directory perché i dispositivi HoloLens non supportano l'aggiunta ad ACTIVE Directory locale. Se non si&#39;è già configurato un Azure Active Directory, passare [a Creare un nuovo tenant in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Identity Management

I dipendenti possono usare un solo account per inizializzare un dispositivo in modo&#39;imperativo che l'organizzazione controlli per primo quale account è abilitato. L'account scelto determinerà chi controlla il dispositivo e influirà sulle funzionalità di gestione.

In questa guida è stato [](/hololens/hololens-identity) scelto che per l'identità usata verranno usati Azure AD account o Azure Active Directory account. Esistono diversi vantaggi per gli Azure AD che si vuole usare, ad esempio:

- I dipendenti usano il proprio account Azure AD per registrare il dispositivo in Azure AD e registrarlo automaticamente nella soluzione MDM dell'organizzazione&#39;(Azure AD+MDM– richiede Azure AD Premium).
- Azure AD supportano [l'accesso Single Sign-On.](/azure/active-directory/manage-apps/what-is-single-sign-on) Quando un utente accede a Remote Assist, l'identità dell'utente Azure AD connesso verrà riconosciuta e l'utente accederà all'app per un'esperienza semplificata.
- Azure AD account hanno opzioni [di autenticazione aggiuntive](/hololens/hololens-identity) tramite Windows Hello for [Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification). Oltre a Iris, gli utenti possono accedere da un altro dispositivo o usare le chiavi di sicurezza FIDO.

### <a name="mobile-device-management"></a>Gestione dei dispositivi mobili

Microsoft [Intune,](/mem/intune/fundamentals/what-is-intune)parte del Enterprise Mobility + Security, è un sistema MDM basato sul cloud che gestisce i dispositivi connessi al tenant. Come Office 365, Intune usa Azure AD per la gestione delle identità, quindi i dipendenti usano le stesse credenziali per registrare i dispositivi in Intune che usano per accedere Office 365. Intune supporta anche i dispositivi che eseguono altri sistemi operativi, ad esempio iOS e Android, per fornire una soluzione MDM completa. Ai fini di questa guida, verrà&#39;'uso di Intune per abilitare una distribuzione cloud su larga scala con HoloLens 2.

> [!IMPORTANT]
> È essenziale disporre della gestione dei dispositivi mobili. Se non è&#39;configurato, seguire questa guida e [Introduzione a Intune.](/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Più sistemi MDM supportano Windows 10 e la maggior parte supporta scenari di distribuzione con dispositivi personali e aziendali. I provider MDM che supportano Windows 10 Holographic attualmente includono: AirWatch, MobileIron e altri. La maggior parte dei fornitori di soluzioni MDM leader del settore supporta già l'integrazione con Azure AD. Puoi trovare i fornitori MDM che supportano Azure AD in [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Rete

In questa configurazione si prevede HoloLens 2 dispositivi che si connettono a Internet da qualsiasi rete Wi-Fi aperta disponibile. Poiché un utente potrebbe dover modificare la connessione di rete in base alla posizione, dovrebbe imparare a connettere HoloLens [dispositivi al Wi-Fi.](/hololens/hololens-network)

Ad Dynamics 365 Remote Assist sono presenti diverse condizioni di rete, tra cui larghezza di banda, latenza, jitter e perdita di pacchetti, che possono influire sull'esperienza di videochiamata. Anche se le chiamate audio e video potrebbero essere possibili in ambienti con larghezza di banda ridotta, è possibile che si verifichi una riduzione delle funzionalità. Quando si Dynamics 365 Remote Assist in HoloLens, ecco i requisiti di rete da tenere presenti:

**Minimo:** sono necessari 1,5 Mbps per le chiamate video di qualità HD peer-to-peer con risoluzione hd 1080p a 30 fps.

**Ottimale:** Per le videochiamate di qualità HD peer-to-peer con risoluzione HD 1080p, dovrebbero essere previsti 4-5 Mbps di up/down.

Altre informazioni:

- [Requisiti di rete](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Raccomandazioni per l'ottimizzazione della rete](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Facoltativo: Connessione il HoloLens vpn

I dispositivi connessi a questa guida si connetteranno alla rete tramite una rete cloud esterna. Può essere che per accedere alle risorse aziendali&#39;necessario connettere i dispositivi tramite VPN. Esistono diversi modi per connettere i dispositivi alla VPN, sia in cui l'utente finale può connettersi tramite l'interfaccia utente del dispositivo oppure i dispositivi possono essere gestiti e ricevere il profilo VPN da un PPKG o MDM. Come configurare la VPN&#39;non sarà trattato in questo articolo, quindi se&#39;si vuole ottenere altre informazioni sui diversi protocolli VPN o sui modi per gestire la VPN, visitare queste guide per informazioni su HoloLens e [VPN.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud - Configurare](hololens2-cloud-connected-configure.md)
