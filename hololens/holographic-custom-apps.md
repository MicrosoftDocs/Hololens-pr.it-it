---
title: Gestire app personalizzate per HoloLens (prima generazione)
description: Scopri come installare, disinstallare e caricare tramite side load app olografiche personalizzate nei dispositivi HoloLens tramite Device Portal e Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, sideload, sideload, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296989"
---
# Gestire app personalizzate per HoloLens (prima generazione)

HoloLens supporta molte attuali applicazioni disponibili su Microsoft Store, nonché nuove app create specificamente per HoloLens. Questo articolo si concentra sulle applicazioni olografiche personalizzate.  

Per altre informazioni sulle app dello Store, vedi [Gestire le app con lo Store.](holographic-store-apps.md)

> [!IMPORTANT]
> Le informazioni seguenti sono state create per HoloLens (prima generazione), chiamata anche HoloLens Developer Edition al momento. Di conseguenza, il sideload delle app tramite portale di dispositivi e l'installazione di app tramite Visual Studio erano all'ora comune. Per le distribuzioni aziendali non è consigliabile abilitare la modalità sviluppatore, che entrambi i metodi usano. Se sei interessato a un metodo di distribuzione delle app sicuro, leggi la nostra [panoramica sulla gestione delle app.](app-deploy-overview.md)
>
> Se stai cercando uno dei due metodi di installazione delle app per i dispositivi HoloLens 2, fai riferimento a:
> - [Device Portal: installazione di un'app](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Uso di Visual Studio per distribuire ed eseguire il debug delle app](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## Installare app personalizzate

Puoi installare le tue applicazioni in HoloLens usando Device Portal o distribuendo le app da Visual Studio.

### Installazione di un pacchetto dell'applicazione con Device Portal

1. Stabilire una connessione da [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) a HoloLens di destinazione.

1. Nel riquadro di spostamento sinistro passare alla **pagina** App.

1. In **Pacchetto dell'app** passare al file con estensione appx associato all'applicazione.

   > [!IMPORTANT]
   > Assicurati di fare riferimento a qualsiasi file di dipendenza e certificato associato.

1. Selezionare **Vai.**

   > [!div class="mx-imgBorder"]
   > ![Installare il modulo dell'app in Windows Device Portal in Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Distribuzione da Microsoft Visual Studio 2015

1. Apri la soluzione Visual Studio della tua app (file con estensione sln).

1. Aprire le proprietà del **progetto.**

1. Selezionare la configurazione di compilazione seguente: **Master/x86/Computer remoto.**

1. Quando si seleziona **Computer remoto:**
   - Assicurati che l'indirizzo punti all'Wi-Fi IP del dispositivo HoloLens.
   - Impostare **l'autenticazione su Universale (protocollo non crittografato).**
   
1. Compilare la soluzione.

1. Per distribuire l'app dal PC di sviluppo a HoloLens, seleziona **Computer remoto.** Se hai già una build esistente in HoloLens, seleziona **Sì** per installare questa versione più recente.  

   ![Distribuzione di computer remoti per le app in Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. L'applicazione verrà installata e avviata automaticamente in HoloLens.

Dopo aver installato un'app, la troverai **nell'elenco Tutte** le app (**Avvia**tutte  >  **le app**).
