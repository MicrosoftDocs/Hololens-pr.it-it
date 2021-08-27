---
title: HoloLens 2 Spostamento della modalità piattaforma
description: Come usare le HoloLens su piattaforme mobili
keywords: piattaforme in movimento, movimento dinamico, hololens, modalità piattaforma mobile
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: cd46e162971ea709d865b2ac998cc7a517d231ec
ms.sourcegitcommit: 18f6c00a57a6b4608dadcec418d1970455d8ee3a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "122989202"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Modalità di spostamento della piattaforma su piattaforme a basso movimento dinamico

Nella **build Insider 20348.1411** è stato aggiunto il supporto beta per il rilevamento di piattaforme con movimento basso dinamico in HoloLens 2. Dopo aver installato la build e aver abilitato la modalità piattaforma mobile, sarà possibile usare il HoloLens 2 in ambienti inaccessibili in precedenza, ad esempio grandi navi e navi di grandi dimensioni. Attualmente, la funzionalità è destinata ad abilitare solo queste piattaforme in movimento specifiche. Sebbene nulla impedisca di provare a usare la funzionalità in altri ambienti, la funzionalità è incentrata sull'aggiunta del supporto per questi ambienti.

> [!NOTE]
> Questa funzionalità è attualmente disponibile solo [tramite Windows Insiders.](hololens-insider.md)

![Esempio di spostamento della piattaforma.](./images/mpm-compare.gif)

Questo articolo riguarda:

