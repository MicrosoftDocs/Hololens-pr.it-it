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
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3de48a913779f124c1cee21791af256a41bf45f8
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828620"
---
# Gestire gli aggiornamenti di HoloLens

HoloLens usa Windows Update allo stesso modo degli altri dispositivi Windows 10. Quando un aggiornamento è disponibile, viene scaricato e installato automaticamente la volta successiva in cui il dispositivo viene collegato ed è connesso a internet. Questo articolo descrive come gestire gli aggiornamenti in un ambiente aziendale o in altri ambienti gestiti. Per informazioni sulla gestione degli aggiornamenti per i dispositivi HoloLens, vedere [Aggiornamento di HoloLens](hololens-update-hololens.md).

## Gestire automaticamente gli aggiornamenti

Windows Holographic for Business può usare [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) per gestire gli aggiornamenti. Tutti i dispositivi HoloLens 2 possono usare Windows Holographic for Business. Assicurati che utilizzino la build 10.0.18362.1042 o successiva di Windows Holographic for Business. Se hai un HoloLens di prima generazione, devi [aggiornarlo a Windows Holographic for Business](hololens1-upgrade-enterprise.md) per gestire gli aggiornamenti.

Windows Update for Business connette direttamente i dispositivi HoloLens al servizio Windows Update. Usando Windows Update for Business, puoi controllare più aspetti del processo di aggiornamento,&mdash;ossia i dispositivi, i tipi di aggiornamento e gli orari. Ad esempio, puoi installare gli aggiornamenti su un sottoinsieme di dispositivi per fare un collaudo, e poi installarli sui dispositivi rimanenenti in seguito. Oppure, puoi definire tabelle di marcia differenti per l’aggiornamento di dispositivi differenti.

