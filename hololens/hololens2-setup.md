---
title: Preparare una nuova HoloLens 2
description: Informazioni su come configurare e modificare il dispositivo HoloLens 2 per la prima volta, inclusi suggerimenti per l'integrità e la sicurezza e guide hardware.
keywords: hololens, luci, fit, comfort, parti
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 77c061c53806e7410d73ecf3aaa20d74c217ea33
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190413"
---
# <a name="get-your-hololens-2-ready-to-use"></a>Prepararsi per HoloLens 2'uso

Le procedure seguenti consentono di configurare un HoloLens 2 per la prima volta.

## <a name="charge-your-hololens"></a>Addebitare i costi HoloLens

Connessione l'alimentatore alla porta di ricarica usando il cavo USB-C (incluso). Collegare l'alimentatore a una presa di alimentazione. L'alimentatore e il cavo USB-C-to-C fornito con il dispositivo sono il modo migliore per caricare il HoloLens 2. Il caricatore fornisce 18W di potenza (9 V a 2A). Usando il caricatore a pareti fornito, HoloLens 2 dispositivi possono caricare la batteria in meno di 65 minuti quando il dispositivo è in standby.

La velocità e la velocità di ricarica possono variare a seconda dell'ambiente in cui è in esecuzione il dispositivo.

- Quando il dispositivo è in carica, l'indicatore della batteria si accende per indicare il livello di carica corrente.  L'ultima luce si dissolve in entrata e in uscita per indicare l'addebito attivo.
- Quando l'HoloLens è on, l'indicatore della batteria visualizza il livello della batteria in incrementi.
- Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%.
- Se il livello della batteria è molto basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente, quindi si esce.

