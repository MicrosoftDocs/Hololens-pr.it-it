---
title: Windows Defender Controllo delle applicazioni - WDAC
description: Panoramica di Windows Defender controllo delle applicazioni e su come usarlo per gestire HoloLens dispositivi di realtà mista.
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
ms.openlocfilehash: ab05f1bbe1570d4966932d6f8ac857e5bd2d8a7d3a8f5b93aaba0335eda05b01
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665557"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Controllo delle applicazioni - WDAC

WDAC consente a un amministratore IT di configurare i propri dispositivi per bloccare l'avvio delle app nei dispositivi. Questo è diverso rispetto ai metodi di restrizione dei dispositivi, ad esempio la modalità tutto schermo, in cui all'utente viene presentata un'interfaccia utente che nasconde le app nel dispositivo, ma che possono comunque essere avviate. Durante l'implementazione di WDAC, le app sono ancora visibili nell'elenco Tutte le app, ma WDAC impedisce l'avvio di tali app e processi da parte dell'utente del dispositivo.

A un dispositivo possono essere assegnati più criteri WDAC. Se in un sistema sono impostati più criteri WDAC, vengono applicati quelli più restrittivi. 

> [!NOTE]
> Quando gli utenti finali tentano di avviare un'app bloccata da WDAC, HoloLens non riceveranno una notifica che indica che non è possibile avviare l'app.

Di seguito è riportata una guida per gli utenti che illustrano come usare [WDAC](/mem/intune/configuration/custom-profile-hololens)e Windows PowerShell per consentire o bloccare le app nei dispositivi HoloLens 2 con Microsoft Intune .

Quando gli utenti cercano le app installate nel PC Windows 10 usando il primo passaggio di esempio, potrebbe essere necessario eseguire alcuni tentativi per restringere i risultati.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se non si conosce il nome completo del pacchetto, potrebbe essere necessario eseguire 'Get-AppxPackage -name \* YourBestGuess' alcune volte per \* trovarlo. Dopo aver creato il nome, eseguire "$package 1 = Get-AppxPackage -name Actual.PackageName"

Ad esempio, l'esecuzione di quanto segue per Microsoft Edge restituirà più di un risultato, ma da tale elenco è possibile identificare che il nome completo necessario è Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Nomi delle famiglie di pacchetti per le app HoloLens

Nella guida collegata in precedenza è possibile modificare manualmente newPolicy.xml e aggiungere regole per le applicazioni installate solo in HoloLens con i relativi nomi di famiglia di pacchetti. In alcuni casi è possibile usare app che non sono presenti nel PC desktop che si vuole aggiungere ai criteri.

Di seguito è riportato un elenco di app di uso In-Box per HoloLens 2 dispositivi.

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

- 1 - Il Programma di installazione app blocca solo l'app Programma di installazione app e non le app installate da altre origini, ad esempio il Microsoft Store o dalla soluzione MDM.

### <a name="how-to-find-a-package-family-name"></a>Come trovare un nome di famiglia di pacchetti

Se un'app non è in questo elenco, un utente può usare Portale di dispositivi, connesso a un HoloLens 2 che ha installato l'app che si vuole bloccare, per determinare PackageRelativeID e da qui ottenere PackageFamilyName.

1. Installare l'app nel HoloLens 2 dispositivo. 
1. Aprire Impostazioni -> Aggiornamenti & Sicurezza -> Per gli sviluppatori, abilitare modalità  sviluppatore e quindi **Portale di dispositivi.** 
    1. Altre istruzioni dettagliate per altre informazioni sulla configurazione [e l'uso del portale per dispositivi sono disponibili qui.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Dopo Portale di dispositivi connesso, passare a **Visualizzazioni e** quindi **ad App.** 
1. Nel pannello App installate usare l'elenco a discesa per selezionare l'app installata. 
1. Individuare PackageRelativeID. 
1. Copiare i caratteri dell'app prima di ! . Questi caratteri saranno packageFamilyName.


