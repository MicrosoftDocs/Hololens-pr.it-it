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
ms.date: 9/23/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: caf860ad5926c03d1e87e829f04838531510df51
ms.sourcegitcommit: 44de31c6d3534b6e0b73ddc2a9336147daf7a41d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "11078384"
---
# Insider Preview per Microsoft HoloLens

Benvenuti alle build di insider Preview più recenti per HoloLens! È facile [iniziare e dare](hololens-insider.md#start-receiving-insider-builds) un valido feedback per il nostro prossimo aggiornamento per il sistema operativo principale per HoloLens.

## Note sulla versione di Windows Insider

Ecco l'elenco delle caratteristiche future che puoi provare oggi in Windows Insider Build.

| Funzionalità                                                | Descrizione                                                                                    | Disponibile nelle build Insider |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [Supporto per la posizione degli occhi automatici](hololens-insider.md#auto-eye-position-support)                              | Trova attivamente le posizioni degli occhi e consente il posizionamento accurato degli ologrammi.                        | 19041.1339 +                 |
| [Gestione certificati](hololens-insider.md#certificate-manager)                                     | Gli utenti possono visualizzare, installare e rimuovere certificati gli utenti correnti e i certificati del computer locale nell'app Impostazioni.                                         | 19041.1361 +                 |
| [Avvio automatico del provisioning da USB](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE rileva automaticamente i pacchetti di provisioning sulle unità USB.                                | 19041.1361 +                 |
| [Convalidare automaticamente i pacchetti di provisioning in OOBE](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | Applicare automaticamente i pacchetti di provisioning in OOBE.                                             | 19041.1361 +                 |
| [Uso di Autopilot con connessione Wi-Fi](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | Usare il pilota automatico da Wi-Fi per dispositivi senza bisogno di un adattatore Ethernet.                             | 19041.1364 +                 |
|[Tenantlockdown CSP e Autopilot](hololens-insider.md#tenantlockdown-csp-and-autopilot) | Dopo la registrazione del tenant e il criterio viene applicato, il dispositivo può essere registrato solo in tale tenant ogni volta che il dispositivo viene reimpostato o reinizializzato. | 19041.1366 +|
| [Accesso assegnato globale](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | Configura il dispositivo HoloLens 2 per la modalità Kiosk di più app applicabile a livello di sistema. | 19041.1356 +                 |
| [Avvio automatico di un'app nel chiosco multi-app](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | Imposta l'avvio automatico di un'applicazione durante l'accesso a una modalità Kiosk a più app.     | 19041.1346 +                 |
| [Modifiche al comportamento della modalità Kiosk per la gestione degli errori](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Le modifiche apportate al modo in cui viene gestito l'errore della modalità Kiosk.                                              | 19041.1356 +                 |
| [Criteri HoloLens](hololens-insider.md#hololens-policies)                                      | Nuovi criteri per i dispositivi di realtà mista.                                                        | 19041.1349 +                 |
| [Appartenenza al gruppo della cache AAD per il chiosco offline](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | Criteri per il numero di giorni in cui è consentito usare la cache di appartenenza al gruppo AAD per la modalità Kiosk.    | 19041.1356 +                 |
| [Nuovi criteri di restrizione dei dispositivi per HoloLens 2](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | Criteri di gestione dei dispositivi abilitati per la nuova abilitazione per HoloLens 2.                               | 19041.1349 +                 |
| [Nuovi criteri di alimentazione per HoloLens 2](hololens-insider.md#new-power-policies-for-hololens-2)                      | Nuovi criteri supportati per le impostazioni di Power timeout.                                           | 19041.1349 +                 |
| [Criteri di aggiornamento](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | Criteri appena abilitati che consentono il controllo degli aggiornamenti.                                            | 19041.1352 +                 |
| [Visibilità della pagina impostazioni abilitate per HoloLens 2](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | Criteri per selezionare le pagine visualizzate nell'app Impostazioni.                                           | 19041.1349 +                 |
|  [Modalità ricerca](hololens-insider.md#research-mode) | Uso della modalità ricerca in HoloLens 2 | 19041.1375 + |
| [Miglioramenti e correzioni nell'aggiornamento](hololens-insider.md#improvements-and-fixes-in-the-update)                   | Correzioni aggiuntive nell'aggiornamento.                                                                | 19041.1361 +                 |


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

### Gestione certificati

In Windows Insider Build 19041.1361 + aggiungiamo un gestore di certificati nell'app impostazioni di HoloLens 2. Accedere a **impostazioni > aggiornare i certificati di > di sicurezza &**. Questa funzionalità consente di visualizzare, installare e rimuovere certificati nel dispositivo in modo semplice e intuitivo. Con il nuovo gestore di certificati, gli amministratori e gli utenti hanno ora strumenti di controllo, diagnosi e convalida migliorati per garantire che i dispositivi rimangano sicuri e conformi. 

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

### Avvio automatico del provisioning da USB
Prima che gli utenti della build dovessero avviare manualmente la schermata di provisioning durante la configurazione guidata per il provisioning tramite una combinazione di pulsanti. Ora gli utenti possono ignorare la combinazione di pulsanti usando un pacchetto di provisioning in un'unità di archiviazione USB. 

1. Collegare l'unità USB con il pacchetto di provisioning durante il primo momento interattivo di OOBE
1. Quando il dispositivo è pronto per essere eseguito il provisioning, verrà aperto automaticamente il prompt con la pagina provisioning. 

> [!NOTE]
> Se un drive USB viene lasciato collegato mentre il dispositivo è in fase di avvio, la configurazione guidata enumera il dispositivo di archiviazione USB esistente, oltre a guardare per altre persone collegate.

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

### Uso di Autopilot con connessione Wi-Fi
Ora, durante la configurazione di OOBE, dopo la connessione di HoloLens 2 con WiFi, OOBE verificherà il profilo di un pilota automatico per il dispositivo. Se ne viene trovata una, verrà usata per completare il resto del flusso di partecipazione e registrazione di AAD. In altre parole, l'uso di Ethernet per USB C o WiFi per l'adattatore USB C non è più un requisito, ma continueranno a funzionare se forniti all'inizio della configurazione guidata. Leggi altre informazioni su [Autopilot per dispositivi HoloLens 2](hololens2-autopilot.md).

### Tenantlockdown CSP e Autopilot
I dispositivi HoloLens 2 supportano ora TenantLockdown CSP come Windows Insider Build 19041.1366 +. 

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

### Accesso assegnato globale-modalità Kiosk
Questa nuova funzionalità consente all'amministratore IT di configurare un dispositivo HoloLens 2 per la modalità Kiosk di più app, applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che accedono al dispositivo. Per [informazioni dettagliate, vedere](hololens-global-assigned-access-kiosk.md)questa nuova funzionalità.

### Avvio automatico di un'applicazione in modalità Kiosk con più app 
Si applica solo alla modalità Kiosk in più app e può essere designata solo 1 app per l'avvio automatico con l'attributo evidenziato di seguito nella configurazione di Access assegnati. 

L'applicazione viene avviata automaticamente quando l'utente effettua l'accesso. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Modifiche al comportamento della modalità Kiosk per la gestione degli errori

In precedenza, quando si verificano errori nell'applicazione della modalità Kiosk, HoloLens usato per visualizzare tutte le applicazioni nel menu Start. A partire da questa build di Windows Insider, in caso di errori, nessuna app verrà visualizzata nel menu Start, come indicato di seguito: 

![L'immagine della modalità Kiosk ora appare quando non riesce.](images/hololens-kiosk-failure-behavior.png )

#### Aggiornamenti
Gli aggiornamenti possono essere configurati anche per questo metodo, quindi, sebbene l'utente non stia installando tramite Microsoft Store, può comunque ricevere gli aggiornamenti. Gli aggiornamenti possono essere configurati in base all'app avviare o pianificata. Per altre informazioni su come configurarlo, [visitare questa pagina](https://docs.microsoft.com/windows/msix/app-installer/update-settings). 

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
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp) *

>[!NOTE]
> Per quanto riguarda [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp), HoloLens sosterrà solo la configurazione di/vendor/MSFT/RemoteLock/Lock. Le configurazioni che gestiscono il PIN, ad esempio Reset e ripristino, non sono supportate.

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

> [!NOTE]
> Per un'esperienza coerente su HoloLens 2, assicurati che i valori di DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery siano impostati come stesso valore. Lo stesso vale per DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Per altri dettagli sulla modalità standby moderna, vedere [visualizzare, dormire e sospendere i timer di ozio](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### Criteri di aggiornamento appena abilitati per HoloLens
Questi criteri di aggiornamento sono ora abilitati nei dispositivi HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### Visibilità della pagina impostazioni abilitate per HoloLens 2
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

### Miglioramenti e correzioni nell'aggiornamento:
- Criteri aggiornati per disabilitare l'enumerazione delle funzioni USB tramite MDM per NCM per AllowUsbConnection.
- Più schermate in OOBE ora sono in modalità oscura.
- Per altre informazioni, vedere l'informativa sulla privacy più recente online.
- È stato risolto un problema per cui gli utenti non potevano eseguire il provisioning dei profili VPN tramite pacchetti.
- È stato risolto un problema che impediva a un dispositivo HoloLens di essere visualizzato in Esplora file tramite il protocollo MTP (Media Transfer Protocol) quando il dispositivo è configurato come [chiosco di app singole](hololens-kiosk.md). Tieni presente che MTP (e la connessione USB in generale) possono comunque essere disabilitati usando i criteri di [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .

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
