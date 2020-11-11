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
ms.openlocfilehash: b12079142049cce28ec00803ad0a1f8dc92333e1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163127"
---
# <span data-ttu-id="e7523-103">Controllo di applicazioni di Windows Defender - WDAC</span><span class="sxs-lookup"><span data-stu-id="e7523-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="e7523-104">WDAC consente a un amministratore IT di configurare i propri dispositivi in modo da bloccare il lancio delle app nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e7523-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="e7523-105">Questo è diverso dai metodi di restrizione del dispositivo, ad esempio la modalità Kiosk, in cui l'utente viene presentato con un'interfaccia utente che nasconde le app nel dispositivo, ma possono comunque essere avviate.</span><span class="sxs-lookup"><span data-stu-id="e7523-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="e7523-106">Mentre WDAC è implementato, le app sono ancora visibili nell'elenco tutte le app, ma WDAC arresta le app e i processi da poter essere avviati dall'utente del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e7523-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="e7523-107">A un dispositivo può essere assegnato più di un criterio WDAC.</span><span class="sxs-lookup"><span data-stu-id="e7523-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="e7523-108">Se in un sistema sono impostati più criteri di WDAC, i più restrittivi avranno effetto.</span><span class="sxs-lookup"><span data-stu-id="e7523-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="e7523-109">Quando gli utenti finali tentano di avviare un'app bloccata da WDAC, in HoloLens non riceveranno una notifica per non essere in grado di avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="e7523-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="e7523-110">Di seguito è riportata una guida per gli utenti per informazioni su come [usare WDAC e Windows PowerShell per consentire o bloccare le app su dispositivi HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="e7523-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="e7523-111">Quando gli utenti cercano le app installate nel PC Windows 10 usando il primo passaggio di esempio, potrebbero essere necessari alcuni tentativi per limitare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e7523-111">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="e7523-112">Se non si conosce il nome completo del pacchetto, potrebbe essere necessario eseguire "Get-AppxPackage-Name \ \* YourBestGuess \ \*" alcune volte per trovarlo.</span><span class="sxs-lookup"><span data-stu-id="e7523-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="e7523-113">Dopo aver eseguito il nome "$package 1 = Get-AppxPackage-Name actual. PackageName"</span><span class="sxs-lookup"><span data-stu-id="e7523-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="e7523-114">Ad esempio, eseguendo le operazioni seguenti per Edge verrà restituito più di un risultato, ma da tale elenco puoi identificare che il nome completo che ti serve è Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="e7523-114">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="e7523-115">Pacchetto di nomi di famiglia per le app in HoloLens</span><span class="sxs-lookup"><span data-stu-id="e7523-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="e7523-116">Nella Guida collegata sopra è possibile modificare manualmente newPolicy.xml e aggiungere regole per le applicazioni installate solo in HoloLens con i loro nomi di famiglia di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e7523-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="e7523-117">Talvolta è possibile usare app che non sono presenti nel PC desktop che si vuole aggiungere ai criteri.</span><span class="sxs-lookup"><span data-stu-id="e7523-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="e7523-118">Ecco un elenco delle app comunemente usate e In-Box per i dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e7523-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="e7523-119">Nome dell'app</span><span class="sxs-lookup"><span data-stu-id="e7523-119">App Name</span></span>                   | <span data-ttu-id="e7523-120">Nome della famiglia di pacchetti</span><span class="sxs-lookup"><span data-stu-id="e7523-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="e7523-121">Visualizzatore 3D</span><span class="sxs-lookup"><span data-stu-id="e7523-121">3D Viewer</span></span>                  | <span data-ttu-id="e7523-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="e7523-123">Programma di installazione app</span><span class="sxs-lookup"><span data-stu-id="e7523-123">App Installer</span></span>              | <span data-ttu-id="e7523-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="e7523-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="e7523-125">Calendario</span><span class="sxs-lookup"><span data-stu-id="e7523-125">Calendar</span></span>                   | <span data-ttu-id="e7523-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="e7523-127">Fotocamera</span><span class="sxs-lookup"><span data-stu-id="e7523-127">Camera</span></span>                     | <span data-ttu-id="e7523-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="e7523-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="e7523-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="e7523-129">Cortana</span></span>                    | <span data-ttu-id="e7523-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="e7523-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="e7523-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="e7523-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="e7523-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e7523-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="e7523-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="e7523-135">Hub di Feedback</span><span class="sxs-lookup"><span data-stu-id="e7523-135">Feedback Hub</span></span>               | <span data-ttu-id="e7523-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="e7523-137">Esplora file</span><span class="sxs-lookup"><span data-stu-id="e7523-137">File Explorer</span></span>              | <span data-ttu-id="e7523-138">c5e2524a-ea46-4f67-841F-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="e7523-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="e7523-139">Mail</span><span class="sxs-lookup"><span data-stu-id="e7523-139">Mail</span></span>                       | <span data-ttu-id="e7523-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="e7523-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e7523-141">Microsoft Store</span></span>            | <span data-ttu-id="e7523-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="e7523-143">Film e TV</span><span class="sxs-lookup"><span data-stu-id="e7523-143">Movies & TV</span></span>                | <span data-ttu-id="e7523-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="e7523-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="e7523-145">OneDrive</span></span>                   | <span data-ttu-id="e7523-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="e7523-147">Foto</span><span class="sxs-lookup"><span data-stu-id="e7523-147">Photos</span></span>                     | <span data-ttu-id="e7523-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="e7523-149">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="e7523-149">Settings</span></span>                   | <span data-ttu-id="e7523-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="e7523-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="e7523-151">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="e7523-151">Tips</span></span>                       | <span data-ttu-id="e7523-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e7523-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="e7523-153">1-il blocco del programma di installazione delle app blocca solo l'app del programma di installazione dell'app e non le app installate da altre origini, ad esempio Microsoft Store o dalla tua soluzione MDM.</span><span class="sxs-lookup"><span data-stu-id="e7523-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="e7523-154">Come trovare un nome di famiglia di pacchetti</span><span class="sxs-lookup"><span data-stu-id="e7523-154">How to find a Package Family Name</span></span>

<span data-ttu-id="e7523-155">Se un'app non è presente nell'elenco, un utente può usare Device Portal, connesso a un HoloLens 2 che ha installato l'app che ha voluto essere bloccata, per determinare la PackageRelativeID e da lì ottenere il PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="e7523-155">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="e7523-156">Installare l'app nel dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e7523-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="e7523-157">Aprire Impostazioni-> gli aggiornamenti & sicurezza > per gli sviluppatori e abilitare la **modalità sviluppatore** e quindi **Device Portal**.</span><span class="sxs-lookup"><span data-stu-id="e7523-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="e7523-158">Altre informazioni dettagliate per altre informazioni [, vedere Configurazione e uso di Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="e7523-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="e7523-159">Una volta connesso Device Portal, passa alle **visualizzazioni** e quindi alle **app**.</span><span class="sxs-lookup"><span data-stu-id="e7523-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="e7523-160">Nel pannello app installate usare l'elenco a discesa per selezionare l'app installata.</span><span class="sxs-lookup"><span data-stu-id="e7523-160">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="e7523-161">Individuare il PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="e7523-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="e7523-162">Copiare i caratteri dell'app prima del!, questo sarà il PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="e7523-162">Copy app characters before the !, this will be your PackageFamilyName.</span></span>


