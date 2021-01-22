---
title: Restrizioni del dispositivo comuni
description: Mantieniti aggiornato con le restrizioni e le impostazioni comuni per il dispositivo di realtà mista HoloLens.
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
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283357"
---
# Restrizioni del dispositivo comuni 

Questa guida consente ai professionisti IT di comprendere le opzioni di gestione più utilizzate disponibili per il sistema operativo Windows 10 Holographic nell'azienda. Per informazioni su come questi criteri vengono abilitati dal tuo fornitore del sistema MDM, consulta la documentazione specifica. Non tutti i sistemi MDM supportano ogni impostazione descritta in questa Guida. Alcuni supportano criteri personalizzati tramite file XML OMA-URI. Vedi le informazioni sul [supporto dei criteri personalizzati in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Le convenzioni di denominazione possono anche variare tra i fornitori di soluzioni MDM.

## Impedire la modifica delle impostazioni
I dipendenti sono in genere autorizzati a modificare determinate impostazioni dei dispositivi, che potresti voler bloccare nei dispositivi aziendali. I dipendenti possono modificare in modo interattivo determinate impostazioni di HoloLens tramite l'interfaccia utente delle impostazioni. Puoi usare MDM per limitare le impostazioni di cui è consentita la modifica. Di seguito sono elencate le impostazioni MDM di uso comune supportate da Windows 10 Holographic per configurare le restrizioni delle impostazioni:
-   [Consenti VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Consente all'utente di modificare le impostazioni VPN
-   [Consenti configurazione WiFi manuale:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Consente agli utenti di effettuare Wi-Fi connessioni esterne alle reti di provisioning MDM
-   [Consenti annullamento manuale della registrazione MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Indica se agli utenti è consentito eliminare l'account aziendale (ad esempio, annullare la registrazione del dispositivo dal sistema MDM)

Aggiunta in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) per dispositivi HoloLens 2:
- [Consenti aggiunta pacchetto di provisioning:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Attiva/disattiva se gli utenti possono aggiungere nuovi pacchetti di provisioning, sovrascrivendo con nuovi valori.
- [Consenti rimozione pacchetto di provisioning:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Attiva/disattiva se gli utenti possono rimuovere i pacchetti di provisioning, consentendo loro di attivare o disattivare le impostazioni bloccate in precedenza.

Altri dettagli sulle opzioni dei criteri nei CSP dei criteri supportati [da](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) HoloLens

## Restrizioni hardware
I dispositivi Windows 10 Holographic usano una tecnologia all'avanguardia che include funzionalità hardware popolari come fotocamere, microfoni, altoparlanti, interfacce USB, interfacce Bluetooth e Wi-Fi. Puoi usare le restrizioni hardware per controllare la disponibilità di queste funzionalità.
Di seguito sono elencate le impostazioni MDM di uso comune supportate da Windows 10 Holographic per configurare le restrizioni hardware:

> [!NOTE]
> Alcune di queste restrizioni hardware influiscono sulla connettività e sono utili per la protezione dei dati.

-   [Consenti Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Indica se gli utenti possono abilitare e usare la radio WiFi nei propri dispositivi.
-   [Consenti connessione USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Indica se la connessione USB è abilitata (non influisce sulla ricarica USB).
-   [Consenti Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Indica se gli utenti possono abilitare e usare la Bluetooth radio nei propri dispositivi.
-   [Limita fotocamera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Specifica se le app di Windows possono accedere alla fotocamera.
-   [Limita microfoni:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Specifica se le app di Windows possono accedere al microfono.

Aggiunta in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) per dispositivi HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Imposta l'intervallo di tempo fino a quando lo schermo non si spegne e, disattivando lo schermo, blocca il dispositivo. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Imposta l'intervallo di tempo fino a quando lo schermo non si spegne e, disattivando lo schermo, blocca il dispositivo. 
