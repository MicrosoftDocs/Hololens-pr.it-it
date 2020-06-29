---
title: Considerazioni sull'ambiente per HoloLens
description: Ottieni la migliore esperienza possibile utilizzando HoloLens quando ottimizzi il dispositivo per gli occhi e l'ambiente. Molti fattori ambientali diversi sono fusi insieme per consentire il rilevamento, ma in qualità di sviluppatore di realtà mista, sono diversi i fattori che puoi tenere presente per ottimizzare uno spazio in modo da ottenere ologrammi migliori.
keywords: fotogramma olografico, campo visivo, FOV, calibrazione, spazi, ambiente, procedure
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d2bec32e118ee1c9307b56fad99b7e8859e2a94d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828681"
---
# Considerazioni sull'ambiente per HoloLens

HoloLens unisce il mondo olografico a quello mondo reale, posizionando gli ologrammi nell'ambiente circostante. Una finestra dell'app olografica "si blocca" sul muro, una ballerina olografica gira sul tavolo, le orecchie da coniglio si siedono sulla testa del tuo amico a sua insaputa. Quando utilizzi un gioco o un'app immersiva, il mondo olografico si aprirà per riempire l'ambiente circostante, ma potrai comunque vedere e spostarti nello spazio.

Gli ologrammi che posizioni rimarranno dove li hai inseriti, anche se spegni il dispositivo.

## Configurazione di un ambiente

I dispositivi HoloLens sanno come posizionare ologrammi stabili e accurati mediante *rilevazione* degli utenti in uno spazio. Senza il rilevamento appropriato, il dispositivo non comprende l'ambiente o l'utente al suo interno, quindi gli ologrammi potrebbero apparire nelle posizioni sbagliate, non vengono visualizzati nello stesso punto ogni volta o non vengono visualizzati affatto. I dati utilizzati per il rilevamento degli utenti sono rappresentati nella *mappa spaziale*.  

Le prestazioni del rilevamento sono fortemente influenzate dall'ambiente in cui si trova l'utente e l'ottimizzazione di un ambiente per ottenere un rilevamento stabile e coerente è un'arte piuttosto che una scienza. Molti fattori ambientali diversi sono fusi insieme per consentire il rilevamento, ma in qualità di sviluppatore di realtà mista, sono diversi i fattori che puoi tenere presente per ottimizzare uno spazio per un migliore rilevamento.

### Illuminazione

Windows Mixed Reality utilizza la luce visiva per rilevare la posizione dell'utente. Quando un ambiente è troppo luminoso, le fotocamere possono essere saturate e non viene visualizzato nulla. Se l'ambiente è troppo scuro, le fotocamere non possono raccogliere informazioni sufficienti e non viene visualizzato nulla. L'illuminazione dovrebbe essere uniforme e sufficiente in modo tale che un essere umano possa vedere senza alcuno sforzo, ma non così brillante per cui la vista può essere disagevole.  

Anche le aree in cui sono presenti punti di luce in un'area nel complesso ombreggiata sono problematiche, perché la fotocamera deve essere regolata quando si sposta dentro e fuori spazi luminosi. Ciò può causare lo "smarrimento" del dispositivo che potrebbe scambiare una modifica dell'illuminazione in una modifica della posizione. I livelli di luce stabili in un'area consentiranno un migliore rilevamento.  

Qualsiasi illuminazione esterna può anche causare instabilità nel sensore, poiché il sole può variare notevolmente nel tempo. Ad esempio, il rilevamento nello stesso spazio in estate e in inverno può produrre risultati drasticamente diversi, perché la luce indiretta potrebbe essere più intensa in momenti diversi dell'anno.  

Se disponi di un luxmetro, un valore di 500-1000 lux costante è un buon punto di partenza.  

#### Tipi di illuminazione

Anche i diversi tipi di luce in uno spazio possono influenzare il rilevamento. Impulso delle lampadine con l'elettricità CA che le attraversa: se la frequenza CA è 50Hz, gli impulsi di luce sono da 50Hz. Per un essere umano, questi impulsi non vengono notati. Tuttavia, la fotocamera da 30 fps di HoloLens vede queste modifiche: alcuni fotogrammi saranno ben illuminati, alcuni saranno poco illuminati e alcuni saranno sovraesposti in quanto la fotocamera tenta di compensare gli impulsi di luce.  

