---
title: HoloLens informazioni di riferimento sulla modalità tutto schermo
description: Informazioni ed esempi per chioschi in modalità tutto schermo HoloLens dispositivi.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032568"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Informazioni di riferimento sulla modalità tutto schermo

Questa pagina contiene informazioni utili per configurare la modalità tutto schermo HoloLens dispositivo. Questi riferimenti includono gli AUMID per le app della posta in arrivo e l'individuazione delle app e diversi esempi XML per la modalità tutto schermo, che sono solo alcune modifiche che non sono pronte per l'uso per diversi scenari. Per informazioni sulla configurazione di un chiosco multimediale, leggere [la pagina Configurare un chiosco multimediale.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens ID modello utente applicazione (AUMID)  

Per informazioni generali su come scegliere le app in modalità tutto schermo, vedere Linee guida per la scelta di [un'app per l'accesso assegnato (modalità tutto schermo).](/windows/configuration/guidelines-for-assigned-access-app)

Se si usa un sistema di gestione dei dispositivi mobili (MDM) o un pacchetto di provisioning per configurare la modalità tutto schermo, usare il provider di servizi di configurazione [AssignedAccess (CSP)](/windows/client-management/mdm/assignedaccess-csp) per specificare le applicazioni. Il provider di servizi di configurazione usa gli ID modello utente [dell'applicazione (AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) per identificare le applicazioni. La tabella seguente elenca gli AUMID di alcune applicazioni in-box che è possibile usare in un chiosco multimediale multi-app.

<a id="aumids"></a>

|Nome dell'app |AUMID |
| --- | --- |
|Visualizzatore 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendario |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Fotocamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Selezione dispositivi in HoloLens (prima generazione) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Selezione dispositivi in HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DispositiviFlowHost |
|Guide di Dynamics 365 |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Hub di &nbsp; feedback |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Esplora file |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Posta |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Dati Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|Nuovo Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> | &nbsp; |
|Film e TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |Microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Foto |Microsoft. Windows. \_Foto App 8wekyb3d8bbwe \! |
|Dati Impostazioni |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nuovo Impostazioni |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Suggerimenti |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Per abilitare l'acquisizione di foto o video, è necessario abilitare l'app Fotocamera come app tutto schermo.  
> <sup>2</sup> Quando si abilita l'app Fotocamera, tenere presenti le condizioni seguenti:
> - Il menu Azioni rapide include i pulsanti Foto e Video.
> - È anche necessario abilitare un'app (ad esempio Foto, Mail o OneDrive) in grado di interagire con o recuperare immagini.  
>  
> <sup>3</sup> Anche se non si abilita l'Cortana come app in modalità tutto schermo, vengono abilitati i comandi vocali predefiniti. Tuttavia, i comandi correlati alle funzionalità disabilitate non hanno alcun effetto.  
> <sup>4</sup> Non è possibile abilitare Miracast direttamente. Per abilitare Miracast come app tutto schermo, abilitare l'app Fotocamera e l'app Selezione dispositivi.

Inoltre, la home page di realtà mista non può essere impostata come app in modalità tutto schermo.

Tornare agli scenari [supportati per la modalità tutto schermo in base al tipo di identità](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Esempi di codice XML in modalità tutto schermo

1. [Profilo di accesso assegnato globale a più app](#multiple-app-global-assigned-access-profile)
1. [Profilo di accesso assegnato globale a più app, esclusi i proprietari dei dispositivi](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Profilo di accesso assegnato da più app per un account locale o un account utente AAD](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Più profili di accesso assegnati all'app per due o più utenti di AAD](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Profilo di accesso assegnato da più app per un gruppo di AAD](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Profilo di accesso assegnato da più app per due o più gruppi di AAD](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Profilo di accesso assegnato da più app per un account AAD e un gruppo di AAD](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Profilo di accesso assegnato da più app per i visitatori](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Sostituire le azioni TODO in base alle esigenze.

### <a name="multiple-app-global-assigned-access-profile"></a>Profilo di accesso assegnato globale a più app

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Torna all'elenco](#kiosk-xml-code-samples) <br>
Tornare agli scenari [supportati per la modalità tutto schermo in base al tipo di identità](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Profilo di accesso assegnato globale a più app, esclusi i proprietari dei dispositivi

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Torna all'elenco](#kiosk-xml-code-samples) <br>
Tornare agli scenari [supportati per la modalità tutto schermo in base al tipo di identità](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Profilo di accesso assegnato da più app per un account locale o un account utente AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Torna all'elenco](#kiosk-xml-code-samples) <br>
Tornare agli scenari [supportati per la modalità tutto schermo in base al tipo di identità](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Più profili di accesso assegnati all'app per due o più utenti di AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Torna all'elenco](#kiosk-xml-code-samples) <br>
Tornare agli scenari [supportati per la modalità tutto schermo in base al tipo di identità](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Profilo di accesso assegnato da più app per un gruppo di AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Torna all'elenco](#kiosk-xml-code-samples) <br>
Tornare agli scenari [supportati per la modalità tutto schermo in base al tipo di identità](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Profilo di accesso assegnato da più app per due o più gruppi di AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Torna all'elenco](#kiosk-xml-code-samples) <br>
Tornare agli scenari [supportati per la modalità tutto schermo in base al tipo di identità](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Profilo di accesso assegnato da più app per un account AAD e un gruppo di AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Torna all'elenco](#kiosk-xml-code-samples) <br>
Tornare agli scenari [supportati per la modalità tutto schermo in base al tipo di identità](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Profilo di accesso assegnato da più app per i visitatori

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Torna all'elenco](#kiosk-xml-code-samples) <br>
Tornare agli scenari [supportati per la modalità tutto schermo in base al tipo di identità](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
