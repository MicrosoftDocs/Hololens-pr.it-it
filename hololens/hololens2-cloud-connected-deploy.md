---
title: Guida alla distribuzione-cloud connected HoloLens 2 distribuzione in scala con assistenza remota-distribuzione
description: Come convalidare la registrazione e l'assistenza remota per i dispositivi HoloLens su una rete connessa al cloud
keywords: HoloLens, gestione, cloud connected, Remote Assist, AAD, Azure AD, MDM, gestione di dispositivi mobili
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
ms.openlocfilehash: 4f4f787d6db16655d5fe3b54438a4524bc9df78f
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196329"
---
# Distribuire-guida connessa al cloud

Ora che hai configurato tutto, dovresti essere pronto per distribuire i dispositivi. Tuttavia, questo è il momento in cui devi prima convalidare la configurazione. Prima di tutto, è necessario convalidare il processo di registrazione di AAD join e MDM, quindi verificare che sia possibile inserire una chiamata di assistenza remota.

## Convalida della registrazione

Con tutto ciò che è stato configurato correttamente per la registrazione di AAD e MDM dovrebbe ora essere un aggancio. È&#39;necessario disporre di una connessione Wi-Fi e del dispositivo HoloLens, nonché di uno degli account utente AAD precedentemente configurati.

Se il dispositivo non è&#39;t attualmente seduto in uno stato delle impostazioni di fabbrica, ora sarebbe un buon momento per [reflashare il dispositivo](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Quando il dispositivo è in configurazione guidata, è&#39;necessario avviare l'interazione e seguire le istruzioni. 
1. Il prompt critico sarà quando viene chiesto a **chi appartiene questo HoloLens?** Selezionare il **mio lavoro o l'Istituto di istruzione proprietario** e immettere le credenziali dell'account AAD.
1. Quando l'iscrizione viene completata correttamente, è&#39;verrà richiesto di configurare un PIN. Questa operazione è univoca per questo dispositivo per l'utente. Verrà richiesto anche l'analisi di Iris, i dati vocali e le impostazioni di telemetria e infine&#39;sarà possibile imparare ad aprire il menu Start e a completare la configurazione guidata.
1. Una volta atterrato nella Home realtà mista, aprire il menu Start con il **gesto iniziale** appena appreso. 
1. Selezionare l'app **Impostazioni** e selezionare **sistema.** La prima informazione che&#39;vedrai è il nome del dispositivo, che per il dispositivo HoloLens 2 verrà &quot; HoloLens &quot; seguito da una stringa di 6 caratteri. 
1. Prendere nota di questo nome.

![HoloLens 2 Impostazioni-informazioni](./images/hololens2-settings-about.jpg)

7. Puoi verificare che il dispositivo sia stato registrato correttamente nel AAD nell'app Impostazioni. In **Impostazioni** selezionare **account**  ->  **o scuola**. Da questa schermata puoi verificare che l'utente sia stato registrato correttamente tramite la visualizzazione &quot; connessa a _nameofAAD_&#39;s Azure ad. Connesso da _nomeutente_ @ _nameofAAD_. onmicrosoft.com &quot; .

Per convalidare il dispositivo, è possibile controllare l'Azure Active Directory da tutti i dispositivi di Azure [Portal](https://portal.azure.com/#home)  ->  **Azure Active Directory**  ->  **Devices**  ->  **All devices** e cercare il nome del dispositivo. Si&#39;sarà in grado di vedere il dispositivo fa parte di Azure Active Directory.

![Azure Active Directory-Device](./images/aad-enrollment.png)

Dopo&#39;sarà necessario accedere all'interfaccia di [amministrazione di Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Accedere e selezionare **dispositivi** e quindi **tutti i dispositivi**. Da qui puoi cercare il nome del dispositivo HoloLens&#39;s. Dovresti essere in grado di vedere il tuo HoloLens elencato in Intune.

![Intune-Device](./images/endpoint-all-devices-enrolled.png)

## Convalida chiamata assistita remota

Dopo aver&#39;verificato che il dispositivo sia registrato sia in AAD che in MDM,&#39;tempo di effettuare una chiamata di assistenza remota di test. Per questa convalida&#39;sarà necessario avere il dispositivo HoloLens e un PC Windows 10, oltre a un secondo account utente AAD per il PC.

Questo passaggio di convalida presuppone che in precedenza sia stato completato l'ultima fase di convalida e che il dispositivo sia registrato e che l'utente AAD si trovi nel dispositivo.

1. Se Don&#39;t ha già installato Microsoft Teams nel PC, è possibile [scaricare teams qui](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. Accedere a teams usando il secondo account utente AAD di quello attualmente connesso a HoloLens. Dopo aver effettuato l'accesso al PC, sarai pronto per ricevere la chiamata.
3. Sbloccare il HoloLens e accedere.
4. Per avviare l'app assistenza remota, aprire il **menu Start** e selezionare **assistenza remota**. L'assistenza remota non è solo inclusa nell'app posta in arrivo, ma è stata aggiunta al menu Start di HoloLens 2&#39;s. In un caso in cui Don&#39;t viene visualizzato nel menu Start, Apri l'elenco **tutte le app** per cercarlo.
5. Una volta avviata l'assistenza remota, dovrebbe identificare l'utente del dispositivo tramite [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) e accedere all'app.
6. Dall'interno dell'app selezionare **Cerca** e cercare il secondo utente nel PC. Selezionare l'utente per avviare la chiamata.
7. Dal PC rispondere alla chiamata.

Congratulazioni, si&#39;collegato correttamente e si è in assistenza telefonica remota. Assicurarsi di provare specifiche funzionalità di assistenza remota, ad esempio usando:

- [Annotazioni in input penna](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Condividere un file e visualizzarlo in una realtà mista](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Ottenere assistenza in un'altra app HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud-manutenzione](hololens2-cloud-connected-maintain.md)