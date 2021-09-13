---
title: Preparare una nuova HoloLens 2
description: Informazioni su come configurare e modificare il dispositivo HoloLens 2 per la prima volta, inclusi suggerimenti per l'integrità e la sicurezza e guide hardware.
keywords: hololens, lights, fit, comfort, parts
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036087"
---
# <a name="get-your-hololens-2-ready-to-use"></a>Prepara il HoloLens 2'uso

Le procedure seguenti consentono di configurare una HoloLens 2 per la prima volta.

## <a name="charge-your-hololens"></a>Addebitare il HoloLens

Connessione'alimentatore alla porta di ricarica usando il cavo USB-C (incluso). Collegare l'alimentatore a una presa di alimentazione. L'alimentatore e il cavo USB-C-to-C forniti con il dispositivo sono il modo migliore per caricare il HoloLens 2. Il caricabatterie fornisce 18W di alimentazione (9 V a 2A). Usando il caricabatterie a parete fornito, HoloLens 2 i dispositivi possono ricaricare la batteria in meno di 65 minuti quando il dispositivo è in standby.

La velocità e la velocità di ricarica possono variare a seconda dell'ambiente in cui è in esecuzione il dispositivo.

- Quando il dispositivo è in carica, l'indicatore della batteria si accende per indicare il livello di carica corrente.  L'ultima luce si dissolverà in entrata e in uscita per indicare la ricarica attiva.
- Quando il HoloLens è on, l'indicatore della batteria visualizza il livello della batteria in incrementi.
- Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%.
- Se il livello della batteria è criticamente basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente e quindi si spegne.

