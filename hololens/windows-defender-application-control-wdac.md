---
title: Controllo applicazioni di Windows Defender
description: Panoramica su cosa Windows Defender controllo delle applicazioni e su come usarlo per gestire i dispositivi holoLens in realtà mista.
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284137"
---
# Controllo applicazioni di Windows Defender

WDAC consente a un amministratore IT di configurare i propri dispositivi per bloccare l'avvio delle app nei dispositivi. Questo è diverso rispetto ai metodi di restrizione del dispositivo, ad esempio la modalità tutto schermo, in cui all'utente viene presentata un'interfaccia utente che nasconde le app nel dispositivo ma può comunque essere avviata. Mentre WDAC è implementato, le app sono ancora visibili nell'elenco Tutte le app, ma WDAC impedisce l'avvio di tali app e processi da parte dell'utente del dispositivo.

A un dispositivo potrebbero essere assegnati più criteri WDAC. Se in un sistema sono impostati più criteri WDAC, vengono applicati quelli più restrittivi. 

> [!NOTE]
> Quando gli utenti finali tentano di avviare un'app bloccata da WDAC, in HoloLens non riceveranno una notifica che indica di non essere in grado di avviare l'app.

Di seguito è riportata una guida per gli utenti che possono imparare a usare WDAC e Windows PowerShell per consentire o bloccare le app nei dispositivi [HoloLens 2 con Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

Quando gli utenti ricercano app installate nel PC Windows 10 usando il primo passaggio di esempio, potrebbero dover eseguire alcuni tentativi per restringere i risultati.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se non conosci il nome completo del pacchetto, potresti dover eseguire "Get-AppxPackage -name \*YourBestGuess\*" alcune volte per trovarlo. Dopo aver creato il nome, eseguire '$package 1 = Get-AppxPackage -name Actual.PackageName'

Ad esempio, se si esegue il comando seguente per Microsoft Edge, verranno restituiti più risultati, ma da tale elenco è possibile identificare che il nome completo necessario è Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## Nomi delle famiglie di pacchetti per le app in HoloLens

Nella guida collegata in precedenza, puoi modificare manualmente newPolicy.xml e aggiungere regole per le applicazioni installate solo in HoloLens con i nomi delle famiglie di pacchetti. A volte ci sono app che puoi usare che non sono presenti nel PC desktop che vuoi aggiungere ai criteri.

Ecco un elenco delle app di uso comune e In-Box per i dispositivi HoloLens 2.

| Nome app                   | Nome famiglia di pacchetti                                |
|----------------------------|----------------------------------------------------|
| Visualizzatore 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Programma di installazione app              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| Calendario                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Fotocamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Hub di Feedback               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Esplora file              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Film e TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Foto                     | Microsoft.Windows.Foto_8wekyb3d8bbwe             |
| Impostazioni                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Suggerimenti                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - Il blocco del programma di installazione app blocca solo l'app del programma di installazione app e non le app installate da altre origini, ad esempio Microsoft Store o dalla soluzione MDM.

### Come trovare il nome di una famiglia di pacchetti

Se un'app non è in questo elenco, un utente può usare Device Portal, connesso a un HoloLens 2 che ha installato l'app che si desidera bloccare, per determinare PackageRelativeID e da qui ottenere PackageFamilyName.

1. Installa l'app nel dispositivo HoloLens 2. 
1. Apri Impostazioni -> aggiornamenti & sicurezza -> per sviluppatori e abilita la modalità sviluppatore **e** quindi **Portale dispositivi.** 
    1. Altre istruzioni dettagliate sulla configurazione e l'uso di [Device Portal sono disponibili qui.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Dopo aver connesso Device Portal, passa a **Visualizzazioni** e **app.** 
1. Nel pannello App installate usa l'elenco a discesa per selezionare l'app installata. 
1. Individuare PackageRelativeID. 
1. Copia i caratteri dell'app prima di !, questi caratteri saranno il tuo PackageFamilyName.


