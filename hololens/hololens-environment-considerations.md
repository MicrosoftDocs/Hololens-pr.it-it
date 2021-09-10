---
title: HoloLens sull'ambiente
description: Ottenere la migliore esperienza possibile usando HoloLens quando si ottimizza il dispositivo per gli occhi e l'ambiente.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: frame olografico, campo di visualizzazione, fov, calibrazione, spazi, ambiente, procedura, HoloLens, realtà mista, visori VR di realtà mista
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427847"
---
# <a name="hololens-environment-considerations"></a>HoloLens sull'ambiente

HoloLens combina l'olografico con il mondo "reale", posizionando gli ologrammi nell'ambiente circostante. Una finestra dell'app olografica "si blocca" sulla superficie, una penna olografica ruota sul tablet, le frecce di bunny siedono sopra la testa dell'amico inconsapevoli. Quando si usa un gioco o un'app immersive, il mondo olografico verrà distribuito per riempire l'ambiente circostante, ma è comunque possibile vedere e spostarsi nello spazio.

Gli ologrammi posizionati rimarranno nella posizione in cui sono stati inseriti, anche se si spegne il dispositivo.

## <a name="setting-up-an-environment"></a>Configurazione di un ambiente

HoloLens dispositivi sanno come posizionare ologrammi stabili e accurati tracciando *gli* utenti in uno spazio. Senza un monitoraggio appropriato, il dispositivo non comprende l'ambiente o l'utente al suo interno. Ologrammi può essere visualizzato in posizioni erre, non essere visualizzato ogni volta nello stesso punto o non essere visualizzato affatto. I dati usati per tenere traccia degli utenti sono rappresentati nella *mappa spaziale*.  

Il monitoraggio delle prestazioni è fortemente influenzato dall'ambiente in cui si trova l'utente e l'ottimizzazione di un ambiente per indurre un rilevamento stabile e coerente è un'arte anziché una scienza. Molti fattori ambientali diversi vengono combinati per consentire il rilevamento, ma gli sviluppatori di realtà mista possono tenere presenti diversi fattori per ottimizzare uno spazio per un monitoraggio migliore.

### <a name="lighting"></a>Luce

Windows Mixed Reality usa la luce visiva per tenere traccia della posizione dell'utente. Quando un ambiente è troppo chiaro, le fotocamere possono essere saturate e non viene visto nulla. Se l'ambiente è troppo scuro, le fotocamere non possono raccogliere informazioni sufficienti e non viene visualizzato nulla. L'illuminazione deve essere uniforme e sufficientemente intelligente che un essere umano possa vedere senza sforzo, ma non è così chiaro che la luce è difficile da guardare.  

Anche le aree in cui sono presenti punti di luce intensa in un'area dim globale sono problematiche, perché la fotocamera deve adattarsi quando si sposta all'ingresso e all'uscita da spazi luminosi. Ciò può causare la perdita del dispositivo e pensare che la modifica della luce equivale a una modifica della posizione. Livelli di luce stabili in un'area porteranno a un monitoraggio migliore.  

Qualsiasi illuminazione esterna può anche causare instabilità nello tracker, perché il sole può variare notevolmente nel tempo. Ad esempio, il rilevamento nello stesso spazio dell'estate rispetto al genere può produrre risultati drasticamente diversi, perché la luce di seconda mano all'esterno può essere maggiore in momenti diversi dell'anno.  

Se si ha un tachimetro, un 500-1000 stabile è un buon punto di partenza.  

#### <a name="types-of-lighting"></a>Tipi di illuminazione

Anche diversi tipi di luce in uno spazio possono influenzare il rilevamento. Le lampadine pulsano con l'elettricità ca in esecuzione: se la frequenza CA è 50 Hz, la luce pulsa a 50 Hz. Per un essere umano, questa pulsazione non viene notata. Tuttavia, HoloLens fotocamera a 30 fps di HoloLens vede queste modifiche: alcuni fotogrammi saranno ben illuminati, altri saranno scarsamente illuminati e altri saranno sovraesposte quando la fotocamera tenta di compensare gli pulse di luce.  

Negli Stati Uniti, lo standard della frequenza di elettricità è di 60 Hz, quindi gli pulse delle lampadine sono errati con la frequenza dei fotogrammi di HoloLens: gli pulse a 60 Hz sono allineati con la frequenza dei fotogrammi a 30 FPS di HoloLens. Tuttavia, molti paesi hanno uno standard di frequenza CA di 50 Hz, il che significa che alcuni fotogrammi HoloLens verranno acquisiti durante gli pulse e altri no. In particolare, è noto che l'illuminazione fluorescente in Europa causa problemi.  

È possibile provare a risolvere alcuni problemi di sfarfallio. Temperature, bulb age, and warm-up cycles are common causes of fluorescent sfarfallio and replacing bulbs may help. Può essere utile anche stringere le lampadine e assicurarsi che le estrazioni correnti siano costanti.  

