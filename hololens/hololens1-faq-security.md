---
title: Domande frequenti sulla sicurezza
description: Non perderti le domande e le risposte frequenti sulla sicurezza relative ai dispositivi HoloLens di realtà mista.
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
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439032"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Domande frequenti sulla sicurezza di HoloLens (Prima generazione)

1. **Qual è il livello di protezione dei dati offerto da HoloLens 1?**
    1. Vedere [Crittografia BitLocker di HoloLens (Prima generazione)](hololens1-encryption.md)
1. **Che tipo di connessione wireless utilizza?**
    1. 802.11ac e Bluetooth 4.1 LE
1. **Che tipo di architettura integra?  Ad esempio: punto a punto, mesh o altro?**
    1. Si può usare la rete Wi-Fi in modalità infrastruttura per comunicare con altri punti di accesso wireless.
    1. Bluetooth può essere usato per parlare peer-to-peer tra più HoloLens se l'applicazione dei clienti lo supporta o ad altri Bluetooth dispositivi.
1. **Che cos'è il codice FCC ID?**
    1. C3K1688
1. **Su quale intervallo di frequenza e canali opera il dispositivo? Sono aspetti configurabili?**
    1. Wi-Fi: l'intervallo di frequenze non è configurabile dall'utente e varia in base al paese di utilizzo. Negli Stati Uniti, il Wi-Fi usa sia i canali da 2,4 GHz (1-11) che quelli da 5 GHz (36-64, 100-165).
    1. Bluetooth: la tecnologia Bluetooth usa l'intervallo standard da 2,4-2,48 GHz.
1. **Il dispositivo può autorizzare o bloccare frequenze specifiche?**
    1. Questo non è controllabile dall'utente/dispositivo.
1. **Qual è il livello di potenza in trasmissione e ricezione? È regolabile? Cos'è il raggio d'azione?**
    1. Gli standard utilizzati nei test delle emissioni sono disponibili [qui](https://fccid.io/C3K1688). Il raggio d'azione dipende in larga parte dal punto di accesso e dall'ambiente, ma è pressoché in linea con quello di altri dispositivi di alta qualità, come telefoni, tablet o PC.
1. **Qual è il ciclo di lavoro/vita per il normale funzionamento?**
    1. 2-3 ore di utilizzo attivo e fino a due settimane di standby
    1. Il ciclo di vita della batteria non è disponibile.
1. **Come agisce il dispositivo in trasmissione e ricezione quando non sono presenti strumenti all'interno del raggio?**
    1. La trasmissione/ricezione di HoloLens segue il modello standard dei dispositivi Wi-Fi/Bluetooth. Ai margini del suo raggio d'azione, è consueto rilevare un input che si fa instabile fino a disconnettersi completamente, ma una volta tornati all'interno del raggio dovrebbe riconnettersi rapidamente.
1. **Che cos'è la densità di distribuzione per centimetro quadrato?**
    1. Dipende dalla propria infrastruttura di rete.
1. **Il dispositivo può usare l'infrastruttura come un client?**
    1. Sì
1. **Quale protocollo viene usato?**
    1. HoloLens non usa alcun protocollo proprietario.
1. **Con quale frequenza viene aggiornato il sistema operativo di HL?  Esiste un programma predefinito?  Microsoft rilascia patch di sicurezza a seconda della necessità.**
    1. Microsoft offre aggiornamenti per il sistema operativo di HoloLens secondo le stesse identiche modalità seguite per Windows 10. In genere, ogni anno vengono rilasciati due principali aggiornamenti: uno in primavera, uno in autunno. Poiché HoloLens è un dispositivo Windows, i concetti relativi agli aggiornamento sono uguali a quelli di qualsiasi altro dispositivo Windows. Microsoft rilascia delle patch di sicurezza in base alle esigenze, seguendo gli stessi concetti applicati ad ogni altro dispositivo Windows.
1. **Quali opzioni sono disponibili per la protezione avanzata del sistema operativo?  È possibile rimuovere o arrestare app o servizi non necessari?**
    1. HoloLens si può compare con uno smartphone. È paragonabile ad altri moderni dispositivi Windows. HoloLens può essere gestito tramite Microsoft Intune o con altre soluzioni di gestione per dispositivi moderni, come MobileIron, Airwatch o Soti. Con tali sistemi di gestione è possibile applicare al dispositivo criteri di sicurezza e protezione avanzata. È anche possibile eliminare applicazioni che l'utente può ritenere di scarsa utilità.
1. **Come vengono gestite e aggiornate le applicazioni software? Di quanto controllo si dispone in merito alla definizione di quali le app caricare e al processo di aggiornamento delle app disponibili nel Microsoft Store?**
    1. HoloLens scarica le applicazioni software solo dal Windows Store. È possibile installare solo pacchetti di applicazioni Appx, sviluppati per l'uso di HoloLens. Puoi vederlo in Microsoft Store con un piccolo logo accanto all'applicazione che mostra il dispositivo HoloLens. Qualunque controllo di cui l'utente disponga sulla gestione delle applicazioni dello Store si applica anche ad HoloLens. È possibile usare la versione dello Store ufficiale o quella per le aziende. Le app possono essere trasferite tramite sideload (processo manuale per caricare un'app su un dispositivo Windows), oppure possono essere gestite tramite un MDM in modo che vengano automaticamente estratte dallo Store quando necessario.
