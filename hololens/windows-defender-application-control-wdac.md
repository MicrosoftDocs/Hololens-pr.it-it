---
title: Controllo applicazione Windows Defender-WDAC
description: Panoramica sulle caratteristiche di WDAC e su come usare la gestione di dispositivi HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d1147b202d3b575fa1f2dd20f620005c786ea9fc
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016784"
---
# Controllo applicazione Windows Defender-WDAC

WDAC consente a un amministratore IT di configurare i propri dispositivi in modo da bloccare il lancio delle app nei dispositivi. Questo è diverso dai metodi di restrizione del dispositivo, ad esempio la modalità Kiosk, in cui l'utente viene presentato con un'interfaccia utente che nasconde le app nel dispositivo, ma possono comunque essere avviate. Mentre WDAC è implementato, le app sono ancora visibili nell'elenco tutte le app, ma WDAC arresta le app e i processi da poter essere avviati dall'utente del dispositivo.

> [!NOTE]
> Quando gli utenti finali tentano di avviare un'app bloccata da WDAC, in HoloLens non riceveranno una notifica per non essere in grado di avviare l'app.

Di seguito è riportata una guida per gli utenti per informazioni su come [usare WDAC e Windows PowerShell per consentire o bloccare le app su dispositivi HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Quando gli utenti cercano le app installate nel PC Windows 10 usando il primo passaggio di esempio, potrebbero essere necessari alcuni tentativi per limitare i risultati.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se non si conosce il nome completo del pacchetto, potrebbe essere necessario eseguire "Get-AppxPackage-Name \ * YourBestGuess \ *" alcune volte per trovarlo. Dopo aver eseguito il nome ' $package 1 = Get-AppxPackage-Name actual. PackageName '

Ad esempio, eseguendo le operazioni seguenti per Edge verrà restituito più di un risultato, ma da tale elenco puoi identificare che il nome completo che ti serve è Microsoft. MicrosoftEdge. 

```powershell
Get-AppxPackage -name *edge*
``` 

## Pacchetto di nomi di famiglia per le app in HoloLens

Nella Guida collegata sopra è possibile modificare manualmente newPolicy.xml e aggiungere regole per le applicazioni installate solo in HoloLens con i loro nomi di famiglia di pacchetti. Talvolta è possibile usare app che non sono presenti nel PC desktop che si vuole aggiungere ai criteri. 

Ecco un elenco delle app comunemente usate e in-box per i dispositivi HoloLens 2.

| Nome dell'app                   | Nome della famiglia di pacchetti                                |
|----------------------------|----------------------------------------------------|
| Visualizzatore 3D                  | Microsoft. Microsoft3DViewer_8wekyb3d8bbwe          |
| Calendario                   | Microsoft. windowscommunicationsapps_8wekyb3d8bbwe  |
| Fotocamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft. 549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft. Dynamics365. Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft. MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Hub di Feedback               | Microsoft. WindowsFeedbackHub_8wekyb3d8bbwe         |
| Esplora file              | c5e2524a-ea46-4f67-841F-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | Microsoft. windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft. WindowsStore_8wekyb3d8bbwe               |
| Film e TV                | Microsoft. ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | Microsoft. microsoftskydrive_8wekyb3d8bbwe          |
| Foto                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Impostazioni                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Suggerimenti                       | Microsoft. HoloLensTips_8wekyb3d8bbwe               |

Se un'app non è presente nell'elenco, un utente può usare Device Portal, connesso a un HoloLens 2 che ha installato l'app che ha voluto essere bloccata, per determinare la PackageRelativeID e da lì ottenere il PackageFamilyName.

1. Installare l'app nel dispositivo HoloLens 2. 
1. Aprire Impostazioni-> gli aggiornamenti & Securtiy-> per gli sviluppatori e abilitare la **modalità sviluppatore** e quindi **Device Portal**. 
    1. Altre informazioni dettagliate per altre informazioni [, vedere Configurazione e uso di Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Una volta connesso Device Portal, passa alle **visualizzazioni** e quindi alle **app**. 
1. Nel pannello app installate usare l'elenco a discesa per selezionare l'app installata. 
1. Individuare il PackageRelativeID. 
1. Copiare i caratteri dell'app prima del!, questo sarà il PackageFamilyName.

