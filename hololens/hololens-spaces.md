---
title: Eseguire il mapping di spazi fisici con HoloLens
description: HoloLens apprende l'aspetto di uno spazio nel tempo. Gli utenti possono semplificare questo processo spostando il HoloLens in determinati modi nello spazio.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, progettazione, mapping spaziale, HoloLens, ricostruzione della superficie, mesh, tracciamento della testa, mapping
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036167"
---
# <a name="map-physical-spaces-with-hololens"></a>Eseguire il mapping di spazi fisici con HoloLens

HoloLens combina ologrammi con il mondo fisico. A tale scopo, HoloLens conoscere il mondo fisico intorno all'utente e ricordare dove posizionare gli ologrammi all'interno di tale spazio.

Nel corso del tempo, HoloLens crea una *mappa* spaziale dell'ambiente che ha visto.  HoloLens aggiorna la mappa quando cambia l'ambiente. Fino a quando si è connessi e il dispositivo è acceso, HoloLens e aggiorna le mappe spaziali. Se si tiene premuto o si usura il dispositivo con le fotocamere puntate a uno spazio, il HoloLens tenta di mappare l'area. Anche se HoloLens apprende uno spazio in modo naturale nel tempo, esistono modi in cui è possibile HoloLens mappare lo spazio in modo più rapido ed efficiente.  

> [!NOTE]
> Se il HoloLens non è in grado di eseguire il mapping dello spazio o non è in grado di eseguire la calibrazione, HoloLens potrebbe essere attivata la modalità Limitata. In modalità Limitata non sarà possibile posizionare gli ologrammi nell'ambiente circostante.

Questo articolo illustra come HoloLens mappe, come migliorare il mapping spaziale e come gestire i dati spaziali raccolti HoloLens dati.

## <a name="choosing-and-setting-up-and-your-space"></a>Scelta e configurazione e spazio

Le funzionalità nell'ambiente in uso possono rendere difficile l'HoloLens interpretare uno spazio. I livelli di luce, i materiali nello spazio, il layout degli oggetti e altro ancora possono influire sul modo in cui HoloLens mappa un'area.

HoloLens funziona meglio in determinati tipi di ambienti. Per produrre la mappa spaziale migliore, scegliere una stanza con luce e spazio adeguato. Evitare spazi scuri e stanze con molte superfici scuri, lride o traslucide(ad esempio, mirror o stinchi di gauzia).

HoloLens è ottimizzato per l'uso in interni. Il mapping spaziale funziona meglio anche quando Wi-Fi è attivato, anche se non è necessario che sia connesso a una rete. HoloLens possibile ottenere Wi-Fi punti di accesso anche se non è connesso o autenticato. HoloLens funzionalità non cambia se i punti di accesso sono connessi a Internet o solo intranet/locale.

