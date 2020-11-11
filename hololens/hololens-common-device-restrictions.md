---
title: Restrizioni del dispositivo comuni
description: Il dispositivo restrctions comunemente impostato su HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 744d54a344867c5c38681781580f5357e0a0da70
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162959"
---
# Restrizioni del dispositivo comuni 

Questa guida aiuta i professionisti IT a comprendere le opzioni di gestione più comunemente usate disponibili per il sistema operativo Windows 10 olografico nell'organizzazione. Per informazioni su come questi criteri vengono abilitati dal tuo fornitore del sistema MDM, consulta la documentazione specifica. Non tutti i sistemi MDM supportano ogni impostazione descritta in questa Guida. Alcuni supportano criteri personalizzati tramite file XML OMA-URI. Vedi le informazioni sul [supporto dei criteri personalizzati in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Le convenzioni di denominazione possono anche variare tra i fornitori di soluzioni MDM.

## Impedire la modifica delle impostazioni
I dipendenti sono in genere autorizzati a modificare determinate impostazioni dei dispositivi, che potresti voler bloccare nei dispositivi aziendali. I dipendenti possono modificare in modo interattivo alcune impostazioni di HoloLens tramite l'interfaccia utente delle impostazioni. Puoi usare MDM per limitare le impostazioni di cui è consentita la modifica. Di seguito sono elencate le impostazioni di MDM usate di frequente che Windows 10 olografico supporta per configurare le restrizioni delle impostazioni:
-   [Consenti VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Consente all'utente di modificare le impostazioni VPN
-   [Consentire la configurazione manuale WiFi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Consente agli utenti di effettuare connessioni Wi-Fi all'esterno delle reti con provisioning MDM
-   [Consenti la registrazione MDM manuale](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se gli utenti possono eliminare l'account di lavoro (ad esempio, annullare la registrazione del dispositivo dal sistema MDM)

Aggiunto in [Windows olografico versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) per i dispositivi HoloLens 2:
- [Consenti Aggiungi pacchetto di provisioning:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Toggle se gli utenti possono aggiungere nuovi pacchetti di provisioning, sovrascrivendo i nuovi valori.
- [Consenti Rimuovi pacchetto di provisioning:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Toggle se gli utenti possono rimuovere i pacchetti di provisioning, consentendo loro di attivare o disattivare le impostazioni precedentemente bloccate.

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

Aggiunto in [Windows olografico, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) per i dispositivi HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Impostare l'intervallo di tempo finché la visualizzazione non viene disattivata e, per disattivare la visualizzazione, blocca il dispositivo. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Impostare l'intervallo di tempo finché la visualizzazione non viene disattivata e, per disattivare la visualizzazione, blocca il dispositivo. 
