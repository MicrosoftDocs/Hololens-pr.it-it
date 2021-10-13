---
title: Gestire HoloLens aggiornamenti
description: Informazioni su come gli amministratori possono usare la gestione dei dispositivi mobili per gestire gli aggiornamenti HoloLens dispositivi mobili.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/12/2021
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
ms.openlocfilehash: 854e867238de6c87732970fba75abdc8e1fb2c64
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924340"
---
# <a name="manage-hololens-updates"></a>Gestire HoloLens aggiornamenti

HoloLens usa Windows'aggiornamento nello stesso modo di altri Windows 10 dispositivi. Quando un aggiornamento è disponibile, viene scaricato e installato automaticamente la volta successiva che il dispositivo viene collegato e connesso a Internet. Questo articolo descrive come gestire gli aggiornamenti in un ambiente aziendale o in un altro ambiente gestito. Per informazioni su come gestire gli aggiornamenti ai singoli HoloLens, vedere [Aggiornamento HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Gestire automaticamente gli aggiornamenti

### <a name="managing-updates-by-using-windows-update-for-business"></a>Gestione degli aggiornamenti tramite Windows Update for Business

Windows Holographic for Business possibile usare Windows [Update for Business per](/windows/deployment/update/waas-manage-updates-wufb) gestire gli aggiornamenti. Tutti HoloLens 2 dispositivi possono usare Windows Holographic for Business. Assicurarsi che usino Windows Holographic for Business build 10.0.18362.1042 o successiva. Se si dispone di HoloLens (prima generazione), è [](hololens1-upgrade-enterprise.md) necessario aggiornarli a Windows Holographic for Business per gestire gli aggiornamenti.

Windows Update for Business connette HoloLens dispositivi direttamente al Windows Update. Usando Windows Update for Business, è possibile controllare più aspetti del processo di aggiornamento, ovvero quali dispositivi ottengono gli &mdash; aggiornamenti in quale momento. Ad esempio, è possibile implementare gli aggiornamenti in un subset di dispositivi per il test, quindi successivamente implementare gli aggiornamenti per i dispositivi rimanenti. In caso contrario, è possibile definire pianificazioni di aggiornamento diverse per diversi tipi di aggiornamenti.

