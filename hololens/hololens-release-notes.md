---
title: Note sulla versione di HoloLens 2
description: Informazioni sugli aggiornamenti in ogni nuova versione di HoloLens.
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
ms.openlocfilehash: 25a1bc21638090cc5d22bc4482299f3931641dea
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829041"
---
# Note sulla versione di HoloLens 2

Per assicurarti di avere un'esperienza produttiva con i tuoi dispositivi HoloLens, continuiamo a rilasciare gli aggiornamenti relativi a funzionalità, bug e sicurezza. In questa pagina è possibile scoprire le novità di HoloLens ogni mese. Se si vuole scaricare l'ultima versione di HoloLens 2 FFU per flashare il dispositivo tramite [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) , è possibile scaricarlo da [qui](https://aka.ms/hololens2download). Questa operazione viene mantenuta aggiornata e corrisponde alla build più recente in generale disponibile. 

Le note sulla versione di HoloLens Emulator possono essere trovate [qui](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows olografico, versione 2004-giugno 2020 Update
- Build 19041,1106

Miglioramenti e correzioni nell'aggiornamento:

- I registratori MRC personalizzati hanno nuovi valori predefiniti per determinate proprietà, se non sono specificati.
  - Nell'effetto video MRC:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auricolare immersiva))
  - Sull'effetto audio MRC:
    - LoopbackGain (il valore di "guadagno dell'app audio" corrente nella pagina di acquisizione di realtà mista in Windows Device Portal)
    - MicrophoneGain (il valore "MIC Audio Gain" corrente nella pagina di acquisizione di realtà mista in Windows Device Portal)
- Questo aggiornamento contiene una correzione di bug che migliora la qualità audio negli scenari di acquisizione di realtà mista. In particolare, dovrebbe eliminare qualsiasi glitch audio nella registrazione quando viene visualizzato il menu Start.
- Migliorata la stabilità degli ologrammi nei video registrati.
- Risolve un problema in cui l'acquisizione di realtà mista non può registrare il video dopo che il dispositivo viene lasciato in stato di standby per più giorni.
- L'API HolographicSpace. UserPresence è in genere disabilitata per le applicazioni Unity per evitare un problema che causa la sospensione di alcune app quando la visiera è capovolta, anche se l'impostazione per l'esecuzione in background è abilitata. L'API è ora abilitata per le versioni 2018.4.18 e successive di Unity e 2019.3.4 e successive.
- Quando si accede a Device Portal tramite una connessione Wi-Fi, un Web browser potrebbe impedire l'accesso a causa di un certificato non valido, segnalando un errore come "ERR_SSL_PROTOCOL_ERROR", anche se il certificato del dispositivo è stato precedentemente considerato attendibile.  In questo caso, non è possibile passare a Device Portal come opzioni per ignorare gli avvisi di sicurezza non disponibili.  Questo aggiornamento risolve il problema.  Se il certificato del dispositivo è stato precedentemente scaricato e considerato attendibile in un PC per rimuovere gli avvisi di sicurezza del browser e si è verificato l'errore SSL, il nuovo certificato dovrà essere scaricato e considerato attendibile per indirizzare gli avvisi di sicurezza del browser.
- Possibilità di creare un pacchetto di provisioning di runtime che consente di installare un'app usando i pacchetti di MSIX.
- Nuova impostazione che gli utenti possono trovare in impostazioni > sistema > gli ologrammi, che consente agli utenti di rimuovere automaticamente tutti gli ologrammi dalla Home realtà mista quando il dispositivo si arresta.
- È stato risolto un problema che causava le app HoloLens che modificano il formato pixel per il rendering nero nell'emulatore HoloLens.
- Corretto un bug che causava un arresto anomalo durante l'accesso a Iris.
- Risolve un problema relativo ai download ripetuti dello Store per le app già aggiornate.
- È stato risolto un bug per impedire alle app immersive di lanciare più volte Edge.
- Risolve un problema intorno all'avvio dell'app Foto in stivali iniziali dopo l'aggiornamento dalla versione di 1903.
- Prestazioni e affidabilità migliorate.

## Windows olografico, versione 1903-giugno 2020 Update
- Build 18362,1064

Miglioramenti e correzioni nell'aggiornamento:

- I registratori MRC personalizzati hanno nuovi valori predefiniti per determinate proprietà, se non sono specificati.
  - Nell'effetto video MRC:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auricolare immersiva))
  - Sull'effetto audio MRC:
    - LoopbackGain (il valore di "guadagno dell'app audio" corrente nella pagina di acquisizione di realtà mista in Windows Device Portal)
    - MicrophoneGain (il valore "MIC Audio Gain" corrente nella pagina di acquisizione di realtà mista in Windows Device Portal)
- L'API HolographicSpace. UserPresence è in genere disabilitata per le applicazioni Unity per evitare un problema che causa la sospensione di alcune app quando la visiera è capovolta, anche se l'impostazione per l'esecuzione in background è abilitata. L'API è ora abilitata per le versioni 2018.4.18 e successive di Unity e 2019.3.4 e successive.
- È stato risolto un problema che causava le app HoloLens che modificano il formato pixel per il rendering nero nell'emulatore HoloLens.
- Risolve un problema intorno all'avvio dell'app Foto in stivali iniziali dopo l'aggiornamento dalla versione di 1903.

## Windows olografico, versione 2004  
Build-19041,1103

Siamo lieti di annunciare il nostro aggiornamento software principale di maggio 2020 per HoloLens 2, **Windows olografico, versione 2004**. Questa versione include una serie di nuove interessanti funzionalità, come il supporto per il pilota automatico Windows, la modalità Dark app, il supporto USB Ethernet per gli hotspot 5G/LTE e molto altro. Per eseguire l'aggiornamento alla versione più recente, aprire l' **app Impostazioni**, quindi fare clic su **Aggiorna & sicurezza**e quindi selezionare il pulsante **Controlla aggiornamenti**   . 

|             Funzionalità                              |          Descrizione                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pre-configurare e configurare in maniera trasparente nuovi dispositivi per la produzione, con Autopilot Windows                 |
|       Supporto di FIDO 2                             |          Supporto per le chiavi di sicurezza di FIDO2 per abilitare l'autenticazione veloce e sicura per i dispositivi condivisi            |
|       Miglioramento del provisioning                      |          Applicare senza problemi un pacchetto di provisioning da un'unità USB al proprio HoloLens                              |
|       Stato di installazione dell'applicazione                 |          Verificare che lo stato di installazione per le app sia stato inserito in HoloLens 2 tramite MDM, nell'app impostazioni              |
|       Provider di servizi di configurazione (CSP)   |          Sono stati aggiunti nuovi provider di servizi di configurazione per migliorare le funzionalità di controllo dell'amministratore.                 |
|       Supporto per USB 5G/LTE                       |          La funzionalità Ethernet USB espansa consente il supporto per 5G/LTE                                    |
|       Modalità app scura                              |          Modalità app scure per le app che supportano le modalità buio e luce, il miglioramento dell'esperienza di visualizzazione        |
|       Comandi vocali                             |          Supporto per comandi vocali di sistema aggiuntivi per controllare HoloLens, vivavoce                           |
|       Miglioramenti per il rilevamento delle mani                 |          Miglioramenti per il rilevamento delle mani rende più accurate i pulsanti e le interazioni in ardesia 2D                        |
|       Miglioramenti e correzioni di qualità                 |          Diversi miglioramenti delle prestazioni e dell'affidabilità del sistema in tutta la piattaforma                            |

### Supporto per il pilota automatico di Windows 

Windows Autopilot per HoloLens 2 consente al canale di vendita del dispositivo di pre-registrare HoloLens nel tenant di Intune.  Quando arrivano i dispositivi, sono pronti a eseguire la distribuzione automatica come dispositivi condivisi sotto il tenant. Per sfruttare la distribuzione automatica, i dispositivi dovranno connettersi a una rete durante la prima schermata della configurazione usando un dongle USB-C o Ethernet o un dongle USB-C per LTE. 

Quando viene avviato il processo di distribuzione automatica di Autopilot, vengono seguiti i passaggi seguenti: 

1. Aggiungere il dispositivo ad Azure Active Directory (Azure AD) 
1. Utilizzare Azure AD per registrare il dispositivo in Microsoft Intune (o in un altro servizio MDM). 
1. Eseguire il download dei criteri, dei certificati e dei profili di rete di destinazione del dispositivo. 
1. Eseguire il provisioning del dispositivo. 
1. Presentare la schermata di accesso all'utente. 

Altre informazioni sulla [Guida alla valutazione di Windows Autopilot per HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

**Contatta il tuo account Manager per partecipare all'anteprima del pilota automatico ora. I dispositivi pronti per il pilota automatico inizieranno presto la spedizione.**

### Supporto della chiave di sicurezza FIDO2 

Molti di voi condividono un dispositivo HoloLens con molte persone in un ambiente lavorativo o scolastico. Se i dispositivi vengono condivisi tra studenti in un'aula o estratti da un armadietto dei dispositivi, è importante essere in grado di cambiare gli utenti in modo rapido e semplice senza digitare nomi e password lunghi. 

FIDO consente a tutti gli utenti dell'organizzazione (tenant) di accedere a HoloLens senza immettere un nome utente o una password. 

Le chiavi di sicurezza di FIDO2 sono un metodo di autenticazione senza password basato su standard unphishable che può rientrare in qualsiasi fattore di forma. Fast Identity online (FIDO) è uno standard aperto per l'autenticazione con password. FIDO consente agli utenti e alle organizzazioni di sfruttare lo standard per accedere alle proprie risorse senza un nome utente o una password usando una chiave di sicurezza esterna o una chiave della piattaforma incorporata in un dispositivo. 

Leggere i [documenti di sicurezza con password](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key) per iniziare. 

### Registrazione MDM migliorata tramite il pacchetto di provisioning 

I pacchetti di provisioning consentono di impostare la configurazione di HoloLens tramite un file di configurazione invece di passare all'esperienza di HoloLens fuori scatola. In precedenza, i pacchetti di provisioning dovevano essere copiati nella memoria interna di HoloLens, ora possono essere su un'unità USB in modo che siano più facili da riutilizzare in più HoloLens e quindi più persone possono eseguire il provisioning di HoloLens in parallelo.  Inoltre, i pacchetti di provisioning supportano un nuovo campo per la registrazione in gestione dispositivi, quindi non è disponibile la configurazione manuale del post-provisioning. 

1. Per provarlo, Scarica la versione più recente di Windows Configuration designer da Windows Store nel PC. 
1. Selezionare **provision HoloLens devices** > selezionare **provision HoloLens 2 Devices** 
1. Creare il profilo di configurazione e, al termine, copiare tutti i file creati in un dispositivo di archiviazione USB-C. 
1. Collegarlo a qualsiasi HoloLens appena balenato e premere **volume giù + Power** per applicare il pacchetto di provisioning. 

### Stato di installazione dell'applicazione line-of-business 

La distribuzione e la gestione delle app MDM per le app line of business (LOB) sono fondamentali per i clienti. Gli amministratori e gli utenti devono essere in grado di visualizzare lo stato di installazione dell'app per scopi di controllo e diagnosi. In questa versione verranno aggiunti altri dettagli in **impostazioni > account > l'accesso al lavoro o all'Istituto di istruzione > fare clic sul proprio account > info.**

### CSP e criteri aggiuntivi 

Un [provider di servizi di configurazione (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) è un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione in un dispositivo. In questa versione aggiungiamo il supporto per altri criteri, aumentando gli amministratori dei controlli sui dispositivi HoloLens distribuiti. Per l'elenco dei CSP supportati da HoloLens, visitare questo [collegamento](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Novità di questa versione:

**CSP Policy** 

Il provider di servizi di configurazione dei criteri consente all'organizzazione di configurare i criteri nei dispositivi Windows. In questa versione verranno aggiunti nuovi criteri per HoloLens, elencati di seguito. [Qui](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)è possibile ottenere ulteriori informazioni sui criteri supportati.  

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

**NETWORKQOSPOLICY CSP** Il provider di servizi di configurazione NetworkQoSPolicy Crea criteri QoS (Network Quality of Service). Un criterio QoS esegue un set di azioni sul traffico di rete basato su un set di condizioni corrispondenti. Per ulteriori [informazioni, vedere](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)questo criterio. 

### Supporto Ethernet USB espanso per dispositivi cablati 5G/LTE

È stato aggiunto il supporto per consentire a determinati dispositivi mobili a banda larga, come i telefoni 5G/LTE e i minestroni WiFi quando sono collegati al HoloLens 2 tramite USB. Questi dispositivi verranno visualizzati nelle impostazioni di rete come un'altra connessione Ethernet. I dispositivi mobili a banda larga che richiedono un driver esterno non sono supportati. Ciò consente connessioni ad alta larghezza di banda in scenari in cui il WiFi non è disponibile e il Tethering WiFi non è abbastanza performanti. Per altre informazioni sui dispositivi USB supportati, vedere [qui](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Miglioramenti per il rilevamento delle mani

Il rilevamento delle mani ha ricevuto diversi miglioramenti in questa versione. 

- **Puntamento della stabilità della posa:** Il sistema ora resisterà a piegare il dito indice quando viene nascosto dal palmo.  Questo migliora la precisione quando si spingono i pulsanti, digitando, scorrendo il contenuto e altro ancora! 
- **Riduzione di rubinetti accidentali:** È stato migliorato il rilevamento del gesto AirTap.  Ora ci sono meno attivazioni accidentali in diversi casi comuni, ad esempio per far cadere le mani al fianco. 
- **Cambiare l'affidabilità dell'utente:** Il sistema è ora più veloce e affidabile per aggiornare le dimensioni delle mani quando si condivide un dispositivo in avanti e indietro. 
- **Sottrazione a mano ridotta:** È stata migliorata la gestione dei casi in cui sono presenti più di due mani in vista dei sensori.  Se più persone stanno lavorando insieme, ora c'è una probabilità molto inferiore che la mano rilevata salterà dall'utente alla mano di qualcun altro nella scena. 
- **Affidabilità del sistema:** È stato risolto un problema che causava il rilevamento manuale per evitare di funzionare per un periodo se il dispositivo è a carico elevato. 

### Modalità scuro

Molte app di Windows ora supportano sia la modalità Dark che la luce e HoloLens 2 i clienti possono scegliere la modalità predefinita per le app che supportano entrambe. Una volta aggiornata, la modalità app predefinita sarà "scura", ma può essere modificata facilmente. Passare a impostazioni > sistema > colori per trovare "Scegli la modalità app predefinita". Ecco alcune delle app in-box che supportano la modalità Dark: 

- Impostazioni 
- Microsoft Store 
- Mail 
- Calendar 
- Esplora file 
- Hub di Feedback 
- OneDrive 
- Foto 
- Visualizzatore 3D 
- Film e TV 

![Windows piastrellato in modalità scura](images/DarkMode.jpg)

### Comandi vocali di sistema

È ora possibile accedere e usare rapidamente i comandi con la voce durante l'uso di qualsiasi app nel dispositivo. Se si sta usando un sistema con una lingua diversa, provare i comandi appropriati in quella lingua. Per altri dettagli sui comandi e su come usarli, vedi la nostra documentazione [qui](https://docs.microsoft.com/hololens/hololens-cortana).  

### Aggiornamenti di Cortana 

L'app aggiornata si integra con Microsoft 365, attualmente disponibile solo in inglese (Stati Uniti), per aiutarti a migliorare l'uso nei tuoi dispositivi. In HoloLens 2, Cortana non supporterà più alcuni comandi specifici per il dispositivo, come la regolazione del volume o il riavvio del dispositivo, che ora sono supportati con i nuovi comandi vocali di sistema menzionati in precedenza. Leggi altre informazioni sulla nuova app Cortana e sulla sua direzione nel nostro [Blog.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/) 

### Miglioramenti e correzioni di qualità 

Miglioramenti e correzioni anche nell'aggiornamento:  
- L'aggiornamento introduce un sistema di calibrazione dello schermo attivo. In questo modo si migliora la stabilità e l'allineamento degli ologrammi, che li aiutano a rimanere in posizione quando si sposta la testa a lato. 
- È stato risolto un bug in cui lo streaming Wi-Fi in HoloLens viene interrotto periodicamente. Se un'applicazione indica che è necessario lo streaming a bassa latenza, questa correzione può essere eseguita chiamando [questa funzione](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode). 
- È stato risolto un problema in cui il dispositivo poteva bloccarsi durante lo streaming in modalità ricerca. 
- Corretto un bug in cui in alcuni casi l'utente corretto non viene visualizzato nella schermata di accesso durante la ripresa della sessione. 
- È stato risolto un problema per cui gli utenti non potevano esportare i log MDM tramite le impostazioni. 
- È stato risolto un problema per cui l'accuratezza del rilevamento degli occhi subito dopo la configurazione fuori scatola potrebbe essere inferiore alla specifica. 
- È stato risolto un problema per cui il sottosistema di rilevamento degli occhi non avrebbe inizializzato e/o eseguito la calibrazione in determinate condizioni. 
- È stato risolto un problema per cui la calibrazione degli occhi veniva richiesta per un utente già calibrato. 
- È stato risolto un problema per cui il driver si arrestava durante la calibrazione degli occhi. 
- È stato risolto un problema per cui le pressioni ripetute del pulsante di alimentazione possono causare un arresto anomalo del sistema e un secondo 60. 
- Stabilità migliorata per i buffer di profondità. 
- Aggiunto il pulsante "Condividi" nell'hub di feedback, in modo che gli utenti possano condividere più facilmente il feedback. 
- È stato risolto un bug in cui RoboRaid non è stato installato correttamente. 

### Problemi noti

- Stiamo esaminando un problema relativo all'uso del linguaggio di sistema zh-CN che impedisce ai comandi vocali di acquisire un'acquisizione di realtà mista o di visualizzare l'indirizzo IP del dispositivo.
- Stiamo esaminando un problema che richiede di avviare l'app Cortana dopo l'avvio del dispositivo per usare l'attivazione vocale "Hey Cortana" e, se è stato aggiornato da una build di 18362, potrebbe essere visualizzato un secondo riquadro dell'app per la versione precedente dell'app Cortana in Start che non funziona più. 

## Windows olografico, versione 1903-maggio 2020 Update 
- Build 18362,1061

Questo aggiornamento di qualità mensile non contiene alcuna modifica della nota perché il team è stato focalizzato sulla fornitura dell'aggiornamento delle funzionalità di qualità più elevata ora disponibile in Windows olografico, la versione 2004 può essere aggiornata in dettaglio. Approfitta di questa opportunità per passare all'aggiornamento delle funzionalità più recente per ottenere una tonnellata di nuove interessanti modifiche.

## Windows olografico, versione 1903-aprile 2020 Update
- Build 18362,1059

**Modalità oscura per le app supportate** 

Molte app di Windows supportano sia la modalità Dark che la luce e presto HoloLens 2 i clienti possono scegliere la modalità predefinita per le app che supportano entrambe le combinazioni di colori. In base al feedback dei clienti in modo estremamente positivo, con questo aggiornamento impostiamo la modalità app predefinita su "scuro", ma è possibile modificare facilmente questa impostazione in qualsiasi momento.
Passare a **impostazioni > sistema > colori** per trovare **"Scegli la modalità app predefinita".**

Ecco alcune delle app in-box che supportano la modalità Dark:
- Impostazioni
- Microsoft Store
- Mail
- Calendar
- Esplora file
- Hub di Feedback
- OneDrive
- Foto
- Visualizzatore 3D
- Film e TV

**Miglioramenti e correzioni anche nell'aggiornamento:** 
- Verificare che le sovrapposizioni di shell siano incluse in acquisizioni di realtà miste.
- Gli sviluppatori irreali ora possono usare la pagina visualizzazione 3D in Device Portal per testare ed eseguire il debug delle proprie applicazioni.
- Migliorare la stabilità degli ologrammi nell'acquisizione di realtà mista quando viene usato l'algoritmo DepthReprojection HolographicDepthReprojectionMethod.
- Risolto l'errore di classe API IStreamSocketListener WinRT non registrata nell'app ARM a 32 bit.

## Windows olografico, versione 1903-marzo 2020 Update 
- Build 18362,1056

Miglioramenti e correzioni nell'aggiornamento:

- Migliorare la stabilità degli ologrammi nell'acquisizione di realtà mista quando viene usato l'algoritmo autoplanare HolographicDepthReprojectionMethod.
- Assicura che il sistema di coordinate allegato a un campione di profondità MF sia coerente con la documentazione pubblica.
- Miglioramento della produttività degli sviluppatori consentendo ai clienti di incollare grandi quantità di testo tramite Device Portal.

## Windows olografico, versione 1903-febbraio 2020 Update 
- Build 18362,1053

Miglioramenti e correzioni nell'aggiornamento:

- Temporaneamente disabilitato l'API HolographicSpace. UserPresence per le applicazioni Unity per evitare un problema che causa la sospensione di alcune app quando la visiera è capovolta, anche se l'impostazione per l'esecuzione in background è abilitata.
- È stato risolto un arresto anomalo di HUP a mano, in cui l'utente noterà un blocco dell'interfaccia utente e poi torna alla shell dopo alcuni secondi.
- È stato migliorato il rilevamento delle mani in modo che, mentre frugando con il dito indice, la parte superiore del dito sia meno probabile che si arricciasse inaspettatamente.
- Maggiore affidabilità del rilevamento della testa, del mapping spaziale e di altri Runtime.

## Windows olografico, versione 1903-gennaio 2020 Update 
- Build 18362,1043

Miglioramento dell'aggiornamento:

- Miglioramenti della stabilità per le app esclusive quando si lavora con l'emulatore di HoloLens 2.

## Windows olografico, versione 1903-dicembre 2019 Update 
- Build 18362,1042

Miglioramenti e correzioni nell'aggiornamento:

- Introduce le correzioni di LSR (ultima fase di riproduzione). Migliora il rendering visivo degli ologrammi per comparire più stabile e nitido con una contabilità più accurata per la profondità. Questa operazione sarà più evidente se le app non impostano correttamente la profondità degli ologrammi, dopo questo aggiornamento.
- Risolve la stabilità delle app esclusive e lo spostamento tra app esclusive.
- Risolve un problema in cui l'acquisizione di realtà mista non può registrare il video dopo che il dispositivo viene lasciato in stato di standby per più giorni.
- Migliora la stabilità degli ologrammi.

## Windows olografico, versione 1903-novembre 2019 Update 
- Build 18362,1039

Miglioramenti e correzioni nell'aggiornamento:

- Correzioni per i comandi vocali **"Seleziona"** durante la configurazione iniziale per en-CA e en-au.
- Miglioramenti della qualità visiva degli oggetti posizionati in modo distante nelle versioni più recenti Unity e MRTK.
- Risolve i problemi relativi alle applicazioni olografiche bloccate in uno stato in pausa all'avvio finché il pannello pin non viene più allontanato.
- Correzioni e miglioramenti alla conformità di runtime di OpenXR per HoloLens 2 e l'emulatore.


