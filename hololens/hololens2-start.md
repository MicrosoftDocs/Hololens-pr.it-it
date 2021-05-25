---
title: Configurare la HoloLens 2
description: Informazioni su come configurare il HoloLens 2 per la prima volta Wi-Fi rete con un account Microsoft (MSA) o Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: d46deaf4048e6a649345dc1676a7f8b94d3ad2fc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397572"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="f28d1-104">Configurare la HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f28d1-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="f28d1-105">La prima volta che si attiva HoloLens, si verrà guidati nella configurazione del dispositivo, nell'accesso con un account utente e nella calibrazione di HoloLens agli occhi.</span><span class="sxs-lookup"><span data-stu-id="f28d1-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="f28d1-106">In questa sezione viene illustrata l'HoloLens 2 di configurazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="f28d1-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="f28d1-107">Nella sezione successiva si apprenderà come usare HoloLens e interagire con gli ologrammi.</span><span class="sxs-lookup"><span data-stu-id="f28d1-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="f28d1-108">Per passare a questo articolo, vedere [Introduzione a HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="f28d1-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="f28d1-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f28d1-109">Before you start</span></span>

<span data-ttu-id="f28d1-110">Prima di iniziare, assicurarsi di avere a disposizione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f28d1-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="f28d1-111">**Una connessione di rete**.</span><span class="sxs-lookup"><span data-stu-id="f28d1-111">**A network connection**.</span></span> <span data-ttu-id="f28d1-112">Per configurarlo, è necessario connettere HoloLens a una rete.</span><span class="sxs-lookup"><span data-stu-id="f28d1-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="f28d1-113">Con HoloLens 2, è possibile connettersi con Wi-Fi o usando ethernet (è necessaria una scheda USB-C-to-Ethernet).</span><span class="sxs-lookup"><span data-stu-id="f28d1-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="f28d1-114">La prima volta che ci si connette, sarà necessaria una rete aperta o protetta da password che non richieda l'accesso a un sito Web o l'uso di certificati per la connessione.</span><span class="sxs-lookup"><span data-stu-id="f28d1-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="f28d1-115">[Altre informazioni sui siti Web che HoloLens usa.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="f28d1-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="f28d1-116">**Oggetto account Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f28d1-116">**A Microsoft account**.</span></span> <span data-ttu-id="f28d1-117">È anche necessario accedere a HoloLens con un account Microsoft (o con l'account aziendale, se l'organizzazione è proprietaria del dispositivo).</span><span class="sxs-lookup"><span data-stu-id="f28d1-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="f28d1-118">Se non si ha una account Microsoft, passare a account.microsoft.com [e](https://account.microsoft.com) configurarne una gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="f28d1-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="f28d1-119">**Uno spazio sicuro e ben illuminato senza rischi di inciampo.**</span><span class="sxs-lookup"><span data-stu-id="f28d1-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="f28d1-120">[Informazioni su integrità e sicurezza.](https://go.microsoft.com/fwlink/p/?LinkId=746661)</span><span class="sxs-lookup"><span data-stu-id="f28d1-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="f28d1-121">**Gli accessori di comfort facoltativi** in dotazione con HoloLens, che consentono di ottenere la scelta più comoda.</span><span class="sxs-lookup"><span data-stu-id="f28d1-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="f28d1-122">[Altre informazioni su fit e comfort.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="f28d1-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="f28d1-123">Configurazione di Windows</span><span class="sxs-lookup"><span data-stu-id="f28d1-123">Set up Windows</span></span>

<span data-ttu-id="f28d1-124">La prima volta che si avvia HoloLens 2, la prima attività è la configurazione di Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="f28d1-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="f28d1-125">Quando avvia HoloLens, ascolti musica e vedi un logo di Windows.</span><span class="sxs-lookup"><span data-stu-id="f28d1-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Prima schermata durante il primo avvio](images/01-magic-moment.png)

