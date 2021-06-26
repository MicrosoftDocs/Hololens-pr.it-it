---
title: Gestire gli aggiornamenti di HoloLens
description: Informazioni su come gli amministratori possono usare la gestione dei dispositivi mobili per gestire gli aggiornamenti ai dispositivi HoloLens.
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: faa6bb2b095d69c3538063b1c042c5ce5e215d33
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924078"
---
# <a name="manage-hololens-updates"></a>Gestire gli aggiornamenti di HoloLens

HoloLens usa Windows Update come altri dispositivi Windows 10 dispositivi. Quando un aggiornamento è disponibile, viene scaricato e installato automaticamente la volta successiva che il dispositivo viene collegato e connesso a Internet. Questo articolo descrive come gestire gli aggiornamenti in un ambiente aziendale o in un altro ambiente gestito. Per informazioni su come gestire gli aggiornamenti ai singoli dispositivi HoloLens, vedere [Aggiornare HoloLens.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Gestire automaticamente gli aggiornamenti

### <a name="managing-updates-by-using-windows-update-for-business"></a>Gestione degli aggiornamenti tramite Windows Update per le aziende

Windows Holographic for Business possibile [usare](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) Windows Update per le aziende per gestire gli aggiornamenti. Tutti HoloLens 2 dispositivi possono usare Windows Holographic for Business. Assicurarsi che usino Windows Holographic for Business build 10.0.18362.1042 o successiva. Se si hanno dispositivi HoloLens (prima generazione), è necessario aggiornarli a Windows Holographic for Business [per](hololens1-upgrade-enterprise.md) gestire gli aggiornamenti.

Windows Update per le aziende connette i dispositivi HoloLens direttamente al Windows Update servizio. Usando Windows Update per le aziende, è possibile controllare più aspetti del processo di aggiornamento, ovvero quali dispositivi ottengono &mdash; gli aggiornamenti in quale momento. Ad esempio, è possibile implementare gli aggiornamenti in un subset di dispositivi per il test, quindi successivamente implementare gli aggiornamenti per i dispositivi rimanenti. In caso contrario, è possibile definire pianificazioni di aggiornamento diverse per diversi tipi di aggiornamenti.

> [!NOTE]  
> Per i dispositivi HoloLens, è possibile gestire automaticamente gli aggiornamenti delle funzionalità (rilasciati due volte all'anno) e gli aggiornamenti qualitativi (rilasciati mensilmente o in base alle esigenze, inclusi gli aggiornamenti critici della sicurezza). Per altre informazioni sui tipi di aggiornamento, vedere [Tipi di aggiornamenti gestiti da Windows Update per le aziende](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

È possibile configurare Windows Update per le aziende per HoloLens usando i criteri in una soluzione di gestione dei dispositivi mobili (MDM), ad esempio Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Gestione Windows Update per le aziende tramite Microsoft Intune

Per una discussione dettagliata su come usare Intune per configurare Windows Update per le aziende, vedere Gestire gli aggiornamenti software Windows 10 [in Intune.](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure) Per altre informazioni sulle funzionalità specifiche di Intune supportate da HoloLens, vedere Funzioni di gestione degli aggiornamenti di Intune supportate da [HoloLens.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> Intune offre due tipi di criteri per la gestione degli aggiornamenti: *Windows 10'anello* di aggiornamento *e Windows 10 funzionalità di aggiornamento.* Il Windows 10 di criteri di aggiornamento delle funzionalità è attualmente in anteprima pubblica e non è supportato per HoloLens.
>  
> È possibile usare i Windows 10 degli anelli di aggiornamento per gestire HoloLens 2 aggiornamenti.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Configurare i criteri di aggiornamento HoloLens 2 o HoloLens (prima generazione)

Questa sezione descrive i criteri che è possibile usare per gestire gli aggiornamenti per HoloLens 2 o HoloLens (prima generazione). Per altre informazioni sulle funzionalità disponibili per HoloLens 2, vedere Pianificare e configurare le implementazioni degli aggiornamenti [per](#plan-and-configure-update-rollouts-for-hololens-2)HoloLens 2 .

Provider di servizi di configurazione dei [criteri: l'aggiornamento](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) definisce i criteri che configurano Windows Update per le aziende.

> [!NOTE]  
> Per un elenco di provider di servizi di configurazione dei criteri (CSP) specifici supportati da edizioni specifiche di HoloLens, vedere Provider di servizi di configurazione dei criteri supportati dai [dispositivi HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)

#### <a name="configure-automatic-checks-for-updates"></a>Configurare i controlli automatici per gli aggiornamenti

È possibile usare i **criteri Update/AllowAutoUpdate** per gestire il comportamento degli aggiornamenti automatici, ad esempio l'analisi, il download e l'installazione degli aggiornamenti. Per altre informazioni sulle impostazioni disponibili per questo criterio, vedere [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> In Microsoft Intune, è possibile usare **il comportamento di aggiornamento automatico** per modificare questo criterio. Per altre informazioni, vedere [Gestire gli Windows 10 software in Intune.](https://docs.microsoft.com/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Configurare una pianificazione degli aggiornamenti

Per configurare come e quando vengono applicati gli aggiornamenti, usare i criteri seguenti:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valori: **0**-**7** (0 = ogni giorno, 1 = domenica, 7 = sabato)
  - Valore predefinito: **0** (ogni giorno)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valori: 0-23 (0 = mezzanotte, 23 = 11 PM)
  - Valore predefinito: 3 AM

#### <a name="configure-active-hours"></a>Configurare l'orario di attività.
A partire [da Windows Holographic, versione 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) un amministratore IT può specificare l'intervallo di ore attive per HoloLens 2 dispositivi.

L'orario di attività identifica il periodo di tempo durante il quale prevedi che il dispositivo sia uso. I riavvi automatici dopo un aggiornamento verranno eseguiti al di fuori dell'orario di attività. L'intervallo specificato verrà conteggiato dall'ora di inizio delle ore attive. È possibile usare MDM, come descritto in [Configurazione degli orari di attività con MDM.](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) MDM usa le impostazioni Update/ActiveHoursStart e Update/ActiveHoursEnd e Update/ActiveHoursMaxRange in Policy CSP per configurare le ore attive.

-   [Update/ActiveHoursEnd:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) questo valore imposta l'ora di fine. È presente un massimo di 12 ore dall'ora di inizio.
    -   I valori supportati sono 0-23, dove 0 è 12 AM, 1 è 1 AM e così via.
    -   Il valore predefinito è 17 (17:00).
-   [Update/ActiveHoursMaxRange:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) questo valore imposta il numero massimo di ore attive dall'ora di inizio.
    -   I valori supportati sono da 8 a 18.
    -   Il valore predefinito è 18 (ore).
-   [Update/ActiveHoursStart:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) questo valore imposta l'ora di inizio. È presente un massimo di 12 ore dall'ora di fine.
    -   I valori supportati sono 0-23, dove 0 è 12 AM, 1 è 1 AM e così via.
    -   Il valore predefinito è 8 (8 AM).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Per i dispositivi che eseguono Windows 10, solo versione 1607

È possibile usare i criteri di aggiornamento seguenti per configurare i dispositivi per ottenere gli aggiornamenti da Windows Server Update Service (WSUS), anziché da Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Pianificare e configurare le implementazioni degli aggiornamenti per HoloLens 2

HoloLens 2 supporta più funzionalità di automazione degli aggiornamenti rispetto a HoloLens (prima generazione). Ciò è particolarmente vero se si usa Microsoft Intune per gestire i Windows Update per le aziende criteri. Queste funzionalità semplificano la pianificazione e l'implementazione delle implementazioni degli aggiornamenti nell'organizzazione.

#### <a name="plan-the-update-strategy"></a>Pianificare la strategia di aggiornamento

Gli aggiornamenti di Windows per le aziende supportano i criteri di rinvio. Dopo che Microsoft ha rilasciato un aggiornamento, è possibile usare un criterio di rinvio per definire il tempo di attesa prima di installare l'aggiornamento nei dispositivi. Associando subset dei dispositivi (noti anche come anelli di *aggiornamento)* a criteri di rinvio diversi, è possibile coordinare una strategia di implementazione degli aggiornamenti per l'organizzazione.

Si consideri ad esempio un'organizzazione con 1.000 dispositivi e deve aggiornare i dispositivi in cinque onde. L'organizzazione può creare cinque anelli di aggiornamento, come illustrato nella tabella seguente.

|Gruppo |Number of devices (Numero di dispositivi) |Rinvio (giorni) |
| ---| :---: | :---: |
|Grp 1 (personale IT) |5 |0 |
|Grp 2 (early adopters) |50 |60 |
|Grp 3 (principale 1) |250 |120 |
|Grp 4 (principale 2) |300 |150 |
|Grp 5 (principale 3) |395 |180 |

Ecco come procede l'implementazione nel tempo per l'intera organizzazione.

![Sequenza temporale per la distribuzione degli aggiornamenti](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Configurare un criterio di rinvio degli aggiornamenti

Un criterio di rinvio specifica il numero di giorni tra la data in cui un aggiornamento diventa disponibile e la data in cui l'aggiornamento viene offerto a un dispositivo.

È possibile configurare differimenti diversi per gli aggiornamenti delle funzionalità e gli aggiornamenti qualitativi. Nella tabella seguente sono elencati i criteri specifici da usare per ogni tipo e il rinvio massimo per ognuno.

|Category |Criteri |Differimento massimo |
| --- | --- | --- |
|Aggiornamenti delle funzionalità |DeferFeatureUpdatesPeriodInDays |365 giorni |
|Aggiornamenti qualitativi |DeferQualityUpdatesPeriodInDays |30 giorni |

#### <a name="pause-updates-via-device"></a>Sospendere gli aggiornamenti tramite il dispositivo

Se un utente non ha accesso a MDM, può sospendere singolarmente gli aggiornamenti per un massimo di 35 giorni manualmente in un dispositivo HoloLens 2 nella build [Windows Holographic, versione 2004](hololens-release-notes.md#windows-holographic-version-2004) o successiva. Gli utenti possono raggiungere questa impostazione passando a Impostazioni **> Aggiorna & Sicurezza >** Opzioni  avanzate scorrere verso il basso fino a Sospendi aggiornamenti e selezionare la data fino alla quale sospenderanno gli aggiornamenti. Quando un utente ha raggiunto il limite di sospensione, il dispositivo dovrà ottenere nuovi aggiornamenti prima di poterlo sospendere di nuovo. 

A partire [da Windows Holographic versione 20H2,](hololens-release-notes.md#windows-holographic-version-20h2)questa funzione di sospensione degli aggiornamenti può essere gestita per HoloLens 2 dispositivi. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (impostazione predefinita): abilitata
    - 1 : disabilitato

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funzioni di gestione degli aggiornamenti di Intune supportate da HoloLens

È possibile usare le funzioni di gestione degli aggiornamenti di Intune seguenti per gestire gli aggiornamenti per HoloLens.

- **Crea** e **assegna:** queste funzioni aggiungono un Windows 10 di aggiornamento all'elenco degli anelli di aggiornamento. Per altre informazioni, vedere [Creare e assegnare anelli di aggiornamento.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- Sospendi: se si verifica un problema quando si distribuisce un aggiornamento qualitativo o di funzionalità, è possibile sospendere l'aggiornamento per 35 giorni (a partire da una data specificata). Questa pausa impedisce ad altri dispositivi di installare l'aggiornamento fino a quando non si risolve o si attenua il problema. Se si sospende un aggiornamento delle funzionalità, gli aggiornamenti qualitativi vengono comunque offerti ai dispositivi per garantire la sicurezza. Quando un tipo di aggiornamento viene sospeso, il riquadro Panoramica per tale anello mostra il numero di giorni che devono trascorrere prima del ripristino del tipo di aggiornamento. Dopo che è trascorsa l'ora specificata, la pausa scade automaticamente e il processo di aggiornamento riprende.

  Mentre l'anello di aggiornamento è in pausa, è possibile selezionare una delle opzioni seguenti:

  - **Estensione:** estendere il periodo di pausa per un tipo di aggiornamento per 35 giorni.
  - **Riprendi:** ripristina l'operazione attiva degli aggiornamenti per l'anello. Se necessario, è possibile sospendere nuovamente l'anello di aggiornamento.

  > [!NOTE]  
  > **L'operazione** di disinstallazione per gli anelli di aggiornamento non è supportata per HoloLens 2 dispositivi.

### <a name="delivery-optimization-preview"></a>Ottimizzazione recapito anteprima

[Windows Holographic versione 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ha abilitato un'anteprima anticipata per le impostazioni di ottimizzazione recapito per ridurre il consumo di larghezza di banda per i download da più dispositivi HoloLens. Una descrizione più completa di questa funzionalità insieme alla configurazione di rete consigliata è disponibile qui: Ottimizzazione recapito [per Windows 10 aggiornamenti](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Le impostazioni seguenti sono abilitate come parte dell'area di gestione e [possono essere configurate da Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Alcune avvertenze su questa offerta di anteprima:

- Il supporto di HoloLens è limitato in questa anteprima solo agli aggiornamenti del sistema operativo.
- Windows Holographic for Business supporta solo le modalità di download HTTP e i download da un [endpoint cache connessa Microsoft](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); Le modalità di download peer-to-peer e le assegnazioni di gruppo non sono attualmente supportate per i dispositivi HoloLens.
- HoloLens non supporta l'ottimizzazione della distribuzione o del recapito Windows Server Update Services endpoint.
- La risoluzione dei problemi richiederà la diagnostica nel server cache connessa o la raccolta di una traccia in HoloLens in HoloLens tramite l'aggiornamento delle impostazioni & risoluzione dei problemi di  >    >     >   **sicurezza Windows Update**.

## <a name="manually-check-for-updates"></a>Controllare manualmente la disponibilità di aggiornamenti

Anche se HoloLens controlla periodicamente la disponibilità di aggiornamenti del sistema, in alcune circostanze è possibile che si voglia controllare manualmente.

Per verificare manualmente la disponibilità di aggiornamenti, passare a **Impostazioni**  >  **Aggiornamento & sicurezza** per gli  >  **aggiornamenti**. Se l'app Impostazioni indica che il dispositivo è aggiornato, sono disponibili tutti gli aggiornamenti.

## <a name="manually-roll-back-an-update"></a>Eseguire manualmente il rollback di un aggiornamento

In alcuni casi, potrebbe essere necessario ripristinare una versione precedente del software HoloLens. Il processo per eseguire questa operazione varia a seconda che si stia usando HoloLens 2 o HoloLens (prima generazione).

### <a name="revert-to-a-previous-version-hololens-2"></a>Ripristinare una versione precedente (HoloLens 2)

Puoi eseguire il rollback degli aggiornamenti e tornare a una versione precedente di HoloLens 2 usando [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) per ripristinare holoLens alla versione precedente.

> [!NOTE]
> Il ripristino di una versione precedente elimina i file e le impostazioni personali.

Per ripristinare una versione precedente di HoloLens 2, seguire questa procedura:

1. Assicurarsi di non avere telefoni o dispositivi Windows collegati al computer.
1. Nel computer scaricare [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dal Microsoft Store.
1. Scaricare la [versione più HoloLens 2 recente.](https://aka.ms/hololens2download)
1. Al termine di questi download, aprire Download di Esplora file, fare clic con il pulsante destro del mouse sulla cartella compressa (.zip) appena scaricata e quindi scegliere Estrai tutto per espandere il  >     >   file.
1. Usare un cavo da USB-A a USB-C per connettere il dispositivo HoloLens al computer. Anche se hai già utilizzato altri cavi per connettere HoloLens, questo tipo di cavo funziona meglio.
1. Advanced Recovery Companion rileva automaticamente il dispositivo HoloLens. Selezionare il **Microsoft HoloLens** riquadro.
1. Nella schermata successiva selezionare **Selezione manuale del pacchetto** e quindi aprire la cartella espansa in precedenza.
1. Selezionare il file di installazione (con estensione ffu).
1. Selezionare **Installa software** e quindi seguire le istruzioni.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Ripristinare una versione precedente (HoloLens (prima generazione))

Puoi eseguire il rollback degli aggiornamenti e tornare a una versione precedente di HoloLens (prima generazione) usando lo strumento ripristino dispositivi di [Windows (WDRT)](https://support.microsoft.com/help/12379) per ripristinare holoLens alla versione precedente.

> [!NOTE]
> Il ripristino di una versione precedente di HoloLens elimina i file e le impostazioni personali.

Per ripristinare una versione precedente di HoloLens (prima generazione), segui questa procedura:

1. Assicurarsi che nel computer non siano collegati telefoni o dispositivi Windows.
1. Nel computer scaricare Windows [Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Scaricare il [pacchetto di ripristino dell'aggiornamento dell'anniversario di HoloLens.](https://aka.ms/hololensrecovery)
1. Al termine dei download, aprire Download di Esplora file, fare clic con il pulsante destro del mouse sulla cartella compressa (.zip) appena scaricata e quindi scegliere Estrai tutto per espandere il  >     >   file.
1. Usa il cavo micro-USB fornito con il dispositivo HoloLens per connettere il dispositivo HoloLens al computer. Anche se si usano altri cavi per connettere il dispositivo HoloLens, questo funziona meglio.
1. WDRT rileva automaticamente il dispositivo HoloLens. Selezionare il **Microsoft HoloLens** riquadro.
1. Nella schermata successiva selezionare **Selezione manuale del pacchetto** e quindi aprire la cartella espansa in precedenza.
1. Selezionare il file di installazione (con estensione ffu).
1. Selezionare **Installa software** e quindi seguire le istruzioni.

**Se WDRT non rileva il dispositivo**

Se WDRT non rileva il dispositivo HoloLens, provare a riavviare il computer. Se il problema non funziona, selezionare **Il dispositivo non** è stato rilevato, selezionare **Microsoft HoloLens** e quindi seguire le istruzioni.

## <a name="related-articles"></a>Articoli correlati

- [HoloLens 2 sulla versione](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Che cos'Windows Update per le aziende?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Assegnare dispositivi ai canali di manutenzione per Windows 10 aggiornamenti](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
