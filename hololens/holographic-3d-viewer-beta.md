---
title: Uso Visualizzatore 3D Beta in HoloLens (prima generazione)
description: Descrive i tipi di file e le funzionalità supportati Visualizzatore 3D Beta in HoloLens (prima generazione) e come usare e risolvere i problemi dell'app.
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
ms.openlocfilehash: d25a87bd210535e36e18f165b5461141c40aa292a07c560018ba7c0cbf76f6ba
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664928"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Uso Visualizzatore 3D Beta in HoloLens (prima generazione)

Visualizzatore 3D Beta consente di visualizzare i modelli 3D HoloLens (prima generazione). È possibile aprire e visualizzare *i file* con estensione fbx supportati Microsoft Edge, OneDrive e altre app.

>[!NOTE]
>Questo articolo si applica all'app immersive Unity **Visualizzatore 3D Beta,** che supporta i file con estensione fbx ed è disponibile solo in HoloLens (prima generazione). L'app  Visualizzatore 3D preinstallata in HoloLens 2 supporta l'apertura di modelli 3D con estensione glb personalizzati nel ambiente iniziale.Per altri dettagli, vedere Panoramica dei requisiti degli asset. [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)

>[!IMPORTANT]
>Anche Visualizzatore 3D Beta può rimanere disponibile nel Microsoft Store per HoloLens (prima generazione), non è più in fase di sviluppo attivo e non è più supportato.

Se si verificano problemi durante l'apertura di un modello 3D in Visualizzatore 3D Beta o se alcune funzionalità del modello 3D non sono supportate, vedere Specifiche di contenuto [supportate](#supported-content-specifications) più avanti.

