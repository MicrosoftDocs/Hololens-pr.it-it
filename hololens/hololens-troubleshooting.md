---
title: Risoluzione dei problemi
description: Soluzioni per problemi di HoloLens comuni.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: problemi, bug, risoluzione dei problemi, correzione, guida, supporto, HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 15998fe11de1e7be4f12087a2724bec7e22337b0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857744"
---
# <span data-ttu-id="2c255-104">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="2c255-104">Troubleshooting</span></span>

<span data-ttu-id="2c255-105">Questo articolo descrive come risolvere diversi problemi di HoloLens comuni.</span><span class="sxs-lookup"><span data-stu-id="2c255-105">This article describes how to resolve several common HoloLens issues.</span></span>

## <span data-ttu-id="2c255-106">Il mio HoloLens non risponde o non si avvia</span><span class="sxs-lookup"><span data-stu-id="2c255-106">My HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="2c255-107">Se il HoloLens non si avvia:</span><span class="sxs-lookup"><span data-stu-id="2c255-107">If your HoloLens won't start:</span></span>

- <span data-ttu-id="2c255-108">Se i LED accanto al pulsante di alimentazione non si accendono o un solo LED lampeggia brevemente, potrebbe essere necessario [caricare il HoloLens.](hololens-recovery.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="2c255-108">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens-recovery.md#charging-the-device)</span></span>
- <span data-ttu-id="2c255-109">Se i LED si accendono quando si preme il pulsante di alimentazione, ma non si riesce a vedere nulla sugli schermi, [preformare un ripristino rigido del dispositivo](hololens-recovery.md#hard-reset-procedure).</span><span class="sxs-lookup"><span data-stu-id="2c255-109">If the LEDs light up when you press the power button but you can't see anything on the displays, [preform a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="2c255-110">Se il HoloLens diventa bloccato o non risponde:</span><span class="sxs-lookup"><span data-stu-id="2c255-110">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="2c255-111">Disattivare il HoloLens premendo il pulsante di alimentazione finché tutti e cinque i LED non si spengono o per 15 secondi se i LED non rispondono.</span><span class="sxs-lookup"><span data-stu-id="2c255-111">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="2c255-112">Per avviare il HoloLens, premere di nuovo il pulsante di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="2c255-112">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="2c255-113">Se questa procedura non funziona, è possibile provare a [recuperare il dispositivo HoloLens 2](hololens-recovery.md) o [HoloLens (1a Gen).](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="2c255-113">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

## <span data-ttu-id="2c255-114">Gli ologrammi non hanno un bell'aspetto</span><span class="sxs-lookup"><span data-stu-id="2c255-114">Holograms don't look good</span></span>

<span data-ttu-id="2c255-115">Se gli ologrammi sono instabili, nervosi o non hanno un aspetto corretto, provare a:</span><span class="sxs-lookup"><span data-stu-id="2c255-115">If your holograms are unstable, jumpy, or don't look right, try:</span></span>

- <span data-ttu-id="2c255-116">Pulizia della visiera del dispositivo e della barra del sensore nella parte anteriore della HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2c255-116">Cleaning your device visor and sensor bar on the front of your HoloLens.</span></span>
- <span data-ttu-id="2c255-117">Aumentare la luce in camera.</span><span class="sxs-lookup"><span data-stu-id="2c255-117">Increasing the light in your room.</span></span>
- <span data-ttu-id="2c255-118">Spostarsi e osservare l'ambiente circostante in modo che HoloLens possa analizzarli più completamente.</span><span class="sxs-lookup"><span data-stu-id="2c255-118">Walking around and looking at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="2c255-119">Calibrazione della HoloLens per gli occhi.</span><span class="sxs-lookup"><span data-stu-id="2c255-119">Calibrating your HoloLens for your eyes.</span></span> <span data-ttu-id="2c255-120">Accedere alle utilità di sistema **delle impostazioni**  >  **System**  >  **Utilities**.</span><span class="sxs-lookup"><span data-stu-id="2c255-120">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="2c255-121">In **Calibrazione**, selezionare **Apri Calibrazione**.</span><span class="sxs-lookup"><span data-stu-id="2c255-121">Under **Calibration**, select **Open Calibration**.</span></span>

## <span data-ttu-id="2c255-122">HoloLens non risponde ai movimenti</span><span class="sxs-lookup"><span data-stu-id="2c255-122">HoloLens doesn't respond to gestures</span></span>

<span data-ttu-id="2c255-123">Per assicurarsi che HoloLens possa visualizzare i movimenti.</span><span class="sxs-lookup"><span data-stu-id="2c255-123">To make sure that HoloLens can see your gestures.</span></span>  <span data-ttu-id="2c255-124">Tieni la mano nel riquadro gestuale: quando HoloLens può vedere la tua mano, il cursore cambia da un punto a un anello.</span><span class="sxs-lookup"><span data-stu-id="2c255-124">Keep your hand in the gesture frame - when HoloLens can see your hand, the cursor changes from a dot to a ring.</span></span>

<span data-ttu-id="2c255-125">Altre informazioni sull'uso dei movimenti in [HoloLens (1a generazione)](hololens1-basic-usage.md#use-hololens-with-your-hands) o [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span><span class="sxs-lookup"><span data-stu-id="2c255-125">Learn more about using gestures on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) or [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="2c255-126">Se l'ambiente è troppo scuro, HoloLens potrebbe non vedere la mano, quindi verificare che ci sia abbastanza luce.</span><span class="sxs-lookup"><span data-stu-id="2c255-126">If your environment is too dark, HoloLens might not see your hand, so make sure that there's enough light.</span></span>

<span data-ttu-id="2c255-127">Se la visiera ha impronte digitali o macchie, usare il panno in microfibra fornito con il HoloLens per pulire delicatamente la visiera.</span><span class="sxs-lookup"><span data-stu-id="2c255-127">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

## <span data-ttu-id="2c255-128">HoloLens non risponde ai comandi vocali</span><span class="sxs-lookup"><span data-stu-id="2c255-128">HoloLens doesn't respond to my voice commands</span></span>

<span data-ttu-id="2c255-129">Se Cortana non risponde ai comandi vocali, verificare che Cortana sia attivato.</span><span class="sxs-lookup"><span data-stu-id="2c255-129">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="2c255-130">Nell'elenco tutte le app selezionare impostazioni del **Cortana**  >  **Menu**  >  **blocco appunti**del menu Cortana  >  **Settings** per apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="2c255-130">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="2c255-131">Per ulteriori informazioni sulle frasi che è possibile pronunciare, vedere [Usare la voce con HoloLens](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="2c255-131">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

## <span data-ttu-id="2c255-132">Non è possibile collocare gli ologrammi o vedere gli ologrammi precedentemente inseriti</span><span class="sxs-lookup"><span data-stu-id="2c255-132">I can't place holograms or see holograms that I previously placed</span></span>

<span data-ttu-id="2c255-133">Se HoloLens non riesce a mappare o caricare lo spazio, entra in modalità limitata e non sarà possibile inserire gli ologrammi o vedere gli ologrammi inseriti.</span><span class="sxs-lookup"><span data-stu-id="2c255-133">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="2c255-134">Ecco alcune soluzioni possibili:</span><span class="sxs-lookup"><span data-stu-id="2c255-134">Here are some things to try:</span></span>

- <span data-ttu-id="2c255-135">Assicurarsi che nell'ambiente sia presente abbastanza luce in modo che HoloLens possa visualizzare e mappare lo spazio.</span><span class="sxs-lookup"><span data-stu-id="2c255-135">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="2c255-136">Assicurarsi di essere connessi a una rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="2c255-136">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="2c255-137">Se non si è connessi a una rete Wi-Fi, HoloLens non riesce a identificare e caricare uno spazio noto.</span><span class="sxs-lookup"><span data-stu-id="2c255-137">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="2c255-138">Se è necessario creare un nuovo spazio, connettersi a Wi-Fi e quindi riavviare il HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2c255-138">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="2c255-139">Per verificare se lo spazio corretto è attivo o per caricare manualmente uno spazio, passa a spazi del sistema di **Impostazioni**  >  **System**  >  **Spaces**.</span><span class="sxs-lookup"><span data-stu-id="2c255-139">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="2c255-140">Se viene caricato lo spazio corretto e si verificano ancora problemi, lo spazio potrebbe essere danneggiato.</span><span class="sxs-lookup"><span data-stu-id="2c255-140">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="2c255-141">Per risolvere il problema, selezionare lo spazio e quindi scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2c255-141">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="2c255-142">Dopo aver rimosso lo spazio, HoloLens inizia a mappare l'ambiente circostante e a creare un nuovo spazio.</span><span class="sxs-lookup"><span data-stu-id="2c255-142">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

## <span data-ttu-id="2c255-143">Il mio HoloLens non può dire in quale spazio mi trovo</span><span class="sxs-lookup"><span data-stu-id="2c255-143">My HoloLens can't tell what space I'm in</span></span>

<span data-ttu-id="2c255-144">Se il HoloLens non riesce a identificare e caricare lo spazio in cui ci si trova automaticamente, verificare i fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c255-144">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="2c255-145">Verificare di essere connessi a una rete Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="2c255-145">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="2c255-146">Verificare che nella sala sia presente molta luce</span><span class="sxs-lookup"><span data-stu-id="2c255-146">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="2c255-147">Verificare che non siano state apportate modifiche importanti all'ambiente circostante.</span><span class="sxs-lookup"><span data-stu-id="2c255-147">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="2c255-148">È anche possibile caricare uno spazio manualmente o gestire gli spazi passando agli spazi di sistema **delle impostazioni**  >  **System**  >  **Spaces**.</span><span class="sxs-lookup"><span data-stu-id="2c255-148">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

## <span data-ttu-id="2c255-149">Viene visualizzato un errore di "spazio su disco ridotto"</span><span class="sxs-lookup"><span data-stu-id="2c255-149">I'm getting a "low disk space" error</span></span>

<span data-ttu-id="2c255-150">È necessario liberare spazio di archiviazione eseguendo una o più delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c255-150">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="2c255-151">Eliminare alcuni spazi inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="2c255-151">Delete some unused spaces.</span></span> <span data-ttu-id="2c255-152">Accedere a spazi del sistema **Impostazioni**  >  **System**  >  **Spaces**, selezionare uno spazio non più necessario e quindi scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2c255-152">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="2c255-153">Rimuovere alcuni degli ologrammi posizionati.</span><span class="sxs-lookup"><span data-stu-id="2c255-153">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="2c255-154">Eliminare alcune immagini e video dall'app foto.</span><span class="sxs-lookup"><span data-stu-id="2c255-154">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="2c255-155">Disinstallare alcune app da HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2c255-155">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="2c255-156">Nell'elenco **tutte le app** toccare e tenere premuta l'app che si vuole disinstallare, quindi selezionare **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="2c255-156">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

## <span data-ttu-id="2c255-157">Il mio HoloLens non riesce a creare un nuovo spazio</span><span class="sxs-lookup"><span data-stu-id="2c255-157">My HoloLens can't create a new space</span></span>

<span data-ttu-id="2c255-158">Il problema più probabile è che si sta esaurendo lo spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2c255-158">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="2c255-159">Provare uno dei [suggerimenti precedenti](#im-getting-a-low-disk-space-error) per liberare spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="2c255-159">Try one of the [previous tips](#im-getting-a-low-disk-space-error) to free up some disk space.</span></span>

## <span data-ttu-id="2c255-160">L'emulatore HoloLens non funziona</span><span class="sxs-lookup"><span data-stu-id="2c255-160">The HoloLens emulator isn't working</span></span>

<span data-ttu-id="2c255-161">Le informazioni sull'emulatore HoloLens si trovano nella documentazione per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="2c255-161">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="2c255-162">Per altre informazioni, vedere [risoluzione dei problemi relativi all'emulatore HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="2c255-162">Read more about [troubleshooting the HoloLens emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>
