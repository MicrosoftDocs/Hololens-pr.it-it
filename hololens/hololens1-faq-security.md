---
title: Domande frequenti sulla sicurezza
description: Rimanere aggiornati con le domande di sicurezza e le risposte frequenti sui dispositivi di realtà mista HoloLens.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, sicurezza
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309973"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Domande frequenti sulla sicurezza di HoloLens (prima generazione)

1. **Quale livello di protezione dei dati offre HoloLens 1?**
    1. Vedere Crittografia BitLocker di [HoloLens (prima generazione)](hololens1-encryption.md)
1. **Quale tipo di wireless viene usato?**
    1. 802.11ac e Bluetooth 4.1 LE
1. **Quale tipo di architettura è incorporato?  Ad esempio: da punto a punto, mesh o altro?**
    1. Wi-Fi può essere utilizzato in modalità infrastruttura per comunicare con altri punti di accesso wireless.
    1. Bluetooth può essere usato per la comunicazione peer-to-peer tra più Dispositivi HoloLens se l'applicazione dei clienti lo supporta o con altri dispositivi Bluetooth.
1. **Che cos'è l'ID FCC?**
    1. C3K1688
1. **Su quale intervallo di frequenza e canali opera il dispositivo ed è configurabile?**
    1. Wi-Fi: l'intervallo di frequenza non è configurabile dall'utente e dipende dal paese d'uso. Negli Stati Uniti Wi-Fi canali a 2,4 GHz (1-11) e a 5 GHz (36-64, 100-165).
    1. Bluetooth: Bluetooth usa l'intervallo standard a 2,4-2,48 GHz.
1. **Il dispositivo può consentire o bloccare frequenze specifiche?**
    1. Non è controllabile dall'utente o dal dispositivo.
1. **Qual è il livello di potenza per trasmissione e ricezione? È regolabile? Qual è l'intervallo di operazioni?**
    1. Gli standard di test delle emissioni sono disponibili [qui.](https://fccid.io/C3K1688) La gamma di operazioni dipende fortemente dal punto di accesso e dall'ambiente, ma equivale approssimativamente ad altri telefoni, tablet o PC di alta qualità.
1. **Qual è il ciclo/durata dei dazi per il normale funzionamento?**
    1. 2-3 ore di utilizzo attivo e fino a due settimane di tempo di standby
    1. La durata della batteria non è disponibile.
1. **Che cos'è il comportamento di trasmissione e ricezione quando uno strumento non è compreso nell'intervallo?**
    1. La trasmissione/ricezione di HoloLens segue il modello Wi-Fi/Bluetooth standard. Al limite dell'intervallo, probabilmente si noterà che l'input non si interrompe fino a quando non si disconnette completamente, ma dopo essere rientrato nell'intervallo dovrebbe riconnettersi rapidamente.
1. **Che cos'è la densità di distribuzione per piede quadrato?**
    1. Questo dipende dall'infrastruttura di rete.
1. **Il dispositivo può usare l'infrastruttura come client?**
    1. Sì
1. **Quale protocollo viene usato?**
    1. HoloLens non usa protocolli proprietari
1. **Frequenza di aggiornamento del sistema operativo: qual è la frequenza degli aggiornamenti del sistema operativo per l'HL?  È disponibile una pianificazione impostata?  Microsoft rilascia le patch di sicurezza in base alle esigenze e così via.**
    1. Microsoft fornisce gli aggiornamenti del sistema operativo a HoloLens esattamente come avviene per Windows 10. In genere sono disponibili due aggiornamenti principali all'anno, uno in primavera, uno in autunno. Poiché HoloLens è un dispositivo Windows, il concetto di aggiornamento è lo stesso di qualsiasi altro dispositivo Windows. Microsoft rilascia le patch di sicurezza in base alle esigenze e segue lo stesso concetto di qualsiasi altro dispositivo Windows.
1. **Protezione avanzata del sistema operativo: quali opzioni sono disponibili per la protezione avanzata del sistema operativo?  È possibile rimuovere o arrestare app o servizi non necessari?**
    1. HoloLens si comporta come uno smartphone. È paragonabile ad altri dispositivi Windows moderni. HoloLens può essere gestito da Microsoft Intune o da altre soluzioni moderne di gestione dei dispositivi, ad esempio MobileIron, Airwatch o Soti. Esistono criteri che è possibile impostare in questi sistemi di gestione per inserire i criteri di sicurezza nel dispositivo e per la protezione avanzata del dispositivo. È anche possibile eliminare eventuali applicazioni non necessarie, se necessario.
1. **Come verranno gestite e aggiornate le applicazioni software? Quale controllo è necessario per definire quali app vengono caricate e il processo di aggiornamento delle app presenti in Microsoft Store?**
    1. HoloLens ottiene le applicazioni software solo tramite Windows Store. È possibile installare solo i pacchetti dell'applicazione Appx, sviluppati per l'uso di HoloLens. È possibile visualizzare questo valore nella Microsoft Store con un piccolo logo accanto all'applicazione che mostra il dispositivo HoloLens. Qualsiasi controllo sulla gestione delle applicazioni dello Store si applica anche a HoloLens. È possibile usare il concetto di negozio ufficiale o di negozio per le aziende. Le app possono essere caricate in locale (processo manuale per caricare un'app in un dispositivo Windows) o gestite tramite mdm in modo che le app siano estratta automaticamente dallo Store quando necessario.
