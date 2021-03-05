---
title: Connessione a dispositivi Bluetooth e USB-C
description: Informazioni di base sulla connessione ai dispositivi e accessori Bluetooth e USB-C dai dispositivi di Realtà mista HoloLens.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385484"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Connessione a dispositivi Bluetooth e USB-C

> [!NOTE]
> I microfoni esterni non possono essere utilizzati. HoloLens 2 usa il suo [](hololens2-hardware.md#audio-and-speech)gruppo microfoni[ incorporato.](hololens2-hardware.md#audio-and-speech)

## <a name="pair-bluetooth-devices"></a>Accoppiare dispositivi Bluetooth

HoloLens 2 supporta le seguenti categorie di dispositivi Bluetooth:

- Mouse
- Tastiera
- Dispositivi A2DP (Bluetooth audio output)

HoloLens (prima generazione) supporta le seguenti categorie di dispositivi Bluetooth:

- Mouse
- Tastiera
- [Clicker HoloLens (prima generazione)](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Altri tipi di dispositivi Bluetooth, come altoparlanti, cuffie, smartphone e game pad, potrebbero essere elencati come disponibili nelle impostazioni di HoloLens. Tuttavia, questi dispositivi non sono supportati in HoloLens (prima generazione). Per maggiori dettagli, vedere [Le impostazioni di HoloLens indicano che i dispositivi sono disponibili, ma questi non funzionano](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Accoppiare una tastiera o un mouse Bluetooth

1. Attivare la tastiera o il mouse e renderli individuabili. Per informazioni su come rendere i dispositivi individuabili, cerca informazioni nel dispositivo (o nella documentazione) oppure visita il sito web del produttore.

1. Apri la mano a fiore (HoloLens prima generazione) o esegui il gesto iniziale (HoloLens 2) per passare a **Start**, e seleziona poi **Impostazioni**.

1. Seleziona **Dispositivi**, e assicurati che il Bluetooth sia attivato.  

1. Quando vedi il nome del dispositivo, seleziona **Associa**, e segui poi le istruzioni.

## <a name="disable-bluetooth"></a>Disattivare il Bluetooth

Questa procedura disattiva i componenti RF della radio Bluetooth, e disabilita tutte le funzionalità Bluetooth di Microsoft HoloLens.

1. Apri la mano a fiore (HoloLens prima generazione) o esegui il gesto iniziale (HoloLens 2) per passare a **Start**, e seleziona poi **Impostazioni** > **Dispositivi**.

1. Sposta il selettore del **Bluetooth** sulla posizione **Off**.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Connettere dispositivi USB-C

HoloLens 2 supporta le seguenti categorie di dispositivi USB-C:

- Dispositivi di archiviazione di massa (come le penne USB)
- Adattatori ethernet (inclusi dispositivi ethernet più ricarica)
- Adattatori da USB-C a presa audio da 3,5 mm
- Auricolari digitali USB-C (inclusi gli adattatori e la ricarica)
- Mouse cablati
- Tastiere cablate
- Hub PD con combinazione (ricarica USB A più PD)

> [!NOTE]
> In risposta al feedback dei clienti, abbiamo abilitato un supporto limitato per la connettività cellulare con tethering direttamente a HoloLens tramite USB-C. Per altre informazioni, vedi [Connettersi alla rete cellulare e 5G.](hololens-cellular.md)

### <a name="usb-c-hubs"></a>Hub USB-C

Alcuni utenti potrebbero avere la necessità di connettere più dispositivi contemporaneamente. Per gli utenti che desiderano visualizzare in anteprima una caratteristica Insider e [usare un microfono USB-C](hololens-insider.md#usb-c-external-microphone-support) insieme a un altro dispositivo connesso, gli hub USB-C possono rappresentare una soluzione adatta. Microsoft non ha testato tali dispositivi, né è nella misura di consigliare un marchio specifico.

**Requisiti per hub USB-C e dispositivi connessi:**

- I dispositivi connessi non possono richiedere un driver per l'installazione.
- Il consumo energetico totale di tutti i dispositivi connessi deve essere inferiore a 4,5 watt.

## <a name="connect-to-miracast"></a>Connettersi a Miracast

Per usare Miracast, segui questa procedura:

1. Effettua una delle seguenti operazioni:  

   - Apri il menu **Start** e seleziona l’icona del display.
   - Pronuncia “Connetti” mentre fissi il **menu Start**.  

1. Seleziona un dispositivo disponibile dall’elenco di dispositivi mostrato.

1. Completa l'associazione per avviare la proiezione.
