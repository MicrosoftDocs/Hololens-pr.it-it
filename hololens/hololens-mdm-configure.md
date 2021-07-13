---
title: Uso di Microsoft Endpoint Manager Intune per gestire HoloLens dispositivi
description: Informazioni su come usare MDM per configurare CSP, criteri e gestire HoloLens dispositivi di realtà mista su larga scala con Intune.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640279"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Uso di Microsoft Endpoint Manager Intune per gestire HoloLens dispositivi

Esistono numerose impostazioni diverse che è possibile gestire tramite MDM. L'uso dei dispositivi di Intune può essere raggruppato e le configurazioni possono essere distribuite a tali gruppi di utenti o dispositivi. Le app possono anche essere distribuite e gestite, configurando i dispositivi per la connessione alla rete, nonché configurando gli aggiornamenti in modo che si verifichino nel momento desiderato e nell'anello di aggiornamento necessario. 

## <a name="how-to-manage-via-intune"></a>Come gestire tramite Intune

### <a name="device-categories-and-groups"></a>Categorie e gruppi di dispositivi
Con Intune è possibile creare categorie di dispositivi per aggiungere automaticamente i dispositivi ai gruppi in base alle categorie create, ad esempio ingegneria, medici, sviluppatori e così via. L'idea è semplificare la gestione dei dispositivi che eseguono Windows Holographic for Business.
Altre informazioni: [Classificare i dispositivi in gruppi](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Profili di configurazione dispositivo
Intune include impostazioni e funzionalità che è possibile abilitare o disabilitare in dispositivi diversi all'interno dell'organizzazione. Queste impostazioni e funzionalità vengono gestite usando i profili. Ad esempio, è possibile creare un profilo che abilita Cortana o usa Microsoft Defender SmartScreen nei dispositivi che eseguono Windows Holographic for Business.
Nei profili è possibile usare URI OMA per personalizzare alcune impostazioni, creare restrizioni dei dispositivi e configurare una rete privata virtuale (VPN) e Wi-Fi.
[Introduzione ai profili di configurazione e](/mem/intune/configuration/device-profiles)panoramica del [profilo](/mem/intune/configuration/device-profile-create).

## <a name="examples-of-what-can-be-managed-and-configured"></a>Esempi di cosa può essere gestito e configurato

L'uso di MDM per gestire i dispositivi offre un'ampia gamma di elementi che è possibile selezionare. 

### <a name="wi-fi"></a>Wi-Fi
[Impostazioni Wi-Fi](/mem/intune/configuration/wi-fi-settings-configure) assegna le impostazioni di rete wireless a utenti e dispositivi. Quando si assegna un profilo Wi-Fi, gli utenti ottengono l'accesso al Wi-Fi aziendale senza doverlo configurare.
Altre informazioni sulla [configurazione della rete per HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certificati
I certificati consentono di migliorare la sicurezza fornendo autenticazione dell'account, Wi-Fi autenticazione, crittografia VPN e crittografia SSL del contenuto Web. Anche se gli amministratori possono gestire manualmente i certificati nei dispositivi tramite il provisioning dei pacchetti, è consigliabile usare il sistema MDM per gestire tali certificati per l'intero ciclo di vita, dalla registrazione al rinnovo e alla revoca. Il sistema MDM può distribuire automaticamente questi certificati agli archivi certificati dei dispositivi dopo la registrazione del dispositivo (purché il sistema MDM supporti il Simple Certificate Enrollment Protocol (SCEP) o public key cryptography standards #12 (PKCS #12)). MDM può anche eseguire query ed eliminare i certificati client registrati o attivare una nuova richiesta di registrazione prima della scadenza del certificato corrente. 

### <a name="proxy"></a>Proxy
La maggior parte delle reti Intranet aziendali sfrutta un proxy per gestire il traffico interno. Con HoloLens 2 è possibile configurare un server proxy per ethernet e Wi-Fi connessioni. Queste impostazioni non si applicano alle connessioni VPN. Per altre informazioni sulle impostazioni proxy per Windows 10, vedere Provider di servizi di configurazione [NetworkProxy.](/windows/client-management/mdm/networkproxy-csp)

### <a name="vpn"></a>Connessione
Le organizzazioni usano spesso una connessione VPN per controllare l'accesso alle app e alle risorse della Intranet aziendale. HoloLens 2 supporta le connessioni VPN SSL, che richiedono un plug-in scaricabile dal Microsoft Store e sono specifiche del fornitore VPN di propria scelta. 
- Altre informazioni sulla [VPN in HoloLens](hololens-network.md#vpn).
- Per altri dettagli sui profili VPN, vedere il provider di servizi di configurazione [VPNv2.](/windows/client-management/mdm/vpnv2-csp)

### <a name="deploy-and-manage-apps"></a>Distribuire e gestire le app
Con Intune è possibile aggiungere le app ai dispositivi che eseguono Windows Holographic for Business. Una soluzione MDM consente ai decision maker IT e agli amministratori di installare (eseguire il push) privatamente delle app line-of-business o di acquistare app all'interno dello Store per un gruppo di utenti. Esistono molti modi per distribuire le app, ad esempio:
-   [Intune e Portale aziendale]( app-deploy-intune.md)
-   [Microsoft Store per le aziende]( app-deploy-store-business.md)

Altre informazioni sulla gestione delle app tramite Intune.
-   [Aggiungere le app a Intune](/mem/intune/apps/apps-add)
-   [Aggiungere le app di Microsoft Store](/mem/intune/apps/store-apps-windows)
-   [Aggiungere le app create dall'utente](/mem/intune/apps/lob-apps-windows)
- [Assegnare app ai gruppi](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Aggiornamenti software
Intune include una funzionalità denominata anelli di aggiornamento per i dispositivi Windows 10. Questi anelli di aggiornamento includono un gruppo di impostazioni che determinano il modo in cui vengono installati gli aggiornamenti. È possibile ad esempio creare una finestra di manutenzione per installare gli aggiornamenti o scegliere di riavviare dopo l'installazione degli aggiornamenti. Un anello di aggiornamento può essere applicato a più dispositivi che eseguono Windows Holographic for Business.
Altre informazioni su come gestire [gli aggiornamenti HoloLens e](hololens-updates.md) Gestire gli aggiornamenti software tramite [Intune.](/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Configurare la modalità tutto schermo
Grazie alle funzionalità del PC in condivisione o guest disponibili in Intune, è possibile configurare i dispositivi Windows Holographic for Business per l'esecuzione in modalità tutto schermo. Questi dispositivi possono eseguire un'app (modalità tutto schermo per app singola), o più app (modalità tutto schermo per più app). La modalità tutto schermo è un'interfaccia utente che consente di controllare quali identità hanno accesso alle app per impostazione predefinita.
Informazioni su come [configurare il HoloLens come chiosco multimediale]( hololens-kiosk.md)

