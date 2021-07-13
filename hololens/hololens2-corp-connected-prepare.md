---
title: Guida alla distribuzione - Connessione aziendale HoloLens 2 con Dynamics 365 Guides - Preparare
description: Informazioni su come preparare la registrazione HoloLens 2 dispositivi in una rete connessa aziendale con Dynamics 365 Guides.
keywords: HoloLens, gestione, aziendale connessa, Dynamics 365 Guides, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.openlocfilehash: 88e7d0614cf95f32eaa0434724eddbcb5b8cf863
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636980"
---
# <a name="prepare---corporate-connected-guide"></a>Preparazione - Guida connessa aziendale
## <a name="infrastructure-essentials"></a>Informazioni di base sulle infrastrutture
Per gli scenari di distribuzione sia personali che aziendali, un sistema di gestione dei dispositivi mobili (MDM) è l'infrastruttura essenziale necessaria per distribuire e gestire i dispositivi Windows 10, in particolare il HoloLens 2. Una [Azure AD Premium è consigliata](/azure/active-directory/fundamentals/active-directory-get-started-premium) come provider di identità ed è **necessaria** per supportare determinate funzionalità.

> [!NOTE]
> Sebbene il HoloLens 2 sia distribuito e gestito come un dispositivo mobile, viene in genere usato come dispositivo condiviso tra molti utenti.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD è un servizio directory basato su cloud che offre funzionalità di gestione delle identità e dell'accesso. Le organizzazioni che usano Microsoft Office 365 o Intune usano già Azure AD, che include tre edizioni: Gratuito, Premium P1 e Premium P2 (vedere [Azure Active Directory edition).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Tutte le edizioni Azure AD la registrazione del dispositivo, ma Premium P1 è necessaria per abilitare la registrazione automatica MDM che verrà utilizzata in questa guida più avanti.
> [!Important]
> È essenziale disporre di un Azure AD perché HoloLens non supportano l'aggiunta ad AD locale. Se non è già stato configurato un Azure AD, seguire le istruzioni per iniziare [e Creare un](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)nuovo tenant in Azure Active Directory .