Negli Stati Uniti, lo standard di frequenza di elettricità è 60hz, quindi gli impulsi della lampadina sono armonizzati con la frequenza di fotogrammi di HoloLens: 60hz si allinea con la frequenza di 30 fotogrammi FPS di HoloLens. Tuttavia, molti paesi hanno uno standard di frequenza CA di 50hz, il che significa che alcuni fotogrammi HoloLens verranno acquisiti durante gli impulsi e altri no. In particolare, l'illuminazione fluorescente in Europa è nota per causare problemi.  

Esistono alcune operazioni che puoi provare per risolvere i problemi di sfarfallio. La temperatura, l'età della lampadina e i cicli di riscaldamento sono cause comuni di sfarfallio fluorescente e la sostituzione delle lampadine può essere utile. Anche le operazioni per serrare bene le lampadine e verificare che la corrente sia sempre costante possono essere di aiuto.  

### Elementi in uno spazio

HoloLens utilizza punti di riferimento ambientali univoci, noti anche come *funzionalità* per individuarsi all'interno di uno spazio.  

Un dispositivo non può quasi mai eseguire il rilevamento in un'area povera di funzionalità, perché il dispositivo non ha modo di sapere dove si trova nello spazio. L'aggiunta di funzionalità alle pareti di uno spazio è in genere un buon modo per migliorare il rilevamento. I poster, i simboli attaccati su una parete, le piante, oggetti univoci o altri elementi simili possono aiutare allo stesso modo. Una scrivania disordinata è un buon esempio di un ambiente che comporta un rilevamento, in quanto sono disponibili numerose funzionalità diverse all'interno di un'unica area.  

Inoltre, utilizza funzionalità univoche nello stesso spazio. Lo stesso poster ripetuto più volte su una parete, ad esempio, causerà confusione per i dispositivi perché HoloLens non saprà quale dei manifesti ripetuti sta esaminando. Un modo comune per aggiungere funzionalità univoche consiste nell'usare righe di nastro adesivo per creare modelli univoci e non ripetitivi lungo le pareti e il pavimento di uno spazio.  

Una buona domanda da porsi è: se hai visto solo una piccola parte della scena, saresti in grado di individuarti in modo univoco nello spazio? In caso contrario, è probabile che il dispositivo possa avere anche problemi di rilevamento.

#### Buchi neri

Se hai due aree o regioni identiche che sembrano coincidere, il tracciatore potrebbe pensare che siano uguali. In questo modo il dispositivo è indotto a pensare di trovarsi altrove. Questi tipi di aree ripetitive vengono chiamati *buchi neri*.  

Per impedire il verificarsi di buchi neri, prova a impedire la presenza di aree identiche nello stesso spazio. Le aree identiche possono talvolta includere stazioni di fabbrica, finestre su un edificio, server rack o stazioni di lavoro. Le aree di etichettatura o l'aggiunta di funzionalità univoche a ciascuna area di aspetto simile consentono di attenuare i buchi neri.

### Movimento in uno spazio

Se l'ambiente viene costantemente spostato e modificato, il dispositivo non dispone di funzionalità stabili da individuare.  

Più oggetti in movimento si trovano in uno spazio, tra cui le persone, più facile è perdere il rilevamento. Nastri trasportatori che si muovono, elementi in diversi stati di costruzione e molte persone in uno spazio sono fattori che notoriamente causano problemi di rilevamento.

HoloLens può adattarsi rapidamente a queste modifiche, ma solo quando l'area è chiaramente visibile per il dispositivo. Le aree che non vengono viste abbastanza frequentemente possono rientrare in ritardo rispetto alla realtà causando errori nella mappa spaziale. Ad esempio, un utente esegue la scansione di un amico e quindi si gira mentre l'amico lascia la stanza. Una rappresentazione 'fantasma' dell'amico resterà nei dati di mapping spaziale finché l'utente non esegue nuovamente l'analisi dello spazio vuoto.

### Vicinanza dell'utente agli elementi nello spazio

In modo analogo a come gli esseri umani non possono mettere a fuoco bene gli oggetti vicino agli occhi, HoloLens incontra difficoltà quando gli oggetti sono troppo vicini alle fotocamere. Se un oggetto è troppo vicino per essere visualizzato con entrambe le fotocamere o se un oggetto sta bloccando una fotocamera, il dispositivo avrà molti più problemi con il rilevamento dell'oggetto.  

Le fotocamere non possono vedere più vicino di 15 cm da un oggetto.

### Superfici in uno spazio

