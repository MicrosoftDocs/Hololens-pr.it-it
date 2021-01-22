---
title: Scenari comuni - HoloLens 2 protetto offline
description: Informazioni su come configurare uno scenario di distribuzione sicura offline e di distribuzione di app con il provisioning per i dispositivi HoloLens.
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
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283417"
---
# Scenari comuni - HoloLens 2 protetto offline

## Panoramica

Questa guida fornisce indicazioni per l'applicazione di un pacchetto di provisioning di esempio che blocchi holoLens 2 per l'uso in ambienti sicuri con le restrizioni seguenti:
-   Disabilitare il WiFi.
-   Disabilita BlueTooth.
-   Disabilitare i microfoni.
-   Impedisce l'aggiunta o la rimozione di pacchetti di provisioning.
-   Nessun utente può abilitare uno dei componenti con restrizioni precedenti.

## Preparazione

Configurazione PC Windows 10
1. Scarica il file del sistema [operativo HoloLens 2 più](https://aka.ms/hololens2download) recente direttamente in un PC. 
   1. Il supporto per questa configurazione è incluso nella build 19041.1117 e successive.
1. Scaricare/installare lo strumento Advanced Recovery Companion(ARC) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al PC
1. Scarica/installa l'ultimo strumento Progettazione configurazione di [Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store al PC.
1. [Scarica la OfflineSecureHL2_Sample con i file di progetto](https://aka.ms/HoloLensDocs-SecureOfflineSample) per compilare il PPKG.
1. Preparare [l'applicazione line-of-business offline per la distribuzione PPKG.](app-deploy-provisioning-package.md) 


## Configura

Creare un pacchetto di provisioning di configurazione sicura

1. Avvia lo strumento WCD nel PC.
1. Selezionare **File -> Apri progetto.**
  1. Passare al percorso della cartella di OfflineSecureHL2_Sample salvata in precedenza e selezionare: OfflineSecureHL2_Sample.icdproj.xml
1. Il progetto dovrebbe aprirsi e ora dovrebbe essere disponibile un elenco delle personalizzazioni disponibili: 

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pacchetto di configurazione aperto in WCD](images/offline-secure-sample-wcd.png)

Configurazioni impostate in questo pacchetto di provisioning:

|     Elemento                                                |     Impostazione                       |     Descrizione                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Account/Utenti                                    |     Nome utente locale & password    |     Per questi dispositivi offline, un singolo nome utente e una singola password dovranno essere impostati e condivisi da tutti gli utenti del dispositivo.          |
|     First Experience / HoloLens / SkipCalibration       |     True                          |     Ignora la calibrazione solo durante la configurazione iniziale del dispositivo                                                                             |
|     First Experience / HoloLens /SkipTraining          |     True                          |     Ignora la formazione dei dispositivi durante la configurazione iniziale del dispositivo                                                                              |
|     First Experience / HoloLens / WiFi                  |     True                          |     Ignora la Wi-Fi configurazione del dispositivo durante la configurazione iniziale del dispositivo                                                                                 |
|     Criteri/Connettività/AllowBluetooth                |     No                            |     Disabilita Bluetooth                                                                                                             |
|     Criteri/Esperienza/AllowCortana                    |     No                            |     Disabilita Cortana (per eliminare potenziali problemi perché i microfoni sono disabilitati)                                          |
|     Criteri/MixedReality/MicrophoneDisabled            |     Sì                           |     Disabilita il microfono                                                                                                            |
|     Criteri/Privacy/LetAppsAccessLocation              |     Forza negazione                    |     Impedisce alle app di tentare di accedere ai dati sulla posizione (per eliminare potenziali problemi poiché il rilevamento della posizione è disabilitato)    |
|     Criteri/Privacy/LetAppsAccessMicrophone            |     Forza negazione                    |     Impedisce alle app di accedere ai microfoni (per eliminare potenziali problemi perché i microfoni sono disabilitati)           |
|     Criteri/Sicurezza/AllowAddProvisioningPackage       |     No                            |     Impedisce a chiunque di aggiungere pacchetti di provisioning che potrebbero tentare di ignorare i criteri bloccati.                         |
|     Criteri/Sicurezza/AllowRemoveProvisioningPackage    |     No                            |     Impedisce a chiunque di rimuovere questo pacchetto di provisioning bloccato.                                                           |
|     Criteri/Sistema/AllowLocation                       |     No                            |     Impedisce al dispositivo di provare a tenere traccia dei dati sulla posizione.                                                                        |
|     Criteri/WiFi/AllowWiFi                             |     No                            |     Disabilita Wi-Fi                                                                                                                 |

4. In Impostazioni di runtime, selezionare **Account / Utenti / UserName: Holo / Password** 
    - Prendere nota della password e reimpostarla, se lo si desidera.
5. Passa a UniversalAppInstall/UserContextApp e [configura l'app LOB](app-deploy-provisioning-package.md) che distribuirai in questi dispositivi.

   > [!div class="mx-imgBorder"]
   > ![Screenshot della posizione in cui aggiungere l'app in WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. Al termine, seleziona il pulsante "Esporta" e segui tutte le istruzioni finché non viene creato il pacchetto di provisioning.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)


## Distribuisci

1. Connetti HL2 al PC Windows 10 tramite cavo USB.
1. Avviare lo strumento ARC e selezionare **HoloLens 2**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. Nella schermata successiva seleziona Selezione manuale **del pacchetto.**
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. Passa al file ffu scaricato in precedenza e seleziona **Apri.**
1. Nella pagina Avviso selezionare **Continua.**

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. Attendere che lo strumento ARC completi l'installazione del sistema operativo HoloLens 2.
1. Una volta completata l'installazione e avviato il backup, dal PC passa a Esplora file e copia il file PPKG salvato in precedenza nella cartella del dispositivo.

   > [!div class="mx-imgBorder"]
   > ![File PPKG nel PC nella finestra Esplora file.](images/offline-secure-file-explorer.png)

1. In HoloLens 2 premi la combinazione di pulsanti seguenti per eseguire il pacchetto di provisioning: tocca **Volume giù** e **Il** pulsante di alimentazione contemporaneamente.
1. Verrà richiesto di applicare il pacchetto di provisioning, selezionare **Conferma**
1. Al termine del pacchetto di provisioning, selezionare **OK.**
1. Dovrebbe quindi essere richiesto di accedere al dispositivo con l'account locale e la password condivisi.

## Gestione

Con questa configurazione, è consigliabile riavviare il processo precedente e ripartire il dispositivo con lo strumento ARC e applicare un nuovo PPKG per apportare eventuali aggiornamenti al sistema operativo e/o alle applicazioni. 

