---
title: Gestire gli aggiornamenti di HoloLens
description: Gli amministratori possono usare la gestione dei dispositivi mobili per gestire gli aggiornamenti dei dispositivi HoloLens.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 3a2246296c5ab8aa86dfaa419ed02aa5a961dbfc
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163137"
---
# Gestire gli aggiornamenti di HoloLens

HoloLens usa Windows Update allo stesso modo degli altri dispositivi Windows 10. Quando un aggiornamento è disponibile, viene scaricato e installato automaticamente la volta successiva in cui il dispositivo viene collegato ed è connesso a internet. Questo articolo descrive come gestire gli aggiornamenti in un ambiente aziendale o in altri ambienti gestiti. Per informazioni sulla gestione degli aggiornamenti per i dispositivi HoloLens, vedi[Aggiornamento di HoloLens](hololens-update-hololens.md).

## Gestire automaticamente gli aggiornamenti

### Gestione degli aggiornamenti mediante Windows Update per le aziende

Windows Holographic for Business può usare [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) per gestire gli aggiornamenti. Tutti i dispositivi HoloLens 2 possono usare Windows Holographic for Business. Assicurati che utilizzino la build 10.0.18362.1042 o successiva di Windows Holographic for Business. Se hai dispositivi HoloLens (prima generazione), devi [aggiornarli a Windows Holographic for Business](hololens1-upgrade-enterprise.md) per gestire gli aggiornamenti.

Windows Update for Business connette direttamente i dispositivi HoloLens al servizio Windows Update. Usando Windows Update for Business, puoi controllare più aspetti del processo di aggiornamento,&mdash;ossia i dispositivi, i tipi di aggiornamento e gli orari. Ad esempio, puoi installare gli aggiornamenti su un sottoinsieme di dispositivi per fare un collaudo, e poi, successivamente, installarli sui dispositivi rimanenti. Oppure, puoi definire tabelle di marcia differenti per l’aggiornamento di dispositivi differenti.