I [dettagli completi sulla ricarica dei dispositivi possono essere letti qui](hololens2-charging.md#charging-the-device) se sono necessarie altre informazioni. 

## <a name="adjust-fit"></a>Adattare l'adattamento

Posizionare il HoloLens 2 sulla testa. Se si indossano occhiali da vista, lasciarli.  Il rilievo della fronte dovrebbe sedersi comodamente sulla fronte e la fascia posteriore dovrebbe sedersi nella parte centrale della testa.

Se necessario, estendere il fasciatoio ruotando la ruota di regolazione e quindi allentare la cinghia.

![HoloLens 2 adattabilità e regolazioni.](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>Collegare e scollegare la cinghia

La cinghia in testa non è necessaria, ma può rendere più HoloLens 2 durante lunghi periodi di utilizzo.

Per scollegare la parte anteriore della cinghia, scollegare il cinghio e scorrerlo attraverso il ciclo retrattile sul rilievo della fronte. Per ricollegarlo, tirare fuori il ciclo e far scorrere di nuovo la cinghia.

Per scollegare la parte posteriore della cinghia, premere il pulsante sotto ogni scheda di connessione ed eseguire il pull con cautela. Per ricollegare la connessione, eseguire nuovamente il push delle schede di connessione negli slot fino a quando non fanno clic.

![collegare o rimuovere il HoloLens 2 della testa.](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>Attivare il HoloLens 2

Per attivare la HoloLens 2, premere il pulsante Di alimentazione.  I LED sotto il pulsante Di alimentazione visualizzano il livello della batteria.

> [!NOTE]
> Per accendere HoloLens 2 per la prima volta, dopo l'unboxing, tenere premuto il pulsante di alimentazione per almeno 4 secondi per attivarlo. La volta successiva che si HoloLens 2, verrà avviato dopo una breve pressione del pulsante di alimentazione.

### <a name="power-button-actions-for-different-power-transitions"></a>Azioni del pulsante di alimentazione per diverse transizioni di alimentazione

| Per | Eseguire questa azione | Il HoloLens 2 a tale scopo |
| - | - | - |
| Per attivare | Premere un solo pulsante. | Tutte e cinque le luci si accendono e quindi cambiano per indicare il livello della batteria. Dopo quattro secondi, viene riprodotto un suono. |
| Dormire | Premere un solo pulsante. | Tutte e cinque le luci si accendono, quindi sfumare una alla volta. Dopo che le luci si sono spente, viene riprodotto un suono e sullo schermo viene visualizzato "Goodbye". |
| Per riattivare la sospensione | Premere un solo pulsante. | Tutte e cinque le luci si accendono e quindi cambiano per indicare il livello della batteria. Viene riprodotto immediatamente un suono. |
| Per disattivare | Premere e tenere premuto per 5s. |  Tutte e cinque le luci si accendono, quindi sfumare una alla volta. Dopo che le luci si sono spente, viene riprodotto un suono e sullo schermo viene visualizzato "Goodbye". |
| Per forzare HoloLens riavvio se non risponde | Premere e tenere premuto per 10s. | Tutte e cinque le luci si accendono, quindi sfumare una alla volta. Dopo che le luci si sono spente. |

## <a name="hololens-behavior-reference"></a>HoloLens riferimento al comportamento

Non si è certi del significato dell'indicatore HoloLens'indicatore? Si vuole sapere come HoloLens comportamento durante la ricarica?  Ecco qualche aiuto.

### <a name="charging-behavior"></a>Comportamento di addebito

| Stato del dispositivo | Azione | HoloLens 2 questa operazione |
| - | - | - |
| OFF | Collegare il cavo USB | Il dispositivo passa a ON con le luci indicatore che mostrano il livello della batteria e il dispositivo avvia la ricarica.
| ON | Rimuovere il cavo USB | Il dispositivo interrompe la ricarica
| ON | Collegare il cavo USB | Il dispositivo avvia la ricarica
| DORMIRE | Collegare il cavo USB | Il dispositivo avvia la ricarica
| DORMIRE | Rimuovere il cavo USB | Il dispositivo interrompe la ricarica
| ON con cavo USB collegato | Disattivare Il dispositivo | Il dispositivo passa a ON con le luci indicatore che mostrano il livello della batteria e il dispositivo inizierà la ricarica |

### <a name="lights-that-indicate-the-battery-level"></a>Luci che indicano il livello della batteria

| Numero di luci | Livello della batteria |
| - | - |
| Quattro luci a tinta unita, una luce che sbiade in e fuori | Tra il 100% e l'81% (addebito completo) |
| Tre luci a tinta unita, una luce che sbiade in e fuori | Tra l'80% e il 61% |
| Due luci a tinta unita, una luce che sbiade in e fuori | Tra il 60% e il 41% |
| Una luce a tinta unita, una luce che sbiade in e fuori | Tra il 40% e il 21% |
| Una luce che sbiade in e fuori | Tra il 20% e il 5% o inferiore (batteria critica) |

### <a name="sleep-behavior"></a>Comportamento di sospensione

| Stato del dispositivo | Azione | HoloLens 2 questa operazione |
| - | - | - |
| ON | Premere un solo pulsante di alimentazione | Il dispositivo passa a SLEEP e disattiva tutte le luci indicatore |
| ON | Nessun movimento per 3 minuti | Transizione del dispositivo a SLEEP e disattiva tutte le luci indicatore |
| DORMIRE | Pulsante di alimentazione singolo Premere | Il dispositivo passa a ON e attiva le luci indicatore |

### <a name="lights-to-indicate-problems"></a>Luci per indicare i problemi

| Quando si esegue questa operazione | Le luci fanno questo | Questo significa che |
| - | - | - |
| Si preme il pulsante Di alimentazione. | Una luce lampeggia cinque volte, quindi si spegne. | La HoloLens della batteria è criticamente bassa. Addebitare il HoloLens. |
| Si preme il pulsante Di alimentazione. | Tutte e cinque le luci lampeggiano cinque volte, quindi si spegnino. |  HoloLens non può essere avviato correttamente e si trova in uno stato di errore. [Reinstallare il sistema operativo](hololens-recovery.md) per ripristinare il dispositivo. |
| Si preme il pulsante Di alimentazione. | La prima, la terza e la 5° luce lampeggiano continuamente. |  HoloLens possibile che si sia verificato un errore hardware. Contattare [il supporto](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb)tecnico . |

## <a name="safety-and-comfort"></a>Sicurezza e comfort

### <a name="use-hololens-in-safe-surroundings"></a>Usare HoloLens in ambienti sicuri

Usare il HoloLens in uno spazio sicuro, senza ostacoli e rischi di inciampo. Non usarlo quando è necessario un campo di visualizzazione chiaro o non è possibile prestare tutta l'attenzione, ad esempio durante il funzionamento di un veicolo o l'esecuzione di altre attività potenzialmente pericolose.

### <a name="stay-comfortable"></a>Mantenere la comodità

Mantenere le prime sessioni con HoloLens breve e assicurarsi di eseguire pause. In caso di disagio, fermarsi e stare in pace fino a quando non si è meglio. Ciò può includere sentimenti temporanei di tristezza, malattia del movimento, vertigini, disorientamento, mal di testa, affaticamento, affaticamento oculare o occhi secchi.

Vedere gli [avvisi di sicurezza del prodotto e le istruzioni](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions).

> [!div class="nextstepaction"]
> [Configurare la HoloLens 2](hololens2-start.md)
