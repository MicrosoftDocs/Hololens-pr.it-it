---
title: HoloLens 2 Spostamento della modalità piattaforma
description: Come usare le HoloLens su piattaforme mobili
keywords: spostamento di piattaforme, movimento dinamico, hololens, modalità di spostamento della piattaforma
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
ms.openlocfilehash: 2c0e6e285b2eb86342450e8f05876e0cc3bccfe8
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858647"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Spostamento della modalità piattaforma su piattaforme a movimento dinamico basso

Nella **build Insider 20348.1411** è stato aggiunto il supporto beta per il rilevamento delle piattaforme di spostamento del movimento a bassa dinamica HoloLens 2. Dopo aver installato la compilazione e abilitato la modalità di spostamento della piattaforma, sarà possibile usare il HoloLens 2 in ambienti precedentemente inaccessibili, ad esempio le grandi navi e le grandi navi. Attualmente, la funzionalità è destinata ad abilitare solo queste piattaforme di spostamento specifiche. Anche se nulla impedisce di provare a usare la funzionalità in altri ambienti, la funzionalità è incentrata sull'aggiunta del supporto per questi ambienti.

> [!NOTE]
> Questa funzionalità è attualmente disponibile solo tramite Windows [Insider.](hololens-insider.md)

Questo articolo riguarda:

1. [Perché è necessario spostare la piattaforma](#why-moving-platform-mode-is-necessary)
1. [Abilitazione della modalità di spostamento della piattaforma](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Perché è necessario spostare la modalità piattaforma

HoloLens deve essere in grado di tenere traccia della posizione della testa con [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) gradi di libertà (traslazione X, Y, Z e rullo, passo, rotazione di yaw) per mostrare ologrammi stabili. A tale scopo, HoloLens traccia di due informazioni simili da due origini separate:

1. Fotocamere di luce visibili, che tracciano l'ambiente, ad esempio la stanza fisica in cui si sta usando il HoloLens
1. Unità di misura inerziale (IMU), costituita da un accelerometro, un giroscopio e un magnetometro che tiene traccia del movimento e dell'orientamento della testa rispetto alla Terra

Le informazioni provenienti da queste due origini vengono composte per tenere traccia della posizione della testa a una bassa latenza e a una frequenza sufficientemente elevata per eseguire il rendering di ologrammi uniformi.

Tuttavia, questo approccio si basa su un presupposto critico. L'ambiente (monitorato dalle fotocamere) rimane stazionaria rispetto alla Terra (su cui l'IMU può effettuare misurazioni). Quando questo non è il caso, ad esempio in un'acqua, le informazioni provenienti da entrambe le fonti possono entrare in conflitto tra loro e causare la perdita del tracciatore. Questo conflitto produce informazioni sulla posizione non corrette e comporta la perdita di ologrammi o di tracciabilità.

Lo spostamento della modalità piattaforma consente di risolvere questo problema. Quando si abilita la modalità di spostamento della piattaforma, questo è un suggerimento per lo tracker che non è possibile fare affidamento sugli input del sensore per concordare completamente l'uno con l'altro in qualsiasi momento. È invece necessario fare più affidamento sul rilevamento visivo e identificare rapidamente i dati di movimento inerziale incongrui e filtrarli di conseguenza prima di&#39;possibile usare di nuovo l'input IMU.

## <a name="supported-environments-and-known-limitations"></a>Ambienti supportati e limitazioni note

Anche se la modalità di spostamento della piattaforma è stata sviluppata per gestire in modo intelligente i casi di conflitto di dati inerziali e visivi, l'ambito è attualmente quello di grandi dimensioni in cui si verifica un movimento poco dinamico. Questo significa che esistono sicuramente limitazioni e scenari non supportati.

### <a name="known-limitations"></a>Limitazioni note

- Gli unici ambienti supportati per la modalità MPM (Moving Platform Mode) sono grandi ambienti in cui il movimento è poco dinamico. In altre parole, molti ambienti/situazioni comuni non sono ancora supportati a causa del movimento ad alta frequenza e dei livelli elevati di accelerazione [e accelerazione.](https://en.wikipedia.org/wiki/Jerk_(physics))  Ad esempio: aerei, veicoli, automobili, biciclette, bus, piccoli passeggeri, ascensori e così via.
- Ologrammi può traballare leggermente quando mpm è abilitato, soprattutto in caso di acqua poco sicura.
- Nulla impedisce agli utenti di provare a usare MPM in ambienti non supportati, tuttavia gli utenti potrebbero sperimentare effetti collaterali indesiderati se il dispositivo è in grado di mantenere il rilevamento nello spazio non supportato. Con MPM, ad esempio, gli utenti potrebbero trovare&#39;possibile usare in un ascensore durante il cambio dei piani, mentre in precedenza era impossibile. Sfortunatamente, anche se MPM consente al dispositivo di mantenere il rilevamento, al momento non gestisce la gestione delle mappe. Gli utenti scopriranno quindi che il cambiamento dei piani in un ascensore causerà la confusione dei piani superiori e inferiori e influirà negativamente sulla qualità della mappa.

## <a name="prerequisites"></a>Prerequisiti

Il supporto beta per lo spostamento della modalità piattaforma richiede solo alcuni prerequisiti:

1. Installare la build 20348.1411 o versione più recente tramite [flashing](hololens-insider.md#ffu-download-and-flash-directions) della build Insider più recente tramite ARC o registrando e aggiornando [il dispositivo.](hololens-insider.md#start-receiving-insider-builds)
   - Nota: questa build è attualmente disponibile solo nel [canale Insider Dev.](hololens-insider.md#start-receiving-insider-builds)
2. Abilitare [la modalità sviluppatore e Portale di dispositivi](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Abilitazione della modalità di spostamento della piattaforma

Per abilitare la modalità di spostamento della piattaforma, [abilitare prima Portale di dispositivi](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Selezionare la **accordion** System (Sistema) nel menu a sinistra
2. Selezionare la **pagina Moving Platform Mode (Modalità di spostamento** della piattaforma) e selezionare la casella di controllo Moving Platform Mode **(Modalità di spostamento della** piattaforma)

![Prima immagine](.\images\moving-platform-1.png) ![Seconda immagine](.\images\moving-platform-2.png)

3. Quando viene visualizzato un avviso, selezionare **OK**

![Terza immagine](.\images\moving-platform-3.png)

4. Riavviare il dispositivo, che può essere eseguito tramite il **menu** Di alimentazione di Portale di dispositivi in alto a destra oppure emettendo il comando vocale seguente Riavviare il dispositivo e &quot; selezionare &quot; &quot; &quot; Sì.

![Quarta immagine](.\images\moving-platform-4.png)

Se non è possibile visualizzare l'opzione Moving Platform Mode (Modalità di spostamento della piattaforma) in Portale di dispositivi, è probabile che non si sia ancora nella compilazione corretta. Vedere la [sezione Prerequisiti.](#prerequisites)