1. **Qual è la frequenza degli aggiornamenti delle app per HoloLens presenti nello Store?**
    1. Nonostante si seguano gli stessi concetti di Microsoft Store e da lì si traggano le app, il ciclo di aggiornamento viene determinato dallo sviluppatore dell'applicazione. Tutte le opzioni di gestione di cui si disponga per controllare i meccanismi di aggiornamento all'interno dello Store restano valide anche per HoloLens.
1. **Esiste una funzionalità di avvio protetto per HoloLens?**
    1. Sì
1. **È possibile disabilitare o scollegare periferiche di supporto dal dispositivo?**
    1. Sì
1. **È possibile controllare o disabilitare l'uso delle porte sul dispositivo?**
    1. HoloLens contiene solo due porte (una per le cuffie e una per la ricarica o la connessione ai PC). Non è possibile disabilitare la porta, per ragioni di funzionalità e di ripristino.
1. **Antivirus, rilevamento endpoint, IPS, elenco consenti controllo app - Qualsiasi possibilità di eseguire antivirus, rilevamento degli endpoint, IPS, elenco consenti controllo app e così via.**
    1. Windows Holographic for Business (Commercial Suite) supporta Windows Defender SmartScreen. Se un'azienda di antivirus crea e pubblica la propria app sulla piattaforma UWP (Universal Windows Platform), sarà possibile scaricarla su HoloLens. Attualmente, nessuna azienda ha sviluppato tale app per HoloLens.
    1. Sul Microsoft Enterprise Store è possibile creare un elenco di app autorizzate, selezionando le specifiche app che sarà possibile scaricare. Inoltre, tramite MDM è possibile fissare quali app possono essere eseguite o anche solo visualizzate sul dispositivo.
1. **È possibile mettere in quarantena il dispositivo dalla rete di produzione finché il dispositivo non viene aggiornato, nel caso sia stato offline per un periodo di tempo prolungato?  Es. Il dispositivo è stato seduto in un cassetto non alimentato per un periodo (sei mesi) e non ha ricevuto aggiornamenti, patch e così via.  Quando tenta di entrare in rete, possiamo contrassegnarlo e dire che devi eseguire l'aggiornamento su un'altra rete prima di essere reclamato per entrare nella rete.**
    1. Si tratta di un'operazione che può essere gestita a livello di infrastruttura tramite un server MDM o un server locale. Se non soddisfa una versione dell'aggiornamento specifica, il dispositivo può essere segnalato come non conforme.
1. **Esiste qualche backdoor o altro accesso ai servizi che consenta a Microsoft di connettersi al dispositivo ai fini eventuali di condivisione dello schermo o supporto remoto?**
    1. No
1. **Quando viene generato un certificato PKI per una comunicazione attendibile, deve essere generato sul dispositivo, in modo da renderlo disponibile solo su quello e che sia unico per tale dispositivo, senza alcuna possibilità di esportazione o utilizzo per la rappresentazione del dispositivo. Questo risulta vero per HoloLens? In caso contrario, esistono misure di prevenzione?**
    1. CSR per SCEP viene generato sul dispositivo stesso. Intune e il connettore SCEP locale consentono di proteggere le richieste stesse aggiungendo e verificando una stringa di verifica inviata al client.
    1. Dal momento che HoloLens (prima e seconda generazione) include un modulo TPM, questi certificati verranno archiviati nel modulo TPM, senza possibilità di estrazione. Inoltre, anche se l'esportazione fosse possibile, le stringhe di verifica non potrebbero essere verificate su un dispositivo diverso, rendendo impossibile l'esecuzione del rendering dei certificati o delle chiavi su altri dispositivi.
