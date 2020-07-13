---
title: Wireless e Wi-Fi
description: Wireless e Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, wireless, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865775"
---
# Wireless e Wi-Fi

La connettività LAN wireless di HoloLens 2 supporta una gamma incredibile degli standard di sicurezza più recenti, ad esempio:
  * WPA2 (Wi-Fi Protected Access 2)  
  * TEAP (Tunnel Extensible Authentication Protocol)  
  * OWE (Opportunistic Wireless Encryption)

TEAP, l'autenticazione alle reti aziendali di nuova generazione, consente di collegare in modo sicuro più credenziali in una singola operazione.  Ciò consente agli amministratori di applicare un approccio alla sicurezza più efficace, che richieda identità valide sia per la macchina che per l'utente durante la stessa transazione di autenticazione.

HoloLens 2 offre protocolli wireless moderni e Wi-Fi che consentono ai clienti di ottenere il massimo supporto. La radio HoloLens 2 è una soluzione Qualcomm WCN3990 in grado di offrire un'esperienza radio premium. La rete Wi-Fi supportata è 802.11 ac/n. L'intervallo di frequenze non è configurabile dall'utente e varia in base al Paese di utilizzo. Negli Stati Uniti, la rete Wi-Fi usa sia canali da 2,4 GHz (1-11) che 5 canali da 5 GHz (36-64, 100-165). Gli utenti e i dispositivi non possono creare elenchi consentiti/rifiutati per frequenze specifiche. Il Bluetooth SIC Core 5.0 dispone di un'antenna da 2,4 GHz dedicata per il Bluetooth che non viene condivisa con il Wi-Fi. Lo stack del software di HoloLens 2 supporta più protocolli e profili, tra cui HID, HOGP, A2DP e GATT. 

Gli amministratori IT possono: 
  * Abilitare o limitare [l'accesso Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)
  * Impostare i [nomi del dispositivo Bluetooth locale](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)
  * Consentire ai [dispositivi di essere individuabili](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)
  * Consentire o meno [le connessioni Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 
  * Consentire o meno [la connessione a un Wi-Fi esterno alle reti del server MDM installato](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)
