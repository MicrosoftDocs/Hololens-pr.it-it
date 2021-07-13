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
# <a name="set-up-your-hololens-2"></a>Configurare l'HoloLens 2

La prima volta che si attiva il HoloLens, si verrà guidati nella configurazione del dispositivo, nell'accesso con un account utente e nella calibrazione del HoloLens agli occhi.  In questa sezione viene illustrata la HoloLens 2 configurazione iniziale.

Nella sezione successiva si apprenderà come usare le HoloLens e interagire con gli ologrammi. Per passare direttamente a questo articolo, vedere [Getting around HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Prima di iniziare

Prima di iniziare, verificare che siano disponibili gli elementi seguenti:

**Una connessione di rete**. È necessario connettere il HoloLens a una rete per configurarlo. Con HoloLens 2, è possibile connettersi con Wi-Fi o tramite ethernet (è necessaria una scheda USB-C-Ethernet). La prima volta che ci si connette, è necessaria una rete aperta o protetta da password che non richiede il passaggio a un sito Web o l'uso di certificati per la connessione. [Altre informazioni sui siti Web che HoloLens usa](hololens-offline.md).

**Oggetto account Microsoft**. È anche necessario accedere a un HoloLens con un account Microsoft (o con l'account aziendale, se l'organizzazione è proprietaria del dispositivo). Se non si ha una account Microsoft, passare a [account.microsoft.com](https://account.microsoft.com) e configurarne una gratuitamente.

**Uno spazio sicuro e ben acceso senza rischi di inciampo.** [Informazioni su integrità e sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Gli accessori di comfort** facoltativi che sono stati HoloLens, per facilitare la scelta più comoda. [Altre informazioni su fit e comfort.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Configurazione di Windows

La prima volta che si avvia HoloLens 2, la prima attività è la configurazione Windows Holographic.  Quando si avvia il HoloLens, si riceverà musica e verrà visualizzato Windows logo.

![Prima schermata durante il primo avvio](images/01-magic-moment.png)

Verrà visualizzato un colibrì che si aggira.

![Hummingbirdbird](images/hummingbird-1.png)

Seguirlo con la mano.

![Hummingbird al primo volo](images/hummingbird-2.png)

HoloLens 2 illustra i passaggi seguenti:

1. Selezionare la lingua.

    ![Seleziona lingua](images/04-language.png)

1. Selezionare un'area.

    ![Selezionare l'area](images/05-region.png)

1. Calibrare HoloLens agli occhi.  Se si sceglie di ignorare la calibrazione, verrà richiesto al successivo accesso. 

    1. Prima di tutto, si regola il visore.
    
        ![Schermata di selezione della calibrazione](images/06-et-corners.png)

    2. Per calibrare, si animerà un set di destinazioni (denominate gemme). È possibile lampeggiare o chiudere gli occhi durante la calibrazione, ma provare a non guardare altri oggetti nella stanza o nello spazio fisico. HoloLens usa questo processo per ottenere informazioni sulla posizione dell'occhio in modo da migliorare il rendering del mondo olografico. 

        ![Regola per gli occhi](images/07-adjust-eyes.png)

        Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando il visore si sposta sulla testa. Le informazioni di calibrazione vengono archiviate localmente nel dispositivo e non sono associate ad alcuna informazione sull'account. Per altre informazioni, vedere [Calibrazione dei dati e sicurezza.](hololens-calibration.md#calibration-data-and-security)

        ![Calibrazione completata](images/calibration-complete.png)

1. Connessione a Internet (selezionare Wi-Fi o la connessione ethernet).

     HoloLens imposta automaticamente il fuso orario in base alle informazioni ottenute dalla Wi-Fi rete. Al termine dell'installazione, è possibile modificare il fuso orario usando l Impostazioni app.

    ![Connettersi alla rete Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Se si procede oltre il passaggio Wi-Fi e successivamente è necessario passare a una rete diversa  durante la configurazione, è possibile premere i pulsanti **Volume** in basso e Alimentazione contemporaneamente per tornare a questo passaggio se si esegue una versione del sistema operativo da ottobre 2019 o versioni successive. Per le versioni precedenti, [](hololens-recovery.md) potrebbe essere necessario reimpostare il dispositivo o riavviarlo in una posizione in cui la rete Wi-Fi non è disponibile per impedirne la connessione automatica.
    > 
    > Si noti anche che, durante HoloLens di installazione, si verifica un timeout delle credenziali di due minuti. Il nome utente/password deve essere immesso entro due minuti. In caso contrario, il campo del nome utente verrà cancellato automaticamente.

1. HoloLens 2 ricerca e applica un profilo Autopilot, se esistente. In questa schermata non è necessaria alcuna azione.
 
    ![Ricerca nel profilo di Autopilot](images/autopilot-profile-search.png) 

1. Fare **clic su** Accetta nella schermata delle licenze.

    ![Windows contratto di licenza](images/windows-license-agreement.png)

1. Accedere al proprio account utente. Si sceglierà tra My work or school owns it and I own it ( Il mio lavoro **o l'istituto di** istruzione ne è il proprietario ed è il mio **proprietario).**

    ![Impostare l'utente](images/13-device-owner.png)
    - Quando si sceglie **Appartiene all'azienda o all'istituto di istruzione**, si esegue l'accesso con un account Azure AD. Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione MDM automatica, HoloLens automaticamente la registrazione in MDM. Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile. In tal caso, è necessario registrare [manualmente i HoloLens nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Immettere le informazioni sull'account aziendale.
        1. Accettare l'informativa sulla privacy e il contratto di licenza con l'utente finale.
        1. Accedere usando le credenziali Azure AD utente. Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.
        1. Continuare a configurare il dispositivo.

    - Quando si sceglie **Appartiene a me**, si esegue l'accesso con un account Microsoft. Al termine dell'installazione, è possibile [registrare manualmente HoloLens nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Immettere le informazioni account Microsoft dati.
        2. Immettere la password. Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completare il processo di verifica.

        
1. Configurare l'accesso Iris selezionando **Avanti.** Si sperimenterà un'esperienza simile alla calibrazione oculare. Al **termine dell'analisi,** selezionare Fine. È anche possibile selezionare **Ignora per** ignorare questo passaggio.
    
    ![Completamento ](images/setup-iris.png) ![ dell'installazione di Iris Iris](images/iris-setup-complete.png) 
     
  
1. Si configura un PIN per accedere al dispositivo. Questo PIN è specifico del dispositivo. 

    ![Configurare Windows Hello](images/setup-windows-hello.png)

    ![Configurare Windows Hello PIN](images/windows-hello-pin.png)

    ![Windows Hello Installazione completata](images/windows-hello-successful.png) 
    
1. Scegliere se abilitare il riconoscimento vocale HoloLens 2.

    ![Abilitare Cortana](images/22-do-more-with-voice.png)

1. Specificare se abilitare la posizione nella HoloLens 2.
    
    ![Abilitare i servizi di posizione](images/setup-location-services.png)

1. Selezionare il livello di telemetria. Se possibile, abilitare i dati di telemetria facoltativi. Queste informazioni sono molto utili per HoloLens team di progettazione.

     ![Livello di telemetria](images/24-telemetry.png)

1. Informazioni su come usare il movimento di avvio HoloLens 2.

     ![Informazioni su come usare il movimento di avvio, immagine 1](images/26-01-startmenu-learning.png)

     ![Informazioni su come usare il movimento di avvio, immagine 2](images/26-02-startmenu-learning.png)

Congratulazioni!  L'installazione è stata completata e si è pronti per usare HoloLens.

## <a name="next-steps"></a>Passaggi successivi

1. Iniziare **subito a** interagire con la realtà mista ed esplorare Windows 10 sul HoloLens: vedere l'app Suggerimenti per esercitazioni pratica sulle interazioni con la mano. Usare il movimento start per passare a Start o pronunciare "Vai a Start" e selezionare Suggerimenti.

1. Fare clic di seguito per continuare a leggere informazioni su come HoloLens 2.

> [!div class="nextstepaction"]
> [Orientarsi in HoloLens 2](hololens2-basic-usage.md)
