---
title: Controllo di applicazioni di Windows Defender - WDAC
description: Panoramica sulle caratteristiche di WDAC e su come usare la gestione di dispositivi HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135572"
---
# Controllo di applicazioni di Windows Defender - WDAC

WDAC consente a un amministratore IT di configurare i propri dispositivi in modo da bloccare il lancio delle app nei dispositivi. Questo è diverso dai metodi di restrizione del dispositivo, ad esempio la modalità Kiosk, in cui l'utente viene presentato con un'interfaccia utente che nasconde le app nel dispositivo, ma possono comunque essere avviate. Mentre WDAC è implementato, le app sono ancora visibili nell'elenco tutte le app, ma WDAC arresta le app e i processi da poter essere avviati dall'utente del dispositivo.

> [!NOTE]
> Quando gli utenti finali tentano di avviare un'app bloccata da WDAC, in HoloLens non riceveranno una notifica per non essere in grado di avviare l'app.

Di seguito è riportata una guida per gli utenti per informazioni su come [usare WDAC e Windows PowerShell per consentire o bloccare le app su dispositivi HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Quando gli utenti cercano le app installate nel PC Windows 10 usando il primo passaggio di esempio, potrebbero essere necessari alcuni tentativi per limitare i risultati.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se non si conosce il nome completo del pacchetto, potrebbe essere necessario eseguire "Get-AppxPackage-Name \ * YourBestGuess \ *" alcune volte per trovarlo. Dopo aver eseguito il nome "$package 1 = Get-AppxPackage-Name actual. PackageName"

Ad esempio, eseguendo le operazioni seguenti per Edge verrà restituito più di un risultato, ma da tale elenco puoi identificare che il nome completo che ti serve è Microsoft. MicrosoftEdge. 

```powershell
Get-AppxPackage -name *edge*
``` 

## Pacchetto di nomi di famiglia per le app in HoloLens

Nella Guida collegata sopra è possibile modificare manualmente newPolicy.xml e aggiungere regole per le applicazioni installate solo in HoloLens con i loro nomi di famiglia di pacchetti. Talvolta è possibile usare app che non sono presenti nel PC desktop che si vuole aggiungere ai criteri. 

Ecco un elenco delle app comunemente usate e In-Box per i dispositivi HoloLens 2.

| Nome dell'app                   | Nome della famiglia di pacchetti                                |
|----------------------------|----------------------------------------------------|
| Visualizzatore 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Programma di installazione app              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| Calendario                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Fotocamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Hub di Feedback               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Esplora file              | c5e2524a-ea46-4f67-841F-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Film e TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Foto                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Impostazioni                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Suggerimenti                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-il blocco del programma di installazione delle app blocca solo l'app del programma di installazione dell'app e non le app installate da altre origini, ad esempio Microsoft Store o dalla tua soluzione MDM.

### Come trovare un nome di famiglia di pacchetti

Se un'app non è presente nell'elenco, un utente può usare Device Portal, connesso a un HoloLens 2 che ha installato l'app che ha voluto essere bloccata, per determinare la PackageRelativeID e da lì ottenere il PackageFamilyName.

1. Installare l'app nel dispositivo HoloLens 2. 
1. Aprire Impostazioni-> gli aggiornamenti & Securtiy-> per gli sviluppatori e abilitare la **modalità sviluppatore** e quindi **Device Portal**. 
    1. Altre informazioni dettagliate per altre informazioni [, vedere Configurazione e uso di Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Una volta connesso Device Portal, passa alle **visualizzazioni** e quindi alle **app**. 
1. Nel pannello app installate usare l'elenco a discesa per selezionare l'app installata. 
1. Individuare il PackageRelativeID. 
1. Copiare i caratteri dell'app prima del!, questo sarà il PackageFamilyName.

## Esempio di installazione dell'app di blocco

Ad esempio, potresti voler bloccare l'app del [programma di installazione dell'app](app-deploy-app-installer.md) . Per questo esempio è stato incluso un codice di esempio. Scaricare questi [esempi di codice per questo esempio](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer). Nel file zip troverai:

| File | Uso |
|-|-|
| compiledPolicy. bin | [Creato nel passaggio 9, usato nel passaggio finale 10.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| mergedPolicy.xml | [Creato nel passaggio 6.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| WDAC_Set. SyncML | Non usato in WDAC ma può essere usato per per [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) |

Se vuoi provare a bloccare immediatamente un'app, in questo caso l'app di installazione dell'app, quindi usa il file compiledPolicy. bin e passa al passaggio 10 nel link precedente. In questo modo potrai testare i criteri personalizzati e verificare che le assegnazioni di gruppo e la configurazione dei criteri siano corrette. 

Se vuoi combinare i criteri di WDAC per bloccare il programma di installazione delle app con altre app nell'elenco precedente o in qualsiasi altra app, puoi usare il file mergedPolicy.xml e continuare a unire nuovi criteri. Come indicato sopra, i criteri di WDAC sono additivi, quindi non è necessario. 

Dato che l'app di installazione dell'app viene avviata tramite il tentativo di aprire un file verrà visualizzata una richiesta. Come indicato sopra, le app bloccate da WDAC non presentano una richiesta di blocco, tuttavia, dato che l'utente sta provando ad aprire un file nel dispositivo, viene visualizzato un messaggio di errore per l'apertura del file. 

![Installazione dell'app bloccata da WDAC](images\wdac-app-installer-no-launch.jpg)

Se non si vuole usare WDAC, è possibile usare [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) in alternativa per rimuovere il programma di installazione dell'app UX, che è un'app dopo tutto. Il risultato è che l'app del programma di installazione dell'app verrà disinstallata dal dispositivo. . appx,. msix,. msixbundle e altre estensioni di file, oltre al protocollo per l'avvio da Web a app, non verranno più gestite dall'app di installazione dell'app. L'utente riceverà una richiesta per cercare un gestore per l'estensione del file/protocollo nello Store e non troverà l'app perché non è elencata.