---
title: Gestire le app personalizzate per HoloLens
description: Caricamento laterale di app personalizzate in HoloLens. Leggi altre informazioni su come installare e disinstallare le app olografiche.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828861"
---
# Gestire le app personalizzate per HoloLens

HoloLens supporta molte applicazioni esistenti provenienti da Microsoft Store, nonché nuove app create appositamente per HoloLens. Questo articolo è dedicato alle applicazioni olografiche personalizzate.  

Per altre informazioni sulle app dello Store, Vedi [gestire le app con lo Store](holographic-store-apps.md).

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
