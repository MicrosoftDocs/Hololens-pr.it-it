---
title: Configurare l'HoloLens 2
description: Informazioni su come configurare il HoloLens 2 per la prima volta tramite una rete Wi-Fi con un account Microsoft (MSA) o Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: a5c0e28eff9bb71135309ec5e484fc5b88f02d08
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636676"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="85232-104">Configurare l'HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="85232-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="85232-105">La prima volta che si attiva il HoloLens, si verrà guidati nella configurazione del dispositivo, nell'accesso con un account utente e nella calibrazione del HoloLens agli occhi.</span><span class="sxs-lookup"><span data-stu-id="85232-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="85232-106">In questa sezione viene illustrata la HoloLens 2 configurazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="85232-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="85232-107">Nella sezione successiva si apprenderà come usare le HoloLens e interagire con gli ologrammi.</span><span class="sxs-lookup"><span data-stu-id="85232-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="85232-108">Per passare direttamente a questo articolo, vedere [Getting around HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="85232-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="85232-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="85232-109">Before you start</span></span>

<span data-ttu-id="85232-110">Prima di iniziare, verificare che siano disponibili gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="85232-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="85232-111">**Una connessione di rete**.</span><span class="sxs-lookup"><span data-stu-id="85232-111">**A network connection**.</span></span> <span data-ttu-id="85232-112">È necessario connettere il HoloLens a una rete per configurarlo.</span><span class="sxs-lookup"><span data-stu-id="85232-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="85232-113">Con HoloLens 2, è possibile connettersi con Wi-Fi o tramite ethernet (è necessaria una scheda USB-C-Ethernet).</span><span class="sxs-lookup"><span data-stu-id="85232-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="85232-114">La prima volta che ci si connette, è necessaria una rete aperta o protetta da password che non richiede il passaggio a un sito Web o l'uso di certificati per la connessione.</span><span class="sxs-lookup"><span data-stu-id="85232-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="85232-115">[Altre informazioni sui siti Web che HoloLens usa](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="85232-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="85232-116">**Oggetto account Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="85232-116">**A Microsoft account**.</span></span> <span data-ttu-id="85232-117">È anche necessario accedere a un HoloLens con un account Microsoft (o con l'account aziendale, se l'organizzazione è proprietaria del dispositivo).</span><span class="sxs-lookup"><span data-stu-id="85232-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="85232-118">Se non si ha una account Microsoft, passare a [account.microsoft.com](https://account.microsoft.com) e configurarne una gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="85232-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="85232-119">**Uno spazio sicuro e ben acceso senza rischi di inciampo.**</span><span class="sxs-lookup"><span data-stu-id="85232-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="85232-120">[Informazioni su integrità e sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="85232-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="85232-121">**Gli accessori di comfort** facoltativi che sono stati HoloLens, per facilitare la scelta più comoda.</span><span class="sxs-lookup"><span data-stu-id="85232-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="85232-122">[Altre informazioni su fit e comfort.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="85232-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="85232-123">Configurazione di Windows</span><span class="sxs-lookup"><span data-stu-id="85232-123">Set up Windows</span></span>

<span data-ttu-id="85232-124">La prima volta che si avvia HoloLens 2, la prima attività è la configurazione Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="85232-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="85232-125">Quando si avvia il HoloLens, si riceverà musica e verrà visualizzato Windows logo.</span><span class="sxs-lookup"><span data-stu-id="85232-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Prima schermata durante il primo avvio](images/01-magic-moment.png)

<span data-ttu-id="85232-127">Verrà visualizzato un colibrì che si aggira.</span><span class="sxs-lookup"><span data-stu-id="85232-127">You will see a hummingbird flying around.</span></span>

![Hummingbirdbird](images/hummingbird-1.png)

<span data-ttu-id="85232-129">Seguirlo con la mano.</span><span class="sxs-lookup"><span data-stu-id="85232-129">Follow it with your hand.</span></span>

![Hummingbird al primo volo](images/hummingbird-2.png)

<span data-ttu-id="85232-131">HoloLens 2 illustra i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="85232-131">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="85232-132">Selezionare la lingua.</span><span class="sxs-lookup"><span data-stu-id="85232-132">Select your language.</span></span>

    ![Seleziona lingua](images/04-language.png)

1. <span data-ttu-id="85232-134">Selezionare un'area.</span><span class="sxs-lookup"><span data-stu-id="85232-134">Select your region.</span></span>

    ![Selezionare l'area](images/05-region.png)

1. <span data-ttu-id="85232-136">Calibrare HoloLens agli occhi.</span><span class="sxs-lookup"><span data-stu-id="85232-136">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="85232-137">Se si sceglie di ignorare la calibrazione, verrà richiesto al successivo accesso.</span><span class="sxs-lookup"><span data-stu-id="85232-137">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="85232-138">Prima di tutto, si regola il visore.</span><span class="sxs-lookup"><span data-stu-id="85232-138">First, you'll adjust your visor.</span></span>
    
        ![Schermata di selezione della calibrazione](images/06-et-corners.png)

    2. <span data-ttu-id="85232-140">Per calibrare, si animerà un set di destinazioni (denominate gemme).</span><span class="sxs-lookup"><span data-stu-id="85232-140">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="85232-141">È possibile lampeggiare o chiudere gli occhi durante la calibrazione, ma provare a non guardare altri oggetti nella stanza o nello spazio fisico.</span><span class="sxs-lookup"><span data-stu-id="85232-141">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="85232-142">HoloLens usa questo processo per ottenere informazioni sulla posizione dell'occhio in modo da migliorare il rendering del mondo olografico.</span><span class="sxs-lookup"><span data-stu-id="85232-142">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Regola per gli occhi](images/07-adjust-eyes.png)

        <span data-ttu-id="85232-144">Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando il visore si sposta sulla testa.</span><span class="sxs-lookup"><span data-stu-id="85232-144">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="85232-145">Le informazioni di calibrazione vengono archiviate localmente nel dispositivo e non sono associate ad alcuna informazione sull'account.</span><span class="sxs-lookup"><span data-stu-id="85232-145">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="85232-146">Per altre informazioni, vedere [Calibrazione dei dati e sicurezza.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="85232-146">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![Calibrazione completata](images/calibration-complete.png)

1. <span data-ttu-id="85232-148">Connessione a Internet (selezionare Wi-Fi o la connessione ethernet).</span><span class="sxs-lookup"><span data-stu-id="85232-148">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="85232-149">HoloLens imposta automaticamente il fuso orario in base alle informazioni ottenute dalla Wi-Fi rete.</span><span class="sxs-lookup"><span data-stu-id="85232-149">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="85232-150">Al termine dell'installazione, è possibile modificare il fuso orario usando l Impostazioni app.</span><span class="sxs-lookup"><span data-stu-id="85232-150">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Connettersi alla rete Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="85232-152">Se si procede oltre il passaggio Wi-Fi e successivamente è necessario passare a una rete diversa  durante la configurazione, è possibile premere i pulsanti **Volume** in basso e Alimentazione contemporaneamente per tornare a questo passaggio se si esegue una versione del sistema operativo da ottobre 2019 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="85232-152">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="85232-153">Per le versioni precedenti, [](hololens-recovery.md) potrebbe essere necessario reimpostare il dispositivo o riavviarlo in una posizione in cui la rete Wi-Fi non è disponibile per impedirne la connessione automatica.</span><span class="sxs-lookup"><span data-stu-id="85232-153">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="85232-154">Si noti anche che, durante HoloLens di installazione, si verifica un timeout delle credenziali di due minuti.</span><span class="sxs-lookup"><span data-stu-id="85232-154">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="85232-155">Il nome utente/password deve essere immesso entro due minuti. In caso contrario, il campo del nome utente verrà cancellato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="85232-155">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="85232-156">HoloLens 2 ricerca e applica un profilo Autopilot, se esistente.</span><span class="sxs-lookup"><span data-stu-id="85232-156">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="85232-157">In questa schermata non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="85232-157">No action is needed on this screen.</span></span>
 
    ![Ricerca nel profilo di Autopilot](images/autopilot-profile-search.png) 

1. <span data-ttu-id="85232-159">Fare **clic su** Accetta nella schermata delle licenze.</span><span class="sxs-lookup"><span data-stu-id="85232-159">Click **Accept** on the licensing screen.</span></span>

    ![Windows contratto di licenza](images/windows-license-agreement.png)

1. <span data-ttu-id="85232-161">Accedere al proprio account utente.</span><span class="sxs-lookup"><span data-stu-id="85232-161">Sign in to your user account.</span></span> <span data-ttu-id="85232-162">Si sceglierà tra My work or school owns it and I own it ( Il mio lavoro **o l'istituto di** istruzione ne è il proprietario ed è il mio **proprietario).**</span><span class="sxs-lookup"><span data-stu-id="85232-162">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    ![Impostare l'utente](images/13-device-owner.png)
    - <span data-ttu-id="85232-164">Quando si sceglie **Appartiene all'azienda o all'istituto di istruzione**, si esegue l'accesso con un account Azure AD.</span><span class="sxs-lookup"><span data-stu-id="85232-164">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="85232-165">Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione MDM automatica, HoloLens automaticamente la registrazione in MDM.</span><span class="sxs-lookup"><span data-stu-id="85232-165">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="85232-166">Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="85232-166">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="85232-167">In tal caso, è necessario registrare [manualmente i HoloLens nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="85232-167">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="85232-168">Immettere le informazioni sull'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="85232-168">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="85232-169">Accettare l'informativa sulla privacy e il contratto di licenza con l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="85232-169">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="85232-170">Accedere usando le credenziali Azure AD utente.</span><span class="sxs-lookup"><span data-stu-id="85232-170">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="85232-171">Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85232-171">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="85232-172">Continuare a configurare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85232-172">Continue setting up the device.</span></span>

    - <span data-ttu-id="85232-173">Quando si sceglie **Appartiene a me**, si esegue l'accesso con un account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85232-173">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="85232-174">Al termine dell'installazione, è possibile [registrare manualmente HoloLens nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="85232-174">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="85232-175">Immettere le informazioni account Microsoft dati.</span><span class="sxs-lookup"><span data-stu-id="85232-175">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="85232-176">Immettere la password.</span><span class="sxs-lookup"><span data-stu-id="85232-176">Enter your password.</span></span> <span data-ttu-id="85232-177">Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completare il processo di verifica.</span><span class="sxs-lookup"><span data-stu-id="85232-177">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

        
1. <span data-ttu-id="85232-178">Configurare l'accesso Iris selezionando **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="85232-178">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="85232-179">Si sperimenterà un'esperienza simile alla calibrazione oculare.</span><span class="sxs-lookup"><span data-stu-id="85232-179">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="85232-180">Al **termine dell'analisi,** selezionare Fine.</span><span class="sxs-lookup"><span data-stu-id="85232-180">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="85232-181">È anche possibile selezionare **Ignora per** ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="85232-181">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="85232-182">![Completamento ](images/setup-iris.png) ![ dell'installazione di Iris Iris](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="85232-182">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="85232-183">Si configura un PIN per accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85232-183">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="85232-184">Questo PIN è specifico del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85232-184">This PIN is device specific.</span></span> 

    ![Configurare Windows Hello](images/setup-windows-hello.png)

    ![Configurare Windows Hello PIN](images/windows-hello-pin.png)

    ![Windows Hello Installazione completata](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="85232-188">Scegliere se abilitare il riconoscimento vocale HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="85232-188">Select whether to enable speech on HoloLens 2.</span></span>

    ![Abilitare Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="85232-190">Specificare se abilitare la posizione nella HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="85232-190">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Abilitare i servizi di posizione](images/setup-location-services.png)

1. <span data-ttu-id="85232-192">Selezionare il livello di telemetria.</span><span class="sxs-lookup"><span data-stu-id="85232-192">Select your telemetry level.</span></span> <span data-ttu-id="85232-193">Se possibile, abilitare i dati di telemetria facoltativi.</span><span class="sxs-lookup"><span data-stu-id="85232-193">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="85232-194">Queste informazioni sono molto utili per HoloLens team di progettazione.</span><span class="sxs-lookup"><span data-stu-id="85232-194">This information really helps the HoloLens engineering team.</span></span>

     ![Livello di telemetria](images/24-telemetry.png)

1. <span data-ttu-id="85232-196">Informazioni su come usare il movimento di avvio HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="85232-196">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Informazioni su come usare il movimento di avvio, immagine 1](images/26-01-startmenu-learning.png)

     ![Informazioni su come usare il movimento di avvio, immagine 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="85232-199">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="85232-199">Congratulations!</span></span>  <span data-ttu-id="85232-200">L'installazione è stata completata e si è pronti per usare HoloLens.</span><span class="sxs-lookup"><span data-stu-id="85232-200">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="85232-201">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="85232-201">Next steps</span></span>

1. <span data-ttu-id="85232-202">Iniziare **subito a** interagire con la realtà mista ed esplorare Windows 10 sul HoloLens: vedere l'app Suggerimenti per esercitazioni pratica sulle interazioni con la mano.</span><span class="sxs-lookup"><span data-stu-id="85232-202">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="85232-203">Usare il movimento start per passare a Start o pronunciare "Vai a Start" e selezionare Suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="85232-203">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="85232-204">Fare clic di seguito per continuare a leggere informazioni su come HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="85232-204">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="85232-205">Orientarsi in HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="85232-205">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
