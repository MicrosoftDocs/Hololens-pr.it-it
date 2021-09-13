---
title: Configurare HoloLens (prima generazione)
description: Informazioni su come configurare l'HoloLens (prima generazione) per la prima volta in una rete Wi-Fi con un account Microsoft (MSA) o Azure Active Directory (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033632"
---
# <a name="set-up-your-hololens-1st-gen"></a>Configurare la HoloLens (prima generazione)

La prima volta che si attiva il HoloLens, si verrà guidati nella calibrazione del dispositivo, nella configurazione del dispositivo e nell'accesso.  Questo articolo illustra in modo HoloLens di avvio e configurazione della prima generazione.

Nella sezione successiva si apprenderà come usare le HoloLens e interagire con gli ologrammi. Per passare direttamente a questo articolo, vedere [Introduzione a HoloLens (prima generazione).](hololens1-basic-usage.md)

## <a name="before-you-start"></a>Prima di iniziare

Prima di iniziare, verificare che siano disponibili gli elementi seguenti:

**Una Wi-Fi connessione .** È necessario connettere il HoloLens a una rete Wi-Fi per configurarlo. La prima volta che ci si connette, è necessaria una rete aperta o protetta da password che non richiede il passaggio a un sito Web o l'uso di certificati per la connessione. [Altre informazioni sui siti Web che HoloLens usa](hololens-offline.md).

**Un account Microsoft o un account aziendale.** È anche necessario usare un account Microsoft (o un account aziendale, se l'organizzazione è proprietaria del dispositivo) per accedere a HoloLens. Se non si ha una account Microsoft, passare a [account.microsoft.com](https://account.microsoft.com) e configurarne una gratuitamente.

**Uno spazio sicuro e ben acceso senza rischi di inciampo.** [Informazioni su integrità e sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Gli accessori di comfort** facoltativi che sono stati HoloLens, per facilitare l'adattamento. [Altre informazioni su fit e comfort.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - La prima volta che si usa il HoloLens, [Cortana](hololens-cortana.md) è già disponibile e pronto per l'utente(anche se non sarà in grado di rispondere alle domande finché non si è configurato il dispositivo). È possibile disattivare Cortana in qualsiasi momento nelle Cortana delle impostazioni.
> - Per passare alla versione cinese o giapponese di HoloLens, è necessario scaricare la build per la lingua in un PC e quindi installarla nel HoloLens. Per altre informazioni, vedere [Installare le versioni localizzate di HoloLens (prima generazione).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Avviare Hololens e configurare Windows

La prima volta che si avvia HoloLens, la prima attività è la configurazione Windows Holographic nel dispositivo.

1. Connessione a Internet (HoloLens consente di selezionare Wi-Fi rete.

1. Accedere al proprio account utente. Scegliere tra **My work or school owns it** and I own **it**.
    - Quando si sceglie **My work or school owns it**(Il mio account aziendale o dell'istituto di istruzione è proprietario), si accede con un account Azure AD personale. Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione MDM automatica, HoloLens automaticamente la registrazione in MDM. Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile, quindi sarà necessario registrare manualmente HoloLens [nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll) Per accedere al dispositivo la prima volta usando un account aziendale o dell'istituto di istruzione, seguire questa procedura:
        1. Immettere le informazioni sull'account aziendale.
        1. Accettare l'informativa sulla privacy.
        1. Accedere usando le credenziali Azure AD utente. Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.
        1. Continuare a configurare il dispositivo.
    - Quando si sceglie **È proprietario,** si accede usando un account Microsoft. Al termine dell'installazione, è possibile [registrare manualmente HoloLens nella gestione dei dispositivi.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Immettere le informazioni account Microsoft dati.
        1. Immettere la password. Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completare il processo di verifica.

1. Il dispositivo imposta il fuso orario in base alle informazioni che ottiene dalla Wi-Fi rete.

## <a name="calibration"></a>Calibrazione

Dopo Cortana si presenta, il passaggio di configurazione successivo è la calibrazione. Per un'esperienza HoloLens, è consigliabile completare il processo di calibrazione durante l'installazione.

HoloLens (prima generazione) usa la distanza tra la distanza tra le persone (IPD o distanza [interpuperiale)](https://en.wikipedia.org/wiki/Interpupillary_distance)per rendere gli ologrammi chiari e facili da interagire. Se l'IPD non è corretto, gli ologrammi possono sembrare instabili o a una distanza non corretta.

Durante la calibrazione, HoloLens chiede di allineare il dito con una serie di sei destinazioni per occhio. HoloLens usa questo processo per impostare l'IPD corretto per gli occhi. Se la calibrazione deve essere aggiornata o modificata per un nuovo utente, il nuovo utente può eseguire l'app Calibrazione al di fuori dell'installazione.

![Schermata di allineamento del dito IPD nel secondo passaggio.](./images/ipd-finger-alignment-300px.jpg)

*Schermata di allineamento del dito IPD nel secondo passaggio*

La procedura è stata completata. L'installazione è stata completata ed è possibile iniziare a usare HoloLens.

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Introduzione all'HoloLens (prima generazione)](hololens1-basic-usage.md)
