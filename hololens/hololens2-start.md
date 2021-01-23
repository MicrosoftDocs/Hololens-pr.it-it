---
title: Configurare il dispositivo HoloLens 2
description: Informazioni su come configurare HoloLens 2 per la prima volta tramite una rete Wi-Fi con un account Microsoft (MSA) o un account di Azure Active Directory (AAD).
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
ms.openlocfilehash: 9824de1d81fd6ba9ccafc8627d660aebefeaed15
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283877"
---
# <span data-ttu-id="da9a6-104">Configurare il dispositivo HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="da9a6-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="da9a6-105">La prima volta che accendi il dispositivo HoloLens, riceverai istruzioni per eseguire la configurazione, l'accesso con un account utente e la calibrazione di HoloLens con gli occhi.</span><span class="sxs-lookup"><span data-stu-id="da9a6-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="da9a6-106">Questa sezione illustra l'esperienza di configurazione iniziale di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="da9a6-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="da9a6-107">Nella sezione successiva imparerai a usare HoloLens e interagire con gli ologrammi.</span><span class="sxs-lookup"><span data-stu-id="da9a6-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="da9a6-108">Per passare direttamente a questo articolo, vedi [Introduzione a HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="da9a6-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <span data-ttu-id="da9a6-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="da9a6-109">Before you start</span></span>

<span data-ttu-id="da9a6-110">Prima di iniziare, assicurati di disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="da9a6-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="da9a6-111">**Una connessione di rete**.</span><span class="sxs-lookup"><span data-stu-id="da9a6-111">**A network connection**.</span></span> <span data-ttu-id="da9a6-112">Devi connettere il dispositivo HoloLens a una rete per configurarlo.</span><span class="sxs-lookup"><span data-stu-id="da9a6-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="da9a6-113">Con HoloLens 2, puoi eseguire la connessione tramite Wi-Fi o Ethernet (è necessario un adattatore da USB-C a Ethernet).</span><span class="sxs-lookup"><span data-stu-id="da9a6-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="da9a6-114">La prima volta che effettui la connessione, ti servirà una rete aperta o protetta da password che non richiede l'accesso a un sito Web o l'utilizzo di certificati per la connessione.</span><span class="sxs-lookup"><span data-stu-id="da9a6-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="da9a6-115">[Scopri di più sui siti Web usati da HoloLens](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="da9a6-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="da9a6-116">**Un account Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="da9a6-116">**A Microsoft account**.</span></span> <span data-ttu-id="da9a6-117">Dovrai inoltre accedere a HoloLens con un account Microsoft o, se la tua organizzazione è proprietaria del dispositivo, con un account aziendale.</span><span class="sxs-lookup"><span data-stu-id="da9a6-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="da9a6-118">Se non disponi di un account Microsoft, vai a [account.microsoft.com](https://account.microsoft.com) e configurane uno gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="da9a6-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="da9a6-119">**Uno spazio sicuro e ben illuminato senza pericoli**.</span><span class="sxs-lookup"><span data-stu-id="da9a6-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="da9a6-120">[Informazioni sulla sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="da9a6-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="da9a6-121">**Accessori opzionali per il comfort** forniti con il dispositivo HoloLens, utili per indossarlo in modo confortevole.</span><span class="sxs-lookup"><span data-stu-id="da9a6-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="da9a6-122">[Ulteriori informazioni per indossarlo in modo confortevole](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="da9a6-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <span data-ttu-id="da9a6-123">Configurare Windows</span><span class="sxs-lookup"><span data-stu-id="da9a6-123">Set up Windows</span></span>

<span data-ttu-id="da9a6-124">La prima volta che avvii HoloLens 2, dovrai innanzitutto configurare Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="da9a6-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="da9a6-125">Quando avvii HoloLens, viene emessa della musica e viene visualizzato un logo Windows.</span><span class="sxs-lookup"><span data-stu-id="da9a6-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Prima schermata durante il primo avvio](images/01-magic-moment.png)

<span data-ttu-id="da9a6-127">HoloLens 2 ti guiderà nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="da9a6-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="da9a6-128">Seleziona la tua lingua.</span><span class="sxs-lookup"><span data-stu-id="da9a6-128">Select your language.</span></span>
    ![Selezione della lingua](images/04-language.png)

1. <span data-ttu-id="da9a6-130">Seleziona la tua regione.</span><span class="sxs-lookup"><span data-stu-id="da9a6-130">Select your region.</span></span>
    ![Selezione della regione](images/05-region.png)

1. <span data-ttu-id="da9a6-132">Calibra HoloLens con i tuoi occhi.</span><span class="sxs-lookup"><span data-stu-id="da9a6-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="da9a6-133">Se scegli di ignorare la calibrazione, verrà richiesto di effettuarla al successivo accesso.</span><span class="sxs-lookup"><span data-stu-id="da9a6-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="da9a6-134">Per eseguire la calibrazione, dovrai guardare una serie di obiettivi (dette gemme).</span><span class="sxs-lookup"><span data-stu-id="da9a6-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="da9a6-135">Durante la calibrazione, puoi sbattere o chiudere gli occhi, ma cerca di non fissare altri oggetti presenti nella stanza o nello spazio fisico.</span><span class="sxs-lookup"><span data-stu-id="da9a6-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="da9a6-136">HoloLens usa questo processo per ottenere informazioni sulla posizione degli occhi, così da garantire un rendering ottimale del mondo olografico.</span><span class="sxs-lookup"><span data-stu-id="da9a6-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="da9a6-137">Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando la visiera si sposta sulla testa.</span><span class="sxs-lookup"><span data-stu-id="da9a6-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="da9a6-138">Le informazioni sulla calibrazione vengono memorizzate localmente nel dispositivo e non sono associate alle informazioni sull'account.</span><span class="sxs-lookup"><span data-stu-id="da9a6-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="da9a6-139">Per altre informazioni, vedi [Dati di calibrazione e sicurezza](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="da9a6-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![Schermata di selezione della calibrazione](images/06-et-corners.png)

1. <span data-ttu-id="da9a6-141">Esegui la connessione a Internet (seleziona la rete Wi-Fi o la connessione Ethernet).</span><span class="sxs-lookup"><span data-stu-id="da9a6-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>
     <span data-ttu-id="da9a6-142">HoloLens imposta automaticamente il fuso orario in base alle informazioni ottenute dalla rete Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="da9a6-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="da9a6-143">Al termine della configurazione, potrai cambiare il fuso orario usando l'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="da9a6-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Connessione alla rete Wi-Fi](images/11-network.png)
