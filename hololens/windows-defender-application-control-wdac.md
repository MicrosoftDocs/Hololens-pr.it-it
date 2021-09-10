---
title: Controllo di applicazioni di Windows Defender (WDAC)
description: Panoramica di Windows Defender controllo delle applicazioni e su come usarlo per gestire HoloLens dispositivi di realtà mista.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427899"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Controllo dell'applicazione - WDAC

## <a name="overview"></a>Panoramica

WDAC consente di configurare HoloLens per bloccare l'avvio delle app. È diversa dalla modalità tutto schermo, in cui l'interfaccia utente nasconde le app ma può comunque essere avviata. Con WDAC è possibile visualizzare le app, ma non avviate.

> [!NOTE]
> Quando gli utenti finali tentano di avviare un'app bloccata da WDAC HoloLens, non saranno informati di non essere in grado di avviare l'app.

A un dispositivo possono essere assegnati più criteri WDAC. Se in un sistema sono impostati più criteri WDAC, vengono applicati quelli più restrittivi. 

Di seguito è riportata una guida per gli utenti che possono imparare a usare [WDAC](/mem/intune/configuration/custom-profile-hololens)e Windows PowerShell per consentire o bloccare le app nei dispositivi HoloLens 2 con Microsoft Intune .

Quando gli utenti ricercano le app installate nel PC Windows 10 usando il primo passaggio di esempio, potrebbe essere necessario eseguire alcuni tentativi per restringere i risultati.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se non si conosce il nome completo del pacchetto, potrebbe essere necessario eseguire 'Get-AppxPackage -name \* YourBestGuess' più volte per \* trovarlo. Dopo aver creato il nome eseguire '$package 1 = Get-AppxPackage -name Actual.PackageName'

Ad esempio, l'esecuzione del codice seguente per Microsoft Edge restituirà più di un risultato, ma da tale elenco è possibile identificare che il nome completo necessario è Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Nomi delle famiglie di pacchetti per le app HoloLens

Nella guida collegata in precedenza è possibile modificare manualmente newPolicy.xml e aggiungere regole per le applicazioni installate solo in HoloLens con i relativi nomi di famiglia di pacchetti. In alcuni casi è possibile usare app non presenti nel PC desktop da aggiungere ai criteri.

Di seguito è riportato un elenco di app In-Box e HoloLens 2 comuni.

| Nome dell'app                   | Nome famiglia pacchetto                                |
|----------------------------|----------------------------------------------------|
| Visualizzatore 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Programma di installazione app              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Calendario                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Fotocamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Guide di Dynamics 365        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Hub di Feedback               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Esplora file              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Posta                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Film e TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Foto                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Impostazioni                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Suggerimenti                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - Bloccando Programma di installazione app verrà bloccata solo l'app Programma di installazione app e non le app installate da altre origini, ad esempio il Microsoft Store o dalla soluzione MDM.

### <a name="how-to-find-a-package-family-name"></a>Come trovare il nome di una famiglia di pacchetti

Se un'app non è in questo elenco, un utente può usare Portale di dispositivi, connesso a un HoloLens 2 che ha installato l'app da bloccare, per determinare PackageRelativeID e da qui ottenere PackageFamilyName.

1. Installare l'app nel dispositivo HoloLens 2 dispositivo. 
1. Aprire Impostazioni -> aggiornamenti & sicurezza -> per gli sviluppatori e abilitare la **modalità** sviluppatore e quindi **portale dispositivi**. 
    1. Per altre informazioni dettagliate, vedere altre informazioni sulla [configurazione e sull'uso del portale dei dispositivi qui.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Dopo Portale di dispositivi connessione, passare a **Visualizzazioni** e quindi **ad App.** 
1. Nel pannello App installate usare l'elenco a discesa per selezionare l'app installata. 
1. Individuare PackageRelativeID. 
1. Copiare i caratteri dell'app prima di `!` , che sarà packageFamilyName.

