---
title: Come eseguire il side load e installare app tramite il programma di installazione app di HoloLens 2
description: Scopri come installare e risolvere i problemi delle app con il programma di installazione app e caricare e installare le app tramite l'interfaccia utente.
keywords: gestione delle app, app, hololens, programma di installazione app
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
ms.openlocfilehash: 89f48fab236fdaf58fb0bf8b29e5a3aacb3bdee3
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283737"
---
# Installare app in HoloLens 2 tramite il programma di installazione app

> [!NOTE]
> Questa funzionalità è stata resa disponibile in [Windows Holographic, versione 20H2 - Aggiornamento di dicembre 2020.](hololens-release-notes.md) Assicurati che il dispositivo [sia aggiornato per](hololens-update-hololens.md) usare questa funzionalità.

Abbiamo aggiunto **una nuova funzionalità (programma** di installazione app) per consentirti di installare le applicazioni in modo più semplice nei dispositivi HoloLens 2. La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti.** Per evitare interruzioni per le aziende, il programma di installazione app non sarà disponibile **per i dispositivi** gestiti in questo momento.  

Un dispositivo viene considerato "gestito" se **si** verifica una delle condizioni seguenti:

- MDM [registrato](hololens-enroll-mdm.md)
- Configurato con il [pacchetto di provisioning](hololens-provisioning.md)
- [L'identità utente](hololens-identity.md) è Azure AD

Ora puoi installare app senza dover abilitare la modalità sviluppatore o usare Device Portal.  Scarica (tramite USB o tramite Microsoft Edge) il bundle Appx nel dispositivo e passa al bundle Appx in Esplora file per chiedere di avviare l'installazione.  In alternativa, [avviare un'installazione da una pagina Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Proprio come le app installate da Microsoft Store o il sideload tramite la funzionalità di distribuzione [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) di app [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) LOB di MDM, le app devono essere firmate digitalmente con lo strumento di firma e il certificato usato per firmare deve essere considerato attendibile dal dispositivo HoloLens prima che l'app possa essere distribuita.

## Requisiti

### Per i dispositivi:

 è attualmente disponibile nelle build di Windows Holographic 20H2 per i dispositivi HoloLens 2. Assicurati che tutti i dispositivi che usano questo metodo siano [aggiornati.](hololens-update-hololens.md)

### Per le tue app: 
La configurazione della soluzione dell'app deve essere **Master** o **Release** perché il programma di installazione app userà le dipendenze dallo Store. Vedi altre informazioni sulla [creazione di pacchetti dell'app.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)

Le app installate tramite questo metodo devono essere firmate digitalmente. Dovrai usare un certificato per firmare l'app. È possibile ottenere un certificato dall'elenco delle CA attendibili [di Microsoft,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)nel qual caso non sarà necessario eseguire alcuna azione aggiuntiva. Oppure puoi firmare il tuo certificato, tuttavia tale certificato dovrà essere inserito nel dispositivo.

- Come firmare le app [con lo strumento di firma.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opzioni certificato:**

- [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Selezionare un metodo di distribuzione del certificato.**

- [I pacchetti di](hololens-provisioning.md) provisioning possono essere applicati ai dispositivi locali.
- MDM può essere usato per [applicare certificati con configurazioni dei dispositivi.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)
- Utilizzare Gestione certificati [nel dispositivo.](certificate-manager.md)

## Metodo di installazione

1. Verifica che il dispositivo non sia considerato gestito.
1. Verifica che il dispositivo HoloLens 2 sia acceso e che tu sia connesso.
1. Nel PC passa alla tua app personalizzata e copia yourapp.appxbundle in yourdevicename\Internal Storage\Downloads.
    Dopo aver completato la copia del file, puoi disconnettere il dispositivo e completare l'installazione in un secondo momento.
1. Dal dispositivo HoloLens 2 apri il **menu Start,** seleziona **Tutte le app** e avvia l'app **Esplora** file.
1. Passare alla cartella Download. Nel pannello sinistro dell'app potrebbe essere necessario selezionare prima questo **dispositivo,** quindi passare a Download.
1. Seleziona il file yourapp.appxbundle.
1. Verrà avviato il programma di installazione app. Seleziona il **pulsante Installa** per installare l'app.

L'app installata verrà avviata automaticamente al termine dell'installazione.

![Installazione di esempi MRTK tramite il programma di installazione app](images/hololens-app-installer-picture.jpg)

### Risoluzione dei problemi relativi alle installazioni

Se l'installazione dell'app non è riuscita, controlla quanto segue per risolvere i problemi:

- L'app è una build Master o Release.
- Il dispositivo viene aggiornato a una build in cui questa funzionalità è disponibile.
- Si è [connessi a Internet.](hololens-network.md)
- Gli [endpoint per Microsoft Store sono](hololens-offline.md) configurati correttamente.  

## Programma di installazione Web

Gli utenti possono installare un'app direttamente da un server Web. Questo flusso utilizza il programma di installazione app combinato con un metodo di distribuzione di download e installazione semplice.

### Come configurare l'installazione Web:

1. Verifica che l'app sia configurata correttamente per l'installazione.
1. Seguire questa [procedura per abilitare l'installazione da una pagina Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### Esperienza utente finale:

1. L'utente riceve e installa il certificato nel dispositivo usando un metodo scelto in precedenza.
1. L'utente visita l'URL creato dal passaggio precedente.

L'app verrà ora installata nel dispositivo. Per trovare l'app, apri il **menu Start** e seleziona il pulsante Tutte le **app** per trovare l'app.

- Per altre informazioni sulla risoluzione dei problemi relativi al metodo di installazione del programma di installazione delle app, visita [la pagina relativa alla risoluzione dei problemi relativi al programma di installazione delle app.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> L'interfaccia utente durante il processo di aggiornamento non è supportata. Pertanto, l'opzione ShowPrompt in [questa pagina e](https://docs.microsoft.com/windows/msix/app-installer/update-settings) le opzioni correlate non sono supportate.

## App di esempio

Per provare il programma di installazione app con alcune app di esempio, vedere alcuni degli esempi disponibili:

- [Hub degli esempi MRTK](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Superfici](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [App di esempio UWP che possono essere usate per i test](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
