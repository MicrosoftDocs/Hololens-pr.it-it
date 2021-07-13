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
ms.openlocfilehash: 454d79e8b719feb73d5a39280794dcd76f134952
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639234"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="09d3f-104">Visibilità Impostazioni pagina</span><span class="sxs-lookup"><span data-stu-id="09d3f-104">Page Settings Visibility</span></span>

<span data-ttu-id="09d3f-105">Una delle funzionalità gestibili per i dispositivi HoloLens usa i criteri [Impostazioni/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visibili all'interno dell'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="09d3f-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="09d3f-106">PageVisibilityList è un criterio che consente agli amministratori IT di impedire che pagine specifiche nell'app System Impostazioni siano visibili o accessibili oppure di eseguire questa operazione per tutte le pagine ad eccezione di quelle specificate.</span><span class="sxs-lookup"><span data-stu-id="09d3f-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="09d3f-107">Questa funzionalità è disponibile solo in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o successiva per HoloLens 2 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="09d3f-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="09d3f-108">Assicurarsi che i dispositivi per cui si intende usarlo siano aggiornati.</span><span class="sxs-lookup"><span data-stu-id="09d3f-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="09d3f-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="09d3f-109">Examples</span></span>
<span data-ttu-id="09d3f-110">Le pagine sono identificate da una versione abbreviata degli URI pubblicati, ovvero l'URI meno il prefisso "ms-settings:".</span><span class="sxs-lookup"><span data-stu-id="09d3f-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="09d3f-111">L'esempio seguente illustra un criterio che consente l'accesso solo alle pagine About e Bluetooth, che hanno rispettivamente l'URI "network-wifi" e "bluetooth":</span><span class="sxs-lookup"><span data-stu-id="09d3f-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="09d3f-112">L'esempio seguente illustra un criterio che nasconde la pagina Reimpostazione sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="09d3f-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="09d3f-113">Distribuzione di questi criteri tramite Intune</span><span class="sxs-lookup"><span data-stu-id="09d3f-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="09d3f-114">Questi sono i valori di configurazione che verranno forniti a Intune:</span><span class="sxs-lookup"><span data-stu-id="09d3f-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="09d3f-115">**Nome:** Nome visualizzato preferito dall'amministratore per il profilo.</span><span class="sxs-lookup"><span data-stu-id="09d3f-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="09d3f-116">**URI OMA:** URI completo della pagina di impostazione, incluso il relativo [ambito](/windows/client-management/mdm/policy-configuration-service-provider).</span><span class="sxs-lookup"><span data-stu-id="09d3f-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="09d3f-117">In questi esempi in questa pagina viene utilizzato `./Device` l'ambito .</span><span class="sxs-lookup"><span data-stu-id="09d3f-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="09d3f-118">**Valore:** Valore stringa che indica se nascondere o visualizzare *solo* le pagine specificate.</span><span class="sxs-lookup"><span data-stu-id="09d3f-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="09d3f-119">I valori possibili sono `hide:<pagename>` e `showonly:<pagename>`.</span><span class="sxs-lookup"><span data-stu-id="09d3f-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="09d3f-120">È possibile specificare più pagine separandole con un punto e virgola. Di seguito è riportato un elenco di pagine comuni.</span><span class="sxs-lookup"><span data-stu-id="09d3f-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="09d3f-121">Creare un **criterio personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="09d3f-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="09d3f-122">Quando si imposta **OMA-URI,** immettere l'URI con ambito completo.</span><span class="sxs-lookup"><span data-stu-id="09d3f-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="09d3f-123">Per esempio: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="09d3f-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="09d3f-124">Quando si seleziona la selezione dati, scegliere: **Stringa**</span><span class="sxs-lookup"><span data-stu-id="09d3f-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="09d3f-125">Quando si specifica **Valore,** usare le indicazioni riportate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="09d3f-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="09d3f-126">Ad esempio: **`showonly:network-wifi;network-proxy;bluetooth`** o **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="09d3f-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="09d3f-127">Assicurarsi di assegnare la configurazione del dispositivo personalizzata a un gruppo in cui deve essere presente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="09d3f-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="09d3f-128">Se questo passaggio non viene eseguito, verrà eseguito il push dei criteri, ma non verrà applicato.</span><span class="sxs-lookup"><span data-stu-id="09d3f-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="09d3f-129">Vedere [HoloLens MDM per](hololens-mdm-configure.md) altre informazioni sui gruppi di Intune e sulle configurazioni dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="09d3f-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="09d3f-130">Distribuzione di questo criterio tramite un pacchetto di provisioning</span><span class="sxs-lookup"><span data-stu-id="09d3f-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="09d3f-131">Questi sono i valori di configurazione che verranno specificati in Progettazione Windows configurazione:</span><span class="sxs-lookup"><span data-stu-id="09d3f-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="09d3f-132">**Valore:** Valore stringa che indica se nascondere o visualizzare *solo* le pagine specificate.</span><span class="sxs-lookup"><span data-stu-id="09d3f-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="09d3f-133">I valori possibili sono `hide:<pagename>` e `showonly:<pagename>`.</span><span class="sxs-lookup"><span data-stu-id="09d3f-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="09d3f-134">È possibile specificare più pagine separandole con un punto e virgola. Di seguito è riportato un elenco di pagine comuni.</span><span class="sxs-lookup"><span data-stu-id="09d3f-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="09d3f-135">Durante la creazione del pacchetto in Progettazione Windows configurazione passare **a Criteri > Impostazioni > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="09d3f-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="09d3f-136">Immettere la stringa: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="09d3f-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="09d3f-137">Esportare il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="09d3f-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="09d3f-138">Applicare il pacchetto al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="09d3f-138">Apply the package to your device.</span></span>
<span data-ttu-id="09d3f-139">Per informazioni dettagliate su come creare e applicare un pacchetto di provisioning, visitare la [pagina HoloLens provisioning .](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="09d3f-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="09d3f-140">Indipendentemente dal metodo scelto, il dispositivo dovrebbe ora ricevere le modifiche e agli utenti verrà visualizzata la seguente Impostazioni app.</span><span class="sxs-lookup"><span data-stu-id="09d3f-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Screenshot delle ore attive modificate nell'app Impostazioni lavoro](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="09d3f-142">Per configurare le Impostazioni dell'app per mostrare o nascondere la propria selezione di pagine, esaminare gli URI Impostazioni disponibili in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="09d3f-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="09d3f-143">Impostazioni Uri</span><span class="sxs-lookup"><span data-stu-id="09d3f-143">Settings URIs</span></span>

<span data-ttu-id="09d3f-144">HoloLens dispositivi e Windows 10 hanno una selezione diversa di pagine all'interno dell Impostazioni app.</span><span class="sxs-lookup"><span data-stu-id="09d3f-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="09d3f-145">In questa pagina sono disponibili solo le impostazioni esistenti in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="09d3f-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="09d3f-146">Account</span><span class="sxs-lookup"><span data-stu-id="09d3f-146">Accounts</span></span>
| <span data-ttu-id="09d3f-147">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="09d3f-147">Settings page</span></span>           | <span data-ttu-id="09d3f-148">URI</span><span class="sxs-lookup"><span data-stu-id="09d3f-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="09d3f-149">Accedi all'azienda o all'istituto di istruzione</span><span class="sxs-lookup"><span data-stu-id="09d3f-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="09d3f-150">Registrazione Iris</span><span class="sxs-lookup"><span data-stu-id="09d3f-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="09d3f-151">Opzioni di accesso</span><span class="sxs-lookup"><span data-stu-id="09d3f-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="09d3f-152">App</span><span class="sxs-lookup"><span data-stu-id="09d3f-152">Apps</span></span>
| <span data-ttu-id="09d3f-153">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="09d3f-153">Settings page</span></span> | <span data-ttu-id="09d3f-154">URI</span><span class="sxs-lookup"><span data-stu-id="09d3f-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="09d3f-155">App & funzionalità <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="09d3f-156">Funzionalità & app > Opzioni avanzate <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="09d3f-157">App & funzionalità > offline Mappe <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="09d3f-158">App & funzionalità > offline Mappe > download mappe <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="09d3f-159">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="09d3f-159">Devices</span></span>
| <span data-ttu-id="09d3f-160">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="09d3f-160">Settings page</span></span> | <span data-ttu-id="09d3f-161">URI</span><span class="sxs-lookup"><span data-stu-id="09d3f-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="09d3f-162">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="09d3f-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="09d3f-163">Mouse <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="09d3f-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="09d3f-165">Privacy</span><span class="sxs-lookup"><span data-stu-id="09d3f-165">Privacy</span></span>
| <span data-ttu-id="09d3f-166">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="09d3f-166">Settings page</span></span>            | <span data-ttu-id="09d3f-167">URI</span><span class="sxs-lookup"><span data-stu-id="09d3f-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="09d3f-168">Informazioni sull'account</span><span class="sxs-lookup"><span data-stu-id="09d3f-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="09d3f-169">Diagnostica app</span><span class="sxs-lookup"><span data-stu-id="09d3f-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="09d3f-170">App in background</span><span class="sxs-lookup"><span data-stu-id="09d3f-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="09d3f-171">Calendario</span><span class="sxs-lookup"><span data-stu-id="09d3f-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="09d3f-172">Registro chiamate</span><span class="sxs-lookup"><span data-stu-id="09d3f-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="09d3f-173">Fotocamera</span><span class="sxs-lookup"><span data-stu-id="09d3f-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="09d3f-174">Contatti</span><span class="sxs-lookup"><span data-stu-id="09d3f-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="09d3f-175">Commenti e suggerimenti & diagnostica</span><span class="sxs-lookup"><span data-stu-id="09d3f-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="09d3f-176">Documenti</span><span class="sxs-lookup"><span data-stu-id="09d3f-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="09d3f-177">E-mail</span><span class="sxs-lookup"><span data-stu-id="09d3f-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="09d3f-178">File system</span><span class="sxs-lookup"><span data-stu-id="09d3f-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="09d3f-179">Generale <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="09d3f-180">Personalizzazione & input penna <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="09d3f-181">Percorso</span><span class="sxs-lookup"><span data-stu-id="09d3f-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="09d3f-182">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="09d3f-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="09d3f-183">Microfono</span><span class="sxs-lookup"><span data-stu-id="09d3f-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="09d3f-184">Movimento <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="09d3f-185">Notifiche</span><span class="sxs-lookup"><span data-stu-id="09d3f-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="09d3f-186">Altri dispositivi</span><span class="sxs-lookup"><span data-stu-id="09d3f-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="09d3f-187">Immagini</span><span class="sxs-lookup"><span data-stu-id="09d3f-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="09d3f-188">Radio</span><span class="sxs-lookup"><span data-stu-id="09d3f-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="09d3f-189">Bordi dello screenshot <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="09d3f-190">Screenshot e app <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="09d3f-191">Voce</span><span class="sxs-lookup"><span data-stu-id="09d3f-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="09d3f-192">Attività</span><span class="sxs-lookup"><span data-stu-id="09d3f-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="09d3f-193">Movimenti dell'utente</span><span class="sxs-lookup"><span data-stu-id="09d3f-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="09d3f-194">Video</span><span class="sxs-lookup"><span data-stu-id="09d3f-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="09d3f-195">Attivazione vocale</span><span class="sxs-lookup"><span data-stu-id="09d3f-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="09d3f-196">Rete e Internet</span><span class="sxs-lookup"><span data-stu-id="09d3f-196">Network & Internet</span></span>
| <span data-ttu-id="09d3f-197">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="09d3f-197">Settings page</span></span> | <span data-ttu-id="09d3f-198">URI</span><span class="sxs-lookup"><span data-stu-id="09d3f-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="09d3f-199">Modalità aereo <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="09d3f-200">Proxy</span><span class="sxs-lookup"><span data-stu-id="09d3f-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="09d3f-201">Connessione</span><span class="sxs-lookup"><span data-stu-id="09d3f-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="09d3f-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="09d3f-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="09d3f-203">Sistema</span><span class="sxs-lookup"><span data-stu-id="09d3f-203">System</span></span>
| <span data-ttu-id="09d3f-204">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="09d3f-204">Settings page</span></span>      | <span data-ttu-id="09d3f-205">URI</span><span class="sxs-lookup"><span data-stu-id="09d3f-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="09d3f-206">Batteria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="09d3f-207">Batteria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="09d3f-208">Colori</span><span class="sxs-lookup"><span data-stu-id="09d3f-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="09d3f-209">Ologrammi <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="09d3f-210"><sup>Calibrazione 2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="09d3f-211">Notifiche e azioni</span><span class="sxs-lookup"><span data-stu-id="09d3f-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="09d3f-212">Esperienze condivise</span><span class="sxs-lookup"><span data-stu-id="09d3f-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="09d3f-213">Suono <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="09d3f-214">Audio > volume dell'app e preferenza del dispositivo <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="09d3f-215">Gestione > audio <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="09d3f-216">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="09d3f-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="09d3f-217">Archiviazione > configurare Archiviazione Sense <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="09d3f-218">Lingua & ora</span><span class="sxs-lookup"><span data-stu-id="09d3f-218">Time & Language</span></span>
| <span data-ttu-id="09d3f-219">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="09d3f-219">Settings page</span></span> | <span data-ttu-id="09d3f-220">URI</span><span class="sxs-lookup"><span data-stu-id="09d3f-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="09d3f-221">Data &'ora <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="09d3f-222">Tastiera <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="09d3f-223">Lingua <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="09d3f-224">Lingua <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="09d3f-225">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="09d3f-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="09d3f-226">Region</span><span class="sxs-lookup"><span data-stu-id="09d3f-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="09d3f-227">Aggiornare & sicurezza</span><span class="sxs-lookup"><span data-stu-id="09d3f-227">Update & Security</span></span>
| <span data-ttu-id="09d3f-228">Pagina Impostazioni</span><span class="sxs-lookup"><span data-stu-id="09d3f-228">Settings page</span></span>                         | <span data-ttu-id="09d3f-229">URI</span><span class="sxs-lookup"><span data-stu-id="09d3f-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="09d3f-230">Opzioni avanzate</span><span class="sxs-lookup"><span data-stu-id="09d3f-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="09d3f-231">Ripristino & ripristino <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="09d3f-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="09d3f-232">Programma Windows Insider</span><span class="sxs-lookup"><span data-stu-id="09d3f-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="09d3f-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="09d3f-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="09d3f-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="09d3f-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="09d3f-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="09d3f-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="09d3f-236">Windows Update - Controlla la disponibilità di aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="09d3f-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="09d3f-237"><sup>1-</sup> Per le versioni precedenti Windows Holographic, versione 21H1, i due URI  **seguenti** non visualizzano effettivamente le pagine Opzioni avanzate. bloccano o visualizzano solo la pagina principale Windows Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="09d3f-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="09d3f-238">windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="09d3f-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="09d3f-239">windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="09d3f-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="09d3f-240"><sup>2</sup> - Disponibile in Windows Holographic 21H1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="09d3f-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="09d3f-241">Per un elenco completo degli URI Windows 10 Impostazioni, vedere la documentazione [relativa alle impostazioni di](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) avvio.</span><span class="sxs-lookup"><span data-stu-id="09d3f-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
