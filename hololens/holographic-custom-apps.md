---
title: Gestire app personalizzate per HoloLens (prima generazione)
description: Informazioni su come installare, disinstallare e caricare sul lato app olografiche personalizzate nei dispositivi HoloLens usando i Portale di dispositivi e Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side load, store, uwp, app, install
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032504"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Gestire app personalizzate per HoloLens (prima generazione)

HoloLens supporta molte applicazioni esistenti dal Microsoft Store, nonché nuove app create appositamente per HoloLens. Questo articolo è in particolare sulle applicazioni olografiche personalizzate.  

Per altre informazioni sulle app dello Store, vedere [Gestire le app con lo Store.](holographic-store-apps.md)

> [!IMPORTANT]
> Le informazioni seguenti sono state create per il HoloLens (prima generazione), denominata anche HoloLens Developer Edition al momento. Di conseguenza, il sideload delle app tramite il portale dei dispositivi e l'installazione di app Visual Studio erano all'uso comune. Per le distribuzioni aziendali non è consigliabile abilitare la modalità sviluppatore, che viene utilizzata da entrambi questi metodi. Se si è interessati a un metodo di distribuzione di app sicuro, vedere Gestione [app: Panoramica](app-deploy-overview.md).
>
> Se si sta cercando uno dei metodi di installazione delle app per HoloLens 2 dispositivi, vedere:
>
> - [Portale di dispositivi: Installazione di un'app](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Uso Visual Studio per distribuire ed eseguire il debug di app](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Installare app personalizzate

È possibile installare le proprie applicazioni in HoloLens usando il Portale di dispositivi o distribuendo le app da Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Installazione di un pacchetto dell'applicazione con Portale di dispositivi

1. Stabilire una connessione dal [Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal) alla destinazione HoloLens.

1. Nel riquadro di spostamento a sinistra passare alla **pagina** App.

1. In **Pacchetto app** passare al file con estensione appx associato all'applicazione.

   > [!IMPORTANT]
   > Assicurarsi di fare riferimento a eventuali file di dipendenza e di certificato associati.

1. Selezionare **Vai**.

   > [!div class="mx-imgBorder"]
   > ![Installare il modulo dell'app Windows Portale di dispositivi in Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Distribuzione da Microsoft Visual Studio 2015

1. Aprire la soluzione di Visual Studio dell'app (file con estensione sln).

1. Aprire proprietà del **progetto**.

1. Selezionare la configurazione di compilazione seguente: **Master/x86/Computer remoto**.

1. Quando si seleziona **Computer remoto**:
   - Assicurarsi che l'indirizzo punti all'Wi-Fi IP del HoloLens.
   - Impostare **l'autenticazione su Universal (Unencrypted Protocol)**.
   
1. Compilare la soluzione.

1. Per distribuire l'app dal PC di sviluppo HoloLens, selezionare **Computer remoto**. Se è già presente una build nel HoloLens, selezionare **Sì** per installare questa versione più recente.  

   ![Distribuzione di computer remoti per le app da Microsoft HoloLens in Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. L'applicazione verrà installata e avviata automaticamente nel HoloLens.

Dopo aver installato un'app, è possibile trovarla nell'elenco **Tutte** le app (**Avvia**  >  **tutte le app**).
