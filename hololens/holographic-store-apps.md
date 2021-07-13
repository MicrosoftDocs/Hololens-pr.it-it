---
title: Trovare, installare e disinstallare applicazioni
description: Il Microsoft Store è l'origine per app e giochi che funzionano con HoloLens.  Altre informazioni su come trovare, installare e disinstallare le app olografiche.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, store, uwp, app, installare
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: bbbc60decb74942bd7930afb04297f78df33028a
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635858"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="41d59-105">Trovare, installare e disinstallare applicazioni dal Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="41d59-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="41d59-106">Il Microsoft Store è l'origine per le app e i giochi che funzionano con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="41d59-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="41d59-107">Quando si passa a Store nel HoloLens, tutte le app presenti verranno eseguite in esso.</span><span class="sxs-lookup"><span data-stu-id="41d59-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="41d59-108">Le app HoloLens usano la visualizzazione 2D o la visualizzazione olografica.</span><span class="sxs-lookup"><span data-stu-id="41d59-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="41d59-109">Le app che usano la visualizzazione 2D sono simili a finestre e possono essere posizionate attorno all'utente.</span><span class="sxs-lookup"><span data-stu-id="41d59-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="41d59-110">Le app che usano la visualizzazione olografica ti circondano e diventano l'unica app visualizzata.</span><span class="sxs-lookup"><span data-stu-id="41d59-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="41d59-111">HoloLens supporta molte applicazioni esistenti del Microsoft Store e nuove app create specificamente per HoloLens.</span><span class="sxs-lookup"><span data-stu-id="41d59-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="41d59-112">Questo articolo è in particolare sulle applicazioni olografiche del Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="41d59-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="41d59-113">Per altre informazioni sull'installazione e l'esecuzione di app personalizzate, vedere [Applicazioni olografiche personalizzate.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="41d59-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="41d59-114">Trovare app</span><span class="sxs-lookup"><span data-stu-id="41d59-114">Find apps</span></span>

<span data-ttu-id="41d59-115">Aprire il Microsoft Store dal menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="41d59-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="41d59-116">Cercare quindi app e giochi.</span><span class="sxs-lookup"><span data-stu-id="41d59-116">Then browse for apps and games.</span></span> <span data-ttu-id="41d59-117">È possibile usare [i comandi](hololens-cortana.md) vocali per eseguire la ricerca pronunciando "Cerca", una volta aperta la finestra di ricerca, pronunciare "Inizia a dettare" e quindi, quando richiesto, iniziare a pronunciare i termini di ricerca.</span><span class="sxs-lookup"><span data-stu-id="41d59-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="41d59-118">I requisiti di sistema per HoloLens dispositivi sono basati sull'architettura della compilazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="41d59-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="41d59-119">Se una build di app per HoloLens (prima generazione) non è stata aggiornata con a una nuova UWP nello Store per includere il pacchetto dell'architettura ARM, non sarà disponibile per i dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="41d59-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="41d59-120">Analogamente, se un'app HoloLens 2 non include il pacchetto di architettura x86, non sarà disponibile per i dispositivi HoloLens (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="41d59-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="41d59-121">HoloLens architetture dei dispositivi:</span><span class="sxs-lookup"><span data-stu-id="41d59-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="41d59-122">x86 = HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="41d59-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="41d59-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="41d59-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="41d59-124">Il 12 gennaio 2021 le app seguenti raggiungeranno la fine del supporto HoloLens dispositivi.</span><span class="sxs-lookup"><span data-stu-id="41d59-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="41d59-125">Si consiglia di usare il collegamento seguente nel dispositivo per usare la versione Web dell'app.</span><span class="sxs-lookup"><span data-stu-id="41d59-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="41d59-126">App</span><span class="sxs-lookup"><span data-stu-id="41d59-126">App</span></span>        | <span data-ttu-id="41d59-127">Collegamento</span><span class="sxs-lookup"><span data-stu-id="41d59-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="41d59-128">Excel per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="41d59-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="41d59-129">Word mobile</span><span class="sxs-lookup"><span data-stu-id="41d59-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="41d59-130">PowerPoint mobile</span><span class="sxs-lookup"><span data-stu-id="41d59-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="41d59-131">Installare app</span><span class="sxs-lookup"><span data-stu-id="41d59-131">Install apps</span></span>

<span data-ttu-id="41d59-132">Per scaricare le app, è necessario accedere con un account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="41d59-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="41d59-133">Alcune app sono gratuite e possono essere scaricate immediatamente.</span><span class="sxs-lookup"><span data-stu-id="41d59-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="41d59-134">Per le app che richiedono un acquisto, è necessario accedere a Store con il proprio account Microsoft e avere un metodo di pagamento valido.</span><span class="sxs-lookup"><span data-stu-id="41d59-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="41d59-135">L'account che si Microsoft Store non deve essere uguale all'account con cui è stato eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="41d59-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="41d59-136">Se si usa un account aziendale o dell'istituto di istruzione nel HoloLens potrebbe essere necessario accedere con l'account personale nell'app dello Store per effettuare un acquisto.</span><span class="sxs-lookup"><span data-stu-id="41d59-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="41d59-137">Per configurare un metodo di pagamento, passare a Account.microsoft.com e [selezionare](https://account.microsoft.com/) Opzioni di pagamento & **pagamento**  >    >  **Aggiungi un'opzione di pagamento.**</span><span class="sxs-lookup"><span data-stu-id="41d59-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="41d59-138">Per aprire il menu [ **Start**](holographic-home.md), eseguire un [movimento Start](/hololens/hololens2-basic-usage#start-gesture) o un movimento [di HoloLens](hololens1-basic-usage.md) (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="41d59-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="41d59-139">Selezionare l Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="41d59-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="41d59-140">Dopo l'apertura dell'app dello Store:</span><span class="sxs-lookup"><span data-stu-id="41d59-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="41d59-141">Usare la barra di ricerca per cercare le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="41d59-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="41d59-142">Selezionare le app essenziali o le app appositamente HoloLens da una delle categorie curate.</span><span class="sxs-lookup"><span data-stu-id="41d59-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="41d59-143">In alto a destra nell'app Dello Store selezionare il pulsante **"..."** e quindi selezionare **Libreria** per visualizzare le app acquistate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="41d59-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="41d59-144">Selezionare **Scarica** o **Installa** nella pagina dell'applicazione (potrebbe essere necessario un acquisto).</span><span class="sxs-lookup"><span data-stu-id="41d59-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="41d59-145">Aggiornare le app</span><span class="sxs-lookup"><span data-stu-id="41d59-145">Update Apps</span></span>

<span data-ttu-id="41d59-146">Per aggiornare un'app installata dal Microsoft Store, è possibile aggiornare l'app dalla Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="41d59-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="41d59-147">Per le app installate per Microsoft Store per le aziende, è anche possibile aggiornare tali app dal Microsoft Store per le aziende.</span><span class="sxs-lookup"><span data-stu-id="41d59-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="41d59-148">Per aprire il menu [ **Start**](holographic-home.md), eseguire un [movimento Start](/hololens/hololens2-basic-usage#start-gesture) o un movimento [di HoloLens](hololens1-basic-usage.md) (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="41d59-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="41d59-149">Selezionare l'app dello Store.</span><span class="sxs-lookup"><span data-stu-id="41d59-149">Select the Store app.</span></span>

1. <span data-ttu-id="41d59-150">Esaminare l'angolo in alto a destra dell'app Dello Store.</span><span class="sxs-lookup"><span data-stu-id="41d59-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="41d59-151">Selezionare il **pulsante "..."** o "Vedi altro".</span><span class="sxs-lookup"><span data-stu-id="41d59-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41d59-152">![Microsoft Store screenshot dell'app.](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="41d59-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="41d59-153">Selezionare **Download e aggiornamenti.**</span><span class="sxs-lookup"><span data-stu-id="41d59-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="41d59-154">Se il dispositivo ha identificato in precedenza gli aggiornamenti, potrebbero essere presenti una freccia rivolta verso il basso e un numero che rappresenta gli aggiornamenti in sospeso.</span><span class="sxs-lookup"><span data-stu-id="41d59-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="41d59-155">Selezionare **Ottieni aggiornamenti.**</span><span class="sxs-lookup"><span data-stu-id="41d59-155">Select **Get updates**.</span></span> <span data-ttu-id="41d59-156">Il dispositivo ora cerca gli aggiornamenti e li imposta per il download e l'installazione.</span><span class="sxs-lookup"><span data-stu-id="41d59-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41d59-157">![Microsoft Store screenshot dell'app per ottenere gli aggiornamenti.](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="41d59-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="41d59-158">Se le app nel dispositivo sono state distribuite dall'organizzazione, possono essere aggiornate tramite gli stessi metodi di gestione delle app commerciali.</span><span class="sxs-lookup"><span data-stu-id="41d59-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="41d59-159">Se questo vale per la situazione specifica, leggere altre informazioni nella panoramica [della distribuzione di app commerciali.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="41d59-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="41d59-160">Se si vuole aggiornare un'app personalizzata che è stata sideloaded o distribuita, è necessario usare lo stesso metodo con la versione aggiornata dell'app.</span><span class="sxs-lookup"><span data-stu-id="41d59-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="41d59-161">Per altre informazioni sull'installazione e l'esecuzione di app personalizzate, vedere [Applicazioni olografiche personalizzate.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="41d59-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="41d59-162">Disinstallazione di app</span><span class="sxs-lookup"><span data-stu-id="41d59-162">Uninstall apps</span></span>

<span data-ttu-id="41d59-163">Esistono tre modi per disinstallare le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="41d59-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="41d59-164">È possibile disinstallare le applicazioni tramite Microsoft Store, menu Start o da Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="41d59-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="41d59-165">Non è possibile disinstallare un'app di sistema o il Microsoft Store stesso.</span><span class="sxs-lookup"><span data-stu-id="41d59-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41d59-166">Se il HoloLens 2 ha più utenti, è necessario essere connessi come utente che ha installato l'app per disinstallarla.</span><span class="sxs-lookup"><span data-stu-id="41d59-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="41d59-167">Disinstallare dal Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="41d59-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="41d59-168">Aprire il Microsoft Store dal menu **Start** e quindi cercare l'applicazione da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="41d59-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="41d59-169">Nella pagina Store ogni applicazione installata ha un **pulsante Disinstalla.**</span><span class="sxs-lookup"><span data-stu-id="41d59-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="41d59-170">Eseguire la disinstallazione dal menu Start</span><span class="sxs-lookup"><span data-stu-id="41d59-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="41d59-171">Passare all'app nel menu **Start** o nell'elenco **All apps**.</span><span class="sxs-lookup"><span data-stu-id="41d59-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="41d59-172">Selezionare e tenere premuto fino a quando non viene visualizzato il menu, quindi selezionare **Uninstall**.</span><span class="sxs-lookup"><span data-stu-id="41d59-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="41d59-173">Eseguire la disinstallazione dalle impostazioni</span><span class="sxs-lookup"><span data-stu-id="41d59-173">Uninstall from Settings</span></span>
<span data-ttu-id="41d59-174">Nel menu **Start** selezionare Impostazioni **-> App.**</span><span class="sxs-lookup"><span data-stu-id="41d59-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="41d59-175">Trovare l'app nell'elenco, selezionarla e quindi fare clic su **Uninstall**.</span><span class="sxs-lookup"><span data-stu-id="41d59-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="41d59-176">Se non è possibile disinstallare un'app, inviare [commenti e suggerimenti](/hololens/hololens-feedback) usando il Hub di Feedback.</span><span class="sxs-lookup"><span data-stu-id="41d59-176">If you are unable to uninstall an app, please file [feedback](/hololens/hololens-feedback) using the Feedback Hub.</span></span>
