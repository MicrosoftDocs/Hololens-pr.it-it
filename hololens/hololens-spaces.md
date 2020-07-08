---
title: Eseguire il mapping degli spazi fisici con HoloLens
description: HoloLens apprende come si presenta un ambiente nel corso del tempo. Gli utenti possono semplificare questo processo muovendo HoloLens nell’ambiente in modo specifico.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, progettazione, mapping spaziale, HoloLens, ricostruzione superficiale, mesh, tracciamento della testa, mapping
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 992b17160eb6ba6ca2f6c8b12e112b98ab154774
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829030"
---
# Eseguire il mapping degli spazi fisici con HoloLens

HoloLens integra gli ologrammi con lo spazio fisico dell’utente. A tale scopo, HoloLens deve imparare a conoscere lo spazio fisico intorno all’utente e ricordare dove vengono posizionati gli ologrammi all'interno dell’ambiente.

Nel corso del tempo, HoloLens crea una *mappa spaziale* dell'ambiente che ha visualizzato.  HoloLens aggiorna la mappa al modificarsi dell’ambiente. Fintanto che l’utente è connesso e il dispositivo è attivato, HoloLens crea e aggiorna le mappe spaziali. Se si usa o si indossa il dispositivo con le telecamere puntate verso uno spazio, HoloLens cercherà di eseguire il mapping dell'area. Anche se HoloLens impara a conoscere l’ambiente in modo naturale nel corso del tempo, è possibile facilitare la mappatura dello spazio in modo più rapido ed efficace.  

> [!NOTE]
> Se HoloLens non può eseguire il mapping dello spazio o non è stata eseguita la calibrazione, potrebbe entrare in modalità limitata. In questa modalità non sarà in grado di inserire gli ologrammi nell'ambiente circostante.

Questo articolo spiega in che modo HoloLens esegue il mapping dell’ambiente, come migliorare il mapping spaziale e come gestire i dati spaziali raccolti da HoloLens.

## Scelta e configurazione dello spazio

Le caratteristiche dell'ambiente possono rendere difficile la comprensione di uno spazio per HoloLens. I livelli luminosi, i materiali nell’ambiente, la forma degli oggetti e altro ancora, possono influire sul modo in cui HoloLens esegue il mapping di un'area.

HoloLens funziona meglio in particolari tipi di ambiente. Per produrre la mappa migliore dello spazio, scegliere una stanza luminosa e abbastanza spaziosa. Evitare gli spazi scuri e con grandi quantità di superfici scure, lucide o traslucide, ad esempio specchi o tende trasparenti.

HoloLens è ottimizzato per l’uso in spazi interni. Il mapping spaziale funziona meglio anche quando è attivata la rete Wi-Fi, anche se non è necessario che il dispositivo sia connesso a una rete. HoloLens può ottenere punti di accesso Wi-Fi anche se non è connesso o autenticato. La funzionalità di HoloLens non cambia se i punti di accesso sono connessi a Internet o solo alla Intranet o in locale.

