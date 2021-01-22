---
title: Aggiornare HoloLens
description: Scopri come controllare il numero di build di HoloLens, mantenerti aggiornato con gli aggiornamenti dei dispositivi, partecipare al Programma Insider e eseguire il rollback degli aggiornamenti.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283937"
---
# Aggiornare HoloLens

HoloLens usa Windows Update, proprio come altri dispositivi Windows 10. HoloLens scaricherà e installerà automaticamente gli aggiornamenti di sistema ogni volta che viene collegato all'alimentazione e connesso a Internet, anche quando è in standby.

Questo articolo illustra gli strumenti di HoloLens per:

- visualizzazione della versione corrente del sistema operativo (numero di build)
- verifica della disponibilità di aggiornamenti
- aggiornamento manuale di HoloLens
- rollback a un aggiornamento precedente

## Controllare la versione del sistema operativo (numero di build)

Puoi verificare il numero di versione del sistema (numero di build) aprendo l'app Impostazioni e selezionando **Informazioni**  >  **sul sistema.**

## Verificare la disponibilità di aggiornamenti e aggiornare manualmente

Puoi verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.  Per visualizzare gli aggiornamenti disponibili e verificare la disponibilità di nuovi aggiornamenti:

1. Apri **l'app** Impostazioni.
1. Passare a **Aggiornamento & Sicurezza di**Windows  >  **Update.**
1. Selezionare **Verifica disponibilità aggiornamenti.**

Se è disponibile un aggiornamento, inizierà a scaricare la nuova versione. Al termine del download, selezionare **il** pulsante Riavvia ora per attivare l'installazione. Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.

Durante l'installazione dell'aggiornamento, HoloLens visualizza ingranaggi rotanti e un indicatore di stato. Non disattivare HoloLens durante questo periodo. Verrà riavviato automaticamente una volta completata l'installazione.

HoloLens applica un aggiornamento alla volta.  Se holoLens è più di una versione rispetto alla versione più recente, potrebbe essere necessario eseguire il processo di aggiornamento più volte per aggiornarlo completamente.

## Tornare a una versione precedente - HoloLens 2

In alcuni casi, potresti voler tornare a una versione precedente del software di HoloLens. A tale scopo, puoi usare Advanced Recovery Companion per ripristinare holoLens alla versione precedente.

> [!NOTE]
> Tornando a una versione precedente, vengono eliminati i file e le impostazioni personali.

Per tornare una versione precedente di HoloLens 2, segui questi passaggi:

1. Assicurati di non avere telefoni o dispositivi Windows collegati al PC.
1. Nel PC scarica [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.
1. Scarica la [versione più recente di HoloLens 2](https://aka.ms/hololens2download).
1. Al termine di questi download, apri **Download di Esplora**  >  **file.** Fai clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e seleziona **Estrai tutto** > **Estratti** per decomprimerla.
1. Connetti HoloLens al PC usando un cavo USB-A-USB-C. Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.
1. Advanced Recovery Companion rileva automaticamente HoloLens. Seleziona il riquadro **Microsoft HoloLens**.
1. Nella schermata successiva, selezionare Selezione manuale del **pacchetto** e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con estensione ffu.
1. Selezionare **Installa software**e seguire le istruzioni.

## Tornare a una versione precedente - HoloLens (prima generazione)

In alcuni casi, potresti voler tornare a una versione precedente del software di HoloLens. A tale scopo, puoi usare lo strumento ripristino dispositivi di Windows per ripristinare holoLens alla versione precedente.

> [!NOTE]
> Tornando a una versione precedente, vengono eliminati i file e le impostazioni personali.

Per tornare a una versione precedente di HoloLens 1, attenersi alla seguente procedura:

1. Assicurati di non avere telefoni o dispositivi Windows collegati al PC.
1. Scarica Windows Device [Recovery Tool (WDRT) nel](https://support.microsoft.com/help/12379)PC.
1. Scarica il pacchetto [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).
1. Al termine dei download, apri **Download di Esplora**  >  **file.** Fai clic con il pulsante destro del **** mouse sulla cartella compressa appena scaricata e scegli  >  **Estrai** tutto per decomprimerla.
1. Connetti HoloLens al PC usando il cavo micro USB con cui è stato fornito. Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.
1. WdRT rileverà automaticamente holoLens. Seleziona il riquadro **Microsoft HoloLens**.
1. Nella schermata successiva, selezionare Selezione manuale del **pacchetto** e scegliere il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con estensione ffu.
1. Selezionare **Installa software**e seguire le istruzioni.

> [!NOTE]
> Se WDRT non rileva HoloLens, prova a riavviare il PC. Se il rilevamento non funziona, seleziona **Il mio dispositivo non è stato rilevato**, seleziona poi **Microsoft HoloLens**, e segui le istruzioni.

## Programma Windows Insider in HoloLens

Vuoi vedere le funzionalità più recenti in HoloLens?  In tal caso, partecipa al Programma Windows Insider; si otterrà l'accesso alle build di anteprima degli aggiornamenti software di HoloLens prima che siano disponibili al pubblico.

[Ottenere Windows Insider Preview per Microsoft HoloLens.](hololens-insider.md)
