---
title: Come installare le app tramite Web Installer
description: Installare app tramite Web Installer per il programma di installazione di app
keywords: gestione app, app, hololens, app Installer, installazione Web
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
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027473"
---
# Installazione di app da una pagina Web

Gli utenti possono installare un'app direttamente da un server Web. In questo modo si usa il programma di installazione dell'app in combinazione con un metodo di distribuzione facile da scaricare e installare. 

> [!IMPORTANT]
> Questa caratteristica è attualmente solo avalible in Windows Insider Build 19041.1366 +. [Altre informazioni su come iscriversi alle build di Windows Insider](hololens-insider.md).

## Come configurarlo:
1.  Verificare che l'app sia configurata correttamente per l'installazione.
1.  Seguire [questa procedura per abilitare questa operazione in una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage). 
1.  Selezionare un metodo di distribuzione del certificato. 
    1.  I [pacchetti di provisioning](hololens-provisioning.md) possono essere applicati ai dispositivi locali.
    1.  MDM può essere usato per [applicare certificati con configurazioni di dispositivi](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
    1.  Usare il [gestore certificati](hololens-insider.md#certificate-manager)per dispositivi. 

## Esperienza utente finale:
1.  L'utente riceve e installa il certificato nel dispositivo usando un metodo precedentemente selezionato. 
1.  L'utente visita l'URL creato dal passaggio precedente.

L'app verrà ora installata nel dispositivo. Per trovare l'app, Apri il **menu Start** e seleziona il pulsante **tutte** le app per trovare la tua app. 

-   Per informazioni sulla risoluzione dei problemi di questo metodo di installazione, vedere [risoluzione di errori di installazione dell'app](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues). 

> [!NOTE]
> L'interfaccia utente durante il processo di aggiornamento non è supportata. Quindi l'opzione ShowPrompt in [Questa pagina](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e le opzioni correlate non sono supportate.
