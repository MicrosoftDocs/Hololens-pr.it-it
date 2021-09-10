---
title: Visibilità Impostazioni pagina
description: Tenersi aggiornati con l'elenco degli URI supportati per PageVisibilityList e la Guida HoloLens dispositivi di realtà mista.
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
ms.openlocfilehash: 92040019b093c5ef63d74f095dcb3809112ae7a0
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428713"
---
# <a name="page-settings-visibility"></a>Visibilità Impostazioni pagina

Una delle funzionalità gestibili per i dispositivi HoloLens usa i criteri [Impostazioni/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visibili all'interno dell'app Impostazioni. PageVisibilityList è un criterio che consente agli amministratori IT di impedire che pagine specifiche nell'app System Impostazioni siano visibili o accessibili oppure di eseguire questa operazione per tutte le pagine ad eccezione di quelle specificate.

> [!NOTE]
> Questa funzionalità è disponibile solo in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o successiva per HoloLens 2 dispositivi. Assicurarsi che i dispositivi per cui si intende usarlo siano aggiornati.


## <a name="examples"></a>Esempio
Le pagine sono identificate da una versione abbreviata degli URI pubblicati, ovvero l'URI meno il prefisso "ms-settings:".

L'esempio seguente illustra un criterio che consente l'accesso solo alle pagine About e Bluetooth, che hanno rispettivamente l'URI "network-wifi" e "bluetooth":
- `showonly:network-wifi;network-proxy;bluetooth`

L'esempio seguente illustra un criterio che nasconde la pagina Reimpostazione sistema operativo:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Distribuzione di questi criteri tramite Intune

Questi sono i valori di configurazione che verranno forniti a Intune:

- **Nome:** Nome visualizzato preferito dall'amministratore per il profilo.
- **URI OMA:** URI completo della pagina di impostazione, incluso il relativo [ambito](/windows/client-management/mdm/policy-configuration-service-provider). In questi esempi in questa pagina viene utilizzato `./Device` l'ambito .
- **Valore:** Valore stringa che indica se nascondere o visualizzare *solo* le pagine specificate. I valori possibili sono `hide:<pagename>` e `showonly:<pagename>`. 
 
È possibile specificare più pagine separandole con un punto e virgola. Di seguito è riportato un elenco di pagine comuni.

1. Creare un **criterio personalizzato.**
1. Quando si imposta **OMA-URI,** immettere l'URI con ambito completo. Per esempio: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Quando si seleziona la selezione dati, scegliere: **Stringa**
1. Quando si specifica **Valore,** usare le indicazioni riportate in precedenza. Ad esempio: **`showonly:network-wifi;network-proxy;bluetooth`** o **`hide:reset`** 
> [!IMPORTANT]
> Assicurarsi di assegnare la configurazione del dispositivo personalizzata a un gruppo in cui deve essere presente il dispositivo. Se questo passaggio non viene eseguito, verrà eseguito il push dei criteri, ma non verrà applicato.

Vedere [HoloLens MDM per](hololens-mdm-configure.md) altre informazioni sui gruppi di Intune e sulle configurazioni dei dispositivi.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Distribuzione di questo criterio tramite un pacchetto di provisioning

Questi sono i valori di configurazione che verranno specificati in Progettazione Windows configurazione:

**Valore:** Valore stringa che indica se nascondere o visualizzare *solo* le pagine specificate. I valori possibili sono `hide:<pagename>` e `showonly:<pagename>`. È possibile specificare più pagine separandole con un punto e virgola. Di seguito è riportato un elenco di pagine comuni.


1. Durante la creazione del pacchetto in Progettazione Windows configurazione passare **a Criteri > Impostazioni > PageVisibilityList**
1. Immettere la stringa: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Esportare il pacchetto di provisioning.
1. Applicare il pacchetto al dispositivo.
Per informazioni dettagliate su come creare e applicare un pacchetto di provisioning, visitare la [pagina HoloLens provisioning .](hololens-provisioning.md)


Indipendentemente dal metodo scelto, il dispositivo dovrebbe ora ricevere le modifiche e agli utenti verrà visualizzata la seguente Impostazioni app.

![Screenshot delle ore attive modificate nell'app Impostazioni lavoro.](images/hololens-page-visibility-list.jpg)

Per configurare le Impostazioni dell'app per mostrare o nascondere la propria selezione di pagine, esaminare gli URI Impostazioni disponibili in HoloLens.

## <a name="settings-uris"></a>Impostazioni Uri

HoloLens dispositivi e Windows 10 hanno una selezione diversa di pagine all'interno dell Impostazioni app. In questa pagina sono disponibili solo le impostazioni esistenti in HoloLens.

### <a name="accounts"></a>Account
| Pagina Impostazioni           | URI                                            |
|-------------------------|------------------------------------------------|
| Accedi all'azienda o all'istituto di istruzione | `workplace`                         |
| Registrazione Iris       | `signinoptions-launchirisenrollment` |
| Opzioni di accesso         | ` signinoptions `                   |

### <a name="apps"></a>App
| Pagina Impostazioni | URI                          |
|---------------|------------------------------|
| App & funzionalità <sup>2</sup>     | `appsfeatures` <br> |
| Funzionalità & app > Opzioni avanzate <sup>2</sup>     | `appsfeatures-app` <br> |
| App & funzionalità > offline Mappe <sup>2</sup>     | `maps-maps` <br> |
| App & funzionalità > offline Mappe > Download maps <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Dispositivi
| Pagina Impostazioni | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Mouse <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Privacy
| Pagina Impostazioni            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informazioni sull'account             | `privacy-accountinfo`              |
| Diagnostica app        | `privacy-appdiagnostics`              |
| App in background        | `privacy-backgroundapps`              |
| Calendario                 | `privacy-calendar`                    |
| Registro chiamate             | `privacy-callhistory`                 |
| Fotocamera                   | `privacy-webcam`                      |
| Contatti                 | `privacy-contacts`                    |
| Commenti e suggerimenti & diagnostica | `privacy-feedback`                    |
| Documenti                | `privacy-documents`                   |
| E-mail                    | `privacy-email`                       |
| File system              | `privacy-broadfilesystemaccess`       |
| Generale <sup>2</sup>             | `privacy-general`       |
| Personalizzazione & input penna <sup>2</sup>             | `privacy-speechtyping`       |
| Località                 | `privacy-location`                    |
| Messaggistica                | `privacy-messaging`                   |
| Microfono               | `privacy-microphone`                  |
| Movimento <sup>2</sup>               | `privacy-motion`                  |
| Notifiche            | `privacy-notifications`               |
| Altri dispositivi            | `privacy-customdevices`               |
| Immagini                 | `privacy-pictures`                    |
| Radio                   | `privacy-radios`                      |
| Bordi dello screenshot <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Screenshot e app <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Voce                   | `privacy-speech`                      |
| Attività                    | `privacy-tasks`                       |
| Movimenti dell'utente           | `privacy-backgroundspatialperception` |
| Video                   | `privacy-videos`                      |
| Attivazione vocale       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Rete e Internet
| Pagina Impostazioni | URI                              |
|---------------|----------------------------------|
| Modalità aereo <sup>2</sup> | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| Connessione   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>Sistema
| Pagina Impostazioni      | URI                                |
|--------------------|------------------------------------|
| Batteria <sup>2</sup>           | `batterysaver`<br>|
| Batteria <sup>2</sup>           | `batterysaver-settings`<br>|
| Colori             | `colors`<br>`personalization-colors` |
| Ologrammi <sup>2</sup>  |  `holograms`  |
| <sup>Calibrazione 2</sup> |  `calibration` |
| Notifiche e azioni  | `notifications`          |
| Esperienze condivise | `crossdevice` 
| Audio <sup>2</sup>           | `sound`<br>|
| Audio > volume dell'app e preferenza del dispositivo <sup>2</sup>           | `apps-volume`<br>|
| Gestione > audio <sup>2</sup>           | `sound-devices`<br>|
| Archiviazione            | `storagesense`           |
| Archiviazione > Configurare Archiviazione Sense <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Lingua & ora
| Pagina Impostazioni | URI                                           |
|---------------|-----------------------------------------------|
| Data & <sup>2</sup> | `dateandtime`                  |
| Tastiera <sup>2</sup> | `keyboard`                  |
| Lingua <sup>2</sup> | `language`                  |
| Lingua <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Linguaggio      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Region        | `regionformatting`                  |

### <a name="update--security"></a>Aggiornare & sicurezza
| Pagina Impostazioni                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Opzioni avanzate                    | `windowsupdate-options`         |
| Ripristino & ripristino <sup>2</sup>      | `reset`         |
| Programma Windows Insider               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Aggiornamento: verifica la disponibilità di aggiornamenti | `windowsupdate-action`          |


- <sup>1</sup> - Per le versioni precedenti Windows Holographic, versione 21H1, i due URI  seguenti non visualizzano effettivamente le pagine Opzioni **avanzate;** verranno bloccate o mostrate solo le pagine Windows pagina Aggiorna.
  -  opzioni di windowsupdate
  -  windowsupdate-restartoptions

- <sup>2</sup> - Disponibile in Windows Holographic 21H1 o versione successiva.


Per un elenco completo degli URI Windows 10 Impostazioni, vedere la documentazione [relativa alle impostazioni di](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) avvio.