## <a name="identity-management"></a>Identity Management
In questa guida, [l'identità](/hololens/hololens-identity) usata sarà Azure AD account. Esistono diversi vantaggi per gli account Azure AD, ad esempio:

- I dipendenti usano il proprio account Azure AD per registrare il dispositivo in Azure AD e possono registrarlo automaticamente con la soluzione MDM dell'organizzazione (Azure AD+MDM: richiede una sottoscrizione Azure AD Premium [aziendale).](/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Azure AD account hanno opzioni [di autenticazione aggiuntive](/hololens/hololens-identity) tramite Windows Hello for [Business.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Oltre all'accesso Iris, gli utenti possono accedere da un altro dispositivo o usare chiavi di sicurezza FIDO.

> [!WARNING] 
> I dipendenti possono usare un solo account per inizializzare un dispositivo, quindi è fondamentale che **l'organizzazione** controlli quale account è abilitato per primo. L'account scelto determinerà chi controlla il dispositivo e influirà sulle funzionalità di gestione.

## <a name="mobile-device-management"></a>Gestione dei dispositivi mobili
Microsoft Intune, parte di Enterprise Mobility + Security, è un sistema MDM basato sul cloud che gestisce i dispositivi connessi al tenant. Come Office 365, Intune usa Azure AD per la gestione delle identità, quindi i dipendenti usano le stesse credenziali per registrare i dispositivi in Intune che usano per accedere Office 365. Intune supporta anche i dispositivi che eseguono altri sistemi operativi, ad esempio iOS e Android, per fornire una soluzione MDM completa. Ai fini di questa guida, ci si concentrerà sull'uso di Intune per abilitare una distribuzione nella rete interna con HoloLens 2.
> [!Important] 
> È essenziale disporre della gestione dei dispositivi mobili. Se non è già stato configurato, seguire questa guida e Introduzione a Intune.

> [!Important]
> Per usare Guide, è necessario Azure AD account.

> [!Note] 
> Più sistemi MDM supportano Windows 10 e la maggior parte supporta scenari di distribuzione con dispositivi personali e aziendali. I provider MDM che supportano Windows 10 Holographic includono: AirWatch, MobileIron e altri. La maggior parte dei fornitori di soluzioni MDM leader del settore supporta già l'integrazione con Azure AD. È possibile trovare l'elenco più attuale dei fornitori MDM che supportano Azure AD in [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Accesso alla rete 
Dynamics 365 Guides è un'applicazione basata sul cloud. Se l'amministratore di rete ha un elenco di approvazione, potrebbe essere necessario aggiungere gli indirizzi IP e/o gli endpoint necessari per connettersi ai server Dynamics 365. [Altre informazioni sullo sblocco di indirizzi IP e URL.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certificati
I certificati consentono di migliorare la sicurezza fornendo l'autenticazione dell'account, Wi-Fi, la crittografia VPN e la crittografia SSL del contenuto Web. Anche se gli amministratori possono gestire manualmente i certificati nei dispositivi tramite il provisioning dei pacchetti, è consigliabile usare il sistema MDM per gestire tali certificati per l'intero ciclo di vita, dalla registrazione al rinnovo e alla revoca. 

Il sistema MDM può distribuire automaticamente questi certificati agli archivi certificati dei dispositivi dopo averli registrati (purché il sistema MDM supporti **Simple Certificate Enrollment Protocol (SCEP)** o **Public Key Cryptography Standards #12 (PKCS #12)**). [Informazioni sui tipi di certificato e sui profili utilizzati con Microsoft Intune](/mem/intune/protect/certificates-configure). MDM può anche eseguire query ed eliminare i certificati client registrati o attivare una nuova richiesta di registrazione prima della scadenza del certificato corrente.

Se i sistemi MDM sono già configurati per i certificati, fare riferimento a Preparare i certificati e i profili di rete [per](/hololens/hololens-certificates-network) HoloLens 2 per avviare la distribuzione di certificati e profili per i HoloLens 2 mobili.

## <a name="scep"></a>SCEP

I servizi seguenti sono necessari per la distribuzione SCEP, ad eccezione del server Web Application Proxy Server.

- [Autorità di certificazione](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Ruolo del server NDES](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Connettore Microsoft Intune](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

È anche necessario pubblicare l'URL NDES esterno alla rete aziendale usando Azure AD proxy di applicazione [o Accesso Web Proxy.](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) È anche possibile usare un altro proxy inverso di propria scelta.

![Flusso di dati SCEP](./images/hololens2-scep-info-flow.png)

Se la rete non supporta già SCEP o non si è certi che la rete sia configurata correttamente per SCEP con Intune, fare riferimento a Configurare l'infrastruttura per supportare [SCEP con Intune.](/mem/intune/protect/certificates-scep-configure)

Se l'infrastruttura supporta già SCEP, [](/mem/intune/protect/certificates-profile-scep) è [](/mem/configmgr/protect/deploy-use/create-certificate-profiles) necessario creare un profilo per ogni certificato SCEP che verrà HoloLens 2. Se si verificano problemi con SCEP, usare Risoluzione dei problemi relativi all'uso dei [profili certificato SCEP](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)per effettuare il provisioning dei certificati con Microsoft Intune .

## <a name="pkcs"></a>PKCS
Intune supporta anche l'uso di certificati PKCS (Public Key Pair) e privati. Per [altre informazioni, vedere](/mem/intune/protect/certificates-pfx-configure) Usare certificati a chiave pubblica Microsoft Intune privata e pubblica.

## <a name="proxy"></a>Proxy
La maggior parte delle reti Intranet aziendali sfrutta un proxy per gestire il traffico esterno. Con HoloLens 2 è possibile configurare un server proxy per le connessioni ethernet, Wi-Fi e VPN.

Esistono diversi tipi di proxy e modi per configurare il proxy. Ai fini di questa guida, si sceglie di scegliere il **proxy Wi-Fi,** impostare tramite l'URL PAC e distribuire tramite MDM. Ciò offre i vantaggi della distribuzione automatica tramite MDM, della possibilità di aggiornare il file PAC invece di usare una configurazione server:porta e infine di usare un proxy Wi-Fi per configurare il proxy in modo da applicarlo solo a una singola connessione Wi-Fi che consente di usare i dispositivi ancora se connessi in un'altra posizione.

Per altre informazioni sulle impostazioni proxy per Windows 10, vedere Creare un profilo Wi-Fi per i [dispositivi in Microsoft Intune - Azure](/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>App line-of-business 
Anche se è possibile installare diverse app tramite il Microsoft Store, è probabile che si abbia una propria app personalizzata creata appositamente per l'uso in realtà mista. Queste app personalizzate distribuite in tutta l'organizzazione per l'azienda sono denominate app line-of-business (LOB).
  
Esistono diversi modi per distribuire applicazioni in HoloLens 2 dispositivi. Le app possono essere distribuite direttamente tramite MDM, Microsoft Store per le aziende(MSfB) o sideloaded tramite un pacchetto di provisioning. Ai fini di questa guida, le app verranno distribuite tramite MDM, tramite l'uso dell'installazione dell'app richiesta. In questo modo le app LOB verranno scaricate automaticamente nei dispositivi HoloLens al termine della registrazione.

Per gli utenti che non hanno il proprio loB, verrà fornito un'app di esempio per testare questo flusso di distribuzione. Questa app sarà l'app [Esempi MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) ed è già stata precompilata e in pacchetto per testare il modello di verifica.

Altri dettagli sulla distribuzione delle app sono disponibili in [Gestione app: Panoramica.](/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 supporta solo l'esecuzione di app ARM64 UWP.

## <a name="guides-playbook"></a>Guide Playbook
Guides usa un ambiente Microsoft Dataverse come archivio dati per le app Guide. È importante comprendere il quadro generale dell'interazione dell'ambiente Dataverse con le app Guide e il tenant. In questa guida non verrà illustrato come gestire i dativerse, ma vedere Concetti di base per la distribuzione di Dynamics 365 Guides [- Dynamics 365 Mixed Reality](/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Passaggio successivo 
> [!div class="nextstepaction"]
> [Distribuzione connessa aziendale - Configurare](hololens2-corp-connected-configure.md)