> [!NOTE]  
> Per i dispositivi HoloLens,puoi gestire automaticamente gli aggiornamenti delle funzionalità (rilasciati due volte all’anno) e della qualità (rilasciati mensilmente o in base alle esigenze, inclusi gli aggiornamenti critici per la sicurezza). Per maggiori dettagli sui tipi di aggiornamento, vedi [Tipologie di aggiornamento gestite da Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Puoi configurare le impostazioni di Windows Update for Business per HoloLens usando i criteri di una soluzione MDM per la gestione dei dispositivi, come Microsoft Intune.

### Configurazione delle impostazioni di Windows Update for Business con Microsoft Intune.

Per una descrizione dettagliata sull’uso di Intune per configurare Windows Update for business, leggi [Gestire gli aggiornamenti del software Windows 10 con Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure). Per maggiori dettagli sulla funzionalità di Intune specifica supportata da HoloLens, vedi [funzioni di gestione degli aggiornamenti di Intune supportati da HoloLens ](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune offre due tipi di criteri per la gestione degli aggiornamenti: *anello di aggiornamento per Windows 10* e *aggiornamento delle funzionalità per Windows 10*. Al momento, la tipologia “aggiornamento delle funzionalità per Windows 10” è in anteprima, e non è supportata su HoloLens.
>  
> Puoi usare i criteri dell’anello di aggiornamento per Windows 10 per gestire gli aggiornamenti dell’HoloLens 2.

### Configurare i criteri di aggiornamento per HoloLens 2 o HoloLens (prima generazione)

Questa sezione descrive i criteri che puoi usare per gestire gli aggiornamenti di HoloLens 2 o HoloLens (prima generazione). Per maggiori dettagli sulle ulteriori funzionalità disponibili per HoloLens 2, vedi [Pianificare e configurare le installazioni degli aggiornamenti per HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

[Criterio CSP - Aggiornamenti](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) definisce i criteri che consentono di configurare Windows Update for business.

> [!NOTE]  
> Per un elenco di provider di servizi di configurazione di criteri specifici (CSP) supportati da edizioni specifiche di HoloLens, vedi [Criteri CSP supportati dai dispositivi HoloLens](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### Configurare il controllo automatico degli aggiornamenti

Puoi usare il criterio **Update/AllowAutoUpdate** per gestire l’aggiornamento automatico, ad esempio la scansione, lo scaricamento e l’installazione degli aggiornamenti.  Per maggiori dettagli sulle impostazioni disponibili per questo criterio, vedi [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> In Microsoft Intune, puoi usare **Configura aggiornamenti automatici** per modificare questo criterio. Per altre informazioni, vedi [Gestire gli aggiornamenti software Windows 10 in Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### Configurare una pianificazione degli aggiornamenti

Per configurare come e quando saranno applicati gli aggiornamenti, usa questi criteri:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valori: **0**–**7** (0 = ogni giorno, 1 = domenica, 7 = sabato)
  - Valore predefinito: **0** (ogni giorno)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valori: 0–23 (0 = mezzanotte, 23 = 11 PM)
  - Valore predefinito: 3 PM

#### Configurare l'orario di attività.
A partire da [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) un amministratore IT può specificare l'intervallo di ore di attività per i dispositivi HoloLens 2.

L’orario di attività identifica il periodo di tempo durante il quale si prevede che il dispositivo sia in uso. I riavvi automatici dopo un aggiornamento verranno eseguiti al di fuori dell'orario di attività. L'intervallo specificato verrà calcolato dall'ora di inizio dell'orario di attività. È possibile usare MDM, come descritto in [Configurazione dell'orario di attività con MDM](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). MDM usa le impostazioni Update/ActiveHoursStart e Update/ActiveHoursEnd e Update/ActiveHoursMaxRange nel CSP del criterio per configurare le ore di attivà.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) - questo valore imposta l'ora di fine. È disponibile un massimo di 12 ore dall'ora di inizio.
    -   I valori supportati sono 0-23, dove 0 è 12 AM, 1 è 1 AM e così via.
    -   Il valore predefinito è 17 (5 PM).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - questo valore imposta il numero massimo di ore di attività dall'ora di inizio.
    -   I valori supportati sono 8-18.
    -   Il valore predefinito è 18 (ore).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - questo valore imposta l'ora di inizio. C'è un massimo di 12 ore dall'ora di fine.
    -   I valori supportati sono 0-23, dove 0 è 12 AM, 1 è 1 AM e così via.
    -   Il valore predefinito è 8 (8 AM).

#### Solo per i dispositivi che eseguono Windows 10, versione 1607

Puoi usare i seguenti criteri aggiornati per configurare i dispositivi in modo da ricevere aggiornamenti da Windows Server Update Service (WSUS), invece di Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### Pianificare e configurare le installazioni degli aggiornamenti per HoloLens 2

HoloLens 2 supporta più funzionalità di automazione di aggiornamento rispetto a HoloLens (prima generazione). Ciò è specialmente vero se usi Microsoft Intune per gestire i criteri di Windows Update for Business. Queste funzionalità ti consentono di pianificare e implementare più facilmente le installazioni degli aggiornamenti nella tua organizzazione.

#### Pianificare la strategia di aggiornamento

Windows Updates for Business supporta i criteri di posticipazione. Quando Microsoft pubblica un aggiornamento, puoi usare un criterio di posticipazione per definire quanto a lungo attendere prima di installarlo sul dispositivo. Associando sottoinsiemi dei tuoi dispositivi (noti come *anelli di aggiornamento*) a criteri di posticipazione differenti, puoi coordinare la strategia di installazione degli aggiornamenti della tua organizzazione.

Ad esempio, considera un’organizzazione che ha 1.000 dispositivi e deve aggiornarli entro cinque giorni. L’organizzazione può creare cinque anelli di aggiornamento, come mostrato nella tabella seguente.

|Gruppo |Numero di dispositivi |Posticipazione (giorni) |
| ---| :---: | :---: |
|GRP 1 (personale IT) |5 |0 |
|GRP 2 (utenti early adopter) |50 |60 |
|GRP 3 (principale 1) |250 |120 |
|GRP 4 (principale 2) |300 |150 |
|GRP 5 (principale 3) |395 |180 |

Ecco come l'implementazione procede nel corso del tempo per l'intera organizzazione.

![Cronologia dell’installazione degli aggiornamenti](./images/hololens-updates-timeline.png)

#### Configurare un criterio di posticipazione degli aggiornamenti

Un criterio di posticipazione specifica il numero di giorni che intercorrono tra la data in cui un aggiornamento viene reso disponibile e la data in cui viene offerto a una dispositivo.

Puoi configurare posticipazioni differenti per gli aggiornamenti delle funzionalità e gli aggiornamenti per la qualità. Nella seguente tabella sono elencati i criteri specifici da usare per ogni tipo, e la posticipazione massima per ciascuno di essi.

|Categoria |Condizione |Differimento massimo |
| --- | --- | --- |
|Aggiornamenti delle funzionalità |DeferFeatureUpdatesPeriodInDays |365 giorni |
|Aggiornamenti qualitativi |DeferQualityUpdatesPeriodInDays |30 days |

#### Sospendere gli aggiornamenti tramite dispositivo

Se un utente non ha accesso a MDM, può sospendere manualmente gli aggiornamenti per un massimo di 35 giorni su un dispositivo HoloLens 2 nella build [Windows Holographic, versione 2004](hololens-release-notes.md#windows-holographic-version-2004) o successiva. Gli utenti possono raggiungere questa impostazione passando a **Impostazioni -> Aggiornamenti e sicurezza -> Opzioni avanzate** scorrendo verso il basso per **Sospendi aggiornamenti** e selezionando la data in cui verranno sospesi gli aggiornamenti. Una volta che un utente ha raggiunto il limite di sospensione, il dispositivo dovrà ottenere nuovi aggiornamenti per effettuare una nuova sospensione. 

A partire da [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2), la funzione di pausa degli aggiornamenti può essere gestita per i dispositivi HoloLens 2. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (impostazione predefinita) - abilitato
    - 1 - disabilitato

#### Funzioni di gestione degli aggiornamenti di Intune supportate da HoloLens

È possibile usare le seguenti funzioni di gestione degli aggiornamenti di Intune per gestire gli aggiornamenti di HoloLens.

- **Creare** e **Assegnare**: Queste funzioni aggiungono una suoneria di aggiornamento di Windows 10 all'elenco degli anelli di aggiornamento. Per altre informazioni, vedi [Creare e assegnare anelli di aggiornamento](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Sospendere**: Se si verifica un problema durante la distribuzione di una caratteristica o un aggiornamento della qualità, puoi sospendere l'aggiornamento per 35 giorni (a partire da una data specifica). Tale sospensione impedisce di installare l’aggiornamento sugli altri dispositivi, finché non avrai risolto o migrato il problema. Se sospendi un aggiornamento delle funzionalità, gli aggiornamenti per la qualità continuano a essere offerti ai dispositivi per garantire che siano protetti. Quando un tipo di aggiornamento viene sospeso, il riquadro di panoramica dell’anello mostra i giorni residui prima del ripristino dell’aggiornamento.  Una volta trascorso il periodo di tempo specificato, la sospensione scadrà automaticamente e il processo di aggiornamento verrà ripristinato.

  Mentre l’anello di aggiornamento è sospeso, puoi selezionare le seguenti opzioni:

  - **Estendere**: Estende il periodo di sospensione per un tipo di aggiornamento per 35 giorni.
  - **Ripristinare**: Per ripristinare gli aggiornamenti per quell’anello all’operazione attiva. Se necessario, puoi sospendere di nuovo l’anello di aggiornamento.

  > [!NOTE]  
  > L’opzione di **Disinstallazione** degli anelli di aggiornamento non è supportata sui dispositivi HoloLens 2.

## Verificare manualmente gli aggiornamenti

Anche se HoloLens verifica periodicamente gli aggiornamenti di sistema, in alcuni casi potrebbe essere necessario verificarli manualmente.

Per verificare manualmente gli aggiornamenti, vai a **Impostazioni** > **Aggiornamento e Sicurezza** > **Controlla la disponibilità di aggiornamenti**. Se l’app Impostazioni indica che il dispositivo è aggiornato, tutti gli aggiornamenti disponibili sono già installati.

## Eseguire il rollback manuale di un aggiornamento

In alcuni casi, potresti voler ripristinare una versione precedente del software di HoloLens. Il processo è differente per i dispositivi HoloLens 2 e gli HoloLens di prima generazione.

### Ripristinare una versione precedente (HoloLens 2)

Puoi eseguire il roll back degli aggiornamenti e tornare a una versione precedente di HoloLens 2 usando [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) per ripristinare una versione precedente sul tuo HoloLens.

> [!NOTE]
> Il ripristino della versione precedente determina la cancellazione dei file e delle impostazioni personali.

Per ripristinare una versione precedente di HoloLens 2, segui questi passaggi:

1. Assicurati che nessun telefono o dispositivo Windows sia collegato al tuo computer.
1. Sul tuo computer, scarica [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.
1. Scarica la [versione più recente di HoloLens 2](https://aka.ms/hololens2download).
1. Una volta completati questi download, apri **Esplora file** > **Download**, fai clic destro sulla cartella compressa (.zip) che hai appena scaricato, e seleziona **Estrarre tutto** > **Estrarre** per espandere il file.
1. Usa un cavo USB-A / USB-C per collegare il tuo HoloLens al tuo computer. Anche se hai usato altri cavi per collegare il tuo HoloLens, questo tipo di cavo funziona meglio.
1. Advanced Recovery Companion rileva automaticamente il tuo HoloLens. Seleziona il riquadro **Microsoft HoloLens**.
1. Nella schermata successiva, seleziona **Selezione manuale del pacchetto**, e apri la cartella che hai espanso in precedenza.
1. Seleziona il file di installazione (.ffu).
1. Seleziona **Installa software**, e segui le istruzioni.

### Ripristinare una versione precedente (HoloLens (prima generazione))

Puoi eseguire il roll back degli aggiornamenti e tornare a una versione precedente di HoloLens (prima generazione) usando [ Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) per reimpostare una versione precedente del tuo HoloLens.

> [!NOTE]
> Il ripristino della versione precedente di HoloLens determina la cancellazione dei file e delle impostazioni personali.

Per ripristinare una versione precedente di HoloLens (prima generazione), segui questi passaggi:

1. Assicurati che nessun telefono o dispositivo Windows sia collegato al tuo computer.
1. Scarica e installa [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) sul tuo PC.
1. Scarica il pacchetto [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).
1. Una volta completati i download, apri **Esplora file** > **Download**, fai clic destro sulla cartella compressa (.zip) che hai appena scaricato, e seleziona **Estrarre tutto** > **Estrarre** per espandere il file.
1. Usa il cavo micro-USB fornito insieme al tuo HoloLens per collegare l’HoloLens al tuo computer. Anche se hai usato altri cavi per collegare il tuo HoloLens, questo tipo di cavo funziona meglio.
1. Lo strumento WDRT rileva automaticamente il dispositivo HoloLens. Seleziona il riquadro **Microsoft HoloLens**.
1. Nella schermata successiva, seleziona **Selezione manuale del pacchetto**, e apri la cartella che hai espanso in precedenza.
1. Seleziona il file di installazione (.ffu).
1. Seleziona **Installa software**, e segui le istruzioni.

**Se WDRT non rileva il dispositivo**

Se WDRT non rileva l’HoloLens, prova a riavviare il computer. Se il rilevamento non funziona, seleziona **Il mio dispositivo non è stato rilevato**, seleziona poi **Microsoft HoloLens**, e segui le istruzioni.

## Articoli correlati

- [Note sulla versione di HoloLens 2](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Che cos'è Windows Update for Business?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Assegnare i dispositivi ai canali di manutenzione per gli aggiornamenti di Windows10](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gestire gli aggiornamenti del software Windows 10 con Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
