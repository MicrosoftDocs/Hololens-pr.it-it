---
title: Connettere HoloLens a una rete
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
ms.openlocfilehash: 0f46ff4a1bef95d153d9fa93c746c8977dc49771
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883150"
---
# Connettere HoloLens a una rete

Per eseguire la maggior parte delle operazioni in HoloLens, è necessario essere connessi a una rete. Questa guida ti aiuterà a:

- Connetterti a una rete tramite Wi-Fi o (solo per HoloLens 2) Ethernet tramite USB-C
- Disabilitare e riabilitare il Wi-Fi

Leggi altre informazioni sull'[uso di HoloLens offline](hololens-offline.md).

## Connessione per la prima volta

La prima volta che usi HoloLens, dovrai seguire le istruzioni per la connessione a una rete Wi-Fi. In caso di problemi di connessione a una rete Wi-Fi durante l'installazione, verifica che la rete sia aperta, protetta da password o captive portal. Verifica che la rete non richieda l'uso di un certificato per la connessione. Dopo la configurazione, potrai connetterti ad altri tipi di reti Wi-Fi.

## Connessione alla rete Wi-Fi dopo la configurazione

1. Eseguire il **gesto Start** e selezionare **Impostazioni**. L'app Impostazioni verrà posizionata automaticamente di fronte a te.
1. Seleziona **Rete e Internet** > **Wi-Fi**. Verifica che il Wi-Fi sia attivato. Se non vedi la tua rete, scorri in basso nell'elenco.
1. Seleziona una rete, quindi fai clic su **Connetti**.
1. Se viene richiesto di digitare una password di rete, inseriscila, quindi seleziona **Avanti**.

HoloLens contiene una radio Wi-Fi 2x2, con supporto di 802.11ac. La connessione di HoloLens a una rete Wi-Fi avviene in modo simile alla connessione di un dispositivo desktop o mobile Windows 10 a una rete Wi-Fi.

![Impostazioni Wi-Fi di HoloLens](./images/wifi-hololens-600px.jpg)

Puoi anche verificare che la connessione a una rete Wi-Fi sia stabilita, controllando lo stato Wi-Fi nel menu **Start**:

1. Apri il menu **Start**.
1. In alto a sinistra del menu **Start** controlla lo stato del Wi-Fi. Verranno visualizzati stato del Wi-Fi e SSID della rete connessa.

## Risoluzione dei problemi relativi alla connessione al Wi-Fi

Se si verificano problemi di connessione al Wi-Fi, vedere [Non riesco a connettermi al Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Quando si accede a un account aziendale o dell'organizzazione sul dispositivo, è possibile che vengano applicati anche criteri di gestione di dispositivi mobili (MDM), se i criteri sono configurati dall'amministratore IT.

## VPN
Una connessione VPN può essere utile per garantire una connessione più sicura e l'accesso alla rete aziendale e a Internet. HoloLens 2 supporta il client VPN predefinito e il plug-in VPN UWP (Universal Windows Platform). 

Protocolli VPN predefiniti supportati:
- IKEv2
- L2TP
- PPTP

Se il certificato viene usato per l'autenticazione per il client VPN predefinito, è necessario aggiungere il certificato client necessario all'archivio certificati utente. Per scoprire se un plug-in VPN di terze parti supporta HoloLens 2, passare allo Store per individuare l'app VPN e controllare se HoloLens compare tra i dispositivi supportati e se nella pagina dei requisiti di sistema l'app supporta l'architettura ARM o ARM64. HoloLens supporta solo le applicazioni della piattaforma UWP per la rete VPN di terze parti.

Per impostazione predefinita, la VPN non è abilitata, ma può essere abilitata manualmente andando l'app **Impostazioni**, quindi **Rete e internet > VPN**. La rete VPN può essere gestita da MDM tramite [Impostazioni/ConsentiVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) e impostata con il [criterio Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).
Scoprire ulteriori informazioni su [come configurare la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [queste guide](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

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

### Tramite i comandi vocali

A seconda del tipo di dispositivo in uso, è possibile usare il comando vocale predefinito o Cortana per visualizzare l'indirizzo IP. Nelle build successive a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) dire "Qual è il mio indirizzo IP?" e verrà visualizzato. Per le build precedenti o per HoloLens (prima generazione) dire "Ehi Cortana, qual è il mio indirizzo IP?" e Cortana visualizzerà e leggerà l'indirizzo IP.

### Usando il Portale di dispositivi di Windows

1. In un Web browser nel PC apri il [portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Passa alla sezione **Reti**.  
   In questa sezione vengono visualizzati l'indirizzo IP e altre informazioni di rete. Usando questo metodo, potrai copiare e incollare l'indirizzo IP nel PC di sviluppo.