Per [informazioni dettagliate sull'addebito dei dispositivi, vedere](hololens2-charging.md#charging-the-device) qui se sono necessarie altre informazioni. 

## <a name="adjust-fit"></a>Adatta

Posizionare il HoloLens 2 sulla testa. Se si usurano gli occhiali, lasciarli su.  Il rilievo della fronte deve essere comodamente sulla fronte e la fascia posteriore deve essere posta nella parte centrale della testa.

Se necessario, estendere la fascetta ruotando la ruota di regolazione e quindi allontanare il plettrino.

![HoloLens 2 adattabilità e regolazioni.](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>Collegare e scollegare il sovraccarico

Il sovraccarico non è necessario, ma può rendere più HoloLens 2 durante lunghi periodi di utilizzo.

Per scollegare la parte anteriore del sovraccarico, distogliere l'anello e scorrerlo attraverso il ciclo ritrattibile sul riquadro della fronte. Per ricollegarlo, estrarre il ciclo e scorrere di nuovo l'anello.

Per scollegare la parte posteriore del sovraccarico, premere il pulsante sotto ogni scheda di connessione ed eseguire il pull. Per ricollegare il collegamento, eseguire il push delle schede di connessione negli slot fino a quando non fanno clic.

![collegare o rimuovere il HoloLens 2 head.](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>Attivare l'HoloLens 2

Per attivare la HoloLens 2, premere il pulsante Di alimentazione.  I LED sotto il pulsante di alimentazione visualizzano il livello della batteria.

> [!NOTE]
> Per accendere HoloLens 2 per la prima volta, dopo l'unboxing, tenere premuto il pulsante di alimentazione per almeno 4 secondi per attivarlo. La volta successiva che si HoloLens 2, l'avvio verrà avviato dopo una breve pressione del pulsante di alimentazione.

### <a name="power-button-actions-for-different-power-transitions"></a>Azioni del pulsante di alimentazione per diverse transizioni di alimentazione

| Per | Eseguire questa azione | Il HoloLens 2 a tale scopo |
| - | - | - |
| Per attivare | Pressione di un singolo pulsante. | Tutte e cinque le luci si accendono e quindi cambiano per indicare il livello della batteria. Dopo quattro secondi, viene riprodotto un suono. |
| Dormire | Pressione di un singolo pulsante. | Tutte e cinque le luci si accendono, quindi si sfumano una alla volta. Dopo lo spegnimento delle luci, viene riprodotto un suono e sullo schermo viene visualizzato "Goodbye". |
| Per riattivare dalla sospensione | Pressione di un singolo pulsante. | Tutte e cinque le luci si accendono e quindi cambiano per indicare il livello della batteria. Viene riprodotto immediatamente un suono. |
| Per disattivare | Premere e tenere premuto per 5s. |  Tutte e cinque le luci si accendono, quindi si sfumano una alla volta. Dopo lo spegnimento delle luci, viene riprodotto un suono e sullo schermo viene visualizzato "Goodbye". |
| Per forzare HoloLens riavvio se non risponde | Premere e tenere premuto per 10s. | Tutte e cinque le luci si accendono, quindi si sfumano una alla volta. Dopo lo spegnimento delle luci. |

## <a name="hololens-behavior-reference"></a>HoloLens sul comportamento

Non si è certi del significato delle luci HoloLens dispositivo? Si vuole sapere come HoloLens comportamento durante l'addebito?  Ecco un aiuto.

### <a name="charging-behavior"></a>Comportamento di addebito

| Stato del dispositivo | Azione | HoloLens 2 questa operazione |
| - | - | - |
| OFF | Collegare il cavo USB | Il dispositivo passa a ON con indicatori di illuminazione che mostrano il livello della batteria e il dispositivo inizia a ricaricarsi.
| ON | Rimuovere il cavo USB | Il dispositivo smette di ricaricarsi
| ON | Collegare il cavo USB | Il dispositivo avvia l'addebito
| DORMIRE | Collegare il cavo USB | Il dispositivo avvia l'addebito
| DORMIRE | Rimuovere il cavo USB | Il dispositivo smette di ricaricarsi
| ON con cavo USB collegato | Disattiva dispositivo | Il dispositivo passa a ON con indicatori di illuminazione che mostrano il livello della batteria e il dispositivo inizierà a ricaricarsi |

### <a name="lights-that-indicate-the-battery-level"></a>Luci che indicano il livello della batteria

| Numero di luci | Livello della batteria |
| - | - |
| Quattro luci a tinta unita, una luce in uscita e in uscita | Tra il 100% e l'81% (completamente addebitato) |
| Tre luci a tinta unita, una luce in uscita e in uscita | Tra l'80% e il 61% |
| Due luci a tinta unita, una luce in uscita e in uscita | Tra il 60% e il 41% |
| Una luce a tinta unita, una luce in uscita e in uscita | Tra il 40% e il 21% |
| Una luce che si dissolve in e fuori | Tra il 20% e il 5% o inferiore (batteria critica) |

### <a name="sleep-behavior"></a>Comportamento di sospensione

| Stato del dispositivo | Azione | HoloLens 2 questa operazione |
| - | - | - |
| ON | Pressione di un singolo pulsante di alimentazione | Il dispositivo passa a SLEEP e disattiva tutte le luci degli indicatori |
| ON | Nessun movimento per 3 minuti | Transizione del dispositivo a SLEEP e disattiva tutte le luci degli indicatori |
| DORMIRE | Pulsante di alimentazione singolo Premere | Il dispositivo passa a ON e attiva le luci degli indicatori |

### <a name="lights-to-indicate-problems"></a>Luci per indicare i problemi

| Quando si esegue questa operazione | Le luci fanno questo | Ciò significa che |
| - | - | - |
| Premere il pulsante Di alimentazione. | Una luce lampeggia cinque volte, quindi si spegne. | La batteria HoloLens è in esaurimento. Addebitare il HoloLens. |
| Premere il pulsante Di alimentazione. | Tutte e cinque le luci lampeggiano cinque volte, quindi si spegnino. |  HoloLens non può essere avviato correttamente ed è in stato di errore. [Reinstallare il sistema operativo](hololens-recovery.md) per ripristinare il dispositivo. |
| Premere il pulsante Di alimentazione. | La prima, la terza e la terza luce lampeggiano continuamente. |  HoloLens possibile che si sia verificato un errore hardware. Contattare [il supporto tecnico](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb). |

## <a name="safety-and-comfort"></a>Sicurezza e comfort

### <a name="use-hololens-in-safe-surroundings"></a>Usare HoloLens in un ambiente sicuro

Usare le HoloLens in uno spazio sicuro, senza ostruzione e rischi di inciampo. Non usarlo quando è necessario un campo di vista chiaro o non è possibile eseguire l'attenzione completa, ad esempio quando si usa un veicolo o si esercitino altre attività potenzialmente pericolose.

### <a name="stay-comfortable"></a>Rimanere a proprio agio

Mantenere le prime sessioni con HoloLens breve e assicurarsi di eseguire le interruzioni. In caso di disagi, fermarsi e attendere fino a quando non si è migliori. Ad esempio, i movimenti temporanei, le emozioni di movimento, le vertigini, l'orientamento, la difficoltà, l'affaticamento, l'affaticamento oculare o gli occhi secchi.

Vedere [gli avvisi sulla sicurezza del prodotto e le istruzioni](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions).

> [!div class="nextstepaction"]
> [Configurare l'HoloLens 2](hololens2-start.md)
