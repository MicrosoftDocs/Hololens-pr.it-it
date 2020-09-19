---
title: Come caricare e installare le app tramite il programma di installazione di HoloLens 2 app
description: Caricare le app e installarle tramite interfaccia utente
keywords: gestione app, app, hololens, app Installer
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027474"
---
# Installare app in HoloLens 2 tramite il programma di installazione di app

Ora gli utenti possono installare le app tramite bundle appx, senza la necessità di abilitare la modalità sviluppatore o usare Device Portal. Questa esperienza è semplice per l'installazione di app su dispositivi locali o per la condivisione di un'app con un altro utente che non ha familiarità con altri metodi di installazione dell'app in HoloLens. 

> [!IMPORTANT]
> Questa caratteristica è attualmente solo avalible in Windows Insider Build 19041.1377 +. [Altre informazioni su come iscriversi alle build di Windows Insider](hololens-insider.md).

> [!NOTE]
> La configurazione della soluzione della tua app deve essere **Master** o **Release** perché il programma di installazione dell'app userà le dipendenze dallo Store. Vedere altre informazioni sulla [creazione di pacchetti di app](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

1.  Verificare che il dispositivo HoloLens 2 sia acceso e che sia stato effettuato l'accesso.
1.  Nel PC passare all'app personalizzata e copiare YourApp. appxbundle in yourdevicename\Internal Storage\Downloads. 
    Una volta completata la copia del file, è possibile scollegare il dispositivo e completare l'installazione in un secondo momento.
1.  Dal dispositivo HoloLens 2 aprire il **menu Start**, selezionare **tutte le app** e avviare l'app **Esplora file** .
1.  Passare alla cartella Downloads. Potrebbe essere necessario nel pannello sinistro dell'app selezionare prima **questo dispositivo** , quindi passare a download.
1.  Selezionare il file YourApp. appxbundle. 
1.  Verrà avviato il programma di installazione dell'app. Selezionare il pulsante **Installa** per installare la tua app. 

L'app installata verrà avviata automaticamente dopo il completamento dell'installazione. 

![Installazione di esempi di MRTK tramite il programma di installazione dell'app](images/hololens-app-installer-picture.jpg)

Se l'app non è stata installata, controllare quanto segue:
-   La tua app è una build master o release.
-   Si è [connessi a Internet](hololens-network.md).
-   Gli [endpoint per Microsoft Store](hololens-offline.md) sono configurati correttamente.  
