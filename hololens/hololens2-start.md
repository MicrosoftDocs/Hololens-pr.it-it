---
title: Configurare il dispositivo HoloLens 2
description: Questa guida illustra come eseguire la configurazione per la prima volta.  Ti servirà una rete Wi-Fi e un account Microsoft o Azure Active Directory (AAD).
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
ms.openlocfilehash: a0ba32e3caff7695cd284ee3752bb91d80da2194
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903242"
---
# <span data-ttu-id="d1643-105">Configurare il dispositivo HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d1643-105">Set up your HoloLens 2</span></span>

<span data-ttu-id="d1643-106">La prima volta che accendi il dispositivo HoloLens, riceverai istruzioni per eseguire la configurazione, l'accesso con un account utente e la calibrazione di HoloLens con gli occhi.</span><span class="sxs-lookup"><span data-stu-id="d1643-106">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="d1643-107">Questa sezione illustra l'esperienza di configurazione iniziale di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d1643-107">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="d1643-108">Nella sezione successiva imparerai a usare HoloLens e interagire con gli ologrammi.</span><span class="sxs-lookup"><span data-stu-id="d1643-108">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="d1643-109">Per passare direttamente a questo articolo, vedi [Introduzione a HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="d1643-109">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <span data-ttu-id="d1643-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d1643-110">Before you start</span></span>

<span data-ttu-id="d1643-111">Prima di iniziare, assicurati di disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d1643-111">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="d1643-112">**Una connessione di rete**.</span><span class="sxs-lookup"><span data-stu-id="d1643-112">**A network connection**.</span></span> <span data-ttu-id="d1643-113">Devi connettere il dispositivo HoloLens a una rete per configurarlo.</span><span class="sxs-lookup"><span data-stu-id="d1643-113">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="d1643-114">Con HoloLens 2, puoi eseguire la connessione tramite Wi-Fi o Ethernet (è necessario un adattatore da USB-C a Ethernet).</span><span class="sxs-lookup"><span data-stu-id="d1643-114">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="d1643-115">La prima volta che effettui la connessione, ti servirà una rete aperta o protetta da password che non richiede l'accesso a un sito Web o l'utilizzo di certificati per la connessione.</span><span class="sxs-lookup"><span data-stu-id="d1643-115">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="d1643-116">[Scopri di più sui siti Web usati da HoloLens](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="d1643-116">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="d1643-117">**Un account Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d1643-117">**A Microsoft account**.</span></span> <span data-ttu-id="d1643-118">Dovrai inoltre accedere a HoloLens con un account Microsoft o, se la tua organizzazione è proprietaria del dispositivo, con un account aziendale.</span><span class="sxs-lookup"><span data-stu-id="d1643-118">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="d1643-119">Se non disponi di un account Microsoft, vai a [account.microsoft.com](https://account.microsoft.com) e configurane uno gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="d1643-119">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="d1643-120">**Uno spazio sicuro e ben illuminato senza pericoli**.</span><span class="sxs-lookup"><span data-stu-id="d1643-120">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="d1643-121">[Informazioni sulla sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="d1643-121">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="d1643-122">**Accessori opzionali per il comfort** forniti con il dispositivo HoloLens, utili per indossarlo in modo confortevole.</span><span class="sxs-lookup"><span data-stu-id="d1643-122">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="d1643-123">[Ulteriori informazioni per indossarlo in modo confortevole](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="d1643-123">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <span data-ttu-id="d1643-124">Configurare Windows</span><span class="sxs-lookup"><span data-stu-id="d1643-124">Set up Windows</span></span>

<span data-ttu-id="d1643-125">La prima volta che avvii HoloLens 2, dovrai innanzitutto configurare Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="d1643-125">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="d1643-126">Quando avvii HoloLens, viene emessa della musica e viene visualizzato un logo Windows.</span><span class="sxs-lookup"><span data-stu-id="d1643-126">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Prima schermata durante il primo avvio](images/01-magic-moment.png)

<span data-ttu-id="d1643-128">HoloLens 2 ti guiderà nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1643-128">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="d1643-129">Seleziona la tua lingua.</span><span class="sxs-lookup"><span data-stu-id="d1643-129">Select your language.</span></span>
    ![Selezione della lingua](images/04-language.png)

1. <span data-ttu-id="d1643-131">Seleziona la tua regione.</span><span class="sxs-lookup"><span data-stu-id="d1643-131">Select your region.</span></span>
    ![Selezione della regione](images/05-region.png)

1. <span data-ttu-id="d1643-133">Calibra HoloLens con i tuoi occhi.</span><span class="sxs-lookup"><span data-stu-id="d1643-133">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="d1643-134">Se scegli di ignorare la calibrazione, verrà richiesto di effettuarla al successivo accesso.</span><span class="sxs-lookup"><span data-stu-id="d1643-134">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="d1643-135">Per eseguire la calibrazione, dovrai guardare una serie di obiettivi (dette gemme).</span><span class="sxs-lookup"><span data-stu-id="d1643-135">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="d1643-136">Durante la calibrazione, puoi sbattere o chiudere gli occhi, ma cerca di non fissare altri oggetti presenti nella stanza o nello spazio fisico.</span><span class="sxs-lookup"><span data-stu-id="d1643-136">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="d1643-137">HoloLens usa questo processo per ottenere informazioni sulla posizione degli occhi, così da garantire un rendering ottimale del mondo olografico.</span><span class="sxs-lookup"><span data-stu-id="d1643-137">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="d1643-138">Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando la visiera si sposta sulla testa.</span><span class="sxs-lookup"><span data-stu-id="d1643-138">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="d1643-139">Le informazioni sulla calibrazione vengono memorizzate localmente nel dispositivo e non sono associate alle informazioni sull'account.</span><span class="sxs-lookup"><span data-stu-id="d1643-139">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="d1643-140">Per altre informazioni, vedi [Dati di calibrazione e sicurezza](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="d1643-140">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![Schermata di selezione della calibrazione](images/06-et-corners.png)