> [!NOTE]  
> Puoi gestire automaticamente gli aggiornamenti delle funzionalità (rilasciati due volte all’anno) e gli aggiornamenti per la qualità (rilasciati mensilmente o in base alle esigenze, inclusi gli aggiornamenti critici per la sicurezza) dei dispositivi HoloLens. Per maggiori dettagli sui tipi di aggiornamento, vedi [Tipologie di aggiornamento gestite da Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Puoi configurare le impostazioni di Windows Update for Business per HoloLens usando i criteri di una soluzione MDM per la gestione dei dispositivi, come Microsoft Intune.

Per una descrizione dettagliata sull’uso di Intune per configurare Windows Update for business, leggi [Gestire gli aggiornamenti del software Windows 10 con Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).

> [!IMPORTANT]  
> Intune offre due tipologie di criterio per la gestione degli aggiornamenti: *anello di aggiornamento per Windows 10* e *aggiornamento delle funzionalità per Windows 10*. Al momento, la tipologia “aggiornamento delle funzionalità per Windows 10” è in anteprima, e non è supportata su HoloLens.
>  
> Puoi usare i criteri dell’anello di aggiornamento per Windows 10 per gestire gli aggiornamenti dell’HoloLens 2.

### Configurare i criteri di aggiornamento per HoloLens 2 o HoloLens (prima generazione)

Questa sezione descrive i criteri che puoi usare per gestire gli aggiornamenti di HoloLens 2 o HoloLens (prima generazione). Per informazioni sulle ulteriori funzionalità disponibili per HoloLens 2, vedi [Pianificare e configurare le installazioni degli aggiornamenti per HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

Il [provider di servizi di configurazione (CSP) dei criteri](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) definisce i criteri di configurazione di Windows Update for Business.

> [!NOTE]  
> Per i dettagli degli specifici criteri supportati per edizioni specifiche di HoloLens, leggi [Criteri supportati dai dispositivi HoloLens](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices).

#### Configurare il controllo automatico degli aggiornamenti

Puoi usare il criterio **Update/AllowAutoUpdate** per gestire l’aggiornamento automatico, ad esempio la scansione, lo scaricamento e l’installazione degli aggiornamenti. 

Questo criterio supporta i seguenti valori:

- **0** - L’utente viene notificato quando degli aggiornamenti per il dispositivo sono disponibili per lo scaricamento.
- **1** - L’aggiornamento viene installato automaticamente, e l’utente viene avvertito di pianificare il riavvio del dispositivo.   
- **2** - L’aggiornamento è installato automaticamente, e il dispositivo si riavvia da solo. Questo è il valore raccomandato, ed è il valore predefinito per questo criterio.  

- **3** - L’aggiornamento viene installato automaticamente, e il riavvio viene eseguito in seguito. Bisogna specifica il giorno e l’ora dell’installazione. Se il giorno e l’ora non sono specificati, il valore predefinito è ogni giorno alle 3:00.   

- **4** - L’aggiornamento viene installato automaticamente, e il dispositivo si riavvia da solo. Questa opzione configura la pagina delle Impostazioni come “solo lettura”.

- **5** - Disattiva gli aggiornamenti automatici.

Per maggiori dettagli sulle impostazioni di questo criterio, vedi [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> In Microsoft Intune, puoi usare **Configura aggiornamenti automatici** per modificare questo criterio. Per altre informazioni, vedi [Gestire gli aggiornamenti del software con Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### Configurare una pianificazione degli aggiornamenti

Per configurare come e quando saranno applicati gli aggiornamenti, usa questi criteri:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).  
   - Valori: **0**–**7** (0 = ogni giorno, 1 = domenica, 7 = sabato)
   - Valore predefinito: **0** (ogni giorno)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).
   - Valori: 0–23 (0 = mezzanotte, 23 = 23:00)
   - Valore predefinito: 15:00

#### Solo per i dispositivi che eseguono Windows 10, versione 1607

Puoi usare i seguenti criteri per configurare i dispositivi in modo da ricevere gli aggiornamenti da Windows Server Update Service (WSUS), invece di Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### Pianificare e configurare le installazioni degli aggiornamenti per HoloLens 2

HoloLens offre più funzionalità di automazione degli aggiornamenti dell’HoloLens di prima generazione. Ciò è specialmente vero se usi Microsoft Intune per gestire i criteri di Windows Update for Business. Queste funzionalità ti consentono di pianificare e implementare più facilmente le installazioni degli aggiornamenti nella tua organizzazione.

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

Ecco come l’aggiornamento viene implementazione nell’organizzazione nel corso del tempo.

![Cronologia dell’installazione degli aggiornamenti](./images/hololens-updates-timeline.png)

#### Configurare un criterio di posticipazione degli aggiornamenti

Un criterio di posticipazione specifica il numero di giorni che intercorrono tra la data in cui un aggiornamento viene reso disponibile e la data in cui viene offerto a una dispositivo.

Puoi configurare posticipazioni differenti per gli aggiornamenti delle funzionalità e gli aggiornamenti per la qualità. Nella tabella seguente trovi i criteri specifici da usare ogni tipologia, e la posticipazione massima per ciascuno.

|Categoria |Condizione |Differimento massimo |
| --- | --- | --- |
|Aggiornamenti delle funzionalità |DeferFeatureUpdatesPeriodInDays |365 giorni |
|Aggiornamenti qualitativi |DeferQualityUpdatesPeriodInDays |30 days |

####  Esempi: Usare Intune per gestire gli aggiornamenti

**Esempio 1: Creare e assegnare una anello di aggiornamento**

Per una versione più dettagliata di questo esempio, vedi [Creare e assegnare anelli di aggiornamento](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

1. Autenticati su [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), e naviga fino ai tuoi profili Intune.
1. Seleziona **Aggiornamenti software** > **Anelli di aggiornamento per Windows 10** > **Crea**.
1. In **Dati principali**, specifica un nome e una descrizione (facoltativa) e seleziona **Avanti**.
1. In **Impostazioni anello di aggiornamento**, per il **Canale di manutenzione**, seleziona **Canale semiannuale**, e modifica poi il valore del **Periodo di posticipazione dell’aggiornamento delle funzionalità** su **120**. Seleziona poi **Avanti**.
1. In **Assegnazioni**, seleziona **+ Seleziona gruppi da includere**, e quindi assegna l’anello di aggiornamento a uno o più gruppi. Usa **+ Seleziona gruppi da escludere** per finalizzare le assegnazioni. Seleziona poi **Avanti**.
1. In **Rivedi + crea**, riesamina le impostazioni. Quando sei pronto a salvare la configurazione dell’anello di aggiornamento, seleziona **Crea**.

Ora l’elenco degli anelli di aggiornamento include il nuovo anello di aggiornamento per Windows 10.

**Esempio 2: Sospendere un anello di aggiornamento**

Se riscontri dei problemi quando distribuisci aggiornamenti delle funzionalità o per la qualità, puoi sospendere l’aggiornamento per 35 giorni (a partire da una data specifica). Tale sospensione impedisce di installare l’aggiornamento sugli altri dispositivi, finché avrai risolto o migrato il problema. Se sospendi un aggiornamento delle funzionalità, gli aggiornamenti per la qualità continuano a essere offerti ai dispositivi per garantire che siano protetti. La sospensione scade automaticamente al termine del periodo specificato. A quel punto, il processo di aggiornamento riprende.

Per sospendere un anello di aggiornamento in Intune, segui questi passaggi:

1. Nella panoramica dell’anello di aggiornamento, seleziona **Sospendi**.
1. Seleziona il tipo di aggiornamento (**Funzionalità** o **Qualità**) da sospendere, e clicca poi su **OK**.

Quando un tipo di aggiornamento viene sospeso, il riquadro di panoramica dell’anello mostra i giorni residui prima del ripristino dell’aggiornamento. 

Mentre l’anello di aggiornamento è sospeso, puoi selezionare le seguenti opzioni:

- Per estendere il periodo di sospensione per un tipo di aggiornamento per 35 giorni, seleziona **Estendi**.
- Per ripristinare gli aggiornamenti di un anello, seleziona **Ricomincia**. Se necessario, puoi sospendere di nuovo l’anello di aggiornamento.

> [!NOTE]  
> L’opzione di **Disinstallazione** degli anelli di aggiornamento non è supportata sui dispositivi HoloLens 2.

## Verificare manualmente gli aggiornamenti

Anche se HoloLens verifica periodicamente gli aggiornamenti di sistema al posto tuo, in alcuni casi potrebbe essere necessario verificarli manualmente.

Per verificare manualmente gli aggiornamenti, vai a **Impostazioni** > **Aggiornamento e Sicurezza** > **Controlla la disponibilità di aggiornamenti**. Se l’app Impostazioni indica che il dispositivo è aggiornato, tutti gli aggiornamenti disponibili sono già installati.

## Disinstallare manualmente un aggiornamento

In alcuni casi, potresti voler tornare a una versione precedente del software di HoloLens. Il processo è differente per i dispositivi HoloLens 2 e gli HoloLens di prima generazione.

### Ripristinare una versione precedente (HoloLens 2)

Puoi disinstallare gli aggiornamenti e tornare a una versione precedente di HoloLens 2 usando Advanced Recovery Companion per ripristinare una versione precedente sul tuo HoloLens.

> [!NOTE]
> Il ripristino della versione precedente determina la cancellazione dei file e delle impostazioni personali.

Per tornare una versione precedente di HoloLens 2, segui questi passaggi:

1. Assicurati che nessun telefono o dispositivo Windows sia collegato al tuo computer.
1. Sul tuo computer, scarica [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.
1. Scarica la [versione più recente di HoloLens 2](https://aka.ms/hololens2download).
1. Una volta completati questi scaricamenti, apri **Esplora file** > **Download**, fai clic destro sulla cartella compressa (.ZIP) che hai appena scaricato, e seleziona **Estrai tutto** > **Estrai** espandere il file.
1. Usa un cavo USB-A / USB-C per collegare il tuo HoloLens al tuo computer. Anche se hai usato altri cavi per collegare il tuo HoloLens, questo tipo di cavo funziona meglio.
1. Advanced Recovery Companion rileva automaticamente il tuo HoloLens. Seleziona il riquadro **Microsoft HoloLens**.
1. Nella schermata successiva, seleziona **Selezione manuale del pacchetto**, e apri la cartella che hai espanso in precedenza. 
1. Seleziona il file di installazione (quello con l’estensione .ffu).
1. Seleziona **Installa software**, e segui le istruzioni.

### Ripristinare una versione precedente (HoloLens di prima generazione)

Puoi disinstallare gli aggiornamenti e tornare a una versione precedente di HoloLens (prima generazione) usando Windows Device Recovery Tool per ripristinare una versione precedente sul tuo HoloLens.

> [!NOTE]
> Il ripristino della versione precedente determina la cancellazione dei file e delle impostazioni personali.

Per tornare una versione precedente di HoloLens (prima generazione), segui questi passaggi:

1. Assicurati che nessun telefono o dispositivo Windows sia collegato al tuo computer.
1. Scarica e installa [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) sul tuo PC.
1. Scarica il pacchetto [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).
1. Una volta completati gli scaricamenti, apri **Esplora file** > **Download**, fai clic destro sulla cartella compressa (.ZIP) che hai appena scaricato, e seleziona **Estrai tutto** > **Estrai** per espandere il file.
1. Usa il cavo micro-USB fornito insieme al tuo HoloLens per collegare l’HoloLens al tuo computer. Anche se hai usato altri cavi per collegare il tuo HoloLens, questo tipo di cavo funziona meglio.
1. Lo strumento WDRT rileva automaticamente il dispositivo HoloLens. Seleziona il riquadro **Microsoft HoloLens**.
1. Nella schermata successiva, seleziona **Selezione manuale del pacchetto**, e apri la cartella che hai espanso in precedenza. 
1. Seleziona il file di installazione (quello con l’estensione .ffu).
1. Seleziona **Installa software**, e segui le istruzioni.

> [!NOTE]
> Se WDRT non rileva l’HoloLens, prova a riavviare il computer. Se il rilevamento non funziona, seleziona **Il mio dispositivo non è stato rilevato**, seleziona poi **Microsoft HoloLens**, e segui le istruzioni.

## Articoli correlati

- [Distribuire gli aggiornamenti mediante Windows Update per le aziende](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Assegnare i dispositivi ai canali di manutenzione per gli aggiornamenti di Windows10](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gestire gli aggiornamenti del software Windows 10 con Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
