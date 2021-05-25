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
# <a name="page-settings-visibility"></a><span data-ttu-id="35bdb-104">Visibilità delle impostazioni della pagina</span><span class="sxs-lookup"><span data-stu-id="35bdb-104">Page Settings Visibility</span></span>

<span data-ttu-id="35bdb-105">Una delle funzionalità gestibili per i dispositivi HoloLens è l'uso dei criteri [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visibili all'interno dell'app Settings.</span><span class="sxs-lookup"><span data-stu-id="35bdb-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="35bdb-106">PageVisibilityList è un criterio che consente agli amministratori IT di impedire che pagine specifiche nell'app Impostazioni di sistema siano visibili o accessibili oppure di eseguire questa operazione per tutte le pagine ad eccezione di quelle specificate.</span><span class="sxs-lookup"><span data-stu-id="35bdb-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="35bdb-107">Questa funzionalità è disponibile solo in [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o successiva per HoloLens 2 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="35bdb-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="35bdb-108">Assicurarsi che i dispositivi per cui si intende usarlo siano aggiornati.</span><span class="sxs-lookup"><span data-stu-id="35bdb-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="35bdb-109">L'esempio seguente illustra un criterio che consente l'accesso solo alle pagine about e bluetooth, che hanno rispettivamente l'URI "ms-settings:network-wifi" e "ms-settings:bluetooth":</span><span class="sxs-lookup"><span data-stu-id="35bdb-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="35bdb-110">Per impostare questa opzione tramite un pacchetto di provisioning:</span><span class="sxs-lookup"><span data-stu-id="35bdb-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="35bdb-111">Durante la creazione del pacchetto in Progettazione configurazione di Windows passare **a Criteri > impostazioni > PaginaVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="35bdb-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="35bdb-112">Immettere la stringa: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="35bdb-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="35bdb-113">Esportare il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="35bdb-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="35bdb-114">Applicare il pacchetto al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="35bdb-114">Apply the package to your device.</span></span>
<span data-ttu-id="35bdb-115">Per informazioni dettagliate su come creare e applicare un pacchetto di provisioning, visitare [questa pagina](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="35bdb-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="35bdb-116">Questa operazione può essere eseguita tramite Intune usando URI OMA:</span><span class="sxs-lookup"><span data-stu-id="35bdb-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="35bdb-117">Creare un **criterio personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="35bdb-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="35bdb-118">Quando si imposta OMA-URI, usare la stringa: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="35bdb-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="35bdb-119">Quando si seleziona la selezione dati, scegliere: **Stringa**</span><span class="sxs-lookup"><span data-stu-id="35bdb-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="35bdb-120">Quando si digita il valore, usare: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="35bdb-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="35bdb-121">Assicurarsi di assegnare la configurazione del dispositivo personalizzata a un gruppo in cui il dispositivo è destinato.</span><span class="sxs-lookup"><span data-stu-id="35bdb-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="35bdb-122">Per altre informazioni sui gruppi di Intune e sulle configurazioni dei dispositivi, vedere Configurazione MDM di [HoloLens.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="35bdb-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="35bdb-123">Indipendentemente dal metodo scelto, il dispositivo riceverà ora le modifiche e agli utenti verrà visualizzata l'app impostazioni seguente.</span><span class="sxs-lookup"><span data-stu-id="35bdb-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Screenshot delle ore attive modificate nell'app Impostazioni](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="35bdb-125">Per configurare le pagine dell'app Impostazioni per mostrare o nascondere la propria selezione di pagine, esaminare gli URI delle impostazioni disponibili in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="35bdb-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="35bdb-126">URI delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-126">Settings URIs</span></span>

<span data-ttu-id="35bdb-127">I dispositivi HoloLens e Windows 10 hanno una selezione diversa di pagine all'interno dell'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="35bdb-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="35bdb-128">In questa pagina sono disponibili solo le impostazioni presenti in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="35bdb-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="35bdb-129">Account</span><span class="sxs-lookup"><span data-stu-id="35bdb-129">Accounts</span></span>
| <span data-ttu-id="35bdb-130">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-130">Settings page</span></span>           | <span data-ttu-id="35bdb-131">URI</span><span class="sxs-lookup"><span data-stu-id="35bdb-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="35bdb-132">Accedi all'azienda o all'istituto di istruzione</span><span class="sxs-lookup"><span data-stu-id="35bdb-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="35bdb-133">Registrazione Iris</span><span class="sxs-lookup"><span data-stu-id="35bdb-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="35bdb-134">Opzioni di accesso</span><span class="sxs-lookup"><span data-stu-id="35bdb-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="35bdb-135">App</span><span class="sxs-lookup"><span data-stu-id="35bdb-135">Apps</span></span>
| <span data-ttu-id="35bdb-136">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-136">Settings page</span></span> | <span data-ttu-id="35bdb-137">URI</span><span class="sxs-lookup"><span data-stu-id="35bdb-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="35bdb-138">App & funzionalità<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="35bdb-139">Funzionalità & app > Opzioni avanzate <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="35bdb-140">App & funzionalità > Mappe offline <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="35bdb-141">App & funzionalità > mappe offline > Mappe di download <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="35bdb-142">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="35bdb-142">Devices</span></span>
| <span data-ttu-id="35bdb-143">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-143">Settings page</span></span> | <span data-ttu-id="35bdb-144">URI</span><span class="sxs-lookup"><span data-stu-id="35bdb-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="35bdb-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="35bdb-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="35bdb-146">Mouse <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="35bdb-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="35bdb-148">Privacy</span><span class="sxs-lookup"><span data-stu-id="35bdb-148">Privacy</span></span>
| <span data-ttu-id="35bdb-149">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-149">Settings page</span></span>            | <span data-ttu-id="35bdb-150">URI</span><span class="sxs-lookup"><span data-stu-id="35bdb-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="35bdb-151">Informazioni sull'account</span><span class="sxs-lookup"><span data-stu-id="35bdb-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="35bdb-152">Diagnostica app</span><span class="sxs-lookup"><span data-stu-id="35bdb-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="35bdb-153">App in background</span><span class="sxs-lookup"><span data-stu-id="35bdb-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="35bdb-154">Calendario</span><span class="sxs-lookup"><span data-stu-id="35bdb-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="35bdb-155">Registro chiamate</span><span class="sxs-lookup"><span data-stu-id="35bdb-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="35bdb-156">Fotocamera</span><span class="sxs-lookup"><span data-stu-id="35bdb-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="35bdb-157">Contatti</span><span class="sxs-lookup"><span data-stu-id="35bdb-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="35bdb-158">Commenti e suggerimenti & diagnostica</span><span class="sxs-lookup"><span data-stu-id="35bdb-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="35bdb-159">Documenti</span><span class="sxs-lookup"><span data-stu-id="35bdb-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="35bdb-160">E-mail</span><span class="sxs-lookup"><span data-stu-id="35bdb-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="35bdb-161">File system</span><span class="sxs-lookup"><span data-stu-id="35bdb-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="35bdb-162">Generale <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="35bdb-163">Personalizzazione & input penna <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="35bdb-164">Location</span><span class="sxs-lookup"><span data-stu-id="35bdb-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="35bdb-165">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="35bdb-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="35bdb-166">Microfono</span><span class="sxs-lookup"><span data-stu-id="35bdb-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="35bdb-167">Movimento <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="35bdb-168">Notifiche</span><span class="sxs-lookup"><span data-stu-id="35bdb-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="35bdb-169">Altri dispositivi</span><span class="sxs-lookup"><span data-stu-id="35bdb-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="35bdb-170">Immagini</span><span class="sxs-lookup"><span data-stu-id="35bdb-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="35bdb-171">Radio</span><span class="sxs-lookup"><span data-stu-id="35bdb-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="35bdb-172">Bordi dello screenshot <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="35bdb-173">Screenshot e app <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="35bdb-174">Voce</span><span class="sxs-lookup"><span data-stu-id="35bdb-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="35bdb-175">Attività</span><span class="sxs-lookup"><span data-stu-id="35bdb-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="35bdb-176">Movimenti dell'utente</span><span class="sxs-lookup"><span data-stu-id="35bdb-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="35bdb-177">Video</span><span class="sxs-lookup"><span data-stu-id="35bdb-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="35bdb-178">Attivazione vocale</span><span class="sxs-lookup"><span data-stu-id="35bdb-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="35bdb-179">Rete e Internet</span><span class="sxs-lookup"><span data-stu-id="35bdb-179">Network & Internet</span></span>
| <span data-ttu-id="35bdb-180">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-180">Settings page</span></span> | <span data-ttu-id="35bdb-181">URI</span><span class="sxs-lookup"><span data-stu-id="35bdb-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="35bdb-182">Modalità aereo <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="35bdb-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="35bdb-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="35bdb-184">Connessione</span><span class="sxs-lookup"><span data-stu-id="35bdb-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="35bdb-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="35bdb-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="35bdb-186">Sistema</span><span class="sxs-lookup"><span data-stu-id="35bdb-186">System</span></span>
| <span data-ttu-id="35bdb-187">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-187">Settings page</span></span>      | <span data-ttu-id="35bdb-188">URI</span><span class="sxs-lookup"><span data-stu-id="35bdb-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="35bdb-189">Batteria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="35bdb-190">Batteria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="35bdb-191">Colori</span><span class="sxs-lookup"><span data-stu-id="35bdb-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="35bdb-192">Ologrammi <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="35bdb-193"><sup>Calibrazione 2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="35bdb-194">Notifiche e azioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="35bdb-195">Esperienze condivise</span><span class="sxs-lookup"><span data-stu-id="35bdb-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="35bdb-196">Audio <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="35bdb-197">Audio > volume dell'app e preferenza del dispositivo <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="35bdb-198">Gestione > audio <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="35bdb-199">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="35bdb-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="35bdb-200">Storage > Configue Sensore memoria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-200">Storage > Configue Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="35bdb-201">Lingua & ora</span><span class="sxs-lookup"><span data-stu-id="35bdb-201">Time & Language</span></span>
| <span data-ttu-id="35bdb-202">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-202">Settings page</span></span> | <span data-ttu-id="35bdb-203">URI</span><span class="sxs-lookup"><span data-stu-id="35bdb-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="35bdb-204">Data & <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="35bdb-205">Tastiera <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="35bdb-206">Lingua <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="35bdb-207">Lingua <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="35bdb-208">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="35bdb-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="35bdb-209">Region</span><span class="sxs-lookup"><span data-stu-id="35bdb-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="35bdb-210">Aggiornare & sicurezza</span><span class="sxs-lookup"><span data-stu-id="35bdb-210">Update & Security</span></span>
| <span data-ttu-id="35bdb-211">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="35bdb-211">Settings page</span></span>                         | <span data-ttu-id="35bdb-212">URI</span><span class="sxs-lookup"><span data-stu-id="35bdb-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="35bdb-213">Opzioni avanzate</span><span class="sxs-lookup"><span data-stu-id="35bdb-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="35bdb-214">Ripristino & ripristino <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="35bdb-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="35bdb-215">Programma Windows Insider</span><span class="sxs-lookup"><span data-stu-id="35bdb-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="35bdb-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="35bdb-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="35bdb-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="35bdb-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="35bdb-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="35bdb-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="35bdb-219">Windows Update - Verifica la disponibilità di aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="35bdb-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


>  <span data-ttu-id="35bdb-220"><sup>1</sup> Per le versioni precedenti a Windows Holographic, versione 21H1, i  due URI **seguenti** non visualizzano effettivamente le pagine Opzioni avanzate. bloccano o visualizzano solo la pagina Windows Update principale.</span><span class="sxs-lookup"><span data-stu-id="35bdb-220"><sup>1</sup> For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="35bdb-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="35bdb-221">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="35bdb-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="35bdb-222">ms-settings:windowsupdate-restartoptions</span></span>
 
> <span data-ttu-id="35bdb-223"><sup>2</sup> - Disponibile in Windows Holographic 21H1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="35bdb-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="35bdb-224">Per un elenco completo degli URI Windows 10 impostazioni, vedere la documentazione [relativa alle impostazioni di](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) avvio.</span><span class="sxs-lookup"><span data-stu-id="35bdb-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