1. <span data-ttu-id="d1643-142">Esegui la connessione a Internet (seleziona la rete Wi-Fi o la connessione Ethernet).</span><span class="sxs-lookup"><span data-stu-id="d1643-142">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>
     <span data-ttu-id="d1643-143">HoloLens imposta automaticamente il fuso orario in base alle informazioni ottenute dalla rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="d1643-143">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="d1643-144">Al termine della configurazione, potrai cambiare il fuso orario usando l'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d1643-144">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Connessione alla rete Wi-Fi](images/11-network.png)
> [!NOTE] 
> <span data-ttu-id="d1643-146">Se superi il passaggio Wi-Fi e successivamente devi passare a una rete diversa mentre sei ancora in fase di installazione, puoi premere contemporaneamente i pulsanti di **riduzione volume** e **accensione** per tornare a questo passaggio se esegui una versione del sistema operativo da ottobre 2019 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d1643-146">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="d1643-147">Per le versioni precedenti, potrebbe essere necessario [reimpostare il dispositivo](hololens-recovery.md) o riavviarlo in un percorso in cui la rete Wi-Fi non è disponibile per impedirne la connessione automatica.</span><span class="sxs-lookup"><span data-stu-id="d1643-147">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
> 
> <span data-ttu-id="d1643-148">Tieni inoltre presente che durante l'installazione di HoloLens si verifica un timeout delle credenziali di due minuti.</span><span class="sxs-lookup"><span data-stu-id="d1643-148">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="d1643-149">Nome utente/password devono essere immessi entro due minuti, altrimenti il campo nome utente verrà cancellato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d1643-149">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="d1643-150">Accedi al tuo account utente.</span><span class="sxs-lookup"><span data-stu-id="d1643-150">Sign in to your user account.</span></span> <span data-ttu-id="d1643-151">Potrai scegliere tra **Appartiene all'azienda o all'istituto di istruzione** e **Appartiene a me**.</span><span class="sxs-lookup"><span data-stu-id="d1643-151">You'll choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="d1643-152">Quando scegli **Appartiene all'azienda o all'istituto di istruzione**, accedi con un account Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d1643-152">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="d1643-153">Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione automatica MDM, HoloLens si registra automaticamente in MDM.</span><span class="sxs-lookup"><span data-stu-id="d1643-153">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="d1643-154">Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d1643-154">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="d1643-155">In questo caso, dovrai [registrare manualmente HoloLens in gestione dispositivi](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="d1643-155">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="d1643-156">Immetti le informazioni sull'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="d1643-156">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="d1643-157">Accetta l'Informativa sulla privacy e il Contratto di licenza con l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="d1643-157">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="d1643-158">Accedi usando le credenziali di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d1643-158">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="d1643-159">Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1643-159">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="d1643-160">Continua a configurare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1643-160">Continue setting up the device.</span></span>
    - <span data-ttu-id="d1643-161">Quando scegli **Appartiene a me**, accedi con un account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1643-161">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="d1643-162">Al termine della configurazione, puoi [registrare manualmente HoloLens in gestione dispositivi](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="d1643-162">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="d1643-163">Immetti le informazioni sull'account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1643-163">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="d1643-164">Immetti la password.</span><span class="sxs-lookup"><span data-stu-id="d1643-164">Enter your password.</span></span> <span data-ttu-id="d1643-165">Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completa il processo di verifica.</span><span class="sxs-lookup"><span data-stu-id="d1643-165">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Impostazione dell'utente](images/13-device-owner.png)

1. <span data-ttu-id="d1643-167">Seleziona se abilitare la sintesi vocale in HoloLens 2 e se inviare la telemetria di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d1643-167">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>
    ![Abilitazione di Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="d1643-169">Seleziona il livello di telemetria.</span><span class="sxs-lookup"><span data-stu-id="d1643-169">Select your telemetry level.</span></span> <span data-ttu-id="d1643-170">Se possibile, abilita il livello di telemetria completo.</span><span class="sxs-lookup"><span data-stu-id="d1643-170">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="d1643-171">Queste informazioni sono veramente utili per il team di sviluppo di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d1643-171">This information really helps the HoloLens engineering team.</span></span>
     ![Livello di telemetria](images/24-telemetry.png)

1. <span data-ttu-id="d1643-173">Scopri come usare il gesto Start in HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d1643-173">Learn how to use the start gesture on HoloLens 2.</span></span>
     ![Informazioni su come usare il gesto Start, immagine 1](images/26-01-startmenu-learning.png) ![Informazioni su come usare il gesto Start, immagine 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="d1643-175">Complimenti.</span><span class="sxs-lookup"><span data-stu-id="d1643-175">Congratulations!</span></span>  <span data-ttu-id="d1643-176">La configurazione è completa. Ora potrai utilizzare HoloLens!</span><span class="sxs-lookup"><span data-stu-id="d1643-176">Setup is complete and you're ready to use HoloLens!</span></span>

## <span data-ttu-id="d1643-177">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d1643-177">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1643-178">Introduzione a HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d1643-178">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
