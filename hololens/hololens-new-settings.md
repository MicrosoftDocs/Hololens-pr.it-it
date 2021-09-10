---
title: Introduzione alla nuova app Impostazioni
description: Informazioni sulla nuova app Impostazioni
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, impostazioni, selezione app, volume
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bcde697b5887573826a3a1a61e8c3707b4d0337a
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427578"
---
# <a name="new-settings-app"></a>Nuova app Impostazioni

Con [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)viene introdotto una nuova versione dell'app Impostazioni. La nuova app Impostazioni include nuove funzionalità e impostazioni espanse per HoloLens 2 nelle aree seguenti: Audio, Sospensione di Power &, Rete & Internet, App, Account, Accessibilità e altro ancora.

> [!NOTE]
> Poiché la nuova app Impostazioni è distinta dall'app Impostazioni legacy, tutte le finestre Impostazioni posizionate in precedenza nell'ambiente verranno rimosse al momento dell'aggiornamento.

![Nuova home Impostazioni dell'app.](images/new-settings-app.png)

**Nuove funzionalità e impostazioni**
- Impostazioni ricerca: cercare le impostazioni dalla home Impostazioni home page usando parole chiave o il nome dell'impostazione.
- Calibrazione colori > [sistema](hololens2-display.md#how-to-use-display-color-calibration)
    - Selezionare un profilo colori alternativo per la HoloLens 2 schermo.
- Suono > sistema:
  - Dispositivi audio di input e output: scegliere in modo indipendente i dispositivi audio di input e output, ad esempio ascoltare l'audio tramite le cuffi Bluetooth o usare un microfono USB-C per l'input audio.
    > [!NOTE]
    > Bluetooth microfoni non sono supportati da HoloLens 2.
  - Volume dell'app: regolare in modo indipendente il volume di ogni app. Vedere [controllo del volume per app.](holographic-home.md#per-app-volume-control)
- Sistema > sospensione & alimentazione: scegliere quando il dispositivo deve andare in sospensione dopo un periodo di inattività.
- Batteria > sistema: abilitare manualmente la risparmio batteria o impostare una soglia della batteria a quel punto risparmio batteria si attiva automaticamente.
- Dispositivi > USB: è possibile disabilitare le connessioni USB per impostazione predefinita.
- Rete & Internet:
  - Le schede Ethernet USB-C verranno ora visualizzate in Rete & Internet.
  - Sono ora disponibili le impostazioni della scheda Ethernet USB-C, incluso il relativo indirizzo IP.
  - È ora possibile abilitare la modalità aereo HoloLens 2.
- App: è possibile reimpostare le app predefinite usate per i tipi di file e collegamenti. Per altre informazioni, vedere [Selezione app predefinita.](holographic-home.md#default-app-picker)
- Account > altri utenti: i proprietari dei dispositivi possono aggiungere utenti, aggiornare gli utenti standard ai proprietari dei dispositivi, effettuare il downgrade dei proprietari di dispositivi agli utenti standard e rimuovere gli utenti.
- Accessibilità: modificare le dimensioni del testo e alcuni effetti visivi.

**Problemi noti**
- Le finestre Impostazioni in precedenza verranno rimosse (vedere la nota precedente).
- Non è più possibile rinominare il dispositivo con l Impostazioni app. Gli amministratori IT possono rinominare i dispositivi usando il modello [Windows Autopilot](hololens2-autopilot.md) per HoloLens 2 o il nodo MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- La pagina Ethernet mostra sempre un dispositivo Ethernet virtuale ("UsbNcm").
- L'utilizzo della batteria per il nuovo Microsoft Edge potrebbe non essere accurato, a causa della sua natura come applicazione desktop Win32 supportata da un livello adattatore UWP (non è prevista alcuna correzione a breve).

