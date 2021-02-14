---
title: Visibilità impostazioni pagina
description: Tieniti aggiornato con l'elenco degli URI supportati per PageVisibilityList e la guida sui dispositivi di realtà mista HoloLens.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, accesso assegnato, chiosco, pagina impostazioni
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327390"
---
# Visibilità impostazioni pagina

L’uso di [criteri Impostazioni/pageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visualizzate all’interno dell’app, è una delle funzionalità gestibili per i dispositivi HoloLens. PageVisibilityList è un criterio che consente agli amministratori IT di impedire che pagine specifiche nelle impostazioni di sistema siano visibili o accessibili oppure di farlo per tutte le pagine ad accezioni di quelle specificate.

> [!NOTE]
> Questa funzionalità è disponibile solo in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) per i dispositivi HoloLens 2. Assicurarsi che i dispositivi per cui si intende utilizzarlo siano aggiornati.

> [!NOTE]
> Oltre 20 nuovi SettingsURI verranno aggiunti a breve. Visita la [pagina di Windows Insider - Nuovi SettingsURI per la visibilità delle impostazioni della pagina](hololens-insider.md#new-settingsuris-for-page-settings-visibility) se sei interessato ad usare in anteprima questa funzionalità con una build di [HoloLens Insider](hololens-insider.md).

L'esempio seguente illustra un criterio che consente l'accesso solo alle pagine Informazioni e Bluetooth, che hanno rispettivamente l'URI "ms-settings:network-wifi" e "ms-settings:bluetooth":
- `showonly:network-wifi;network-proxy;bluetooth`

Per impostare questa impostazione con un pacchetto di provisioning:

1. Durante la creazione del pacchetto in Progettazione configurazione di Windows, passa a **Criteri > Impostazioni > PageVisibilityList**
1. Immetti la stringa: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Esporta il pacchetto di provisioning.
1. Applica il pacchetto al dispositivo.
Per informazioni dettagliate su come creare e applicare un pacchetto di provisioning, visita [questa pagina.](hololens-provisioning.md)

Questa operazione può essere eseguita tramite Intune usando OMA-URI:

1. Crea un **criterio personalizzato**.
1. Quando imposti l'OMA-URI, usa la stringa: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Quando selezioni i dati, scegli: **stringa**
1. Quando inserisci il valore, utilizza: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Assicurati di assegnare la configurazione di un dispositivo personalizzato a un gruppo all'interno del quale il dispositivo deve essere.

Per altre informazioni sui gruppi di Intune e sulle configurazioni di dispositivi, vedi [configurazione MDM di HoloLens](hololens-mdm-configure.md).

Indipendentemente dal metodo scelto, il dispositivo riceverà le modifiche e gli utenti riceveranno l'app Impostazioni seguente.

![Schermata dell'orario di attività che viene modificato nell'app Impostazioni](images/hololens-page-visibility-list.jpg)

Per configurare le pagine dell'app Impostazioni in modo da mostrare o nascondere la tua selezione di pagine, dai un'occhiata agli URI delle impostazioni disponibili in HoloLens.

## Impostazioni URI

I dispositivi HoloLens e i dispositivi Windows 10 hanno una selezione delle pagine diversa nell'app Impostazioni. In questa pagina troverai solo le impostazioni presenti in HoloLens.

### Account
| Pagina delle impostazioni           | URI                                            |
|-------------------------|------------------------------------------------|
| Opzioni di accesso         | ` ms-settings:signinoptions `                   |
| Registrazione Iris       | `ms-settings:signinoptions-launchirisenrollment` |
| Accedi all'azienda o all'istituto di istruzione | `ms-settings:workplace`                         |

### Dispositivi
| Pagina delle impostazioni | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### Privacy
| Pagina delle impostazioni            | URI                                             |
|--------------------------|-------------------------------------------------|
| Info account             | `ms-settings:privacy-accountinfo`              |
| Diagnostica app        | `ms-settings:privacy-appdiagnostics`              |
| App in background        | `ms-settings:privacy-backgroundapps`              |
| Movimenti degli utenti           | `ms-settings:privacy-backgroundspatialperception` |
| File system              | `ms-settings:privacy-broadfilesystemaccess`       |
| Calendario                 | `ms-settings:privacy-calendar`                    |
| Registro chiamate             | `ms-settings:privacy-callhistory`                 |
| Contatti                 | `ms-settings:privacy-contacts`                    |
| Altri dispositivi            | `ms-settings:privacy-customdevices`               |
| Documenti                | `ms-settings:privacy-documents`                   |
| Posta elettronica                    | `ms-settings:privacy-email`                       |
| Diagnostica e feedback | `ms-settings:privacy-feedback`                    |
| Posizione                 | `ms-settings:privacy-location`                    |
| Messaggi                | `ms-settings:privacy-messaging`                   |
| Microfono               | `ms-settings:privacy-microphone`                  |
| Notifiche            | `ms-settings:privacy-notifications`               |
| Immagini                 | `ms-settings:privacy-pictures`                    |
| Radio                   | `ms-settings:privacy-radios`                      |
| Comandi vocali                   | `ms-settings:privacy-speech`                      |
| Attività                    | `ms-settings:privacy-tasks`                       |
| Video                   | `ms-settings:privacy-videos`                      |
| Attivazione vocale       | `ms-settings:privacy-voiceactivation`             |
| Fotocamera                   | `ms-settings:privacy-webcam`                      |

### Rete e internet
| Pagina delle impostazioni | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| VPN   | `ms-settings:network-vpn`          |
| Proxy | `ms-settings:network-proxy`        |

### Sistema
| Pagina delle impostazioni      | URI                                |
|--------------------|------------------------------------|
| Esperienze condivise | `ms-settings:crossdevice`            |
| Colori             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Notifiche e azioni  | `ms-settings:notifications`          |
| Archiviazione            | `ms-settings:storagesense`           |

### Data/ora e lingua
| Pagina delle impostazioni | URI                                           |
|---------------|-----------------------------------------------|
| Regione        | `ms-settings:regionformatting`                  |
| Lingua      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### Aggiornamento e sicurezza
| Pagina delle impostazioni                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Programma Windows Insider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update - Verifica la disponibilità di aggiornamenti | `ms-settings:windowsupdate-action`          |
| Opzioni avanzate                    | `ms-settings:windowsupdate-options`         |

>  <sup>1 </sup> I due URI seguenti non portano alle **Opzioni Avanzate** o alla pagina **Opzioni**, bloccano/mostrano solo la pagina principale di Windows Update.
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Per un elenco completo degli URI delle impostazioni di Windows 10, visitare la documentazione relativa alle [impostazioni di avvio](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
