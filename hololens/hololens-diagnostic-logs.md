---
title: Raccogliere e usare le informazioni di diagnostica HoloLens dispositivi
description: Informazioni su come raccogliere, usare e conservare le informazioni di diagnostica HoloLens dispositivi.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 9/12/2021
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
ms.openlocfilehash: 4f62a70430d78087157b3adcdf76af53183db708
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924402"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Raccogliere e usare le informazioni di diagnostica HoloLens dispositivi

HoloLens utenti e amministratori possono scegliere tra quattro metodi diversi per raccogliere informazioni di diagnostica da HoloLens:

- Hub di Feedback app
- CSP DiagnosticLog
- app Impostazioni
- Diagnostica offline

> [!IMPORTANT]  
> I log di diagnostica del dispositivo contengono informazioni personali, ad esempio su quali processi o applicazioni l'utente avvia durante le operazioni tipiche. Quando più utenti condividono un dispositivo HoloLens ,ad esempio gli utenti a cui a loro volta a un account Microsoft Azure Active Directory (Azure AD) diverso, i log di diagnostica possono contenere informazioni personali che si applicano a più utenti. Per altre informazioni, vedere Informativa [sulla privacy di Microsoft.](https://privacy.microsoft.com/privacystatement)

Nella tabella seguente vengono confrontati i diversi metodi di raccolta. I nomi dei metodi si collegano a informazioni più dettagliate nelle sezioni che seguono la tabella.