Usare HoloLens solo in spazi sicuri senza il rischio di inciampare. [Altre informazioni sulla sicurezza](https://support.microsoft.com/help/4023454/safety-information).

## Mappatura dello spazio

Ora è possibile iniziare a eseguire il mapping degli spazi.  Quando HoloLens inizia il mapping dell'ambiente circostante, viene visualizzata una grafica mesh distribuita sullo spazio.  In ambiente iniziale, è possibile attivare la visualizzazione della mappa selezionando una superficie mappata.

Ecco le linee guida per la creazione di una mappa spaziale eccellente.

### Informazioni sugli scenari dell'area

È importante trascorrere la maggior parte del tempo nel luogo dove verrà usato il dispositivo HoloLens, in modo che la mappa sia pertinente e completa. Ad esempio, se uno scenario utente per HoloLens implica il movimento dal punto A al punto B, spostarsi lungo il percorso due o tre volte guardando in tutte le direzioni durante il movimento.  

### Camminare lentamente nell’ambiente

Se si cammina troppo velocemente, è probabile che il dispositivo HoloLens non riesca a eseguire il mapping dell’area. Camminare lentamente nello spazio, fermarsi ogni 1,5 - 2,5 m e guardarsi intorno.  

I movimenti fluidi consentono a HoloLens di eseguire il mapping in modo più efficace.

### Guardare in tutte le direzioni

Guardarsi intorno quando si esegue il mapping dello spazio, consente a HoloLens di acquisire maggiori informazioni sulla posizione di alcuni punti rispetto agli altri.  

Se non si guarda verso l’alto, ad esempio, HoloLens potrebbe non sapere dove si trova il soffitto della stanza.  

Assicurarsi di guardare il pavimento mentre si esegue il mapping dello spazio.

### Coprire le aree principali più volte

Muoversi attraverso un'area più volte aiuterà ad acquisire le caratteristiche perse nel primo passaggio. Per creare una mappa ideale, provare ad attraversare l’area due o tre volte.

Se possibile, durante la ripetizione dei movimenti, dedicare tempo a spostarsi nell’area prima in una direzione, poi tornare indietro sullo stesso percorso.

### Prendere tempo per eseguire il mapping dell’area

Può essere necessario tra 15 e 20 minuti perché HoloLens possa completare la mappatura e regolarsi sull'ambiente circostante. In un ambiente in cui si prevede di usare spesso il dispositivo HoloLens, dedicare del tempo per eseguire il mapping dello spazio consentirà di evitare problemi in un secondo momento.  

## Possibili errori nella mappa spaziale

Gli errori nei dati di mapping spaziale rientrano nelle categorie seguenti:

- *Buchi*: le superfici reali non sono presenti nei dati di mapping spaziale.
- *Allucinazioni*: le superfici esistono nei dati di mapping spaziale ma non esistono nel mondo reale.
- *Cunicoli spazio temporali*: HoloLens "perde" parti della mappa spaziale pensando che si trovino in un'altra parte della mappa rispetto alla realtà.
- *Deviazione*: le superfici nei dati di mapping spaziale sono allineate in modo non corretto alle superfici reali, anche se vengono spostate in avanti o indietro.

Se viene visualizzato uno di questi errori, usare il [FeedbackHub](hololens-feedback.md) per inviare il proprio feedback.

## Sicurezza e archiviazione dei dati spaziali

L'aggiornamento di Windows 10, versione 1803 per Microsoft HoloLens e versioni successive, consente di eseguire l’archiviazione dei dati di mapping in un database locale interno al dispositivo.

Gli utenti di HoloLens non possono accedere direttamente al database contenente i dati della mappa, neanche quando il dispositivo è collegato a un PC o quando si usa l'app Esplora file. Se BitLocker è abilitato in HoloLens, anche i dati della mappa archiviati vengono crittografati insieme all'intero volume.

### Rimuovere i dati della mappa e gli spazi noti da HoloLens

Sono disponibili due opzioni per l'eliminazione dei dati della mappa in **Impostazioni > Sistema > Ologrammi**:

- Per eliminare gli ologrammi nelle vicinanze, selezionare **Rimuovi ologrammi nelle vicinanze**. Il comando cancella i dati della mappa e gli ologrammi ancorati per lo spazio circostante. Se si continua a usare il dispositivo nello stesso spazio, verrà creata e archiviata una nuova sezione della mappa per sostituire le informazioni eliminate.

   > [!NOTE]
   > Gli ologrammi "nelle vicinanze" sono ologrammi ancorati all'interno della stessa sezione della mappa nello spazio circostante.

   Ad esempio, è possibile usare questa opzione per cancellare i dati della mappa correlati al lavoro senza influire sui dati della mappa correlati all'abitazione.

- Per eliminare tutti gli ologrammi nelle vicinanze, selezionare **Rimuovi tutti gli ologrammi**. Con questo comando vengono cancellati tutti i dati della mappa archiviati nel dispositivo, nonché tutti gli ologrammi ancorati. Sarà necessario posizionare esplicitamente gli ologrammi. Non sarà possibile trovare gli ologrammi precedentemente inseriti.

> [!NOTE]
> Dopo aver rimosso tutti gli ologrammi o quelli nelle vicinanze, HoloLens inizierà immediatamente ad analizzare e mappare lo spazio circostante.

### Dati Wi-Fi nelle mappe spaziali

HoloLens archivia le funzionalità della rete Wi-Fi per correlare le posizioni degli ologrammi e le sezioni della mappa archiviate nel database di HoloLens degli spazi noti. Le informazioni sulle funzionalità Wi-Fi non sono accessibili agli utenti e non vengono inviate a Microsoft usando il cloud o la telemetria.

Fintanto che è abilitata la rete Wi-Fi, HoloLens correla i dati della mappa ai punti di accesso Wi-Fi vicini. Non c'è alcuna differenza di comportamento nel caso in cui una rete è connessa o appena rilevata nelle vicinanze. Se la rete Wi-Fi è disabilitata, HoloLens continuerà a cercare lo spazio. Tuttavia, il dispositivo deve cercare numerosi dati della mappa all’interno del database degli spazi e potrebbe essere necessario più tempo per trovare gli ologrammi. Senza informazioni della rete Wi-Fi, HoloLens deve confrontare le analisi attive con tutti gli ologrammi ancorati e le sezioni mappa archiviati nel dispositivo per individuare la parte corretta della mappa.

## Argomenti correlati

- [Progettazione della mappatura spaziale](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping-design)
