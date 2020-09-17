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
# <span data-ttu-id="f2a4f-103">Controllo applicazione Windows Defender-WDAC</span><span class="sxs-lookup"><span data-stu-id="f2a4f-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="f2a4f-104">WDAC consente a un amministratore IT di configurare i propri dispositivi in modo da bloccare il lancio delle app nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="f2a4f-105">Questo è diverso dai metodi di restrizione del dispositivo, ad esempio la modalità Kiosk, in cui l'utente viene presentato con un'interfaccia utente che nasconde le app nel dispositivo, ma possono comunque essere avviate.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="f2a4f-106">Mentre WDAC è implementato, le app sono ancora visibili nell'elenco tutte le app, ma WDAC arresta le app e i processi da poter essere avviati dall'utente del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="f2a4f-107">Quando gli utenti finali tentano di avviare un'app bloccata da WDAC, in HoloLens non riceveranno una notifica per non essere in grado di avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="f2a4f-108">Di seguito è riportata una guida per gli utenti per informazioni su come [usare WDAC e Windows PowerShell per consentire o bloccare le app su dispositivi HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="f2a4f-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="f2a4f-109">Quando gli utenti cercano le app installate nel PC Windows 10 usando il primo passaggio di esempio, potrebbero essere necessari alcuni tentativi per limitare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="f2a4f-110">Se non si conosce il nome completo del pacchetto, potrebbe essere necessario eseguire "Get-AppxPackage-Name \ \* YourBestGuess \ \*" alcune volte per trovarlo.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="f2a4f-111">Dopo aver eseguito il nome ' $package 1 = Get-AppxPackage-Name actual. PackageName '</span><span class="sxs-lookup"><span data-stu-id="f2a4f-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="f2a4f-112">Ad esempio, eseguendo le operazioni seguenti per Edge verrà restituito più di un risultato, ma da tale elenco puoi identificare che il nome completo che ti serve è Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="f2a4f-113">Pacchetto di nomi di famiglia per le app in HoloLens</span><span class="sxs-lookup"><span data-stu-id="f2a4f-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="f2a4f-114">Nella Guida collegata sopra è possibile modificare manualmente newPolicy.xml e aggiungere regole per le applicazioni installate solo in HoloLens con i loro nomi di famiglia di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="f2a4f-115">Talvolta è possibile usare app che non sono presenti nel PC desktop che si vuole aggiungere ai criteri.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="f2a4f-116">Ecco un elenco delle app comunemente usate e in-box per i dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="f2a4f-117">Nome dell'app</span><span class="sxs-lookup"><span data-stu-id="f2a4f-117">App Name</span></span>                   | <span data-ttu-id="f2a4f-118">Nome della famiglia di pacchetti</span><span class="sxs-lookup"><span data-stu-id="f2a4f-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="f2a4f-119">Visualizzatore 3D</span><span class="sxs-lookup"><span data-stu-id="f2a4f-119">3D Viewer</span></span>                  | <span data-ttu-id="f2a4f-120">Microsoft. Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="f2a4f-121">Calendario</span><span class="sxs-lookup"><span data-stu-id="f2a4f-121">Calendar</span></span>                   | <span data-ttu-id="f2a4f-122">Microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-122">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="f2a4f-123">Fotocamera</span><span class="sxs-lookup"><span data-stu-id="f2a4f-123">Camera</span></span>                     | <span data-ttu-id="f2a4f-124">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="f2a4f-124">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="f2a4f-125">Cortana</span><span class="sxs-lookup"><span data-stu-id="f2a4f-125">Cortana</span></span>                    | <span data-ttu-id="f2a4f-126">Microsoft. 549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-126">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="f2a4f-127">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="f2a4f-127">Dynamics 365 Guides</span></span>        | <span data-ttu-id="f2a4f-128">Microsoft. Dynamics365. Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-128">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="f2a4f-129">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="f2a4f-129">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="f2a4f-130">Microsoft. MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-130">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="f2a4f-131">Hub di Feedback</span><span class="sxs-lookup"><span data-stu-id="f2a4f-131">Feedback Hub</span></span>               | <span data-ttu-id="f2a4f-132">Microsoft. WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-132">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="f2a4f-133">Esplora file</span><span class="sxs-lookup"><span data-stu-id="f2a4f-133">File Explorer</span></span>              | <span data-ttu-id="f2a4f-134">c5e2524a-ea46-4f67-841F-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="f2a4f-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="f2a4f-135">Mail</span><span class="sxs-lookup"><span data-stu-id="f2a4f-135">Mail</span></span>                       | <span data-ttu-id="f2a4f-136">Microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-136">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="f2a4f-137">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f2a4f-137">Microsoft Store</span></span>            | <span data-ttu-id="f2a4f-138">Microsoft. WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-138">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="f2a4f-139">Film e TV</span><span class="sxs-lookup"><span data-stu-id="f2a4f-139">Movies & TV</span></span>                | <span data-ttu-id="f2a4f-140">Microsoft. ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-140">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="f2a4f-141">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f2a4f-141">OneDrive</span></span>                   | <span data-ttu-id="f2a4f-142">Microsoft. microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-142">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="f2a4f-143">Foto</span><span class="sxs-lookup"><span data-stu-id="f2a4f-143">Photos</span></span>                     | <span data-ttu-id="f2a4f-144">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-144">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="f2a4f-145">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="f2a4f-145">Settings</span></span>                   | <span data-ttu-id="f2a4f-146">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="f2a4f-146">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="f2a4f-147">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="f2a4f-147">Tips</span></span>                       | <span data-ttu-id="f2a4f-148">Microsoft. HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2a4f-148">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

<span data-ttu-id="f2a4f-149">Se un'app non è presente nell'elenco, un utente può usare Device Portal, connesso a un HoloLens 2 che ha installato l'app che ha voluto essere bloccata, per determinare la PackageRelativeID e da lì ottenere il PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-149">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="f2a4f-150">Installare l'app nel dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-150">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="f2a4f-151">Aprire Impostazioni-> gli aggiornamenti & Securtiy-> per gli sviluppatori e abilitare la **modalità sviluppatore** e quindi **Device Portal**.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-151">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="f2a4f-152">Altre informazioni dettagliate per altre informazioni [, vedere Configurazione e uso di Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="f2a4f-152">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="f2a4f-153">Una volta connesso Device Portal, passa alle **visualizzazioni** e quindi alle **app**.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-153">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="f2a4f-154">Nel pannello app installate usare l'elenco a discesa per selezionare l'app installata.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-154">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="f2a4f-155">Individuare il PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-155">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="f2a4f-156">Copiare i caratteri dell'app prima del!, questo sarà il PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="f2a4f-156">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