1. **Qual è la frequenza degli aggiornamenti alle app nello Store per HoloLens?**
    1. Quando si segue lo stesso concetto di Microsoft Store ed eseguire il pull delle app da questa posizione, il ciclo di aggiornamento è determinato dallo sviluppatore dell'applicazione. Tutte le opzioni di gestione che è necessario controllare il meccanismo di aggiornamento nello Store si applicano anche a HoloLens.
1. **È disponibile una funzionalità di avvio sicuro per HoloLens?**
    1. Sì
1. **È possibile disabilitare o disconnettere il supporto delle periferiche dal dispositivo?**
    1. Sì
1. **È possibile controllare o disabilitare l'uso di porte nel dispositivo?**
    1. HoloLens contiene solo due porte(una per le cuffi e una per la ricarica o la connessione ai PC). Non è possibile disabilitare la porta per motivi di funzionalità e ripristino.
1. **Antivirus, rilevamento degli endpoint, IPS, elenco consenti controllo app: qualsiasi possibilità di eseguire antivirus, rilevamento degli endpoint, IPS, elenco di controllo delle app consentiti e così via.**
    1. Windows Holographic for Business (suite commerciale) supporta Windows Defender Smart Screen. Se un'azienda antivirus crea e pubblica la propria app nel piattaforma UWP (Universal Windows Platform), può essere scaricata in HoloLens. Attualmente, nessuna società ha eseguito questa operazione per HoloLens.
    1. È possibile consentire le app usando Microsoft Enterprise Store, in cui è possibile scegliere solo le app specifiche che è possibile scaricare. Inoltre, tramite MDM è possibile bloccare le app specifiche che possono essere eseguite o persino viste nel dispositivo.
1. **È possibile mettere in quarantena il dispositivo dalla rete prod fino ad aggiornare il dispositivo se è stato offline per un lungo periodo di tempo?  Ad esempio, il dispositivo è stato acceso in un cassetto non acceso per un periodo (sei mesi) e non ha ricevuto aggiornamenti, patch e così via.  Quando tenta di accedere alla rete, è possibile contrassegnarla e dire che è necessario eseguire l'aggiornamento in un'altra rete prima di essere contestato per l'aggiunta alla rete.**
    1. Si tratta di un elemento che può essere gestito a livello di infrastruttura da un server MDM o locale. Il dispositivo può essere contrassegnato come non conforme se non soddisfa una versione di aggiornamento specificata.
1. **Microsoft include back doors o l'accesso ai servizi che consentono a Microsoft di connettersi al dispositivo per la condivisione dello schermo o il supporto remoto a p pmento?**
    1. No
1. **Quando viene generato un certificato PKI per la comunicazione attendibile, si vuole che il certificato venga generato nel dispositivo in modo da sapere che si trova solo in tale dispositivo, univoco per tale dispositivo e non può essere esportato o usato per rappresentare il dispositivo. Questo vale per HoloLens? In caso di errore, esiste una potenziale mitigazione?**
    1. CSR per SCEP viene generato nel dispositivo stesso. Intune e il connettore SCEP locale consentono di proteggere le richieste aggiungendo e verificando una stringa di richiesta inviata al client.
    1. Poiché HoloLens (prima generazione e seconda generazione) ha un modulo TPM, questi certificati vengono archiviati nel modulo TPM e non possono essere estratti. Inoltre, anche se fosse possibile estrarlo, le stringhe di verifica non potevano essere verificate in un dispositivo diverso, rendendo inutilizzabili i certificati o la chiave in dispositivi diversi.
