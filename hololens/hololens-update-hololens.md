---
title: Aggiornare HoloLens 2
description: Informazioni su come controllare il numero HoloLens build, mantenersi aggiornati con gli aggiornamenti dei dispositivi, partecipare al programma Insiders ed eseguire il rollback degli aggiornamenti.
keywords: procedura, aggiornamento, rollback, HoloLens, controllare la compilazione, numero di build
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
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662844"
---
# <a name="update-hololens-2"></a>Aggiornare HoloLens 2

HoloLens usa Windows Update, proprio come altri Windows 10 dispositivi. Il HoloLens scarica e installa automaticamente gli aggiornamenti di sistema ogni volta che è collegato all'alimentazione e connesso a Internet, anche quando è in standby.

Questo articolo illustra in modo HoloLens strumenti per:

- visualizzazione della versione corrente del sistema operativo (numero di build)
- controllo della disponibilità di aggiornamenti
- aggiornamento manuale HoloLens
- rollback a un aggiornamento precedente

## <a name="check-your-operating-system-version-build-number"></a>Controllare la versione del sistema operativo (numero di build)

È possibile verificare il numero di versione del sistema (numero di build) aprendo l'app Impostazioni e selezionando **Informazioni**  >  **sul sistema.**

## <a name="check-for-updates-and-manually-update"></a>Verificare la disponibilità di aggiornamenti e aggiornare manualmente

È possibile verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.  Per visualizzare gli aggiornamenti disponibili e verificare la presenza di nuovi aggiornamenti:

1. Aprire l'app **Impostazioni**.
1. Passare a **Update & Security** Windows  >  **Update**.
1. Selezionare **Verifica disponibilità aggiornamenti**.

Se è disponibile un aggiornamento, inizierà a scaricare la nuova versione. Al termine del download, selezionare il pulsante **Riavvia** ora per attivare l'installazione. Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.

Mentre il HoloLens sta installando l'aggiornamento, verranno visualizzati ingranaggi rotanti e un indicatore di stato. Non disattivare la HoloLens durante questo periodo. Verrà riavviato automaticamente al termine dell'installazione.

HoloLens applica un aggiornamento alla volta.  Se il HoloLens è più di una versione rispetto alla versione più recente, potrebbe essere necessario eseguire più volte il processo di aggiornamento per aggiornarlo completamente.

## <a name="go-back-to-a-previous-version"></a>Tornare a una versione precedente

In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens software. I passaggi consigliati sono:

1. Contattare il supporto tecnico per verificare se è possibile risolvere il problema.
    1. Assicurarsi che **la telemetria** facoltativa **o** completa sia abilitata, in modo da rendere il bug più gestibile e più semplice da diagnosticare per i tecnici.
    1. [Il feedback dei](hololens-feedback.md) file è il più descrittivo possibile. Prendere nota del titolo o usare la funzionalità di condivisione per condividere il bug con il supporto tecnico.
    1. Contattare [il supporto](https://aka.ms/hlsupport)tecnico . Se il problema è quello che deve essere risolto tornando a una versione precedente, possono fornire l'FFU per eseguire il flashing del dispositivo.

1. Se il problema non funziona, reimpostare o convertire il HoloLens 2 [con Advanced Recovery Companion.](hololens-recovery.md)
    1. Nel PC scaricare [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dal Microsoft Store.
    1. Assicurarsi di non avere telefoni o dispositivi Windows collegati al PC.
    1. Scegliere la versione in cui si vuole eseguire il flash:
        1. È possibile scaricare la [versione più recente HoloLens 2 versione](https://aka.ms/hololens2download).
        1. È possibile usare la compilazione predefinita ospitata da ARC. Se si sceglie questa opzione, ignorare il passaggio successivo.
        1. È possibile usare un supporto di compilazione fornito con .
    1. Al termine di questi download, **aprire** Esplora file  >  **Download**. Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.
    1. Connessione il HoloLens al PC usando un cavo da USB A a USB-C. Anche se si usano altri cavi per connettere il HoloLens, questo funziona meglio.
    1. Advanced Recovery Companion rileva automaticamente il HoloLens. Selezionare il **Microsoft HoloLens** riquadro.
    1. Nella schermata successiva selezionare **Selezione** pacchetto manuale e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con estensione ffu.
    1. Selezionare **Installa software** e seguire le istruzioni.

> [!NOTE]
> Tornando a una versione precedente, i file e le impostazioni personali vengono eliminati.

Inoltre, se si vuole rimanere nella versione attualmente installata, è anche possibile sospendere manualmente [gli aggiornamenti](hololens-updates.md#pause-updates-via-device). In questo modo il team di progettazione avrà il tempo di risolvere il problema.

## <a name="windows-insider-program-on-hololens"></a>Windows Programma Insider in HoloLens

Per visualizzare le funzionalità più recenti in HoloLens?  In tal caso, aggiungere il Windows Programma Insider; si otterrà l'accesso alle build di anteprima HoloLens aggiornamenti software prima che siano disponibili per il pubblico generale.

[Ottenere Windows Insider Preview per Microsoft HoloLens](hololens-insider.md).
