---
title: Guida alla distribuzione - Distribuzione di applicazioni HoloLens 2 cloud su larga scala con Remote Assist - Distribuire
description: Informazioni su come convalidare la registrazione e Remote Assist per HoloLens dispositivi su una rete connessa al cloud.
keywords: HoloLens, gestione, connessa al cloud, Remote Assist, AAD, Azure AD, MDM, gestione di dispositivi mobili
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189750"
---
# <a name="deploy---cloud-connected-guide"></a>Distribuire - Guida alla connessione al cloud

Ora che sono stati configurati tutti gli elementi, è necessario essere pronti per distribuire i dispositivi. A questo punto, tuttavia, è necessario convalidare per la prima volta la configurazione. È prima Azure AD convalidare il processo di aggiunta e registrazione MDM, quindi verificare che sia Remote Assist possibile effettuare una chiamata.

## <a name="enrollment-validation"></a>Convalida della registrazione

Ora che tutti gli elementi sono configurati correttamente per Azure AD e la registrazione MDM, il resto dovrebbe essere uno snap. Sarà&#39;una connessione Wi-Fi e il dispositivo HoloLens, nonché uno degli account utente AAD configurati in precedenza.

Se il dispositivo non&#39;attualmente in uno stato delle impostazioni predefinite, è il momento giusto per eseguire il [reflash del dispositivo.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Quando il dispositivo è nella Configurazione&#39;, è necessario iniziare a interagire e seguire le istruzioni. 
1. Il prompt critico sarà quando viene chiesto se **Who è proprietario di questa HoloLens?** Selezionare My work or school owns it (L'account aziendale o **dell'istituto** di istruzione è proprietario) e immettere Azure AD credenziali dell'account.
1. Al termine della registrazione,&#39;verrà richiesto di configurare un PIN. Questo PIN è univoco per questo dispositivo per questo utente. Verranno inoltre richieste le analisi Iris, i dati vocali e le impostazioni di telemetria e, infine,&#39;sarà possibile imparare ad aprire il menu Start e completare la Configurazione guidata.
1. Quando si apre la home page di Realtà mista, apri menu Start usando il **movimento Start** appena appreso.
1. Selezionare **l Impostazioni app** e selezionare **Sistema.** La prima informazione che&#39;visualizzare è il nome del dispositivo, che per il dispositivo HoloLens 2 sarà HOLOLENS, seguito da una stringa &quot; &quot; di sei caratteri.
1. Prendere nota di questo nome.

![HoloLens 2 Impostazioni- Informazioni.](./images/hololens2-settings-about.jpg)

7. È possibile verificare che il dispositivo sia registrato correttamente nell'Azure AD all'interno dell Impostazioni app. In  Impostazioni account **Accedere**  ->  **all'account di lavoro o dell'istituto di istruzione.** Da questa schermata è possibile verificare che la registrazione sia stata eseguita correttamente. Vedere Connected &quot; to nameofAAD&#39;'s Azure AD (Connesso a _nameofAAD_ Azure AD). Connesso tramite _nomeutentenomeAAD_ @ .onmicrosoft.com &quot; .


Per verificare che il dispositivo Azure AD aggiunto, è possibile controllare [](https://portal.azure.com/#home)il Azure Active Directory dal portale di Azure Azure Active Directory Tutti i dispositivi e cercare il nome  ->    ->    ->  del dispositivo. È&#39;possibile vedere che il dispositivo fa parte del Azure Active Directory.


![Azure Active Directory - Dispositivo.](./images/aad-enrollment.png)

Successivamente,&#39;necessario accedere all'interfaccia [Microsoft Endpoint Manager di amministrazione.](https://endpoint.microsoft.com/#home) Accedere e selezionare Dispositivi **e** quindi **Tutti i dispositivi.** Da qui è possibile cercare il HoloLens del&#39;nome. Dovrebbe essere possibile visualizzare i dati HoloLens elencati in Intune.

![Intune - Dispositivo.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist di chiamata

Dopo aver&#39;verificato che il dispositivo sia registrato sia in AAD che in MDM, è&#39;il momento di eseguire un test Remote Assist chiamata. Per questa convalida&#39;necessario avere il dispositivo HoloLens e un PC Windows 10, nonché un secondo account utente Azure AD per il PC.

Questo passaggio di convalida presuppone che l'utente abbia completato in precedenza l'ultimo passaggio di convalida e che il dispositivo sia registrato e che Azure AD'utente sia nel dispositivo.


1. Se non è già installato Microsoft Teams nel PC, è possibile scaricare Teams [qui.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Accedere al Teams usando il secondo account utente Azure AD quello attualmente connesso al HoloLens. Dopo aver eseguito l'accesso al PC, sarà possibile ricevere la chiamata.
3. Sbloccare HoloLens e accedere.
4. Per avviare l Remote Assist app, aprire il **menu Start** e selezionare **Remote Assist**. Remote Assist non solo viene in bundle come app di posta in arrivo, ma viene aggiunto al menu HoloLens 2&#39;menu Start. In un caso in cui&#39;non viene aggiunto al menu Start,  aprire l'elenco Tutte le app per cercarlo.
5. Dopo Remote Assist si avvia, dovrebbe identificare l'utente del dispositivo tramite [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) e accedere all'app.
6. Dall'interno dell'app **selezionare Cerca** e cercare il secondo utente nel PC. Selezionare l'utente per avviare la chiamata.
7. Dal PC rispondere alla chiamata.

Congratulazioni, la&#39;è stata connessa correttamente ed è in esecuzione la chiamata di assistenza remota. Assicurarsi di provare specifiche funzionalità di assistenza remota, ad esempio l'uso di:

- [Annotazioni per l'input penna](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Condividere un file e visualizzarlo nella realtà mista](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Ottenere assistenza in un'altra app HoloLens](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud - Manutenzione](hololens2-cloud-connected-maintain.md)