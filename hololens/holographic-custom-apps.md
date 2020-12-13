---
title: Gestire le app personalizzate per HoloLens
description: Caricamento laterale di app personalizzate in HoloLens. Leggi altre informazioni su come installare e disinstallare le app olografiche.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, trasferire localmente, carico laterale, carico laterale, Store, UWP, app, install
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218633"
---
# Gestire le app personalizzate per HoloLens

HoloLens supporta molte attuali applicazioni disponibili su Microsoft Store, nonché nuove app create specificamente per HoloLens. Questo articolo è dedicato alle applicazioni olografiche personalizzate.  

Per altre informazioni sulle app dello Store, Vedi [gestire le app con lo Store](holographic-store-apps.md).

> [!IMPORTANT]
> Le informazioni seguenti sono state create per HoloLens (1a generazione), detta anche HoloLens Developer Edition in quel momento. In questo modo, le app sideload tramite Device Portal e l'installazione di app tramite Visual Studio erano comuni. Per le distribuzioni aziendali, non è consigliabile abilitare la modalità sviluppatore, che usano entrambi i metodi. Se si è interessati a un metodo di distribuzione delle app sicure, vedere la [sezione gestione delle app: Panoramica](app-deploy-overview.md).
>
> Se stai cercando un metodo per gli sviluppatori per l'installazione di app per dispositivi HoloLens 2, consulta:
> - [Device Portal: installare un'app](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Uso di Visual Studio per la distribuzione e il debug delle app](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## Installare app personalizzate

Puoi installare le tue applicazioni in HoloLens usando il portale dispositivi o distribuendo le app da Visual Studio.

### Installazione di un pacchetto di applicazione con Device Portal

1. Stabilire una connessione da [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) alla HoloLens di destinazione.
1. Nella barra di spostamento sinistra passare alla pagina **app** .
1. In **pacchetto dell'app** individuare il file con estensione appx associato all'applicazione.
   > [!IMPORTANT]
   > Assicurarsi di fare riferimento a qualsiasi file di dipendenza e certificato associato.

1. Selezionare **Vai**.
   ![Modulo di installazione dell'app in Windows Device Portal in Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Distribuzione da Microsoft Visual Studio 2015

1. Aprire la soluzione Visual Studio (file con estensione sln) dell'app.
1. Aprire le **Proprietà**del progetto.
1. Selezionare la configurazione di compilazione seguente: **computer master/x86/Remote**.
1. Quando si seleziona **computer remoto**:
   - Verificare che l'indirizzo indichi l'indirizzo IP Wi-Fi del proprio HoloLens.
   - Impostare l'autenticazione su **universale (protocollo non crittografato)**.
1. Creare la soluzione.
1. Per distribuire l'app dal PC di sviluppo alla HoloLens, selezionare **computer remoto**. Se si dispone già di una build esistente in HoloLens, selezionare **Sì** per installare la versione più recente.  

   ![Distribuzione di computer remoti per le app in Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
1. L'applicazione verrà installata e avviata automaticamente in HoloLens.

Dopo aver installato un'app, la troverai nell'elenco **tutte** le app (**Avvia**  >  **tutte le app**).
