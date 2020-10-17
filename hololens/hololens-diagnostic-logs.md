---
title: Raccogliere e usare le informazioni di diagnostica dai dispositivi HoloLens
description: Raccogliere e usare le informazioni di diagnostica dai dispositivi HoloLens
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
ms.openlocfilehash: e1302a3d482648b1ebbf7fee71ceec3ca4261d23
ms.sourcegitcommit: 87d503434339fc6c9b41aa9473e35ddfde845cac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "11120147"
---
# Raccogliere e usare le informazioni di diagnostica dai dispositivi HoloLens

Gli utenti e gli amministratori di HoloLens possono scegliere tra quattro metodi diversi per raccogliere informazioni di diagnostica da HoloLens:

- App Hub feedback
- CSP DiagnosticLog
- app Impostazioni

> [!IMPORTANT]  
> I log di diagnostica del dispositivo contengono informazioni personali, ad esempio i processi o le applicazioni che l'utente avvia durante le operazioni tipiche. Quando più utenti condividono un dispositivo HoloLens, ad esempio gli utenti accedono allo stesso dispositivo usando diversi account di Microsoft Azure Active Directory (AAD), i log di diagnostica potrebbero contenere informazioni personali che si applicano a più utenti. Per altre informazioni, vedere l'informativa [sulla privacy Microsoft](https://privacy.microsoft.com/privacystatement).

Nella tabella seguente vengono confrontati i tre metodi di raccolta. I nomi dei metodi si collegano a informazioni più dettagliate nelle sezioni che seguono la tabella.

|Metodo |Prerequisiti |Posizioni dei dati |Accesso ai dati e utilizzo |Conservazione dei dati |
| --- | --- | --- | --- | --- |
|[Hub di Feedback](#feedback-hub) |Connessione di rete e Internet<br /><br />App Hub feedback<br /><br />Autorizzazione per caricare file in Microsoft Cloud |Microsoft Cloud<br /><br />Dispositivo HoloLens (facoltativo) |L'utente richiede assistenza, accetta le condizioni per l'uso e carica i dati<br /><br />I dipendenti Microsoft visualizzano i dati, in conformità con le condizioni per l'utilizzo |I dati nel cloud vengono conservati per il periodo definito dalla privacy di nuova generazione (NGP). I dati vengono quindi eliminati automaticamente.<br /><br />I dati del dispositivo possono essere eliminati in qualsiasi momento da un utente con autorizzazioni di **amministratore** o **proprietario del dispositivo** . |
|[Risoluzione dei problemi di impostazioni](#settings-troubleshooter) |app Impostazioni |Dispositivo HoloLens<br /><br />Computer connesso (facoltativo) |L'utente archivia i dati e solo l'utente accede ai dati, a meno che l'utente non condivida in modo specifico i dati con un altro utente. |I dati vengono mantenuti finché l'utente non la Elimina. * |
|[CSP DiagnosticLog](#diagnosticlog-csp) |Connessione di rete<br /><br />Ambiente MDM che supporta il CSP DiagnosticLog |L'amministratore configura i percorsi di archiviazione |Nell'ambiente gestito l'utente acconsente implicitamente all'accesso di amministratore ai dati.<br /><br />L'amministratore configura i ruoli e le autorizzazioni di accesso. | L'amministratore configura i criteri di conservazione. |
|[Diagnostica offline](#offline-diagnostics) |Configurazione dispositivo:<ul><li>Acceso e connesso al computer</li><li>Funzionamento dei pulsanti di alimentazione e di volume</li></ul> |Dispositivo HoloLens<br /><br />Computer connesso |L'utente archivia i dati e solo l'utente accede ai dati, a meno che l'utente non condivida in modo specifico i dati con un altro utente. |I dati vengono mantenuti finché l'utente non la Elimina. | 


-   L'utente finale è responsabile della condivisione dei registri in modo responsabile con altri utenti. Questi file sono principalmente utili per contattare il servizio assistenza clienti e il supporto tecnico.  

## Hub di Feedback

Un utente di HoloLens può usare l'app desktop Microsoft Feedback hub per inviare informazioni di diagnostica al supporto Microsoft. Per informazioni dettagliate e istruzioni complete, vedere [inviare commenti e suggerimenti](hololens-feedback.md).  

> [!NOTE]  
> **Utenti commerciali o aziendali:** Se usi l'app hub di feedback per segnalare un problema che si riferisce a MDM, provisioning o qualsiasi altro aspetto di gestione dei dispositivi, modifica la categoria **Enterprise Management**dell'app in  >  **Categoria dispositivo**di gestione aziendale.

### Prerequisiti

- Il dispositivo è connesso a una rete.
- L'app hub di feedback è disponibile nel computer desktop dell'utente e l'utente può caricare i file nel cloud Microsoft.

### Posizioni dei dati, accesso e conservazione

Accettando le condizioni per l'uso dell'hub di feedback, l'utente acconsente esplicitamente all'archiviazione e all'uso dei dati (come definito da tale contratto).

L'hub di feedback offre due posizioni per l'utente per archiviare le informazioni di diagnostica:

- **Microsoft Cloud**. I dati caricati dall'utente tramite l'app hub di feedback vengono archiviati per il numero di giorni coerenti con i requisiti per la privacy di nuova generazione (NGP). I dipendenti Microsoft possono usare un visualizzatore conforme a NGP per accedere alle informazioni durante questo periodo.
   > [!NOTE]  
   > Questi requisiti si applicano ai dati in tutte le categorie di hub di feedback.

- **Il dispositivo HoloLens**. Durante l'archiviazione di un report nell'hub di feedback, l'utente può selezionare **Salva una copia locale di diagnostica e allegati creati quando si dà un feedback**. Se l'utente seleziona questa opzione, l'hub di feedback archivia una copia delle informazioni di diagnostica nel dispositivo HoloLens. Queste informazioni restano accessibili per l'utente (o tutti gli utenti che usano quell'account per accedere a HoloLens). Per eliminare queste informazioni, un utente deve avere il **proprietario del dispositivo** o le autorizzazioni di **amministratore** per il dispositivo. Un utente con le autorizzazioni appropriate può accedere all'hub di feedback, selezionare i **Settings**  >  **registri di diagnostica della visualizzazione**impostazioni ed eliminare le informazioni.

## Risoluzione dei problemi di impostazioni

Un utente di HoloLens può usare l'app impostazioni nel dispositivo per risolvere i problemi e raccogliere informazioni di diagnostica. A tale scopo, effettua quanto segue:

1. Aprire l'app Impostazioni e selezionare **Aggiorna &**  >  pagina**risoluzione dei problemi** di sicurezza.
1. Selezionare l'area appropriata e selezionare **Avvia**.
1. Riprodurre il problema.
1. Dopo aver riprodotto il problema, tornare a impostazioni e quindi selezionare **Interrompi**.

### Prerequisiti

- L'app impostazioni è installata nel dispositivo ed è disponibile per l'utente.

### Posizioni dei dati, accesso e conservazione

Dato che l'utente avvia la raccolta dati, l'utente acconsente implicitamente all'archiviazione delle informazioni di diagnostica. Solo l'utente o chiunque con cui l'utente condivide i dati può accedere ai dati.

Le informazioni di diagnostica sono archiviate nel dispositivo. Se il dispositivo è connesso al computer dell'utente, le informazioni si trovano anche nel computer nel file seguente:

> Questo PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> . etl

> [!NOTE]  
> In questo percorso e nome del file \<*HoloLens device name*> rappresenta il nome del dispositivo HoloLens e \<*ddmmyyhhmmss*> rappresenta la data e l'ora in cui il file è stato creato.

Le informazioni di diagnostica restano in questi percorsi finché l'utente non la Elimina.

## CSP DiagnosticLog

In un ambiente di gestione di dispositivi mobili (MDM), l'amministratore IT può usare il [provider del servizio di configurazione di DiagnosticLog (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) per configurare le impostazioni di diagnostica nei dispositivi HoloLens registrati. L'amministratore IT può configurare queste impostazioni per raccogliere i log dai dispositivi registrati.

### Prerequisiti

- Il dispositivo è connesso a una rete.
- Il dispositivo è registrato in un ambiente MDM che supporta il CSP DiagnosticLog.

### Posizioni dei dati, accesso e conservazione

Dato che il dispositivo fa parte dell'ambiente gestito, l'utente acconsente implicitamente all'accesso amministrativo alle informazioni di diagnostica.

L'amministratore IT usa il CSP DiagnosticLog per configurare i criteri di archiviazione, conservazione e accesso dei dati, inclusi i criteri che regolano le operazioni seguenti:

- Infrastruttura cloud in cui sono archiviate le informazioni di diagnostica.
- Periodo di conservazione per le informazioni di diagnostica.
- Autorizzazioni che controllano l'accesso alle informazioni di diagnostica.

## Diagnostica offline
In situazioni in cui il dispositivo non è in grado di raccogliere la diagnostica tramite hub di feedback o lo strumento di risoluzione dei problemi di impostazione, è possibile raccogliere la diagnostica manualmente. Uno scenario in cui è necessario quando il dispositivo non riesce a connettersi alla rete Wi-Fi. La diagnostica raccoglie i dump e i registri di arresto anomalo del dispositivo che aiutano un ingegnere del supporto tecnico Microsoft a isolare i problemi.

Questa operazione funziona quando il dispositivo viene visualizzato in Esplora file dopo averla collegata a un PC tramite un cavo USB. 

> [!NOTE]
> La diagnostica offline è abilitata solo quando l'utente sta attraversando il valore dei criteri OOBE o [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) è impostato su Full (il valore predefinito è Basic in Hololens). 

Se il dispositivo è bloccato, i log non verranno visualizzati. Per disabilitare la diagnostica offline, vai alla pagina **Impostazioni App > privacy** e seleziona **Basic** in **dati di diagnostica**. Nelle build in cui la diagnostica offline dipende dall'impostazione di telemetria, l'effetto si verifica solo se i registri vengono raccolti o meno. Non influisce sui file raccolti.

Guarda questo video per saperne di più. 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Seguire questa procedura per raccogliere la diagnostica:
1.  Connettere il dispositivo con un cavo USB al PC.
2.  In Esplora file nel PC passare a **"questo PC \<hololens-device> \Internal storage"**.
3.  Se la cartella di **archiviazione interna** non viene visualizzata, il dispositivo attende l'accesso di un utente. Eseguire l'accesso o il ciclo di alimentazione del dispositivo tenendo premuto il pulsante di alimentazione per 10 secondi.
4.  Premere e rilasciare immediatamente i pulsanti **Power + Volume Down** insieme.
5.  Attendere un minuto prima che il dispositivo prepari gli archivi zip. Un file temporaneo denominato HololensDiagnostics. Temp può diventare visibile mentre il dispositivo genera gli archivi zip. Non accedere o salvare il file. Al termine del processo verrà sostituito dagli archivi zip.
6.  Aggiornare Esplora file e passare alla cartella **' \Documents '** .
7.  Copiare i file ZIP di diagnostica e condividerli con il team di supporto Microsoft.

> [!NOTE]
> Alcuni file ZIP di diagnostica possono contenere informazioni personali.



