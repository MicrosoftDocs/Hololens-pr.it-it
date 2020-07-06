---
title: Uso del visualizzatore 3D in HoloLens (prima generazione)
description: L’articolo descrive i tipi di file e le funzionalità supportate dal visualizzatore 3D in HoloLens (prima generazione) e spiega come usare l'app e risolvere eventuali problemi.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 47fe1fd5dc164c56ce22a09d7edf5bffdb60ea14
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828890"
---
# Uso del visualizzatore 3D in HoloLens (prima generazione)

Il visualizzatore 3D consente di visualizzare i modelli 3D in HoloLens (prima generazione). È possibile aprire e visualizzare i file in formato FBX *supportati* da Microsoft Edge, OneDrive e altre app.

>[!NOTE]
>Questo articolo si applica all'app immersiva Unity **Visualizzatore 3D** che supporta file FBX ed è disponibile solo in HoloLens (prima generazione). La versione preinstallata del **visualizzatore 3D** in HoloLens 2 supporta l'apertura di modelli 3D in formato GLB personalizzati in ambiente iniziale. Per altre informazioni, vedere [Panoramica dei requisiti delle risorse](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview).

Se si verificano problemi durante l'apertura di un modello 3D in un visualizzatore 3D o se alcune funzionalità del modello non sono supportate, vedere [Specifiche dei contenuti supportati](#supported-content-specifications).

