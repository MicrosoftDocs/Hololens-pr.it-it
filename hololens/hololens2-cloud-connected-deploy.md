---
title: Guida alla distribuzione - Distribuzione di HoloLens 2 connessa al cloud su larga scala con Assistenza remota - Distribuzione
description: Informazioni su come convalidare la registrazione e l'assistenza remota per i dispositivi HoloLens tramite una rete connessa al cloud.
keywords: HoloLens, gestione, connesso al cloud, Assistenza remota, AAD, Azure AD, MDM, Gestione dispositivi mobili
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282937"
---
# Distribuzione - Guida connessa al cloud

Ora che hai configurato tutto, dovresti essere pronto per distribuire i dispositivi. Tuttavia, ora è la prima volta che devi convalidare la configurazione. Prima di tutto, è necessario convalidare il processo di aggiunta ad Azure AD e registrazione MDM, quindi verificare che sia possibile effettuare una chiamata di Assistenza remota.

## Convalida registrazione

Ora che tutto è configurato correttamente per Azure AD e la registrazione MDM, il resto dovrebbe essere uno snap. Dovrai&#39;una connessione Wi-Fi e il dispositivo HoloLens, nonché uno degli account utente AAD configurati in precedenza.

Se il dispositivo non&#39;attualmente in uno stato delle impostazioni predefinite, ora è il momento giusto per riapprociare [il dispositivo.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Una volta che il dispositivo è nella Configurazione&#39;, dovrai iniziare a interagire e a seguire le istruzioni. 
1. Il prompt critico sarà quando ti viene chiesto chi **è il proprietario di questo HoloLens?** Seleziona **Il mio istituto di istruzione o il mio lavoro è proprietario** e immetti le credenziali dell'account Azure AD.
1. Quando la registrazione ha esito positivo,&#39;verrà richiesto di configurare un PIN. Questo PIN è univoco per questo dispositivo per questo utente. Verranno inoltre richieste le analisi dell'iride, i dati vocali e le impostazioni di telemetria e, infine,&#39;sarà possibile imparare ad aprire il menu Start e completare la Configurazione guidata.
1. Una volta che sei atterrato nella Home realtà mista, apri il menu Start usando il gesto **Start** appena appreso.
1. Seleziona **l'app** Impostazioni e seleziona **Sistema.** La prima informazione che vedrai&#39;è il nome del dispositivo, che per il dispositivo HoloLens 2 sarà HOLOLENS seguito da una stringa di sei &quot; &quot; caratteri.
1. Prendere nota di questo nome.

![Impostazioni di HoloLens 2 - Informazioni su](./images/hololens2-settings-about.jpg)

7. Puoi verificare che il dispositivo sia stato registrato correttamente in Azure AD nell'app Impostazioni. In **Impostazioni selezionare** Account Per **accedere**  ->  **all'istituto di istruzione o all'istituto di istruzione.** Da questa schermata è possibile verificare che la registrazione sia stata eseguita correttamente selezionando Connesso a &quot; _nameofAAD_&#39;Azure AD. Connesso tramite _nomeutenteofAAD_ @ __.onmicrosoft.com &quot; .


Per verificare che il dispositivo sia stato aggiunto ad Azure AD, è possibile controllare Azure Active Directory dal portale [di Azure](https://portal.azure.com/#home)Active Directory Dispositivi tutti i dispositivi e cercare  ->  ****  ->  ****  ->  **** il nome del dispositivo. È&#39;possibile vedere che il dispositivo fa parte di Azure Active Directory.


![Azure Active Directory - Dispositivo](./images/aad-enrollment.png)

Successivamente,&#39;necessario accedere all'interfaccia di amministrazione di [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/#home) Accedi e seleziona **Dispositivi e** quindi Tutti **i dispositivi.** Da qui è possibile cercare il dispositivo HoloLens&#39;nome. Dovresti essere in grado di visualizzare holoLens elencato in Intune.

![Intune - Dispositivo](./images/endpoint-all-devices-enrolled.png)

## Convalida delle chiamate di assistenza remota

Dopo aver&#39;che il dispositivo sia registrato sia in AAD che in MDM, è&#39;il momento di eseguire una chiamata di test di Assistenza remota. Per questa convalida&#39;avere il dispositivo HoloLens e un PC Windows 10, nonché un secondo account utente azure AD per il PC.

Questo passaggio di convalida presuppone che tu abbia già completato l'ultimo passaggio di convalida e che il dispositivo sia registrato e che l'utente di Azure AD sia nel dispositivo.


1. Se Microsoft Teams non è già installato nel PC, è possibile [scaricare Teams qui.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Accedere a Teams usando il secondo account utente di Azure AD rispetto a quello attualmente connesso a HoloLens. Dopo aver effettuato l'accesso al PC, potrai ricevere la chiamata.
3. Sblocca HoloLens ed effettua l'accesso.
4. Per avviare l'app Assistenza remota, apri il **menu Start** e seleziona **Assistenza remota.** Remote Assist non è solo fornito come app posta in arrivo, ma è aggiunto al menu Start di HoloLens 2&#39;menu Start. In un caso in cui&#39;non lo vedi aggiunto al menu Start, apri l'elenco Tutte le **app** per cercarlo.
5. Dopo l'avvio di Remote Assist, dovrebbe identificare l'utente del dispositivo tramite [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) ed eseguire l'accesso all'app.
6. Nell'app seleziona **Cerca e** cerca il secondo utente nel PC. Selezionare l'utente per avviare la chiamata.
7. Dal PC, rispondere alla chiamata.

Congratulazioni, la&#39;è stata connessa correttamente ed è in esecuzione la chiamata di assistenza remota. Assicurati di provare specifiche funzionalità di assistenza remota, ad esempio l'uso di:

- [Annotazioni input penna](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Condividere un file e una visualizzazione in realtà mista](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Ottenere assistenza in un'altra app di HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud - Manutenzione](hololens2-cloud-connected-maintain.md)