<span data-ttu-id="f28d1-127">HoloLens 2 verranno descritti i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f28d1-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="f28d1-128">Selezionare la lingua.</span><span class="sxs-lookup"><span data-stu-id="f28d1-128">Select your language.</span></span>

    ![Seleziona lingua](images/04-language.png)

1. <span data-ttu-id="f28d1-130">Selezionare un'area.</span><span class="sxs-lookup"><span data-stu-id="f28d1-130">Select your region.</span></span>

    ![Selezionare l'area](images/05-region.png)

1. <span data-ttu-id="f28d1-132">Calibrare HoloLens agli occhi.</span><span class="sxs-lookup"><span data-stu-id="f28d1-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="f28d1-133">Se si sceglie di ignorare la calibrazione, verrà richiesto al successivo accesso.</span><span class="sxs-lookup"><span data-stu-id="f28d1-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="f28d1-134">Per calibrare, si animerà un set di destinazioni (denominate gemme).</span><span class="sxs-lookup"><span data-stu-id="f28d1-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="f28d1-135">È possibile lampeggiare o chiudere gli occhi durante la calibrazione, ma provare a non guardare altri oggetti nella stanza o nello spazio fisico.</span><span class="sxs-lookup"><span data-stu-id="f28d1-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="f28d1-136">HoloLens usa questo processo per ottenere informazioni sulla posizione dell'occhio, in modo da migliorare il rendering del mondo olografico.</span><span class="sxs-lookup"><span data-stu-id="f28d1-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="f28d1-137">Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando il visore si sposta sulla testa.</span><span class="sxs-lookup"><span data-stu-id="f28d1-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="f28d1-138">Le informazioni di calibrazione vengono archiviate localmente nel dispositivo e non sono associate ad alcuna informazione sull'account.</span><span class="sxs-lookup"><span data-stu-id="f28d1-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="f28d1-139">Per altre informazioni, vedere [Calibrazione dei dati e sicurezza.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="f28d1-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![Schermata di selezione della calibrazione](images/06-et-corners.png)

1. <span data-ttu-id="f28d1-141">Connettersi a Internet (selezionare Wi-Fi o la connessione ethernet.</span><span class="sxs-lookup"><span data-stu-id="f28d1-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="f28d1-142">HoloLens imposta automaticamente il fuso orario in base alle informazioni ottenute dalla Wi-Fi rete.</span><span class="sxs-lookup"><span data-stu-id="f28d1-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="f28d1-143">Al termine dell'installazione, è possibile modificare il fuso orario usando l'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f28d1-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Connettersi alla rete Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="f28d1-145">Se si procede oltre il passaggio Wi-Fi e successivamente è necessario passare a una rete diversa  durante la configurazione, è possibile premere i pulsanti **Volume** in basso e Alimentazione contemporaneamente per tornare a questo passaggio se si esegue una versione del sistema operativo da ottobre 2019 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f28d1-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="f28d1-146">Per le versioni precedenti, [](hololens-recovery.md) potrebbe essere necessario reimpostare il dispositivo o riavviarlo in una posizione in cui la rete Wi-Fi non è disponibile per impedirne la connessione automatica.</span><span class="sxs-lookup"><span data-stu-id="f28d1-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="f28d1-147">Si noti anche che durante l'installazione di HoloLens si verifica un timeout delle credenziali di due minuti.</span><span class="sxs-lookup"><span data-stu-id="f28d1-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="f28d1-148">Il nome utente/password deve essere immesso entro due minuti; in caso contrario, il campo del nome utente verrà cancellato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f28d1-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="f28d1-149">Accedere al proprio account utente.</span><span class="sxs-lookup"><span data-stu-id="f28d1-149">Sign in to your user account.</span></span> <span data-ttu-id="f28d1-150">Si sceglierà tra **Il mio lavoro o l'istituto di** istruzione è proprietario e io lo **sono.**</span><span class="sxs-lookup"><span data-stu-id="f28d1-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="f28d1-151">Quando si sceglie **Appartiene all'azienda o all'istituto di istruzione**, si esegue l'accesso con un account Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f28d1-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="f28d1-152">Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione MDM automatica, HoloLens si registra automaticamente in MDM.</span><span class="sxs-lookup"><span data-stu-id="f28d1-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="f28d1-153">Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="f28d1-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="f28d1-154">In tal caso, è necessario registrare [manualmente HoloLens nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="f28d1-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="f28d1-155">Immettere le informazioni sull'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="f28d1-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="f28d1-156">Accettare l'informativa sulla privacy e il contratto di licenza con l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="f28d1-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="f28d1-157">Accedere usando le credenziali Azure AD utente.</span><span class="sxs-lookup"><span data-stu-id="f28d1-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="f28d1-158">Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f28d1-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="f28d1-159">Continuare a configurare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f28d1-159">Continue setting up the device.</span></span>

    - <span data-ttu-id="f28d1-160">Quando si sceglie **Appartiene a me**, si esegue l'accesso con un account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f28d1-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="f28d1-161">Al termine dell'installazione, è possibile [registrare manualmente HoloLens nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="f28d1-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="f28d1-162">Immettere le account Microsoft dati.</span><span class="sxs-lookup"><span data-stu-id="f28d1-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="f28d1-163">Immettere la password.</span><span class="sxs-lookup"><span data-stu-id="f28d1-163">Enter your password.</span></span> <span data-ttu-id="f28d1-164">Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completare il processo di verifica.</span><span class="sxs-lookup"><span data-stu-id="f28d1-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Impostare l'utente](images/13-device-owner.png)

1. <span data-ttu-id="f28d1-166">Consente di scegliere se abilitare il riconoscimento vocale HoloLens 2 e se inviare i dati di telemetria di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="f28d1-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>

    ![Abilitare Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="f28d1-168">Selezionare il livello di telemetria.</span><span class="sxs-lookup"><span data-stu-id="f28d1-168">Select your telemetry level.</span></span> <span data-ttu-id="f28d1-169">Se possibile, abilitare i dati di telemetria completi.</span><span class="sxs-lookup"><span data-stu-id="f28d1-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="f28d1-170">Queste informazioni sono molto utili al team di progettazione di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f28d1-170">This information really helps the HoloLens engineering team.</span></span>

     ![Livello di telemetria](images/24-telemetry.png)

1. <span data-ttu-id="f28d1-172">Informazioni su come usare il movimento di avvio HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f28d1-172">Learn how to use the start gesture on HoloLens 2.</span></span>

     <span data-ttu-id="f28d1-173">![Informazioni su come usare il movimento di avvio, immagine 1 ](images/26-01-startmenu-learning.png) ![ Informazioni su come usare il movimento di avvio, immagine 2](images/26-02-startmenu-learning.png)</span><span class="sxs-lookup"><span data-stu-id="f28d1-173">![Learn how to use the start gesture, image 1](images/26-01-startmenu-learning.png) ![Learn how to use the start gesture, image 2](images/26-02-startmenu-learning.png)</span></span>

<span data-ttu-id="f28d1-174">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="f28d1-174">Congratulations!</span></span>  <span data-ttu-id="f28d1-175">La configurazione è stata completata e si è pronti per usare HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f28d1-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="f28d1-176">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f28d1-176">Next steps</span></span>

1. <span data-ttu-id="f28d1-177">Inizia subito a interagire con la realtà mista e Windows 10 su HoloLens: consulta **l'app** Suggerimenti per esercitazioni pratici per le interazioni con la mano.</span><span class="sxs-lookup"><span data-stu-id="f28d1-177">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="f28d1-178">Usare il movimento di avvio per passare a Start o pronunciare "Vai a Start" e selezionare Tips (Suggerimenti).</span><span class="sxs-lookup"><span data-stu-id="f28d1-178">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="f28d1-179">Fare clic di seguito per continuare a leggere informazioni su come HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f28d1-179">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f28d1-180">Introduzione all'HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f28d1-180">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