### <a name="items-in-a-space"></a>Elementi in uno spazio

HoloLens usa punti di riferimento ambientali univoci, noti anche come *funzionalità*, per individuarsi in uno spazio.  

Un dispositivo non può quasi mai tenere traccia in un'area in cui le funzionalità sono scarse, perché il dispositivo non è in grado di sapere dove si trova nello spazio. L'aggiunta di funzionalità alle pareti di uno spazio è in genere un buon modo per migliorare il rilevamento. Poster, simboli collegati a una barriera, piante, oggetti univoci o altri elementi simili sono utili. Un desk disordinato è un buon esempio di ambiente che porta a un buon monitoraggio: in un'unica area sono presenti molte funzionalità diverse.  

Inoltre, usare funzionalità univoche nello stesso spazio. Lo stesso poster ripetuto più volte su una barriera, ad esempio, causerà confusione del dispositivo perché il HoloLens non saprà quale poster ripetitivo sta esaminando. Un modo comune per aggiungere caratteristiche univoche è usare linee di nastro mascheramento per creare modelli univoci, non ripetitivi lungo le pareti e il piano di uno spazio.  

Una domanda utile da porsi è: se si vede solo una piccola quantità della scena, è possibile individuarsi nello spazio in modo univoco? In caso contrario, è probabile che anche il dispositivo abbia problemi di rilevamento.

#### <a name="wormholes"></a>Wormhole

Se si hanno due aree o aree che hanno lo stesso aspetto, lo tracker potrebbe pensare che siano uguali. Ciò fa in modo che il dispositivo si invii a pensare che si trova in un'altra posizione. Questi tipi di aree ripetitive sono *d'ora in poi.*  

Per evitare worm tunnel, provare a evitare aree identiche nello stesso spazio. Le aree identiche possono talvolta includere stazioni di fabbrica, finestre in un edificio, rack server o stazioni di lavoro. L'etichettatura di aree o l'aggiunta di funzionalità univoche a ogni area simile può contribuire a mitigare i worm tunnel.

### <a name="movement-in-a-space"></a>Spostamento in uno spazio

Se l'ambiente è in continua evoluzione, il dispositivo non ha funzionalità stabili da individuare.  

Maggiore è il numero di oggetti in movimento che si verificano in uno spazio, incluse le persone, più facile è perdere il rilevamento. Lo spostamento di nastri trasportatori, elementi in diversi stati di costruzione e molte persone in uno spazio sono stati tutti noti per causare problemi di tracciamento.

Il HoloLens può adattarsi rapidamente a queste modifiche, ma solo quando tale area è chiaramente visibile al dispositivo. Le aree che non vengono viste con frequenza possono essere in ritardo rispetto alla realtà, causando errori nella mappa spaziale. Ad esempio, un utente analizza un amico e quindi si volta mentre l'amico esce dalla stanza. Una rappresentazione "fantasma" dell'elemento Friend verrà mantenuta nei dati di mapping spaziale fino a quando l'utente non esegue di nuovo l'analisi dello spazio vuoto.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Prossimità dell'utente agli elementi nello spazio

Analogamente al modo in cui gli esseri umani non possono concentrarsi bene sugli oggetti vicini agli occhi, HoloLens difficoltà quando gli oggetti sono vicini alle fotocamere. Se un oggetto è troppo vicino per essere visualizzato con entrambe le fotocamere o se un oggetto blocca una fotocamera, il dispositivo avrà molto più problemi con il rilevamento dell'oggetto.  

Le fotocamere possono vedere non più vicino a 15 cm da un oggetto.

### <a name="surfaces-in-a-space"></a>Superfici in uno spazio

Le superfici fortemente riflettenti avranno probabilmente un aspetto diverso a seconda dell'angolo, che influisce sul rilevamento. Si pensi a un'auto completamente nuova: quando ci si sposta attorno, la luce si riflette e si vedono oggetti diversi in superficie mentre ci si sposta. Per lo tracker, i diversi oggetti riflessi nella superficie rappresentano un ambiente che cambia e il dispositivo perde il rilevamento.

Gli oggetti meno luminosi sono più facili da rilevare.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi sulle impronte digitali

Fino a quando Wi-Fi abilitata, i dati della mappa verranno correlati con un'impronta digitale Wi-Fi, anche quando non sono connessi a una rete/router Wi-Fi effettiva. Senza Wi-Fi informazioni, lo spazio e gli ologrammi possono essere leggermente più lenti da riconoscere. Se i Wi-Fi cambiano in modo significativo, il dispositivo potrebbe pensare che si trova in uno spazio diverso.

L'identificazione di rete(ad esempio, SSID o indirizzo MAC) non viene inviata a Microsoft e tutti i riferimenti Wi-Fi vengono mantenuti locali nel HoloLens.

## <a name="mapping-new-spaces"></a>Mapping di nuovi spazi

