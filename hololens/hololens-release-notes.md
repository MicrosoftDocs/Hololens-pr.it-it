---
title: Note sulla versione di HoloLens 2
description: Informazioni sugli aggiornamenti in ogni nuova versione di HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 0825e3fd2d0a4e6328eaa617e4233639f481e8cb
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163148"
---
# Note sulla versione di HoloLens 2

Per assicurarti di avere un'esperienza produttiva con i tuoi dispositivi HoloLens, continuiamo a rilasciare gli aggiornamenti relativi a funzionalità, bug e sicurezza. In questa pagina è possibile vedere le novità di HoloLens ogni mese. Per ottenere il più recente aggiornamento di HoloLens 2 Full Flash (FFU) per [flashare il dispositivo tramite il compagno di ripristino avanzato](hololens-recovery.md#clean-reflash-the-device), [scaricalo qui](https://aka.ms/hololens2download). Il download viene mantenuto aggiornato e fornisce la build più recente in generale disponibile.

>[!NOTE]
> Per leggere le note sulla versione dell'emulatore HoloLens, [visita l'archivio](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows olografico, versione 20H2
- Build 19041,1128

Windows olografico, versione 20H2 è ora disponibile e offre un'ampia serie di nuove funzionalità per gli utenti e i professionisti IT di HoloLens 2. Dal posizionamento degli occhi automatici, a gestione certificati in impostazioni, alle funzionalità di modalità Kiosk migliorate e alle nuove funzionalità di configurazione del pilota automatico. Questo nuovo aggiornamento consente ai team IT di assumere un controllo più granulare per la configurazione e la gestione dei dispositivi HoloLens e offre agli utenti un'esperienza olografica ancora più trasparente. 

Questa ultima versione è un aggiornamento mensile della versione 2004, ma questa volta includiamo nuove funzionalità. Il numero di build principale rimarrà lo stesso e Windows Update indicherà un rilascio mensile alla versione 2004 (Build 19041). È possibile esaminare il numero di build nelle impostazioni > informazioni sullo schermo per confermare che si è in 19041.1128 + build più recente disponibile. Per eseguire l'aggiornamento alla versione più recente, aprire l'app Impostazioni, fare clic su Aggiorna & sicurezza e quindi toccare Controlla aggiornamenti. Per altre informazioni su come gestire gli aggiornamenti di HoloLens, visita [Questa pagina](https://docs.microsoft.com/hololens/hololens-updates).

### Novità di Windows olografico, versione 20H2  

| Funzionalità                                              | Descrizione                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Supporto per la posizione degli occhi automatici](hololens-release-notes.md#auto-eye-position-support) | Calcola attivamente le posizioni degli occhi senza che gli utenti debbano eseguire la calibrazione attiva.   |
| [Gestione certificati](hololens-release-notes.md#certificate-manager)   | Consente di installare e rimuovere i certificati dall'app impostazioni per nuovi metodi più semplici.     |
| [Avvio automatico del provisioning da USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Il provisioning dei pacchetti sulle unità USB richiede automaticamente la pagina di provisioning in OOBE.                                                         |
| [Convalidare automaticamente i pacchetti di provisioning in OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | I pacchetti di provisioning vengono applicati automaticamente durante la configurazione guidata dalla pagina provisioning.                                                         |
| [Provisioning automatico senza usare l'interfaccia utente](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Come combinare l'avvio automatico di provisioning e la conferma automatica insieme. |
| [Uso di Autopilot con Wi-Fi connessione](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Usare il pilota automatico da dispositivo Wi-Fi senza bisogno di un adattatore Ethernet. |
| [Tenantlockdown CSP e Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Dopo la registrazione del tenant e il criterio viene applicato, il dispositivo può essere registrato solo in tale tenant ogni volta che il dispositivo viene reimpostato o reinizializzato. |
| [Accesso assegnato globale](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nuovo metodo di configurazione per la modalità Kiosk più app che applica il chiosco a livello di sistema, che lo rende applicabile a tutti.                  |
| [Avvio automatico di un'app nel chiosco multi-app](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Imposta l'avvio automatico di un'applicazione durante l'accesso a una modalità Kiosk a più app.                                                        |
| [Modifiche al comportamento della modalità Kiosk per la gestione degli errori](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | L'errore della modalità Kiosk ora ha un fallback restrittivo.                                                                                                |
| [Criteri HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nuovi criteri per HoloLens.     |
| [Appartenenza al gruppo della cache AAD per il chiosco offline](hololens-release-notes.md#cache-aad-group-membership-for-offline-kiosk)         | I nuovi criteri consentono agli utenti di utilizzare la cache di appartenenza ai gruppi per usare la modalità Kiosk offline per il numero impostato di giorni.                                        |
| [Nuovi criteri di restrizione dei dispositivi per HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Criteri di gestione dei dispositivi abilitati per la nuova abilitazione per HoloLens 2.                                                                                |
| [Nuovi criteri di alimentazione per HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nuovi criteri supportati per le impostazioni di Power timeout.  |
| [Criteri di aggiornamento](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Criteri appena abilitati che consentono il controllo degli aggiornamenti.           |
| [Visibilità della pagina impostazioni abilitate per HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Criteri per selezionare le pagine visualizzate nell'app Impostazioni.             |
| [Modalità ricerca](hololens-release-notes.md#research-mode) | Uso della modalità ricerca in HoloLens 2. |
| [Lunghezza della registrazione aumentata](hololens-release-notes.md#recording-length-increased) | Le registrazioni MRC non sono più limitate a 5 minuti. |
| [Miglioramenti e correzioni nell'aggiornamento](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correzioni aggiuntive nell'aggiornamento.   |

### Supporto per la posizione degli occhi automatici

- Ora forniamo maggiore precisione per il posizionamento degli ologrammi attraverso il supporto della posizione degli occhi automatici per un comfort di visualizzazione elevato e una qualità di visualizzazione migliorata. 

In HoloLens 2 le posizioni degli occhi permettono un posizionamento accurato degli ologrammi, un'esperienza di visualizzazione confortevole e una qualità di visualizzazione migliorata. Le posizioni degli occhi vengono calcolate come parte del risultato del rilevamento degli occhi. Tuttavia, questo richiede a ogni utente di passare alla calibrazione della verifica degli occhi, anche quando l'esperienza non richiede l'input dello sguardo oculare.

La **posizione degli occhi automatici (AEP)** consente a questi scenari di calcolare le posizioni degli occhi per l'utente in modo libero da interazioni.  La posizione degli occhi automatici inizia a lavorare in background automaticamente dal momento in cui l'utente inserisce il dispositivo. Se l'utente non ha una calibrazione preventiva degli occhi, la posizione degli occhi automatici inizierà a fornire le posizioni degli occhi dell'utente al sistema di visualizzazione dopo un breve periodo di elaborazione. Questo tempo di elaborazione è in genere compreso tra 20-60 secondi. I dati dell'utente non vengono mantenuti nel dispositivo e quindi questo processo viene ripetuto se l'utente decolla e riattiva il dispositivo o se il dispositivo si riavvia o si risveglia dal sonno.  

Ci sono alcune modifiche al comportamento del sistema con la funzionalità posizione occhio automatico quando un utente non calibrato inserisce il dispositivo. Un utente non calibrato fa riferimento a una persona che non ha superato il processo di calibrazione del rilevamento degli occhi nel dispositivo in precedenza.

|     Applicazione attiva                           |     Comportamento precedente                                   |     Comportamento per la versione olografica di Windows 20H2 in avanti                                                     |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     App o Shell olografica abilitata per gli occhi non consentiti    |     Viene visualizzata la richiesta di calibrazione del rilevamento degli occhi.    |     Non viene visualizzato alcun messaggio.                                                                                |
|     App sguardo abilitato                             |     Viene visualizzata la richiesta di calibrazione del rilevamento degli occhi.    |     La richiesta di calibrazione degli occhi viene visualizzata solo quando l'applicazione accede al flusso dello sguardo oculare.     |

 Se l'utente passa da un'applicazione abilitata senza lo sguardo a quella che accede ai dati sugli sguardi, verrà visualizzata la richiesta di calibrazione. Non verrà modificato il flusso di esperienza fuori scatola. 
 
Per le esperienze che richiedono dati sugli occhi o un posizionamento olografico molto preciso, è consigliabile che gli utenti non calibrati eseguano la calibrazione della verifica degli occhi dalla richiesta di calibrazione degli occhi o lancino l'app Impostazioni dal menu Start e quindi selezionando **sistema > calibrazione > calibrazione degli occhi > eseguire la calibrazione degli**occhi.

Queste informazioni possono essere trovate in seguito con [altre informazioni sulla calibrazione](hololens-calibration.md#auto-eye-position-support). 

### Gestione certificati

- Strumenti di controllo, diagnosi e convalida migliorati per la sicurezza e la conformità dei dispositivi tramite il nuovo gestore di certificati. Questa funzionalità consentirà di distribuire, risolvere i problemi e convalidare i certificati in scala in ambienti commerciali.

In versione olografica di Windows 20H2 aggiungiamo un gestore di certificati nell'app impostazioni di HoloLens 2. Accedere a **impostazioni > aggiornare i certificati di > di sicurezza &**. Questa funzionalità consente di visualizzare, installare e rimuovere certificati nel dispositivo in modo semplice e intuitivo. Con il nuovo gestore di certificati, gli amministratori e gli utenti hanno ora strumenti di controllo, diagnosi e convalida migliorati per garantire che i dispositivi rimangano sicuri e conformi. 

-   **Controllo:** Possibilità di verificare che un certificato sia distribuito correttamente o per verificare che sia stato rimosso in modo appropriato. 
-   **Diagnosi:** In caso di problemi, verifica che i certificati appropriati esistano nel dispositivo per risparmiare tempo e consente di risolvere i problemi. 
-   **Convalida:** Verificare che un certificato serva lo scopo previsto ed è funzionale, può risparmiare tempo significativo, in particolare in ambienti commerciali prima di distribuire i certificati su scala più ampia.

Per trovare rapidamente un certificato specifico nell'elenco, sono disponibili opzioni per ordinare in base al nome, all'archivio o alla data di scadenza. Gli utenti possono anche cercare direttamente un certificato. Per visualizzare le singole proprietà del certificato, selezionare il certificato e fare clic su **informazioni**. 

L'installazione del certificato supporta attualmente i file con estensione CER e CRT. I proprietari di dispositivi possono installare i certificati nel computer locale e nell'utente corrente;  tutti gli altri utenti possono essere installati solo nell'utente corrente. Gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia utente delle impostazioni. Se un certificato è stato installato con altri mezzi, deve essere rimosso anche dallo stesso meccanismo.

#### Per installare un certificato: 

1.  Connettere il HoloLens 2 a un PC.
1.  Posizionare il file di certificato che si vuole installare in un percorso di HoloLens 2.
1.  Passare all' **app impostazioni > aggiornare i certificati di & sicurezza >** e selezionare installa un certificato.
1.  Fare clic su **Importa file** e passare alla posizione in cui è stato salvato il certificato.
1.  Selezionare **posizione archivio**.
1.  Selezionare **archivio certificati**.
1.  Fai clic su **Installa**.

Il certificato dovrebbe ora essere installato nel dispositivo.

#### Per rimuovere un certificato: 
1. Passare all' **app impostazioni > aggiornamento e sicurezza > certificati**.
1. Cercare il certificato per nome nella casella di ricerca.
1. Selezionare il certificato.
1. Fare clic su **Rimuovi**
1. Selezionare **Sì** quando viene richiesto di confermare.

![Visualizzatore certificati nell'app impostazioni](images/certificate-viewer-device.jpg)

![Immagine che Mostra come usare l'interfaccia utente del certificato per installare un certificato](images/certificate-device-install.jpg)

Queste informazioni possono essere trovate [in un secondo momento in una nuova pagina di gestione certificati](certificate-manager.md).

### Avvio automatico del provisioning da USB

- Processi automatizzati che consentono di usare meno interazioni degli utenti, quando durante la configurazione vengono usate le unità USB con pacchetti di provisioning.

Prima che gli utenti di questa versione dovessero avviare manualmente la schermata di provisioning durante la configurazione guidata per il provisioning tramite una combinazione di pulsanti. Ora gli utenti possono ignorare la combinazione di pulsanti usando un pacchetto di provisioning in un'unità di archiviazione USB. 

1. Collegare l'unità USB con il pacchetto di provisioning durante il primo momento interattivo di OOBE
1. Quando il dispositivo è pronto per essere eseguito il provisioning, verrà aperto automaticamente il prompt con la pagina provisioning. 

Nota: se un drive USB viene lasciato collegato mentre il dispositivo viene avviato, la configurazione guidata enumera il dispositivo di archiviazione USB esistente, oltre a controllare se sono collegati altri dispositivi.

Per altre informazioni sull'applicazione di pacchetti di provisioning durante la configurazione guidata, continuare a leggere [qui](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

Queste informazioni possono essere trovate più avanti [qui.](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### Convalidare automaticamente i pacchetti di provisioning in OOBE
- Processo automatizzato che consente di usare meno interazioni degli utenti, quando viene visualizzata la pagina del pacchetto di provisioning verrà applicato automaticamente tutti i pacchetti elencati.

Quando viene visualizzata la schermata principale di provisioning, la configurazione guidata verrà conteggiata per 10 secondi prima di iniziare automaticamente l'applicazione di tutti i pacchetti di provisioning. Gli utenti possono ancora confermare o annullare entro questi 10 secondi dopo aver verificato i pacchetti attesi.

Queste informazioni possono essere trovate più avanti [qui.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### Provisioning automatico senza usare l'interfaccia utente
- Processi automatici combinati per le interazioni tra dispositivi ridotte per il provisioning. 

Combinando l'avvio automatico del provisioning dei dispositivi USB e la conferma automatica dei pacchetti di provisioning, un utente può eseguire il provisioning automatico di dispositivi HoloLens 2 senza usare l'interfaccia utente del dispositivo o addirittura indossare il dispositivo. Puoi continuare a usare lo stesso pacchetto di unità USB e provisioning per più dispositivi. Questa operazione è utile per la distribuzione di più dispositivi contemporaneamente nella stessa area. 

1. [Creare un pacchetto di provisioning](hololens-provisioning.md) con [Windows Configuration designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copiare il pacchetto in un'unità di archiviazione USB.
1. [Flashare il HoloLens da 2](hololens-insider.md#ffu-download-and-flash-directions) a [19041,1361 o una build più recente](https://aka.ms/hololens2previewdownload). 
1. Quando [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ha completato il lampeggio del dispositivo scollegare il cavo USB-C. 
1. Collegare l'unità USB al dispositivo.
1. Quando il dispositivo HoloLens 2 si avvia in OOBE, il pacchetto di provisioning viene rilevato automaticamente nell'unità USB e viene avviata la pagina di provisioning.
1. Dopo 10 secondi il dispositivo applica automaticamente il pacchetto di provisioning. 

Il dispositivo è ora configurato e visualizzerà lo schermo di provisioning riuscito.

Queste informazioni possono essere trovate più avanti [qui.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Uso di Autopilot con Wi-Fi connessione
- È stata rimossa la necessità di adattatori USB-C alle esigenze hardware riducenti Ethernet, abilitando Autopilot per funzionare su Wi-Fi dispositivi connessi.

Ora, durante la configurazione di OOBE, dopo la connessione di HoloLens 2 con WiFi, OOBE verificherà il profilo di un pilota automatico per il dispositivo. Se ne viene trovata una, verrà usata per completare il resto del flusso di partecipazione e registrazione di AAD. In altre parole, l'uso di Ethernet a USB-C o Wi-Fi all'adattatore USB-C non è più un requisito, ma continueranno a funzionare se forniti all'inizio della configurazione guidata. Leggi altre informazioni su [Autopilot per dispositivi HoloLens 2](hololens2-autopilot.md).

### Tenantlockdown CSP e Autopilot
- Mantiene i dispositivi nel tenant dell'organizzazione tramite il blocco al tenant anche tramite reset del dispositivo o reflash. Con ulteriore sicurezza, non è consentito la creazione di account in via provisioning. 

I dispositivi HoloLens 2 supportano ora TenantLockdown CSP come [versione olografica di Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP consente a HoloLens 2 di essere collegato alla registrazione MDM usando solo il pilota automatico. Una volta che il nodo RequireNetworkInOOBE di CSP di TenantLockdown è impostato su true o false (inizialmente impostato) su HoloLens 2, il valore rimane nel dispositivo nonostante il relampeggio, gli aggiornamenti del sistema operativo e così via. 

Una volta che il nodo RequireNetworkInOOBE CSP di TenantLockdown è impostato su true in HoloLens 2, OOBE attende a tempo indeterminato che il profilo del pilota automatico venga scaricato e applicato correttamente, dopo la connettività di rete. 

Una volta che il nodo RequireNetworkInOOBE CSP di TenantLockdown è impostato su true in HoloLens 2, le operazioni seguenti non sono consentite in OOBE: 
- Creazione di un utente locale con il provisioning di runtime 
- Esecuzione dell'operazione AAD join tramite provisioning di runtime 
- Selezione di chi possiede il dispositivo nell'esperienza di configurazione guidata 

#### Come impostare l'uso di Intune? 
1. Crea un profilo di configurazione del dispositivo URI OMA personalizzato e specifica true per il nodo RequireNetworkInOOBE, come illustrato di seguito.
Il valore URI OMA deve essere./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Impostazione del blocco di Tennant tramite OMA-URI](images/hololens-tenant-lockdown.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo al gruppo di dispositivi. 

1. Impostare il membro del dispositivo HoloLens 2 del gruppo creato nel passaggio precedente e attivare la sincronizzazione.  

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Una volta che questa configurazione del dispositivo si applica correttamente al dispositivo Hololens 2, gli effetti di TenantLockdown saranno attivi.

#### Come si annulla la RequireNetworkInOOBE di TenantLockdown in HoloLens 2 usando Intune? 
1. Rimuovere il HoloLens 2 dal gruppo di dispositivi a cui è stata assegnata la configurazione di dispositivo precedente. 

1. Crea un profilo di configurazione del dispositivo basato su URI OMA personalizzato e specifica false per RequireNetworkInOOBE, come illustrato di seguito. Il valore URI OMA deve essere./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot dell'impostazione di RequireNetworkInOOBE su false tramite URI OMA in Intune](images/hololens-tenant-lockdown-false.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo al gruppo di dispositivi. 

1. Impostare il membro del dispositivo HoloLens 2 del gruppo creato nel passaggio precedente e attivare la sincronizzazione.

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Una volta che questa configurazione del dispositivo si applica correttamente al dispositivo Hololens 2, gli effetti di TenantLockdown saranno inattivi. 

#### Cosa succede durante la configurazione guidata, se il profilo Autopilot non è assegnato in un HoloLens dopo che TenantLockdown è stato impostato su true? 
Il file OOBE attenderà in modo indefinito il download del profilo del pilota automatico e la finestra di dialogo seguente verrà presentata. Per rimuovere gli effetti di TenantLockdown, il dispositivo deve essere registrato con il suo tenant originale usando solo il pilota automatico e RequireNetworkInOOBE deve essere annullato, come descritto nel passaggio precedente, prima che le restrizioni introdotte da TenantLockdown CSP vengano rimosse. 

![Visualizzazione in un dispositivo per quando il criterio viene applicato al dispositivo.](images/hololens-autopilot-lockdown.png)

Queste informazioni ora possono essere trovate insieme al resto del pilota automatico in [TENANTLOCKDOWN CSP e Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### Accesso assegnato globale-modalità Kiosk
- Gestione delle identità ridotta per Kiosk, abilitando il nuovo metodo Kiosk che applica la modalità Kiosk a livello di sistema.

Questa nuova funzionalità consente all'amministratore IT di configurare un dispositivo HoloLens 2 per la modalità Kiosk di più app, applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che accedono al dispositivo. Per [informazioni dettagliate, vedere](hololens-global-assigned-access-kiosk.md)questa nuova funzionalità.

### Avvio automatico di un'applicazione in modalità Kiosk con più app 
- Esperienza focalizzata con l'avvio automatico delle app, aumentando ulteriormente l'interfaccia utente e le selezioni delle app scelte per le esperienze in modalità Kiosk.

Si applica solo alla modalità Kiosk in più app e può essere designata solo 1 app per l'avvio automatico con l'attributo evidenziato di seguito nella configurazione di Access assegnati. 

L'applicazione viene avviata automaticamente quando l'utente effettua l'accesso. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Modifiche al comportamento della modalità Kiosk per la gestione degli errori
- Modalità Kiosk più sicura eliminando le app disponibili in errori di modalità Kiosk. 

In precedenza, quando si verificano errori nell'applicazione della modalità Kiosk, HoloLens usato per visualizzare tutte le applicazioni nel menu Start. Ora in versione olografica di Windows 20H2 in caso di errori nessuna app verrà visualizzata nel menu Start come indicato di seguito: 

![L'immagine della modalità Kiosk ora appare quando non riesce.](images/hololens-kiosk-failure-behavior.png )

### Criteri HoloLens
- Opzioni di gestione dei dispositivi specifiche per HoloLens creato per la gestione del dispositivo. 

I nuovi criteri di realtà mista sono stati creati per i dispositivi HoloLens 2 in versione olografica di Windows 20H2. Le nuove impostazioni controllabili includono: impostazione della luminosità, impostazione del volume, disabilitazione della registrazione audio in acquisizioni di realtà miste, impostazione quando la diagnostica può essere raccolta e cache dell'appartenenza al gruppo AAD.  

| Nuovi criteri di HoloLens                                | Descrizione                                                                               | Note                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Consente di disabilitare i pulsanti di luminosità in modo che la pressione non cambi la luminosità.       | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\VolumeButtonDisabled                  | Consente di disabilitare i pulsanti del volume in modo da premere il tasto non cambia volume.               | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\MicrophoneDisabled                    | Disattiva il microfono in modo che non sia possibile una registrazione audio in HoloLens 2.                      | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\FallbackDiagnostics                   | Controlla il comportamento di quando è possibile raccogliere i log diagnostici.                               | 0 disabilitato, 1 abilitato per i proprietari di dispositivi, 2 abilitato per tutti (impostazione predefinita) |
| MixedReality\HeadTrackingMode                      | Riservato per un uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controlla il numero di giorni in cui viene usata la cache di appartenenza a un gruppo di destinatari per i gruppi AAD. | Vedere di seguito.                                                           |

### Appartenenza al gruppo della cache AAD per il chiosco offline
- Sono stati abilitati i chioschi offline per essere usati con i gruppi AAD per un massimo di 60 giorni.

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
> Finché non viene eseguito il passaggio 4 per un utente AAD si verificherà un comportamento di errore menzionato in ambienti "disconnessi". 

### Nuovi criteri di restrizione dei dispositivi per HoloLens 2
- Consente agli utenti di gestire specifici criteri di gestione dei dispositivi, ad esempio bloccare l'aggiunta o la rimozione di pacchetti di provisioning.

Criteri appena abilitati che consentono di avere più opzioni di gestione dei dispositivi HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Queste due nuove polizie per AllowAddProvisioningPackage e AllowRemoveProvisioningPackage vengono aggiunte alle [restrizioni dei dispositivi comuni](hololens-common-device-restrictions.md).

### Nuovi criteri di alimentazione per Hololens 2
- Altre opzioni per quando HoloLens dorme o si blocca con i criteri di alimentazione. 

Questi nuovi criteri aggiunti consentono agli amministratori di controllare gli Stati di alimentazione, ad esempio il timeout inattivo. Per saperne di più su ogni singolo criterio, fare clic sul collegamento relativo al criterio.

|     Collegamento documentazione criteri                |     Note                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valore di esempio da usare in Windows Configuration designer, ovvero  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valore di esempio da usare in Windows Configuration designer, ovvero  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valore di esempio da usare in Windows Configuration designer, ovvero 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valore di esempio da usare in Windows Configuration designer, ovvero 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valore di esempio da usare in Windows Configuration designer, ovvero   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valore di esempio da usare in Windows Configuration designer, ovvero  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Queste due nuove polizie per DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn vengono aggiunte alle [restrizioni dei dispositivi comuni](hololens-common-device-restrictions.md).

> [!NOTE]
> Per un'esperienza coerente su HoloLens 2, assicurati che i valori di DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery siano impostati come stesso valore. Lo stesso vale per DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Per altri dettagli sulla modalità standby moderna, vedere [visualizzare, dormire e sospendere i timer di ozio](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### Criteri di aggiornamento appena abilitati per HoloLens
- Altre opzioni per l'installazione degli aggiornamenti o la disabilitazione del pulsante Sospendi aggiornamenti per garantire gli aggiornamenti.

Questi criteri di aggiornamento sono ora abilitati nei dispositivi HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Tutti i dettagli sui criteri di aggiornamento di Thise e su come usarli per i dispositivi HoloLens possono essere letti qui in [gestire gli aggiornamenti di HoloLens](hololens-updates.md).

### Visibilità della pagina impostazioni abilitate per HoloLens 2
- Maggiore controllo dell'interfaccia utente nell'app Impostazioni, che potrebbe essere confusa per visualizzare una selezione limitata di pagine.

Ora abbiamo abilitato un criterio che consente agli amministratori IT di impedire che pagine specifiche nell'app impostazioni di sistema siano visibili o accessibili oppure di farlo per tutte le pagine eccetto quelle specificate. Per informazioni su come personalizzare completamente questa caratteristica, fare clic sul collegamento seguente.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Per informazioni sulle impostazioni di pagina che è possibile personalizzare in HoloLens 2, visitare la pagina relativa agli [URI delle impostazioni](settings-uri-list.md). 
 
![Schermata dell'orario di attività in fase di modifica nell'app Impostazioni](images/hololens-page-visibility-list.jpg)

### Modalità ricerca
Mentre si è in modalità di ricerca, HoloLens 2 diventa uno strumento potente per la ricerca di computer vision. Rispetto alle edizioni precedenti, la modalità di ricerca per HoloLens 2 presenta i vantaggi seguenti:
-   Oltre ai sensori esposti nella modalità di ricerca di HoloLens (1a generazione), ora forniamo l'accesso ai sensori di IMU, tra cui accelerometro, giroscopio e magnetometro.
-   HoloLens 2 offre nuove funzionalità che possono essere usate insieme alla modalità ricerca. In particolare, l'accesso alle API articolate per il monitoraggio delle mani e degli Eye-Tracking in grado di offrire un insieme più ricco di esperimenti.

I ricercatori hanno ora la possibilità di abilitare la modalità di ricerca sui loro dispositivi HoloLens per accedere a tutti questi flussi di sensori di immagini grezzi esterni. La modalità di ricerca per HoloLens 2 offre anche l'accesso alle letture accelerometro, giroscopio e magnetometro. Per proteggere la privacy degli utenti, le immagini della videocamera non sono disponibili tramite la modalità ricerca, ma l'orientamento degli occhi è disponibile tramite le API esistenti.

Per ulteriori dettagli tecnici, vedere la [documentazione della modalità ricerca](https://docs.microsoft.com/windows/mixed-reality/research-mode) .

### Lunghezza della registrazione aumentata
A causa del feedback dei clienti abbiamo aumentato la lunghezza della registrazione delle [acquisizioni di realtà miste](holographic-photos-and-videos.md). Le acquisizioni di realtà miste non saranno più limitate a 5 minuti per impostazione predefinita, ma calcolerà la lunghezza massima di registrazione in base allo spazio disponibile su disco. Il dispositivo stimerà la durata massima della registrazione video in base allo spazio disponibile su disco fino al 80% dello spazio totale sul disco.

> [!NOTE]
> HoloLens utilizzerà la lunghezza predefinita della registrazione video (5 minuti) se si verifica una delle operazioni seguenti:
> - La durata stimata della registrazione max è inferiore ai 5 minuti predefiniti.
> - Lo spazio disponibile su disco è inferiore al 20% dello spazio totale su disco.

Queste informazioni possono essere trovate di nuovo [qui](holographic-photos-and-videos.md#maximum-recording-length). 

### Miglioramenti e correzioni nell'aggiornamento:
- Più schermate in OOBE ora sono in modalità oscura.
- Per altre informazioni, vedere l'informativa sulla privacy più recente online.
- È stato risolto un problema per cui gli utenti non potevano eseguire il provisioning dei profili VPN tramite pacchetti.
- Problema di configurazione del proxy fisso per la connessione VPN.
- Criteri aggiornati per disabilitare l'enumerazione delle funzioni USB tramite MDM per NCM per AllowUsbConnection.
- È stato risolto un problema che impediva a un dispositivo HoloLens di essere visualizzato in Esplora file tramite il protocollo MTP (Media Transfer Protocol) quando il dispositivo è configurato come [chiosco di app singole](hololens-kiosk.md). Tieni presente che MTP (e la connessione USB in generale) possono comunque essere disabilitati usando i criteri di [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
- È stato risolto un problema per cui le icone nel menu Start venivano ridimensionate correttamente in modalità Kiosk.
- È stato risolto un problema dovuto alla memorizzazione nella cache HTTP che interferiva con la modalità Kiosk mirata ai gruppi AAD.
- È stato risolto un problema per cui gli utenti non erano in grado di usare il pulsante Pair dopo l'abilitazione della modalità sviluppatore con il provisioning dei pacchetti, a meno che non fossero disabilitati e riabilitati.

## Windows olografico, versione 1903-novembre 2020 Update
- Build 18362,1085

Questo aggiornamento mensile di qualità non contiene modifiche sostanziali, ti invitiamo a provare la versione più recente della funzionalità build Windows olografica 20H2.

## Windows olografico, versione 2004-ottobre 2020 Update
- Build 19041,1124
 
Miglioramenti e correzioni nell'aggiornamento:

- È stato rimosso un controllo non necessario che causava un errore di Runtime System.

## Windows olografico, versione 1903-ottobre 2020 Update
- Build 18362,1081

Questo aggiornamento mensile di qualità non contiene modifiche importanti, ti invitiamo a provare le nostre build più recenti per Windows olografico, versione 2004.

## Windows olografico, versione 2004-settembre 2020 Update
- Build 19041,1117

Miglioramenti e correzioni nell'aggiornamento:

- Risolve un problema che impediva a Visual Studio di eseguire il debug di un'applicazione quando SupportsMultipleInstances = "true" è presente in appxmanifest.
- Questa versione include la correzione del rilevamento proxy di NCSI per risolvere il rilevamento di Internet non riuscito tramite proxy di rete. NCSI può usare il proxy del computer e il proxy per profilo per il rilevamento della connettività Internet. Il proxy per utente sarà supportato da NCSI in versione futura.
- Nella maggior parte dei dispositivi di realtà mista di Windows, il vettore di direzione in avanti è parallelo al suolo quando la testa dell'utente si trova in posizione neutrale in attesa. Tuttavia, le versioni precedenti di HoloLens 2 hanno allineato il vettore in modo che sia perpendicolare ai pannelli visualizzati, che è inclinato verso il basso di alcuni gradi rispetto all'orientamento ideale. Le versioni più recenti di HoloLens 2 hanno corretto questa operazione per garantire la coerenza semantica tra i fattori di forma.
- Migliorata la robustezza del monitoraggio delle mani che causa meno perdite di rilevamento in scenari specifici.
- Questa versione contiene una correzione per migliorare la qualità timestamp audio che potrebbe aver contribuito a problemi di acquisizione video.

## Windows olografico, versione 1903-settembre 2020 Update
- Build 18362,1079

Miglioramenti e correzioni nell'aggiornamento:

- Nella maggior parte dei dispositivi di realtà mista di Windows, il vettore di direzione in avanti è parallelo al suolo quando la testa dell'utente si trova in posizione neutrale in attesa. Tuttavia, le versioni precedenti di HoloLens 2 hanno allineato il vettore in modo che sia perpendicolare ai pannelli visualizzati, che è inclinato verso il basso di alcuni gradi rispetto all'orientamento ideale. Le versioni più recenti di HoloLens 2 hanno corretto questa operazione per garantire la coerenza semantica tra i fattori di forma.
- Migliorata la robustezza del monitoraggio delle mani che causa meno perdite di rilevamento in scenari specifici.

## Windows olografico, versione 2004-agosto 2020 Update
- Build 19041,1113

Miglioramenti e correzioni nell'aggiornamento:

- L'app impostazioni non seguirà più l'utente nella registrazione dell'iride o nelle esperienze di calibrazione degli occhi.
- È stato risolto un bug in cui l'applicazione di un pacchetto di provisioning durante la configurazione di un file che rinomina il dispositivo ed esegue altre azioni, ad esempio la connessione a una rete, non eseguirebbe le altre azioni dopo il riavvio del dispositivo a causa di un ridenominazione.
- Combinazione di colori modificata dei flussi di configurazione del dispositivo iniziali per migliorare la qualità visiva.

## Windows olografico, versione 1903-agosto 2020 Update
- Build 18362,1074

Questo aggiornamento mensile di qualità non contiene modifiche importanti, ti invitiamo a provare le nostre build più recenti per Windows olografico, versione 2004.

## Windows olografico, versione 2004-luglio 2020 Update
- Build 19041,1109

Miglioramenti e correzioni nell'aggiornamento:

- Gli sviluppatori possono ora scegliere tra l'abilitazione o la disabilitazione con Device Portal richiede una connessione sicura.
- Affidabilità migliorata per i lanci delle applicazioni dopo gli aggiornamenti del sistema operativo.
- Modifica della luminosità predefinita della posta in arrivo in 100%.
- È stato risolto un problema relativo all'inoltro HTTPS per Windows Device Portal in HoloLens 2.

## Windows olografico, versione 1903-luglio 2020 Update
- Build 18362,1071

Miglioramenti e correzioni nell'aggiornamento:

- È stato risolto un problema che potrebbe causare la scomparsa degli ologrammi nelle applicazioni Unity quando si perde o si riprende il rilevamento.
- È stato risolto un problema che causava l'arresto anomalo delle app HoloLens esclusive nella shell durante l'uso dell'emulatore HoloLens con accelerazione hardware su determinati dispositivi.
- È stato risolto un problema relativo all'inoltro HTTPS per Windows Device Portal in HoloLens 2.

## Windows olografico, versione 2004-giugno 2020 Update
- Build 19041,1106

Miglioramenti e correzioni nell'aggiornamento:

- I registratori MRC personalizzati ora hanno nuovi valori predefiniti per determinate proprietà, se non sono specificati.
  - Nell' *effetto video MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auricolare immersiva))
  - Sull' *effetto audio MRC*:
    - LoopbackGain (il valore di "guadagno dell'app audio" corrente nella pagina di acquisizione di realtà mista in Windows Device Portal)
    - MicrophoneGain (il valore "MIC Audio Gain" corrente nella pagina di acquisizione di realtà mista in Windows Device Portal)
- È stato risolto un bug per migliorare la qualità audio negli scenari di acquisizione di realtà mista. In particolare, questa correzione deve eliminare il glitch audio nella registrazione quando viene visualizzato il menu **Start** .
- Migliorata la stabilità degli ologrammi nei video registrati.
- Risolto un problema per cui l'acquisizione di realtà mista non poteva registrare il video dopo che il dispositivo è stato lasciato in standby per più giorni.
- L'API HolographicSpace. UserPresence è in genere disabilitata per le applicazioni Unity. Questo comportamento evita un problema che ha causato la sospensione di alcune app quando la visiera è stata capovolta, anche se l'impostazione "Esegui in background" è stata abilitata. L'API è ora abilitata per le versioni 2018.4.18 e successive di Unity e 2019.3.4 e versioni successive.
- Quando si accede a Device Portal tramite una connessione Wi-Fi, un Web browser può impedire l'accesso a causa di un certificato non valido. Il browser potrebbe segnalare un errore, ad esempio "ERR_SSL_PROTOCOL_ERROR", anche se il certificato del dispositivo è stato considerato attendibile in precedenza. In questo caso, non è possibile passare a Device Portal, perché non è possibile ignorare gli avvisi di sicurezza. Questo aggiornamento ha risolto il problema. Se il certificato del dispositivo è stato precedentemente scaricato e considerato attendibile in un PC per rimuovere gli avvisi di sicurezza del browser e si verifica l'errore SSL, il nuovo certificato deve essere scaricato e considerato attendibile per indirizzare gli avvisi di sicurezza del browser.
- È stata abilitata la possibilità di creare un pacchetto di provisioning di runtime in grado di installare un'app usando i pacchetti MSIX.
- Aggiunta di un'impostazione nel sistema di **Impostazioni**  >  **System**  >  **olografici** che consente agli utenti di rimuovere automaticamente tutti gli ologrammi dalla realtà mista Home quando il dispositivo si arresta.
- È stato risolto un problema che causava le app HoloLens che modificano il formato pixel per il rendering nero nell'emulatore HoloLens.
- È stato risolto un bug che causava un arresto anomalo durante l'accesso a Iris.
- È stato risolto un problema relativo ai download ripetuti dello Store per le app già aggiornate.
- È stato risolto un bug per evitare che le app immersive potessero aprire più volte Microsoft Edge.
- È stato risolto un problema con l'avvio dell'app Foto in stivali iniziali dopo l'aggiornamento dalla versione di 1903.
- Prestazioni e affidabilità migliorate.

## Windows olografico, versione 1903-giugno 2020 Update
- Build 18362,1064

Miglioramenti e correzioni nell'aggiornamento:

- I registratori MRC personalizzati hanno nuovi valori predefiniti per determinate proprietà, se non sono specificati.
  - Nell' *effetto video MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auricolare immersiva))
  - Sull' *effetto audio MRC*:
    - LoopbackGain (il valore di "guadagno dell'app audio" corrente nella pagina di acquisizione di realtà mista in Windows Device Portal)
    - MicrophoneGain (il valore "MIC Audio Gain" corrente nella pagina di acquisizione di realtà mista in Windows Device Portal)
- L'API HolographicSpace. UserPresence è in genere disabilitata per le applicazioni Unity. Questo comportamento evita un problema che causa la sospensione di alcune app quando la visiera è capovolta, anche se l'impostazione per l'esecuzione in background è abilitata. L'API è ora abilitata per le versioni 2018.4.18 e successive di Unity e 2019.3.4 e versioni successive.
- È stato risolto un problema che causava le app HoloLens che modificano il formato pixel per il rendering nero nell'emulatore HoloLens.
- È stato risolto un problema relativo all'avvio dell'app Foto in stivali iniziali dopo l'aggiornamento dalla versione di 1903.

## Windows olografico, versione 2004  
- Build-19041,1103

L'aggiornamento software principale di maggio 2020 per HoloLens 2, *Windows olografico, versione 2004* include numerose nuove funzionalità, come il supporto per il pilota automatico Windows, la modalità Dark app, il supporto USB Ethernet per gli hotspot 5g/LTE e molto altro. Per eseguire l'aggiornamento alla versione più recente, aprire l'app **Impostazioni**   , fare clic su **Aggiorna & sicurezza**e selezionare il pulsante **Controlla aggiornamenti**   . 

|             Funzionalità                              |          Descrizione                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pre-configurare e configurare in maniera trasparente nuovi dispositivi per la produzione usando il pilota automatico di Windows                 |
|       Supporto di FIDO 2                             |          Supporto per le chiavi di sicurezza di FIDO2 per abilitare l'autenticazione veloce e sicura per i dispositivi condivisi            |
|       Miglioramento del provisioning                      |          Applicare senza problemi un pacchetto di provisioning da un'unità USB al proprio HoloLens                              |
|       Stato di installazione dell'applicazione                 |          Verificare che lo stato di installazione nell'app impostazioni per le app sia stato inserito in HoloLens 2 tramite MDM               |
|       Provider di servizi di configurazione (CSP)   |          Sono stati aggiunti nuovi provider di servizi di configurazione per migliorare le funzionalità di controllo dell'amministratore                 |
|       Supporto per USB 5G/LTE                       |          La funzionalità Ethernet USB espansa consente il supporto per 5G/LTE                                    |
|       Modalità app scura                              |          Modalità app scure disponibile per le app che supportano le modalità buio e luce, il miglioramento dell'esperienza di visualizzazione        |
|       Comandi vocali                             |          Supporto per comandi vocali di sistema aggiuntivi per controllare HoloLens Hands-Free                           |
|       Miglioramenti per il rilevamento delle mani                 |          Miglioramenti per il rilevamento delle mani rende più accurate i pulsanti e le interazioni in ardesia 2D                        |
|       Miglioramenti e correzioni di qualità                 |          Diversi miglioramenti delle prestazioni e dell'affidabilità del sistema in tutta la piattaforma                            |

### Supporto per il pilota automatico di Windows

Windows Autopilot per HoloLens 2 consente al canale di vendita del dispositivo di pre-registrare HoloLens nel tenant di Intune. Quando arrivano i dispositivi, sono pronti a eseguire la distribuzione automatica come dispositivi condivisi sotto il tenant. Per sfruttare la distribuzione automatica, il dispositivo deve connettersi a una rete durante la prima schermata del programma di installazione usando un USB-C-to-Ethernet.

Dopo che un utente ha avviato il processo di distribuzione automatica del pilota automatico, il processo completa i passaggi seguenti:

1. Aggiungere il dispositivo ad Azure Active Directory (Azure AD)
1. Utilizzare Azure AD per registrare il dispositivo in Microsoft Intune (o in un altro servizio MDM).
1. Eseguire il download dei criteri, dei certificati e dei profili di rete di destinazione del dispositivo.
1. Eseguire il provisioning del dispositivo.
1. Presentare la schermata di accesso all'utente.

Altre informazioni sulla [Guida alla valutazione di Windows Autopilot per HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Contatta il tuo account Manager per partecipare all'anteprima del pilota automatico ora. I dispositivi pronti per il pilota automatico inizieranno presto la spedizione.*

### Supporto della chiave di sicurezza FIDO2

Alcuni utenti condividono un dispositivo HoloLens con altre persone in un ambiente lavorativo o scolastico. Quindi è importante che gli utenti possano facilmente senza digitare nomi utente e password lunghi. Fast Identity online (FIDO) consente a tutti gli utenti dell'organizzazione (Azure AD tenant) di accedere facilmente a HoloLens senza immettere un nome utente o una password.

Le chiavi di sicurezza di FIDO2 sono un metodo di autenticazione senza password basato su standard "unphishable" che può rientrare in qualsiasi fattore di forma. FIDO è uno standard aperto per l'autenticazione con password. Consente agli utenti e alle organizzazioni di accedere alle proprie risorse senza un nome utente o una password. Usano invece una chiave di sicurezza esterna o una chiave della piattaforma incorporata in un dispositivo.

Per iniziare, vedere [abilitare l'accesso tramite chiave di sicurezza senza password](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### Registrazione MDM migliorata tramite il pacchetto di provisioning

I pacchetti di provisioning consentono di impostare la configurazione di HoloLens tramite un file di configurazione anziché tramite l'esperienza di HoloLens out-of-box. In precedenza, i pacchetti di provisioning dovevano essere copiati nella memoria interna di HoloLens. Ora possono essere su un'unità USB in modo che siano più facili da riutilizzare su più dispositivi HoloLens ed è possibile eseguire il provisioning di dispositivi in parallelo. I pacchetti di provisioning ora supportano anche un campo per la registrazione in gestione dispositivi, quindi non è disponibile alcuna configurazione manuale dopo il provisioning.

Per provare:

1. Scaricare la versione più recente di Windows Configuration designer da Windows Store nel PC.
1. Selezionare **provision HoloLens Devices**  >  **provision HoloLens 2 Devices**.
2. Creare il profilo di configurazione. Copiare quindi tutti i file creati in un dispositivo di archiviazione USB-C.
3. Inserire il dispositivo USB-C in qualsiasi HoloLens appena balenato. Quindi premere i **volume down**  +  pulsanti di**accensione** del volume per applicare il pacchetto di provisioning.

### Stato di installazione dell'applicazione line-of-business

La distribuzione e la gestione delle app MDM per le app line of business sono fondamentali per HoloLens. Gli amministratori e gli utenti devono visualizzare lo stato di installazione dell'app per il controllo e la diagnosi. In questa versione sono stati aggiunti altri **dettagli negli**  >  **account**di  >  **accesso o nell'Istituto di istruzione**,  >  **fare clic sulle informazioni dell'account**  >  **Info**.

### CSP e criteri aggiuntivi

Un [provider di servizi di configurazione (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) è un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione in un dispositivo. In questa versione aggiungiamo il supporto per altri criteri per aumentare gli amministratori dei controlli con i dispositivi HoloLens distribuiti. Per l'elenco dei CSP supportati da HoloLens, vedere [CSP di NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novità di questa versione:

**CSP Policy** 

Il provider di servizi di configurazione dei criteri consente all'organizzazione di configurare i criteri nei dispositivi Windows. In questa versione sono stati aggiunti nuovi criteri per HoloLens, elencati qui. Per altre informazioni, vedere [CSP dei criteri supportato da HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**CSP NetworkQoSPolicy**

Il provider di servizi di configurazione NetworkQoSPolicy Crea criteri QoS (Quality of Service) di rete. Un criterio QoS esegue un set di azioni sul traffico di rete basato su un set di condizioni corrispondenti. Per altre informazioni, Vedi [CSP di NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### Supporto Ethernet USB espanso per dispositivi cablati 5G/LTE

È stato aggiunto il supporto per consentire ad alcuni dispositivi mobili a banda larga, come i telefoni 5G/LTE e Wi-Fi minestroni, quando sono collegati al HoloLens 2 tramite USB. Questi dispositivi sono ora visualizzati in **impostazioni di rete** come un'altra connessione Ethernet. I dispositivi mobili a banda larga che richiedono un driver esterno non sono supportati. Questa funzionalità consente connessioni a larghezza di banda elevata quando Wi-Fi non è disponibile e Wi-Fi il tethering non è sufficiente. Per altre informazioni sui dispositivi USB supportati, vedere [connettersi a dispositivi Bluetooth e USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Miglioramenti per il rilevamento delle mani

Questa versione include diversi miglioramenti per il rilevamento delle mani:

- **Puntamento della stabilità della posa:** Il sistema ora resiste a piegare il dito indice quando viene nascosto dal palmo. Questa modifica migliora la precisione quando si preme un pulsante, si digita, si scorre il contenuto e altro ancora. 
- **Rubinetti ad aria accidentali ridotti:** È stata migliorata la rilevazione del gesto di tocco dell'aria. Ci sono ora meno attivazioni accidentali in diversi scenari comuni, ad esempio quando si rilasciano le mani verso i lati.
- **Cambiare l'affidabilità dell'utente:** Il sistema è ora più veloce e affidabile per l'aggiornamento delle dimensioni delle mani quando si condivide un dispositivo.
- **Sottrazione a mano ridotta:** È stata migliorata la gestione dei casi in cui sono presenti più di due mani in vista dei sensori. Se più persone stanno lavorando insieme, c'è una probabilità molto inferiore che la mano rilevata "salterà" dall'utente alla mano di qualcun altro nella scena.
- **Affidabilità del sistema:** È stato risolto un problema che causava il rilevamento delle mani per evitare di funzionare quando il dispositivo è a carico elevato.

### Modalità scuro

Molte app di Windows ora supportano sia le modalità buio che la luce. HoloLens 2 gli utenti possono scegliere la modalità predefinita per le app che supportano entrambe. Dopo l'aggiornamento, la modalità app predefinita è "scura", ma è possibile modificare facilmente questa impostazione: passare a **Impostazioni**di  >  **sistema**  >  **colori**  >  **scegliere la modalità app predefinita**. 

Queste app "in-box" supportano la modalità oscura: 

- Impostazioni 
- Microsoft Store 
- Mail 
- Calendario 
- Esplora file 
- Hub di Feedback 
- OneDrive 
- Foto 
- Visualizzatore 3D 
- Film e TV 

![Windows piastrellato in modalità scura](images/DarkMode.jpg)

### Comandi vocali di sistema

Ora puoi usare i comandi vocali con qualsiasi app nel dispositivo. Per altre informazioni, vedere [usare la voce per gestire HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Vedere anche [lingue supportate per HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### Aggiornamenti di Cortana

L'app aggiornata si integra con Microsoft 365 per facilitare l'uso dei tuoi dispositivi (attualmente in US-English solo). In HoloLens 2 Cortana non supporta più alcuni comandi specifici del dispositivo, ad esempio la regolazione del volume o il riavvio. Queste opzioni sono ora supportate dai nuovi comandi vocali di sistema. Leggi altre informazioni sulla nuova app Cortana nel [Blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### Miglioramenti e correzioni di qualità

Miglioramenti e correzioni anche nell'aggiornamento:  
- È stato introdotto un sistema di calibrazione display attivo. Questa caratteristica migliora la stabilità e l'allineamento degli ologrammi. Ora restano in posizione quando si sposta la testa da un lato all'altro.
- È stato risolto un bug in cui Wi-Fi lo streaming in HoloLens è stato interrotto periodicamente. Se un'applicazione indica che è necessario un flusso a bassa latenza, implementare la correzione chiamando la [funzione SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- È stato risolto un blocco del dispositivo che si è verificato durante lo streaming in modalità ricerca.
- È stato risolto un bug in cui in alcuni casi l'utente corretto non veniva visualizzato nella schermata di accesso quando si riprende una sessione.
- È stato risolto un problema per cui gli utenti non potevano esportare i log MDM tramite **le impostazioni**.
- È stato risolto un problema per cui l'accuratezza del rilevamento degli occhi subito dopo la configurazione fuori casella potrebbe essere inferiore al previsto.
- È stato risolto un problema per cui il sottosistema di rilevamento degli occhi non è riuscito ad inizializzare o eseguire la calibrazione in determinate condizioni.
- È stato risolto un problema per cui la calibrazione degli occhi veniva richiesta per un utente già calibrato.
- È stato risolto un problema per cui il driver si arrestava durante la calibrazione degli occhi.
- È stato risolto un problema per cui le pressioni ripetute del pulsante di alimentazione potrebbero causare un arresto anomalo del sistema di 60 secondi e Shell.
- Stabilità migliorata per i buffer di profondità.
- È stato aggiunto un pulsante **Condividi** nell'hub di feedback in modo che gli utenti possano condividere più facilmente il feedback.
- È stato risolto un bug in cui RoboRaid WAN è stato installato correttamente.

### Problemi noti

- Un problema con il linguaggio di sistema zh-CN impedisce ai comandi vocali di acquisire un'acquisizione di realtà mista o di visualizzare l'indirizzo IP del dispositivo.
- Un problema richiede l'avvio dell'app Cortana dopo l'avvio del dispositivo per l'uso dell'attivazione vocale "Hey Cortana". Se l'aggiornamento è stato aggiornato da una build di 18362, è possibile che venga visualizzato anche un secondo riquadro dell'app per la versione precedente dell'app Cortana che non funziona più in **Start**.

## Windows olografico, versione 1903-maggio 2020 Update 
- Build 18362,1061

Questo aggiornamento di qualità mensile non contiene modifiche importanti perché il team stava lavorando alla versione olografica di Windows 2004 può essere aggiornato, come descritto in precedenza.

## Windows olografico, versione 1903-aprile 2020 Update
- Build 18362,1059

**Modalità oscura per le app supportate** 

Molte app di Windows supportano sia la modalità oscura che quella Light. HoloLens 2 i clienti possono ora scegliere la modalità predefinita per le app che supportano entrambe le combinazioni di colori. In base al feedback dei clienti, la modalità app predefinita viene impostata su "scuro", ma è possibile modificare facilmente questa impostazione in qualsiasi momento: passare a **impostazioni > sistema > colori** per trovare **"Scegli la modalità app predefinita".**

Queste app "in-box" supportano la modalità oscura:
- Impostazioni
- Microsoft Store
- Mail
- Calendario
- Esplora file
- Hub di Feedback
- OneDrive
- Foto
- Visualizzatore 3D
- Film e TV

**Miglioramenti e correzioni anche nell'aggiornamento:** 
- Assicurati che le sovrapposizioni di shell siano incluse in acquisizioni di realtà miste.
- Gli sviluppatori irreali ora possono usare la pagina della visualizzazione 3D in Device Portal per testare e eseguire il debug delle proprie applicazioni.
- Migliorata la stabilità degli ologrammi nell'acquisizione di realtà mista quando viene usato l'algoritmo *DepthReprojection HolographicDepthReprojectionMethod* .
- È stato risolto l'errore "WinRT IStreamSocketListener API non registrata" nelle app ARM a 32 bit.

## Windows olografico, versione 1903-marzo 2020 Update 
- Build 18362,1056

Miglioramenti e correzioni nell'aggiornamento:

- Migliorata la stabilità degli ologrammi nell'acquisizione di realtà mista quando viene usato l'algoritmo *Autoplanare HolographicDepthReprojectionMethod* .
- Verificare che il sistema di coordinate allegato a un esempio di profondità MF sia coerente con la documentazione pubblica.
- Migliorata la produttività degli sviluppatori, consentendo ai clienti di incollare grandi quantità di testo attraverso il portale dei dispositivi.

## Windows olografico, versione 1903-febbraio 2020 Update 
- Build 18362,1053

Miglioramenti e correzioni nell'aggiornamento:

- Disabilita temporaneamente l'API HolographicSpace. UserPresence per le applicazioni Unity. Questa modifica evita un problema che ha causato la sospensione di alcune app quando la visiera è stata capovolta, anche se l'impostazione "Esegui in background" è stata abilitata.
- È stato risolto un arresto anomalo di HUP causato dal rilevamento manuale, in cui l'utente ha notato un blocco dell'interfaccia utente e poi torna alla shell dopo alcuni secondi.
- Migliorate il rilevamento delle mani in modo che quando si tocca il dito indice, la parte superiore del dito è meno probabile che si arriccia improvvisamente.
- Maggiore affidabilità del rilevamento della testa, del mapping spaziale e di altri Runtime.

## Windows olografico, versione 1903-gennaio 2020 Update 
- Build 18362,1043
 
Miglioramenti e correzioni nell'aggiornamento:

- Stabilità migliorata per le app esclusive quando si lavora con l'emulatore di HoloLens 2.

## Windows olografico, versione 1903-dicembre 2019 Update 
- Build 18362,1042

Miglioramenti e correzioni nell'aggiornamento:

- È stata introdotta la riproduzione di ultima fase (LSR). È stato migliorato il rendering visivo degli ologrammi per apparire più stabile e nitido con una contabilità più accurata per la profondità. Questo sintomo sarà più evidente dopo questo aggiornamento se le app non impostano correttamente la profondità degli ologrammi.
- Stabilità fissa delle app esclusive e spostamento tra app esclusive.
- Risolto un problema per cui l'acquisizione di realtà mista non poteva registrare il video dopo che il dispositivo era in stato di standby per diversi giorni.
- Migliorata la stabilità degli ologrammi.

## Windows olografico, versione 1903-novembre 2019 Update 
- Build 18362,1039

Miglioramenti e correzioni nell'aggiornamento:

- Funzionalità fisse di **selezionare** i comandi vocali durante la configurazione iniziale per en-CA e en-au.
- Migliorata la qualità visiva degli oggetti collocati in modo distante nelle versioni più recenti Unity e Mixed Reality Toolkit (MRTK).
- Problemi di indirizzamento corretti con le applicazioni olografiche che si bloccano in uno stato in pausa all'avvio fino all'apertura del menu Start e quindi chiuse.
- Correzioni e miglioramenti alla conformità di runtime di OpenXR per HoloLens 2 e l'emulatore.
