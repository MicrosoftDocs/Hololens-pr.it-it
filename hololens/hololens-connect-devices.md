---
title: Connessione dispositivi Bluetooth e USB-C
description: Inizia a connetterti Bluetooth dispositivi e accessori USB-C dai tuoi HoloLens di realtà mista.
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
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036025"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Connessione dispositivi Bluetooth e USB-C

## <a name="pair-bluetooth-devices"></a>Associare Bluetooth dispositivi

HoloLens 2 supporta le classi di dispositivi Bluetooth seguenti:

- [HID](/windows-hardware/drivers/hid/):
    - Mouse
    - Tastiera
- Dispositivi di output audio (A2DP)

HoloLens 2 supporta le API Bluetooth seguenti:
- [Server](/windows/uwp/devices-sensors/gatt-server) e [client](/windows/uwp/devices-sensors/gatt-client) GATT
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Potrebbe essere necessario installare le app complementari corrispondenti da Microsoft Store per usare effettivamente i dispositivi HID e GATT.

HoloLens (prima generazione) supporta le classi di dispositivi Bluetooth seguenti:

- Mouse
- Tastiera
- [HoloLens clicker (prima generazione)](hololens1-clicker.md)

> [!NOTE]
> Altri tipi di Bluetooth, ad esempio altoparlanti, visori VR, smartphone e game pad, possono essere elencati come disponibili nelle impostazioni HoloLens dispositivo. Tuttavia, questi dispositivi non sono supportati in HoloLens (prima generazione). Per altre informazioni, vedere HoloLens Impostazioni elenca i dispositivi come disponibili, ma i dispositivi [non funzionano.](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Associare una Bluetooth o un mouse

1. Accendere la tastiera o il mouse e renderla individuabile. Per informazioni su come rendere individuabile il dispositivo, cercare informazioni sul dispositivo (o sulla relativa documentazione) o visitare il sito Web del produttore.

1. Usare il movimento di fiore (HoloLens (prima generazione)) o il movimento di avvio (HoloLens 2) per passare a **Start** e quindi **selezionare Impostazioni**.

1. Selezionare **Dispositivi** e assicurarsi che l'Bluetooth sia selezionata.  

1. Quando viene visualizzato il nome del dispositivo, selezionare **Associa** e quindi seguire le istruzioni.

## <a name="disable-bluetooth"></a>Disabilitare Bluetooth

Questa procedura disattiva i componenti RF della radio Bluetooth e disabilita tutte le funzionalità Bluetooth in Microsoft HoloLens.

1. Usare il movimento di fiore (HoloLens (prima generazione)) o il movimento di avvio (HoloLens 2) per passare a **Start** e quindi **selezionare Impostazioni**  >  **Dispositivi**.

1. Spostare l'interruttore del **dispositivo Bluetooth** nella **posizione Disattivato.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Connessione USB-C

HoloLens 2 supporta le classi seguenti di dispositivi USB-C:

- Dispositivi di archiviazione di massa (ad esempio, le unità thumb)
- Schede Ethernet (tra cui ethernet e ricarica)
- Adattatori audio digitali USB da C a 3,5 mm
- Visori VR audio digitali USB-C (inclusi adattatori per visori VR e ricarica)
- Microfoni esterni USB-C[(Windows Holographic, versione 21H1 e](hololens-release-notes.md#windows-holographic-version-21h1) successive)
- Mouse cablato
- Tastiera cablata
- Hub PD combinato (USB A e ricarica PD)


> [!NOTE]
> In risposta ai commenti e suggerimenti dei clienti, è stato abilitato un supporto limitato per la connettività cellulare collegata direttamente al HoloLens tramite USB-C. Per [altre informazioni, Connessione alla rete cellulare e 5G.](hololens-cellular.md)

### <a name="usb-c-external-microphone-support"></a>Supporto microfono esterno USB-C

> [!IMPORTANT]
> L'inserimento di un microfono USB non **lo imposta automaticamente come dispositivo di input.** Quando si collega un set di cuffi USB-C, gli utenti osserveranno che l'audio della cuffia verrà reindirizzato automaticamente alle cuffie, ma il sistema operativo HoloLens assegna la priorità all'array di microfoni interni rispetto a qualsiasi altro dispositivo di input. **Per usare un microfono USB-C, seguire questa procedura.**

> [!NOTE]
> Non è possibile usare microfoni esterni nelle build precedenti Windows [olografica, versione 21H1 e](hololens-release-notes.md#windows-holographic-version-21h1) successive. 

Gli utenti possono selezionare microfoni esterni connessi tramite USB-C usando il **pannello Impostazioni** audio. I microfoni USB-C possono essere usati per chiamare, registrare e così via.

Aprire **l'app Impostazioni** e selezionare **Suono del**  >  **sistema.**

![Audio Impostazioni.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Per usare microfoni esterni **con** Remote Assist , gli utenti dovranno fare clic sul collegamento ipertestuale "Gestisci dispositivi audio".
>
> Usare quindi l'elenco a discesa per impostare il microfono esterno su **Predefinito** o **Predefinito comunicazioni.** Se **si sceglie Predefinito,** il microfono esterno verrà usato ovunque.
>
> Se **si sceglie** Comunicazioni predefinite, il microfono esterno verrà usato in Remote Assist e in altre app di comunicazione, ma l'array di microfoni HoloLens può comunque essere usato per altre attività.

![Gestire i dispositivi audio.](images/usbc-mic-2.png)

<br>

![Impostare il microfono predefinito.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Che ne è del Bluetooth microfono?

Sfortunatamente, Bluetooth microfoni non sono ancora supportati in HoloLens 2.

### <a name="usb-c-hubs"></a>Hub USB-C

Alcuni utenti potrebbero dover connettere più dispositivi contemporaneamente. Per gli utenti che desiderano usare un microfono [USB-C](#usb-c-external-microphone-support) insieme a un altro dispositivo connesso, gli hub USB-C possono soddisfare le esigenze del cliente. Microsoft non ha testato questi dispositivi, né è possibile consigliare marchi specifici.

**Requisiti per l'hub USB-C e i dispositivi connessi:**

- I dispositivi connessi non devono richiedere l'installazione di un driver.
- Il consumo di energia totale di tutti i dispositivi connessi deve essere inferiore a 4,5 Punti.

## <a name="connect-to-miracast"></a>Connessione da Miracast

Per usare Miracast, seguire questa procedura:

1. Eseguire una delle operazioni seguenti:  

   - Aprire il menu **Start** e selezionare **l'icona** Visualizza.
   - Pronunciare "Connessione" mentre si guarda il menu **Start.**  

1. Nell'elenco dei dispositivi visualizzato selezionare un dispositivo disponibile.

1. Completare l'associazione per iniziare la progettazione.
