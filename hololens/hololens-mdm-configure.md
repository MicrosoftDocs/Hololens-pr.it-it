---
title: Uso di Microsoft Endpoint Manager Intune per la gestione di dispositivi HoloLens
description: Informazioni su come usare MDM per configurare CSP, Policy e gestire i dispositivi di realtà mista HoloLens su scala con Intune.
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
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283957"
---
# Uso di Microsoft Endpoint Manager Intune per la gestione di dispositivi HoloLens

Sono disponibili numerose impostazioni diverse che è possibile gestire tramite MDM. L'uso dei dispositivi Intune può essere raggruppato insieme e le configurazioni possono essere distribuite in questi gruppi di utenti o dispositivi. Le app possono anche essere distribuite e gestite, configurare i dispositivi per la connessione alla rete, nonché configurare gli aggiornamenti in modo che si verifichino al momento desiderato e nell'anello di aggiornamento necessario. 

## Come gestire tramite Intune

### Categorie e gruppi di dispositivi
Usando Intune, puoi creare categorie di dispositivi per aggiungere automaticamente periferiche ai gruppi in base alle categorie create, ad esempio ingegneria, medico, sviluppatori e così via. L'idea è quella di semplificare la gestione dei dispositivi in cui è in uso Windows olografico for business.
Per saperne di più: [categorizzare i dispositivi in gruppi](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### Profili di configurazione dei dispositivi
Intune include le impostazioni e le caratteristiche che è possibile abilitare o disabilitare in dispositivi diversi all'interno dell'organizzazione. Queste impostazioni e funzionalità vengono gestite con i profili. Ad esempio, puoi creare un profilo che consente a Cortana o usa Microsoft Defender Smart Screen nei tuoi dispositivi con Windows olografico for business.
Nei tuoi profili puoi usare OMA-URI per personalizzare alcune impostazioni, creare restrizioni per i dispositivi e configurare una rete privata virtuale (VPN) e Wi-Fi.
Iniziare [a usare i profili di configurazione e la](https://docs.microsoft.com/mem/intune/configuration/device-profiles) [Panoramica del profilo](https://docs.microsoft.com/mem/intune/configuration/device-profile-create).

## Esempi di elementi che possono essere gestiti e configurati

L'uso di MDM per gestire i dispositivi offre una vasta gamma di elementi che possono essere selezionati. 

### Wi-Fi
[Le impostazioni Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) assegnano le impostazioni di rete wireless a utenti e dispositivi. Quando si assegna un profilo di Wi-Fi, gli utenti possono accedere alle Wi-Fi aziendali senza doverlo configurare autonomamente.
Leggi altre informazioni su [come configurare la rete per HoloLens](hololens-commercial-infrastructure.md)

### Certificati
I certificati consentono di migliorare la sicurezza fornendo l'autenticazione dell'account, l'autenticazione Wi-Fi, la crittografia VPN e la crittografia SSL del contenuto Web. Anche se gli amministratori possono gestire i certificati sui dispositivi manualmente tramite il provisioning dei pacchetti, è consigliabile usare il sistema MDM per gestire i certificati durante l'intero ciclo di vita, dall'iscrizione al rinnovo e alla revoca. Il sistema MDM può distribuire automaticamente questi certificati agli archivi certificati dei dispositivi dopo la registrazione del dispositivo (purché il sistema MDM supporti il protocollo SCEP) o gli standard di crittografia a chiave pubblica #12 (PKCS # 12)). MDM può anche eseguire query ed eliminare certificati client registrati o attivare una nuova richiesta di registrazione prima della scadenza del certificato corrente. 

### Proxy
La maggior parte delle reti Intranet aziendali sfrutta un proxy per gestire il traffico interno. Con HoloLens 2 è possibile configurare un server proxy per le connessioni Ethernet e Wi-Fi. Queste impostazioni non si applicano alle connessioni VPN. Per altre informazioni sulle impostazioni proxy per Windows 10, Vedi [CSP di NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

### VPN
Le organizzazioni usano spesso una connessione VPN per controllare l'accesso alle app e alle risorse della Intranet aziendale. HoloLens 2 supporta le connessioni VPN SSL, che richiedono un plug-in scaricabile da Microsoft Store e sono specifiche del fornitore di VPN a scelta. 
- Per saperne di più [su VPN in HoloLens](hololens-network.md#vpn).
- Per altre informazioni sui profili VPN, vedere il [CSP di VPNv2](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

### Distribuire e gestire le app
Usando Intune, puoi aggiungere app ai tuoi dispositivi che usano Windows olografico for business. Una soluzione MDM consente ai responsabili IT e agli amministratori di installare automaticamente le proprie app line-of-business in privato o di acquistare app tramite lo Store per un gruppo di utenti. Esistono diversi modi per distribuire le app, tra cui:
-   [Intune e portale aziendale]( app-deploy-intune.md)
-   [Microsoft Store per le aziende]( app-deploy-store-business.md)

Leggi altre informazioni sulla gestione delle app tramite Intune.
-   [Aggiungere app a Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Aggiungere app di Microsoft Store](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Aggiungere app create](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Assegnare app ai gruppi](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### Aggiornamenti software
Intune include una caratteristica chiamata Update Rings per dispositivi Windows 10. Questi anelli di aggiornamento includono un gruppo di impostazioni che determinano la modalità di installazione degli aggiornamenti. Ad esempio, è possibile creare una finestra di manutenzione per installare gli aggiornamenti oppure scegliere di riavviare dopo l'installazione degli aggiornamenti. Un anello di aggiornamento può essere applicato a più dispositivi con Windows olografico per le aziende.
Leggi altre informazioni su come [gestire gli aggiornamenti di HoloLens](hololens-updates.md) e [gestire gli aggiornamenti software tramite Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

### Configura la modalità tutto schermo
Usando le caratteristiche di PC condivise o guest disponibili in Intune, puoi configurare i dispositivi Windows olografici per le aziende per l'esecuzione come chiosco. Questi dispositivi possono eseguire un'app (modalità Kiosk Single-app) o eseguire più app (modalità Kiosk multi-app). La modalità Kiosk è un'interfaccia utente per controllare le identità che hanno accesso alle app per impostazione predefinita.
Informazioni su come [configurare HoloLens come chiosco]( hololens-kiosk.md)

