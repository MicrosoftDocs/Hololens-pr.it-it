---
title: Come eseguire il side load e installare le app tramite HoloLens 2 Programma di installazione app
description: Informazioni su come installare e risolvere i problemi delle app con il programma di installazione delle app e il caricamento laterale e installare le app tramite l'interfaccia utente.
keywords: gestione delle app, app, hololens, programma di installazione delle app
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
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032488"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Installare app in HoloLens 2 tramite Programma di installazione app

> [!NOTE]
> Questa funzionalità è stata resa disponibile in [Windows Holographic, versione 20H2 - Aggiornamento di dicembre 2020.](hololens-release-notes.md) Assicurarsi che il dispositivo [sia aggiornato](hololens-update-hololens.md) per usare questa funzionalità.

È stata aggiunta una nuova funzionalità **(Programma di installazione app)** per consentire di installare le applicazioni in modo più semplice HoloLens 2 dispositivi. La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti.** Per evitare interruzioni per le aziende, il programma di installazione delle app non **sarà attualmente disponibile per** i dispositivi gestiti.  

Un dispositivo viene considerato "gestito" **se si** verifica una delle condizioni seguenti:

- MDM [registrato](hololens-enroll-mdm.md)
- Configurato con il [pacchetto di provisioning](hololens-provisioning.md)
- [L'identità utente](hololens-identity.md) Azure AD

È ora possibile installare le app senza dover abilitare la modalità sviluppatore o usare Portale di dispositivi.  Scaricare (tramite USB o tramite Microsoft Edge) il bundle Appx nel dispositivo e passare al bundle Appx nel Esplora file per chiedere di avviare l'installazione.  In alternativa, [avviare un'installazione da una pagina Web](/windows/msix/app-installer/installing-windows10-apps-web). Proprio come le app installate dal Microsoft Store o il sideload usando la funzionalità di distribuzione di app [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) LOB [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) MDM, le app devono essere firmate digitalmente con lo strumento di firma e il certificato usato per firmare deve essere considerato attendibile dal dispositivo HoloLens prima che l'app possa essere distribuita.

## <a name="requirements"></a>Requisiti

### <a name="for-your-devices"></a>Per i dispositivi:

Questa funzionalità è attualmente disponibile nelle build Windows Holographic 20H2 per HoloLens 2 dispositivi. Assicurarsi che tutti i dispositivi che usano questo metodo siano [aggiornati.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Per le app:

La configurazione della soluzione dell'app deve essere **Master** o **Release** perché l'Programma di installazione app userà le dipendenze dallo Store. Vedere altre informazioni sulla [creazione di pacchetti di app.](/windows/msix/app-installer/create-appinstallerfile-vs)

Le app installate tramite questo metodo devono essere firmate digitalmente. È necessario usare un certificato per firmare l'app. È possibile ottenere un certificato dall'elenco di [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)attendibili ms , nel qual caso non sarà necessario eseguire alcuna azione aggiuntiva. Oppure è possibile firmare il proprio certificato, tuttavia tale certificato dovrà essere inserito nel dispositivo.

- Come firmare le app [usando lo strumento di firma.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opzioni del certificato:**

- [Elenco di CA attendibili ms](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Selezionare un metodo di distribuzione del certificato.**

- [I pacchetti di](hololens-provisioning.md) provisioning possono essere applicati ai dispositivi locali.
- MDM può essere usato per [applicare i certificati con le configurazioni dei dispositivi.](/mem/intune/protect/certificates-configure)
- Usare gestione certificati [nel dispositivo](certificate-manager.md).

## <a name="installation-method"></a>Metodo di installazione

1. Verificare che il dispositivo non sia considerato gestito.
1. Verificare che il dispositivo HoloLens 2 sia acceso e che sia stato eseguito l'accesso.
1. Nel PC passare all'app personalizzata e copiare yourapp.appxbundle indevicename\Internal Archiviazione\Downloads.
    Al termine della copia del file, è possibile disconnettere il dispositivo e completare l'installazione in un secondo momento.
1. Dal dispositivo HoloLens 2 aprire il **menu Start,** selezionare **Tutte le app** e avviare l Esplora file app. 
1. Passare alla cartella Download. Potrebbe essere necessario nel pannello sinistro dell'app selezionare **Prima questo dispositivo,** quindi passare a Download.
1. Selezionare il file yourapp.appxbundle.
1. Il Programma di installazione app verrà avviato. Selezionare il **pulsante Installa** per installare l'app.

L'app installata verrà avviata automaticamente al termine dell'installazione.

![Installazione di esempi MRTK tramite Programma di installazione app.](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Risoluzione dei problemi relativi alle installazioni

Se l'installazione dell'app non è riuscita, controllare quanto segue per risolvere i problemi:

- L'app è una build master o di versione.
- Il dispositivo viene aggiornato a una build in cui è disponibile questa funzionalità.
- Si è [connessi a Internet.](hololens-network.md)
- Gli [endpoint per l'Microsoft Store](hololens-offline.md) sono configurati correttamente.  

## <a name="web-installer"></a>Programma di installazione Web

Gli utenti possono installare un'app direttamente da un server Web. Questo flusso usa l'Programma di installazione app combinato con un metodo di distribuzione facile per il download e l'installazione.

### <a name="how-to-set-up-web-install"></a>Come configurare l'installazione Web:

1. Verificare che l'app sia configurata correttamente per l'installazione.
1. Seguire questa [procedura per abilitare l'installazione da una pagina Web](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### <a name="end-user-experience"></a>Esperienza utente finale:

1. L'utente riceve e installa il certificato nel dispositivo usando un metodo scelto in precedenza.
1. L'utente visita l'URL creato nel passaggio precedente.

L'app verrà ora installata nel dispositivo. Per trovare l'app, aprire il **menu Start** e selezionare il pulsante **Tutte le** app per trovare l'app.

- Per altre informazioni sulla risoluzione dei problemi relativi al metodo di installazione del programma di installazione dell'app, vedere [Risolvere i problemi del programma di installazione dell'app.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> L'interfaccia utente durante il processo di aggiornamento non è supportata. L'opzione ShowPrompt in [questa pagina e](/windows/msix/app-installer/update-settings) le opzioni correlate non sono quindi supportate.

## <a name="sample-apps"></a>App di esempio

Provare il Programma di installazione app con una delle app di esempio disponibili. 
> [!div class="nextstepaction"]
> [App di esempio](/windows/mixed-reality/develop/features-and-samples)
