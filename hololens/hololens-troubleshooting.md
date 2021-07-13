---
title: HoloLens Risoluzione dei problemi del dispositivo
description: Rimanere aggiornati sulle soluzioni più comuni per risolvere i problemi dei HoloLens e le tecniche di risoluzione dei problemi.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemi, bug, risoluzione dei problemi, correzione, guida, supporto, HoloLens, emulatore
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635450"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="3f4b9-104">Risoluzione dei problemi del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3f4b9-104">Device Troubleshooting</span></span>

<span data-ttu-id="3f4b9-105">Questo articolo descrive come risolvere diversi problemi HoloLens comuni.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3f4b9-106">Prima di iniziare qualsiasi procedura di risoluzione dei problemi, assicurarsi che il dispositivo venga addebitato al **20-40%** della capacità della batteria, se possibile.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="3f4b9-107">Le [luci indicatore della batteria](hololens2-setup.md#lights-that-indicate-the-battery-level) posizionate sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="3f4b9-108">**Problemi noti**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-108">**Known Issues**</span></span>
- [<span data-ttu-id="3f4b9-109">Remote Assist video si blocca dopo 20 minuti</span><span class="sxs-lookup"><span data-stu-id="3f4b9-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="3f4b9-110">L'accesso automatico richiede l'accesso</span><span class="sxs-lookup"><span data-stu-id="3f4b9-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="3f4b9-111">Microsoft Edge non viene avviato</span><span class="sxs-lookup"><span data-stu-id="3f4b9-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="3f4b9-112">La tastiera non passa ai caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="3f4b9-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="3f4b9-113">Il download dei file bloccati non mostra un errore</span><span class="sxs-lookup"><span data-stu-id="3f4b9-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="3f4b9-114">Portale di dispositivi timeout di caricamento/download di file</span><span class="sxs-lookup"><span data-stu-id="3f4b9-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="3f4b9-115">Schermata blu dopo l'annullamento della registrazione da Insider Preview in un dispositivo flash con una build Insider</span><span class="sxs-lookup"><span data-stu-id="3f4b9-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="3f4b9-116">OneDrive non carica automaticamente le immagini</span><span class="sxs-lookup"><span data-stu-id="3f4b9-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="3f4b9-117">**Generale**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-117">**General**</span></span>
- [<span data-ttu-id="3f4b9-118">HoloLens non risponde o non si avvia</span><span class="sxs-lookup"><span data-stu-id="3f4b9-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="3f4b9-119">Errore "Spazio su disco insufficiente"</span><span class="sxs-lookup"><span data-stu-id="3f4b9-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="3f4b9-120">La calibrazione non riesce</span><span class="sxs-lookup"><span data-stu-id="3f4b9-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="3f4b9-121">Non è possibile accedere perché il HoloLens è stato configurato in precedenza per un altro utente</span><span class="sxs-lookup"><span data-stu-id="3f4b9-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="3f4b9-122">Unity non funziona</span><span class="sxs-lookup"><span data-stu-id="3f4b9-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="3f4b9-123">Windows Portale di dispositivi non funziona correttamente</span><span class="sxs-lookup"><span data-stu-id="3f4b9-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="3f4b9-124">Il HoloLens Emulator non funziona</span><span class="sxs-lookup"><span data-stu-id="3f4b9-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="3f4b9-125">**Input**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-125">**Input**</span></span>
- [<span data-ttu-id="3f4b9-126">I comandi vocali non funzionano</span><span class="sxs-lookup"><span data-stu-id="3f4b9-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="3f4b9-127">L'input manuale non funziona</span><span class="sxs-lookup"><span data-stu-id="3f4b9-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="3f4b9-128">**Connettività**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-128">**Connectivity**</span></span>
- [<span data-ttu-id="3f4b9-129">Non è possibile connettersi al Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3f4b9-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="3f4b9-130">**Dispositivi esterni**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-130">**External Devices**</span></span> 
- [<span data-ttu-id="3f4b9-131">Bluetooth dispositivi non associati</span><span class="sxs-lookup"><span data-stu-id="3f4b9-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="3f4b9-132">Il microfono USB-C non funziona</span><span class="sxs-lookup"><span data-stu-id="3f4b9-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="3f4b9-133">I dispositivi elencati come disponibili Impostazioni non funzionano</span><span class="sxs-lookup"><span data-stu-id="3f4b9-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="3f4b9-134">Remote Assist video si blocca dopo 20 minuti</span><span class="sxs-lookup"><span data-stu-id="3f4b9-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="3f4b9-135">È disponibile una versione più recente di Remote Assist che include una correzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="3f4b9-136">Aggiornare [Remote Assist](holographic-store-apps.md#update-apps) alla versione più recente per evitare questo problema.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="3f4b9-137">A causa della gravità di questo problema noto, è stata temporaneamente sospesa la disponibilità Windows Holographic, versione 21H1.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="3f4b9-138">La build 21H1 è ora nuovamente disponibile, quindi i dispositivi possono essere ancora una volta aggiornati alla build 21H1 più recente.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="3f4b9-139">Nella versione più recente di [Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)alcuni utenti di Remote Assist hanno riscontrato il blocco dei video durante le chiamate per più di 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="3f4b9-140">Si tratta di **un problema noto.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="3f4b9-141">Soluzioni alternative</span><span class="sxs-lookup"><span data-stu-id="3f4b9-141">Workarounds</span></span>

<span data-ttu-id="3f4b9-142">Se non è possibile aggiornare Remote Assist a una build più recente, provare a risolvere il problema seguente.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="3f4b9-143">Riavvio tra le chiamate</span><span class="sxs-lookup"><span data-stu-id="3f4b9-143">Restart in between calls</span></span>

<span data-ttu-id="3f4b9-144">Se le chiamate hanno una durata di 20 minuti e si verifica questo problema, provare a riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="3f4b9-145">Il riavvio del dispositivo tra Remote Assist le chiamate aggiorna il dispositivo e lo riporta a uno stato valido.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="3f4b9-146">Per riavviare rapidamente un dispositivo [Windows Holographic, versione 21H1](hololens-release-notes.md#windows-holographic-version-21h1) aprire il menu Start e selezionare l'icona utente e quindi **selezionare Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="3f4b9-147">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="3f4b9-148">L'accesso automatico richiede l'accesso</span><span class="sxs-lookup"><span data-stu-id="3f4b9-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="3f4b9-149">Un HoloLens 2 può essere configurato per l'accesso automatico tramite **Impostazioni**  ->  **Accounts**  ->  **Sign-in Options** -> e in **Obbligatorio** impostare il valore su Mai .</span><span class="sxs-lookup"><span data-stu-id="3f4b9-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="3f4b9-150">Ad alcuni utenti potrebbe essere richiesto di accedere di nuovo al dispositivo quando si aggiorna un dispositivo con un aggiornamento di grandi dimensioni, ad esempio un aggiornamento delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="3f4b9-151">Si tratta di **un problema noto.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-151">This is a **known issue**.</span></span>

<span data-ttu-id="3f4b9-152">Esempio di quando ciò può verificarsi:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-152">Example of when this could occur:</span></span>

- <span data-ttu-id="3f4b9-153">Aggiornamento di un dispositivo da Windows Holographic versione 2004 (build 19041.xxxx) a Windows Holographic, versione 21H1 (build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="3f4b9-154">Aggiornamento di un dispositivo per eseguire un aggiornamento di grandi dimensioni nella stessa build principale, ad esempio Windows Holographic, versione 2004 a Windows Holographic, versione 20H2</span><span class="sxs-lookup"><span data-stu-id="3f4b9-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="3f4b9-155">Aggiornamento di un dispositivo da un'immagine factory all'immagine più recente</span><span class="sxs-lookup"><span data-stu-id="3f4b9-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="3f4b9-156">Questa operazione non deve verificarsi durante:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-156">This should not occur during:</span></span>

- <span data-ttu-id="3f4b9-157">Dispositivi che ese prendono un aggiornamento di manutenzione mensile</span><span class="sxs-lookup"><span data-stu-id="3f4b9-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="3f4b9-158">Aggirare i metodi:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-158">Work around methods:</span></span>

- <span data-ttu-id="3f4b9-159">Metodi di accesso come PIN, password, Iris, autenticazione Web o chiavi FIDO2.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="3f4b9-160">Se non è possibile ricordare il PIN del dispositivo e non sono disponibili altri metodi di autenticazione, un utente può usare la modalità [reflashing manuale.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="3f4b9-161">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="3f4b9-162">Microsoft Edge non viene avviato</span><span class="sxs-lookup"><span data-stu-id="3f4b9-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="3f4b9-163">Questo problema è stato originariamente creato con la versione di Microsoft Edge in considerazione.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="3f4b9-164">Questo problema può essere risolto nel [nuovo Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="3f4b9-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="3f4b9-165">In caso contrario, inviare commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="3f4b9-166">Alcuni clienti hanno segnalato un problema a causa del quale Microsoft Edge non viene avviato.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="3f4b9-167">Per questi clienti, il problema persiste durante il riavvio e non viene risolto con gli aggiornamenti Windows o dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="3f4b9-168">Se si verifica questo problema e si è verificato che [Windows](hololens-updates.md#manually-check-for-updates)è aggiornato, mettere un bug dall'app [Hub di Feedback](hololens-feedback.md) con la categoria e la sottocatego; Installare e aggiornare > Downloading, installing, and configuring Windows Update (Download, installazione e configurazione di Windows Update).</span><span class="sxs-lookup"><span data-stu-id="3f4b9-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="3f4b9-169">Non sono disponibili soluzioni alternative note perché finora non è stato possibile stabilire la causa radice del problema.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="3f4b9-170">La segnalazione di un bug tramite Hub di Feedback sarà utile per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="3f4b9-171">Si tratta di **un problema noto.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-171">This is a **known issue**.</span></span>

[<span data-ttu-id="3f4b9-172">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="3f4b9-173">La tastiera non passa ai caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="3f4b9-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="3f4b9-174">Si verifica un problema durante la Configurazione fuori rete, in cui dopo che l'utente ha scelto un account aziendale o dell'istituto di istruzione e ha immesso la password, il tentativo di passare ai caratteri speciali sulla tastiera toccando il pulsante &123 non cambia in caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="3f4b9-175">Si tratta di **un problema noto.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-175">This is a **known issue**.</span></span>

<span data-ttu-id="3f4b9-176">Operazioni da risolvere:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-176">Work-arounds:</span></span>
-   <span data-ttu-id="3f4b9-177">Chiudere la tastiera e riaprirla toccando il campo di testo.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="3f4b9-178">Immettere la password in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-178">Incorrectly enter your password.</span></span> <span data-ttu-id="3f4b9-179">Al successivo riavvio, la tastiera funzionerà come previsto.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="3f4b9-180">Autenticazione Web, chiudere la tastiera e selezionare **Accedi da un altro dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="3f4b9-181">Se si immettono solo numeri, un utente può tenere premuti determinati tasti per aprire un menu espanso.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="3f4b9-182">Uso di una tastiera USB.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-182">Using a USB keyboard.</span></span>

<span data-ttu-id="3f4b9-183">Ciò non influisce su:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-183">This does not affect:</span></span>
- <span data-ttu-id="3f4b9-184">Utenti che scelgono di usare un account personale.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="3f4b9-185">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="3f4b9-186">Il download dei file bloccati non ha un errore</span><span class="sxs-lookup"><span data-stu-id="3f4b9-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="3f4b9-187">Si tratta di **un problema** noto risolto in Windows Insider, versione 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="3f4b9-188">Nelle build precedenti di Windows Holographic, quando si tenta di scaricare un file bloccato, il risultato è una pagina di errore HTTP.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="3f4b9-189">Nell'aggiornamento Windows Holographic versione 21H1, il tentativo di scaricare un file bloccato non comporta alcuna operazione visibile: il file non viene scaricato e non si verifica alcun errore.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="3f4b9-190">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="3f4b9-191">Portale di dispositivi timeout di caricamento/download di file</span><span class="sxs-lookup"><span data-stu-id="3f4b9-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="3f4b9-192">Si tratta di **un problema** noto risolto in Windows Insider, versione 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="3f4b9-193">Se in precedenza è stata disabilitata la connessione SSL come parte della soluzione alternativa, è consigliabile abilitarla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="3f4b9-194">Alcuni clienti hanno rilevato che, durante il tentativo di caricare o scaricare file, l'operazione potrebbe sembrare bloccarsi e quindi verificarsi un timeout o non essere mai completata.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="3f4b9-195">Questo problema è separato dal problema noto["file](#downloading-locked-files-doesnt-error) bloccato", che interessa le build di Windows Holographic, versioni 2004, 20H2 e 21H1.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="3f4b9-196">Il problema è stato causato da un bug nella gestione di determinate richieste di Portale di dispositivi ed è stato raggiunto in modo più coerente quando si usa https, che è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="3f4b9-197">Soluzione alternativa</span><span class="sxs-lookup"><span data-stu-id="3f4b9-197">Workaround</span></span>

<span data-ttu-id="3f4b9-198">Questa soluzione alternativa, che si applica ugualmente Wi-Fi e UsbNcm, consiste nel disabilitare l'opzione "obbligatorio" in "Connessione SSL".</span><span class="sxs-lookup"><span data-stu-id="3f4b9-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="3f4b9-199">A tale scopo, passare Portale di dispositivi, **Sistema** e selezionare la **pagina** Preferenze.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="3f4b9-200">Nella sezione **Sicurezza del dispositivo** individuare Connessione SSL **e** deselezionare per disabilitare **Obbligatorio.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="3f4b9-201">L'utente deve quindi passare a http://, non https:// (indirizzo IP) e le funzionalità come il caricamento e il download di file funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="3f4b9-202">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="3f4b9-203">Schermata blu dopo l'annullamento della registrazione da Insider Preview in un dispositivo flash con una build Insider</span><span class="sxs-lookup"><span data-stu-id="3f4b9-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="3f4b9-204">Si tratta di un problema che interessa gli utenti che si trovavano in una build di anteprima Insider, hanno ricompresso il proprio HoloLens 2 con una nuova build Insider Preview e quindi hanno rimosso la registrazione dal programma Insider.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="3f4b9-205">Si tratta di **un problema noto.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-205">This is a **known issue**.</span></span>

<span data-ttu-id="3f4b9-206">Ciò non influisce su:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-206">This does not affect:</span></span>
- <span data-ttu-id="3f4b9-207">Utenti che non sono registrati a Windows Insider</span><span class="sxs-lookup"><span data-stu-id="3f4b9-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="3f4b9-208">Addetti ai lavori:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-208">Insiders:</span></span>
    - <span data-ttu-id="3f4b9-209">Se un dispositivo è stato registrato dopo le build Insider, la versione era 18362.x</span><span class="sxs-lookup"><span data-stu-id="3f4b9-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="3f4b9-210">Se hanno eseguito il flash di una build 19041.x firmata da Insider e rimangono registrati al programma Insider</span><span class="sxs-lookup"><span data-stu-id="3f4b9-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="3f4b9-211">Risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-211">Work-around:</span></span> 
- <span data-ttu-id="3f4b9-212">Evitare il problema</span><span class="sxs-lookup"><span data-stu-id="3f4b9-212">Avoid the issue</span></span> 
    - <span data-ttu-id="3f4b9-213">Eseguire il flash di una build non insider.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-213">Flash a non-insider build.</span></span> <span data-ttu-id="3f4b9-214">Uno degli aggiornamenti mensili regolari.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="3f4b9-215">Rimanere in Insider Preview</span><span class="sxs-lookup"><span data-stu-id="3f4b9-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="3f4b9-216">Reflash del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3f4b9-216">Reflash the device</span></span>

    1. <span data-ttu-id="3f4b9-217">Attivare manualmente [HoloLens 2 flashing](hololens-recovery.md) attivando completamente il sistema mentre non ci si connette.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="3f4b9-218">Quindi, tenendo premuto Volume in alto, toccare il pulsante Di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="3f4b9-219">Connessione al PC e aprire Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="3f4b9-220">Eseguire il flash HoloLens 2 alla compilazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="3f4b9-221">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="3f4b9-222">OneDrive non carica automaticamente le immagini</span><span class="sxs-lookup"><span data-stu-id="3f4b9-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="3f4b9-223">L'app OneDrive per HoloLens non supporta il caricamento automatico della fotocamera per gli account aziendali o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="3f4b9-224">Si tratta di **un problema noto.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-224">This is a **known issue**.</span></span>

<span data-ttu-id="3f4b9-225">Soluzioni alternative:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-225">Workarounds:</span></span>

- <span data-ttu-id="3f4b9-226">Se possibile per l'azienda, il caricamento automatico della fotocamera è supportato per gli account Microsoft consumer.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="3f4b9-227">È possibile accedere al proprio account Microsoft oltre all'account aziendale o dell'istituto di istruzione (l'app OneDrive supporta l'accesso doppio.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="3f4b9-228">Dal profilo account Microsoft all'interno OneDrive è possibile abilitare il caricamento automatico del rullino della fotocamera in background.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="3f4b9-229">Se non è possibile usare in modo sicuro un account Microsoft consumer per caricare automaticamente le foto, è possibile caricare manualmente le foto nell'account aziendale o dell'istituto di istruzione dall'app OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="3f4b9-230">A tale scopo, assicurarsi di aver eseguito l'accesso all'account aziendale o dell'istituto di istruzione nell'app OneDrive lavoro.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="3f4b9-231">Selezionare il **+** pulsante e scegliere **Upload**.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="3f4b9-232">Trovare le foto o i video da caricare passando a **Pictures (Immagini) > Camera Roll (Rullino foto).**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="3f4b9-233">Selezionare le foto o i video da caricare e quindi selezionare il **pulsante** Apri.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="3f4b9-234">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="3f4b9-235">HoloLens non risponde o non si avvia</span><span class="sxs-lookup"><span data-stu-id="3f4b9-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="3f4b9-236">Se il HoloLens non si avvia:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="3f4b9-237">Se i LED accanto al pulsante di alimentazione non si accendere o un solo LED lampeggia brevemente, potrebbe essere necessario caricare il [HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="3f4b9-238">Se i LED si accendeno quando si preme il pulsante di alimentazione, ma non è possibile visualizzare nulla sui display, eseguire [un ripristino azzerato del dispositivo.](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="3f4b9-239">Se il HoloLens viene bloccato o non risponde:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="3f4b9-240">Disattivare il HoloLens premendo il pulsante di alimentazione fino a quando tutti e cinque i LED non si spegnino o per 15 secondi se i LED non rispondono.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="3f4b9-241">Per avviare il HoloLens, premere di nuovo il pulsante di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="3f4b9-242">Se questi passaggi non funzionano, [](hololens-recovery.md) è possibile provare a ripristinare il HoloLens 2 o il HoloLens di prima [generazione.](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="3f4b9-243">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="3f4b9-244">Errore "Spazio su disco insufficiente"</span><span class="sxs-lookup"><span data-stu-id="3f4b9-244">"Low Disk Space" error</span></span>

<span data-ttu-id="3f4b9-245">È necessario liberare spazio di archiviazione eseguendo una o più delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="3f4b9-246">Eliminare alcuni spazi inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-246">Delete some unused spaces.</span></span> <span data-ttu-id="3f4b9-247">Passare a **Impostazioni**  >  **di**  >  **sistema,** selezionare uno spazio non più necessario e quindi selezionare **Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="3f4b9-248">Rimuovere alcuni degli ologrammi posizionati.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="3f4b9-249">Eliminare alcune immagini e video dall'app Foto app.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="3f4b9-250">Disinstallare alcune app dal HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="3f4b9-251">**Nell'elenco Tutte le** app toccare e tenere premuta l'app da disinstallare e quindi selezionare **Disinstalla.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="3f4b9-252">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="3f4b9-253">La calibrazione non riesce</span><span class="sxs-lookup"><span data-stu-id="3f4b9-253">Calibration fails</span></span>

<span data-ttu-id="3f4b9-254">La calibrazione dovrebbe funzionare per la maggior parte delle persone, ma in alcuni casi la calibrazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="3f4b9-255">Di seguito sono riportati alcuni possibili motivi per cui si è verificato un errore di calibrazione:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="3f4b9-256">Distrarsi e non seguire le destinazioni di calibrazione</span><span class="sxs-lookup"><span data-stu-id="3f4b9-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="3f4b9-257">Visore del dispositivo dirty o scratched o visore del dispositivo non posizionato correttamente</span><span class="sxs-lookup"><span data-stu-id="3f4b9-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="3f4b9-258">Occhiali dirty o grattati</span><span class="sxs-lookup"><span data-stu-id="3f4b9-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="3f4b9-259">Alcuni tipi di lenti e occhiali da contatto (lenti a contatto colorate, lenti a contatto torici, occhiali da blocco IR, alcuni occhiali da sole, occhiali da sole o simili)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="3f4b9-260">Forma più pronunciata e alcune estensioni della ciglia</span><span class="sxs-lookup"><span data-stu-id="3f4b9-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="3f4b9-261">Fotogrammi a forma di occhio o di spessore oculare se bloccano la visualizzazione degli occhi da parte del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3f4b9-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="3f4b9-262">Alcune fisiologia oculare, condizioni oculari o problemi oculari, ad esempio occhi ristretti, lunghe ciglia, amblyopia, nystagmus, alcuni casi di LASIK o altri interventi oculari</span><span class="sxs-lookup"><span data-stu-id="3f4b9-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="3f4b9-263">Se la calibrazione non riesce, provare:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="3f4b9-264">Pulizia del visore del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3f4b9-264">Cleaning your device visor</span></span>
- <span data-ttu-id="3f4b9-265">Pulizia degli occhiali</span><span class="sxs-lookup"><span data-stu-id="3f4b9-265">Cleaning your glasses</span></span>
- <span data-ttu-id="3f4b9-266">Push del visore del dispositivo il più vicino possibile agli occhi</span><span class="sxs-lookup"><span data-stu-id="3f4b9-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="3f4b9-267">Spostamento di oggetti nel visore (ad esempio, i capello)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="3f4b9-268">Accensione di una luce nella stanza o uscita dalla camera diretta</span><span class="sxs-lookup"><span data-stu-id="3f4b9-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="3f4b9-269">Se sono seguite tutte le linee guida e la calibrazione ha ancora esito negativo, è possibile disabilitare la richiesta di calibrazione in Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="3f4b9-270">È anche possibile inviare commenti e suggerimenti in [Hub di Feedback](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="3f4b9-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="3f4b9-271">Vedere anche le informazioni correlate per la risoluzione [dei problemi relativi al colore o alla luminosità dell'immagine.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="3f4b9-272">L'impostazione di IPD non è applicabile HoloLens 2, poiché le posizioni degli occhi vengono calcolate dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="3f4b9-273">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="3f4b9-274">Non è possibile accedere perché il HoloLens è stato configurato in precedenza per un altro utente</span><span class="sxs-lookup"><span data-stu-id="3f4b9-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="3f4b9-275">È possibile [impostare il dispositivo in modalità **flashing e** usare Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) per ripristinare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="3f4b9-276">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="3f4b9-277">Unity non funziona</span><span class="sxs-lookup"><span data-stu-id="3f4b9-277">Unity isn't working</span></span>

- <span data-ttu-id="3f4b9-278">Vedere [Installare gli strumenti](/windows/mixed-reality/install-the-tools) per la versione più aggiornata di Unity consigliata per HoloLens sviluppo.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="3f4b9-279">I problemi noti di Unity HoloLens Technical Preview sono documentati nei [forum HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="3f4b9-280">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="3f4b9-281">Windows Portale di dispositivi non funziona correttamente</span><span class="sxs-lookup"><span data-stu-id="3f4b9-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="3f4b9-282">La funzionalità anteprima live nell'acquisizione di realtà mista può presentare diversi secondi di latenza.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="3f4b9-283">Nella pagina Input virtuale i controlli Movimento e Scorrimento nella sezione Movimenti virtuali non sono funzionali.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="3f4b9-284">L'uso di questi strumenti non avrà alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-284">Using them will have no effect.</span></span> <span data-ttu-id="3f4b9-285">La tastiera virtuale nella pagina di input virtuale funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="3f4b9-286">Dopo l'abilitazione della modalità sviluppatore in Impostazioni, l'attivazione dell'Portale di dispositivi potrebbe richiedere alcuni secondi.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="3f4b9-287">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="3f4b9-288">Il HoloLens Emulator non funziona</span><span class="sxs-lookup"><span data-stu-id="3f4b9-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="3f4b9-289">Le informazioni sull'emulatore HoloLens sono disponibili nella documentazione per sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="3f4b9-290">Altre informazioni sulla risoluzione [dei problemi dell'emulatore HoloLens.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="3f4b9-291">Non tutte le app nella Microsoft Store sono compatibili con l'emulatore.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="3f4b9-292">Ad esempio, Young Conker e Fragments non sono riproducibili nell'emulatore.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="3f4b9-293">Non è possibile usare la webcam del PC nel Emulator.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="3f4b9-294">La funzionalità di anteprima live del Windows Portale di dispositivi non funziona con l'emulatore.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="3f4b9-295">È comunque possibile acquisire video e immagini di realtà mista.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="3f4b9-296">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="3f4b9-297">I comandi vocali non funzionano</span><span class="sxs-lookup"><span data-stu-id="3f4b9-297">Voice commands aren't working</span></span>

<span data-ttu-id="3f4b9-298">Se Cortana non risponde ai comandi vocali, assicurarsi che Cortana sia attivata.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="3f4b9-299">Nell'elenco Tutte le app **selezionare** Cortana  >    >  **Menu Notebook**  >  **Impostazioni** apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="3f4b9-300">Per altre informazioni su ciò che è possibile dire, vedere Usare la voce [con HoloLens](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="3f4b9-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="3f4b9-301">Nella HoloLens (prima generazione), il riconoscimento vocale incorporato non è configurabile.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="3f4b9-302">È sempre attivata.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-302">It is always turned on.</span></span> <span data-ttu-id="3f4b9-303">In HoloLens 2 è possibile scegliere se attivare il riconoscimento vocale e il riconoscimento Cortana durante la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="3f4b9-304">Se il HoloLens 2 non risponde alla voce, assicurarsi che il riconoscimento vocale sia attivato.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="3f4b9-305">Passare a **Start**  >  **Impostazioni**  >  **Privacy**  >  **Speech e** attivare Riconoscimento **vocale.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="3f4b9-306">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="3f4b9-307">L'input manuale non funziona</span><span class="sxs-lookup"><span data-stu-id="3f4b9-307">Hand input isn't working</span></span>

<span data-ttu-id="3f4b9-308">Per assicurarsi che HoloLens possano vedere le mani, è necessario mantenerle nel fotogramma del movimento.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="3f4b9-309">La home page di Realtà mista fornisce commenti e suggerimenti che ti consentono di sapere quando vengono tracciate le mani.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="3f4b9-310">Il feedback è diverso nelle diverse versioni di HoloLens:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="3f4b9-311">Nella HoloLens (prima generazione), il cursore sguardo fisso cambia da punto a anello</span><span class="sxs-lookup"><span data-stu-id="3f4b9-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="3f4b9-312">In HoloLens 2 viene visualizzato un cursore punta del dito quando la mano è vicina a uno slate e viene visualizzato un raggio della mano quando gli slate sono più lontani</span><span class="sxs-lookup"><span data-stu-id="3f4b9-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="3f4b9-313">Molte app immersive seguono modelli di input simili alla home page di realtà mista.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="3f4b9-314">Altre informazioni sull'uso dell'input [manuale HoloLens (prima generazione)](hololens1-basic-usage.md#use-hololens-with-your-hands) [e HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span><span class="sxs-lookup"><span data-stu-id="3f4b9-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="3f4b9-315">Se si è in bilito, si noti che alcuni tipi di scarpe non funzionano con il tracciamento delle mani.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="3f4b9-316">Un esempio comune è quello dei 1000 scarpe nere, che tendono ad assalere la luce a indotta e non vengono prelevati dalla fotocamera di profondità.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="3f4b9-317">Se il lavoro prevede un paio di gradazioni, è consigliabile provare un colore più chiaro, ad esempio blu o grigio.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="3f4b9-318">Un altro esempio è l'utilizzo di ampi ovaiosi, che tendono a nascondere la forma della mano.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="3f4b9-319">Per ottenere risultati ottimali, è consigliabile usare i modelli più adattabili possibile.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="3f4b9-320">Se il visore ha impronte digitali o sbavature, usare la pulizia del microfibero fornita con il HoloLens per pulire il visore.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="3f4b9-321">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="3f4b9-322">Non è possibile connettersi a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3f4b9-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="3f4b9-323">Di seguito sono riportati alcuni aspetti da provare se non è possibile connettere il HoloLens a una Wi-Fi rete:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="3f4b9-324">Assicurarsi che la Wi-Fi sia attivata.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="3f4b9-325">Per verificare, usare il movimento Avvia, quindi **selezionare** Impostazioni  >  **Rete &amp; Internet**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="3f4b9-326">Se Wi-Fi è attivata, provare a disattivarla e quindi ad attivarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="3f4b9-327">Spostarsi più vicino al router o al punto di accesso.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="3f4b9-328">Riavviare il router Wi-Fi, quindi [riavviare HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="3f4b9-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="3f4b9-329">Provare a eseguire di nuovo la connessione.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-329">Try connecting again.</span></span>
- <span data-ttu-id="3f4b9-330">Se nessuna di queste operazioni funziona, verificare che il router utilizzi il firmware più recente.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="3f4b9-331">Queste informazioni sono disponibili nel sito Web del produttore.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="3f4b9-332">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="3f4b9-333">Bluetooth dispositivi non associati</span><span class="sxs-lookup"><span data-stu-id="3f4b9-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="3f4b9-334">Se si verificano problemi durante [l'associazione di Bluetooth dispositivo,](hololens-connect-devices.md)provare a eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="3f4b9-335">Passare a **Impostazioni** dispositivi e assicurarsi  >  che l'Bluetooth sia attivata.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="3f4b9-336">In caso contrario, disattivarla e riattivarla.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="3f4b9-337">Assicurarsi che il dispositivo Bluetooth sia completamente caricato o abbia batterie nuove.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="3f4b9-338">Se non è ancora possibile connettersi, [riavviare il HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="3f4b9-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="3f4b9-339">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="3f4b9-340">Il microfono USB-C non funziona</span><span class="sxs-lookup"><span data-stu-id="3f4b9-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="3f4b9-341">Tenere presente che alcuni microfoni USB-C segnalano erroneamente se stessi sia come microfono *che come* altoparlante.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="3f4b9-342">Si tratta di un problema con il microfono e non con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="3f4b9-343">Quando si collega uno di questi microfoni in HoloLens, l'audio potrebbe essere perso.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="3f4b9-344">Fortunatamente è disponibile una semplice correzione.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="3f4b9-345">In **Impostazioni** Sistema audio impostare in modo esplicito gli altoparlanti  ->    ->   **predefiniti (analog Feature Audio Driver)** come **dispositivo predefinito.**</span><span class="sxs-lookup"><span data-stu-id="3f4b9-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="3f4b9-346">HoloLens necessario ricordare questa impostazione anche se il microfono viene rimosso e riconnesso in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Risoluzione dei problemi relativi ai microfoni USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="3f4b9-348">I dispositivi elencati come disponibili Impostazioni non funzionano</span><span class="sxs-lookup"><span data-stu-id="3f4b9-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="3f4b9-349">HoloLens (prima generazione) non supporta l'Bluetooth profili audio.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="3f4b9-350">Bluetooth dispositivi audio, ad esempio altoparlanti e visori VR, possono essere visualizzati come disponibili nelle impostazioni HoloLens, ma non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="3f4b9-351">HoloLens 2 supporta il profilo audio Bluetooth A2DP per la riproduzione stereo.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="3f4b9-352">Il Bluetooth hands free che consente l'acquisizione del microfono da una periferica Bluetooth non è supportata in HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="3f4b9-353">Se si verificano problemi durante l'uso Bluetooth dispositivo, assicurarsi che sia supportato.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="3f4b9-354">I dispositivi supportati includono:</span><span class="sxs-lookup"><span data-stu-id="3f4b9-354">Supported devices include the following:</span></span>

- <span data-ttu-id="3f4b9-355">QWERTY in lingua Bluetooth tastiere (è possibile usarle ovunque si usi la tastiera olografica).</span><span class="sxs-lookup"><span data-stu-id="3f4b9-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="3f4b9-356">Bluetooth mouse.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-356">Bluetooth mice.</span></span>
- <span data-ttu-id="3f4b9-357">Il [HoloLens clicker .](hololens1-clicker.md)</span><span class="sxs-lookup"><span data-stu-id="3f4b9-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="3f4b9-358">È possibile associare altri Bluetooth HID e GATT con l'HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="3f4b9-359">Tuttavia, potrebbe essere necessario installare le app complementari corrispondenti da Microsoft Store per usare effettivamente i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3f4b9-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="3f4b9-360">Torna all'elenco</span><span class="sxs-lookup"><span data-stu-id="3f4b9-360">Back to list</span></span>](#list)
