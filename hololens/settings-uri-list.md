---
title: Impostazioni URI
description: Elenco degli URI supportati da HoloLens per PageVisibilityList
author: evmill
ms.author: v-evmill
ms.date: 09/16/2020
ms.topic: article
keywords: hololens, hololens 2, accesso assegnato, chiosco, pagina impostazioni
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 17959fa25763d2c6b89d0956f29b9999b3012e60
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016700"
---
# Impostazioni URI

L’uso di [criteri Impostazioni/pageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visualizzate all’interno dell’app, è una delle funzionalità gestibili per i dispositivi HoloLens. PageVisibilityList è un criterio che consente agli amministratori IT di impedire che pagine specifiche nelle impostazioni di sistema siano visibili o accessibili oppure di farlo per tutte le pagine ad accezioni di quelle specificate. 

> [!IMPORTANT]
> Questa funzionalità è attualmente disponibile solo nelle [build di Windows Insider](hololens-insider.md). Assicurarsi che i dispositivi che si intende usare siano presenti nella build 19041.1349+.

L'esempio seguente illustra un criterio che consente l'accesso solo alle pagine Informazioni e Bluetooth, che hanno rispettivamente l'URI "ms-settings:network-wifi" e "ms-settings:bluetooth":
- showonly:network-wifi;network-proxy;bluetooth

Per impostare questa impostazione con un pacchetto di provisioning: 
1. Durante la creazione del pacchetto in Progettazione configurazione di Windows, andare a **Criteri > Impostazioni > PageVisibilityList**
1. Inserire la stringa: **showonly:network-wifi;network-proxy;bluetooth**
1. Esportare il pacchetto di provisioning.
1. Applicare il pacchetto al dispositivo. Per informazioni dettagliate su come creare e applicare un pacchetto di provisioning, visitare [questa pagina](hololens-provisioning.md). 

Questa operazione può essere eseguita tramite Intune usando OMA-URI.
1. Crea un **criterio personalizzato**.
1. Durante l'installazione dell'OMA-UR, usare la stringa: **./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList**
1. Quando si seleziona i dati scegliere: **stringa**
1. Quando si digita il valore, usare: **showonly:network-wifi;network-proxy;bluetooth**
1. Assicurarsi di assegnare la configurazione di un dispositivo personalizzato a un gruppo all’interno del quale il dispositivo deve essere.
Per altre informazioni sui gruppi Intune e sulle configurazioni dei dispositivi Intune fare clic [qui](hololens-mdm-configure.md).

Indipendentemente dal metodo scelto, il dispositivo dovrebbe ora ricevere le modifiche e agli utenti verrà presentata la seguente app Impostazioni. 

![Schermata dell'orario di attività in fase di modifica nell'app Impostazioni](images/hololens-page-visibility-list.jpg)

Per configurare le pagine dell'app Impostazioni in modo da visualizzare o nascondere una selezione di pagine, vedere le impostazioni URI disponibili in HoloLens. 

## Impostazioni URI

I dispositivi HoloLens e i dispositivi Windows 10 hanno una selezione di pagine diversa nelle Impostazioni dell’app. In questa pagina ci sono solo le impostazioni disponibili in HoloLens. 

### Account
| Pagina delle impostazioni           | URI                                            |
|-------------------------|------------------------------------------------|
| Opzioni di accesso         | ms-settings:signinoptions                      |
| Registrazione Iris       | ms-settings:signinoptions-launchirisenrollment |
| Accedi all'azienda o all'istituto di istruzione | ms-settings:workplace                          |

### Dispositivi
| Pagina delle impostazioni | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

### Privacy
| Pagina delle impostazioni            | URI                                             |
|--------------------------|-------------------------------------------------|
| Info account             | ms-settings:privacy-accountinfo                 |
| Diagnostica dell'app        | ms-settings:privacy-appdiagnostics              |
| App in background        | ms-settings:privacy-backgroundapps              |
| Movimenti degli utenti           | ms-settings:privacy-backgroundspatialperception |
| File system              | ms-settings:privacy-broadfilesystemaccess       |
| Calendario                 | ms-settings:privacy-calendar                    |
| Registro chiamate             | ms-settings:privacy-callhistory                 |
| Contatti                 | ms-settings:privacy-contacts                    |
| Altri dispositivi            | ms-settings:privacy-customdevices               |
| Documenti                | ms-settings:privacy-documents                   |
| E-mail                    | ms-settings:privacy-email                       |
| Diagnostica e Feedback | ms-settings:privacy-feedback                    |
| Location                 | ms-settings:privacy-location                    |
| Messaggi                | ms-settings:privacy-messaging                   |
| Microfono               | ms-settings:privacy-microphone                  |
| Notifications            | ms-settings:privacy-notifications               |
| Immagini                 | ms-settings:privacy-pictures                    |
| Radio                   | ms-settings:privacy-radios                      |
| Comandi vocali                   | ms-settings:privacy-speech                      |
| Attività                    | ms-settings:privacy-tasks                       |
| Video                   | ms-settings:privacy-videos                      |
| Attivazione vocale       | ms-settings:privacy-voiceactivation             |
| Fotocamera                   | ms-settings:privacy-webcam                      |

### Rete e Internet
| Pagina delle impostazioni | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

### Sistema
| Pagina delle impostazioni      | URI                                |
|--------------------|------------------------------------|
| Esperienze condivise | ms-settings:crossdevice            |
| Colori             | ms-settings:colors<br>ms-settings:personalization-colors |
| Notifiche e azioni  | ms-settings:notifications          |
| Archiviazione            | ms-settings:storagesense           |

### Data/ora e lingua
| Pagina delle impostazioni | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| Lingua      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

### Aggiornamento e sicurezza
| Pagina delle impostazioni                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Programma Windows Insider               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows Update                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows Update - Verifica la disponibilità di aggiornamenti | ms-settings:windowsupdate-action          |
| Opzioni avanzate                    | ms-settings:windowsupdate-options         |

> [!NOTE]
>  1 I due URI seguenti non portano alle Opzioni Avanzate o la pagina Opzioni, bloccano/mostrano solo la pagina principale di Windows Update. 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Per un elenco completo degli URI delle impostazioni di Windows 10, visitare [questa pagina](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference). 