|Metodo |Prerequisiti |Posizioni dei dati |Accesso ai dati e uso |Conservazione dei dati |
| --- | --- | --- | --- | --- |
|[Hub di Feedback](#feedback-hub) |Connessione di rete e Internet<br /><br />Hub di Feedback app<br /><br />Autorizzazione per caricare file nel cloud Microsoft |Cloud Microsoft<br /><br />HoloLens dispositivo (facoltativo) |L'utente richiede assistenza, accetta le condizioni per l'utilizzo e carica i dati<br /><br />I dipendenti Microsoft visualizzano i dati in modo coerente con le condizioni per l'utilizzo |I dati nel cloud vengono conservati per il periodo definito da Next Generation Privacy (NGP). I dati vengono quindi eliminati automaticamente.<br /><br />I dati nel dispositivo possono essere eliminati in qualsiasi momento da un utente con autorizzazioni di **proprietario del dispositivo** **o** amministratore. |
|[Impostazioni Troubleshooter](#settings-troubleshooter) |app Impostazioni |Dispositivo HoloLens<br /><br />Computer connesso (facoltativo) |L'utente archivia i dati e solo l'utente accede ai dati ( a meno che l'utente non condiva i dati in modo specifico con un altro utente). |I dati vengono mantenuti nel dispositivo fino a quando l'utente non lo elimina.* |
|[CSP DiagnosticLog](#diagnosticlog-csp) |Connessione di rete<br /><br />Ambiente MDM che supporta il provider di servizi di configurazione DiagnosticLog |L'amministratore configura le posizioni di archiviazione |Nell'ambiente gestito l'utente acconsente implicitamente all'accesso come amministratore ai dati.<br /><br />L'amministratore configura le autorizzazioni e i ruoli di accesso. | I dati vengono conservati nell'archiviazione cloud e l'amministratore configura i criteri di conservazione. |
|[Diagnostica offline](#offline-diagnostics) |Configurazione del dispositivo:<ul><li>Acceso e connesso al computer</li><li>Pulsanti di alimentazione e volume funzionanti</li></ul> |Dispositivo HoloLens<br /><br />Computer connesso |L'utente archivia i dati e solo l'utente accede ai dati ( a meno che l'utente non condiva i dati in modo specifico con un altro utente). |I dati vengono mantenuti nel dispositivo fino a quando l'utente non lo elimina. |

* L'utente finale è responsabile della condivisione responsabile dei log con un altro utente. Questi file sono particolarmente utili quando si contatta il servizio clienti e il supporto tecnico.  

## <a name="feedback-hub"></a>Hub di Feedback

Un HoloLens utente può usare l'app desktop Microsoft Hub di Feedback per inviare informazioni di diagnostica Supporto tecnico Microsoft. Per informazioni dettagliate e istruzioni complete, vedere [Inviare commenti e suggerimenti.](hololens-feedback.md)  

> [!NOTE]  
> **Utenti commerciali o aziendali:** Se si usa l'app Hub di Feedback per segnalare un problema relativo a MDM, provisioning o qualsiasi altro aspetto della gestione dei dispositivi, modificare la categoria dell'app in **Enterprise Management**  >  **Device (Gestione dispositivi).**

>[!IMPORTANT]
> Per fornire i migliori dati possibili per la risoluzione dei problemi, è consigliabile impostare i dati di telemetria del dispositivo su **Facoltativo.** È possibile impostare questo valore durante la configurazione predefinita o usando **l'app** Impostazioni predefinita. Per eseguire questa operazione usando Impostazioni, selezionare **Start > Impostazioni > Privacy > App Diagnostics > On .**

### <a name="prerequisites"></a>Prerequisiti

- Il dispositivo è connesso a una rete.
- L Hub di Feedback app è disponibile nel computer desktop dell'utente e l'utente può caricare i file nel cloud Microsoft.

### <a name="data-locations-access-and-retention"></a>Percorsi, accesso e conservazione dei dati

Accettando le condizioni per l'utilizzo del Hub di Feedback, l'utente acconsente esplicitamente all'archiviazione e all'utilizzo dei dati (come definito dal contratto).

Il Hub di Feedback offre all'utente due posizioni in cui archiviare le informazioni di diagnostica:

- **Microsoft Cloud.** I dati caricati dall'utente usando l'app Hub di Feedback vengono archiviati per il numero di giorni che è coerente con i requisiti NGP (Next Generation Privacy). I dipendenti Microsoft possono usare un visualizzatore conforme a NGP per accedere alle informazioni durante questo periodo.

   > [!NOTE]  
   > Questi requisiti si applicano ai dati in tutte Hub di Feedback categorie.

- **Oggetto HoloLens dispositivo.** Durante l'archiviazione di un report in Hub di Feedback, l'utente può selezionare Salva una copia locale della diagnostica e degli allegati creati quando si **inviano commenti e suggerimenti.** Se l'utente seleziona questa opzione, il Hub di Feedback archivia una copia delle informazioni di diagnostica nel HoloLens dispositivo. Queste informazioni rimangono accessibili all'utente (o a chiunque usi tale account per accedere a HoloLens). Per eliminare queste informazioni, un utente deve avere le **autorizzazioni di proprietario del dispositivo** **o** amministratore per il dispositivo. Un utente che dispone delle autorizzazioni appropriate può accedere al Hub di Feedback, selezionare Impostazioni Visualizza log  >  **di** diagnostica ed eliminare le informazioni.

## <a name="settings-troubleshooter"></a>Impostazioni Troubleshooter

Un HoloLens utente può usare l'app **Impostazioni** nel dispositivo per risolvere i problemi e raccogliere informazioni di diagnostica. A questo scopo, seguire questa procedura:

1. Aprire l'app Impostazioni e selezionare **Aggiorna & risoluzione dei problemi**  >  **di** sicurezza.
1. Selezionare l'area appropriata e selezionare **Avvia**.
1. Riprodurre il problema.
1. Dopo aver riprodotto il problema, tornare a Impostazioni e quindi selezionare **Arresta**.

Un utente può anche configurare il comportamento di Diagnostica di fallback dall'app **Impostazioni** app. Passare alla **pagina Privacy -> Risoluzione dei problemi** per configurare questa impostazione.
> [!NOTE]
> Se per il dispositivo sono configurati criteri MDM, l'utente non sarà in grado di eseguire l'override di tale comportamento.

### <a name="os-update-troubleshooter"></a>Strumento di risoluzione dei problemi di aggiornamento del sistema operativo

Nelle build Windows [Holographic, versione 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e versioni successiva:
- Oltre ai precedenti strumento di risoluzione dei problemi all'interno dell'app Impostazioni, è stato aggiunto un nuovo strumento di risoluzione dei problemi con l'aggiunta della nuova app Impostazioni per gli aggiornamenti del sistema operativo. Passare a **-Impostazioni -> Update & Security -> Troubleshoot -> Windows Update** e selezionare **Avvia.** In questo modo è possibile raccogliere tracce durante la riproduzione del problema con gli aggiornamenti del sistema operativo per facilitare la risoluzione dei problemi con l'IT o il supporto tecnico.

### <a name="prerequisites"></a>Prerequisiti

- **L Impostazioni app** è installata nel dispositivo ed è disponibile per l'utente.

### <a name="data-locations-access-and-retention"></a>Percorsi, accesso e conservazione dei dati

Poiché l'utente avvia la raccolta dei dati, l'utente acconsente implicitamente all'archiviazione delle informazioni di diagnostica. Solo l'utente o chiunque con cui l'utente condivide i dati può accedere ai dati.

Le informazioni di diagnostica vengono archiviate nel dispositivo. Se il dispositivo è connesso al computer dell'utente, le informazioni si trovano anche nel computer nel file seguente:

> Questo PC \\ \<*HoloLens device name*> \\ interno Archiviazione documenti \\ traccia \\ \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> In questo percorso e nome di file rappresenta il nome del dispositivo HoloLens e rappresenta la data e l'ora di creazione \<*HoloLens device name*> \<*ddmmyyhhmmss*> del file.

Le informazioni di diagnostica rimangono in queste posizioni fino a quando l'utente non le elimina.

### <a name="view-diagnostic-report"></a>Visualizzare il report di diagnostica

Per visualizzare la diagnostica MDM HoloLens 2, selezionare l'icona Wi-Fi, quindi passare Impostazioni Account accesso aziendale o dell'istituto di istruzione e selezionare Esporta  ->    >   i log **di gestione.** HoloLens invia i file di log all'account e visualizza la relativa posizione nel PC desktop.

## <a name="diagnosticlog-csp"></a>CSP DiagnosticLog

In un ambiente di gestione di dispositivi mobili (MDM), l'amministratore IT può usare il provider di servizi di configurazione [DiagnosticLog (CSP)](/windows/client-management/mdm/diagnosticlog-csp) per configurare le impostazioni di diagnostica nei dispositivi HoloLens registrati. L'amministratore IT può configurare queste impostazioni per raccogliere i log dai dispositivi registrati.

Per altre informazioni, vedere:
- [Raccogliere la diagnostica da un Windows dispositivo](/mem/intune/remote-actions/collect-diagnostics)
- [Anteprima pubblica di Intune - Diagnostica Windows 10 dispositivo](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Prerequisiti

- Il dispositivo è connesso a una rete.
- Il dispositivo viene registrato in un ambiente MDM che supporta diagnosticLog CSP.

### <a name="data-locations-access-and-retention"></a>Percorsi, accesso e conservazione dei dati

Poiché il dispositivo fa parte dell'ambiente gestito, l'utente acconsente implicitamente all'accesso amministrativo alle informazioni di diagnostica.

L'amministratore IT usa il provider di servizi di configurazione DiagnosticLog per configurare i criteri di archiviazione, conservazione e accesso dei dati, inclusi i criteri che regolano gli elementi seguenti:

- Infrastruttura cloud in cui sono archiviate le informazioni di diagnostica.
- Periodo di conservazione per le informazioni di diagnostica.
- Autorizzazioni che controllano l'accesso alle informazioni di diagnostica.

## <a name="offline-diagnostics"></a>Diagnostica offline

Nelle situazioni in cui il dispositivo non è in grado di raccogliere la diagnostica tramite Hub di Feedback o lo strumento Impostazioni risoluzione dei problemi, è possibile raccogliere la diagnostica manualmente. Uno scenario in cui ciò è necessario è quando il dispositivo non può connettersi Wi-Fi o non è possibile accedere ad altri metodi indicati in precedenza. La diagnostica raccoglie i dump e i log di arresto anomalo del sistema dal dispositivo che consentono a un tecnico del supporto Microsoft di isolare i problemi.

Questa operazione funziona quando il dispositivo viene visualizzato Esplora file dopo la connessione a un PC tramite un cavo USB.

> [!NOTE]
> La generazione e la gestione della diagnostica offline vengono controllate in modo diverso a seconda della versione del sistema operativo. In precedenza era controllato dall'impostazione di telemetria, ma ora è controllato direttamente tramite criteri MDM. Se disabilitata tramite l'impostazione o i criteri MDM, i log di diagnostica non possono essere raccolti usando questo meccanismo.

Comportamento precedente a [Windows Holographic, versione 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - La diagnostica offline è abilitata solo quando l'utente sta passando la configurazione guidata o il valore dei criteri [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) è impostato su Full (Basic è il valore predefinito HoloLens). 
- Per disabilitare la diagnostica offline, passare **alla pagina Impostazioni App > Privacy** e selezionare Di **base** in Dati **di diagnostica**. Nelle compilazioni in cui la diagnostica offline dipende dall'impostazione di telemetria, influisce solo sulla raccolta o meno dei log. Non influisce sui file raccolti.
- Se il dispositivo è bloccato, i log non verranno visualizzati.

Nelle build Windows [Holographic, versione 20H2 e](hololens-release-notes.md#windows-holographic-version-20h2) versioni successiva:
- Quando la diagnostica di fallback è abilitata, verrà controllata da criteri MDM specifici con l'impostazione [mixedReality/FallbackDiagnostics corrispondente](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Se il dispositivo è bloccato, i log non verranno visualizzati.

Guardare questo video per saperne di più.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Seguire questa procedura per raccogliere la diagnostica:

1.  Connessione dispositivo con un cavo USB al PC.

2.  Nel Esplora file nel PC passare a **"Questo PC \<hololens-device> \Internal Archiviazione"**.

3.  Se la **cartella Internal Archiviazione** non viene visualizzato, il dispositivo è in attesa dell'accesso di un utente. Accedere o eseguire il ciclo di alimentazione del dispositivo tenendo premuto il pulsante POWER per 10 secondi.

4.  Premere e rilasciare immediatamente i **pulsanti Power + Volume Down** insieme.

5.  Attendere un minuto che il dispositivo prepari gli archivi ZIP. Un file temporaneo denominato HololensDiagnostics.temp può diventare visibile mentre il dispositivo genera gli archivi ZIP. Non accedere o salvare il file. Al termine del processo, verrà sostituito dagli archivi ZIP.

6.  Aggiornare Esplora file e passare alla **cartella '\Documents'.**

7.  Copiare i file ZIP di diagnostica e condividerli con il team di supporto Microsoft.

> [!NOTE]
> Alcuni dei file ZIP di diagnostica possono contenere informazioni personali.

### <a name="offline-diagnostics-notifications"></a>Notifiche di diagnostica offline

- Introdotto in [Windows Holographic, versione 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Si tratta di un aggiornamento per una funzionalità esistente denominata [Diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics). In precedenza, non era presente alcun indicatore chiaro per gli utenti che avevano attivato la raccolta diagnostica o che era stata completata.
A questo punto, Windows build Insider, sono disponibili due forme di feedback visivo per la diagnostica offline. Il primo è notifiche di tipo avviso popup visualizzate sia all'avvio che al completamento della raccolta. Verranno visualizzati quando l'utente è connesso e dispone di oggetti visivi.

![Avviso popup per la raccolta di log.](./images/logcollection1.jpg)

![Avviso popup al termine della raccolta dei log.](./images/logcollection2.jpg)

Poiché gli utenti usano spesso La diagnostica offline come meccanismo di raccolta dei log di fallback per quando non hanno accesso a una visualizzazione, non possono accedere o sono ancora in Configurazione guidata. Verrà inoltre riprodotto un segnale audio quando vengono raccolti i log. Questo suono verrà riprodotto oltre alla notifica di tipo avviso popup.

Questa nuova funzionalità verrà abilitata quando il dispositivo viene aggiornato e non deve essere abilitata o gestita. In qualsiasi caso in cui questo nuovo feedback non possa essere visualizzato o ascoltato, la diagnostica offline verrà comunque generata.

Con questa aggiunta più recente di commenti e suggerimenti per l'audio è più facile raccogliere dati di diagnostica e risolvere più rapidamente i problemi.

### <a name="low-storage-log-collection-improvements"></a>Miglioramenti della raccolta di log di archiviazione a basso livello

- Introdotto in [Windows Holographic, versione 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Negli scenari in cui un dispositivo sembra avere spazio su disco  insufficiente quando vengono raccolti i log di diagnostica, verrà creato un report aggiuntivo denominatoStorageDiagnostics.zip. La soglia di spazio di archiviazione basso viene determinata automaticamente dal Windows [di archiviazione.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

## <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Visualizzare il report di diagnostica avanzato in Impostazioni in HoloLens

- Introdotto in [Windows Holographic, versione 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Per i dispositivi gestiti durante la risoluzione dei problemi, verificare che sia applicata una configurazione dei criteri prevista è un passaggio importante. In precedenza questa nuova funzionalità doveva essere eseguita fuori dal dispositivo tramite MDM o vicino al dispositivo dopo l'esportazione dei log di diagnostica MDM raccolti tramite gli account **Impostazioni** Accesso all'organizzazione o all'istituto di istruzione e selezionare Esporta i log di gestione e visualizzati in un PC nelle  ->    >  vicinanze. 

È ora possibile visualizzare la diagnostica MDM nel dispositivo usando il browser Edge. Per visualizzare più facilmente il report di diagnostica MDM, passare alla pagina Accedi all'istituto di istruzione o all'istituto di istruzione e selezionare **Visualizza report di diagnostica avanzato.** Verrà generato e aperto il report in una nuova finestra di Edge.

![Visualizzare il report di diagnostica avanzato nell Impostazioni app.](./images/view-advanced-diagnostic-report.jpg)
