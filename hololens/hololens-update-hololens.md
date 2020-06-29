---
title: Aggiornare HoloLens
description: Controllare il numero di build, l'aggiornamento e la rollback degli aggiornamenti di HoloLens.
keywords: procedura, aggiornamento, rollback, HoloLens, controllo Build, numero di Build
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828591"
---
# Aggiornare HoloLens

HoloLens usa Windows Update, proprio come gli altri dispositivi Windows 10. Il HoloLens scaricherà e installerà automaticamente gli aggiornamenti di sistema ogni volta che viene collegato a Power e connesso a Internet, anche quando è in standby.

In questo articolo verranno illustrati gli strumenti di HoloLens per:

- visualizzazione della versione del sistema operativo corrente (numero di Build)
- Verifica della disponibilità di aggiornamenti
- aggiornamento manuale di HoloLens
- rollback di un aggiornamento precedente

## Verificare la versione del sistema operativo (numero di Build)

Puoi verificare il numero di versione del sistema (numero di Build) aprendo l'app Impostazioni e selezionando **System**  >  **About**.

## Verificare la disponibilità di aggiornamenti e aggiornare manualmente

Puoi verificare la disponibilità di aggiornamenti in qualsiasi momento in impostazioni.  Per visualizzare gli aggiornamenti disponibili e verificare la disponibilità di nuovi aggiornamenti:

1. Aprire l'app **Impostazioni** .
1. Passare alla pagina **Update & Security**  >  **Update di Windows**.
1. Selezionare **Controlla aggiornamenti**.

Se è disponibile un aggiornamento, inizierà a scaricare la nuova versione. Al termine del download, selezionare il pulsante **Riavvia ora** per attivare l'installazione. Se il dispositivo è inferiore a 40% e non è collegato, il riavvio non verrà avviato per l'installazione dell'aggiornamento.

Durante l'installazione dell'aggiornamento, il HoloLens visualizzerà gli ingranaggi rotanti e un indicatore di stato. Non disattivare il HoloLens durante questo periodo. Verrà riavviato automaticamente dopo aver completato l'installazione.

HoloLens applica un aggiornamento alla volta.  Se il HoloLens è più di una versione dietro alla più recente, potrebbe essere necessario eseguire più volte il processo di aggiornamento per aggiornarlo completamente.

## Tornare a una versione precedente-HoloLens 2

In alcuni casi, potresti voler tornare a una versione precedente del software HoloLens. Puoi eseguire questa operazione usando il compagno di ripristino avanzato per reimpostare il HoloLens alla versione precedente.

> [!NOTE]
> Tornando a una versione precedente vengono eliminati i file e le impostazioni personali.

Per tornare a una versione precedente di HoloLens 2, eseguire le operazioni seguenti:

1. Verificare che non siano presenti telefoni o dispositivi Windows collegati al PC.
1. Nel PC scaricare il compagno di [Ripristino avanzato](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.
1. Scaricare la [versione più recente di HoloLens 2](https://aka.ms/hololens2download).
1. Dopo aver completato questi download, aprire download di **Esplora file**  >  **Downloads**. Fai clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e seleziona **Estrai tutto** > **Estratti** per decomprimerla.
1. Connettere il HoloLens al PC usando un cavo USB-a-USB-C. Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.
1. Il compagno di recupero avanzato rileva automaticamente il HoloLens. Selezionare il riquadro **Microsoft HoloLens** .
1. Nella schermata successiva selezionare **Selezione pacchetto manuale** e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con estensione FFU.
1. Selezionare **Installa software**e seguire le istruzioni.

## Tornare a una versione precedente-HoloLens (1st Gen)

In alcuni casi, potresti voler tornare a una versione precedente del software HoloLens. Puoi eseguire questa operazione usando lo strumento ripristino dispositivi Windows per reimpostare il HoloLens alla versione precedente.

> [!NOTE]
> Tornando a una versione precedente vengono eliminati i file e le impostazioni personali.

Per tornare a una versione precedente di HoloLens 1, eseguire le operazioni seguenti:

1. Verificare che non siano presenti telefoni o dispositivi Windows collegati al PC.
1. Nel PC scaricare lo [strumento Windows Device Recovery (WDRT)](https://support.microsoft.com/help/12379).
1. Scaricare il [pacchetto di ripristino dell'aggiornamento di HoloLens anniversario](https://aka.ms/hololensrecovery).
1. Al termine del download, aprire download di **Esplora file**  >  **Downloads**. Fai clic con il pulsante destro del mouse sulla cartella zippata appena scaricata e seleziona **Estrai tutti gli**  >  **estratti** per decomprimerla.
1. Connettere il HoloLens al PC usando il cavo micro-USB con cui è stato fornito. Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.
1. WDRT rileverà automaticamente la HoloLens. Selezionare il riquadro **Microsoft HoloLens** .
1. Nella schermata successiva selezionare **Selezione pacchetto manuale** e scegliere il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con estensione FFU.
1. Selezionare **Installa software**e seguire le istruzioni.

> [!NOTE]
> Se WDRT non rileva il HoloLens, provare a riavviare il PC. Se non funziona, selezionare il **dispositivo non è stato rilevato**, selezionare **Microsoft HoloLens**e quindi seguire le istruzioni.

## Programma Windows insider in HoloLens

Vuoi vedere le caratteristiche più recenti di HoloLens?  In questo caso, partecipa al programma Windows Insider; otterrai l'accesso alle build di anteprima degli aggiornamenti software di HoloLens prima che siano disponibili per il pubblico generale.

[Ottenere Windows Insider Preview per Microsoft HoloLens](hololens-insider.md).
