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
ms.localizationpriority: high
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 0e3b7f40aa6d5163b6d58b7f21b9ea6daa9cc9b4
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284007"
---
# Domande frequenti sulla sicurezza di HoloLens (Prima generazione)

1. **Qual è il livello di protezione dei dati offerto da HoloLens 1?**
    1. Vedere [Crittografia BitLocker di HoloLens (Prima generazione)](hololens1-encryption.md)
1. **Che tipo di connessione wireless utilizza?**
    1. 802.11ac e Bluetooth 4.1 LE
1. **Che tipo di architettura integra?  Ad esempio: point to point, mesh o altro?**
    1. Si può usare la rete Wi-Fi in modalità infrastruttura per comunicare con altri punti di accesso wireless.
    1. Il Bluetooth può essere usato per la comunicazione peer-to-peer tra vari HoloLens, se l'applicazione dei clienti lo supporta, oppure verso altri dispositivi Bluetooth.
1. **Che cos'è il codice FCC ID?**
    1. C3K1688
1. **Su quale intervallo di frequenza e canali opera il dispositivo? Sono aspetti configurabili?**
    1. Wi-Fi: l'intervallo di frequenze non è configurabile dall'utente e varia in base al paese di utilizzo. Negli Stati Uniti, il Wi-Fi usa sia i canali da 2,4 GHz (1-11) che quelli da 5 GHz (36-64, 100-165).
    1. Bluetooth: la tecnologia Bluetooth usa l'intervallo standard da 2,4-2,48 GHz.
1. **Il dispositivo può autorizzare o bloccare frequenze specifiche?**
    1. Questo aspetto non è controllabile dall'utente tramite il dispositivo.
1. **Qual è il livello di potenza in trasmissione e ricezione? È regolabile? Cos'è il raggio d'azione?**
    1. Gli standard utilizzati nei test delle emissioni sono disponibili [qui](https://fccid.io/C3K1688). Il raggio d'azione dipende in larga parte dal punto di accesso e dall'ambiente, ma è pressoché in linea con quello di altri dispositivi di alta qualità, come telefoni, tablet o PC.
1. **Qual è il ciclo di lavoro/vita per il normale funzionamento?**
    1. 2-3hrs in uso attivo e fino a 2 settimane in standby.
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
1. **Quali opzioni sono disponibili per la protezione avanzata del sistema operativo?  È possibile rimuovere o arrestare le app o i servizi non necessari?**
    1. HoloLens si può compare con uno smartphone. È paragonabile ad altri moderni dispositivi Windows. HoloLens può essere gestito tramite Microsoft Intune o con altre soluzioni di gestione per dispositivi moderni, come MobileIron, Airwatch o Soti. Con tali sistemi di gestione è possibile applicare al dispositivo criteri di sicurezza e protezione avanzata. È anche possibile eliminare applicazioni che l'utente può ritenere di scarsa utilità.
1. **Come vengono gestite e aggiornate le applicazioni software? Di quanto controllo si dispone in merito alla definizione di quali le app caricare e al processo di aggiornamento delle app disponibili nel Microsoft Store?**
    1. HoloLens scarica le applicazioni software solo dal Windows Store. È possibile installare solo pacchetti di applicazioni Appx, sviluppati per l'uso di HoloLens. È possibile distinguerli in Microsoft Store grazie a un piccolo logo posto accanto all'applicazione, il quale mostra il dispositivo HoloLens. Qualunque controllo di cui l'utente disponga sulla gestione delle applicazioni dello Store si applica anche ad HoloLens. È possibile usare la versione dello Store ufficiale o quella per le aziende. Le app possono essere trasferite tramite sideload (processo manuale per caricare un'app su un dispositivo Windows), oppure possono essere gestite tramite un MDM in modo che vengano automaticamente estratte dallo Store quando necessario.
1. **Qual è la frequenza degli aggiornamenti delle app per HoloLens presenti nello Store?**
    1. Nonostante si seguano gli stessi concetti di Microsoft Store e da lì si traggano le app, il ciclo di aggiornamento viene determinato dallo sviluppatore dell'applicazione. Tutte le opzioni di gestione di cui si disponga per controllare i meccanismi di aggiornamento all'interno dello Store restano valide anche per HoloLens.
1. **Esiste una funzionalità di avvio protetto per HoloLens?**
    1. Sì
1. **È possibile disabilitare o scollegare periferiche di supporto dal dispositivo?**
    1. Sì
1. **È possibile controllare o disabilitare l'uso delle porte sul dispositivo?**
    1. HoloLens include solo 2 porte, una per le cuffie e una per la ricarica o la connessione al PC. Non è possibile disabilitare la porta, per ragioni di funzionalità e di ripristino.
1. **È possibile eseguire una scansione antivirus, rilevare endpoint, IPS, attendibilità delle app e così via?**
    1. Windows Holographic for Business (Commercial Suite) supporta Windows Defender SmartScreen. Se un'azienda di antivirus crea e pubblica la propria app sulla piattaforma UWP (Universal Windows Platform), sarà possibile scaricarla su HoloLens. Attualmente, nessuna azienda ha sviluppato tale app per HoloLens.
    1. Sul Microsoft Enterprise Store è possibile creare un elenco di app autorizzate, selezionando le specifiche app che sarà possibile scaricare. Inoltre, tramite MDM è possibile fissare quali app possono essere eseguite o anche solo visualizzate sul dispositivo.
1. **È possibile mettere in quarantena il dispositivo dalla rete di produzione finché il dispositivo non viene aggiornato, nel caso sia stato offline per un periodo di tempo prolungato?  Es. Il dispositivo è rimasto in un cassetto, mai acceso, durante un certo periodo di tempo (6 mesi) e non ha ricevuto alcun aggiornamento, patch o quant'altro. Quando si tenta l'accesso alla rete, è possibile segnalare la necessità di eseguire l'aggiornamento tramite un'altra rete, prima che il dispositivo sia considerato conforme a prender parte a tale rete.**
    1. Si tratta di un'operazione che può essere gestita a livello di infrastruttura tramite un server MDM o un server locale. Se non soddisfa una versione dell'aggiornamento specifica, il dispositivo può essere segnalato come non conforme.
1. **Esiste qualche backdoor o altro accesso ai servizi che consenta a Microsoft di connettersi al dispositivo ai fini eventuali di condivisione dello schermo o supporto remoto?**
    1. No
1. **Quando viene generato un certificato PKI per una comunicazione attendibile, deve essere generato sul dispositivo, in modo da renderlo disponibile solo su quello e che sia unico per tale dispositivo, senza alcuna possibilità di esportazione o utilizzo per la rappresentazione del dispositivo. Questo risulta vero per HoloLens? In caso contrario, esistono misure di prevenzione?**
    1. CSR per SCEP viene generato sul dispositivo stesso. Intune e il connettore SCEP locale contribuiscono alla protezione delle richieste, aggiungendo e verificando una stringa di verifica da inviare al client.
    1. Dal momento che HoloLens (prima e seconda generazione) include un modulo TPM, questi certificati verranno archiviati nel modulo TPM, senza possibilità di estrazione. Inoltre, anche se l'esportazione fosse possibile, le stringhe di verifica non potrebbero essere verificate su un dispositivo diverso, rendendo impossibile l'esecuzione del rendering dei certificati o delle chiavi su altri dispositivi.
