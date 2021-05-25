---
title: Visibilità delle impostazioni della pagina
description: Tenersi aggiornati con l'elenco degli URI supportati per PageVisibilityList e la Guida sui dispositivi di realtà mista HoloLens.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, accesso assegnato, chiosco multimediale, pagina impostazioni
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397872"
---
# <a name="page-settings-visibility"></a>Visibilità delle impostazioni della pagina

Una delle funzionalità gestibili per i dispositivi HoloLens è l'uso dei criteri [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visibili all'interno dell'app Settings. PageVisibilityList è un criterio che consente agli amministratori IT di impedire che pagine specifiche nell'app Impostazioni di sistema siano visibili o accessibili oppure di eseguire questa operazione per tutte le pagine ad eccezione di quelle specificate.

> [!NOTE]
> Questa funzionalità è disponibile solo in [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o successiva per HoloLens 2 dispositivi. Assicurarsi che i dispositivi per cui si intende usarlo siano aggiornati.

L'esempio seguente illustra un criterio che consente l'accesso solo alle pagine about e bluetooth, che hanno rispettivamente l'URI "ms-settings:network-wifi" e "ms-settings:bluetooth":
- `showonly:network-wifi;network-proxy;bluetooth`

Per impostare questa opzione tramite un pacchetto di provisioning:

1. Durante la creazione del pacchetto in Progettazione configurazione di Windows passare **a Criteri > impostazioni > PaginaVisibilityList**
1. Immettere la stringa: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Esportare il pacchetto di provisioning.
1. Applicare il pacchetto al dispositivo.
Per informazioni dettagliate su come creare e applicare un pacchetto di provisioning, visitare [questa pagina](hololens-provisioning.md).

Questa operazione può essere eseguita tramite Intune usando URI OMA:

1. Creare un **criterio personalizzato.**
1. Quando si imposta OMA-URI, usare la stringa: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Quando si seleziona la selezione dati, scegliere: **Stringa**
1. Quando si digita il valore, usare: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Assicurarsi di assegnare la configurazione del dispositivo personalizzata a un gruppo in cui il dispositivo è destinato.

Per altre informazioni sui gruppi di Intune e sulle configurazioni dei dispositivi, vedere Configurazione MDM di [HoloLens.](hololens-mdm-configure.md)

Indipendentemente dal metodo scelto, il dispositivo riceverà ora le modifiche e agli utenti verrà visualizzata l'app impostazioni seguente.

![Screenshot delle ore attive modificate nell'app Impostazioni](images/hololens-page-visibility-list.jpg)

Per configurare le pagine dell'app Impostazioni per mostrare o nascondere la propria selezione di pagine, esaminare gli URI delle impostazioni disponibili in HoloLens.

## <a name="settings-uris"></a>URI delle impostazioni

I dispositivi HoloLens e Windows 10 hanno una selezione diversa di pagine all'interno dell'app Impostazioni. In questa pagina sono disponibili solo le impostazioni presenti in HoloLens.

### <a name="accounts"></a>Account
| Pagina Impostazioni           | URI                                            |
|-------------------------|------------------------------------------------|
| Accedi all'azienda o all'istituto di istruzione | `ms-settings:workplace`                         |
| Registrazione Iris       | `ms-settings:signinoptions-launchirisenrollment` |
| Opzioni di accesso         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>App
| Pagina Impostazioni | URI                          |
|---------------|------------------------------|
| App & funzionalità<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Funzionalità & app > Opzioni avanzate <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| App & funzionalità > Mappe offline <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| App & funzionalità > mappe offline > Mappe di download <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Dispositivi
| Pagina Impostazioni | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Mouse <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Privacy
| Pagina Impostazioni            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informazioni sull'account             | `ms-settings:privacy-accountinfo`              |
| Diagnostica app        | `ms-settings:privacy-appdiagnostics`              |
| App in background        | `ms-settings:privacy-backgroundapps`              |
| Calendario                 | `ms-settings:privacy-calendar`                    |
| Registro chiamate             | `ms-settings:privacy-callhistory`                 |
| Fotocamera                   | `ms-settings:privacy-webcam`                      |
| Contatti                 | `ms-settings:privacy-contacts`                    |
| Commenti e suggerimenti & diagnostica | `ms-settings:privacy-feedback`                    |
| Documenti                | `ms-settings:privacy-documents`                   |
| E-mail                    | `ms-settings:privacy-email`                       |
| File system              | `ms-settings:privacy-broadfilesystemaccess`       |
| Generale <sup>2</sup>             | `ms-settings:privacy-general`       |
| Personalizzazione & input penna <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Location                 | `ms-settings:privacy-location`                    |
| Messaggistica                | `ms-settings:privacy-messaging`                   |
| Microfono               | `ms-settings:privacy-microphone`                  |
| Movimento <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Notifiche            | `ms-settings:privacy-notifications`               |
| Altri dispositivi            | `ms-settings:privacy-customdevices`               |
| Immagini                 | `ms-settings:privacy-pictures`                    |
| Radio                   | `ms-settings:privacy-radios`                      |
| Bordi dello screenshot <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Screenshot e app <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Voce                   | `ms-settings:privacy-speech`                      |
| Attività                    | `ms-settings:privacy-tasks`                       |
| Movimenti dell'utente           | `ms-settings:privacy-backgroundspatialperception` |
| Video                   | `ms-settings:privacy-videos`                      |
| Attivazione vocale       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Rete e Internet
| Pagina Impostazioni | URI                              |
|---------------|----------------------------------|
| Modalità aereo <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| Connessione   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>Sistema
| Pagina Impostazioni      | URI                                |
|--------------------|------------------------------------|
| Batteria <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Batteria <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Colori             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Ologrammi <sup>2</sup>  |  `ms-settings:holograms`  |
| <sup>Calibrazione 2</sup> |  `ms-settings:calibration` |
| Notifiche e azioni  | `ms-settings:notifications`          |
| Esperienze condivise | `ms-settings:crossdevice` 
| Audio <sup>2</sup>           | `ms-settings:sound`<br>|
| Audio > volume dell'app e preferenza del dispositivo <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Gestione > audio <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Archiviazione            | `ms-settings:storagesense`           |
| Storage > Configue Sensore memoria <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Lingua & ora
| Pagina Impostazioni | URI                                           |
|---------------|-----------------------------------------------|
| Data & <sup>2</sup> | `ms-settings:dateandtime`                  |
| Tastiera <sup>2</sup> | `ms-settings:keyboard`                  |
| Lingua <sup>2</sup> | `ms-settings:language`                  |
| Lingua <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Linguaggio      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Region        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Aggiornare & sicurezza
| Pagina Impostazioni                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Opzioni avanzate                    | `ms-settings:windowsupdate-options`         |
| Ripristino & ripristino <sup>2</sup>      | `ms-settings:reset`         |
| Programma Windows Insider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update - Verifica la disponibilità di aggiornamenti | `ms-settings:windowsupdate-action`          |


>  <sup>1</sup> Per le versioni precedenti a Windows Holographic, versione 21H1, i  due URI **seguenti** non visualizzano effettivamente le pagine Opzioni avanzate. bloccano o visualizzano solo la pagina Windows Update principale.
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions
 
> <sup>2</sup> - Disponibile in Windows Holographic 21H1 o versione successiva.


Per un elenco completo degli URI Windows 10 impostazioni, vedere la documentazione [relativa alle impostazioni di](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) avvio.
