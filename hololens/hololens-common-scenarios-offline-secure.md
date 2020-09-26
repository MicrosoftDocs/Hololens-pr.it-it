---
title: Scenari comuni-offline Secure HoloLens 2
description: Una distribuzione sicura offline e la distribuzione di app tramite il provisioning.
keywords: HoloLens, gestione, offline, protezione offline
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080502"
---
# Scenari comuni-offline Secure HoloLens 2

## Panoramica
Questa guida fornisce indicazioni per l'applicazione di un pacchetto di provisioning di esempio che bloccherà un HoloLens 2 per l'uso in ambienti sicuri con le restrizioni seguenti:
-   Disabilitare il WiFi.
-   Disabilitare il BlueTooth.
-   Disabilitare i microfoni.
-   Impedisce l'aggiunta o la rimozione di pacchetti di provisioning.
-   Nessun utente può abilitare nessuno dei componenti ristretti sopra.

## Preparare 
Configurazione di Windows 10 PC
1. [Scaricare il file più recente del sistema operativo HoloLens 2](https://aka.ms/hololens2download) direttamente in un PC. 
   1. Il supporto per questa configurazione è incluso nella build 19041,1117 e versioni successive.
1. Scaricare/installare lo strumento ARC (Advanced Recovery Companion) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al PC
1. Scaricare/installare lo strumento più recente di [Windows Configuration designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store al PC.
1. [Scaricare la cartella OfflineSecureHL2_Sample con i file di progetto](https://aka.ms/HoloLensDocs-SecureOfflineSample) per compilare il PPKG.
1. Preparare l' [applicazione offline line of business per la distribuzione di PPKG](app-deploy-provisioning-package.md). 


## Configura
Creare un pacchetto di provisioning della configurazione sicura

1. Avviare lo strumento WCD nel PC.
1. Selezionare **file-> progetto aperto**.
  1. Passare al percorso della cartella OfflineSecureHL2_Sample salvata in precedenza e selezionare: OfflineSecureHL2_Sample.icdproj.xml
1. Il progetto dovrebbe essere aperto ed è ora necessario un elenco delle personalizzazioni disponibili: 

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pacchetto di configurazione aperto in WCD](images/offline-secure-sample-wcd.png)

Configurazioni impostate in questo pacchetto di provisioning:

|     Elemento                                                |     Impostazione                       |     Descrizione                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Account/utenti                                    |     Nome utente locale & password    |     Per questi dispositivi offline, un nome utente e una password singoli dovranno essere impostati e condivisi da tutti gli utenti del dispositivo.          |
|     First Experience/HoloLens/SkipCalibration       |     True                          |     Salta la calibrazione solo durante la configurazione iniziale del dispositivo                                                                             |
|     First Experience/HoloLens/SkipTraining          |     True                          |     Ignora la formazione del dispositivo durante l'installazione del dispositivo iniziale                                                                              |
|     First Experience/HoloLens/WiFi                  |     True                          |     Salta la configurazione Wi-Fi durante l'installazione del dispositivo iniziale                                                                                 |
|     Criteri/connettività/AllowBluetooth consente                |     No                            |     Disabilita il Bluetooth                                                                                                             |
|     Criteri/esperienza/AllowCortana                    |     No                            |     Disattiva Cortana (per eliminare i potenziali problemi in quanto i microfoni sono disabilitati)                                          |
|     Policies/MixedReality/MicrophoneDisabled            |     Sì                           |     Disattiva il microfono                                                                                                            |
|     Criteri/privacy/LetAppsAccessLocation              |     Forza di negazione                    |     Impedisce alle app di provare ad accedere ai dati della posizione (per eliminare i potenziali problemi perché il rilevamento della posizione è disabilitato)    |
|     Criteri/privacy/LetAppsAccessMicrophone            |     Forza di negazione                    |     Impedisce alle app di provare ad accedere ai microfoni (per eliminare i potenziali problemi in quanto i microfoni sono disabilitati)           |
|     Criteri/sicurezza/AllowAddProvisioningPackage       |     No                            |     Impedisce ad altri utenti di aggiungere pacchetti di provisioning che potrebbero tentare di ignorare i criteri bloccati.                         |
|     Criteri/sicurezza/AllowRemoveProvisioningPackage    |     No                            |     Impedisce a chiunque di rimuovere il pacchetto di provisioning bloccato.                                                           |
|     Criteri/sistema/AllowLocation                       |     No                            |     Impedisce al dispositivo di provare a tenere traccia dei dati sulla posizione.                                                                        |
|     Criteri/WiFi/AllowWiFi consente                             |     No                            |     Disabilita la connessione Wi-Fi                                                                                                                 |

4. In impostazioni di Runtime selezionare **account/utenti/nomeutente: Holo/password** 
    - Nota la password e Reimposta, se necessario.
5. Passare a UniversalAppInstall/UserContextApp e [configurare l'app line-of-business](app-deploy-provisioning-package.md) che verrà distribuita in questi dispositivi.

   > [!div class="mx-imgBorder"]
   > ![Screenshot della posizione in cui aggiungere la tua app in WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. Una volta completata la procedura, selezionare il pulsante "Esporta" e seguire tutte le istruzioni fino a quando non viene creato il pacchetto di provisioning.

   > [!div class="mx-imgBorder"]
   > ![Screenshot del pulsante Esporta per il pacchetto in WCD.](images/offline-secure-sample-wcd-export.png)


## Distribuisci
1. Connettere il HL2 al PC Windows 10 tramite cavo USB.
1. Avviare lo strumento ARC e selezionare **HoloLens 2**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. Nella schermata successiva selezionare **Selezione pacchetto manuale**.
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. Passare al file con estensione FFU scaricato in precedenza e selezionare **Apri**.
1. Nella pagina avviso selezionare **continua**.

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. Attendere lo strumento ARC per completare l'installazione del sistema operativo HoloLens 2.
1. Quando il dispositivo completa il backup di installazione e avvio, dal PC passare a Esplora file e copiare il file PPKG salvato in precedenza nella cartella del dispositivo.

   > [!div class="mx-imgBorder"]
   > ![File di PPKG nel PC nella finestra Esplora file.](images/offline-secure-file-explorer.png)

1. Nella HoloLens 2 Premere il tasto seguente per eseguire il pacchetto di provisioning: toccare **volume giù** e pulsante di **accensione** contemporaneamente.
1. Verrà richiesto di applicare il pacchetto di provisioning, selezionare **conferma**
1. Dopo aver completato il pacchetto di provisioning, selezionare **OK**.
1. Viene quindi richiesto di accedere al dispositivo con l'account e la password locali condivisi.

## Gestione
Con questa configurazione, è consigliabile riavviare il processo sopra e reflashare il dispositivo con lo strumento ARC e applicare un nuovo PPKG per apportare gli aggiornamenti al sistema operativo e/o alle applicazioni. 

