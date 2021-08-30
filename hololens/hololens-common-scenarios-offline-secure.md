---
title: Scenari comuni- Sicurezza offline HoloLens 2
description: Informazioni su come configurare uno scenario di distribuzione sicura e di distribuzione di app offline con il provisioning HoloLens dispositivi.
keywords: HoloLens, gestione, offline, offline sicuro
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189121"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Scenari comuni- Sicurezza offline HoloLens 2

## <a name="overview"></a>Panoramica

Questa guida fornisce indicazioni per l'applicazione di un pacchetto di provisioning di esempio che blocca un HoloLens 2 per l'uso in ambienti sicuri con le restrizioni seguenti:

-   Disabilitare il Wi-Fi.
-   Disabilitare BlueTooth.
-   Disabilitare i microfoni.
-   Impedisce l'aggiunta o la rimozione di pacchetti di provisioning.
-   Nessun utente può abilitare uno dei componenti con restrizioni precedenti.

[![Scenario di sicurezza offline. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Preparare

Windows 10 Configurazione del PC
1. [Scaricare la versione HoloLens 2 file del sistema operativo](https://aka.ms/hololens2download) direttamente in un PC. 
   1. Il supporto per questa configurazione è incluso nella build 19041.1117 e successive.
1. Scaricare/installare lo strumento Arc (Advanced Recovery Companion) [dal Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) nel PC
1. Scaricare/installare lo strumento [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) più recente dal Microsoft Store nel PC.
1. [Scaricare la cartella OfflineSecureHL2_Sample con i file di progetto](https://aka.ms/HoloLensDocs-SecureOfflineSample) per compilare il file PPKG.
1. Preparare [l'applicazione line-of-business](app-deploy-provisioning-package.md)offline per la distribuzione PPKG . 


## <a name="configure"></a>Configurazione

Creare un pacchetto di provisioning della configurazione sicura

1. Avviare lo strumento WCD nel PC.
1. Selezionare **File -> Apri progetto**.
  1. Passare al percorso della cartella di OfflineSecureHL2_Sample salvata in precedenza e selezionare: OfflineSecureHL2_Sample.icdproj.xml
1. Il progetto dovrebbe essere aperto e dovrebbe essere ora disponibile un elenco di personalizzazioni disponibili:

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pacchetto di configurazione aperto in WCD.](images/offline-secure-sample-wcd.png)

   Configurazioni impostate in questo pacchetto di provisioning:
   
   |     Elemento                                                |     Impostazione                       |     Descrizione                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Account/Utenti                                    |     Nome utente locale & password    |     Per questi dispositivi offline, un singolo nome utente e una singola password dovranno essere impostati e condivisi da tutti gli utenti del dispositivo.          |
   |     Prima esperienza/HoloLens/SkipCalibration       |     Vero                          |     Ignora la calibrazione solo durante la configurazione iniziale del dispositivo                                                                             |
   |     Prima esperienza/HoloLens/SkipTraining          |     Vero                          |     Ignora il training del dispositivo durante la configurazione iniziale del dispositivo                                                                              |
   |     Prima esperienza/HoloLens/Wi-Fi                  |     Vero                          |     Ignora la Wi-Fi durante la configurazione iniziale del dispositivo                                                                                 |
   |     Policies/Connectivity/AllowBluetooth                |     No                            |     Disabilita Bluetooth                                                                                                             |
   |     Criteri/Esperienza/AllowCortana                    |     No                            |     Disabilita Cortana (per eliminare potenziali problemi perché i microfoni sono disabilitati)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Sì                           |     Disabilita il microfono                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     Forza negazione                    |     Impedisce alle app di provare ad accedere ai dati della posizione (per eliminare potenziali problemi perché il rilevamento della posizione è disabilitato)    |
   |     Policies/Privacy/LetAppsAccessMicrophone            |     Forza negazione                    |     Impedisce alle app di provare ad accedere ai microfoni (per eliminare potenziali problemi perché i microfoni sono disabilitati)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     No                            |     Impedisce a chiunque di aggiungere pacchetti di provisioning che potrebbero tentare di eseguire l'override dei criteri bloccati.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     Impedisce a chiunque di rimuovere questo pacchetto di provisioning bloccato.                                                           |
   |     Policies/System/AllowLocation                       |     No                            |     Impedisce al dispositivo di provare a tenere traccia dei dati sulla posizione.                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     No                            |     Disabilita Wi-Fi                                                                                                                 |

1. In Runtime Impostazioni selezionare **Accounts/Users/UserName: Holo/Password**.

   Prendere nota della password e reimpostarla, se necessario.

1. Passare a UniversalAppInstall/UserContextApp e [configurare l'app LOB](app-deploy-provisioning-package.md) che verrà distribuita in questi dispositivi.

   > [!div class="mx-imgBorder"]
   > ![Screenshot della posizione in cui aggiungere l'app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Al termine, selezionare il pulsante "Esporta" e seguire tutte le richieste fino a quando non viene creato il pacchetto di provisioning.

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pulsante Esporta per questo pacchetto in WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Distribuire

1. Connessione HL2 al PC Windows 10 tramite cavo USB.
1. Avviare lo strumento ARC e selezionare **HoloLens 2**

   ![HoloLens 2 iniziale della reflash pulita.](images/ARC2.png)

1. Nella schermata successiva selezionare **Selezione manuale del pacchetto.**

   ![HoloLens 2 Schermata informazioni ARC.](images/arc_device_info.png)

1. Passare al file con estensione ffu scaricato in precedenza e selezionare **Apri.**
1. Nella pagina Avviso selezionare **Continua.**

   ![HoloLens 2 Schermata di avviso ARC.](images/arc_warning.png)

1. Attendere che lo strumento ARC completi l'installazione HoloLens 2 sistema operativo.
1. Al termine dell'installazione e dell'avvio del dispositivo, dal PC passare a Esplora file e copiare il file PPKG salvato in precedenza nella cartella del dispositivo.

   > [!div class="mx-imgBorder"]
   > ![File PPKG nel PC Esplora file finestra.](images/offline-secure-file-explorer.png)

1. Nel HoloLens 2 premere la casella combinata di pulsanti seguenti per eseguire il pacchetto di provisioning: toccare **volume** in basso e **pulsante** di alimentazione contemporaneamente.
1. Verrà richiesto di applicare il pacchetto di provisioning e selezionare **Conferma**
1. Al termine del pacchetto di provisioning, selezionare **OK.**
1. Verrà quindi richiesto di accedere al dispositivo con l'account locale condiviso e la password.

## <a name="maintain"></a>Effettuare la manutenzione

Con questa configurazione, è consigliabile riavviare il processo precedente e aggiornare il dispositivo con lo strumento ARC e applicare un nuovo PPKG per apportare eventuali aggiornamenti al sistema operativo e/o alle applicazioni.