Usare i HoloLens in luoghi sicuri senza rischi di inciampo. [Altre informazioni sulla sicurezza.](https://support.microsoft.com/help/4023454/safety-information)

## <a name="mapping-your-space"></a>Mapping dello spazio

A questo punto è possibile iniziare a eseguire il mapping della riserva.  Quando HoloLens inizia a eseguire il mapping dell'ambiente circostante, verrà visualizzata un'immagine a mesh che si estende nello spazio.  In ambiente iniziale è possibile attivare la mappa da visualizzare selezionando una superficie mappata.

Di seguito sono riportate le linee guida per la creazione di una mappa spaziale ideale.

### <a name="understand-the-scenarios-for-the-area"></a>Comprendere gli scenari per l'area

È importante dedicare la maggior parte del tempo all'uso del HoloLens, in modo che la mappa sia pertinente e completa. Ad esempio, se uno scenario utente per HoloLens comporta il passaggio dal punto A al punto B, seguire il percorso da due a tre volte, esaminando tutte le direzioni mentre ci si sposta.  

### <a name="walk-slowly-around-the-space"></a>Spostarsi lentamente nello spazio

Se si aggira troppo rapidamente l'area, è probabile che il HoloLens le aree di mapping. Spostarsi lentamente intorno allo spazio, fermandosi ogni 5-8 piedi per guardare l'ambiente circostante.  

I movimenti uniformi consentono anche di HoloLens mappa in modo più efficiente.

### <a name="look-in-all-directions"></a>Cerca in tutte le direzioni

Se si guarda intorno mentre si esegue il mapping dello spazio, HoloLens più dati sulla posizione in cui i punti sono relativi tra loro.  

Se non si cerca, ad esempio, il HoloLens potrebbe non sapere dove si trova il controsoffitto in una stanza.  

Non dimenticare di guardare il piano mentre si esegue il mapping dello spazio.

### <a name="cover-key-areas-multiple-times"></a>Coprire più volte le aree chiave

Spostarsi più volte in un'area consente di selezionare le funzionalità che potrebbero non essere state perse nella prima procedura dettagliata. Per creare una mappa ideale, provare ad attraversare un'area da due a tre volte.

Se possibile, durante la ripetizione di questi movimenti, dedicare tempo a spostarsi in un'area in una direzione, quindi spostarsi e tornare indietro nel modo in cui si è arrivati.

### <a name="take-your-time-mapping-the-area"></a>Eseguire il mapping dell'area nel tempo

La mappa completa del HoloLens può richiedere da 15 a 20 minuti e adattarsi all'ambiente circostante. Se si dispone di uno spazio in cui si prevede di usare spesso un HoloLens, il tempo necessario per eseguire il mapping dello spazio può impedire problemi in un secondo momento.  

## <a name="possible-errors-in-the-spatial-map"></a>Possibili errori nella mappa spaziale

Gli errori nei dati di mapping spaziale rientrano in alcune categorie:

- *Fori:* le superfici reali non sono presenti nei dati di mapping spaziale.
- *Allucinazioni:* le superfici esistono nei dati di mapping spaziale che non esistono nel mondo reale.
- *Worm tunnel:* HoloLens 'perde' parte della mappa spaziale, pensando che si trova in una parte diversa della mappa rispetto a quella effettivamente presente.
- *Distorsione:* le superfici nei dati di mapping spaziale sono perfettamente allineate alle superfici del mondo reale, sia all'esterno che all'esterno.

Se viene visualizzato uno di questi errori, usare [FeedbackHub](hololens-feedback.md) per inviare commenti e suggerimenti.

## <a name="security-and-storage-for-spatial-data"></a>Sicurezza e archiviazione per i dati spaziali

Windows 10 versione 1803 per Microsoft HoloLens e versioni successive archivia i dati di mapping in un database locale (su dispositivo).

HoloLens gli utenti non possono accedere direttamente al database delle mappe, anche quando il dispositivo è collegato a un PC o quando si usa l Esplora file app. Quando BitLocker è abilitato in HoloLens, anche i dati mappa archiviati vengono crittografati insieme all'intero volume.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Rimuovere i dati della mappa e gli spazi noti HoloLens

Sono disponibili due opzioni per l'eliminazione dei dati della **mappa in Impostazioni > sistema > Ologrammi**:

- Per eliminare gli ologrammi vicini, selezionare **Rimuovi ologrammi vicini.** Questo comando cancella i dati della mappa e gli ologrammi ancorati per lo spazio corrente. Se si continua a usare il dispositivo nello stesso spazio, viene creata e archiviata una sezione mappa completamente nuova per sostituire le informazioni eliminate.

   > [!NOTE]
   > Gli ologrammi "vicini" sono ologrammi ancorati nella stessa sezione della mappa nello spazio corrente.

   Ad esempio, è possibile usare questa opzione per cancellare i dati della mappa correlati al lavoro senza influire sui dati della mappa relativi alla casa.

- Per eliminare tutti gli ologrammi, selezionare **Rimuovi tutti gli ologrammi**. Questo comando cancella tutti i dati della mappa archiviati nel dispositivo e tutti gli ologrammi ancorati. Sarà necessario inserire in modo esplicito gli ologrammi. Non sarà possibile riscoprire gli ologrammi inseriti in precedenza.

> [!NOTE]
> Dopo aver rimosso tutti gli ologrammi vicini o tutti, HoloLens immediatamente l'analisi e il mapping dello spazio corrente.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi dati nelle mappe spaziali

HoloLens archivia Wi-Fi caratteristiche che consentono di correlare le posizioni degli ologrammi e le sezioni della mappa archiviate all'interno del database HoloLens di spazi noti. Le informazioni sulle Wi-Fi non sono accessibili agli utenti e non vengono inviate a Microsoft usando il cloud o i dati di telemetria.

Se l'Wi-Fi è abilitata, HoloLens correla i dati della mappa con i punti di accesso Wi-Fi vicini. Non esiste alcuna differenza nel comportamento indipendentemente dal fatto che una rete sia connessa o appena rilevata nelle vicinanze. Se Wi-Fi è disabilitata, HoloLens continua a cercare nello spazio. Tuttavia, HoloLens deve cercare più dati della mappa all'interno del database degli spazi e potrebbe essere necessario più tempo per trovare gli ologrammi. Senza le informazioni Wi-Fi, il HoloLens deve confrontare le analisi attive con tutti gli ancoraggi ologrammi e le sezioni della mappa archiviate nel dispositivo per individuare la parte corretta della mappa.

## <a name="related-topics"></a>Argomenti correlati

- [Progettazione del mapping spaziale](/windows/mixed-reality/spatial-mapping)
