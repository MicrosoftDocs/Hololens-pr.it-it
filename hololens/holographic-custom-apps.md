---
title: Gestire app personalizzate per HoloLens (prima generazione)
description: Informazioni su come installare, disinstallare e eseguire il side load di app olografiche personalizzate nei dispositivi HoloLens usando il Portale di dispositivi e Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, sideload, store, uwp, app, install
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428523"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Gestire app personalizzate per HoloLens (prima generazione)

HoloLens supporta molte applicazioni esistenti dal Microsoft Store, nonché nuove app create in modo specifico per HoloLens. Questo articolo è in particolare sulle applicazioni olografiche personalizzate.  

Per altre informazioni sulle app dello Store, vedere [Gestire le app con lo Store.](holographic-store-apps.md)

> [!IMPORTANT]
> Le informazioni seguenti sono state create per la HoloLens (prima generazione), denominata anche HoloLens Developer Edition al momento. Di conseguenza, il sideload delle app tramite il portale di dispositivi e l'installazione di app tramite Visual Studio erano comuni. Per le distribuzioni aziendali non è consigliabile abilitare la modalità sviluppatore, che viene utilizzata da entrambi questi metodi. Se si è interessati a un metodo di distribuzione dell'app sicuro, vedere Gestione [delle app: Panoramica.](app-deploy-overview.md)
>
> Se si sta cercando uno dei due metodi di installazione delle app per gli HoloLens 2, fare riferimento a:
>
> - [Portale di dispositivi: Installazione di un'app](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Uso di Visual Studio per distribuire ed eseguire il debug di app](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Installare app personalizzate

È possibile installare le proprie applicazioni HoloLens usando il Portale di dispositivi o distribuendo le app da Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Installazione di un pacchetto dell'applicazione con il Portale di dispositivi

1. Stabilire una connessione dal [Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal) al HoloLens di HoloLens.

1. Nel riquadro di spostamento a sinistra passare alla **pagina** App.

1. In **Pacchetto dell'app** passare al file con estensione appx associato all'applicazione.

   > [!IMPORTANT]
   > Assicurarsi di fare riferimento a eventuali dipendenze e file di certificato associati.

1. Selezionare **Vai**.

   > [!div class="mx-imgBorder"]
   > ![Installare il modulo dell'app Windows Portale di dispositivi in Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Distribuzione da Microsoft Visual Studio 2015

1. Aprire la soluzione di Visual Studio dell'app (file con estensione sln).

1. Aprire proprietà **del progetto.**

1. Selezionare la configurazione di compilazione seguente: **Master/x86/Computer remoto**.

1. Quando si seleziona **Computer remoto:**
   - Assicurarsi che l'indirizzo punti all'Wi-Fi IP del HoloLens.
   - Impostare **l'autenticazione su Universale (protocollo non crittografato).**
   
1. Compilare la soluzione.

1. Per distribuire l'app dal PC di sviluppo al HoloLens, selezionare **Computer remoto.** Se si dispone già di una build esistente nel HoloLens, selezionare **Sì** per installare questa versione più recente.  

   ![Distribuzione di computer remoti per le app Microsoft HoloLens in Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. L'applicazione verrà installata e avviata automaticamente nel HoloLens.

Dopo aver installato un'app, è possibile trovarla nell'elenco Tutte le **app** (**Avvia tutte** le  >  **app**).
