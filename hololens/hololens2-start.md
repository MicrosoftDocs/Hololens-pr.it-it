---
title: Configurare l'HoloLens 2
description: Informazioni su come configurare il HoloLens 2 per la prima volta in una rete Wi-Fi con un account Microsoft (MSA) o Azure Active Directory (AAD).
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
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189767"
---
# <a name="set-up-your-hololens-2"></a>Configurare l'HoloLens 2

La prima volta che si attiva il HoloLens, si verrà guidati nella configurazione del dispositivo, nell'accesso con un account utente e nella calibrazione del HoloLens agli occhi.  Questa sezione illustra in modo HoloLens 2 configurazione iniziale.

Nella sezione successiva si apprenderà come usare le HoloLens e interagire con gli ologrammi. Per passare direttamente a questo articolo, vedere [Getting around HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Prima di iniziare

Prima di iniziare, verificare che siano disponibili gli elementi seguenti:

**Una connessione di rete**. È necessario connettere il HoloLens a una rete per configurarlo. Con HoloLens 2, è possibile connettersi con Wi-Fi o tramite ethernet (è necessaria una scheda USB-C-Ethernet). La prima volta che ci si connette, è necessaria una rete aperta o protetta da password che non richiede il passaggio a un sito Web o l'uso di certificati per la connessione. [Altre informazioni sui siti Web che HoloLens usa](hololens-offline.md).

**Oggetto account Microsoft**. È anche necessario accedere a HoloLens con un account Microsoft (o con l'account aziendale, se l'organizzazione è proprietaria del dispositivo). Se non si ha una account Microsoft, passare a [account.microsoft.com](https://account.microsoft.com) e configurarne una gratuitamente.

**Uno spazio sicuro e ben acceso senza rischi di inciampo.** [Informazioni su integrità e sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Gli accessori di comfort facoltativi** che sono stati HoloLens, per facilitare la scelta più comoda. [Altre informazioni su fit e comfort.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Configurazione di Windows

La prima volta che si avvia HoloLens 2, la prima attività è la configurazione Windows Holographic.  Quando si avvia il HoloLens, si riceverà musica e verrà visualizzato un logo Microsoft.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Verrà visualizzato un colibrì che si aggira.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Seguirà la mano.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Verrà visualizzato un pulsante con un logo Microsoft. Premere il pulsante per HoloLens 2 procedura dettagliata:

1. Selezionare la lingua.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Selezionare un'area.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Calibrare HoloLens agli occhi.  Se si sceglie di ignorare la calibrazione, verrà richiesto al successivo accesso. 

    1. Prima di tutto, si regola il visore.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Per calibrare, si animerà un set di destinazioni (denominate gemme). È possibile lampeggiare o chiudere gli occhi durante la calibrazione, ma provare a non guardare altri oggetti nella stanza o nello spazio fisico. HoloLens usa questo processo per conoscere la posizione dell'occhio in modo che possa migliorare il rendering del mondo olografico. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando il visore si sposta sulla testa. Le informazioni di calibrazione vengono archiviate localmente nel dispositivo e non sono associate ad alcuna informazione sull'account. Per altre informazioni, vedere [Calibrazione dei dati e sicurezza.](hololens-calibration.md#calibration-data-and-security)

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Connessione a Internet (selezionare Wi-Fi o la connessione ethernet).

     HoloLens imposta automaticamente il fuso orario in base alle informazioni ottenute dalla Wi-Fi rete. Al termine dell'installazione, è possibile modificare il fuso orario usando l Impostazioni app.

    ![Connessione alla rete Wi-Fi.](images/11-network.png)

    > [!NOTE] 
    > Se si procede oltre il passaggio Wi-Fi e successivamente è necessario passare a una  rete diversa  durante la configurazione, è possibile premere i pulsanti Volume in basso e Alimentazione contemporaneamente per tornare a questo passaggio se si esegue una versione del sistema operativo da ottobre 2019 o versioni successive. Per le versioni precedenti, [](hololens-recovery.md) potrebbe essere necessario reimpostare il dispositivo o riavviarlo in una posizione in cui la rete Wi-Fi non è disponibile per impedire la connessione automatica.
    > 
    > Si noti anche che durante HoloLens installazione di , si verifica un timeout delle credenziali di due minuti. Il nome utente/password deve essere immesso entro due minuti. In caso contrario, il campo del nome utente verrà cancellato automaticamente.

1. HoloLens 2 ricerca e applica un profilo Autopilot, se esistente. In questa schermata non è necessaria alcuna azione.
 
    ![Ricerca del profilo autopilot.](images/autopilot-profile-search.png) 

1. Fare **clic su** Accetta nella schermata delle licenze.

    ![Windows contratto di licenza.](images/windows-license-agreement.png)

1. Accedere al proprio account utente. Si sceglierà tra My work or school owns it and I own it ( Il mio lavoro **o l'istituto di** istruzione ne è il proprietario ed è il mio **proprietario).**

    ![Impostare l'utente.](images/13-device-owner.png)
    - Quando si sceglie **Appartiene all'azienda o all'istituto di istruzione**, si esegue l'accesso con un account Azure AD. Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione MDM automatica, HoloLens automaticamente la registrazione in MDM. Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile. In tal caso, è necessario registrare manualmente i [HoloLens nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Immettere le informazioni sull'account aziendale.
        1. Accettare l'informativa sulla privacy e il contratto di licenza con l'utente finale.
        1. Accedere usando le credenziali Azure AD utente. Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.
        1. Continuare a configurare il dispositivo.

    - Quando si sceglie **Appartiene a me**, si esegue l'accesso con un account Microsoft. Al termine dell'installazione, è possibile [registrare manualmente HoloLens nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Immettere le informazioni account Microsoft dati.
        2. Immettere la password. Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completare il processo di verifica.

        
1. Configurare l'accesso Iris selezionando **Avanti.** Si sperimenterà un'esperienza simile alla calibrazione oculare. Al **termine dell'analisi,** selezionare Fine. È anche possibile selezionare **Ignora per** ignorare questo passaggio.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Si configura un PIN per accedere al dispositivo. Questo PIN è specifico del dispositivo. 

    ![Configurare Windows Hello.](images/setup-windows-hello.png)

    ![Configurare Windows Hello PIN.](images/windows-hello-pin.png)

    ![Windows Hello Installazione completata.](images/windows-hello-successful.png) 

    
1. Scegliere se abilitare il riconoscimento vocale HoloLens 2.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Specificare se abilitare la posizione nella HoloLens 2.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Selezionare il livello di telemetria. Se possibile, abilitare i dati di telemetria facoltativi. Queste informazioni sono molto utili per HoloLens team di progettazione.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Informazioni su come usare il movimento di avvio HoloLens 2.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    È stata  La configurazione è stata completata e si è pronti per usare HoloLens.

## <a name="next-steps"></a>Passaggi successivi

1. Inizia subito a interagire con la realtà mista e Windows 10 nel tuo HoloLens: consulta l'app **Suggerimenti** per esercitazioni di base per le interazioni con la mano. Usare il movimento di avvio per passare a Start o pronunciare "Vai a Start" e selezionare Suggerimenti.

1. Fare clic di seguito per continuare a leggere informazioni su come HoloLens 2.

> [!div class="nextstepaction"]
> [Orientarsi in HoloLens 2](hololens2-basic-usage.md)
