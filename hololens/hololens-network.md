---
title: Connettersi a una rete
description: Istruzioni su come connettersi a Internet con HoloLens e come identificare l'indirizzo IP del dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, wireless, Internet, IP, indirizzo IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0bc5a5f7f3eaf3d811da055a7bda664fd3f0daff
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829286"
---
# Connettersi a una rete

Per eseguire la maggior parte delle operazioni in HoloLens, è necessario essere connessi a una rete. Questa guida ti aiuterà a:

- Connetterti a una rete tramite Wi-Fi o (solo per HoloLens 2) Ethernet tramite USB-C
- Disabilitare e riabilitare il Wi-Fi

Leggi altre informazioni sull'[uso di HoloLens offline](hololens-offline.md).

## Connessione per la prima volta

La prima volta che usi HoloLens, dovrai seguire le istruzioni per la connessione a una rete Wi-Fi. In caso di problemi di connessione a una rete Wi-Fi durante l'installazione, verifica che la rete sia aperta, protetta da password o captive portal. Verifica che la rete non richieda l'uso di un certificato per la connessione. Dopo la configurazione, potrai connetterti ad altri tipi di reti Wi-Fi.

## Connessione alla rete Wi-Fi dopo la configurazione

1. Seleziona **Start** > **Impostazioni**.
   - *Solo HoloLens (prima generazione)*: usa lo sguardo per inserire l'app Impostazioni, quindi simula il tocco per posizionarla oppure pronuncia "Posizionare".
1. Seleziona **Rete e Internet** > **Wi-Fi**. Se non vedi la tua rete, scorri in basso nell'elenco.
1. Seleziona una rete, quindi fai clic su **Connetti**.
1. Se viene richiesto di digitare una password di rete, inseriscila, quindi seleziona **Avanti**.

## Connessione a una rete Wi-Fi su HoloLens (prima generazione)

HoloLens contiene una radio Wi-Fi 2x2, con supporto di 802.11ac. La connessione di HoloLens a una rete Wi-Fi avviene in modo simile alla connessione di un dispositivo desktop o mobile Windows 10 a una rete Wi-Fi.

![Impostazioni Wi-Fi di HoloLens](./images/wifi-hololens-600px.jpg)

1. Apri il menu **Start**.
1. Seleziona l'app Impostazioni da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**. L'app Impostazioni verrà posizionata automaticamente di fronte a te.
1. Seleziona **Rete e Internet**.
1. Verifica che il Wi-Fi sia attivato.
1. Seleziona una rete Wi-Fi nell'elenco.
1. Se necessario, digita la password della rete Wi-Fi.

Puoi anche verificare che la connessione a una rete Wi-Fi sia stabilita, controllando lo stato Wi-Fi nel menu **Start**:

1. Apri il menu **Start**.
1. In alto a sinistra del menu **Start** controlla lo stato del Wi-Fi. Verranno visualizzati stato del Wi-Fi e SSID della rete connessa.

## Risoluzione dei problemi relativi alla connessione al Wi-Fi

Se si verificano problemi di connessione al Wi-Fi, vedere [Non riesco a connettermi al Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Quando si accede a un account aziendale o dell'organizzazione sul dispositivo, è possibile che vengano applicati anche criteri di gestione di dispositivi mobili (MDM), se i criteri sono configurati dall'amministratore IT.

## Disabilitazione della rete Wi-Fi in HoloLens (prima generazione)

### Uso dell'app Impostazioni in HoloLens

1. Apri il menu **Start**.
1. Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**. L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.
1. Seleziona **Rete e Internet**.
1. Seleziona il dispositivo di scorrimento Wi-Fi per spostarlo nella posizione **Off**. I componenti RF della radio Wi-Fi verranno disattivati e tutte le funzionalità Wi-Fi in HoloLens verranno disabilitate.

    > [!WARNING]
    > Quando la radio Wi-Fi è disabilitata, HoloLens non sarà in grado di caricare automaticamente gli [spazi](hololens-spaces.md).

1. Sposta il dispositivo di scorrimento sulla posizione **Attivato** per attivare la radio Wi-Fi e ripristinare la funzionalità Wi-Fi su Microsoft HoloLens. Lo stato della radio Wi-Fi selezionato (**Attivato** o **Disattivato**) verrà mantenuto a ogni riavvio.

## Identificazione dell'indirizzo IP di HoloLens nella rete Wi-Fi

### Usando l'app Impostazioni

1. Apri il menu **Start**.
1. Seleziona l'app **Impostazioni** da **Start** o nell'elenco **Tutte le app** a destra del menu **Start**. L'app **Impostazioni** verrà posizionata automaticamente di fronte a te.
1. Seleziona **Rete e Internet**.
1. Scorri in basso verso la fine dell'elenco delle reti Wi-Fi disponibili e seleziona **Proprietà hardware**.

    ![Proprietà hardware nelle impostazioni Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   L'indirizzo IP viene visualizzato accanto all'**indirizzo IPv4**.

### Usando Cortana

Pronunciare "Ehi Cortana, qual è il mio indirizzo IP?" e Cortana visualizzerà e leggerà l'indirizzo IP.

### Usando il Portale di dispositivi di Windows

1. In un Web browser nel PC apri il [portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Passa alla sezione **Reti**.  
   In questa sezione vengono visualizzati l'indirizzo IP e altre informazioni di rete. Usando questo metodo, potrai copiare e incollare l'indirizzo IP nel PC di sviluppo.