1. [Perché è necessario spostare la piattaforma](#why-moving-platform-mode-is-necessary)
1. [Abilitazione della modalità piattaforma mobile](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Perché è necessaria la modalità di spostamento della piattaforma

HoloLens deve essere in grado di tenere traccia della posizione della testa con [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) gradi di libertà (X, Y, Z, traslazione e rollio, passo, rotazione yaw) per mostrare ologrammi stabili. A tale scopo, HoloLens due informazioni simili da due origini separate:

1. Fotocamere di luce visibili, che monitorano l'ambiente, ad esempio la stanza fisica in cui si usa il HoloLens
1. Unità di misura inerziale (IMU), costituita da un accelerometro, un giroscopio e un magnetometro che tiene traccia del movimento della testa e dell'orientamento rispetto alla Terra

Le informazioni provenienti da queste due origini vengono composte per tenere traccia della posizione della testa a una bassa latenza e a una frequenza sufficiente per eseguire il rendering di ologrammi uniformi.

Tuttavia, questo approccio si basa su un presupposto critico; l'ambiente (monitorato dalle fotocamere) rimane fermo rispetto alla Terra (su cui l'IMU può effettuare misurazioni). In caso contrario, ad esempio su una barcone in acqua, le informazioni provenienti da entrambe le origini possono entrare in conflitto tra loro e causare la perdita del tracker. Questo conflitto produce informazioni sulla posizione non corrette e comporta la perdita di ologrammi da acqua o persino il rilevamento della perdita.

Lo spostamento della modalità piattaforma consente di risolvere questo problema. Quando si abilita la modalità piattaforma mobile, questo è un suggerimento per il tracker che non è possibile fare affidamento sugli input del sensore per concordare completamente l'uno con l'altro in qualsiasi momento. È invece necessario affidarsi maggiormente al rilevamento visivo e identificare rapidamente i dati di movimento inerziale incongrui e filtrarli di conseguenza prima di poter usare l'input IMU.

## <a name="supported-environments-and-known-limitations"></a>Ambienti supportati e limitazioni note

Anche se la modalità piattaforma mobile è stata sviluppata per gestire in modo intelligente i casi di conflitto di dati inerziali e visivi, è attualmente in ambito per le grandi navi marine che hanno un movimento a bassa dinamica. Ciò significa che esistono sicuramente limitazioni e scenari non supportati.

### <a name="known-limitations"></a>Limitazioni note

- Gli unici ambienti supportati per la modalità MPM (Moving Platform Mode) sono le grandi navi con movimento a bassa dinamica. In altre parole, molti ambienti/situazioni comuni non sono ancora supportati a causa del movimento ad alta frequenza e dei livelli elevati di accelerazione e [di avallo.](https://en.wikipedia.org/wiki/Jerk_(physics))  Ad esempio: aerei, treni, automobili, biciclette, bus, piccole navi, ascensori e così via.
- Ologrammi può variare leggermente quando MPM è abilitato, soprattutto in caso di acqua squarta.
- Nulla impedisce agli utenti di provare a usare MPM in ambienti non supportati, tuttavia, gli utenti potrebbero sperimentare effetti collaterali indesiderati se il dispositivo è in grado di mantenere il rilevamento nello spazio non supportato. Ad esempio, con MPM, gli utenti possono trovare che sia possibile usare in un ascensore mentre cambiano i piani, mentre in precedenza era impossibile. Sfortunatamente, mentre MPM consente al dispositivo di mantenere il rilevamento, al momento non gestisce la gestione delle mappe. Gli utenti scopriranno che cambiando i piani in un ascensore il dispositivo confonde i piani superiore e inferiore e influisce negativamente sulla qualità della mappa.

## <a name="prerequisites"></a>Prerequisiti

Il supporto beta per la modalità piattaforma mobile richiede solo alcuni prerequisiti:

1. Installare la build 20348.1411 o versione più recente lampeggiando la build insider più recente [tramite ARC](hololens-insider.md#ffu-download-and-flash-directions) o registrando e [aggiornando il dispositivo.](hololens-insider.md#start-receiving-insider-builds)

   > [!NOTE]
   > Questa build è attualmente disponibile solo in [Insider Dev Channel.](hololens-insider.md#start-receiving-insider-builds)

2. Abilitare [la modalità sviluppatore e Portale di dispositivi](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Abilitazione della modalità piattaforma mobile

Per abilitare la modalità Piattaforma mobile, abilitare [prima Portale di dispositivi](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Selezionare **la accordion** Di sistema nel menu a sinistra

   ![Prima immagine](.\images\moving-platform-1w.png)

2. Selezionare la **pagina Modalità piattaforma mobile** e selezionare la casella di controllo Modalità piattaforma **mobile**

    ![Seconda immagine](.\images\moving-platform-2z.png)

3. Quando viene visualizzato un avviso, selezionare **OK**

   ![Terza immagine](.\images\moving-platform-3w.png)

4. Riavviare il dispositivo, che può essere eseguito tramite il **menu** Alimentazione Portale di dispositivi in alto a destra oppure emettendo il comando vocale seguente Riavviare il dispositivo e &quot; selezionare Sì &quot; &quot; &quot; .

   ![Quarta immagine](.\images\moving-platform-4z.png)

Se non è possibile visualizzare l'opzione Modalità piattaforma in Portale di dispositivi, è probabile che non si sia ancora nella compilazione corretta. Vedere la [sezione Prerequisiti.](#prerequisites)

## <a name="reporting-issues"></a>Segnalazione di problemi

Come accennato in precedenza, questa funzionalità è una funzionalità beta disponibile solo in modalità sviluppatore, il che significa che potrebbero verificarsi problemi. In questo caso, in modo da poter analizzare e migliorare il prodotto,

1. Segnalare il problema tramite [Hub di Feedback](hololens-feedback.md) nella categoria accuratezza, stabilità e affidabilità **dell'ologramma** e includere:
    1. Descrizione del problema, incluso il comportamento previsto e il comportamento riscontrato
    1. Acquisizione [video di realtà mista](holographic-photos-and-videos.md#capture-a-mixed-reality-video) del problema
2.  Aprire un caso di supporto in e condividere l'URL Hub di Feedback, in modo da potersi contattare in caso di [https://aka.ms/hlsupport](https://aka.ms/hlsupport) domande di follow-up