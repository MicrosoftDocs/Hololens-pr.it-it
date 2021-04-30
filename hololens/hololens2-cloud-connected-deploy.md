---
title: Guida alla distribuzione - Distribuzione HoloLens 2 cloud su larga scala con Remote Assist - Distribuire
description: Informazioni su come convalidare la registrazione e Remote Assist per i dispositivi HoloLens tramite una rete connessa al cloud.
keywords: HoloLens, gestione, connessa al cloud, Remote Assist, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309793"
---
# <a name="deploy---cloud-connected-guide"></a>Distribuire - Guida connessa al cloud

Ora che sono stati configurati tutti gli elementi, è necessario essere pronti per distribuire i dispositivi. Tuttavia, a questo punto è necessario convalidare per la prima volta la configurazione. È prima Azure AD convalidare il processo di aggiunta e registrazione MDM, quindi verificare che sia possibile Remote Assist chiamata.

## <a name="enrollment-validation"></a>Convalida della registrazione

Ora che tutto è configurato correttamente per Azure AD e la registrazione MDM, il resto dovrebbe essere uno snap. È&#39;una connessione Wi-Fi e il dispositivo HoloLens, nonché uno degli account utente AAD configurati in precedenza.

Se il dispositivo&#39;non è attualmente in uno stato delle impostazioni predefinite, è possibile eseguire il [reflash del dispositivo.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Una volta che il dispositivo è in Configurazione&#39;, è necessario iniziare a interagire e a seguire le richieste. 
1. La richiesta critica verrà visualizzata quando viene chiesto **chi è il proprietario di questo HoloLens?** Selezionare **L'account aziendale o dell'istituto di** istruzione è proprietario e immettere le credenziali Azure AD'account.
1. Quando la registrazione ha esito positivo,&#39;verrà richiesto di configurare un PIN. Questo PIN è univoco per questo dispositivo per questo utente. Verranno inoltre richieste le analisi Iris, i dati vocali e le impostazioni di telemetria e, infine,&#39;sarà possibile imparare ad aprire il menu Start e completare la configurazione guidata.
1. Dopo aver atterrato nella home page di realtà mista, aprire il menu Start usando il **movimento Start** appena appreso.
1. Selezionare **l'app** Impostazioni e quindi **Sistema.** La prima informazione che verrà&#39;è il nome del dispositivo, che per il dispositivo HoloLens 2 sarà &quot; HOLOLENS, seguito da una stringa di sei &quot; caratteri.
1. Prendere nota di questo nome.

![HoloLens 2 impostazioni - Informazioni](./images/hololens2-settings-about.jpg)

7. È possibile verificare che il dispositivo sia registrato correttamente nel Azure AD all'interno dell'app Impostazioni. In **Impostazioni selezionare Account** **Accedi**  ->  **all'attività o all'istituto di istruzione.** Da questa schermata è possibile verificare che la registrazione sia stata eseguita correttamente. Vedere Connected &quot; to _nameofAAD_&#39;'s Azure AD (Connesso a nameofAAD Azure AD). Connesso tramite _nomeutentenomeAAD_ @ .onmicrosoft.com &quot; .


Per verificare che il dispositivo Azure AD aggiunto, è possibile [](https://portal.azure.com/#home)controllare il Azure Active Directory dal portale di Azure Azure Active Directory Tutti i dispositivi e cercare il nome  ->    ->    ->  del dispositivo. Sarà&#39;possibile vedere che il dispositivo fa parte del Azure Active Directory.


![Azure Active Directory - Dispositivo](./images/aad-enrollment.png)

Successivamente,&#39;necessario accedere all'interfaccia di [amministrazione di Microsoft Endpoint Manager.](https://endpoint.microsoft.com/#home) Accedere e selezionare Dispositivi **e** quindi **Tutti i dispositivi.** Da qui è possibile cercare il nome del&#39;HoloLens. Dovrebbe essere possibile visualizzare l'elenco di HoloLens in Intune.

![Intune - Dispositivo](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist di chiamata

Dopo aver&#39;verificato che il dispositivo sia registrato sia in AAD che in MDM, è necessario&#39;eseguire un test Remote Assist chiamata. Per questa convalida&#39;necessario avere il dispositivo HoloLens e un PC Windows 10, nonché un secondo account utente Azure AD per il PC.

Questo passaggio di convalida presuppone che l'utente abbia completato in precedenza l'ultimo passaggio di convalida e che il dispositivo sia registrato e che Azure AD'utente sia nel dispositivo.


1. Se Microsoft Teams non è già installato nel PC, è possibile [scaricare Teams qui.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Accedere a Teams usando il secondo account Azure AD account utente rispetto a quello attualmente connesso a HoloLens. Dopo aver eseguito l'accesso al PC, si sarà pronti per ricevere la chiamata.
3. Sbloccare HoloLens e accedere.
4. Per avviare l'app Remote Assist aprire il **menu Start** e **selezionare Remote Assist**. Remote Assist non viene solo in bundle come app di posta in arrivo, ma è stato aggiunto HoloLens 2&#39;menu Start. In un caso in cui&#39;non viene aggiunto al menu Start, aprire l'elenco Tutte le **app** per cercarlo.
5. Dopo Remote Assist l'avvio, deve identificare l'utente del dispositivo tramite [l'accesso SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) e accedere all'app.
6. Nell'app selezionare **Cerca** e cercare il secondo utente nel PC. Selezionare l'utente per avviare la chiamata.
7. Dal PC rispondere alla chiamata.

Si è&#39;la connessione e si è connessi alla chiamata di assistenza remota. Assicurarsi di provare specifiche funzionalità di Assistenza remota, ad esempio l'uso di:

- [Annotazioni input penna](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Condividere un file e visualizzarlo in realtà mista](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Ottenere assistenza in un'altra app HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud - Manutenzione](hololens2-cloud-connected-maintain.md)