---
title: Restrizioni comuni per i dispositivi
description: Il dispositivo restrctions comunemente impostato su HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ace1e071b3d73855daacc8a11ac87770fb7f5f99
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016785"
---
# Restrizioni comuni per i dispositivi 

Questa guida aiuta i professionisti IT a comprendere le opzioni di gestione più comunemente usate disponibili per il sistema operativo Windows 10 olografico nell'organizzazione. Per informazioni su come questi criteri vengono abilitati dal tuo fornitore del sistema MDM, consulta la documentazione specifica. Non tutti i sistemi MDM supportano ogni impostazione descritta in questa Guida. Alcuni supportano criteri personalizzati tramite file XML OMA-URI. Vedi le informazioni sul [supporto dei criteri personalizzati in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Le convenzioni di denominazione possono anche variare tra i fornitori di soluzioni MDM.

## Impedire la modifica delle impostazioni
I dipendenti sono in genere autorizzati a modificare determinate impostazioni dei dispositivi, che potresti voler bloccare nei dispositivi aziendali. I dipendenti possono modificare in modo interattivo alcune impostazioni di HoloLens tramite l'interfaccia utente delle impostazioni. Puoi usare MDM per limitare le impostazioni di cui è consentita la modifica. Di seguito sono elencate le impostazioni di MDM usate di frequente che Windows 10 olografico supporta per configurare le restrizioni delle impostazioni:
-   [Consenti VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Consente all'utente di modificare le impostazioni VPN
-   [Consentire la configurazione manuale WiFi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Consente agli utenti di effettuare connessioni Wi-Fi all'esterno delle reti con provisioning MDM
-   [Consenti la registrazione MDM manuale](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se gli utenti possono eliminare l'account di lavoro (ad esempio, annullare la registrazione del dispositivo dal sistema MDM)

Per altre informazioni sulle opzioni dei criteri, vedere [DSN sui criteri](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) supportati da HoloLens

## Restrizioni hardware
I dispositivi olografici di Windows 10 usano tecnologie all'avanguardia che includono caratteristiche hardware popolari come fotocamere, microfoni, altoparlanti, interfacce USB, interfacce Bluetooth e Wi-Fi. Puoi usare le restrizioni hardware per controllare la disponibilità di queste funzionalità.
Di seguito sono elencate le impostazioni di MDM comunemente usate che Windows 10 olografico supporta per configurare le restrizioni hardware:

> [!NOTE]
> Alcune di queste restrizioni hardware influenzano la connettività e aiutano la protezione dei dati.

-   [Consenti Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se gli utenti possono abilitare e usare la radio WiFi nei loro dispositivi.
-   [Consenti connessione USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Indipendentemente dal fatto che la connessione USB sia abilitata (non influenza la ricarica USB)
-   [Consenti Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se gli utenti possono abilitare e usare la radio Bluetooth sui loro dispositivi.
-   [Limitare la fotocamera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Specifica se le app di Windows possono accedere alla videocamera.
-   [Limitare i microfoni:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Specifica se le app di Windows possono accedere al microfono.