Quando si immette un nuovo spazio (o se ne carica uno esistente), viene visualizzata un'immagine mesh che si estende nello spazio. Ciò significa che il dispositivo sta mappando l'ambiente circostante. Mentre un HoloLens apprenderà uno spazio nel tempo, sono disponibili suggerimenti e consigli per mappare gli spazi.

## <a name="environment-management"></a>Gestione dell'ambiente

Sono disponibili due impostazioni che consentono agli utenti di "pulire" gli ologrammi e HoloLens di "dimenticare" uno spazio. Esistono in ambienti **Ologrammi e nell'app** impostazioni, con la seconda impostazione visualizzata anche in **Privacy** nell'app impostazioni.  

1. **Eliminare gli ologrammi vicini.** Quando si seleziona questa impostazione, HoloLens cancella tutti gli ologrammi ancorati e tutti i dati mappa archiviati per lo "spazio corrente" in cui si trova il dispositivo. Una nuova sezione della mappa verrà creata e archiviata nel database per tale posizione dopo che gli ologrammi saranno nuovamente posizionati nello stesso spazio.

1. **Eliminare tutti gli ologrammi**. Selezionando questa impostazione, HoloLens cancella tutti i dati della mappa e gli ologrammi ancorati negli interi database di spazi. Non verranno individuati ologrammi e gli ologrammi dovranno essere posizionati di nuovo per archiviare nuovamente le sezioni della mappa nel database.

## <a name="hologram-quality"></a>Qualità ologramma

Ologrammi possono essere posizionati in tutto l'ambiente, ad alto, basso e intorno all'utente, ma saranno visualizzati tramite una cornice [olografica](/windows/mixed-reality/holographic-frame) che si trova davanti agli occhi. Per ottenere la visualizzazione migliore, assicurarsi di regolare il dispositivo in modo da visualizzare l'intero fotogramma. E non esitare a esplorare l'ambiente.

Perché gli [ologrammi](/windows/mixed-reality/hologram) siano chiari, chiari e stabili, HoloLens deve essere calibrato solo per l'utente. Quando si configura il HoloLens, si verrà guidati in questo processo. In seguito, se gli ologrammi non hanno un aspetto giusto o vengono visualizzati numerosi errori, è possibile apportare modifiche.

Se si verificano problemi durante il mapping degli spazi, provare a eliminare gli ologrammi nelle vicinanze e a ridefinire il mapping dello spazio.

### <a name="calibration"></a>Calibrazione

Se gli ologrammi sembrano instabilità o traballanti o se si verificano problemi di posizionamento degli ologrammi, la prima cosa da provare è [l'app Calibrazione](hololens-calibration.md). Questa app può essere utile anche in caso di problemi durante l'uso del HoloLens.

Per accedere all'app Calibrazione, passare a **Impostazioni**  >  **utilità di**  >  **sistema**. Selezionare **Apri calibrazione** e seguire le istruzioni.

Se un altro utente sta per usare il HoloLens, deve eseguire prima l'app Calibrazione in modo che il dispositivo sia configurato correttamente.

## <a name="temperature-and-regulatory-information"></a>Informazioni su temperatura e normative

[HoloLens informazioni normative:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)include informazioni su intervallo di temperatura, eliminazione, interferenze radio e TV e altro ancora.

Vedere i dettagli per "HoloLens" in [Materials and materials and materials >](https://www.microsoft.com/legal/compliance/materials-substances) REACH Article 33 Disclosure on Environmental Compliance (PDF).

Di seguito sono riportate alcune linee guida da seguire quando si usa il dispositivo:

1. Archiviare il dispositivo in un ambiente entro l'intervallo di temperatura (in standby o disattivato) per un'ora prima di usare il dispositivo.
1. Usare il dispositivo in un ambiente compreso nell'intervallo di temperatura.
1. Usare il dispositivo all'interno.
1. Usare il dispositivo in ombreggiatura; anche all'interno evitare la luce solare diretta attraverso finestre o lucernari.
1. Se si seguono le linee guida precedenti ma si verificano problemi imprevisti di surriscaldamento, seguire questa procedura per inviare [commenti e suggerimenti.](hololens-feedback.md) 
    1. Verificare **che la telemetria** completa **o** facoltativa sia abilitata nel dispositivo. In caso contrario, abilitarlo. 
    >[!CAUTION]
    > I dati di telemetria non sono retroattivi per gli eventi termici: devono essere abilitati durante il surriscaldamento o i dati necessari non verranno acquisiti.
    
    2. Riprodurre il problema di riscaldamento.
    3. Includere la data e l'ora in cui si è verificato il surriscaldamento.
    4. Inviare [commenti e suggerimenti.](hololens-feedback.md)

## <a name="see-also"></a>Vedi anche

- [Progettazione del mapping spaziale](/windows/mixed-reality/spatial-mapping)
- [Ologrammi](/windows/mixed-reality/hologram)
