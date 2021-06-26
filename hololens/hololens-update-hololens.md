---
title: Aggiornare HoloLens 2
description: Informazioni su come controllare il numero di build di HoloLens, mantenersi aggiornati con gli aggiornamenti del dispositivo, partecipare al programma Insiders ed eseguire il rollback degli aggiornamenti.
keywords: procedura, aggiornamento, rollback, HoloLens, controllo della compilazione, numero di build
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924112"
---
# <a name="update-hololens-2"></a>Aggiornare HoloLens 2

HoloLens usa Windows Update, proprio come altri Windows 10 dispositivi. HoloLens scarica e installa automaticamente gli aggiornamenti di sistema ogni volta che è collegato all'alimentazione e connesso a Internet, anche quando è in standby.

Questo articolo illustra gli strumenti di HoloLens per:

- visualizzazione della versione corrente del sistema operativo (numero di build)
- controllo della disponibilità di aggiornamenti
- aggiornamento manuale di HoloLens
- rollback a un aggiornamento precedente

## <a name="check-your-operating-system-version-build-number"></a>Controllare la versione del sistema operativo (numero di build)

È possibile verificare il numero di versione del sistema (numero di build) aprendo l'app Impostazioni e selezionando **Informazioni**  >  **sul sistema.**

## <a name="check-for-updates-and-manually-update"></a>Verificare la disponibilità di aggiornamenti e aggiornare manualmente

È possibile verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.  Per visualizzare gli aggiornamenti disponibili e verificare la presenza di nuovi aggiornamenti:

1. Aprire l'app **Impostazioni**.
1. Passare a **Update & Security**  >  **Windows Update**.
1. Selezionare **Verifica disponibilità aggiornamenti**.

Se è disponibile un aggiornamento, inizierà a scaricare la nuova versione. Al termine del download, selezionare il pulsante **Riavvia** ora per attivare l'installazione. Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.

Durante l'installazione dell'aggiornamento, HoloLens visualizza ingranaggi rotanti e un indicatore di stato. Non disattivare HoloLens durante questo periodo. Verrà riavviato automaticamente al termine dell'installazione.

HoloLens applica un aggiornamento alla volta.  Se HoloLens è più di una versione rispetto alla versione più recente, potrebbe essere necessario eseguire più volte il processo di aggiornamento per aggiornarlo completamente.

## <a name="go-back-to-a-previous-version"></a>Tornare a una versione precedente

In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens. I passaggi consigliati sono:

1. Contattare il supporto tecnico per verificare se è possibile risolvere il problema.
    1. Assicurarsi che **i dati di** **telemetria** facoltativi o completi siano abilitati, in modo da rendere il bug più gestibile e più semplice da diagnosticare per i tecnici.
    1. [Il feedback dei](hololens-feedback.md) file è il più descrittivo possibile. Prendere nota del titolo o usare la funzionalità di condivisione per condividere il bug con il supporto tecnico.
    1. Contattare [il supporto](https://aka.ms/hlsupport)tecnico . Se il problema è quello che deve essere risolto tornando a una versione precedente, possono fornire l'FFU per eseguire il flashing del dispositivo.

1. Se non funziona, reimpostare o convertire il HoloLens 2 [con Advanced Recovery Companion.](hololens-recovery.md)
    1. Nel PC scaricare [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dal Microsoft Store.
    1. Assicurarsi di non avere telefoni o dispositivi Windows collegati al PC.
    1. Scegliere la versione in cui si vuole eseguire il flash:
        1. È possibile scaricare la [versione più recente HoloLens 2 versione](https://aka.ms/hololens2download).
        1. È possibile usare la compilazione predefinita ospitata da ARC. Se si sceglie questa opzione, ignorare il passaggio successivo.
        1. È possibile usare un supporto di compilazione fornito con .
    1. Al termine di questi download, **aprire** Esplora file  >  **Download**. Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.
    1. Connettere HoloLens al PC usando un cavo DA USB A a USB-C. Anche se si usano altri cavi per connettere HoloLens, questo funziona meglio.
    1. Advanced Recovery Companion rileva automaticamente HoloLens. Selezionare il **Microsoft HoloLens** riquadro.
    1. Nella schermata successiva selezionare **Selezione** pacchetto manuale e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con estensione ffu.
    1. Selezionare **Installa software** e seguire le istruzioni.

> [!NOTE]
> Tornando a una versione precedente, i file e le impostazioni personali vengono eliminati.

Inoltre, se si vuole rimanere nella versione attualmente installata, è anche possibile sospendere manualmente [gli aggiornamenti](hololens-updates.md#pause-updates-via-device). In questo modo il team di progettazione avrà il tempo di risolvere il problema.

## <a name="windows-insider-program-on-hololens"></a>Programma Windows Insider su HoloLens

Per visualizzare le funzionalità più recenti in HoloLens,  In tal caso, aggiungere il Programma Windows Insider; Si otterrà l'accesso alle build di anteprima degli aggiornamenti software HoloLens prima che siano disponibili per il pubblico generale.

[Ottenere partecipante al Programma Windows Insider anteprima per Microsoft HoloLens](hololens-insider.md).
