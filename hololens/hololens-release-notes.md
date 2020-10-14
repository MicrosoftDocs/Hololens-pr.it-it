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
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 23ec5478c35977d1fd1fa20a33827e441d4b5c12
ms.sourcegitcommit: 264c8ff6726f702c3770525d774e0c1d263a2705
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117771"
---
# Note sulla versione di HoloLens 2

Per assicurarti di avere un'esperienza produttiva con i tuoi dispositivi HoloLens, continuiamo a rilasciare gli aggiornamenti relativi a funzionalità, bug e sicurezza. In questa pagina è possibile vedere le novità di HoloLens ogni mese. Per ottenere il più recente aggiornamento di HoloLens 2 Full Flash (FFU) per [flashare il dispositivo tramite il compagno di ripristino avanzato](hololens-recovery.md#clean-reflash-the-device), [scaricalo qui](https://aka.ms/hololens2download). Il download viene mantenuto aggiornato e fornisce la build più recente in generale disponibile.

>[!NOTE]
> Per leggere le note sulla versione dell'emulatore HoloLens, [visita l'archivio](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

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

Windows Autopilot per HoloLens 2 consente al canale di vendita del dispositivo di pre-registrare HoloLens nel tenant di Intune. Quando arrivano i dispositivi, sono pronti a eseguire la distribuzione automatica come dispositivi condivisi sotto il tenant. Per sfruttare la distribuzione automatica, il dispositivo deve connettersi a una rete durante la prima schermata del programma di installazione usando un dongle USB-C-to-Ethernet o USB-C-to-LTE.

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