> [!NOTE]  
> Per HoloLens dispositivi, è possibile gestire automaticamente gli aggiornamenti delle funzionalità (rilasciati due volte all'anno) e gli aggiornamenti qualitativi (rilasciati mensilmente o in base alle esigenze, inclusi gli aggiornamenti critici della sicurezza). Per altre informazioni sui tipi di aggiornamento, vedere [Tipi di aggiornamenti gestiti da Windows Update for Business.](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)

È possibile configurare Windows impostazioni di Update for Business per HoloLens usando criteri in una soluzione di gestione di dispositivi mobili (MDM), ad esempio Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Gestione Windows Update for Business tramite Microsoft Intune

Per una discussione dettagliata su come usare Intune per configurare Windows Update for Business, vedere Gestire gli aggiornamenti software Windows 10 [in Intune.](/intune/protect/windows-update-for-business-configure) Per altre informazioni sulle funzionalità specifiche di Intune supportate da HoloLens, vedere Funzioni di gestione degli aggiornamenti di [Intune HoloLens supporta](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune offre due tipi di criteri per la gestione degli aggiornamenti: *Windows 10'anello* di aggiornamento e Windows 10 *funzionalità.* Il Windows 10 di criteri di aggiornamento delle funzionalità è attualmente in anteprima pubblica e non è supportato per HoloLens.
>  
> È possibile usare i Windows 10 degli anelli di aggiornamento per gestire HoloLens 2 aggiornamenti.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Configurare i criteri di aggiornamento HoloLens 2 o HoloLens (prima generazione)

Questa sezione descrive i criteri che è possibile usare per gestire gli aggiornamenti per HoloLens 2 o HoloLens (prima generazione). Per altre informazioni sulle funzionalità disponibili per HoloLens 2, vedere Pianificare e configurare le implementazioni degli aggiornamenti [per](#plan-and-configure-update-rollouts-for-hololens-2)HoloLens 2 .

[Policy CSP : Update](/windows/client-management/mdm/policy-csp-update) definisce i criteri che configurano Windows Update for Business.

> [!NOTE]  
> Per un elenco di provider di servizi di configurazione dei criteri (CSP) specifici supportati da edizioni specifiche di HoloLens, vedere Provider di servizi di configurazione dei criteri supportati da HoloLens [dispositivi](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Configurare i controlli automatici per gli aggiornamenti

È possibile usare i **criteri Update/AllowAutoUpdate** per gestire il comportamento degli aggiornamenti automatici, ad esempio l'analisi, il download e l'installazione degli aggiornamenti. Per altre informazioni sulle impostazioni disponibili per questo criterio, vedere [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> In Microsoft Intune, è possibile usare **il comportamento di aggiornamento automatico** per modificare questo criterio. Per altre informazioni, vedere [Gestire gli Windows 10 software in Intune.](/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Configurare una pianificazione degli aggiornamenti

Per configurare come e quando vengono applicati gli aggiornamenti, usare i criteri seguenti:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valori: **0**-**7** (0 = ogni giorno, 1 = domenica, 7 = sabato)
  - Valore predefinito: **0** (ogni giorno)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valori: 0-23 (0 = mezzanotte, 23 = 11 PM)
  - Valore predefinito: 3 AM

#### <a name="configure-active-hours"></a>Configurare l'orario di attività.
A partire [da Windows Holographic, la versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) di un amministratore IT può specificare l'intervallo di ore attive per HoloLens 2 dispositivi.

L'orario di attività identifica il periodo di tempo durante il quale prevedi che il dispositivo sia uso. I riavvi automatici dopo un aggiornamento verranno eseguiti al di fuori dell'orario di attività. L'intervallo specificato verrà conteggiato dall'ora di inizio delle ore attive. È possibile usare MDM, come descritto in [Configurazione degli orari di attività con MDM.](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) MDM usa le impostazioni Update/ActiveHoursStart e Update/ActiveHoursEnd e Update/ActiveHoursMaxRange in Policy CSP per configurare le ore attive.

-   [Update/ActiveHoursEnd:](/windows/client-management/mdm/policy-csp-update#update-activehoursend) questo valore imposta l'ora di fine. È presente un massimo di 12 ore dall'ora di inizio.
    -   I valori supportati sono 0-23, dove 0 è 12 AM, 1 è 1 AM e così via.
    -   Il valore predefinito è 17 (17:00).
-   [Update/ActiveHoursMaxRange:](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) questo valore imposta il numero massimo di ore attive dall'ora di inizio.
    -   I valori supportati sono da 8 a 18.
    -   Il valore predefinito è 18 (ore).
-   [Update/ActiveHoursStart:](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) questo valore imposta l'ora di inizio. È presente un massimo di 12 ore dall'ora di fine.
    -   I valori supportati sono 0-23, dove 0 è 12 AM, 1 è 1 AM e così via.
    -   Il valore predefinito è 8 (8 AM).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Per i dispositivi che eseguono Windows 10, solo versione 1607

È possibile usare i criteri di aggiornamento seguenti per configurare i dispositivi per ottenere gli aggiornamenti da Windows Server Update Service (WSUS), anziché da Windows Update:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

#### <a name="improved-update-restart-detection-and-notifications"></a>Rilevamento e notifiche del riavvio degli aggiornamenti migliorati

- Introdotto in [Windows Holographic, versione 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Tra l'orario di attività e i criteri di tempo di installazione, è possibile evitare il riavvio HoloLens dispositivi quando sono in uso. Tuttavia, potrebbe anche ritardare l'adozione degli aggiornamenti se non si verificano riavvii per completare l'installazione di un aggiornamento necessario. Sono stati ora aggiunti criteri per consentire all'IT di applicare scadenze e riavvii necessari e garantire che l'installazione di un aggiornamento sia stata completata in modo corretto. Gli utenti possono ricevere una notifica prima dell'avvio del riavvio e ritardare il riavvio in base ai criteri IT.

Sono stati aggiunti i criteri di aggiornamento seguenti:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Pianificare e configurare le implementazioni degli aggiornamenti per HoloLens 2

HoloLens 2 supporta più funzionalità di automazione degli aggiornamenti rispetto HoloLens di prima generazione. Questo vale soprattutto se si usa Microsoft Intune per gestire Windows criteri di Aggiornamento per le aziende. Queste funzionalità semplificano la pianificazione e l'implementazione delle implementazioni degli aggiornamenti nell'organizzazione.

#### <a name="plan-the-update-strategy"></a>Pianificare la strategia di aggiornamento

Windows Updates for Business supporta i criteri di rinvio. Dopo che Microsoft ha rilasciato un aggiornamento, è possibile usare un criterio di rinvio per definire il tempo di attesa prima di installare l'aggiornamento nei dispositivi. Associando subset dei dispositivi (noti anche come anelli di *aggiornamento)* a criteri di rinvio diversi, è possibile coordinare una strategia di implementazione degli aggiornamenti per l'organizzazione.

Si consideri ad esempio un'organizzazione con 1.000 dispositivi e deve aggiornare i dispositivi in cinque onde. L'organizzazione può creare cinque anelli di aggiornamento, come illustrato nella tabella seguente.

|Group |Number of devices (Numero di dispositivi) |Rinvio (giorni) |
| ---| :---: | :---: |
|Grp 1 (personale IT) |5 |0 |
|Grp 2 (early adopters) |50 |60 |
|Grp 3 (principale 1) |250 |120 |
|Grp 4 (principale 2) |300 |150 |
|Grp 5 (principale 3) |395 |180 |

Ecco come procede l'implementazione nel tempo per l'intera organizzazione.

![Sequenza temporale per la distribuzione degli aggiornamenti.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Configurare un criterio di rinvio degli aggiornamenti

Un criterio di rinvio specifica il numero di giorni tra la data in cui un aggiornamento diventa disponibile e la data in cui l'aggiornamento viene offerto a un dispositivo.

È possibile configurare differimenti diversi per gli aggiornamenti delle funzionalità e gli aggiornamenti qualitativi. Nella tabella seguente sono elencati i criteri specifici da usare per ogni tipo e il differimento massimo per ogni tipo.

|Category |Criteri |Differimento massimo |
| --- | --- | --- |
|Aggiornamenti delle funzionalità |DeferFeatureUpdatesPeriodInDays |365 giorni |
|Aggiornamenti qualitativi |DeferQualityUpdatesPeriodInDays |30 giorni |

#### <a name="pause-updates-via-device"></a>Sospendere gli aggiornamenti tramite il dispositivo

Se un utente non ha accesso a MDM, può sospendere manualmente gli aggiornamenti per un massimo di 35 giorni manualmente in un dispositivo HoloLens 2 nella build [Windows Holographic, versione 2004](hololens-release-notes.md#windows-holographic-version-2004) o successiva. Gli utenti possono raggiungere questa impostazione passando Impostazioni > Opzioni avanzate Impostazioni > Aggiornamento & Sicurezza  > fino **a** Sospendi aggiornamenti e selezionare la data fino alla quale sospenderanno gli aggiornamenti. Dopo che un utente ha raggiunto il limite di sospensione, il dispositivo dovrà ottenere nuovi aggiornamenti prima di poterlo sospendere di nuovo. 

A partire [da Windows Holographic, versione 20H2,](hololens-release-notes.md#windows-holographic-version-20h2)questa funzione di sospensione degli aggiornamenti può essere gestita per HoloLens 2 dispositivi. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (impostazione predefinita) - Abilitato
    - 1 - Disabilitato

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funzioni di gestione degli aggiornamenti di Intune HoloLens supportate

È possibile usare le funzioni di gestione degli aggiornamenti di Intune seguenti per gestire gli aggiornamenti per HoloLens.

- **Crea** e **assegna:** queste funzioni aggiungono un Windows 10'anello di aggiornamento all'elenco degli anelli di aggiornamento. Per altre informazioni, vedere [Creare e assegnare anelli di aggiornamento](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Sospendi:** se si verifica un problema durante la distribuzione di una funzionalità o di un aggiornamento qualitativo, è possibile sospendere l'aggiornamento per 35 giorni (a partire da una data specificata). Questa sospensione impedisce ad altri dispositivi di installare l'aggiornamento fino a quando non si risolve o si attenua il problema. Se si sospende un aggiornamento delle funzionalità, gli aggiornamenti qualitativi vengono comunque offerti ai dispositivi per assicurarsi che rimangano protetti. Quando un tipo di aggiornamento viene sospeso, il riquadro Panoramica per tale anello mostra il numero di giorni che devono trascorrere prima del ripristino del tipo di aggiornamento. Al termine del tempo specificato, la sospensione scade automaticamente e il processo di aggiornamento riprende.

  Mentre l'anello di aggiornamento è sospeso, è possibile selezionare una delle opzioni seguenti:

  - **Estensione:** estendere il periodo di sospensione per un tipo di aggiornamento per 35 giorni.
  - **Resume**: consente di ripristinare l'operazione attiva degli aggiornamenti per l'anello. Se necessario, è possibile sospendere nuovamente l'anello di aggiornamento.

  > [!NOTE]  
  > **L'operazione** di disinstallazione per gli anelli di aggiornamento non è supportata per HoloLens 2 dispositivi.

### <a name="delivery-optimization-preview"></a>Ottimizzazione recapito anteprima

[Windows Holographic, la versione 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ha abilitato un'anteprima anticipata per le impostazioni di ottimizzazione del recapito per ridurre il consumo di larghezza di banda per i download da HoloLens dispositivi. Una descrizione più completa di questa funzionalità insieme alla configurazione di rete consigliata è disponibile qui: Ottimizzazione recapito [per Windows 10 aggiornamenti](/windows/deployment/update/waas-delivery-optimization).

Le impostazioni seguenti sono abilitate come parte dell'area di gestione e [possono essere configurate da Intune:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Alcune avvertenze su questa offerta di anteprima:

- HoloLens supporto è limitato in questa anteprima solo agli aggiornamenti del sistema operativo.
- Windows Holographic for Business supporta solo le modalità di download HTTP e i download da un [endpoint cache connessa Microsoft](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). Le modalità di download peer-to-peer e le assegnazioni di gruppo non sono attualmente supportate HoloLens dispositivi.
- HoloLens non supporta l'ottimizzazione della distribuzione o del recapito Windows Server Update Services endpoint.
- La risoluzione dei problemi richiederà la diagnostica nel server cache connessa o la raccolta di una traccia in HoloLens in HoloLens tramite **Impostazioni**  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update**.

## <a name="manually-check-for-updates"></a>Controllare manualmente la disponibilità di aggiornamenti

Anche HoloLens verifica periodicamente la presenza di aggiornamenti di sistema, è possibile che in alcuni casi si voglia controllare manualmente.

Per verificare manualmente la disponibilità di aggiornamenti, vedere Impostazioni  >  **aggiornamenti & di** sicurezza per gli  >  **aggiornamenti**. Se l Impostazioni app indica che il dispositivo è aggiornato, sono disponibili tutti gli aggiornamenti.

## <a name="manually-roll-back-an-update"></a>Eseguire manualmente il rollback di un aggiornamento

In alcuni casi, potrebbe essere necessario ripristinare una versione precedente del software HoloLens software. Il processo per questa operazione dipende dal fatto che si stia usando HoloLens 2 o HoloLens (prima generazione).

### <a name="revert-to-a-previous-version-hololens-2"></a>Ripristinare una versione precedente (HoloLens 2)

È possibile eseguire il rollback degli aggiornamenti e tornare a una versione precedente di HoloLens 2 usando [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) per reimpostare il HoloLens alla versione precedente.

> [!NOTE]
> Il ripristino di una versione precedente elimina i file e le impostazioni personali.

Per ripristinare una versione precedente di HoloLens 2, seguire questa procedura:

1. Assicurarsi di non avere telefoni o dispositivi Windows collegati al computer.
1. Nel computer scaricare [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dal Microsoft Store.
1. Scaricare la [versione più recente HoloLens 2 .](https://aka.ms/hololens2download)
1. Al termine di questi download, aprire **Esplora file** Download , fare clic con il pulsante destro del mouse sulla cartella compressa  >  (.zip) appena scaricata e quindi scegliere **Estrai** tutto per espandere  >   il file.
1. Usare un cavo da USB A a USB-C per connettere il dispositivo HoloLens al computer. Anche se si usano altri cavi per connettere il HoloLens, questo tipo di cavo funziona meglio.
1. Advanced Recovery Companion rileva automaticamente il dispositivo HoloLens dispositivo. Selezionare il **Microsoft HoloLens** riquadro.
1. Nella schermata successiva selezionare **Selezione pacchetto manuale** e quindi aprire la cartella espansa in precedenza.
1. Selezionare il file di installazione (con estensione ffu).
1. Selezionare **Installa software** e quindi seguire le istruzioni.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Ripristinare una versione precedente (HoloLens (prima generazione))

È possibile eseguire il rollback degli aggiornamenti e tornare a una versione precedente di HoloLens (prima generazione) usando lo strumento di ripristino del dispositivo [Windows (WDRT)](https://support.microsoft.com/help/12379) per ripristinare la versione precedente del HoloLens.

> [!NOTE]
> Il ripristino di una versione HoloLens precedente elimina i file e le impostazioni personali.

Per ripristinare una versione precedente di HoloLens (prima generazione), seguire questa procedura:

1. Assicurarsi di non avere telefoni o dispositivi Windows collegati al computer.
1. Nel computer scaricare lo strumento [di ripristino Windows dispositivo (WDRT)](https://support.microsoft.com/help/12379).
1. Scaricare il pacchetto [HoloLens di ripristino dell'aggiornamento dell'anniversario](https://aka.ms/hololensrecovery).
1. Al termine dei download, aprire **Esplora file** Download , fare clic con il pulsante destro del mouse sulla cartella compressa (.zip) appena scaricata e quindi scegliere Estrai tutto per espandere il  >     >   file.
1. Usare il cavo micro USB fornito insieme al dispositivo HoloLens per connettere il dispositivo HoloLens al computer. Anche se si usano altri cavi per connettere il dispositivo HoloLens, questo funziona meglio.
1. WDRT rileva automaticamente il dispositivo HoloLens dispositivo. Selezionare il **Microsoft HoloLens** riquadro.
1. Nella schermata successiva selezionare **Selezione pacchetto manuale** e quindi aprire la cartella espansa in precedenza.
1. Selezionare il file di installazione (con estensione ffu).
1. Selezionare **Installa software** e quindi seguire le istruzioni.

**Se WDRT non rileva il dispositivo**

Se WDRT non rileva il dispositivo HoloLens, provare a riavviare il computer. Se non funziona, selezionare **Il dispositivo non** è stato rilevato, **selezionare** Microsoft HoloLens e quindi seguire le istruzioni.

## <a name="related-articles"></a>Articoli correlati

- [HoloLens 2 sulla versione](hololens-release-notes.md)
- [Che cos'Windows Update for Business?](/windows/deployment/update/waas-manage-updates-wufb)
- [Assegnare i dispositivi ai canali di manutenzione per Windows 10 aggiornamenti](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gestire gli aggiornamenti software di Windows 10 in Intune](/mem/intune/protect/windows-update-for-business-configure)
