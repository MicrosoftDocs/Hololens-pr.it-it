---
title: Raccogliere e usare le informazioni di diagnostica dai dispositivi HoloLens
description: Scopri come raccogliere, usare e conservare le informazioni di diagnostica dai dispositivi HoloLens.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4a360e99a45b855957e36dd6ba31ede3da9631ba
ms.sourcegitcommit: b5f1b7c197cb58b746efc3809c61cf7a2e8c08ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "11399808"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Raccogliere e usare le informazioni di diagnostica dai dispositivi HoloLens

Gli utenti e gli amministratori di HoloLens possono scegliere tra quattro metodi diversi per raccogliere informazioni di diagnostica da HoloLens:

- App Hub di Feedback
- CSP DiagnosticLog
- app Impostazioni
- Diagnostica offline

> [!IMPORTANT]  
> I log di diagnostica dei dispositivi contengono informazioni personali, ad esempio sui processi o le applicazioni avviati dall'utente durante le operazioni tipiche. Quando più utenti condividono un dispositivo HoloLens (ad esempio, gli utenti accodati allo stesso dispositivo usando account Microsoft Azure Active Directory (Azure AD) diversi, i log di diagnostica possono contenere informazioni sulle informazioni personali applicabili a più utenti. Per ulteriori informazioni, vedere [l'Informativa sulla privacy di Microsoft.](https://privacy.microsoft.com/privacystatement)

Nella tabella seguente vengono confrontati i diversi metodi di raccolta. I nomi dei metodi si collegano a informazioni più dettagliate nelle sezioni successive alla tabella.

|Metodo |Prerequisiti |Posizioni dei dati |Accesso e utilizzo dei dati |Conservazione dei dati |
| --- | --- | --- | --- | --- |
|[Hub di Feedback](#feedback-hub) |Connessione di rete e Internet<br /><br />App Hub di Feedback<br /><br />Autorizzazione per caricare file nel cloud Microsoft |Cloud Microsoft<br /><br />Dispositivo HoloLens (facoltativo) |L'utente richiede assistenza, accetta le condizioni per l'utilizzo e carica i dati<br /><br />I dipendenti Microsoft visualizzano i dati in modo coerente con le condizioni per l'utilizzo |I dati nel cloud vengono conservati per il periodo definito da Next Generation Privacy (NGP). I dati vengono quindi eliminati automaticamente.<br /><br />I dati nel dispositivo possono essere eliminati in qualsiasi momento da un utente con autorizzazioni di **proprietario del dispositivo** **o** amministratore. |
|[Risoluzione dei problemi delle impostazioni](#settings-troubleshooter) |app Impostazioni |Dispositivo HoloLens<br /><br />Computer connesso (facoltativo) |L'utente archivia i dati e solo l'utente accede ai dati (a meno che l'utente non condiva in modo specifico i dati con un altro utente). |I dati vengono conservati nel dispositivo fino a quando l'utente non lo elimina.* |
|[CSP DiagnosticLog](#diagnosticlog-csp) |Connessione di rete<br /><br />Ambiente MDM che supporta il provider di servizi di configurazione DiagnosticLog |L'amministratore configura i percorsi di archiviazione |Nell'ambiente gestito, l'utente acconsente implicitamente all'accesso da parte dell'amministratore ai dati.<br /><br />L'amministratore configura le autorizzazioni e i ruoli di accesso. | I dati vengono conservati nell'archiviazione cloud e l'amministratore configura i criteri di conservazione. |
|[Diagnostica offline](#offline-diagnostics) |Configurazione dispositivo:<ul><li>Acceso e connesso al computer</li><li>Pulsanti di alimentazione e volume funzionanti</li></ul> |Dispositivo HoloLens<br /><br />Computer connesso |L'utente archivia i dati e solo l'utente accede ai dati (a meno che l'utente non condiva in modo specifico i dati con un altro utente). |I dati vengono conservati nel dispositivo fino a quando l'utente non lo elimina. |

- L'utente finale è responsabile della condivisione responsabile dei log con un altro utente. Questi file sono utili principalmente quando si contatta il servizio clienti e il supporto tecnico.  

## <a name="feedback-hub"></a>Hub di Feedback

Un utente di HoloLens può usare l'app desktop Hub di Microsoft Feedback per inviare informazioni di diagnostica al supporto tecnico Microsoft. Per informazioni dettagliate e istruzioni complete, vedere [Inviare commenti e suggerimenti.](hololens-feedback.md)  

> [!NOTE]  
> **Utenti commerciali o aziendali:** Se usi l'app Hub di Feedback per segnalare un problema relativo a MDM, provisioning o altri aspetti della gestione dei dispositivi, modifica la categoria dell'app in **Categoria**dispositivo di gestione  >  **aziendale.**

### <a name="prerequisites"></a>Prerequisiti

- Il dispositivo è connesso a una rete.
- L'app Hub di Feedback è disponibile nel computer desktop dell'utente e l'utente può caricare file nel cloud Microsoft.

### <a name="data-locations-access-and-retention"></a>Posizioni, accesso e conservazione dei dati

Accettando le condizioni per l'uso di Hub di Feedback, l'utente acconsente esplicitamente all'archiviazione e all'utilizzo dei dati (come definito dal contratto).

Hub di Feedback offre due posizioni in cui l'utente può archiviare le informazioni di diagnostica:

- **Microsoft Cloud.** I dati caricati dall'utente tramite l'app Hub di Feedback vengono archiviati per il numero di giorni che è coerente con i requisiti NGP (Next Generation Privacy). I dipendenti Microsoft possono usare un visualizzatore conforme a NGP per accedere alle informazioni durante questo periodo.
   > [!NOTE]  
   > Questi requisiti si applicano ai dati in tutte le categorie di Hub di Feedback.

- **Il dispositivo HoloLens.** Durante l'archiviazione di un report nell'Hub di Feedback, l'utente può selezionare Salva una copia locale della diagnostica e degli allegati creati per **inviare commenti e suggerimenti.** Se l'utente seleziona questa opzione, Hub di Feedback archivia una copia delle informazioni di diagnostica nel dispositivo HoloLens. Queste informazioni rimangono accessibili all'utente (o a chiunque usi tale account per accedere a HoloLens). Per eliminare queste informazioni, un utente deve disporre delle autorizzazioni **di proprietario del dispositivo** **o** amministratore per il dispositivo. Un utente che dispone delle autorizzazioni appropriate può **** accedere all'Hub di Feedback, selezionare Impostazioni Visualizza log di  >  **** diagnostica ed eliminare le informazioni.

## <a name="settings-troubleshooter"></a>Risoluzione dei problemi delle impostazioni

Un utente di HoloLens può usare l'app Impostazioni nel dispositivo per risolvere i problemi e raccogliere informazioni diagnostiche. A tale scopo, effettua quanto segue:

1. Apri l'app Impostazioni e seleziona **Aggiorna & risoluzione dei problemi**  >  **di** sicurezza.
1. Selezionare l'area appropriata e quindi fare clic su **Start.**
1. Riprodurre il problema.
1. Dopo aver riprodotto il problema, tornare a Impostazioni e selezionare **Interrompi.**

### <a name="prerequisites"></a>Prerequisiti

- L'app Impostazioni viene installata nel dispositivo ed è disponibile per l'utente.

### <a name="data-locations-access-and-retention"></a>Posizioni, accesso e conservazione dei dati

Poiché l'utente avvia la raccolta dei dati, l'utente acconsente implicitamente all'archiviazione delle informazioni di diagnostica. Solo l'utente o chiunque con cui condivide i dati può accedere ai dati.

Le informazioni di diagnostica vengono archiviate nel dispositivo. Se il dispositivo è connesso al computer dell'utente, le informazioni risiedono anche nel computer nel file seguente:

> Questo PC\\ \<*HoloLens device name*> \\Archiviazione interna\\Documenti\\Traccia \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> In questo percorso e nome di file rappresenta il nome del dispositivo HoloLens e rappresenta la data e l'ora di creazione \<*HoloLens device name*> \<*ddmmyyhhmmss*> del file.

Le informazioni di diagnostica rimangono in queste posizioni fino a quando l'utente non le elimina.

## <a name="diagnosticlog-csp"></a>CSP DiagnosticLog

In un ambiente di gestione di dispositivi mobili (MDM, Mobile Device Management), l'amministratore IT può usare il provider di servizi di configurazione [DiagnosticLog (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) per configurare le impostazioni di diagnostica nei dispositivi HoloLens registrati. L'amministratore IT può configurare queste impostazioni per raccogliere i log dai dispositivi registrati.

Altre informazioni:
- [Raccogliere la diagnostica da un dispositivo Windows](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [Anteprima pubblica di Intune - Diagnostica dei dispositivi Windows 10](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Prerequisiti

- Il dispositivo è connesso a una rete.
- Il dispositivo viene registrato in un ambiente MDM che supporta il CSP DiagnosticLog.

### <a name="data-locations-access-and-retention"></a>Posizioni, accesso e conservazione dei dati

Poiché il dispositivo fa parte dell'ambiente gestito, l'utente acconsente implicitamente all'accesso amministrativo alle informazioni di diagnostica.

L'amministratore IT utilizza il provider di servizi di configurazione DiagnosticLog per configurare i criteri di archiviazione, conservazione e accesso dei dati, inclusi i criteri che regolano gli elementi seguenti:

- Infrastruttura cloud in cui vengono archiviate le informazioni di diagnostica.
- Periodo di conservazione per le informazioni di diagnostica.
- Autorizzazioni che controllano l'accesso alle informazioni di diagnostica.

## <a name="offline-diagnostics"></a>Diagnostica offline
In situazioni in cui il dispositivo non è in grado di raccogliere la diagnostica tramite Hub di Feedback o lo strumento di risoluzione dei problemi delle impostazioni, puoi raccogliere la diagnostica manualmente. Uno scenario in cui ciò è necessario è quando il dispositivo non può connettersi a Wi-Fi o non è possibile accedere ad altri metodi menzionati in precedenza. La diagnostica raccoglie i dump di arresto anomalo e i log dal dispositivo che consentono a un tecnico del supporto Microsoft di isolare i problemi.

Questa operazione funziona quando il dispositivo viene visualizzato in Esplora file dopo la connessione a un PC tramite un cavo USB.

> [!NOTE]
> La generazione e la gestione della diagnostica offline vengono controllate in modo diverso a seconda della versione del sistema operativo. In precedenza era controllato dall'impostazione di telemetria, ma ora è controllato direttamente tramite criteri MDM. Se disabilitata tramite l'impostazione o i criteri MDM, i log di diagnostica non possono essere raccolti con questo meccanismo.

Comportamento precedente a [Windows Holographic, versione 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - La diagnostica offline è abilitata solo quando l'utente sta passando attraverso la Configurazione guidata o Sistema\Il valore del criterio [AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) è impostato su Completo (il valore di base è il valore predefinito in HoloLens). 
- Per disabilitare la diagnostica offline, vai alla pagina **Impostazioni app > Privacy** e seleziona **Base** in Dati **di diagnostica.** Nelle build in cui la diagnostica offline dipende dall'impostazione di telemetria, influisce solo sulla raccolta o meno di eventuali log. Non influisce sui file raccolti.
- Se il dispositivo è bloccato, i log non verranno visualizzati.

Nelle build [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) e versioni successiva:
- Quando la diagnostica di fallback è abilitata, verrà controllata da criteri MDM specifici con l'impostazione [MixedReality/FallbackDiagnostics corrispondente](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Se il dispositivo è bloccato, i log non verranno visualizzati.

Guardare questo video per altre informazioni.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Segui questi passaggi per raccogliere la diagnostica:
1.  Collega il dispositivo con un cavo USB al PC.
2.  In Esplora file nel PC passa a **"Questo PC \<hololens-device> \Archiviazione interna".**
3.  Se la **cartella Di** archiviazione interna non viene mostrata, il dispositivo è in attesa dell'accesso di un utente. Accesso o ciclo di alimentazione del dispositivo tenendo premuto il pulsante POWER per 10 secondi.
4.  Premere e rilasciare immediatamente i **pulsanti POWER + VOLUME DOWN** insieme.
5.  Attendere un minuto che il dispositivo prepari gli archivi ZIP. Un file temporaneo denominato HololensDiagnostics.temp potrebbe diventare visibile mentre il dispositivo genera gli archivi ZIP. Non accedere al file o salvarlo. Al termine del processo, questo verrà sostituito dagli archivi ZIP.
6.  Aggiornare Esplora file e passare alla **cartella "\Documents".**
7.  Copiare i file ZIP di diagnostica e condividerli con il team di supporto Microsoft.

> [!NOTE]
> Alcuni dei file ZIP di diagnostica possono contenere informazioni personali.
