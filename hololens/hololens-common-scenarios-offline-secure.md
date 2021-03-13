---
title: 'Scenari comuni: protezione offline di HoloLens 2'
description: Scopri come configurare uno scenario di distribuzione sicura e di distribuzione delle app offline con provisioning per i dispositivi HoloLens.
keywords: HoloLens, gestione, offline, offline secure
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407586"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Scenari comuni: protezione offline di HoloLens 2

## <a name="overview"></a>Panoramica

Questa guida fornisce indicazioni per l'applicazione di un pacchetto di provisioning di esempio che blocchi un HoloLens 2 per l'uso in ambienti sicuri con le restrizioni seguenti:

-   Disabilita WiFi.
-   Disabilitare BlueTooth.
-   Disabilita microfoni.
-   Impedisce l'aggiunta o la rimozione di pacchetti di provisioning.
-   Nessun utente può abilitare uno dei componenti con restrizioni precedenti.

## <a name="prepare"></a>Preparazione

Configurazione PC Windows 10
1. [Scarica il file del sistema operativo HoloLens 2 più](https://aka.ms/hololens2download) recente direttamente in un PC. 
   1. Il supporto per questa configurazione è incluso nella Build 19041.1117 e successive.
1. Scaricare/installare lo strumento Advanced Recovery Companion(ARC) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al PC
1. Scarica/installa lo strumento [WCD (Windows Configuration Designer)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) più recente da Microsoft Store al PC.
1. [Scarica la OfflineSecureHL2_Sample file di progetto per](https://aka.ms/HoloLensDocs-SecureOfflineSample) compilare PPKG.
1. Preparare [l'applicazione Line of Business offline per la distribuzione di PPKG.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Configura

Creare un pacchetto di provisioning della configurazione sicura

1. Avvia lo strumento WCD nel PC.
1. Selezionare **File -> Apri progetto**.
  1. Passare al percorso della cartella di OfflineSecureHL2_Sample salvata in precedenza e selezionare: OfflineSecureHL2_Sample.icdproj.xml
1. Il progetto dovrebbe aprirsi e ora dovrebbe essere disponibile un elenco di personalizzazioni disponibili:

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pacchetto di configurazione aperto in WCD](images/offline-secure-sample-wcd.png)

   Configurazioni impostate in questo pacchetto di provisioning:
   
   |     Elemento                                                |     Impostazione                       |     Descrizione                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Account /Utenti                                    |     Nome utente locale & password    |     Per questi dispositivi offline, un singolo nome utente e password dovranno essere impostati e condivisi da tutti gli utenti del dispositivo.          |
   |     First Experience / HoloLens / SkipCalibration       |     True                          |     Ignora la calibrazione solo durante la configurazione iniziale del dispositivo                                                                             |
   |     First Experience / HoloLens / SkipTraining          |     True                          |     Ignora la formazione dei dispositivi durante la configurazione iniziale del dispositivo                                                                              |
   |     First Experience / HoloLens / WiFi                  |     True                          |     Ignora la Wi-Fi configurazione durante la configurazione iniziale del dispositivo                                                                                 |
   |     Criteri/Connettività/AllowBluetooth                |     No                            |     Disabilita Bluetooth                                                                                                             |
   |     Criteri/Esperienza/AllowCortana                    |     No                            |     Disabilita Cortana (per eliminare potenziali problemi perché i microfoni sono disabilitati)                                          |
   |     Criteri/MixedReality/MicrophoneDisabled            |     Sì                           |     Disabilita microfono                                                                                                            |
   |     Criteri/Privacy/LetAppsAccessLocation              |     Forza negazione                    |     Impedisce alle app di tentare di accedere ai dati sulla posizione (per eliminare potenziali problemi poiché il rilevamento della posizione è disabilitato)    |
   |     Criteri/Privacy/LetAppsAccessMicrophone            |     Forza negazione                    |     Impedisce alle app di tentare di accedere ai microfoni (per eliminare potenziali problemi poiché i microfoni sono disabilitati)           |
   |     Criteri/Sicurezza/AllowAddProvisioningPackage       |     No                            |     Impedisce a chiunque di aggiungere pacchetti di provisioning che potrebbero tentare di ignorare i criteri bloccati.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     Impedisce a chiunque di rimuovere questo pacchetto di provisioning bloccato.                                                           |
   |     Criteri/Sistema/AllowLocation                       |     No                            |     Impedisce al dispositivo di provare a tenere traccia dei dati sulla posizione.                                                                        |
   |     Criteri/WiFi/AllowWiFi                             |     No                            |     Disabilita Wi-Fi                                                                                                                 |

1. In Impostazioni di runtime, selezionare **Account / Utenti / UserName: Holo / Password**.

   Annotare la password e reimpostarla, se lo si desidera.

1. Passa a UniversalAppInstall / UserContextApp e [configura l'app LOB](app-deploy-provisioning-package.md) che verrà distribuita in questi dispositivi.

   > [!div class="mx-imgBorder"]
   > ![Screenshot della posizione in cui aggiungere l'app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Al termine, seleziona il pulsante "Esporta" e segui tutte le istruzioni finché non viene creato il pacchetto di provisioning.

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pulsante Esporta per questo pacchetto in WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Distribuisci

1. Connetti HL2 al PC Windows 10 tramite cavo USB.
1. Avviare lo strumento ARC e selezionare **HoloLens 2**

   ![Schermata iniziale di riconfigurazione di HoloLens 2](images/ARC2.png)

1. Nella schermata successiva seleziona **Selezione manuale del pacchetto.**

   ![Schermata info HoloLens 2 ARC](images/arc_device_info.png)

1. Passare al file ffu scaricato in precedenza e selezionare **Apri**.
1. Nella pagina Avviso selezionare **Continua.**

   ![Schermata di avviso HoloLens 2 ARC](images/arc_warning.png)

1. Attendere che lo strumento ARC completi l'installazione del sistema operativo HoloLens 2.
1. Una volta completata l'installazione e avviato il backup, dal PC passare a Esplora file e copiare il file PPKG salvato in precedenza nella cartella del dispositivo.

   > [!div class="mx-imgBorder"]
   > ![File PPKG nel PC nella finestra Esplora file.](images/offline-secure-file-explorer.png)

1. In HoloLens 2 premi la combinazione di pulsanti seguente per eseguire il pacchetto di provisioning: tocca **Volume giù** e **Pulsante** di alimentazione contemporaneamente.
1. Verrà richiesto di applicare il pacchetto di provisioning, selezionare **Conferma**
1. Al termine del pacchetto di provisioning, seleziona **OK.**
1. Verrà quindi richiesto di accedere al dispositivo con l'account locale condiviso e la password.

## <a name="maintain"></a>Gestione

Con questa configurazione, è consigliabile riavviare il processo precedente e ripartire il dispositivo con lo strumento ARC e applicare un nuovo PPKG per apportare eventuali aggiornamenti al sistema operativo e/o alle applicazioni.
