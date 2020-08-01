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
# Configurare il dispositivo HoloLens 2

La prima volta che accendi il dispositivo HoloLens, riceverai istruzioni per eseguire la configurazione, l'accesso con un account utente e la calibrazione di HoloLens con gli occhi.  Questa sezione illustra l'esperienza di configurazione iniziale di HoloLens 2.

Nella sezione successiva imparerai a usare HoloLens e interagire con gli ologrammi. Per passare direttamente a questo articolo, vedi [Introduzione a HoloLens 2](hololens2-basic-usage.md).

## Prima di iniziare

Prima di iniziare, assicurati di disporre di quanto segue:

**Una connessione di rete**. Devi connettere il dispositivo HoloLens a una rete per configurarlo. Con HoloLens 2, puoi eseguire la connessione tramite Wi-Fi o Ethernet (è necessario un adattatore da USB-C a Ethernet). La prima volta che effettui la connessione, ti servirà una rete aperta o protetta da password che non richiede l'accesso a un sito Web o l'utilizzo di certificati per la connessione. [Scopri di più sui siti Web usati da HoloLens](hololens-offline.md).

**Un account Microsoft**. Dovrai inoltre accedere a HoloLens con un account Microsoft o, se la tua organizzazione è proprietaria del dispositivo, con un account aziendale. Se non disponi di un account Microsoft, vai a [account.microsoft.com](https://account.microsoft.com) e configurane uno gratuitamente.

**Uno spazio sicuro e ben illuminato senza pericoli**. [Informazioni sulla sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Accessori opzionali per il comfort** forniti con il dispositivo HoloLens, utili per indossarlo in modo confortevole. [Ulteriori informazioni per indossarlo in modo confortevole](hololens2-setup.md#adjust-fit).

## Configurare Windows

La prima volta che avvii HoloLens 2, dovrai innanzitutto configurare Windows Holographic.  Quando avvii HoloLens, viene emessa della musica e viene visualizzato un logo Windows.

![Prima schermata durante il primo avvio](images/01-magic-moment.png)

HoloLens 2 ti guiderà nei passaggi seguenti:

1. Seleziona la tua lingua.
    ![Selezione della lingua](images/04-language.png)

1. Seleziona la tua regione.
    ![Selezione della regione](images/05-region.png)

1. Calibra HoloLens con i tuoi occhi.  Se scegli di ignorare la calibrazione, verrà richiesto di effettuarla al successivo accesso.

    Per eseguire la calibrazione, dovrai guardare una serie di obiettivi (dette gemme). Durante la calibrazione, puoi sbattere o chiudere gli occhi, ma cerca di non fissare altri oggetti presenti nella stanza o nello spazio fisico. HoloLens usa questo processo per ottenere informazioni sulla posizione degli occhi, così da garantire un rendering ottimale del mondo olografico. Dopo la calibrazione, gli ologrammi verranno visualizzati correttamente anche quando la visiera si sposta sulla testa.

    Le informazioni sulla calibrazione vengono memorizzate localmente nel dispositivo e non sono associate alle informazioni sull'account. Per altre informazioni, vedi [Dati di calibrazione e sicurezza](hololens-calibration.md#calibration-data-and-security).

    ![Schermata di selezione della calibrazione](images/06-et-corners.png)

1. Esegui la connessione a Internet (seleziona la rete Wi-Fi o la connessione Ethernet).
     HoloLens imposta automaticamente il fuso orario in base alle informazioni ottenute dalla rete Wi-Fi. Al termine della configurazione, potrai cambiare il fuso orario usando l'app Impostazioni.

    ![Connessione alla rete Wi-Fi](images/11-network.png)
> [!NOTE] 
> Se superi il passaggio Wi-Fi e successivamente devi passare a una rete diversa mentre sei ancora in fase di installazione, puoi premere contemporaneamente i pulsanti di **riduzione volume** e **accensione** per tornare a questo passaggio se esegui una versione del sistema operativo da ottobre 2019 o versione successiva. Per le versioni precedenti, potrebbe essere necessario [reimpostare il dispositivo](hololens-recovery.md) o riavviarlo in un percorso in cui la rete Wi-Fi non è disponibile per impedirne la connessione automatica.
> 
> Tieni inoltre presente che durante l'installazione di HoloLens si verifica un timeout delle credenziali di due minuti. Nome utente/password devono essere immessi entro due minuti, altrimenti il campo nome utente verrà cancellato automaticamente.

1. Accedi al tuo account utente. Potrai scegliere tra **Appartiene all'azienda o all'istituto di istruzione** e **Appartiene a me**.
    - Quando scegli **Appartiene all'azienda o all'istituto di istruzione**, accedi con un account Azure AD. Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione automatica MDM, HoloLens si registra automaticamente in MDM. Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile. In questo caso, dovrai [registrare manualmente HoloLens in gestione dispositivi](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Immetti le informazioni sull'account aziendale.
        1. Accetta l'Informativa sulla privacy e il Contratto di licenza con l'utente finale.
        1. Accedi usando le credenziali di Azure AD. Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.
        1. Continua a configurare il dispositivo.
    - Quando scegli **Appartiene a me**, accedi con un account Microsoft. Al termine della configurazione, puoi [registrare manualmente HoloLens in gestione dispositivi](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Immetti le informazioni sull'account Microsoft.
        2. Immetti la password. Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completa il processo di verifica.

    ![Impostazione dell'utente](images/13-device-owner.png)

1. Seleziona se abilitare la sintesi vocale in HoloLens 2 e se inviare la telemetria di diagnostica.
    ![Abilitazione di Cortana](images/22-do-more-with-voice.png)

1. Seleziona il livello di telemetria. Se possibile, abilita il livello di telemetria completo. Queste informazioni sono veramente utili per il team di sviluppo di HoloLens.
     ![Livello di telemetria](images/24-telemetry.png)

1. Scopri come usare il gesto Start in HoloLens 2.
     ![Informazioni su come usare il gesto Start, immagine 1](images/26-01-startmenu-learning.png) ![Informazioni su come usare il gesto Start, immagine 2](images/26-02-startmenu-learning.png)

Complimenti.  La configurazione è completa. Ora potrai utilizzare HoloLens!

## Passaggi successivi

> [!div class="nextstepaction"]
> [Introduzione a HoloLens 2](hololens2-basic-usage.md)
