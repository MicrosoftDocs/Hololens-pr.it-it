---
title: Note sulla versione di HoloLens 2
description: Mantieniti aggiornato con tutti gli aggiornamenti in ogni nuova versione di HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 7ab8eede6e48ed1a6cb4584188a80adbd832c169
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340555"
---
# Note sulla versione di HoloLens 2

Per garantire un'esperienza produttiva con i dispositivi HoloLens, microsoft continua a rilasciare aggiornamenti di funzionalità, bug e sicurezza. In questa pagina puoi vedere le novità di HoloLens ogni mese. Per ottenere l'aggiornamento più recente di HoloLens 2, puoi controllare la disponibilità di aggiornamenti e aggiornarti manualmente oppure ottenere l'aggiornamento flash completo (FFU) per lampeggiare il dispositivo tramite [Advanced Recovery Companion.](hololens-recovery.md#clean-reflash-the-device) [](hololens-update-hololens.md#check-for-updates-and-manually-update) Il [download](https://aka.ms/hololens2download) viene mantenuto aggiornato e fornisce la build più recente disponibile a livello generale.

>[!NOTE]
> Siamo contenti di iniziare di nuovo a eseguire la distribuzione di nuove funzionalità per i windows insider. Per gli aggiornamenti più recenti, il canale dev verrà in esecuzione sul Canale di sviluppo. Man mano che aggiungiamo altre funzionalità e aggiornamenti alle build di Windows Insider, continueremo a visualizzare le note di [**HoloLens Insider.**](hololens-insider.md) Prepararsi a combinare questi aggiornamenti nella realtà.

Consultare le note sulla versione correlate:

- [Visita l'archivio dell'emulatore di HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## Windows Holographic, versione 20H2 - Aggiornamento di febbraio 2021
- Build 19041.1136

Miglioramenti e correzioni nell'aggiornamento:

- Risolve un problema relativo alla configurazione iniziale del dispositivo e agli aggiornamenti delle app dello Store.
- Risolve un problema relativo agli aggiornamenti e ai voli per le versioni successive di HoloLens.
- Sono stati rimossi i certificati preinstallati inutilizzati dall'archivio radice eSIM dai dispositivi HoloLens.

## Windows Holographic, versione 1903 - Aggiornamento di febbraio 2021
- Build 18362.1098

Questo aggiornamento qualitativo mensile non contiene modifiche di questo tipo, ti invitiamo a provare le build più recenti per Windows Holographic, versione 2004.

## Windows Holographic, versione 20H2 - Aggiornamento di gennaio 2021
- Build 19041.1134

Miglioramenti e correzioni nell'aggiornamento:

- Prestazioni migliorate durante l'avvio, la ripresa e il cambio utente quando sono presenti molti utenti nel dispositivo.
- È stato aggiunto il supporto arm32 per [la modalità di ricerca.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## Windows Holographic, versione 1903 - Aggiornamento di gennaio 2021
- Build 18362.1091

Questo aggiornamento qualitativo mensile non contiene modifiche di questo tipo, ti invitiamo a provare le build più recenti per Windows Holographic, versione 2004.

## Windows Holographic, versione 20H2 - Aggiornamento di dicembre 2020
- Build 19041.1131

### Installare app in HoloLens 2 tramite il programma di installazione app

We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices. La funzionalità sarà **attivata per impostazione predefinita per i dispositivi non gestiti.** Per evitare interruzioni per le aziende, il programma di installazione app non sarà disponibile **per i dispositivi** gestiti in questo momento.  

Un dispositivo viene considerato "gestito" se **si** verifica una delle condizioni seguenti:
- MDM [registrato](hololens-enroll-mdm.md)
- Configurato con il [pacchetto di provisioning](hololens-provisioning.md)
- [L'identità utente](hololens-identity.md) è Azure AD

Ora puoi installare app senza dover abilitare la modalità sviluppatore o usare Device Portal.  Scarica semplicemente (tramite USB o tramite Edge) il bundle Appx nel dispositivo e passa al bundle Appx in Esplora file per chiedere di avviare l'installazione.  In alternativa, [avviare un'installazione da una pagina Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Proprio come le app installate da Microsoft Store o il sideload tramite la funzionalità di distribuzione [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) di app [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) LOB di MDM, le app devono essere firmate digitalmente con lo strumento di firma e il certificato usato per firmare deve essere considerato attendibile dal dispositivo HoloLens prima che l'app possa essere distribuita.

**Istruzioni per l'installazione dell'applicazione.**

1.  Assicurarsi che il dispositivo non sia considerato gestito
1.  Verificare che il dispositivo HoloLens 2 sia acceso e connesso al PC
1.  Assicurarsi di aver eseguito l'accesso al dispositivo HoloLens 2
1.  Nel PC passa alla tua app personalizzata e copia yourapp.appxbundle in yourdevicename\Internal Storage\Downloads.   Dopo aver completato la copia del file, puoi disconnettere il dispositivo
1.  Nel dispositivo HoloLens 2 apri il menu Start, seleziona Tutte le app e avvia l'app Esplora file.
1.  Passare alla cartella Download. Nel pannello sinistro dell'app potrebbe essere necessario selezionare prima questo dispositivo, quindi passare a Download.
1.  Seleziona il file yourapp.appxbundle.
1.  Verrà avviato il programma di installazione app. Seleziona il pulsante Installa per installare l'app.
L'app installata verrà avviata automaticamente al termine dell'installazione.

Puoi trovare app di esempio su [GitHub di](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) esempi universali di Windows per testare questo flusso.

Informazioni sul processo completo di installazione [delle app in HoloLens 2 con il programma di installazione app.](app-deploy-app-installer.md)  

![Installazione di esempi MRTK tramite il programma di installazione app](images/hololens-app-installer-picture.jpg)

### Miglioramenti e correzioni nell'aggiornamento:

- Il tracciamento della mano ora mantiene il tracciamento in molti nuovi casi in cui la mano in precedenza sarebbe stata persa.  In alcuni di questi nuovi casi, solo la posizione del palmo continua ad aggiornarsi in base alla mano reale dell'utente, mentre le altre giunzioni vengono dedote in base a una posizione precedente.  Questa modifica consente di migliorare la coerenza di tracciabilità nei movimenti, ad esempio schiaffi, lancio, ambito e clapping.  È utile anche nei casi in cui la mano è vicina a una superficie o contiene un oggetto.  Quando vengono dedote le giunzioni della mano, il valore di accuratezza [per](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) giunzione verrà impostato su "Approximate" invece che su "High".
- È stato risolto un problema per cui la reimpostazione del PIN per gli account Azure AD mostrava un errore "Si è verificato un problema.
- Gli utenti dovrebbero vedere meno arresti anomali della Configurazione guidata dopo l'avvio quando avviano ET, Iris dall'app impostazioni, nuovo utente o avviso popup di notifica.
- Gli utenti devono avere un fuso orario corretto in uscita dalla Rubrica fuori rete.

## Windows Holographic, versione 1903 - Aggiornamento di dicembre 2020
- Build 18362.1088

Questo aggiornamento qualitativo mensile non contiene alcuna modifica importante, ti invitiamo a provare la versione più recente di Windows Holographic, versione 20H2 - Aggiornamento di dicembre 2020 e la nuova funzionalità del programma di installazione app aggiunta nella build.


## Windows Holographic, versione 20H2
- Build 19041.1128

Windows Holographic, versione 20H2 è ora disponibile e offre un'ottima serie di nuove funzionalità agli utenti e ai professionisti IT di HoloLens 2. Dal posizionamento automatico degli occhi, a Gestione certificati in Impostazioni, alle funzionalità migliorate della modalità tutto schermo e alle nuove funzionalità di configurazione di Autopilot. Questo nuovo aggiornamento consente ai team IT di assumere un controllo più granulare per la configurazione e la gestione dei dispositivi HoloLens e offre agli utenti esperienze olografiche ancora più semplici. 

Questa versione più recente è un aggiornamento mensile alla versione 2004, ma questa volta sono incluse nuove funzionalità. Il numero di build principale rimarrà lo stesso e Windows Update indicherà un rilascio mensile alla versione 2004 (build 19041). Puoi esaminare il numero di build nella schermata Impostazioni > Informazioni su per confermare di essere sulla build più recente disponibile 19041.1128+. Per eseguire l'aggiornamento alla versione più recente, apri l'app Impostazioni, passa a Aggiornamento & Sicurezza e tocca Verifica disponibilità aggiornamenti. Per altre informazioni su come gestire gli aggiornamenti di HoloLens, visita [questa pagina.](https://docs.microsoft.com/hololens/hololens-updates)

### Novità di Windows Holographic, versione 20H2  

| Funzionalità                                              | Descrizione                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Supporto per Posizione automatica degli occhi](hololens-release-notes.md#auto-eye-position-support) | Calcola attivamente le posizioni degli occhi senza che gli utenti si sottosezionano alla calibrazione del tracciamento oculare.   |
| [Gestione certificati](hololens-release-notes.md#certificate-manager)   | Consente nuovi metodi più semplici per installare e rimuovere certificati dall'app Impostazioni.     |
| [Provisioning ad avvio automatico da USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | I pacchetti di provisioning nelle unità USB richiede automaticamente la pagina di provisioning nella Configurazione automatica.                                                         |
| [Conferma automatica dei pacchetti di provisioning nella Configurazione automatica](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | I pacchetti di provisioning vengono applicati automaticamente durante la configurazione automatica dalla pagina di provisioning.                                                         |
| [Provisioning automatico senza usare l'interfaccia utente](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Come combinare l'avvio automatico del provisioning e la conferma automatica. |
| [Utilizzo di Autopilot con Wi-Fi connessione](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Usa autopilot da dispositivi Wi-Fi senza la necessità di una scheda ethernet. |
| [Tenantlockdown CSP e Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Dopo l'applicazione della registrazione del tenant e dell'applicazione del criterio, il dispositivo può essere registrato nel tenant solo ogni volta che il dispositivo viene reimpostato o ripristinato. |
| [Accesso assegnato globale](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nuovo metodo di configurazione per la modalità tutto schermo per più app che applica il chiosco multimediale a livello di sistema, rendendolo applicabile a tutti.                  |
| [Avviare automaticamente un'app in chiosco multimediale con più app](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Imposta l'avvio automatico di un'applicazione quando si accede a una modalità tutto schermo con più app.                                                        |
| [Modifiche al comportamento della modalità tutto schermo per la gestione degli errori](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | L'errore della modalità tutto schermo ha ora un fallback restrittivo.                                                                                                |
| [Criteri di HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nuovi criteri per HoloLens.     |
| [Memorizzare nella cache l'appartenenza ai gruppi di Azure AD per chiosco offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | I nuovi criteri consentono agli utenti di usare la cache di appartenenza ai gruppi per usare la modalità tutto schermo offline per un numero di giorni impostato.                                        |
| [Nuovi criteri di restrizione dei dispositivi per HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Criteri di gestione dei dispositivi abilitati per HoloLens 2.                                                                                |
| [Nuovi criteri di risparmio energia per HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nuovi criteri supportati per le impostazioni di timeout di alimentazione.  |
| [Criteri di aggiornamento](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Nuovi criteri abilitati che consentono il controllo degli aggiornamenti.           |
| [Visibilità della pagina Impostazioni abilitate per HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Criteri per selezionare le pagine visibili nell'app Impostazioni.             |
| [Modalità di ricerca](hololens-release-notes.md#research-mode) | Uso della modalità ricerca in HoloLens 2. |
| [Lunghezza registrazione aumentata](hololens-release-notes.md#recording-length-increased) | Le registrazioni MRC non hanno più un massimo di 5 minuti. |
| [Miglioramenti e correzioni nell'aggiornamento](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correzioni aggiuntive nell'aggiornamento.   |

### Supporto per Posizione automatica degli occhi

In HoloLens 2, le posizioni degli occhi consentono un posizionamento accurato dell'ologramma, un'esperienza visiva confortevole e una migliore qualità di visualizzazione. Le posizioni degli occhi vengono calcolate internamente come parte del calcolo del tracciamento oculare. Tuttavia, questo richiede a ogni utente di passare alla calibrazione della verifica degli occhi, anche quando l'esperienza potrebbe non richiedere l'input sguardo fisso.

**Posizione automatica degli occhi** consente di calcolare la posizione degli occhi per l'utente, in una modalità priva di interazione. Posizione automatica degli occhi inizia a funzionare automaticamente in background dal momento in cui l'utente accende il dispositivo. Se l'utente non ha una calibrazione preventiva degli occhi, Posizione automatica degli occhi inizierà a fornire le posizioni degli occhi dell'utente al sistema di visualizzazione dopo un tempo di elaborazione di 20-30 secondi. I dati dell'utente non vengono conservati sul dispositivo e quindi questo processo viene ripetuto se l'utente toglie e rimette il dispositivo o se il dispositivo si riavvia o si riattiva dalla modalità sospensione.

Quando un utente non calibrato indossa il dispositivo, ci sono alcune modifiche al comportamento del sistema della funzionalità Posizione automatica degli occhi. In questo contesto, un utente non calibrato fa riferimento a una persona che non ha superato il processo di calibrazione del rilevamento degli occhi nel dispositivo in precedenza.

| Applicazione attiva | Comportamento precedente | Comportamento da Windows Holographic, versione 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| App sguardo fisso non abilitata o Holographic Shell |Viene visualizzata la finestra di dialogo di richiesta della calibrazione degli occhi. | Non viene visualizzata alcuna richiesta. |
| App sguardo fisso abilitata | Viene visualizzata la finestra di dialogo di richiesta della calibrazione degli occhi. | La richiesta di calibrazione degli occhi viene visualizzata solo quando l'applicazione accede al flusso dello sguardo fisso. |

Se l'utente passa da un'applicazione non abilitata allo sguardo fisso a una che accede ai dati sullo sguardo fisso, verrà visualizzata una richiesta di calibrazione. 

Tutti gli altri comportamenti del sistema saranno simili a quando l'utente corrente non ha una calibrazione attiva per la verifica degli occhi. Ad esempio, il gesto iniziale con una sola mano non verrà abilitato. Per la configurazione iniziale, non ci sarà alcun cambiamento nell'esperienza di configurazione guidata.

Per le esperienze che richiedono dati sullo sguardo fisso o un posizionamento olografico molto preciso, è consigliabile che gli utenti non calibrati eseguano la calibrazione del tracciamento oculare. È accessibile dalla richiesta di calibrazione degli occhi o avviando l'app Impostazioni dal menu Start, quindi selezionando **Sistema > Calibrazione > Calibrazione degli occhi > Esegui calibrazione degli occhi**.

Queste informazioni sono disponibili in un secondo momento con [altre informazioni sulla calibrazione.](hololens-calibration.md#auto-eye-position-support) 

### Gestione certificati

- Strumenti di controllo, diagnosi e convalida migliorati per la sicurezza e la conformità dei dispositivi tramite il nuovo Gestore certificati. Questa funzionalità consente di distribuire, risolvere i problemi e convalidare i certificati su vasta scala in ambienti commerciali.

In Windows Holographic versione 20H2, stiamo aggiungendo un Gestore certificati nell'app Impostazioni di HoloLens 2. Passare a **Impostazioni > aggiornamento & sicurezza > certificati**. Questa funzionalità offre un modo semplice e semplice per visualizzare, installare e rimuovere certificati nel dispositivo. Con il nuovo Gestore certificati, gli amministratori e gli utenti ora dispongono di strumenti di controllo, diagnosi e convalida migliorati per garantire che i dispositivi rimangano sicuri e conformi. 

-   **Controllo:** Possibilità di convalidare che un certificato sia stato distribuito correttamente o di confermare che sia stato rimosso in modo appropriato. 
-   **Diagnosi:** Quando si verificano problemi, la convalida dell'esistenza dei certificati appropriati nel dispositivo consente di risparmiare tempo e di risolvere i problemi. 
-   **Convalida:** La verifica che un certificato si adequa allo scopo previsto e funzioni, può risparmiare tempo significativo, in particolare negli ambienti commerciali prima di distribuire i certificati su larga scala.

Per trovare rapidamente un certificato specifico nell'elenco, sono disponibili opzioni per ordinare in base al nome, all'archivio o alla data di scadenza. Gli utenti possono anche cercare direttamente un certificato. Per visualizzare le singole proprietà del certificato, selezionare il certificato e fare clic su **Informazioni.** 

L'installazione dei certificati attualmente supporta i file con estensione cer e crt. I proprietari dei dispositivi possono installare certificati nel computer locale e nell'utente corrente;  Tutti gli altri utenti possono eseguire l'installazione solo nell'utente corrente. Gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia utente impostazioni. Se un certificato è stato installato con altri mezzi, deve essere rimosso anche dallo stesso meccanismo.

#### Per installare un certificato: 

1.  Connettere HoloLens 2 a un PC.
1.  Posizionare il file di certificato che si desidera installare in un percorso in HoloLens 2.
1.  Passa a **Impostazioni app > Aggiornamento & sicurezza > certificati**e seleziona Installa un certificato.
1.  Fare **clic su Importa file** e passare al percorso in cui è stato salvato il certificato.
1.  Seleziona **Posizione dello Store.**
1.  Selezionare **Archivio certificati.**
1.  Fai clic su **Installa**.

Il certificato dovrebbe ora essere installato nel dispositivo.

#### Per rimuovere un certificato: 
1. Passare a **Impostazioni App > Aggiornamento e sicurezza > certificati**.
1. Cercare il certificato per nome nella casella di ricerca.
1. Selezionare il certificato.
1. Fare **clic su Rimuovi**
1. Selezionare **Sì** quando viene richiesta la conferma.

![Visualizzatore certificati nell'app Impostazioni](images/certificate-viewer-device.jpg)

![Immagine che mostra come usare l'interfaccia utente del certificato per installare un certificato](images/certificate-device-install.jpg)

Queste informazioni sono disponibili più avanti [in una nuova pagina di Gestione certificati.](certificate-manager.md)

### Provisioning ad avvio automatico da USB

- Processi automatizzati che consentono una minore interazione dell'utente, quando le unità USB con pacchetti di provisioning vengono usate durante la configurazione automatica.

Prima di questa versione, gli utenti dovevano avviare manualmente la schermata di provisioning durante la Configurazione manuale per eseguire il provisioning usando una combinazione di pulsanti. Ora gli utenti possono ignorare la combinazione di pulsanti usando un pacchetto di provisioning in un'unità di archiviazione USB. 

1. Collega l'unità USB con il pacchetto di provisioning durante il primo momento di interazione della Configurazione guidata
1. Quando il dispositivo è pronto per il provisioning, viene aperta automaticamente la richiesta con la pagina di provisioning. 

Nota: se un'unità USB viene lasciata collegata durante l'avvio del dispositivo, la Configurazione guidata enumererà il dispositivo di archiviazione USB esistente, oltre a controllare eventuali altri dispositivi collegati.

Per ulteriori informazioni sull'applicazione di pacchetti di provisioning durante la configurazione manuale, visitare la documentazione [relativa al provisioning di HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Ulteriori informazioni sul [provisioning di avvio automatico da un'unità USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) sono disponibili nella documentazione relativa al provisioning di HoloLens.

### Conferma automatica dei pacchetti di provisioning nella Configurazione automatica
- Processo automatizzato che consente una minore interazione dell'utente, quando viene visualizzata la pagina Pacchetto di provisioning, verranno applicati automaticamente tutti i pacchetti elencati.

Quando viene visualizzata la schermata principale del provisioning, la Configurazione fuori sede contarà per 10 secondi prima di iniziare automaticamente ad applicare tutti i pacchetti di provisioning. Gli utenti possono [comunque confermare o annullare](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) entro questi 10 secondi dopo aver verificato i pacchetti previsti.

### Provisioning automatico senza usare l'interfaccia utente
- Processi automatici combinati per interazioni con dispositivi ridotte per il provisioning. 

Combinando l'avvio automatico del provisioning dai dispositivi USB e la conferma automatica dei pacchetti di provisioning, un utente può effettuare automaticamente il provisioning dei dispositivi HoloLens 2 senza usare l'interfaccia utente del dispositivo o persino indossare il dispositivo. Puoi continuare a usare la stessa unità USB e lo stesso pacchetto di provisioning per più dispositivi. Ciò è utile per la distribuzione di più dispositivi contemporaneamente nella stessa area. 

1. [Creare un pacchetto di provisioning](hololens-provisioning.md) con Progettazione configurazione di [Windows.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Copia il pacchetto in un'unità di archiviazione USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build.](https://aka.ms/hololens2previewdownload) 
1. Quando [Advanced Recovery Companion ha](https://www.microsoft.com/store/productId/9P74Z35SFRS8) completato il flashing del dispositivo, scollega il cavo USB-C. 
1. Collega l'unità USB al dispositivo.
1. Quando il dispositivo HoloLens 2 si avvia nella Configurazione guidata, rileverà automaticamente il pacchetto di provisioning nell'unità USB e avvierà la pagina di provisioning.
1. Dopo 10 secondi il dispositivo applicherà automaticamente il pacchetto di provisioning. 

Il dispositivo è ora configurato e verrà [visualizzata la schermata Provisioning completato.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Utilizzo di Autopilot con Wi-Fi connessione
- È stata rimossa la necessità di adattatori USB-C per ridurre le esigenze hardware, riducendo le esigenze hardware, consentendo ad Autopilot di funzionare Wi-Fi dispositivi connessi.

Ora durante la configurazione automatica, dopo aver connesso HoloLens 2 con il Wi-Fi, la configurazione automatica controlla la presenza di un profilo Autopilot per il dispositivo. Se ne viene trovato uno, verrà usato per completare il resto del flusso di partecipazione e registrazione di AAD. In altre parole, l'uso di ethernet su USB-C o Wi-Fi per l'adattatore USB-C non è più un requisito, ma continuano a funzionare se forniti all'inizio della Configurazione fuori rete. Altre informazioni su [Autopilot per dispositivi HoloLens 2.](hololens2-autopilot.md)

### Tenantlockdown CSP e Autopilot
- Mantiene i dispositivi nel tenant dell'organizzazione bloccandoli al tenant anche tramite il ripristino o l’esecuzione del flashing del dispositivo, con maggiore sicurezza, impedendo la creazione di account tramite provisioning. 

I dispositivi HoloLens 2 ora supportano il provider di servizi di configurazione TenantLockdown a causa della versione [20H2 di Windows Holographic.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP consente a HoloLens 2 di essere collegato alla registrazione MDM usando solo Autopilot. Una volta che il nodo RequireNetworkInOOBE del CSP TenantLockdown è impostato sul valore true o false (inizialmente impostato) su HoloLens 2, quel valore rimane sul dispositivo nonostante la riesecuzione del flashing, gli aggiornamenti del sistema operativo e così via. 

Una volta che il nodo RequireNetworkInOOBE del CSP TenantLockdown è impostato su true in HoloLens 2, la Configurazione guidata attende a tempo indefinito che il profilo Autopilot venga scaricato e applicato correttamente, dopo la connettività di rete. 

Una volta che il nodo RequireNetworkInOOBE del CSP TenantLockdown è impostato su true in HoloLens 2, le seguenti operazioni non sono consentite in Configurazione guidata: 
- creazione di un utente locale usando il provisioning di runtime 
- esecuzione dell'operazione di aggiunta Azure AD tramite provisioning di runtime 
- selezione di chi possiede il dispositivo nell'esperienza di Configurazione guidata 

#### Come impostarlo usando Intune? 
1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato e specificare true per il nodo RequireNetworkInOOBE come mostrato di seguito.
Il valore OMA-URI deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Impostazione del blocco del tenant tramite OMA-URI](images/hololens-tenant-lockdown.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo al gruppo di dispositivi. 

1. Rendere il dispositivo HoloLens 2 membro del gruppo creato nel passaggio precedente e attivare la sincronizzazione.  

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Una volta che la configurazione del dispositivo viene applicata correttamente al dispositivo HoloLens 2, gli effetti di TenantLockdown saranno attivi.

#### Come si annulla RequireNetworkInOOBE di TenantLockdown in HoloLens 2 usando Intune? 
1. Rimuovere HoloLens 2 dal gruppo di dispositivi a cui è stata assegnata la configurazione di dispositivo precedente. 

1. Creare un profilo di configurazione del dispositivo basato su URI OMA personalizzato e specificare false per RequireNetworkInOOBE come mostrato di seguito. Il valore OMA-URI deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot dell'impostazione di RequireNetworkInOOBE su false tramite OMA URI in Intune](images/hololens-tenant-lockdown-false.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo al gruppo di dispositivi. 

1. Rendere il dispositivo HoloLens 2 membro del gruppo creato nel passaggio precedente e attivare la sincronizzazione.

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Una volta che la configurazione del dispositivo viene applicata correttamente al dispositivo HoloLens 2, gli effetti di TenantLockdown saranno inattivi. 

#### Cosa succederebbe durante la Configurazione guidata, se il profilo di Autopilot non viene assegnato a HoloLens dopo che TenantLockdown è stato impostato su true? 
La Configurazione guidata attenderà a tempo indefinito il download del profilo di Autopilot e verrà visualizzata la seguente finestra di dialogo. Per rimuovere gli effetti di TenantLockdown, il dispositivo deve essere registrato con il suo tenant originale usando solo Autopilot e RequireNetworkInOOBE deve essere disattivato, come descritto nel passaggio precedente, prima che le restrizioni introdotte da TenantLockdown CSP vengano rimosse. 

![Visualizzazione nel dispositivo per quando il criterio viene applicato al dispositivo.](images/hololens-autopilot-lockdown.png)

Queste informazioni sono ora disponibili insieme al resto di Autopilot in [CSP Tenantlockdown e Autopilot.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### Accesso assegnato globale - Modalità tutto schermo
- Riduzione della gestione delle identità per chiosco multimediale, abilitando il nuovo metodo Kiosk che applica la modalità tutto schermo a livello di sistema.

Questa nuova funzionalità consente a un amministratore IT di configurare un dispositivo HoloLens 2 per la modalità tutto schermo per più app, applicabile a livello di sistema, senza affinità con alcuna identità nel sistema e applicabile a tutti gli utenti che accodati al dispositivo. Informazioni dettagliate su questa nuova funzionalità nel chiosco di accesso assegnato globale [di HoloLens.](hololens-global-assigned-access-kiosk.md)

### Avvio automatico di un'applicazione in modalità tutto schermo con più app 
- Esperienza mirata con l'avvio automatico dell'app, aumentando ulteriormente le selezioni di interfaccia utente e app scelte per le esperienze in modalità tutto schermo.

Si applica solo alla modalità tutto schermo con più app e solo 1 app può essere designata per l'avvio automatico usando l'attributo evidenziato seguente nella configurazione accesso assegnato. 

L'applicazione viene avviata automaticamente all'accesso dell'utente. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Modifiche al comportamento della modalità tutto schermo per la gestione degli errori
- Modalità tutto schermo più sicura eliminando le app disponibili in caso di errori in modalità tutto schermo. 

In precedenza, quando si verificano errori durante l'applicazione della modalità tutto schermo, HoloLens mostrava tutte le applicazioni nel menu Start. Ora in Windows Holographic versione 20H2 in caso di errori nessuna app verrà visualizzata nel menu Start come indicato di seguito: 

![Immagine dell'aspetto della modalità tutto schermo in caso di errore.](images/hololens-kiosk-failure-behavior.png )

### Criteri di HoloLens
- Opzioni di gestione dei dispositivi specifiche per HoloLens create per la gestione del dispositivo. 

Sono stati creati nuovi criteri di realtà mista per i dispositivi HoloLens 2 in Windows Holographic versione 20H2. Le nuove impostazioni controllabili includono: l'impostazione della luminosità, l'impostazione del volume, la disabilitazione della registrazione audio nelle acquisizioni in realtà mista, l'impostazione quando è possibile raccogliere la diagnostica e la cache di appartenenza ai gruppi AAD.  

| Nuovi criteri di HoloLens                                | Descrizione                                                                               | Note                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Consente di disabilitare i pulsanti di luminosità in modo che la sua pressione non cambi la luminosità.       | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\VolumeButtonDisabled                  | Consente di disabilitare i pulsanti del volume in modo da non modificare il volume premendolo.               | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\MicrophoneDisabled                    | Disabilita il microfono in modo che non sia possibile registrare audio in HoloLens 2.                      | 1 Sì, 0 No (impostazione predefinita)                                                |
| MixedReality\FallbackDiagnostics                   | Controlla il comportamento del momento in cui è possibile raccogliere i log di diagnostica.                               | 0 Disabilitato, 1 Abilitato per i proprietari dei dispositivi, 2 Abilitato per tutti (impostazione predefinita) |
| MixedReality\HeadTrackingMode                      | Riservato per uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controlla il numero di giorni in cui viene usata la cache di appartenenza ai gruppi di Azure AD per i chioschi in modalità tutto schermo per i gruppi di Azure AD. | Vedi di seguito.                                                           |

### Memorizzare nella cache l'appartenenza ai gruppi di Azure AD per chiosco offline
- Abilitati i chioschi offline da usare con i gruppi di AAD per un massimo di 60 giorni.

Questo criterio controlla per quanti giorni la cache di appartenenza ai gruppi di Azure AD può essere usata per le configurazioni di accesso assegnato per i gruppi di Azure AD per l'utente connesso. Una volta impostato il valore del criterio solo su un valore maggiore di 0, la cache viene utilizzata in caso contrario.  

Nome: Valore URI AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 giorni  
Max - 60 giorni 

Passaggi per utilizzare correttamente questo criterio: 
1. Crea un profilo di configurazione del dispositivo per il chiosco multimediale per i gruppi di Azure AD e assegnalo ai dispositivi HoloLens. 
1. Crea una configurazione del dispositivo basata su URI OMA personalizzata che imposta il valore del criterio sul numero di giorni desiderato (> 0) e assegnalo ai dispositivi HoloLens. 
    1. Il valore URI deve essere immesso nella casella di testo URI OMA come ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Il valore può essere compreso tra min/max consentito.
1. Registrare i dispositivi HoloLens e verificare che entrambe le configurazioni siano applicate al dispositivo. 
1. Consentire l'accesso dell'utente di Azure AD 1 quando è disponibile Internet, dopo che l'utente ha eseguito l'accesso e l'appartenenza ai gruppi di Azure AD è stata confermata, verrà creata la cache. 
1. Ora l'utente 1 di Azure AD può portare HoloLens offline e usarlo per la modalità tutto schermo, purché il valore dei criteri consenta X numero di giorni. 
1. I passaggi 4 e 5 possono essere ripetuti per qualsiasi altro utente di Azure AD N. Il punto chiave qui è che qualsiasi utente di Azure AD deve accedere al dispositivo tramite Internet in modo che almeno una volta possiamo determinare che sono membri del gruppo di Azure AD a cui è destinata la configurazione del chiosco multimediale. 
 
> [!NOTE]
> Fino a quando non viene eseguito il passaggio 4 per un utente di Azure AD, si verifica un comportamento di errore menzionato negli ambienti "disconnessi". 

### Nuovi criteri di restrizione dei dispositivi per HoloLens 2
- Consente agli utenti di gestire criteri di gestione dei dispositivi specifici, ad esempio bloccando l'aggiunta o la rimozione di pacchetti di provisioning.

Nuovi criteri abilitati che consentono più opzioni di gestione dei dispositivi HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Questi due nuovi criteri per AllowAddProvisioningPackage e AllowRemoveProvisioningPackage vengono aggiunti alle restrizioni [dei dispositivi comuni.](hololens-common-device-restrictions.md)

> [!NOTE]
> Per quanto [riguarda RemoteLock,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)HoloLens supporterà solo la configurazione ./Vendor/MSFT/RemoteLock/Lock. Le configurazioni che gestiscono il PIN, ad esempio la reimpostazione e il ripristino, non sono supportate.

### Nuovi criteri di risparmio energia per HoloLens 2
- Altre opzioni per la sospensione o il blocco di HoloLens tramite i criteri di risparmio energia. 

Questi criteri appena aggiunti consentono agli amministratori di controllare gli stati di alimentazione, ad esempio il timeout di inattività. Per altre informazioni su ogni singolo criterio, fare clic sul collegamento per tale criterio.

|     Collegamento alla documentazione dei criteri                |     Note                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valore di esempio da usare in Progettazione configurazione di Windows, ad esempio  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Questi due nuovi criteri per DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn vengono aggiunti alle restrizioni [dei dispositivi comuni.](hololens-common-device-restrictions.md)

> [!NOTE]
> Per un'esperienza coerente in HoloLens 2, assicurarsi che i valori per DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery siano impostati sullo stesso valore. Lo stesso vale per DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Per ulteriori dettagli sullo standby moderno, vedere Visualizzare, sospensione e [ibernazione dei timer](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) inattivi.

### Criteri di aggiornamento appena abilitati per HoloLens
- Altre opzioni per l'installazione degli aggiornamenti o la disabilitazione del pulsante Sospendi aggiornamenti per garantire gli aggiornamenti.

Questi criteri di aggiornamento sono ora abilitati nei dispositivi HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Dettagli completi su questi criteri di aggiornamento e su come usarli per i dispositivi HoloLens sono disponibili qui in Gestire gli [aggiornamenti di HoloLens.](hololens-updates.md)

### Visibilità della pagina Impostazioni abilitate per HoloLens 2
- Maggiore controllo dell'interfaccia utente nell'app Impostazioni, che potrebbe essere confuso per mostrare una selezione limitata di pagine.

Ora abbiamo abilitato un criterio che consente agli amministratori IT di impedire che pagine specifiche nell'app Impostazioni di sistema siano visibili o accessibili oppure di farlo per tutte le pagine ad eccezione di quelle specificate. Per informazioni su come personalizzare completamente questa funzionalità, fare clic sul collegamento seguente.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Per sapere quali impostazioni di pagina è possibile personalizzare in HoloLens 2, visitare la [pagina URI delle impostazioni.](settings-uri-list.md) 
 
![Schermata dell'orario di attività che viene modificato nell'app Impostazioni](images/hololens-page-visibility-list.jpg)

### Modalità di ricerca
Mentre è in modalità di ricerca, HoloLens 2 diventa uno strumento potente per la ricerca di computer vision. Rispetto alle edizioni precedenti, la modalità di ricerca per HoloLens 2 presenta i vantaggi seguenti:
-   Oltre ai sensori esposti in modalità di ricerca HoloLens (prima generazione), ora forniamo l'accesso ai sensori IMU, tra cui un accelerometro, un giroscopio e un magnetometro.
-   HoloLens 2 offre nuove funzionalità che possono essere usate insieme alla modalità di ricerca. In particolare, l'accesso alle API di tracciamento manuale e tracciamento oculare articolate che possono offrire un set più ricco di esperimenti.

I ricercatori ora hanno la possibilità di abilitare la modalità di ricerca nei dispositivi HoloLens per accedere a tutti questi flussi di sensori di immagini non elaborati rivolti all'esterno. La modalità di ricerca per HoloLens 2 fornisce anche l'accesso alle letture di accelerometro, giroscopio e magnetometro. Per proteggere la privacy degli utenti, le immagini della fotocamera per il tracciamento oculare non sono disponibili tramite la modalità di ricerca, ma la direzione dello sguardo è disponibile tramite le API esistenti.

Per ulteriori dettagli [tecnici, vedere](https://docs.microsoft.com/windows/mixed-reality/research-mode) la documentazione relativa alla modalità di ricerca.

### Lunghezza registrazione aumentata
A causa del feedback dei clienti, abbiamo aumentato la durata di registrazione delle acquisizioni [in realtà mista.](holographic-photos-and-videos.md) Le acquisizioni in realtà mista non saranno più limitate a 5 minuti per impostazione predefinita, ma calcoleranno invece la lunghezza massima di registrazione in base allo spazio disponibile su disco. Il dispositivo stima la durata massima della registrazione video in base allo spazio su disco disponibile fino all'80% dello spazio totale su disco.

> [!NOTE]
> HoloLens userà la durata predefinita della registrazione video (5 minuti) se si verifica una delle condizioni seguenti:
> - La durata massima stimata per la registrazione è inferiore ai 5 minuti predefiniti.
> - Lo spazio su disco disponibile è inferiore al 20% dello spazio su disco totale.

Puoi trovare i requisiti completi nella nostra documentazione di foto e video [olografici.](holographic-photos-and-videos.md#maximum-recording-length) 

### Miglioramenti e correzioni nell'aggiornamento:
- Più schermate nella Procedura guidata sono ora in modalità scura.
- Ulteriori informazioni devono puntare all'ultima Informativa sulla privacy online.
- È stato risolto un problema per cui gli utenti non potevano effettuare il provisioning dei profili VPN tramite pacchetti di provisioning.
- Risolto un problema di configurazione proxy per la connessione VPN.
- Criteri aggiornati per disabilitare l'enumerazione delle funzioni USB tramite MDM per NCM per AllowUsbConnection.
- È stato risolto un problema che impediva la visualizzazione di un dispositivo HoloLens in Esplora file su MTP (Media Transfer Protocol) quando il dispositivo è configurato come chiosco multimediale con [un'unica app.](hololens-kiosk.md) Tieni presente che MTP (e la connessione USB in generale) possono comunque essere disabilitati usando il [criterio AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- È stato risolto un problema per cui le icone nel menu Start venivano ridimensionate correttamente in modalità tutto schermo.
- È stato risolto un problema a causa della memorizzazione nella cache HTTP che interferiva con la modalità tutto schermo destinata ai gruppi di Azure AD.
- È stato risolto un problema per cui gli utenti non erano in grado di usare il pulsante Associa dopo aver abilitato la modalità sviluppatore con i pacchetti di provisioning, a meno che non fossero stati disabilitati e ri-abilitati.

## Windows Holographic, versione 1903 - Aggiornamento di novembre 2020
- Build 18362.1085

Questo aggiornamento qualitativo mensile non contiene alcuna modifica importante, ti invitiamo a provare la versione più recente di Windows Holographic, versione 20H2.

## Windows Holographic, versione 2004 - Aggiornamento di ottobre 2020
- Build 19041.1124
 
Miglioramenti e correzioni nell'aggiornamento:

- È stato rimosso un controllo non necessario che ha causato un errore di sistema di runtime.

## Windows Holographic, versione 1903 - Aggiornamento di ottobre 2020
- Build 18362.1081

Questo aggiornamento qualitativo mensile non contiene modifiche di questo tipo, ti invitiamo a provare le build più recenti per Windows Holographic, versione 2004.

## Windows Holographic, versione 2004 - Aggiornamento di settembre 2020
- Build 19041.1117

Miglioramenti e correzioni nell'aggiornamento:

- Risolve un problema che impediva a Visual Studio di eseguire il debug di un'applicazione quando SupportsMultipleInstances="true" è presente in appxmanifest.
- Questa versione include la correzione di rilevamento proxy NCSI per risolvere il rilevamento Internet non riuscito tramite proxy di rete. NCSI può usare proxy computer e proxy per profilo per il rilevamento della connettività Internet. Il proxy per utente sarà supportato da NCSI nelle versioni future.
- Nella maggior parte dei dispositivi Windows Mixed Reality, il vettore di direzione in avanti è parallelo al terreno quando la testa dell'utente si trova in una posizione neutra in attesa. Tuttavia, le versioni precedenti di HoloLens 2 allineavano il vettore per essere perpendicolare ai pannelli di visualizzazione, che viene inclinato verso il basso di alcuni gradi rispetto all'orientamento ideale. Le versioni più recenti di HoloLens 2 hanno corretto questo problema per garantire la coerenza semantica tra i fattori di forma.
- Maggiore affidabilità del tracciamento delle mani che comporta un minor numero di perdite di tracciabilità in scenari specifici.
- Questa versione contiene una correzione per migliorare la qualità del timestamp audio che potrebbe aver contribuito ai problemi di acquisizione video.

## Windows Holographic, versione 1903 - Aggiornamento di settembre 2020
- Build 18362.1079

Miglioramenti e correzioni nell'aggiornamento:

- Nella maggior parte dei dispositivi Windows Mixed Reality, il vettore di direzione in avanti è parallelo al terreno quando la testa dell'utente si trova in una posizione neutra in attesa. Tuttavia, le versioni precedenti di HoloLens 2 allineavano il vettore per essere perpendicolare ai pannelli di visualizzazione, che viene inclinato verso il basso di alcuni gradi rispetto all'orientamento ideale. Le versioni più recenti di HoloLens 2 hanno corretto questo problema per garantire la coerenza semantica tra i fattori di forma.
- Maggiore affidabilità del tracciamento delle mani che comporta un minor numero di perdite di tracciabilità in scenari specifici.

## Windows Holographic, versione 2004 - Aggiornamento di agosto 2020
- Build 19041.1113

Miglioramenti e correzioni nell'aggiornamento:

- L'app Impostazioni non seguirà più l'utente nelle esperienze di registrazione dell'iride o calibrazione del tracciamento oculare.
- È stato risolto un bug in cui l'applicazione di un pacchetto di provisioning durante la configurazione guidata che rinomina il dispositivo ed esegue altre azioni (ad esempio la connessione a una rete) non eseguiva le altre azioni dopo il riavvio del dispositivo a causa della ridenominazione.
- Combinazione di colori modificata dei flussi iniziali di configurazione del dispositivo per migliorare la qualità visiva.

## Windows Holographic, versione 1903 - Aggiornamento di agosto 2020
- Build 18362.1074

Questo aggiornamento qualitativo mensile non contiene modifiche di questo tipo, ti invitiamo a provare le build più recenti per Windows Holographic, versione 2004.

## Windows Holographic, versione 2004 - Aggiornamento di luglio 2020
- Build 19041.1109

Miglioramenti e correzioni nell'aggiornamento:

- Gli sviluppatori possono ora scegliere se abilitare o disabilitare la richiesta di una connessione sicura da parte di Device Portal.
- Affidabilità migliorata per gli avvii delle applicazioni dopo gli aggiornamenti del sistema operativo.
- La luminosità predefinita della posta in arrivo è stata modificata al 100%.
- È stato risolto un problema relativo all'inoltro HTTPS per Windows Device Portal in HoloLens 2.

## Windows Holographic, versione 1903 - Aggiornamento di luglio 2020
- Build 18362.1071

Miglioramenti e correzioni nell'aggiornamento:

- È stato risolto un problema che poteva causare la scomparsa degli ologrammi nelle applicazioni Unity quando si perdeva o si riprendeva il monitoraggio.
- È stato risolto un problema che causava l'arresto anomalo delle app di HoloLens esclusive nella shell durante l'uso dell'emulatore HoloLens con accelerazione hardware in alcuni dispositivi.
- È stato risolto un problema relativo all'inoltro HTTPS per Windows Device Portal in HoloLens 2.

## Windows Holographic, versione 2004 - Aggiornamento di giugno 2020
- Build 19041.1106

Miglioramenti e correzioni nell'aggiornamento:

- I registratori MRC personalizzati ora hanno nuovi valori predefiniti per determinate proprietà se non vengono specificati.
  - *Nell'effetto video MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (headset immersivo))
  - *Nell'effetto audio MRC:*
    - LoopbackGain (il valore "Guadagno audio app" corrente nella pagina Acquisizione in realtà mista in Windows Device Portal)
    - MicrophoneGain (il valore "Guadagno audio Mic" corrente nella pagina acquisizione in realtà mista in Windows Device Portal)
- È stato risolto un bug per migliorare la qualità audio negli scenari di acquisizione in realtà mista. In particolare, questa correzione dovrebbe eliminare glitch audio nella registrazione quando viene visualizzato il menu **Start.**
- Stabilità dell'ologramma migliorata nei video registrati.
- È stato risolto un problema per cui l'acquisizione in realtà mista non poteva registrare video dopo che il dispositivo è stato lasciato in stato di standby per più giorni.
- L'API HolographicSpace.UserPresence è in genere disabilitata per le applicazioni Unity. Questo comportamento evita un problema che causava la sospensione di alcune app quando la visiera era capovolta, anche se era abilitata l'impostazione "Esegui in background". L'API è ora abilitata per unity versioni 2018.4.18 e successive e 2019.3.4 e successive.
- Quando accedi a Device Portal tramite una Wi-Fi, un Web browser potrebbe impedire l'accesso a causa di un certificato non valido. Il browser potrebbe segnalare un errore, ad esempio "ERR_SSL_PROTOCOL_ERROR", anche se il certificato del dispositivo è stato considerato attendibile in precedenza. In questo caso, non puoi andare a Device Portal, perché non c'è alcuna opzione per ignorare gli avvisi di sicurezza. Questo aggiornamento ha risolto il problema. Se il certificato del dispositivo è stato precedentemente scaricato e considerato attendibile in un PC per rimuovere gli avvisi di sicurezza del browser e si verifica l'errore SSL, il nuovo certificato deve essere scaricato e considerato attendibile per risolvere gli avvisi di sicurezza del browser.
- È stata abilitata la possibilità di creare un pacchetto di provisioning di runtime in grado di installare un'app tramite pacchetti MSIX.
- È stata **** aggiunta un'impostazione in  >  ****  >  **Ologrammi** di sistema delle impostazioni che consente agli utenti di rimuovere automaticamente tutti gli ologrammi dalla casa della realtà mista quando il dispositivo si arresta.
- È stato risolto un problema che causava la modifica del formato pixel delle app di HoloLens per il rendering nero nell'emulatore di HoloLens.
- È stato risolto un bug che causava un arresto anomalo durante l'accesso all'Iride.
- È stato risolto un problema relativo ai download ripetuti dello Store per le app già correnti.
- È stato risolto un bug per impedire alle app immersive di aprire Ripetutamente Microsoft Edge.
- È stato risolto un problema con l'avvio dell Foto app negli avvii iniziali dopo l'aggiornamento dalla versione 1903.
- Prestazioni e affidabilità migliorate.

## Windows Holographic, versione 1903 - Aggiornamento di giugno 2020
- Build 18362.1064

Miglioramenti e correzioni nell'aggiornamento:

- I registratori MRC personalizzati hanno nuovi valori predefiniti per determinate proprietà se non vengono specificati.
  - *Nell'effetto video MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (headset immersivo))
  - *Nell'effetto audio MRC:*
    - LoopbackGain (il valore "Guadagno audio app" corrente nella pagina Acquisizione in realtà mista in Windows Device Portal)
    - MicrophoneGain (il valore "Guadagno audio Mic" corrente nella pagina acquisizione in realtà mista in Windows Device Portal)
- L'API HolographicSpace.UserPresence è in genere disabilitata per le applicazioni Unity. Questo comportamento evita un problema che causa la sospensione di alcune app quando la visiera viene capovolta, anche se l'impostazione per l'esecuzione in background è abilitata. L'API è ora abilitata per unity versioni 2018.4.18 e successive e 2019.3.4 e successive.
- È stato risolto un problema che causava il rendering nero delle app di HoloLens che modificano il formato pixel nell'emulatore di HoloLens.
- È stato risolto un problema relativo all'avvio dell Foto app negli avvii iniziali dopo l'aggiornamento dalla versione 1903.

## Windows Holographic, versione 2004  
- Build - 19041.1103

L'aggiornamento software principale di maggio 2020 per HoloLens 2, *Windows Holographic, versione 2004* include una serie di interessanti nuove funzionalità, come il supporto per Windows Autopilot, la modalità app scura, il supporto Ethernet USB per hotspot 5G/LTE e molto altro ancora. Per eseguire l'aggiornamento alla **** versione più recente, apri l'app Impostazioni, passa a Aggiornamento & Sicurezza e seleziona il pulsante Controlla    **** ****   aggiornamenti. 

|             Funzionalità                              |          Descrizione                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pre-configurare e configurare facilmente nuovi dispositivi per la produzione tramite Windows AutoPilot                 |
|       Supporto FIDO 2                             |          Supporto per le chiavi di sicurezza FIDO2 per abilitare l'autenticazione rapida e sicura per i dispositivi condivisi            |
|       Provisioning migliorato                      |          Applicare facilmente un pacchetto di provisioning da un'unità USB a HoloLens                              |
|       Stato di installazione dell'applicazione                 |          Controllare lo stato di installazione nell'app Impostazioni per le app che sono state spinte a HoloLens 2 tramite MDM               |
|       Provider di servizi di configurazione (CSP)   |          Sono stati aggiunti nuovi provider di servizi di configurazione per migliorare le funzionalità di controllo dell'amministratore                 |
|       Supporto USB 5G/LTE                       |          La funzionalità Ethernet USB espansa consente il supporto per 5G/LTE                                    |
|       Modalità app scura                              |          Modalità app scura disponibile per le app che supportano sia le modalità scura che la modalità scura, migliorando l'esperienza di visualizzazione        |
|       Comandi vocali                             |          Supporto per comandi vocali di sistema aggiuntivi per controllare HoloLens senza mani                           |
|       Miglioramenti al tracciamento della mano                 |          I miglioramenti del tracciamento della mano rendono più accurate le interazioni con pulsanti e ardesia 2D                        |
|       Miglioramenti qualitativi e correzioni                 |          Vari miglioramenti delle prestazioni e dell'affidabilità del sistema in tutta la piattaforma                            |

### Supporto per Windows Autopilot

Windows Autopilot per HoloLens 2 consente al canale di vendita del dispositivo di pre-registrare HoloLens nel tenant di Intune. Quando arrivano, i dispositivi sono pronti per la distribuzione autonoma come dispositivi condivisi nel tenant. Per sfruttare i vantaggi dell'auto-distribuzione, il dispositivo deve connettersi a una rete durante la prima schermata dell'installazione tramite usb-C-to-Ethernet.

Dopo che un utente avvia il processo di distribuzione automatica di Autopilot, il processo completa i passaggi seguenti:

1. Aggiungere il dispositivo ad Azure Active Directory (Azure AD)
1. Utilizzare Azure AD per registrare il dispositivo in Microsoft Intune (o in un altro servizio MDM).
1. Eseguire il download dei criteri, dei certificati e dei profili di rete di destinazione del dispositivo.
1. Eseguire il provisioning del dispositivo.
1. Presentare la schermata di accesso all'utente.

Per altre informazioni, vedere la guida alla valutazione di [Windows Autopilot per HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Contatta il tuo Account Manager per partecipare all'anteprima di AutoPilot ora. I dispositivi pronti per Autopilot inizieranno la spedizione a breve.*

### Supporto delle chiavi di sicurezza FIDO2

Alcuni utenti condividono un dispositivo HoloLens con altri in un ambiente aziendale o dell'istituto di istruzione. È quindi importante che gli utenti possano facilmente senza digitare lunghi nomi utente e password. Fast Identity Online (FIDO) consente a chiunque nell'organizzazione (tenant di Azure AD) di accedere facilmente a HoloLens senza immettere un nome utente o una password.

Le chiavi di sicurezza FIDO2 sono un metodo di autenticazione senza password basato su standard "unphishable" che può essere utilizzato in qualsiasi fattore di forma. FIDO è uno standard aperto per l'autenticazione senza password. Consente agli utenti e alle organizzazioni di accedere alle proprie risorse senza un nome utente o una password. Usano invece una chiave di sicurezza esterna o una chiave della piattaforma incorporata in un dispositivo.

Per iniziare, vedere [Abilitare l'accesso con chiave di sicurezza](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)senza password.

### Registrazione MDM migliorata tramite pacchetto di provisioning

I pacchetti di provisioning consentono di impostare la configurazione di HoloLens tramite un file di configurazione anziché tramite l'esperienza predefinita di HoloLens. In precedenza, i pacchetti di provisioning dovevano essere copiati nella memoria interna di HoloLens. Ora possono essere su un'unità USB in modo che siano più facili da riutilizzare in più dispositivi HoloLens ed è possibile effettuare il provisioning dei dispositivi in parallelo. I pacchetti di provisioning ora supportano anche un campo per la registrazione nella gestione dei dispositivi, quindi non è disponibile alcuna configurazione manuale dopo il provisioning.

Per provare:

1. Scarica la versione più recente di Progettazione configurazione di Windows da Windows Store nel PC.
1. Selezionare **Provisioning dispositivi HoloLens per il**provisioning dei dispositivi  >  **HoloLens 2.**
2. Creare il profilo di configurazione. Copia quindi tutti i file creati in un dispositivo di archiviazione USB-C.
3. Collega il dispositivo USB-C a qualsiasi HoloLens appena lampeggiato. Premi quindi i pulsanti **di risparmio energia**del volume per applicare il pacchetto di  +  **** provisioning.

### Stato di installazione dell'applicazione line-of-business

La distribuzione e la gestione delle app MDM per le app line-of-business sono fondamentali per HoloLens. Gli amministratori e gli utenti devono visualizzare lo stato di installazione dell'app per il controllo e la diagnosi. In questa versione, abbiamo aggiunto altri dettagli **in**Impostazioni Account Accesso all'attività aziendale o  >  ****  >  **all'istituto**di istruzione  >  **Click on your account**  >  **Info.**

### Criteri e CSP aggiuntivi

Un [provider di servizi di](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) configurazione è un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione in un dispositivo. In questa versione viene aggiunto il supporto per altri criteri per aumentare il controllo che gli amministratori hanno sui dispositivi HoloLens distribuiti. Per l'elenco dei provider di servizi di configurazione supportati da HoloLens, vedere [CSP NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

Novità di questa versione:

**CSP Policy** 

Il provider di servizi di configurazione dei criteri consente all'organizzazione di configurare i criteri nei dispositivi Windows. In questa versione sono stati aggiunti nuovi criteri per HoloLens, elencati qui. Per altre informazioni, vedere [Criteri CSP supportati da HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

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

Il provider del servizio di configurazione NetworkQoSPolicy crea criteri di qualità del servizio (QoS) di rete. Un criterio QoS esegue un set di azioni sul traffico di rete basato su un set di condizioni corrispondenti. Per ulteriori informazioni, vedere [CSP NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### Supporto Ethernet USB espanso per dispositivi con tethering 5G/LTE

È stato aggiunto il supporto per abilitare determinati dispositivi mobili a banda larga, ad esempio telefoni 5G/LTE e hotspot Wi-Fi, quando vengono collegati a HoloLens 2 tramite USB. Questi dispositivi vengono ora visualizzati nelle impostazioni **di rete** come un'altra connessione Ethernet. I dispositivi mobili a banda larga che richiedono un driver esterno non sono supportati. Questa funzionalità abilita le connessioni a larghezza di banda elevata quando Wi-Fi non è disponibile e Wi-Fi tethering non è sufficientemente performante. Per altre informazioni sui dispositivi USB supportati, vedi [Connettersi Bluetooth dispositivi USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### Miglioramenti al tracciamento della mano

Questa versione include diversi miglioramenti del tracciamento delle mani:

- **Stabilità della posizione di puntamento:** Il sistema ora resiste a piegare l'indice quando viene occluded dal palmo. Questa modifica migliora l'accuratezza quando si preme pulsanti, si digita, si scorre il contenuto e altro ancora. 
- **Riduzione dei tocchi d'aria accidentali:** Abbiamo migliorato il rilevamento del movimento di tocco dell'aria. Ora ci sono meno attivazioni accidentali in diversi scenari comuni, ad esempio quando si rilasciano le mani ai lati.
- **Affidabilità del commutatore utente:** Il sistema è ora più veloce e affidabile per aggiornare le dimensioni della mano quando condividi un dispositivo.
- **Riduzione del furto delle mani:** Abbiamo migliorato la gestione dei casi in cui sono presenti più di due mani in vista dei sensori. Se più persone lavorano insieme, c'è una probabilità molto inferiore che la mano tracciata "salti" dall'utente alla mano di qualcun altro nella scena.
- **Affidabilità del sistema:** È stato risolto un problema che causava l'interruzione del funzionamento del rilevamento delle mani quando il dispositivo era carico elevato.

### Modalità scura

Molte app di Windows ora supportano sia le modalità scura che la modalità light. Gli utenti di HoloLens 2 possono scegliere la modalità predefinita per le app che supportano entrambi. Dopo l'aggiornamento, la modalità app predefinita è "scura", ma **** puoi modificare facilmente questa impostazione: passa a Impostazioni colori di sistema  >  ****  >  ****  >  **Scegli la modalità predefinita dell'app.** 

Queste app "predefinite" supportano la modalità scura: 

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

![Finestre in modalità scura affiancate](images/DarkMode.jpg)

### Comandi vocali di sistema

Ora puoi usare i comandi vocali con qualsiasi app nel dispositivo. Per altre informazioni, vedi [Usare la voce per usare HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Vedi anche [Lingue supportate per HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-language-support)  

### Aggiornamenti di Cortana

L'app aggiornata si integra con Microsoft 365 per aiutarti a fare di più nei dispositivi (attualmente in US-English solo). In HoloLens 2, Cortana non supporta più determinati comandi specifici del dispositivo, ad esempio la regolazione del volume o il riavvio. Queste opzioni sono ora supportate dai nuovi comandi vocali di sistema. Altre informazioni sulla nuova app Cortana sono presenti nel [blog.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### Miglioramenti qualitativi e correzioni

Miglioramenti e correzioni anche nell'aggiornamento:  
- È stato introdotto un sistema di calibrazione dello schermo attivo. Questa funzionalità migliora la stabilità e l'allineamento degli ologrammi. Ora rimangono sul posto quando sposti la testa da un lato all'altro.
- È stato risolto un bug Wi-Fi lo streaming verso HoloLens era stato interrotto periodicamente. Se un'applicazione indica che è necessario un flusso a bassa latenza, implementare la correzione chiamando la [funzione SetSocketMediaStreamingMode.](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- È stato risolto un blocco del dispositivo che si verificava durante lo streaming in modalità di ricerca.
- È stato risolto un bug in cui in alcuni casi l'utente giusto non sarebbe stato visualizzato nella schermata di accesso quando si riprendeva una sessione.
- È stato risolto un problema per cui gli utenti non potevano esportare i log MDM tramite **Impostazioni.**
- È stato risolto un problema per cui l'accuratezza del tracciamento oculare subito dopo la configurazione guidata poteva essere inferiore al previsto.
- È stato risolto un problema per cui il sottosistema di tracciamento oculare non era in grado di inizializzare o eseguire la calibrazione in determinate condizioni.
- È stato risolto un problema per cui la calibrazione oculare richiedeva un utente già calibrato.
- È stato risolto un problema per cui un driver si arresta in modo anomalo durante la calibrazione oculare.
- È stato risolto un problema per cui le ripetute pressione del pulsante di alimentazione potevano causare un timeout di sistema di 60 secondi e un arresto anomalo della shell.
- Stabilità migliorata per i buffer di profondità.
- È stato aggiunto **un pulsante** Condividi nell'Hub di Feedback in modo che gli utenti possano condividere più facilmente il feedback.
- È stato risolto un bug in cui RoboRaid wan non era installato correttamente.

### Problemi noti

- Un problema con la lingua del sistema zh-CN impedisce ai comandi vocali di acquisire in realtà mista o visualizzare l'indirizzo IP del dispositivo.
- Un problema richiede di avviare l'app Cortana dopo aver avviato il dispositivo per usare l'attivazione vocale "Ehi Cortana". Se hai aggiornato da una build 18362, potresti vedere anche un secondo riquadro dell'app per la versione precedente dell'app Cortana che non funziona più nella **schermata Start.**

## Windows Holographic, versione 1903 - Aggiornamento di maggio 2020 
- Build 18362.1061

Questo aggiornamento qualitativo mensile non contiene alcuna modifica importante perché il team stava lavorando all'aggiornamento di maggio di Windows Holographic versione 2004, come descritto in precedenza.

## Windows Holographic, versione 1903 - Aggiornamento di aprile 2020
- Build 18362.1059

**Modalità scura per le app supportate** 

Molte app di Windows supportano sia la modalità scura che la modalità light. I clienti di HoloLens 2 ora possono scegliere la modalità predefinita per le app che supportano entrambe le combinazioni di colori. In base al feedback dei clienti, la modalità predefinita dell'app viene impostata su "scuro", ma puoi modificare facilmente questa impostazione in qualsiasi momento: passa a Impostazioni **> Colori >** sistema per trovare "Scegli la modalità predefinita dell'app". ****

Queste app "predefinite" supportano la modalità scura:
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
- Assicurati che le sovrapposizioni della shell siano incluse nelle acquisizioni in realtà mista.
- Gli sviluppatori irreali possono ora usare la pagina Visualizzazione 3D in Device Portal per testare ed eseguire il debug delle applicazioni.
- Stabilità dell'ologramma migliorata nell'acquisizione in realtà mista quando viene usato l'algoritmo *DepthReprojection holographicDepthReprojectionMethod.*
- È stato risolto l'errore "Classe API IStreamSocketListener winrt non registrata" nelle app ARM a 32 bit.

## Windows Holographic, versione 1903 - Aggiornamento di marzo 2020 
- Build 18362.1056

Miglioramenti e correzioni nell'aggiornamento:

- Stabilità dell'ologramma migliorata nell'acquisizione in realtà mista quando viene usato l'algoritmo *AutoPlanar HolographicDepthReprojectionMethod.*
- Verificare che il sistema di coordinate collegato a un campione MF di profondità sia coerente con la documentazione pubblica.
- È stata migliorata la produttività degli sviluppatori consentendo ai clienti di incollare grandi quantità di testo tramite il portale dei dispositivi.

## Windows Holographic, versione 1903 - Aggiornamento di febbraio 2020 
- Build 18362.1053

Miglioramenti e correzioni nell'aggiornamento:

- Disabilita temporaneamente l'API HolographicSpace.UserPresence per le applicazioni Unity. Questa modifica evita un problema che causava la sospensione di alcune app quando la visiera era capovolta, anche se era abilitata l'impostazione "Esegui in background".
- È stato risolto un arresto anomalo HUP casuale causato dal tracciamento della mano, in cui l'utente notava un blocco dell'interfaccia utente e poi torna alla shell dopo alcuni secondi.
- È stato migliorato il tracciamento delle mani in modo che, quando si punta con il dito indice, la parte superiore di tale dito sia meno probabile che si inclina in modo imprevisto.
- Miglioramento dell'affidabilità del tracciamento della testa, del mapping spaziale e di altri runtime.

## Windows Holographic, versione 1903 - Aggiornamento di gennaio 2020 
- Build 18362.1043
 
Miglioramenti e correzioni nell'aggiornamento:

- Stabilità migliorata per le app esclusive quando si utilizza l'emulatore di HoloLens 2.

## Windows Holographic, versione 1903 - Aggiornamento di dicembre 2019 
- Build 18362.1042

Miglioramenti e correzioni nell'aggiornamento:

- Sono state introdotte correzioni per la riproduzione dell'ultima fase (LSR). Rendering visivo migliorato degli ologrammi in modo da risultare più stabile e nitido, valutando in modo più accurato la profondità. Questo sintomo sarà più evidente dopo questo aggiornamento se le app non impostano correttamente la profondità degli ologrammi.
- Stabilità fissa delle app esclusive e spostamento tra app esclusive.
- È stato risolto un problema per cui l'acquisizione in realtà mista non poteva registrare video dopo che il dispositivo era in stato di standby per diversi giorni.
- Stabilità dell'ologramma migliorata.

## Windows Holographic, versione 1903 - Aggiornamento di novembre 2019 
- Build 18362.1039

Miglioramenti e correzioni nell'aggiornamento:

- È stata corretta la **funzionalità dei** comandi vocali Select durante la configurazione iniziale per en-CA ed en-AU.
- Migliore qualità visiva degli oggetti posizionati lontano nelle versioni più recenti di Unity e Mixed Reality Toolkit (MRTK).
- Risolto i problemi di risoluzione dei problemi relativi alle applicazioni olografiche bloccate in uno stato di pausa all'avvio fino a quando il menu Start non è stato aperto e quindi chiuso.
- Correzioni e miglioramenti per la conformità al runtime OpenXR per HoloLens 2 e l'emulatore.