Le superfici fortemente riflettenti avranno probabilmente un aspetto diverso a seconda dell'angolo, che influisce sul rilevamento. Pensa a una nuova auto: quando ti sposti al suo interno, la luce riflette e vedrai diversi oggetti in superficie mentre ti sposti. Per il tracciatore, i diversi oggetti riflessi su una superficie rappresentano un ambiente in evoluzione e il dispositivo perde il rilevamento.

Gli oggetti meno lucidi sono più facili da rilevare.

### Considerazioni sull'impronta digitale Wi-Fi

Se è abilitata la connessione Wi-Fi, i dati della mappa saranno correlati con un'impronta digitale Wi-Fi, anche quando non sono connessi a una rete/router WiFi effettiva. Senza info sul Wi-Fi, lo spazio e gli ologrammi potrebbero essere leggermente più lenti da riconoscere. Se i segnali Wi-Fi cambiano in modo significativo, il dispositivo potrebbe pensare di trovarsi in uno spazio completamente diverso.

L'identificazione della rete (ad esempio SSID o indirizzo MAC) non viene inviata a Microsoft e tutti i riferimenti al Wi-Fi vengono mantenuti in locale su HoloLens.

## Mapping di nuovi spazi

Quando immetti un nuovo spazio (o ne carichi uno esistente), vedrai una grafica mesh distribuita nello spazio. Questo significa che il tuo dispositivo sta mappando l'ambiente circostante. Sebbene un dispositivo HoloLens sia in grado di registrare uno spazio nel tempo, esistono alcuni suggerimenti e trucchi per la mappatura degli spazi.

## Gestione dell'ambiente

Esistono due impostazioni che consentono agli utenti di "pulire" gli ologrammi e fare in modo che HoloLens "dimentichi" uno spazio. Si trovano in **Ologrammi e ambienti** nell'app Impostazioni, con la seconda impostazione visualizzata anche in **Privacy** nell'app Impostazioni.  

1. **Eliminare ologrammi nelle vicinanze**. Quando selezioni questa impostazione, HoloLens cancellerà tutti gli ologrammi ancorati e tutti i dati della mappa archiviati per lo "spazio corrente" in cui si trova il dispositivo. Una nuova sezione della mappa verrebbe creata e archiviata nel database per tale posizione dopo che gli ologrammi sono stati nuovamente posizionati nello stesso spazio.

1. **Elimina tutti gli ologrammi**. Selezionando questa impostazione, HoloLens cancellerà TUTTI i dati delle mappe e gli ologrammi ancorati nell'intero database di spazi. Gli ologrammi non verranno individuati nuovamente e tutti gli ologrammi devono essere riposizionati per archiviare nuovamente sezioni della mappa nel database.

## Qualità dell'ologramma

Gli ologrammi possono essere posizionati in tutto l'ambiente, in alto, in basso e intorno a te, ma li vedrai attraverso un [fotogramma olografico](https://docs.microsoft.com/windows/mixed-reality/holographic-frame) che si trova davanti agli occhi. Per ottenere la visualizzazione ottimale, assicurati di regolare il dispositivo in modo da poter vedere l'intero fotogramma. E non esitare a esplorare l'ambiente circostante.

Per fare in modo che gli [ologrammi](https://docs.microsoft.com/windows/mixed-reality/hologram) appaiono nitidi, chiari e stabili, HoloLens deve essere calibrato solo per te. Quando configuri per la prima volta HoloLens, verrai guidato attraverso questo processo. In seguito, se gli ologrammi non hanno un aspetto corretto o se si verificano molti errori, puoi apportare modifiche.

Se si verificano problemi di mapping degli spazi, prova a eliminare gli ologrammi nelle vicinanze e a rimappare lo spazio.

### Calibrazione

Se gli ologrammi presentano un tremolio o si verificano problemi con il posizionamento degli stessi, la prima cosa da provare è l'[app Calibrazione](hololens-calibration.md). Questa app può anche essere utile se provi disagio durante l'uso di HoloLens.

Per accedere all'app Calibrazione, vai a **Impostazioni** > **Sistema** > **Utilità**. Seleziona **Apri calibrazione** e segui le istruzioni.

Se qualcun altro sta usando il tuo dispositivo HoloLens, dovrebbe prima eseguire l'app Calibrazione in modo che il dispositivo sia configurato correttamente.

## Vedi anche

- [Progettazione della mappatura spaziale](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
- [Ologrammi](https://docs.microsoft.com/windows/mixed-reality/hologram)
