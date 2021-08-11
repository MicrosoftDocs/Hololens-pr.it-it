---
title: Configurare il HoloLens 2
description: Informazioni su come configurare il HoloLens 2 per la prima volta Wi-Fi rete con un account Microsoft (MSA) o Azure Active Directory (AAD).
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
ms.openlocfilehash: 6f50874c39d8bffa43ff94101c81dcffe3dc1b3c34c69e940ed503dc7bd8b4ba
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659195"
---
# <a name="set-up-your-hololens-2"></a>Configurare il HoloLens 2

La prima volta che si attiva il HoloLens, si verrà guidati nella configurazione del dispositivo, nell'accesso con un account utente e nella calibrazione del HoloLens agli occhi.  In questa sezione viene illustrata l'HoloLens 2 di configurazione iniziale.

Nella sezione successiva si apprenderà come usare HoloLens e interagire con gli ologrammi. Per passare a questo articolo, vedere [Getting around HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Prima di iniziare

Prima di iniziare, assicurarsi di avere a disposizione quanto segue:

**Una connessione di rete**. È necessario connettere il HoloLens a una rete per configurarlo. Con HoloLens 2, è possibile connettersi con Wi-Fi o usando ethernet (è necessaria una scheda USB-C-to-Ethernet). La prima volta che ci si connette, sarà necessaria una rete aperta o protetta da password che non richieda l'accesso a un sito Web o l'uso di certificati per la connessione. [Altre informazioni sui siti Web che HoloLens usa](hololens-offline.md).

**Oggetto account Microsoft**. È anche necessario accedere a HoloLens con un account Microsoft (o con l'account aziendale, se l'organizzazione è proprietaria del dispositivo). Se non si ha una account Microsoft, passare a account.microsoft.com [e](https://account.microsoft.com) configurarne una gratuitamente.

**Uno spazio sicuro e ben illuminato senza rischi di inciampo.** [Informazioni su integrità e sicurezza.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Gli accessori di comfort facoltativi** in dotazione con HoloLens, per facilitare la scelta più comoda. [Altre informazioni su adattamento e comfort.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Configurazione di Windows

La prima volta che si avvia il HoloLens 2, la prima attività è configurare Windows Holographic.  Quando si avvia il HoloLens, si ode musica e viene visualizzato un logo Microsoft.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Verrà visualizzato un colibrì che vola in giro.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Seguirà la mano.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Verrà visualizzato un pulsante con un logo Microsoft. Premere il pulsante e HoloLens 2 i passaggi seguenti:

1. Selezionare la lingua.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Selezionare un'area.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Calibrare HoloLens agli occhi.  Se si sceglie di ignorare la calibrazione, verrà richiesto al successivo accesso. 

    1. In primo luogo, si regola la visiera.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Per calibrare, si guarderà un set di destinazioni (definite gemme). Va bene se si lampeggiano o chiudono gli occhi durante la calibrazione, ma si cerca di non guardare altri oggetti nella stanza o nello spazio fisico. HoloLens questo processo per conoscere la posizione dell'occhio in modo che possa eseguire meglio il rendering del mondo olografico. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando la visiera si sposta sulla testa. Le informazioni di calibrazione vengono archiviate in locale nel dispositivo e non sono associate ad alcuna informazione sull'account. Per altre informazioni, vedere [Calibrazione dei dati e della sicurezza](hololens-calibration.md#calibration-data-and-security).

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Connessione a Internet (selezionare Wi-Fi o la connessione ethernet).

     HoloLens il fuso orario automaticamente in base alle informazioni ottenute dalla Wi-Fi rete. Al termine dell'installazione, è possibile modificare il fuso orario usando l Impostazioni app.

    ![Connettersi alla rete Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Se si procede oltre il passaggio Wi-Fi e successivamente è necessario passare a una rete diversa  durante la configurazione, è possibile premere i pulsanti **Volume** giù e Alimentazione contemporaneamente per tornare a questo passaggio se si esegue una versione del sistema operativo da ottobre 2019 o successiva. Per le versioni precedenti, [](hololens-recovery.md) potrebbe essere necessario reimpostare il dispositivo o riavviarlo in un percorso in cui la rete Wi-Fi non è disponibile per impedirne la connessione automatica.
    > 
    > Si noti anche che durante HoloLens configurazione, si verifica un timeout delle credenziali di due minuti. Il nome utente/password deve essere immesso entro due minuti; in caso contrario, il campo del nome utente verrà cancellato automaticamente.

1. HoloLens 2 ricerca e applica un profilo Autopilot, se presente. In questa schermata non è necessaria alcuna azione.
 
    ![Ricerca profilo Autopilot](images/autopilot-profile-search.png) 

1. Fare **clic su Accetta** nella schermata delle licenze.

    ![Windows di licenza](images/windows-license-agreement.png)

1. Accedere al proprio account utente. Si sceglierà tra **Il mio lavoro o l'istituto di istruzione è proprietario** e **il** proprietario è .

    ![Impostare l'utente](images/13-device-owner.png)
    - Quando si sceglie **Appartiene all'azienda o all'istituto di istruzione**, si esegue l'accesso con un account Azure AD. Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione MDM automatica, HoloLens automaticamente in MDM. Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile. In tal caso, è necessario registrare manualmente [HoloLens nella gestione dei dispositivi](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Immettere le informazioni sull'account aziendale.
        1. Accettare l'informativa sulla privacy e il contratto di licenza con l'utente finale.
        1. Accedere usando le credenziali Azure AD utente. Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.
        1. Continuare a configurare il dispositivo.

    - Quando si sceglie **Appartiene a me**, si esegue l'accesso con un account Microsoft. Al termine dell'installazione, è possibile [registrare manualmente HoloLens in Gestione dispositivi](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Immettere le account Microsoft dati.
        2. Immettere la password. Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completare il processo di verifica.

        
1. Configurare l'accesso Iris selezionando **Avanti.** Si passa attraverso un'esperienza simile alla calibrazione oculare. Al **termine dell'analisi,** selezionare Fine. È anche possibile selezionare **Ignora** per ignorare questo passaggio.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Si configura un PIN per accedere al dispositivo. Questo PIN è specifico del dispositivo. 

    ![Configurare Windows Hello](images/setup-windows-hello.png)

    ![Configurare Windows Hello PIN](images/windows-hello-pin.png)

    ![Windows Hello Installazione completata](images/windows-hello-successful.png) 

    
1. Consente di scegliere se abilitare la voce HoloLens 2.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Consente di scegliere se abilitare la posizione HoloLens 2.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Selezionare il livello di telemetria. Se possibile, abilitare i dati di telemetria facoltativi. Queste informazioni sono davvero utili al team HoloLens engineering.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Informazioni su come usare il movimento di inizio HoloLens 2.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Congratulazioni!  La configurazione è stata completata e si è pronti per usare HoloLens.

## <a name="next-steps"></a>Passaggi successivi

1. Iniziare subito a interagire con la realtà mista e Windows 10 nel HoloLens: vedere l'app **Suggerimenti** per esercitazioni pratica sulle interazioni con la mano. Usare il movimento start per passare a Start o pronunciare "Vai a Start" e selezionare Suggerimenti.

1. Fare clic di seguito per continuare a leggere informazioni su come HoloLens 2.

> [!div class="nextstepaction"]
> [Orientarsi in HoloLens 2](hololens2-basic-usage.md)
