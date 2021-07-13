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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639931"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="4481d-103">Windows Defender Controllo delle applicazioni - WDAC</span><span class="sxs-lookup"><span data-stu-id="4481d-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="4481d-104">WDAC consente a un amministratore IT di configurare i propri dispositivi per bloccare l'avvio delle app nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4481d-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="4481d-105">Questo è diverso rispetto ai metodi di restrizione dei dispositivi, ad esempio la modalità tutto schermo, in cui all'utente viene presentata un'interfaccia utente che nasconde le app nel dispositivo, ma che possono comunque essere avviate.</span><span class="sxs-lookup"><span data-stu-id="4481d-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="4481d-106">Durante l'implementazione di WDAC, le app sono ancora visibili nell'elenco Tutte le app, ma WDAC impedisce l'avvio di tali app e processi da parte dell'utente del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4481d-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="4481d-107">A un dispositivo possono essere assegnati più criteri WDAC.</span><span class="sxs-lookup"><span data-stu-id="4481d-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="4481d-108">Se in un sistema sono impostati più criteri WDAC, vengono applicati quelli più restrittivi.</span><span class="sxs-lookup"><span data-stu-id="4481d-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="4481d-109">Quando gli utenti finali tentano di avviare un'app bloccata da WDAC, HoloLens non riceveranno una notifica che indica che non è possibile avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="4481d-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="4481d-110">Di seguito è riportata una guida per gli utenti che illustrano come usare [WDAC](/mem/intune/configuration/custom-profile-hololens)e Windows PowerShell per consentire o bloccare le app nei dispositivi HoloLens 2 con Microsoft Intune .</span><span class="sxs-lookup"><span data-stu-id="4481d-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="4481d-111">Quando gli utenti cercano le app installate nel PC Windows 10 usando il primo passaggio di esempio, potrebbe essere necessario eseguire alcuni tentativi per restringere i risultati.</span><span class="sxs-lookup"><span data-stu-id="4481d-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="4481d-112">Se non si conosce il nome completo del pacchetto, potrebbe essere necessario eseguire 'Get-AppxPackage -name \* YourBestGuess' alcune volte per \* trovarlo.</span><span class="sxs-lookup"><span data-stu-id="4481d-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="4481d-113">Dopo aver creato il nome, eseguire "$package 1 = Get-AppxPackage -name Actual.PackageName"</span><span class="sxs-lookup"><span data-stu-id="4481d-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="4481d-114">Ad esempio, l'esecuzione di quanto segue per Microsoft Edge restituirà più di un risultato, ma da tale elenco è possibile identificare che il nome completo necessario è Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="4481d-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="4481d-115">Nomi delle famiglie di pacchetti per le app HoloLens</span><span class="sxs-lookup"><span data-stu-id="4481d-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="4481d-116">Nella guida collegata in precedenza è possibile modificare manualmente newPolicy.xml e aggiungere regole per le applicazioni installate solo in HoloLens con i relativi nomi di famiglia di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="4481d-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="4481d-117">In alcuni casi è possibile usare app che non sono presenti nel PC desktop che si vuole aggiungere ai criteri.</span><span class="sxs-lookup"><span data-stu-id="4481d-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="4481d-118">Di seguito è riportato un elenco di app di uso In-Box per HoloLens 2 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4481d-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="4481d-119">Nome dell'app</span><span class="sxs-lookup"><span data-stu-id="4481d-119">App Name</span></span>                   | <span data-ttu-id="4481d-120">Nome famiglia pacchetto</span><span class="sxs-lookup"><span data-stu-id="4481d-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="4481d-121">Visualizzatore 3D</span><span class="sxs-lookup"><span data-stu-id="4481d-121">3D Viewer</span></span>                  | <span data-ttu-id="4481d-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="4481d-123">Programma di installazione app</span><span class="sxs-lookup"><span data-stu-id="4481d-123">App Installer</span></span>              | <span data-ttu-id="4481d-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4481d-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="4481d-125">Calendario</span><span class="sxs-lookup"><span data-stu-id="4481d-125">Calendar</span></span>                   | <span data-ttu-id="4481d-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="4481d-127">Fotocamera</span><span class="sxs-lookup"><span data-stu-id="4481d-127">Camera</span></span>                     | <span data-ttu-id="4481d-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="4481d-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="4481d-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="4481d-129">Cortana</span></span>                    | <span data-ttu-id="4481d-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="4481d-131">Guide di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4481d-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="4481d-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="4481d-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="4481d-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="4481d-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="4481d-135">Hub di Feedback</span><span class="sxs-lookup"><span data-stu-id="4481d-135">Feedback Hub</span></span>               | <span data-ttu-id="4481d-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="4481d-137">Esplora file</span><span class="sxs-lookup"><span data-stu-id="4481d-137">File Explorer</span></span>              | <span data-ttu-id="4481d-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="4481d-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="4481d-139">Posta</span><span class="sxs-lookup"><span data-stu-id="4481d-139">Mail</span></span>                       | <span data-ttu-id="4481d-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="4481d-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="4481d-141">Microsoft Store</span></span>            | <span data-ttu-id="4481d-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="4481d-143">Film e TV</span><span class="sxs-lookup"><span data-stu-id="4481d-143">Movies & TV</span></span>                | <span data-ttu-id="4481d-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="4481d-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4481d-145">OneDrive</span></span>                   | <span data-ttu-id="4481d-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="4481d-147">Foto</span><span class="sxs-lookup"><span data-stu-id="4481d-147">Photos</span></span>                     | <span data-ttu-id="4481d-148">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="4481d-149">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="4481d-149">Settings</span></span>                   | <span data-ttu-id="4481d-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="4481d-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="4481d-151">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="4481d-151">Tips</span></span>                       | <span data-ttu-id="4481d-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="4481d-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="4481d-153">1 - Il Programma di installazione app blocca solo l'app Programma di installazione app e non le app installate da altre origini, ad esempio il Microsoft Store o dalla soluzione MDM.</span><span class="sxs-lookup"><span data-stu-id="4481d-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="4481d-154">Come trovare un nome di famiglia di pacchetti</span><span class="sxs-lookup"><span data-stu-id="4481d-154">How to find a Package Family Name</span></span>

<span data-ttu-id="4481d-155">Se un'app non è in questo elenco, un utente può usare Portale di dispositivi, connesso a un HoloLens 2 che ha installato l'app che si vuole bloccare, per determinare PackageRelativeID e da qui ottenere PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="4481d-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="4481d-156">Installare l'app nel HoloLens 2 dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4481d-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="4481d-157">Aprire Impostazioni -> Aggiornamenti & Sicurezza -> Per gli sviluppatori, abilitare modalità  sviluppatore e quindi **Portale di dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="4481d-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="4481d-158">Altre istruzioni dettagliate per altre informazioni sulla configurazione [e l'uso del portale per dispositivi sono disponibili qui.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="4481d-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="4481d-159">Dopo Portale di dispositivi connesso, passare a **Visualizzazioni e** quindi **ad App.**</span><span class="sxs-lookup"><span data-stu-id="4481d-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="4481d-160">Nel pannello App installate usare l'elenco a discesa per selezionare l'app installata.</span><span class="sxs-lookup"><span data-stu-id="4481d-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="4481d-161">Individuare PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="4481d-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="4481d-162">Copiare i caratteri dell'app prima di ! . Questi caratteri saranno packageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="4481d-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


