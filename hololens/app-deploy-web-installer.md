---
title: Come installare le app tramite Web Installer
description: Installare app tramite Web Installer per il programma di installazione di app
keywords: gestione app, app, hololens, app Installer, installazione Web
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027473"
---
# <span data-ttu-id="25abb-104">Installazione di app da una pagina Web</span><span class="sxs-lookup"><span data-stu-id="25abb-104">Installing apps from a web page</span></span>

<span data-ttu-id="25abb-105">Gli utenti possono installare un'app direttamente da un server Web.</span><span class="sxs-lookup"><span data-stu-id="25abb-105">Users can install an app directly from a web server.</span></span> <span data-ttu-id="25abb-106">In questo modo si usa il programma di installazione dell'app in combinazione con un metodo di distribuzione facile da scaricare e installare.</span><span class="sxs-lookup"><span data-stu-id="25abb-106">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="25abb-107">Questa caratteristica è attualmente solo avalible in Windows Insider Build 19041.1366 +.</span><span class="sxs-lookup"><span data-stu-id="25abb-107">This feature is currently only avalible in Windows Insider builds 19041.1366+.</span></span> <span data-ttu-id="25abb-108">[Altre informazioni su come iscriversi alle build di Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="25abb-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

## <span data-ttu-id="25abb-109">Come configurarlo:</span><span class="sxs-lookup"><span data-stu-id="25abb-109">How to set this up:</span></span>
1.  <span data-ttu-id="25abb-110">Verificare che l'app sia configurata correttamente per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="25abb-110">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="25abb-111">Seguire [questa procedura per abilitare questa operazione in una pagina Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="25abb-111">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 
1.  <span data-ttu-id="25abb-112">Selezionare un metodo di distribuzione del certificato.</span><span class="sxs-lookup"><span data-stu-id="25abb-112">Pick a certificate deployment method.</span></span> 
    1.  <span data-ttu-id="25abb-113">I [pacchetti di provisioning](hololens-provisioning.md) possono essere applicati ai dispositivi locali.</span><span class="sxs-lookup"><span data-stu-id="25abb-113">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
    1.  <span data-ttu-id="25abb-114">MDM può essere usato per [applicare certificati con configurazioni di dispositivi](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="25abb-114">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
    1.  <span data-ttu-id="25abb-115">Usare il [gestore certificati](hololens-insider.md#certificate-manager)per dispositivi.</span><span class="sxs-lookup"><span data-stu-id="25abb-115">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="25abb-116">Esperienza utente finale:</span><span class="sxs-lookup"><span data-stu-id="25abb-116">End User Experience:</span></span>
1.  <span data-ttu-id="25abb-117">L'utente riceve e installa il certificato nel dispositivo usando un metodo precedentemente selezionato.</span><span class="sxs-lookup"><span data-stu-id="25abb-117">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1.  <span data-ttu-id="25abb-118">L'utente visita l'URL creato dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="25abb-118">User visits the URL created from the step above.</span></span>

<span data-ttu-id="25abb-119">L'app verrà ora installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25abb-119">The app will now install to the device.</span></span> <span data-ttu-id="25abb-120">Per trovare l'app, Apri il **menu Start** e seleziona il pulsante **tutte** le app per trovare la tua app.</span><span class="sxs-lookup"><span data-stu-id="25abb-120">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="25abb-121">Per informazioni sulla risoluzione dei problemi di questo metodo di installazione, vedere [risoluzione di errori di installazione dell'app](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span><span class="sxs-lookup"><span data-stu-id="25abb-121">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="25abb-122">L'interfaccia utente durante il processo di aggiornamento non è supportata.</span><span class="sxs-lookup"><span data-stu-id="25abb-122">UI during the update process is not supported.</span></span> <span data-ttu-id="25abb-123">Quindi l'opzione ShowPrompt in [Questa pagina](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e le opzioni correlate non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="25abb-123">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>
