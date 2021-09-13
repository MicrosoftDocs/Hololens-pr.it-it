---
title: Restrizioni comuni dei dispositivi
description: Rimanere aggiornati con le restrizioni e le impostazioni comuni del dispositivo HoloLens dispositivo di realtà mista.
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
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032548"
---
# <a name="common-device-restrictions"></a>Restrizioni comuni dei dispositivi 

Questa guida consente ai professionisti IT di comprendere le opzioni di gestione più comunemente usate disponibili per il Windows 10 Holographic sistema operativo aziendale. Per informazioni su come questi criteri vengono abilitati dal tuo fornitore del sistema MDM, consulta la documentazione specifica. Non tutti i sistemi MDM supportano ogni impostazione descritta in questa Guida. Alcuni supportano criteri personalizzati tramite file XML OMA-URI. Vedi le informazioni sul [supporto dei criteri personalizzati in Microsoft Intune](/mem/intune/configuration/custom-settings-windows-10). Le convenzioni di denominazione possono anche variare tra i fornitori di soluzioni MDM.

## <a name="prevent-changing-of-settings"></a>Impedire la modifica delle impostazioni
I dipendenti sono in genere autorizzati a modificare determinate impostazioni dei dispositivi, che potresti voler bloccare nei dispositivi aziendali. I dipendenti possono modificare in modo interattivo determinate impostazioni del HoloLens tramite l'interfaccia utente delle impostazioni. Puoi usare MDM per limitare le impostazioni di cui è consentita la modifica. Di seguito sono elencate le impostazioni MDM di uso comune Windows 10 Holographic supportano per configurare le restrizioni delle impostazioni:
-   [Consenti VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Consente all'utente di modificare le impostazioni VPN
-   [Consenti configurazione Wi-Fi manuale:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Consente agli utenti di effettuare Wi-Fi connessioni esterne alle reti con provisioning MDM
-   [Consenti annullamento manuale della registrazione MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se agli utenti è consentito eliminare l'account aziendale(ad esempio, annullare la registrazione del dispositivo dal sistema MDM)

Aggiunta in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) per HoloLens 2 dispositivi:
- [Consenti aggiunta pacchetto di provisioning:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Attivare o disattivare se gli utenti possono aggiungere nuovi pacchetti di provisioning, sovrascrivendo con nuovi valori.
- [Consenti rimozione pacchetto di provisioning:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Attivare o disattivare se gli utenti possono rimuovere i pacchetti di provisioning, consentendo loro di attivare o disattivare le impostazioni bloccate in precedenza.

Per altre informazioni sulle opzioni dei criteri, vedere HoloLens criteri [supportati](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Restrizioni hardware
Windows 10 Holographic i dispositivi usano una tecnologia all'avanguardia che include funzionalità hardware comuni come fotocamere, microfoni, altoparlanti, interfacce USB, interfacce Bluetooth e Wi-Fi. Puoi usare le restrizioni hardware per controllare la disponibilità di queste funzionalità.
Di seguito sono elencate le impostazioni MDM di uso comune supportate Windows 10 Holographic per configurare le restrizioni hardware:

> [!NOTE]
> Alcune di queste restrizioni hardware influiscono sulla connettività e sono utili per la protezione dei dati.

-   [Consenti Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Indica se gli utenti possono abilitare e usare la radio Wi-Fi nei propri dispositivi.
-   [Consenti connessione USB:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Indica se la connessione USB è abilitata (non influisce sulla ricarica USB).
-   [Consenti Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Indica se gli utenti possono abilitare e usare la Bluetooth radio nei propri dispositivi.
-   [Limita fotocamera:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Specifica se le Windows possono accedere alla fotocamera.
-   [Limita microfoni:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Specifica se le Windows possono accedere al microfono.

Aggiunta in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) per HoloLens 2 dispositivi. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Impostare l'intervallo di tempo fino a quando la visualizzazione non si spegne e, disattivando lo schermo, blocca il dispositivo. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Impostare l'intervallo di tempo fino a quando la visualizzazione non si spegne e, disattivando lo schermo, blocca il dispositivo. 
