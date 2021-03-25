---
title: Guida alla distribuzione - HoloLens 2 connesso all'azienda con guide di Dynamics 365 - Preparare
description: Informazioni su come prepararsi per la registrazione dei dispositivi HoloLens 2 su una rete connessa aziendale con le guide di Dynamics 365.
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
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448569"
---
# <a name="prepare---corporate-connected-guide"></a>Preparare - Guida aziendale connessa
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
Per gli scenari di distribuzione sia personali che aziendali, un sistema di gestione dei dispositivi mobili (MDM) è l'infrastruttura essenziale necessaria per distribuire e gestire i dispositivi Windows 10, in particolare HoloLens 2. Una [sottoscrizione Di Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) è consigliata come provider di identità e **necessaria** per supportare determinate funzionalità.

> [!NOTE]
> Anche se HoloLens 2 viene distribuito e gestito come un dispositivo mobile, in genere viene usato come dispositivo condiviso tra molti utenti.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD è un servizio directory basato su cloud che offre funzionalità di gestione delle identità e dell'accesso. Le organizzazioni che usano Microsoft Office 365 o Intune usano già Azure AD, che ha tre edizioni: Free, Premium P1 e Premium P2 (vedi edizioni [di Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Tutte le edizioni supportano la registrazione dei dispositivi Azure AD, ma Premium P1 è necessario per abilitare la registrazione automatica MDM che verrà utilizzata in questa guida più avanti.
> [!Important]
> È essenziale disporre di azure AD perché i dispositivi HoloLens non supportano l'aggiunta ad AD locale. Se non si dispone già di una configurazione di Azure AD, seguire le istruzioni per iniziare [e Creare un nuovo tenant in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Identity Management
In questa guida, [l'identità](https://docs.microsoft.com/hololens/hololens-identity) usata sarà account Azure AD. Esistono diversi vantaggi per gli account Azure AD, ad esempio:
- I dipendenti usano il proprio account Azure AD per registrare il dispositivo in Azure AD e possono registrarlo automaticamente con la soluzione MDM dell'organizzazione (Azure AD+MDM – richiede una sottoscrizione [Di Azure AD Premium).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Gli account Azure AD hanno [opzioni di autenticazione aggiuntive](https://docs.microsoft.com/hololens/hololens-identity) tramite Windows Hello for [Business.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Oltre all'accesso Iris, gli utenti possono accedere da un altro dispositivo o usare le chiavi di sicurezza FIDO.

> [!WARNING] 
> I dipendenti possono usare un solo account per inizializzare un dispositivo, quindi è imperativo che **l'organizzazione**controlli quale account è abilitato per primo. L'account scelto determinerà chi controlla il dispositivo e influirà sulle funzionalità di gestione.

## <a name="mobile-device-management"></a>Gestione dei dispositivi mobili
Microsoft Intune, parte di Enterprise Mobility + Security, è un sistema MDM basato su cloud che gestisce i dispositivi connessi al tenant. Come Office 365, Intune usa Azure AD per la gestione delle identità, quindi i dipendenti usano le stesse credenziali per registrare i dispositivi in Intune che usano per accedere a Office 365. Intune supporta anche dispositivi che eseguono altri sistemi operativi, ad esempio iOS e Android, per fornire una soluzione MDM completa. Ai fini di questa guida, ci concentreremo sull'uso di Intune per abilitare una distribuzione nella rete interna con HoloLens 2.
> [!Important] 
> È essenziale disporre di Gestione dispositivi mobili. Se non è già stata impostata, seguire questa guida e Iniziare a usare Intune.

> [!Important]
> Per usare Guide, è necessario un account Azure AD.

> [!Note] 
> Più sistemi MDM supportano Windows10 e la maggior parte supporta scenari di distribuzione con dispositivi personali e aziendali. I provider MDM che supportano Windows 10 Holographic includono: AirWatch, MobileIron e altri. La maggior parte dei fornitori di soluzioni MDM leader del settore supporta già l'integrazione con Azure AD. È possibile trovare l'elenco più attuale dei fornitori MDM che supportano Azure AD in [Azure Marketplace.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Accesso di rete 
Dynamics 365 Guides è un'applicazione basata sul cloud. Se l'amministratore di rete ha un elenco di approvazione, potrebbe essere necessario aggiungere gli indirizzi IP e/o gli endpoint necessari per connettersi ai server Dynamics 365. [Ulteriori informazioni sullo sblocco di indirizzi IP e URL.](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certificati
I certificati consentono di migliorare la sicurezza fornendo l'autenticazione Wi-Fi account, la crittografia VPN e la crittografia SSL del contenuto Web. Anche se gli amministratori possono gestire manualmente i certificati nei dispositivi tramite pacchetti di provisioning, è consigliabile usare il sistema MDM per gestire tali certificati per l'intero ciclo di vita, dalla registrazione al rinnovo e alla revoca. 

Il sistema MDM può distribuire automaticamente questi certificati agli archivi certificati dei dispositivi dopo averli registrati (purché il sistema MDM supporti il protocollo **SCEP (Simple Certificate Enrollment Protocol)** o **public key cryptography standards #12 (PKCS#12).** [Informazioni sui tipi di certificato e sui profili utilizzati con Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/certificates-configure) MDM può anche eseguire query ed eliminare i certificati client registrati o attivare una nuova richiesta di registrazione prima della scadenza del certificato corrente.
 
Se i sistemi MDM sono già configurati per i certificati, fare riferimento a Preparare i certificati e i profili di rete per [HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) per avviare la distribuzione di certificati e profili per i dispositivi HoloLens 2.

## <a name="scep"></a>SCEP

I servizi seguenti sono necessari per la distribuzione SCEP, ad eccezione del server proxy dell'applicazione Web.
- [Autorità di certificazione](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Ruolo del server NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Connettore Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

È inoltre necessario pubblicare l'URL NDES esterno alla rete aziendale utilizzando il [proxy dell'applicazione Azure AD o il proxy di accesso Web.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Puoi anche usare un altro proxy inverso di tua scelta.

![Flusso di dati SCEP](./images/hololens2-scep-info-flow.png)

Se la rete non supporta già SCEP o non si è certi che la rete sia configurata correttamente per SCEP con Intune, fare riferimento a Configurare l'infrastruttura per supportare [SCEP con Intune.](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)

Se l'infrastruttura supporta già SCEP, [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) sarà [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) necessario creare un profilo per ogni certificato SCEP che verrà utilizzato da HoloLens 2. Se si verificano problemi con SCEP, usare Risoluzione dei problemi relativi all'uso dei profili certificato SCEP per [effettuare il provisioning dei certificati con Microsoft Intune.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)

## <a name="pkcs"></a>PKCS
Intune supporta inoltre l'uso di certificati pkcs (Public Key Pair) e privati. Riferimento [Usare certificati a chiave pubblica e privata in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) per altre informazioni.

## <a name="proxy"></a>Proxy
La maggior parte delle reti Intranet aziendali sfrutta un proxy per gestire il traffico esterno. Con HoloLens 2 puoi configurare un server proxy per le connessioni ethernet, Wi-Fi e VPN.

Esistono diversi tipi di proxy e modi per configurare il proxy. Ai fini di questa guida, scegliamo il **proxy Wi-Fi,** l'impostazione tramite URL PAC e la distribuzione tramite MDM. Ciò offre i vantaggi di essere distribuiti automaticamente tramite MDM, di poter aggiornare il file PAC invece di usare una configurazione server:port e infine di usare un proxy di Wi-Fi per configurare il proxy per applicarlo solo a una singola connessione Wi-Fi consentendo l'uso dei dispositivi ancora se connessi in un'altra posizione. 


Per altri dettagli sulle impostazioni proxy per Windows 10, vedi Creare un profilo Wi-Fi per i dispositivi [in Microsoft Intune - Azure.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>App line-of-business 
Anche se è possibile installare diverse app tramite Microsoft Store, è probabile che tu abbia una tua app personalizzata creata appositamente per l'uso in realtà mista. Queste app personalizzate distribuite in tutta l'organizzazione per la tua azienda sono denominate app Line of Business (LOB).
  
Esistono diversi modi per distribuire le applicazioni nei dispositivi HoloLens 2. Le app possono essere distribuite direttamente tramite MDM, Microsoft Store per le aziende (MSfB) o sideloaded tramite un pacchetto di provisioning. Ai fini di questa guida, distribuiremo le app tramite MDM, tramite l'uso dell'installazione delle app necessaria. In questo modo le app LOB verranno scaricate automaticamente nei dispositivi HoloLens al termine della registrazione.

Per coloro che non hanno un proprio loB, forniremo un'app di esempio per testare questo flusso di distribuzione. Questa app sarà l'app [Esempi MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) ed è già stata precompilata e in pacchetto per testare la prova del concetto.
 
Altri dettagli sulla distribuzione delle app sono disponibili in [Gestione app: Panoramica](https://docs.microsoft.com/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2 supporta solo l'esecuzione di app ARM64 UWP.

## <a name="guides-playbook"></a>Guide Playbook
Guides usa un ambiente Microsoft Dataverse come archivio dati per le app Guide. È importante comprendere l'immagine più ampia del modo in cui l'ambiente Dataverse interagisce con le app Guide e il tenant. Non verrà illustrato come gestire i dati in questa guida, ma leggere i concetti di base per la distribuzione di [Dynamics 365 Guides - Dynamics 365 Mixed Reality.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook)

## <a name="next-step"></a>Passaggio successivo 
> [!div class="nextstepaction"]
> [Distribuzione connessa aziendale - Configurare](hololens2-corp-connected-configure.md)