Per creare od ottimizzare i modelli 3D da usare con il visualizzatore 3D, vedere [Ottimizzazione dei modelli 3D per il visualizzatore 3D](#optimizing-3d-models-for-3d-viewer).

Esistono due modalità di apertura di un modello 3D in HoloLens. Per altre informazioni, vedere [Visualizzare i file in formato FBX in HoloLens](#viewing-fbx-files-on-hololens).

In caso di problemi durante la lettura di questi argomenti, vedere [Risoluzione dei problemi](#troubleshooting).

## Specifiche dei contenuti supportati

### Formato file

- Formato FBX
- Versione massima FBX: 2015.1.0

### Dimensione file

- Minima: 5 GB
- Massima: 500 MB

### Geometria

- Solo modelli poligonali. Nessuna suddivisione delle superfici o NURB
- Sistema di coordinate destrorso
- La distorsione delle matrici di trasformazione non è supportata

### Trame

- Il mapping delle trame deve essere incorporato nel file FBX
- Formati immagine supportati
  - Immagini JPEG e PNG
  - Immagini BMP (16,8 milioni di colori RGB 24 bit)
  - Immagini TGA (16,8 milioni di colori RGB 24 bit e RGBQ 32 bit)
- Risoluzione massima della trama: 2048x2048
- Massimo un mapping diffuso, un mapping normale e un mapping cubo di riflessione per mesh
- Il canale alfa nelle trame diffuse causa il rigetto dei pixel se inferiori al 50%

### Animazione

- Ridimensionamento/rotazione/traslazione delle animazioni su singoli oggetti
- Animazione scheletrica (ossa) con l’uso delle interfacce
  - Massimo 4 influenze per vertice

### Materiali

- I materiali Lambert e Phong sono supportati con parametri variabili
- Proprietà dei materiali supportati per Lambert
  - Trama principale (RGB + test Alpha)
  - Colore diffuso (RGB)
  - Colore ambientale (RGB)
- Proprietà dei materiali supportati per Phong
  - Trama principale (RGB + test Alpha)
  - Colore diffuso (RGB)
  - Colore ambientale (RGB)
  - Colore speculare (RGB)
  - Lucentezza
  - Riflettività
- I materiali personalizzati non sono supportati
- Massimo un materiale per mesh
- Massimo un livello di materiale
- Massimo 8 materiali per file

### Limitazioni per file e modelli

Esistono limiti rigidi per le dimensioni dei file, il numero di modelli, vertici e mesh che possono essere aperti contemporaneamente nel visualizzatore 3D:

- Dimensione massima dei file per modello: 500 MB
- Vertici: 600.000 combinati in tutti i modelli aperti
- Mesh: 1.600 combinati in tutti i modelli aperti
- Numero massimo di modelli aperti contemporaneamente: 40

## Ottimizzazione dei modelli 3D per il visualizzatore 3D

### Considerazioni particolari

- Evitare materiali di colore nero o aree nere nel mapping delle trame. Gli ologrammi sono fatti di luce, perciò HoloLens esegue il rendering del colore nero (assenza di luce) come trasparente.
- Prima di esportare in formato FBX dallo strumento di creazione, assicurarsi che la geometria sia visibile e non bloccata e che nessun livello contenente geometria sia disattivato o basato su modelli. Visibilità non rispettata.
- Evitare offset di traslazione molto grandi tra i nodi, ad esempio 100.000 unità. Ciò può causare l’instabilità del modello durante lo spostamento/ridimensionamento/rotazione.

### Ottimizzazione delle prestazioni

Tenere presenti le prestazioni durante la creazione dei contenuti e convalidarle nell'app Visualizzatore 3D su HoloLens per ottenere risultati ottimali. Il visualizzatore 3D esegue il rendering dei contenuti in tempo reale e le prestazioni dipendono dalle funzionalità hardware di HoloLens.  

Molte variabile possono influire sulle prestazioni di un modello 3D. Il visualizzatore 3D mostrerà un messaggio di avviso durante il caricamento se sono presenti più di 150.000 vertici o di 400 mesh. Le animazioni possono influire sulle prestazioni di altri modelli aperti. Inoltre, esistono limiti rigidi per il numero totale di modelli, vertici e mesh che possono essere aperti contemporaneamente nel visualizzatore 3D, vedere [Limitazioni per file e modelli](#file-and-model-limitations).  

Se il modello 3D non viene eseguito correttamente a causa della complessità del modello, prendere in considerazione:

- Riduzione del numero di poligoni
- Riduzione del numero di ossa nelle animazioni
- Evitare auto occlusione

Il rendering su due lati è supportato nel visualizzatore 3D, anche se per motivi di prestazioni è disattivato per impostazione predefinita. Questa opzione può essere attivata tramite il pulsante **Fronte retro** nella pagina **Dettagli**. Per ottenere prestazioni ottimali, evitare il rendering su due lati nei contenuti.

### Convalida del modello 3D

Convalidare il modello aprendolo nel visualizzatore 3D su HoloLens. Selezionare il pulsante **Dettagli** per visualizzare le funzionalità del modello e i messaggi di avviso per i contenuti non supportato, se presenti.

### Rendering di modelli 3D con dimensioni reali

Per impostazione predefinita, il visualizzatore 3D mostra i modelli 3D con una dimensione e una posizione comode in rapporto all'utente. Tuttavia, se il rendering di un modello 3D con misure reali è importante, ad esempio quando si esaminano modelli di mobili per una stanza, l'autore del contenuto può inserire un contrassegnare nei metadati del file per impedire che l’applicazione o l’utente possano ridimensionare il modello.

Per impedire il ridimensionamento del modello, aggiungere un attributo personalizzato booleano a tutti gli oggetti nella scena denominata Microsoft_DisableScale e impostarlo come vero. Il visualizzatore 3D rispetterà le informazioni di FbxSystemUnit contenute nel file FBX. Il ridimensionamento nel visualizzatore 3D è 1 m per unità FBX.

## Visualizzare i file FBX in HoloLens

### Aprire un file di FBX in Microsoft Edge

I file FBX possono essere aperti direttamente da un sito Web tramite Microsoft Edge in HoloLens.

1. In Microsoft Edge, passare alla pagina Web che contiene il file FBX che si vuole visualizzare.
1. Selezionare il file per scaricarlo.
1. Una volta completato il download, selezionare il pulsante **Apri** in Microsoft Edge per aprire il file nel visualizzatore 3D.

È possibile accedere e aprire nuovamente il file scaricato in un secondo momento usando l’opzione Download in Microsoft Edge. Per salvare un modello 3D e garantirne l'accesso continuato, scaricare il file nel PC e salvarlo nell'account di OneDrive. Il file può essere aperto dall'app OneDrive in HoloLens.

> [!NOTE]
> Alcuni siti Web con modelli FBX scaricabili, li forniscono in formato ZIP compresso. Il visualizzatore 3D non può aprire direttamente i file ZIP. In alternativa, usare il PC per estrarre i file FBX e salvarli nell'account di OneDrive. Il file può essere aperto dall'app OneDrive in HoloLens.

### Aprire un file FBX in OneDrive

È possibile aprire i file FBX in OneDrive usando l'app OneDrive in HoloLens. Assicurarsi di aver installato OneDrive tramite l'app Microsoft Store in HoloLens e di aver già caricato il file FBX in OneDrive nel PC.

In OneDrive è possibile aprire i file FBX in HoloLens usando il visualizzatore 3D in due modi:

- Avviare OneDrive in HoloLens e selezionare il file FBX per aprirlo nel visualizzatore 3D.
- Avviare il visualizzatore 3D, simulare il tocco per visualizzare la barra degli strumenti e selezionare **Apri file**. Verrà avviato OneDrive, che consentirà di selezionare un file FBX.

## Risoluzione dei problemi

### Visualizzo un avviso quando apro un modello 3D

Viene visualizzato un messaggio di avviso quando si prova ad aprire un modello 3D che contiene funzionalità non supportate dal visualizzatore 3D o se il modello è troppo complesso e ciò potrebbe influire sulle prestazioni. Il visualizzatore 3D caricherà comunque il modello 3D, ma le prestazioni o la fedeltà visiva potrebbero essere compromesse.

Per altre informazioni, vedere [Specifiche dei contenuti supportati](#supported-content-specifications) e [Ottimizzazione dei modelli 3D per il visualizzatore 3D](#optimizing-3d-models-for-3d-viewer).

### Visualizzo un avviso e il modello 3D non viene caricato

Viene visualizzato un messaggio di errore quando il visualizzatore 3D non può caricare un modello 3D a causa della complessità o delle dimensioni del file oppure se il file FBX è danneggiato o non valido. Viene visualizzato un messaggio di errore anche se è stato raggiunto il limite del numero totale di modelli, vertici o mesh che è possibile aprire contemporaneamente.  

Per altre informazioni, vedere [Specifiche dei contenuti supportati](#supported-content-specifications) e [Limitazioni per file e modelli](#file-and-model-limitations).

Se si ritiene che il modello soddisfi le specifiche dei contenuti supportati e che non siano stati superati i limiti dei file o modelli, è possibile inviare il file FBX al team del visualizzatore 3D all’indirizzo holoapps@microsoft.com. Non siamo in grado di rispondere ai singoli messaggi, ma ricevere gli esempi di file che non vengono caricati correttamente aiuterà il team a migliorare le versioni future dell'app.

### Il modello 3D viene caricato ma non viene visualizzato come previsto

Se il modello 3D non ha l’aspetto previsto nel visualizzatore 3D, simulare il tocco per visualizzare la barra degli strumenti, poi selezionare **Dettagli**. Gli elementi dei file non supportati dal visualizzatore 3D verranno evidenziate con messaggi di avviso.

I problemi più comuni che potrebbero verificarsi riguardano le trame mancanti, probabilmente perché non sono incorporate nel file FBX. In questo caso, il modello apparirà bianco. Questo problema può essere risolto nel processo di creazione esportando dallo strumento di creazione in formato FBX e selezionando l'opzione di incorporazione della trama.

Per altre informazioni, vedere [Specifiche dei contenuti supportati](#supported-content-specifications) e [Ottimizzazione dei modelli 3D per il visualizzatore 3D](#optimizing-3d-models-for-3d-viewer).

### Durante la visualizzazione di un modello 3D, si verifica una diminuzione delle prestazioni

Durante il caricamento e la visualizzazione di un modello 3D, le prestazioni possono essere interessate dalla complessità del modello, dal numero di modelli aperti contemporaneamente o dal numero di modelli con animazioni attive.

Per altre informazioni, vedere [Ottimizzazione dei modelli 3D per il visualizzatore 3D](#optimizing-3d-models-for-3d-viewer) e [Limitazioni per file e modelli](#file-and-model-limitations).

### Quando apro un file FBX in HoloLens, non si apre in visualizzatore 3D

Il visualizzatore 3D viene associato automaticamente ai file con estensione FBX al momento dell'installazione.

Se si prova ad aprire un file FBX e viene visualizzata una finestra di dialogo che indirizza a Microsoft Store significa che non si ha al momento un'app associata ai file con estensione FBX in HoloLens.

Verificare che il visualizzatore 3D sia installato. Se non è installato, scaricarlo da Microsoft Store in HoloLens.

Se il visualizzatore 3D è già installato, avviarlo e poi riprovare ad aprire il file. Se il problema persiste, disinstallare e reinstallare il visualizzatore 3D. Questa operazione consentirà di associare nuovamente i file con estensione FBX al visualizzatore 3D.

Se si prova ad aprire un file FBX e viene aperta un'app diversa dal visualizzatore 3D, è probabile che l'app sia stata installata dopo il visualizzatore 3D e abbia rilevato l'associazione con l'estensione di file FBX. Se si preferisce che il visualizzatore 3D sia associato all'estensione di file FBX, disinstallare l’app e installarla nuovamente.

### Il pulsante Apri file in visualizzatore 3D non avvia l'app

Il pulsante **Apri file** aprirà l'app associata alla funzione di selezione dei file in HoloLens. Se è installato OneDrive, il pulsante **Apri file** dovrebbe avviare OneDrive. Tuttavia, se al momento non è associata alcuna app alla funzione di selezione dei file installata in HoloLens, si verrà reindirizzati a Microsoft Store.

Se il pulsante **Apri file** avvia un'app diversa da OneDrive, è probabile che l'app sia stata installata dopo OneDrive e ha rilevato l'associazione con la funzione di selezione file. Se si preferisce l’avvio di OneDrive quando si seleziona il pulsante **Apri file** nel visualizzatore 3D, disinstallare e reinstallare OneDrive.

Se il pulsante **Apri file** non è attivo, è possibile che sia stato raggiunto il limite di modelli che è possibile aprire contemporaneamente in un visualizzatore 3D. Se si hanno 40 modelli aperti in visualizzatore 3D, è necessario chiuderli alcuni prima di riuscire ad aprire altri modelli.

## Risorse aggiuntive

- [Forum del supporto tecnico](http://forums.hololens.com/categories/3d-viewer-beta)
- [Avvisi di terze parti](https://www.microsoft.com/{lang-locale}/legal/products)
