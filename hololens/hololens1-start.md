---
title: Configurare il dispositivo HoloLens (prima generazione)
description: Questa guida illustra come eseguire la configurazione per la prima volta.  Ti servirà una rete Wi-Fi e un account Microsoft o Azure Active Directory (Azure AD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 042856de2b89395fa0168d90515a7700298087f1
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829465"
---
# Configurare HoloLens (prima generazione)

La prima volta che accendi il dispositivo HoloLens, riceverai istruzioni per eseguire la calibrazione, la configurazione e l'accesso.  Questo articolo illustra come eseguire il primo avvio e configurare HoloLens (prima generazione).

Nella sezione successiva imparerai a usare HoloLens e interagire con gli ologrammi. Per ignorare questo articolo, vedi [Introduzione a HoloLens (prima generazione)](hololens1-basic-usage.md).

## Prima di iniziare

Prima di iniziare, assicurati di disporre di quanto segue:

**Una connessione Wi-Fi**. Dovrai connettere il tuo dispositivo HoloLens a una rete Wi-Fi per configurarlo. La prima volta che effettui la connessione, ti servirà una rete aperta o protetta da password che non richiede l'accesso a un sito Web o l'utilizzo di certificati per la connessione. [Scopri di più sui siti Web usati da HoloLens](hololens-offline.md).

**Un account Microsoft o un account aziendale**. Dovrai anche usare un account Microsoft o, se la tua organizzazione è proprietaria del dispositivo, un account aziendale per accedere a HoloLens. Se non disponi di un account Microsoft, vai a [account.microsoft.com](https://account.microsoft.com) e configurane uno gratuitamente.

**Uno spazio sicuro e ben illuminato senza pericoli**. [Informazioni sulla sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Accessori opzionali per il comfort** forniti con il dispositivo HoloLens, utili per indossarlo in modo confortevole. [Ulteriori informazioni per indossarlo in modo confortevole](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - La prima volta che usi il tuo dispositivo HoloLens, [Cortana](hololens-cortana.md) è già attiva e pronta per guidarti (sebbene sarà in grado di rispondere alle tue domande solo dopo che avrai configurato il dispositivo). Puoi disattivare Cortana in qualsiasi momento tramite le relative impostazioni.
> - Per passare alla versione cinese o giapponese di HoloLens, dovrai scaricare la build per la lingua desiderata in un PC e quindi installarla nel tuo dispositivo HoloLens. Per altre informazioni, vedi [Installare versioni localizzate di HoloLens (prima generazione)](hololens1-install-localized.md).

## Avviare il dispositivo Hololens e configurare Windows

La prima volta che avvii HoloLens, dovrai innanzitutto configurare Windows Holographic nel tuo dispositivo.

1. Connettiti a Internet (HoloLens ti guida per selezionare la rete Wi-Fi).

1. Accedi al tuo account utente. Scegli tra **Appartiene all'azienda o all'istituto di istruzione** e **Appartiene a me**.
    - Quando scegli **Appartiene all'azienda o all'istituto di istruzione**, accedi usando un account Azure AD. Se l'organizzazione usa Azure AD Premium e ha configurato la registrazione automatica MDM, HoloLens si registra automaticamente in MDM. Se l'organizzazione non usa Azure AD Premium, la registrazione MDM automatica non è disponibile, quindi dovrai [registrare manualmente HoloLens nella gestione dispositivi](hololens-enroll-mdm.md#enroll-through-settings-app). Per accedere al dispositivo per la prima volta usando un account aziendale o dell'istituto di istruzione, effettua quanto segue:
        1. Immetti le informazioni sull'account aziendale.
        1. Accettare l'Informativa sulla privacy.
        1. Accedi usando le credenziali di Azure AD. Potresti essere reindirizzato alla pagina di accesso dell'organizzazione.
        1. Continua a configurare il dispositivo.
    - Quando scegli **Appartiene a me**, accedi usando un account Microsoft. Al termine della configurazione, puoi [registrare manualmente HoloLens in gestione dispositivi](hololens-enroll-mdm.md#enroll-through-settings-app).
        1. Immetti le informazioni sull'account Microsoft.
        1. Immettere la password. Se l'account Microsoft richiede la [verifica in due passaggi (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completare il processo di verifica.

1. Il dispositivo imposta il fuso orario in base alle informazioni ottenute dalla rete Wi-Fi.

## Calibrazione

Dopo l'introduzione di Cortana, il passaggio di configurazione successivo è la calibrazione. Per una migliore esperienza di HoloLens, è consigliabile completare il processo di calibrazione durante l'installazione.

HoloLens (prima generazione) usa la distanza tra le tue pupille ([distanza interpupillare](https://en.wikipedia.org/wiki/Interpupillary_distance)) per rendere l'interazione con gli ologrammi chiara e facile. Se la distanza interpupillare non è corretta, gli ologrammi potrebbero sembrare instabili o a una distanza errata.

Durante la calibrazione, HoloLens chiede di allineare il dito con una serie di sei obiettivi per occhio. HoloLens usa questo processo per impostare la distanza interpupillare corretta per gli occhi. Se la calibrazione deve essere aggiornata o regolata per un nuovo utente, quest'ultimo può eseguire l'app Calibrazione al di fuori della configurazione.

![Schermata di allineamento della distanza oculare tramite dita, seconda fase](./images/ipd-finger-alignment-300px.jpg)

*Schermata di allineamento della distanza oculare tramite dita, seconda fase*

A questo punto, La configurazione è completa ed è possibile iniziare a usare HoloLens.

## Passaggi successivi

> [!div class="nextstepaction"]
> [Informazioni di base su HoloLens (prima generazione)](hololens1-basic-usage.md)
