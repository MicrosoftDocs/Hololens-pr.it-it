---
title: Insider Preview per Microsoft HoloLens
description: È semplice iniziare con le build Insider e dare un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb7c60ed8a381c0ce8c7f6a28bc8274d5ea20f30
ms.sourcegitcommit: bdbaed42dd9ecbd0ed9517de2e98a0465f584c1d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929877"
---
# Insider Preview per Microsoft HoloLens

Benvenuti alle build di insider Preview più recenti per HoloLens! È facile [iniziare e dare](hololens-insider.md#start-receiving-insider-builds) un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.

## Note sulla versione di Windows Insider

Se si sta cercando una caratteristica che non è più elencata, ora è in genere disponibile. Leggere le [Note sulla versione](hololens-release-notes.md) per verificare la funzionalità di compilazione con cui si è soddisfatti. Assicurati di [aggiornare il HoloLens](hololens-update-hololens.md) per ottenere tutte le caratteristiche più recenti.

Verrà aggiornata di nuovo questa pagina con nuove funzionalità mentre le rilasceremo alle build Insider di Windows.

| Funzionalità                                              | Descrizione                                                                                   | Disponibile nelle build Insider |
|------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| Supporto per la posizione degli occhi automatici                            | Trova attivamente le posizioni degli occhi e consente il posizionamento accurato degli ologrammi.                       | 19041.1339 +                 |
| Visualizzatore certificati                                   | Visualizzare i certificati utente e dispositivo nell'app Impostazioni.                                        | 19041.1346 +                 |
| Installare e rimuovere i certificati                      | Gli utenti possono installare e rimuovere i certificati tramite il Visualizzatore certificati.                       | 19041.1361 +                 |
| Avvio automatico del provisioning da USB                    | OOBE rileva automaticamente i pacchetti di provisioning sulle unità USB.                                 | 19041.1361 +                 |
| Confermare automaticamente i pacchetti di provisioning in OOBE           | Applicare automaticamente i pacchetti di provisioning in OOBE.                                            | 19041.1361 +                 |
| Connessione Wi-Fi e uso di Autopilot                 | Usare il pilota automatico da Wi-Fi per dispositivi senza bisogno di un adattatore Ethernet.                            | 19041.1364 +                 |
| Criteri HoloLens                                    | Nuovi criteri per i dispositivi di realtà mista.                                                       | 19041.1349 +                 |
| Appartenenza al gruppo della cache AAD per il chiosco offline         | Criteri per il numero di giorni in cui è consentito usare la cache di appartenenza al gruppo AAD per la modalità Kiosk.     | 19041.1356 +                 |
| Nuovi criteri di restrizione dei dispositivi per HoloLens 2       | Criteri di gestione dei dispositivi abilitati per la nuova abilitazione per HoloLens 2.                              | 19041.1349 +                 |
| Nuovi criteri di alimentazione per HoloLens 2                    | Nuovi criteri supportati per le impostazioni di Power timeout.                                          | 19041.1349 +                 |
| Criteri di aggiornamento                                      | Criteri appena abilitati che consentono il controllo degli aggiornamenti.                                           | 19041.1352 +                 |
| Visibilità della pagina impostazioni abilitate per HoloLens 2      | Criteri per selezionare le pagine visualizzate nell'app Impostazioni.                                          | 19041.1349 +                 |
| Accesso assegnato globale                               | Configura il dispositivo HoloLens 2 per la modalità Kiosk di più app applicabile a livello di sistema.  | 19041.1356 +                 |
| Avvio automatico di un'app nel chiosco multi-app                | Imposta l'avvio automatico di un'applicazione durante l'accesso a una modalità Kiosk a più app. | 19041.1346 +                 |
| Accesso automatico visitatori per chioschi multimediali                        | Consente di usare l'accesso automatico agli account dei visitatori per le modalità Kiosk.                        | 19041.1361 +                 |
| Modifiche al comportamento della modalità Kiosk per la gestione degli errori | Le modifiche apportate al modo in cui viene gestito l'errore della modalità Kiosk.                                             | 19041.1356 +                 |
| Miglioramenti e correzioni nell'aggiornamento                 | Correzioni aggiuntive nell'aggiornamento.                                                               | 19041.1361 +                 |

### Supporto per la posizione degli occhi automatici

In HoloLens 2 le posizioni degli occhi permettono un posizionamento accurato degli ologrammi, un'esperienza di visualizzazione confortevole e una qualità di visualizzazione migliorata. Le posizioni degli occhi vengono calcolate come parte del risultato del rilevamento degli occhi. Tuttavia, questo richiede a ogni utente di passare alla calibrazione della verifica degli occhi, anche quando l'esperienza non richiede l'input dello sguardo oculare.

La **posizione degli occhi automatici (AEP)** consente a questi scenari di calcolare le posizioni degli occhi per l'utente in modo libero da interazioni.  La posizione degli occhi automatici inizia a lavorare in background automaticamente dal momento in cui l'utente inserisce il dispositivo. Se l'utente non ha una calibrazione preventiva degli occhi, la posizione degli occhi automatici inizierà a fornire le posizioni degli occhi dell'utente al sistema di visualizzazione dopo un breve periodo di elaborazione. Questo tempo di elaborazione è in genere compreso tra 20-60 secondi. I dati dell'utente non vengono mantenuti nel dispositivo e quindi questo processo viene ripetuto se l'utente decolla e riattiva il dispositivo o se il dispositivo si riavvia o si risveglia dal sonno.  

Ci sono alcune modifiche al comportamento del sistema con la funzionalità posizione occhio automatico quando un utente non calibrato inserisce il dispositivo. Un utente non calibrato fa riferimento a una persona che non ha superato il processo di calibrazione del rilevamento degli occhi nel dispositivo in precedenza.

|     Applicazione attiva                           |     Comportamento corrente                                   |     Comportamento da Windows Insider Build 19041.1339 +                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     App o Shell olografica abilitata per gli occhi non consentiti    |     Viene visualizzata la richiesta di calibrazione del rilevamento degli occhi.    |     Non viene visualizzato alcun messaggio.                                                                                |
|     App sguardo abilitato                             |     Viene visualizzata la richiesta di calibrazione del rilevamento degli occhi.    |     La richiesta di calibrazione degli occhi viene visualizzata solo quando l'applicazione accede al flusso dello sguardo oculare.     |

 Se l'utente passa da un'applicazione abilitata senza lo sguardo a quella che accede ai dati sugli sguardi, verrà visualizzata la richiesta di calibrazione. Non verrà modificato il flusso di esperienza fuori scatola. 
 
Per le esperienze che richiedono dati sugli occhi o un posizionamento olografico molto preciso, è consigliabile che gli utenti non calibrati eseguano la calibrazione della verifica degli occhi dalla richiesta di calibrazione degli occhi o lancino l'app Impostazioni dal menu Start e quindi selezionando **sistema > calibrazione > calibrazione degli occhi > eseguire la calibrazione degli**occhi.

**Problemi noti**
 - Stiamo esaminando un problema in cui il processo di host del driver dell'eye tracker potrebbe arrestarsi in modo anomalo durante l'esecuzione in un carico di memoria elevato. Il processo host del driver di rilevamento degli occhi deve essere recuperato automaticamente.

### Visualizzatore certificati

In Windows Insider Build 19041.1346 + aggiungiamo un visualizzatore di certificati nell'app impostazioni di HoloLens 2. L'installazione del certificato supporta attualmente i file con estensione CER e CRT. I proprietari di dispositivi possono installare i certificati nel computer locale e nell'utente corrente;  tutti gli altri utenti possono essere installati solo nell'utente corrente. Gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia utente delle impostazioni. Se un certificato è stato installato con altri mezzi, deve essere rimosso anche dallo stesso meccanismo.

-   **Controllo:** Possibilità di verificare che un certificato sia distribuito correttamente o per verificare che sia stato rimosso in modo appropriato. 
-   **Diagnosi:** In caso di problemi, verifica che i certificati appropriati esistano nel dispositivo per risparmiare tempo e consente di risolvere i problemi. 
-   **Convalida:** Verificare che il certificato serva allo scopo previsto ed è funzionale, può risparmiare tempo significativo, in particolare in ambienti commerciali prima di distribuire i certificati su scala più ampia.

Per visualizzare i certificati, scegliere **impostazioni > aggiorna & sicurezza > certificati**.

![Visualizzatore certificati nell'app impostazioni](images/hololens-certificate-viewer.png)

### Installare e rimuovere i certificati
A partire da Windows Insider Release 19041.1361 + è possibile installare e rimuovere i certificati direttamente in HoloLens 2, tramite l'app Impostazioni. L'installazione del certificato supporta attualmente i file con estensione CER e CRT. I proprietari di dispositivi possono installare i certificati nel computer locale e nell'utente corrente;  tutti gli altri utenti possono essere installati solo nell'utente corrente. Gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia utente delle impostazioni. Se un certificato è stato installato con altri mezzi, deve essere rimosso anche dallo stesso meccanismo.

#### Per installare un certificato usando il Visualizzatore certificati: 
1. Passare ai **Settings App**  ->  certificati di**aggiornamento e sicurezza**dell'app impostazioni  ->  **Certificates**e selezionare **installa un certificato**. 
1. Selezionare un file con estensione cer dall'esperienza di selezione file.
1. Selezionare computer locale (o il proprio certificato).
1. Selezionare **radice** come archivio certificati o in quale archivio si vuole inserire il certificato. 
1. Fai clic su **Installa**.

Il certificato dovrebbe ora essere installato nel dispositivo.

#### Per rimuovere un certificato usando il Visualizzatore certificati: 
1. Passare ai **Settings App**  ->  certificati di**aggiornamento e sicurezza**delle app impostazioni  ->  **Certificates**.
1. Cercare il certificato per nome nella casella di ricerca.
1. Selezionare il certificato.
1. Fare clic su **Rimuovi**
1. Selezionare Sì quando richiesto e quando viene richiesto di confermare.

![Immagine che Mostra come usare l'interfaccia utente del certificato per installare un certificato](images/hololens-install-certificate.jpg)

#### Problemi noti 
Stiamo esaminando un problema in cui durante il flusso di installazione, dopo aver selezionato un certificato da selezione file, l'interfaccia utente della finestra di dialogo di installazione non Mostra il file di certificato selezionato, anche se è stato selezionato. Dopo aver selezionato il file, è possibile procedere con l'installazione anche se il file non viene visualizzato nella finestra di dialogo. 

### Avvio automatico del provisioning da USB
Prima che gli utenti della build dovessero avviare manualmente la schermata di provisioning durante la configurazione guidata per il provisioning tramite una combinazione di pulsanti. Ora gli utenti possono ignorare la combinazione di pulsanti usando un pacchetto di provisioning in un'unità di archiviazione USB. 

1. Collegare l'unità USB con il pacchetto di provisioning durante il primo momento interattivo di OOBE
1. Quando il dispositivo è pronto per essere eseguito il provisioning, verrà aperto automaticamente il prompt con la pagina provisioning. 

Nota: se un drive USB viene lasciato collegato mentre il dispositivo viene avviato, la configurazione guidata enumera il dispositivo di archiviazione USB esistente, oltre a controllare se sono collegati altri dispositivi.

Per altre informazioni sull'applicazione di pacchetti di provisioning durante la configurazione guidata, continuare a leggere [qui](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### Convalidare automaticamente i pacchetti di provisioning in OOBE
Quando viene visualizzata la schermata principale di provisioning, la configurazione guidata verrà conteggiata per 10 secondi prima di iniziare automaticamente l'applicazione di tutti i pacchetti di provisioning. Gli utenti possono ancora confermare o annullare entro questi 10 secondi dopo aver verificato i pacchetti attesi.

### Provisioning automatico senza usare l'interfaccia utente
Combinando l'avvio automatico del provisioning dei dispositivi USB e la conferma automatica dei pacchetti di provisioning, un utente può eseguire il provisioning automatico di dispositivi HoloLens 2 senza usare l'interfaccia utente del dispositivo o addirittura indossare il dispositivo. Puoi continuare a usare lo stesso pacchetto di unità USB e provisioning per più dispositivi. Questa operazione è utile per la distribuzione di più dispositivi contemporaneamente nella stessa area. 

1. [Creare un pacchetto di provisioning](hololens-provisioning.md) con [Windows Configuration designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copiare il pacchetto in un'unità di archiviazione USB.
1. [Flashare il HoloLens da 2](hololens-insider.md#ffu-download-and-flash-directions) a [19041,1361 o una build più recente](https://aka.ms/hololens2previewdownload). 
1. Quando [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ha completato il lampeggio del dispositivo scollegare il cavo USB-C. 
1. Collegare l'unità USB al dispositivo.
1. Quando il dispositivo HoloLens 2 si avvia in OOBE, il pacchetto di provisioning viene rilevato automaticamente nell'unità USB e viene avviata la pagina di provisioning.
1. Dopo 10 secondi il dispositivo applica automaticamente il pacchetto di provisioning. 

Il dispositivo è ora configurato e visualizzerà lo schermo di provisioning riuscito.

### Connessione Wi-Fi e uso di Autopilot
Ora, durante la configurazione di OOBE, dopo la connessione di HoloLens 2 con WiFi, OOBE verificherà il profilo di un pilota automatico per il dispositivo. Se ne viene trovata una, verrà usata per completare il resto del flusso di partecipazione e registrazione di AAD. In altre parole, l'uso di Ethernet per USB C o WiFi per l'adattatore USB C non è più un requisito, ma continueranno a funzionare se forniti all'inizio della configurazione guidata. Leggi altre informazioni su [Autopilot per dispositivi HoloLens 2](hololens2-autopilot.md).

### Criteri HoloLens
I nuovi criteri di realtà mista sono stati creati per i dispositivi HoloLens 2 nelle build 19041.1349 +. Le nuove impostazioni controllabili includono: impostazione della luminosità, impostazione del volume, disabilitazione della registrazione audio in acquisizioni di realtà miste, impostazione quando la diagnostica può essere raccolta e cache dell'appartenenza al gruppo AAD.  

| Nuovi criteri di HoloLens                                | Descrizione                                                                               | Note                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Consente di disabilitare i pulsanti di luminosità in modo che la pressione non cambi la luminosità.       | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\VolumeButtonDisabled                  | Consente di disabilitare i pulsanti del volume in modo da premere il tasto non cambia volume.               | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\MicrophoneDisabled                    | Disattiva il microfono in modo che non sia possibile una registrazione audio in HoloLens 2.                      | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\FallbackDiagnostics                   | Controlla il comportamento di quando è possibile raccogliere i log diagnostici.                               | 0 disabilitato, 1 abilitato per i proprietari di dispositivi, 2 abilitato per tutti (impostazione predefinita) |
| MixedReality\HeadTrackingMode                      | Riservato per un uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controlla il numero di giorni in cui viene usata la cache di appartenenza a un gruppo di destinatari per i gruppi AAD. | Vedere di seguito.                                                           |

### Appartenenza al gruppo della cache AAD per il chiosco offline

Questo criterio Controlla il numero di giorni in cui è consentita la cache dell'appartenenza a un gruppo AAD per le configurazioni di accesso assegnate destinate ai gruppi AAD per l'utente connesso. Quando il valore di questo criterio è impostato su un valore maggiore di 0 solo la cache viene usata in caso contrario.  

Nome: valore URI AADGroupMembershipCacheValidityInDays:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 giorni  
Max-60 giorni 

Procedura per usare correttamente questo criterio: 
1. Creare un profilo di configurazione del dispositivo per il chiosco che designa i gruppi AAD e assegnarlo ai dispositivi HoloLens. 
1. Crea una configurazione di dispositivo basata su URI OMA personalizzata che imposta il valore di questo criterio sul numero desiderato di giorni (> 0) e assegnalo ai dispositivi HoloLens. 
    1. Il valore URI deve essere immesso nella casella di testo OMA-URI come./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Il valore può essere compreso tra min/max consentita.
1. Registrare i dispositivi HoloLens e verificare che entrambe le configurazioni vengano applicate al dispositivo. 
1. Consentire all'utente di accedere a AAD 1 quando è disponibile Internet, una volta che l'utente ha eseguito l'accesso e l'appartenenza al gruppo AAD è stata confermata, verrà creata la cache. 
1. Ora l'utente AAD 1 può prendere offline HoloLens e usarlo per la modalità Kiosk, purché il valore dei criteri consenta un numero X di giorni. 
1. I passaggi 4 e 5 possono essere ripetuti per qualsiasi altro utente AAD N. il punto chiave è che qualsiasi utente AAD deve effettuare l'accesso al dispositivo tramite Internet, quindi almeno una volta che siamo in grado di determinare di essere membri del gruppo AAD a cui è destinata la configurazione del chiosco. 
 
> [!NOTE]
> Finché non viene eseguito il passaggio 4 per un utente AAD si verificherà un comportamento di errore di seguito indicato in ambienti "disconnessi". 

### Nuovi criteri di restrizione dei dispositivi per HoloLens 2
Criteri appena abilitati che consentono di avere più opzioni di gestione dei dispositivi HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

### Nuovi criteri di alimentazione per Hololens 2
Questi nuovi criteri aggiunti consentono agli amministratori di controllare gli Stati di alimentazione, ad esempio il timeout inattivo. Per saperne di più su ogni singolo criterio, fare clic sul collegamento relativo al criterio.

|     Collegamento documentazione criteri                |     Note                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valore di esempio da usare in Windows Configuration designer, ovvero  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valore di esempio da usare in Windows Configuration designer, ovvero  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valore di esempio da usare in Windows Configuration designer, ovvero 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valore di esempio da usare in Windows Configuration designer, ovvero 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valore di esempio da usare in Windows Configuration designer, ovvero   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valore di esempio da usare in Windows Configuration designer, ovvero  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### Criteri di aggiornamento appena abilitati per HoloLens
Questi criteri di aggiornamento sono ora abilitati nei dispositivi HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### Visibilità della pagina impostazioni abilitate per HoloLens 2
Ora abbiamo abilitato un criterio che consente agli amministratori IT di impedire che pagine specifiche nell'app impostazioni di sistema siano visibili o accessibili oppure di farlo per tutte le pagine eccetto quelle specificate. Per informazioni su come personalizzare completamente questa caratteristica, fare clic sul collegamento seguente.
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![Screenshot delle ore attive modificate nell'app impostazioni](images/hololens-page-visibility-list.jpg)

### Accesso assegnato globale-modalità Kiosk
Questa nuova funzionalità consente all'amministratore IT di configurare un dispositivo HoloLens 2 per la modalità Kiosk di più app, applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che accedono al dispositivo. Per [informazioni dettagliate, vedere](hololens-global-assigned-access-kiosk.md)questa nuova funzionalità.

### Avvio automatico di un'applicazione in modalità Kiosk con più app 
Si applica solo alla modalità Kiosk in più app e può essere designata solo 1 app per l'avvio automatico con l'attributo evidenziato di seguito nella configurazione di Access assegnati. 

L'applicazione viene avviata automaticamente quando l'utente effettua l'accesso. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Accesso automatico visitatori per chioschi multimediali
Questa nuova funzionalità consente di usare l'accesso automatico agli account del visitatore per le modalità Kiosk. 

Per una configurazione non AAD, per configurare un dispositivo per l'autologo del visitatore:
1.  Creare un pacchetto di provisioning che:
    1.  Configura **le impostazioni di runtime/AssignedAccess** per consentire agli account del visitatore.
    1.  Facoltativamente, il dispositivo viene registrato in MDM **(impostazioni di runtime/area di lavoro/iscrizioni)** in modo che possa essere gestito in un secondo momento.
    1.  Non creare un account locale
1.  [Applicare il pacchetto di provisioning](hololens-provisioning.md).

Per una configurazione AAD, gli utenti possono ottenere qualcosa di simile a questo oggi senza questo cambiamento. I dispositivi collegati a AAD configurati per la modalità Kiosk possono accedere a un account del visitatore con un singolo tocco di pulsante della schermata di accesso. Dopo aver eseguito l'accesso all'account del visitatore, il dispositivo non richiederà più di accedere finché il visitatore non viene esplicitamente disconnesso dal menu Start o il dispositivo viene riavviato.

### Modifiche al comportamento della modalità Kiosk per la gestione degli errori

In precedenza, quando si verificano errori nell'applicazione della modalità Kiosk, HoloLens usato per visualizzare tutte le applicazioni nel menu Start. A partire da questa build di Windows Insider, in caso di errori, nessuna app verrà visualizzata nel menu Start, come indicato di seguito: 

![L'immagine della modalità Kiosk ora appare quando non riesce.](images/hololens-kiosk-failure-behavior.png )

### Miglioramenti e correzioni nell'aggiornamento:
- Criteri aggiornati per disabilitare l'enumerazione delle funzioni USB tramite MDM per NCM per AllowUsbConnection.
- Più schermate in OOBE ora sono in modalità oscura.
- Per altre informazioni, vedere l'informativa sulla privacy più recente online.
- Risolti e problema in cui gli utenti non potevano eseguire il provisioning dei profili VPN tramite pacchetti.

## Iniziare a ricevere compilazioni Insider

> [!NOTE]
> Se non è stato aggiornato di recente, riavviare il dispositivo per aggiornare lo stato e ottenere la build più recente.
> - Il comando vocale "dispositivo di riavvio" funziona bene. 
> - È anche possibile scegliere il pulsante Riavvia in Impostazioni/programma Insider di Windows.
>
> Abbiamo avuto un bug sul back-end che potresti aver incontrato e questo ti riporterà in carreggiata.

In un dispositivo HoloLens 2 passa a **Impostazioni**di  >  **aggiornamento &**  >  **programma sicurezza Windows Insider** e selezionare per **iniziare**. Collegare l'account usato per la registrazione come Windows Insider.

Windows Insider ora sta passando ai canali. L'anello **veloce** diventerà il canale **dev**, l'anello **lento** diventerà il **canale Beta**e l' **anteprima del rilascio** diventerà il canale di **anteprima del rilascio**. Ecco come si presenta il mapping:

![Spiegazione di Windows Insider Channels](images/WindowsInsiderChannels.png)

Per altre informazioni, vedere [Introduzione ai canali Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nei Blog di Windows.

Selezionare quindi **lo sviluppo attivo di Windows**, scegliere se si vuole ricevere le build del canale **dev** o del canale **beta** e rivedere le condizioni del programma.

Selezionare **conferma > Riavvia ora** per completare l'installazione. Dopo aver riavviato il dispositivo, accedere a **impostazioni > aggiorna & sicurezza > verificare la disponibilità di aggiornamenti** per ottenere la build più recente.

## FFU download e istruzioni Flash
Per eseguire il test con un FFU firmato per il volo, è necessario prima di tutto sbloccare il dispositivo prima di infiammare il volo firmato FFU.
1. Nel PC:

    1. Scaricare FFU dal PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installare ARC (Advanced Recovery Companion) da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. In HoloLens-Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Windows Insider Program** , quindi iscriviti, riavvia il dispositivo.

1. Flash FFU-ora è possibile flashare il FFU firmato in anteprima con ARC.

## Inviare feedback e segnalare i problemi

Usare [l'app hub di feedback](hololens-feedback.md) in HoloLens per inviare commenti e segnalazioni. L'uso di hub di feedback assicura che vengano incluse tutte le informazioni di diagnostica necessarie per aiutare i nostri ingegneri a eseguire rapidamente il debug e risolvere il problema.  I problemi con la versione cinese e giapponese di HoloLens devono essere segnalati allo stesso modo.

> [!NOTE]
> Assicurarsi di accettare il messaggio che chiede se si vuole che l'hub di feedback acceda alla cartella documenti (selezionare **Sì** quando richiesto).

## Nota per gli sviluppatori

Sei il benvenuto e ti consigliamo di provare a sviluppare le tue applicazioni usando le build Insider di HoloLens.  Per iniziare, vedere la [documentazione di HoloLens per sviluppatori](https://developer.microsoft.com/windows/mixed-reality/development) . Le stesse istruzioni funzionano con le build Insider di HoloLens.  Puoi usare le stesse build di Unity e Visual Studio che stai già usando per lo sviluppo di HoloLens.

## Interrompere la ricezione delle build Insider

Se non si vuole più ricevere Build Insider di Windows olografico, è possibile rifiutare la disattivazione quando HoloLens è in esecuzione una build di produzione oppure è possibile [recuperare il dispositivo](hololens-recovery.md) usando il compagno di ripristino avanzato per recuperare il dispositivo in una versione non Insider di Windows olografico.

> [!CAUTION]
> Esiste un problema noto in cui gli utenti che non si iscrivono da insider Preview Builds dopo la reinstallazione manuale di una nuova versione di anteprima acquisiranno una schermata blu. In seguito dovrà recuperare manualmente il dispositivo. Per informazioni dettagliate su se si è interessati o meno, vedere altre informazioni su questo [problema noto](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Per verificare che HoloLens esegua una build di produzione:

1. Accedere a **impostazioni > sistema > informazioni**e trovare il numero di Build.

1. [Vedere le note sulla versione per i numeri di build della produzione](hololens-release-notes.md).

Per rifiutare le build Insider:

1. In un HoloLens in cui è in corso una build di produzione, passare a **impostazioni > aggiornare & sicurezza > programma Windows Insider**e selezionare **Interrompi Build Insider**.

1. Seguire le istruzioni per rifiutare il dispositivo.
