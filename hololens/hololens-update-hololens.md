---
title: Aggiornare HoloLens
description: Scopri come controllare il numero di build di HoloLens, rimanere aggiornati con gli aggiornamenti del dispositivo, partecipare al programma Insider ed eseguire il rollback degli aggiornamenti.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309514"
---
# <a name="update-hololens"></a>Aggiornare HoloLens

HoloLens usa Windows Update, proprio come altri Windows 10 dispositivi. HoloLens scaricherà e installerà automaticamente gli aggiornamenti di sistema ogni volta che è collegato all'alimentazione e connesso a Internet, anche quando è in standby.

Questo articolo illustra gli strumenti di HoloLens per:

- visualizzazione della versione corrente del sistema operativo (numero di build)
- controllo della disponibilità di aggiornamenti
- aggiornamento manuale di HoloLens
- rollback a un aggiornamento precedente

## <a name="check-your-operating-system-version-build-number"></a>Controllare la versione del sistema operativo (numero di build)

È possibile verificare il numero di versione del sistema (numero di build) aprendo l'app Impostazioni e selezionando **Informazioni**  >  **sul sistema.**

## <a name="check-for-updates-and-manually-update"></a>Verificare la disponibilità di aggiornamenti e aggiornare manualmente

È possibile verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.  Per visualizzare gli aggiornamenti disponibili e verificare la disponibilità di nuovi aggiornamenti:

1. Aprire l'app **Impostazioni**.
1. Passare a **Aggiorna & sicurezza**  >  **Windows Update**.
1. Selezionare **Verifica disponibilità aggiornamenti**.

Se è disponibile un aggiornamento, verrà avviato il download della nuova versione. Al termine del download, selezionare il pulsante **Riavvia ora** per attivare l'installazione. Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.

Durante l'installazione dell'aggiornamento, HoloLens visualizza ingranaggi rotanti e un indicatore di stato. Non disattivare HoloLens durante questo periodo. Verrà riavviato automaticamente al termine dell'installazione.

HoloLens applica un aggiornamento alla volta.  Se HoloLens è più di una versione rispetto alla versione più recente, potrebbe essere necessario eseguire più volte il processo di aggiornamento per aggiornarlo completamente.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Tornare a una versione precedente - HoloLens 2

In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens. È possibile eseguire questa operazione usando Advanced Recovery Companion per reimpostare HoloLens alla versione precedente.

> [!NOTE]
> Tornando a una versione precedente, i file e le impostazioni personali vengono eliminati.

Per tornare a una versione precedente di HoloLens 2, seguire questa procedura:

1. Assicurarsi di non avere telefoni o dispositivi Windows collegati al PC.
1. Nel PC scaricare [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dal Microsoft Store.
1. Scaricare la [versione più recente HoloLens 2 .](https://aka.ms/hololens2download)
1. Al termine di questi download, aprire **Esplora file**  >  **Download**. Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.
1. Connettere HoloLens al PC usando un cavo DA USB A a USB-C. Anche se si usano altri cavi per connettere HoloLens, questo funziona meglio.
1. Advanced Recovery Companion rileva automaticamente HoloLens. Selezionare il **Microsoft HoloLens** riquadro.
1. Nella schermata successiva selezionare **Selezione** pacchetto manuale e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con estensione ffu.
1. Selezionare **Installa software** e seguire le istruzioni.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Tornare a una versione precedente - HoloLens (prima generazione)

In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens. A tale scopo, puoi usare lo strumento ripristino dispositivi di Windows per ripristinare holoLens alla versione precedente.

> [!NOTE]
> Se si torna a una versione precedente, i file e le impostazioni personali vengono eliminati.

Per tornare a una versione precedente di HoloLens 1, seguire questa procedura:

1. Assicurarsi che non siano presenti telefoni o dispositivi Windows collegati al PC.
1. Nel PC scaricare Windows [Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Scaricare il [pacchetto di ripristino dell'aggiornamento dell'anniversario di HoloLens.](https://aka.ms/hololensrecovery)
1. Al termine dei download, aprire **Download di Esplora**  >  **file.** Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.
1. Connetti HoloLens al PC usando il cavo micro USB fornito. Anche se hai già utilizzato altri cavi per connettere HoloLens, questo funziona meglio.
1. WdRT rileverà automaticamente HoloLens. Selezionare il **Microsoft HoloLens** riquadro.
1. Nella schermata successiva selezionare Selezione manuale **del pacchetto** e scegliere il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con estensione ffu.
1. Selezionare **Installa software** e seguire le istruzioni.

> [!NOTE]
> Se WDRT non rileva HoloLens, prova a riavviare il PC. Se non funziona, selezionare **Il** dispositivo non è stato rilevato, selezionare Microsoft HoloLens **e** quindi seguire le istruzioni.

## <a name="windows-insider-program-on-hololens"></a>Programma Windows Insider su HoloLens

Per visualizzare le funzionalità più recenti in HoloLens,  In tal caso, aggiungere il Programma Windows Insider; Si otterrà l'accesso alle build di anteprima degli aggiornamenti software HoloLens prima che siano disponibili per il pubblico generale.

[Ottenere partecipante al Programma Windows Insider anteprima per Microsoft HoloLens](hololens-insider.md).
