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
# <span data-ttu-id="55283-104">Visibilità impostazioni pagina</span><span class="sxs-lookup"><span data-stu-id="55283-104">Page Settings Visibility</span></span>

<span data-ttu-id="55283-105">L’uso di [criteri Impostazioni/pageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) per limitare le pagine visualizzate all’interno dell’app, è una delle funzionalità gestibili per i dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55283-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="55283-106">PageVisibilityList è un criterio che consente agli amministratori IT di impedire che pagine specifiche nelle impostazioni di sistema siano visibili o accessibili oppure di farlo per tutte le pagine ad accezioni di quelle specificate.</span><span class="sxs-lookup"><span data-stu-id="55283-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="55283-107">Questa funzionalità è disponibile solo in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) per i dispositivi HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="55283-107">This feature is only avalible in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> <span data-ttu-id="55283-108">Assicurarsi che i dispositivi per cui si intende utilizzarlo siano aggiornati.</span><span class="sxs-lookup"><span data-stu-id="55283-108">Please ensure devices you intend to use this for are updated.</span></span>

> [!NOTE]
> <span data-ttu-id="55283-109">Oltre 20 nuovi SettingsURI verranno aggiunti a breve.</span><span class="sxs-lookup"><span data-stu-id="55283-109">20+ new SettingsURIs are being added soon.</span></span> <span data-ttu-id="55283-110">Visita la [pagina di Windows Insider - Nuovi SettingsURI per la visibilità delle impostazioni della pagina](hololens-insider.md#new-settingsuris-for-page-settings-visibility) se sei interessato ad usare in anteprima questa funzionalità con una build di [HoloLens Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="55283-110">Please view [the Windows Insider page - New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) if you are interesting in previewing this setting on a [HoloLens Insider](hololens-insider.md) build.</span></span>

<span data-ttu-id="55283-111">L'esempio seguente illustra un criterio che consente l'accesso solo alle pagine Informazioni e Bluetooth, che hanno rispettivamente l'URI "ms-settings:network-wifi" e "ms-settings:bluetooth":</span><span class="sxs-lookup"><span data-stu-id="55283-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="55283-112">Per impostare questa impostazione con un pacchetto di provisioning:</span><span class="sxs-lookup"><span data-stu-id="55283-112">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="55283-113">Durante la creazione del pacchetto in Progettazione configurazione di Windows, passa a **Criteri > Impostazioni > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="55283-113">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="55283-114">Immetti la stringa: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="55283-114">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="55283-115">Esporta il pacchetto di provisioning.</span><span class="sxs-lookup"><span data-stu-id="55283-115">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="55283-116">Applica il pacchetto al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="55283-116">Apply the package to your device.</span></span>
<span data-ttu-id="55283-117">Per informazioni dettagliate su come creare e applicare un pacchetto di provisioning, visita [questa pagina.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="55283-117">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="55283-118">Questa operazione può essere eseguita tramite Intune usando OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="55283-118">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="55283-119">Crea un **criterio personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="55283-119">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="55283-120">Quando imposti l'OMA-URI, usa la stringa: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="55283-120">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="55283-121">Quando selezioni i dati, scegli: **stringa**</span><span class="sxs-lookup"><span data-stu-id="55283-121">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="55283-122">Quando inserisci il valore, utilizza: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="55283-122">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="55283-123">Assicurati di assegnare la configurazione di un dispositivo personalizzato a un gruppo all'interno del quale il dispositivo deve essere.</span><span class="sxs-lookup"><span data-stu-id="55283-123">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="55283-124">Per altre informazioni sui gruppi di Intune e sulle configurazioni di dispositivi, vedi [configurazione MDM di HoloLens](hololens-mdm-configure.md).</span><span class="sxs-lookup"><span data-stu-id="55283-124">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="55283-125">Indipendentemente dal metodo scelto, il dispositivo riceverà le modifiche e gli utenti riceveranno l'app Impostazioni seguente.</span><span class="sxs-lookup"><span data-stu-id="55283-125">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Schermata dell'orario di attività che viene modificato nell'app Impostazioni](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="55283-127">Per configurare le pagine dell'app Impostazioni in modo da mostrare o nascondere la tua selezione di pagine, dai un'occhiata agli URI delle impostazioni disponibili in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55283-127">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <span data-ttu-id="55283-128">Impostazioni URI</span><span class="sxs-lookup"><span data-stu-id="55283-128">Settings URIs</span></span>

<span data-ttu-id="55283-129">I dispositivi HoloLens e i dispositivi Windows 10 hanno una selezione delle pagine diversa nell'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="55283-129">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="55283-130">In questa pagina troverai solo le impostazioni presenti in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55283-130">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <span data-ttu-id="55283-131">Account</span><span class="sxs-lookup"><span data-stu-id="55283-131">Accounts</span></span>
| <span data-ttu-id="55283-132">Pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="55283-132">Settings page</span></span>           | <span data-ttu-id="55283-133">URI</span><span class="sxs-lookup"><span data-stu-id="55283-133">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="55283-134">Opzioni di accesso</span><span class="sxs-lookup"><span data-stu-id="55283-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |
| <span data-ttu-id="55283-135">Registrazione Iris</span><span class="sxs-lookup"><span data-stu-id="55283-135">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="55283-136">Accedi all'azienda o all'istituto di istruzione</span><span class="sxs-lookup"><span data-stu-id="55283-136">Access work or school</span></span> | `ms-settings:workplace`                         |

### <span data-ttu-id="55283-137">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="55283-137">Devices</span></span>
| <span data-ttu-id="55283-138">Pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="55283-138">Settings page</span></span> | <span data-ttu-id="55283-139">URI</span><span class="sxs-lookup"><span data-stu-id="55283-139">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="55283-140">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="55283-140">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### <span data-ttu-id="55283-141">Privacy</span><span class="sxs-lookup"><span data-stu-id="55283-141">Privacy</span></span>
| <span data-ttu-id="55283-142">Pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="55283-142">Settings page</span></span>            | <span data-ttu-id="55283-143">URI</span><span class="sxs-lookup"><span data-stu-id="55283-143">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="55283-144">Info account</span><span class="sxs-lookup"><span data-stu-id="55283-144">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="55283-145">Diagnostica app</span><span class="sxs-lookup"><span data-stu-id="55283-145">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="55283-146">App in background</span><span class="sxs-lookup"><span data-stu-id="55283-146">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="55283-147">Movimenti degli utenti</span><span class="sxs-lookup"><span data-stu-id="55283-147">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="55283-148">File system</span><span class="sxs-lookup"><span data-stu-id="55283-148">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="55283-149">Calendario</span><span class="sxs-lookup"><span data-stu-id="55283-149">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="55283-150">Registro chiamate</span><span class="sxs-lookup"><span data-stu-id="55283-150">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="55283-151">Contatti</span><span class="sxs-lookup"><span data-stu-id="55283-151">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="55283-152">Altri dispositivi</span><span class="sxs-lookup"><span data-stu-id="55283-152">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="55283-153">Documenti</span><span class="sxs-lookup"><span data-stu-id="55283-153">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="55283-154">Posta elettronica</span><span class="sxs-lookup"><span data-stu-id="55283-154">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="55283-155">Diagnostica e feedback</span><span class="sxs-lookup"><span data-stu-id="55283-155">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="55283-156">Posizione</span><span class="sxs-lookup"><span data-stu-id="55283-156">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="55283-157">Messaggi</span><span class="sxs-lookup"><span data-stu-id="55283-157">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="55283-158">Microfono</span><span class="sxs-lookup"><span data-stu-id="55283-158">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="55283-159">Notifiche</span><span class="sxs-lookup"><span data-stu-id="55283-159">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="55283-160">Immagini</span><span class="sxs-lookup"><span data-stu-id="55283-160">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="55283-161">Radio</span><span class="sxs-lookup"><span data-stu-id="55283-161">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="55283-162">Comandi vocali</span><span class="sxs-lookup"><span data-stu-id="55283-162">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="55283-163">Attività</span><span class="sxs-lookup"><span data-stu-id="55283-163">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="55283-164">Video</span><span class="sxs-lookup"><span data-stu-id="55283-164">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="55283-165">Attivazione vocale</span><span class="sxs-lookup"><span data-stu-id="55283-165">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |
| <span data-ttu-id="55283-166">Fotocamera</span><span class="sxs-lookup"><span data-stu-id="55283-166">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |

### <span data-ttu-id="55283-167">Rete e internet</span><span class="sxs-lookup"><span data-stu-id="55283-167">Network & Internet</span></span>
| <span data-ttu-id="55283-168">Pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="55283-168">Settings page</span></span> | <span data-ttu-id="55283-169">URI</span><span class="sxs-lookup"><span data-stu-id="55283-169">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="55283-170">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="55283-170">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| <span data-ttu-id="55283-171">VPN</span><span class="sxs-lookup"><span data-stu-id="55283-171">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="55283-172">Proxy</span><span class="sxs-lookup"><span data-stu-id="55283-172">Proxy</span></span> | `ms-settings:network-proxy`        |

### <span data-ttu-id="55283-173">Sistema</span><span class="sxs-lookup"><span data-stu-id="55283-173">System</span></span>
| <span data-ttu-id="55283-174">Pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="55283-174">Settings page</span></span>      | <span data-ttu-id="55283-175">URI</span><span class="sxs-lookup"><span data-stu-id="55283-175">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="55283-176">Esperienze condivise</span><span class="sxs-lookup"><span data-stu-id="55283-176">Shared Experiences</span></span> | `ms-settings:crossdevice`            |
| <span data-ttu-id="55283-177">Colori</span><span class="sxs-lookup"><span data-stu-id="55283-177">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="55283-178">Notifiche e azioni</span><span class="sxs-lookup"><span data-stu-id="55283-178">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="55283-179">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="55283-179">Storage</span></span>            | `ms-settings:storagesense`           |

### <span data-ttu-id="55283-180">Data/ora e lingua</span><span class="sxs-lookup"><span data-stu-id="55283-180">Time & Language</span></span>
| <span data-ttu-id="55283-181">Pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="55283-181">Settings page</span></span> | <span data-ttu-id="55283-182">URI</span><span class="sxs-lookup"><span data-stu-id="55283-182">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="55283-183">Regione</span><span class="sxs-lookup"><span data-stu-id="55283-183">Region</span></span>        | `ms-settings:regionformatting`                  |
| <span data-ttu-id="55283-184">Lingua</span><span class="sxs-lookup"><span data-stu-id="55283-184">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### <span data-ttu-id="55283-185">Aggiornamento e sicurezza</span><span class="sxs-lookup"><span data-stu-id="55283-185">Update & Security</span></span>
| <span data-ttu-id="55283-186">Pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="55283-186">Settings page</span></span>                         | <span data-ttu-id="55283-187">URI</span><span class="sxs-lookup"><span data-stu-id="55283-187">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="55283-188">Programma Windows Insider</span><span class="sxs-lookup"><span data-stu-id="55283-188">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="55283-189">Windows Update</span><span class="sxs-lookup"><span data-stu-id="55283-189">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup><span data-ttu-id="55283-190">1</span><span class="sxs-lookup"><span data-stu-id="55283-190">1</span></span></sup>`ms-settings:windowsupdate-options`<br><sup><span data-ttu-id="55283-191">1</span><span class="sxs-lookup"><span data-stu-id="55283-191">1</span></span></sup>`ms-settings:windowsupdate-restartoptions` |
| <span data-ttu-id="55283-192">Windows Update - Verifica la disponibilità di aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="55283-192">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |
| <span data-ttu-id="55283-193">Opzioni avanzate</span><span class="sxs-lookup"><span data-stu-id="55283-193">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |

>  <sup><span data-ttu-id="55283-194">1 </sup> I due URI seguenti non portano alle **Opzioni Avanzate** o alla pagina **Opzioni**, bloccano/mostrano solo la pagina principale di Windows Update.</span><span class="sxs-lookup"><span data-stu-id="55283-194">1</sup> The following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="55283-195">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="55283-195">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="55283-196">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="55283-196">ms-settings:windowsupdate-restartoptions</span></span> 

<span data-ttu-id="55283-197">Per un elenco completo degli URI delle impostazioni di Windows 10, visitare la documentazione relativa alle [impostazioni di avvio](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).</span><span class="sxs-lookup"><span data-stu-id="55283-197">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
