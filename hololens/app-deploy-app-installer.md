---
title: Come caricare e installare le app tramite il programma di installazione di HoloLens 2 app
description: Caricare le app e installarle tramite interfaccia utente
keywords: gestione app, app, hololens, app Installer
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eba1fd00215ef197f9e32949e958bdbded089d6d
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162897"
---
# Installare app in HoloLens 2 tramite il programma di installazione di app


Spediremo la funzionalità di installazione dell'app subito dopo l'aggiornamento di Windows olografico, versione 20H2. Aggiungiamo **una nuova funzionalità (Installer delle app) per consentire l'installazione delle applicazioni in modo più trasparente** nei dispositivi HoloLens 2. La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti**. Per evitare interruzioni alle aziende, il programma di installazione **delle app non sarà disponibile per i dispositivi gestiti** in questo momento.  

> [!IMPORTANT]
> Questa funzionalità è attualmente disponibile solo nelle build di Windows Insider. [Altre informazioni su come iscriversi alle build di Windows Insider](hololens-insider.md).

In Windows Insider Release aggiungiamo **una nuova funzionalità (programma di installazione delle app) per consentire l'installazione di applicazioni più agevolmente** nei dispositivi HoloLens 2. La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti**. Per evitare interruzioni alle aziende, il programma di installazione **delle app non sarà disponibile per i dispositivi gestiti** in questo momento.  

Un dispositivo viene considerato "gestito **" Se una delle opzioni** seguenti è vera:
- MDM [registrato](hololens-enroll-mdm.md)
- Configurato con il [pacchetto di provisioning](hololens-provisioning.md)
- L' [identità](hololens-identity.md) dell'utente è AAD

Ora è possibile installare le app senza dover abilitare la modalità sviluppatore o usando Device Portal.  È sufficiente scaricare (tramite USB o Edge) il bundle appx nel dispositivo e passare al bundle appx in Esplora file per richiedere di avviare l'installazione.  In alternativa, [avviare un'installazione da una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Proprio come le app installate da Microsoft Store o trasferire localmente usando la funzionalità di distribuzione dell'app LOB di MDM, le app devono essere firmate digitalmente con lo [strumento Sign](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e il [certificato usato per firmare deve essere considerato attendibile](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) dal dispositivo HoloLens prima che l'app possa essere distribuita.   

## Requisiti

### Per i dispositivi: 
Questo è attualmente avalible in [Windows Insider Builds](hololens-insider.md) for HoloLens 2 Devices. Assicurati che i dispositivi che usano questo metodo vengano [aggiornati](hololens-update-hololens.md). 

### Per le tue app: 
La configurazione della soluzione della tua app deve essere **Master** o **Release** perché il programma di installazione dell'app userà le dipendenze dallo Store. Vedere altre informazioni sulla [creazione di pacchetti di app](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Le app installate tramite questo metodo devono essere firmate digitalmente. È necessario usare un certificato per firmare l'app. Puoi ottenere un certificato dall' [elenco CA attendibile di MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in questo caso non dovrai eseguire altre azioni. In alternativa, è possibile firmare il proprio certificato, ma il certificato deve essere inserito nel dispositivo. 
- Come firmare le app [con lo strumento Sign.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opzioni certificato:** 
- [Elenco CA attendibile MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Selezionare un metodo di distribuzione del certificato.** 
- I [pacchetti di provisioning](hololens-provisioning.md) possono essere applicati ai dispositivi locali.
- MDM può essere usato per [applicare certificati con configurazioni di dispositivi](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Usare il [gestore certificati](certificate-manager.md)per dispositivi. 

## Metodo di installazione

1.  Verificare che il dispositivo non sia considerato gestito.
1.  Verificare che il dispositivo HoloLens 2 sia acceso e che sia stato effettuato l'accesso.
1.  Nel PC passare all'app personalizzata e copiare YourApp. appxbundle in yourdevicename\Internal Storage\Downloads. 
    Una volta completata la copia del file, è possibile scollegare il dispositivo e completare l'installazione in un secondo momento.
1.  Dal dispositivo HoloLens 2 aprire il **menu Start**, selezionare **tutte le app** e avviare l'app **Esplora file** .
1.  Passare alla cartella Downloads. Potrebbe essere necessario nel pannello sinistro dell'app selezionare prima **questo dispositivo** , quindi passare a download.
1.  Selezionare il file YourApp. appxbundle. 
1.  Verrà avviato il programma di installazione dell'app. Selezionare il pulsante **Installa** per installare la tua app. 

L'app installata verrà avviata automaticamente dopo il completamento dell'installazione. 

![Installazione di esempi di MRTK tramite il programma di installazione dell'app](images/hololens-app-installer-picture.jpg)

### Risoluzione dei problemi di installazione
Se l'app non è stata installata, controllare quanto segue:
-   La tua app è una build master o release.
- Il dispositivo viene aggiornato a una build in cui è disponibile questa funzionalità. 
-   Si è [connessi a Internet](hololens-network.md).
-   Gli [endpoint per Microsoft Store](hololens-offline.md) sono configurati correttamente.  

## Web Installer

Gli utenti possono installare un'app direttamente da un server Web. In questo modo si usa il programma di installazione dell'app in combinazione con un metodo di distribuzione facile da scaricare e installare. 

### Come configurare l'installazione Web:
1.  Verificare che l'app sia configurata correttamente per l'installazione.
1.  Seguire [questa procedura per abilitare questa operazione in una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage). 

### Esperienza utente finale:
1. L'utente riceve e installa il certificato nel dispositivo usando un metodo precedentemente selezionato. 
1. L'utente visita l'URL creato dal passaggio precedente.

L'app verrà ora installata nel dispositivo. Per trovare l'app, Apri il **menu Start** e seleziona il pulsante **tutte** le app per trovare la tua app. 

-   Per informazioni sulla risoluzione dei problemi di questo metodo di installazione, vedere [risoluzione di errori di installazione dell'app](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues). 

> [!NOTE]
> L'interfaccia utente durante il processo di aggiornamento non è supportata. Quindi l'opzione ShowPrompt in [Questa pagina](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e le opzioni correlate non sono supportate.

## App di esempio

Se si vuole provare questa soluzione con alcune app di esempio, vedere alcuni esempi disponibili:
- [Hub esempi di MRTK](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Superfici](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [App di esempio UWP che possono essere usate per i test](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