Per compilare o ottimizzare modelli 3D da usare con Visualizzatore 3D Beta, vedere [Ottimizzazione dei modelli 3D Visualizzatore 3D Beta più](#optimizing-3d-models-for-3d-viewer-beta) avanti.

Esistono due modi per aprire un modello 3D in HoloLens. Per altre informazioni, vedere Visualizzazione di file [FBX HoloLens](#viewing-fbx-files-on-hololens) di seguito.

Se si verificano problemi dopo aver letto questi argomenti, vedere Risoluzione [dei problemi di](#troubleshooting) seguito.

## <a name="supported-content-specifications"></a>Specifiche di contenuto supportate

### <a name="file-format"></a>Formato file

- Formato FBX
- Versione massima di FBX 2015.1.0

### <a name="file-size"></a>Dimensione del file

- Minimo 5 KB
- Massimo 500 MB

### <a name="geometry"></a>Geometria

- Solo modelli poligonali. Nessuna superficie di suddivisione o NURB
- Sistema di coordinate destro
- La proiezione nelle matrici di trasformazione non è supportata

### <a name="textures"></a>Trame

- Le mappe di trama devono essere incorporate nel file FBX
- Formati di immagine supportati
  - Immagini JPEG e PNG
  - Immagini BMP (vero colore RGB a 24 bit)
  - Immagini TGA (RGB a 24 bit e RGBQ a 32 bit true-color)
- Risoluzione massima della trama di 2048x2048
- Al massimo una mappa diffusa, una mappa normale e una mappa cubo di reflection per mesh
- Il canale alfa nelle trame diffuse causa la eliminazione dei pixel se inferiore al 50%

### <a name="animation"></a>Animazione

- Animazione di ridimensionamento,rotazione/traslazione su singoli oggetti
- Animazione scheletrico (con interfaccia) con interfaccia
  - Massimo 4 fattori per vertice

### <a name="materials"></a>Materiali

- Sono supportati i materiali Lambert e Phong, con parametri regolabili
- Proprietà dei materiali supportate per Lambert
  - Trama principale (test RGB + alfa)
  - Colore diffuso (RGB)
  - Colore ambiente (RGB)
- Proprietà dei materiali supportate per Phong
  - Trama principale (test RGB + alfa)
  - Colore diffuso (RGB)
  - Colore ambiente (RGB)
  - Colore speculare (RGB)
  - Luminosità
  - Riflettività
- I materiali personalizzati non sono supportati
- Massimo un materiale per mesh
- Massimo un livello materiale
- Massimo 8 materiali per file

### <a name="file-and-model-limitations"></a>Limitazioni di file e modelli

Esistono limiti rigidi per le dimensioni dei file, nonché per il numero di modelli, vertici e mesh che possono essere aperti contemporaneamente in Visualizzatore 3D Beta:

- Dimensioni massime del file di 500 MB per modello
- Vertici: 600.000 combinati in tutti i modelli aperti
- Mesh: 1.600 combinati in tutti i modelli aperti
- Massimo 40 modelli aperti contemporaneamente

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Ottimizzazione dei modelli 3D per Visualizzatore 3D Beta

### <a name="special-considerations"></a>Considerazioni speciali

- Evitare materiali neri o aree nere nelle mappe di trama. Ologrammi sono di luce, pertanto HoloLens il nero (l'assenza di luce) come trasparente.
- Prima di eseguire l'esportazione in FBX dallo strumento di creazione, verificare che tutta la geometria sia visibile e sbloccata e che nessun livello contenente geometria sia disattivato o su modello. La visibilità non viene rispettata.
- Evitare offset di traslazione molto grandi tra i nodi (ad esempio, 100.000 unità). Ciò può causare instabilità del modello durante lo spostamento, la scalabilità o la rotazione.

### <a name="performance-optimization"></a>Ottimizzazione delle prestazioni

Per ottenere risultati ottimali, tenere presenti le prestazioni durante la creazione del contenuto e la convalida nell'app Visualizzatore 3D Beta HoloLens durante il processo di creazione. Visualizzatore 3D Beta esegue il rendering del contenuto in tempo reale e le prestazioni sono soggette HoloLens funzionalità hardware.  

Esistono molte variabili in un modello 3D che possono influire sulle prestazioni. Visualizzatore 3D Beta visualizza un avviso al caricamento se sono presenti più di 150.000 vertici o più di 400 mesh. Le animazioni possono avere un impatto sulle prestazioni di altri modelli aperti. Esistono anche limiti rigidi per i modelli di numero totale, i vertici e le mesh che possono essere aperti contemporaneamente in Visualizzatore 3D Beta (vedere Limitazioni di file [e modelli).](#file-and-model-limitations)  

Se il modello 3D non viene eseguito bene a causa della complessità del modello, considerare:

- Riduzione del numero di poligoni
- Riduzione del numero di elementi in un'animazione non ancorata
- Evitare l'occlusione autonoma

Il rendering lato doppio è supportato in Visualizzatore 3D Beta, anche se è disattivato per impostazione predefinita per motivi di prestazioni. Questa opzione può essere attivata tramite **il pulsante Doppio lato** nella **pagina** Dettagli. Per ottenere prestazioni ottimali, evitare la necessità di eseguire il rendering su due lati nel contenuto.

### <a name="validating-your-3d-model"></a>Convalida del modello 3D

Convalidare il modello aprendolo in Visualizzatore 3D Beta in HoloLens. Selezionare il **pulsante** Dettagli per visualizzare le caratteristiche e gli avvisi del modello relativi a contenuto non supportato (se presente).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Rendering di modelli 3D con dimensioni true-to-life

Per impostazione predefinita, Visualizzatore 3D Beta visualizza modelli 3D con dimensioni e posizione familiari rispetto all'utente. Tuttavia, se il rendering di un modello 3D con misurazioni true-to-life è importante (ad esempio, quando si valutano modelli di recupero in una stanza), l'autore del contenuto può impostare un flag all'interno dei metadati del file per impedire il ridimensionamento del modello sia da parte dell'applicazione che dell'utente.

Per impedire il ridimensionamento del modello, aggiungere un attributo personalizzato booleano a qualsiasi oggetto nella scena denominato Microsoft_DisableScale e impostarlo su true. Visualizzatore 3D Beta rispetterà quindi le informazioni FbxSystemUnit contenute nel file FBX. La scalabilità Visualizzatore 3D Beta è di 1 metro per unità FBX.

## <a name="viewing-fbx-files-on-hololens"></a>Visualizzazione di file FBX in HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Aprire un file FBX da Microsoft Edge

I file FBX possono essere aperti direttamente da un sito Web usando Microsoft Edge in HoloLens.

1. In Microsoft Edge passare alla pagina Web contenente il file FBX che si vuole visualizzare.
1. Selezionare il file per scaricarlo.
1. Al termine del download, selezionare il **pulsante** Apri in Microsoft Edge per aprire il file in Visualizzatore 3D Beta.

È possibile accedere al file scaricato e riaperrlo in un secondo momento usando Download in Microsoft Edge. Per salvare un modello 3D e garantire l'accesso continuo, scaricare il file nel PC e salvarlo nell'account OneDrive personale. Il file può quindi essere aperto dall'app OneDrive in HoloLens.

> [!NOTE]
> Alcuni siti Web con modelli FBX scaricabili li forniscono in formato ZIP compresso. Visualizzatore 3D Beta non può aprire direttamente i file ZIP. Usare invece il PC per estrarre il file FBX e salvarlo nell'account OneDrive personale. Il file può quindi essere aperto dall'app OneDrive in HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Aprire un file FBX da OneDrive

I file FBX possono essere aperti da OneDrive usando l'app OneDrive in HoloLens. Assicurarsi di aver installato OneDrive'app Microsoft Store in HoloLens e di aver già caricato il file FBX in OneDrive nel PC.

Una volta OneDrive, i file FBX possono essere aperti in HoloLens usando Visualizzatore 3D Beta in uno dei due modi seguenti:

- Avviare OneDrive in HoloLens e selezionare il file FBX per aprirlo in Visualizzatore 3D Beta.
- Avviare Visualizzatore 3D Beta, fare clic con il pulsante del mouse per visualizzare la barra degli strumenti e **selezionare Apri file.** OneDrive verrà avviato, consentendo di selezionare un file FBX.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Viene visualizzato un avviso quando si apre un modello 3D

Verrà visualizzato un avviso se si tenta di aprire un modello 3D che contiene funzionalità non supportate da Visualizzatore 3D Beta o se il modello è troppo complesso e le prestazioni potrebbero essere influenzate. Visualizzatore 3D Beta carica comunque il modello 3D, ma le prestazioni o la fedeltà visiva potrebbero essere compromesse.

Per altre informazioni, vedere [Specifiche di contenuto supportate](#supported-content-specifications) e [Ottimizzazione dei modelli 3D per Visualizzatore 3D Beta.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Viene visualizzato un avviso e il modello 3D non viene caricato

Verrà visualizzato un messaggio di errore quando Visualizzatore 3D Beta non è in grado di caricare un modello 3D a causa di complessità o dimensioni del file o se il file FBX è danneggiato o non valido. Verrà visualizzato un messaggio di errore anche se è stato raggiunto il limite per il numero totale di modelli, vertici o mesh che possono essere aperti contemporaneamente.  

Per altre informazioni, vedere [Specifiche di contenuto supportate e](#supported-content-specifications) Limitazioni di file e [modelli.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Il modello 3D viene caricato, ma non viene visualizzato come previsto

Se il modello 3D non ha l'aspetto previsto in Visualizzatore 3D Beta, fare clic per visualizzare la barra degli strumenti e quindi selezionare **Dettagli.** Gli aspetti del file che non sono supportati da Visualizzatore 3D Beta verranno evidenziati come avvisi.

Il problema più comune che potrebbe verificarsi è la mancanza di trame, probabilmente perché non sono incorporate nel file FBX. In questo caso, il modello verrà visualizzato in bianco. Questo problema può essere risolto durante il processo di creazione esportando dallo strumento di creazione in FBX con l'opzione incorporamento trame selezionata.

Per altre informazioni, vedere [Specifiche di contenuto supportate](#supported-content-specifications) e [Ottimizzazione dei modelli 3D per Visualizzatore 3D Beta.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Si verifica un calo delle prestazioni durante la visualizzazione del modello 3D

Le prestazioni durante il caricamento e la visualizzazione di un modello 3D possono essere influenzate dalla complessità del modello, dal numero di modelli aperti simultaneamente o dal numero di modelli con animazioni attive.

Per altre informazioni, vedere [Ottimizzazione dei modelli 3D per Visualizzatore 3D beta](#optimizing-3d-models-for-3d-viewer-beta) e [Limitazioni di file e modelli.](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Quando si apre un file FBX HoloLens, non si apre in Visualizzatore 3D Beta

Visualizzatore 3D Beta viene automaticamente associata all'estensione di file fbx al momento dell'installazione.

Se si tenta di aprire un file FBX e viene visualizzata una finestra di dialogo che indirizza a Microsoft Store, non è attualmente disponibile un'app associata all'estensione di file fbx in HoloLens.

Verificare che Visualizzatore 3D Beta sia installato. Se non è installato, scaricarlo da Microsoft Store in HoloLens.

Se Visualizzatore 3D Beta è già installato, avviare Visualizzatore 3D Beta, quindi provare ad aprire di nuovo il file. Se il problema persiste, disinstallare e reinstallare Visualizzatore 3D Beta. In questo modo l'estensione di file fbx verrà nuovamente associata Visualizzatore 3D Beta.

Se il tentativo di aprire un file FBX apre un'app diversa da Visualizzatore 3D Beta, è probabile che l'app sia stata installata dopo Visualizzatore 3D Beta e abbia assunto l'associazione con l'estensione di file fbx. Se si preferisce Visualizzatore 3D Beta per essere associato all'estensione di file fbx, disinstallare e reinstallare Visualizzatore 3D Beta.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>Il pulsante Apri file in Visualizzatore 3D Beta non avvia un'app

Il **pulsante Apri file** aprirà l'app associata alla funzione di selezione file HoloLens. Se OneDrive installato, il **pulsante Apri file** dovrebbe OneDrive. Tuttavia, se attualmente non è presente alcuna app associata alla funzione di selezione file installata in HoloLens, si verrà indirizzati a Microsoft Store.

Se il **pulsante Apri file** avvia un'app diversa da OneDrive, è probabile che l'app sia stata installata dopo OneDrive e abbia assunto l'associazione con la funzione di selezione file. Se si preferisce OneDrive avviare quando si seleziona il pulsante Apri **file** in Visualizzatore 3D Beta, disinstallare e reinstallare OneDrive.

Se il **pulsante Apri file** non è attivo, è possibile che sia stato raggiunto il limite di modelli che possono essere aperti in Visualizzatore 3D Beta contemporaneamente. Se in Visualizzatore 3D Beta sono aperti 40 modelli, è necessario chiude alcuni modelli prima di poter aprire modelli aggiuntivi.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Forum di supporto:](http://forums.hololens.com/categories/3d-viewer-beta) solo a scopo di archiviazione. Questo forum non è più attivo.
- [Comunicazioni di terze parti](https://www.microsoft.com/{lang-locale}/legal/products)