> [!NOTE] 
> <span data-ttu-id="da9a6-145">Se superi il passaggio Wi-Fi e successivamente devi passare a una rete diversa mentre sei ancora in fase di installazione, puoi premere contemporaneamente i pulsanti di **riduzione volume** e **accensione** per tornare a questo passaggio se esegui una versione del sistema operativo da ottobre 2019 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="da9a6-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="da9a6-146">Per le versioni precedenti, potrebbe essere necessario [reimpostare il dispositivo](hololens-recovery.md) o riavviarlo in un percorso in cui la rete Wi-Fi non è disponibile per impedirne la connessione automatica.</span><span class="sxs-lookup"><span data-stu-id="da9a6-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
> 
> <span data-ttu-id="da9a6-147">Tieni inoltre presente che durante l'installazione di HoloLens si verifica un timeout delle credenziali di due minuti.</span><span class="sxs-lookup"><span data-stu-id="da9a6-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="da9a6-148">Nome utente/password devono essere immessi entro due minuti, altrimenti il campo nome utente verrà cancellato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="da9a6-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="da9a6-149">Accedi al tuo account utente.</span><span class="sxs-lookup"><span data-stu-id="da9a6-149">Sign in to your user account.</span></span> <span data-ttu-id="da9a6-150">Potrai scegliere tra **Appartiene all'azienda o all'istituto di istruzione** e **Appartiene a me**.</span><span class="sxs-lookup"><span data-stu-id="da9a6-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="da9a6-151">Quando scegli **Appartiene all'azienda o all'istituto di istruzione**, accedi con un account Azure AD.</span><span class="sxs-lookup"><span data-stu-id="da9a6-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="da9a6-152">Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione automatica MDM, HoloLens si registra automaticamente in MDM.</span><span class="sxs-lookup"><span data-stu-id="da9a6-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="da9a6-153">Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="da9a6-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="da9a6-154">In questo caso, dovrai [registrare manualmente HoloLens in gestione dispositivi](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="da9a6-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="da9a6-155">Immetti le informazioni sull'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="da9a6-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="da9a6-156">Accetta l'Informativa sulla privacy e il Contratto di licenza con l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="da9a6-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="da9a6-157">Accedi usando le credenziali di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="da9a6-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="da9a6-158">Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="da9a6-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="da9a6-159">Continua a configurare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="da9a6-159">Continue setting up the device.</span></span>
    - <span data-ttu-id="da9a6-160">Quando scegli **Appartiene a me**, accedi con un account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="da9a6-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="da9a6-161">Al termine della configurazione, puoi [registrare manualmente HoloLens in gestione dispositivi](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="da9a6-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="da9a6-162">Immetti le informazioni sull'account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="da9a6-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="da9a6-163">Immettere la password.</span><span class="sxs-lookup"><span data-stu-id="da9a6-163">Enter your password.</span></span> <span data-ttu-id="da9a6-164">Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completa il processo di verifica.</span><span class="sxs-lookup"><span data-stu-id="da9a6-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Impostazione dell'utente](images/13-device-owner.png)

1. <span data-ttu-id="da9a6-166">Seleziona se abilitare la sintesi vocale in HoloLens 2 e se inviare la telemetria di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="da9a6-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>
    ![Abilitazione di Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="da9a6-168">Seleziona il livello di telemetria.</span><span class="sxs-lookup"><span data-stu-id="da9a6-168">Select your telemetry level.</span></span> <span data-ttu-id="da9a6-169">Se possibile, abilita il livello di telemetria completo.</span><span class="sxs-lookup"><span data-stu-id="da9a6-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="da9a6-170">Queste informazioni sono veramente utili per il team di sviluppo di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="da9a6-170">This information really helps the HoloLens engineering team.</span></span>
     ![Livello di telemetria](images/24-telemetry.png)

1. <span data-ttu-id="da9a6-172">Scopri come usare il gesto Start in HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="da9a6-172">Learn how to use the start gesture on HoloLens 2.</span></span>
     ![Informazioni su come usare il gesto Start, immagine 1](images/26-01-startmenu-learning.png) ![Informazioni su come usare il gesto Start, immagine 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="da9a6-174">Complimenti.</span><span class="sxs-lookup"><span data-stu-id="da9a6-174">Congratulations!</span></span>  <span data-ttu-id="da9a6-175">La configurazione è completa. Ora potrai utilizzare HoloLens!</span><span class="sxs-lookup"><span data-stu-id="da9a6-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <span data-ttu-id="da9a6-176">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="da9a6-176">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="da9a6-177">Introduzione a HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="da9a6-177">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
