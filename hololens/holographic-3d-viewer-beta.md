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
# <span data-ttu-id="3cfae-103">Uso del visualizzatore 3D in HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="3cfae-103">Using 3D Viewer on HoloLens (1st gen)</span></span>

<span data-ttu-id="3cfae-104">Il visualizzatore 3D consente di visualizzare i modelli 3D in HoloLens (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="3cfae-104">3D Viewer lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="3cfae-105">È possibile aprire e visualizzare i file in formato FBX *supportati* da Microsoft Edge, OneDrive e altre app.</span><span class="sxs-lookup"><span data-stu-id="3cfae-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="3cfae-106">Questo articolo si applica all'app immersiva Unity **Visualizzatore 3D** che supporta file FBX ed è disponibile solo in HoloLens (prima generazione).</span><span class="sxs-lookup"><span data-stu-id="3cfae-106">This article applies to the immersive Unity **3D Viewer** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="3cfae-107">La versione preinstallata del **visualizzatore 3D** in HoloLens 2 supporta l'apertura di modelli 3D in formato GLB personalizzati in ambiente iniziale. Per altre informazioni, vedere [Panoramica dei requisiti delle risorse](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview).</span><span class="sxs-lookup"><span data-stu-id="3cfae-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

<span data-ttu-id="3cfae-108">Se si verificano problemi durante l'apertura di un modello 3D in un visualizzatore 3D o se alcune funzionalità del modello non sono supportate, vedere [Specifiche dei contenuti supportati](#supported-content-specifications).</span><span class="sxs-lookup"><span data-stu-id="3cfae-108">If you're having trouble opening a 3D model in 3D Viewer, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications).</span></span>

<span data-ttu-id="3cfae-109">Per creare od ottimizzare i modelli 3D da usare con il visualizzatore 3D, vedere [Ottimizzazione dei modelli 3D per il visualizzatore 3D](#optimizing-3d-models-for-3d-viewer).</span><span class="sxs-lookup"><span data-stu-id="3cfae-109">To build or optimize 3D models for use with 3D Viewer, see [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer).</span></span>

<span data-ttu-id="3cfae-110">Esistono due modalità di apertura di un modello 3D in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-110">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="3cfae-111">Per altre informazioni, vedere [Visualizzare i file in formato FBX in HoloLens](#viewing-fbx-files-on-hololens).</span><span class="sxs-lookup"><span data-stu-id="3cfae-111">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) to learn more.</span></span>

<span data-ttu-id="3cfae-112">In caso di problemi durante la lettura di questi argomenti, vedere [Risoluzione dei problemi](#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="3cfae-112">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting).</span></span>

## <span data-ttu-id="3cfae-113">Specifiche dei contenuti supportati</span><span class="sxs-lookup"><span data-stu-id="3cfae-113">Supported content specifications</span></span>

### <span data-ttu-id="3cfae-114">Formato file</span><span class="sxs-lookup"><span data-stu-id="3cfae-114">File format</span></span>

- <span data-ttu-id="3cfae-115">Formato FBX</span><span class="sxs-lookup"><span data-stu-id="3cfae-115">FBX format</span></span>
- <span data-ttu-id="3cfae-116">Versione massima FBX: 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="3cfae-116">Maximum FBX release 2015.1.0</span></span>

### <span data-ttu-id="3cfae-117">Dimensione file</span><span class="sxs-lookup"><span data-stu-id="3cfae-117">File size</span></span>

- <span data-ttu-id="3cfae-118">Minima: 5 GB</span><span class="sxs-lookup"><span data-stu-id="3cfae-118">Minimum 5 KB</span></span>
- <span data-ttu-id="3cfae-119">Massima: 500 MB</span><span class="sxs-lookup"><span data-stu-id="3cfae-119">Maximum 500 MB</span></span>

### <span data-ttu-id="3cfae-120">Geometria</span><span class="sxs-lookup"><span data-stu-id="3cfae-120">Geometry</span></span>

- <span data-ttu-id="3cfae-121">Solo modelli poligonali.</span><span class="sxs-lookup"><span data-stu-id="3cfae-121">Polygonal models only.</span></span> <span data-ttu-id="3cfae-122">Nessuna suddivisione delle superfici o NURB</span><span class="sxs-lookup"><span data-stu-id="3cfae-122">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="3cfae-123">Sistema di coordinate destrorso</span><span class="sxs-lookup"><span data-stu-id="3cfae-123">Right-handed coordinate system</span></span>
- <span data-ttu-id="3cfae-124">La distorsione delle matrici di trasformazione non è supportata</span><span class="sxs-lookup"><span data-stu-id="3cfae-124">Shear in transformation matrices is not supported</span></span>

### <span data-ttu-id="3cfae-125">Trame</span><span class="sxs-lookup"><span data-stu-id="3cfae-125">Textures</span></span>

- <span data-ttu-id="3cfae-126">Il mapping delle trame deve essere incorporato nel file FBX</span><span class="sxs-lookup"><span data-stu-id="3cfae-126">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="3cfae-127">Formati immagine supportati</span><span class="sxs-lookup"><span data-stu-id="3cfae-127">Supported image formats</span></span>
  - <span data-ttu-id="3cfae-128">Immagini JPEG e PNG</span><span class="sxs-lookup"><span data-stu-id="3cfae-128">JPEG and PNG images</span></span>
  - <span data-ttu-id="3cfae-129">Immagini BMP (16,8 milioni di colori RGB 24 bit)</span><span class="sxs-lookup"><span data-stu-id="3cfae-129">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="3cfae-130">Immagini TGA (16,8 milioni di colori RGB 24 bit e RGBQ 32 bit)</span><span class="sxs-lookup"><span data-stu-id="3cfae-130">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="3cfae-131">Risoluzione massima della trama: 2048x2048</span><span class="sxs-lookup"><span data-stu-id="3cfae-131">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="3cfae-132">Massimo un mapping diffuso, un mapping normale e un mapping cubo di riflessione per mesh</span><span class="sxs-lookup"><span data-stu-id="3cfae-132">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="3cfae-133">Il canale alfa nelle trame diffuse causa il rigetto dei pixel se inferiori al 50%</span><span class="sxs-lookup"><span data-stu-id="3cfae-133">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <span data-ttu-id="3cfae-134">Animazione</span><span class="sxs-lookup"><span data-stu-id="3cfae-134">Animation</span></span>

- <span data-ttu-id="3cfae-135">Ridimensionamento/rotazione/traslazione delle animazioni su singoli oggetti</span><span class="sxs-lookup"><span data-stu-id="3cfae-135">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="3cfae-136">Animazione scheletrica (ossa) con l’uso delle interfacce</span><span class="sxs-lookup"><span data-stu-id="3cfae-136">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="3cfae-137">Massimo 4 influenze per vertice</span><span class="sxs-lookup"><span data-stu-id="3cfae-137">Maximum of 4 influences per vertex</span></span>

### <span data-ttu-id="3cfae-138">Materiali</span><span class="sxs-lookup"><span data-stu-id="3cfae-138">Materials</span></span>

- <span data-ttu-id="3cfae-139">I materiali Lambert e Phong sono supportati con parametri variabili</span><span class="sxs-lookup"><span data-stu-id="3cfae-139">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="3cfae-140">Proprietà dei materiali supportati per Lambert</span><span class="sxs-lookup"><span data-stu-id="3cfae-140">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="3cfae-141">Trama principale (RGB + test Alpha)</span><span class="sxs-lookup"><span data-stu-id="3cfae-141">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="3cfae-142">Colore diffuso (RGB)</span><span class="sxs-lookup"><span data-stu-id="3cfae-142">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="3cfae-143">Colore ambientale (RGB)</span><span class="sxs-lookup"><span data-stu-id="3cfae-143">Ambient Color (RGB)</span></span>
- <span data-ttu-id="3cfae-144">Proprietà dei materiali supportati per Phong</span><span class="sxs-lookup"><span data-stu-id="3cfae-144">Supported material properties for Phong</span></span>
  - <span data-ttu-id="3cfae-145">Trama principale (RGB + test Alpha)</span><span class="sxs-lookup"><span data-stu-id="3cfae-145">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="3cfae-146">Colore diffuso (RGB)</span><span class="sxs-lookup"><span data-stu-id="3cfae-146">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="3cfae-147">Colore ambientale (RGB)</span><span class="sxs-lookup"><span data-stu-id="3cfae-147">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="3cfae-148">Colore speculare (RGB)</span><span class="sxs-lookup"><span data-stu-id="3cfae-148">Specular Color (RGB)</span></span>
  - <span data-ttu-id="3cfae-149">Lucentezza</span><span class="sxs-lookup"><span data-stu-id="3cfae-149">Shininess</span></span>
  - <span data-ttu-id="3cfae-150">Riflettività</span><span class="sxs-lookup"><span data-stu-id="3cfae-150">Reflectivity</span></span>
- <span data-ttu-id="3cfae-151">I materiali personalizzati non sono supportati</span><span class="sxs-lookup"><span data-stu-id="3cfae-151">Custom materials are not supported</span></span>
- <span data-ttu-id="3cfae-152">Massimo un materiale per mesh</span><span class="sxs-lookup"><span data-stu-id="3cfae-152">Maximum of one material per mesh</span></span>
- <span data-ttu-id="3cfae-153">Massimo un livello di materiale</span><span class="sxs-lookup"><span data-stu-id="3cfae-153">Maximum of one material layer</span></span>
- <span data-ttu-id="3cfae-154">Massimo 8 materiali per file</span><span class="sxs-lookup"><span data-stu-id="3cfae-154">Maximum of 8 materials per file</span></span>

### <span data-ttu-id="3cfae-155">Limitazioni per file e modelli</span><span class="sxs-lookup"><span data-stu-id="3cfae-155">File and model limitations</span></span>

<span data-ttu-id="3cfae-156">Esistono limiti rigidi per le dimensioni dei file, il numero di modelli, vertici e mesh che possono essere aperti contemporaneamente nel visualizzatore 3D:</span><span class="sxs-lookup"><span data-stu-id="3cfae-156">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer:</span></span>

- <span data-ttu-id="3cfae-157">Dimensione massima dei file per modello: 500 MB</span><span class="sxs-lookup"><span data-stu-id="3cfae-157">500 MB maximum file size per model</span></span>
- <span data-ttu-id="3cfae-158">Vertici: 600.000 combinati in tutti i modelli aperti</span><span class="sxs-lookup"><span data-stu-id="3cfae-158">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="3cfae-159">Mesh: 1.600 combinati in tutti i modelli aperti</span><span class="sxs-lookup"><span data-stu-id="3cfae-159">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="3cfae-160">Numero massimo di modelli aperti contemporaneamente: 40</span><span class="sxs-lookup"><span data-stu-id="3cfae-160">Maximum of 40 models open at one time</span></span>

## <span data-ttu-id="3cfae-161">Ottimizzazione dei modelli 3D per il visualizzatore 3D</span><span class="sxs-lookup"><span data-stu-id="3cfae-161">Optimizing 3D models for 3D Viewer</span></span>

### <span data-ttu-id="3cfae-162">Considerazioni particolari</span><span class="sxs-lookup"><span data-stu-id="3cfae-162">Special considerations</span></span>

- <span data-ttu-id="3cfae-163">Evitare materiali di colore nero o aree nere nel mapping delle trame.</span><span class="sxs-lookup"><span data-stu-id="3cfae-163">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="3cfae-164">Gli ologrammi sono fatti di luce, perciò HoloLens esegue il rendering del colore nero (assenza di luce) come trasparente.</span><span class="sxs-lookup"><span data-stu-id="3cfae-164">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="3cfae-165">Prima di esportare in formato FBX dallo strumento di creazione, assicurarsi che la geometria sia visibile e non bloccata e che nessun livello contenente geometria sia disattivato o basato su modelli.</span><span class="sxs-lookup"><span data-stu-id="3cfae-165">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="3cfae-166">Visibilità non rispettata.</span><span class="sxs-lookup"><span data-stu-id="3cfae-166">Visibility is not respected.</span></span>
- <span data-ttu-id="3cfae-167">Evitare offset di traslazione molto grandi tra i nodi, ad esempio 100.000 unità.</span><span class="sxs-lookup"><span data-stu-id="3cfae-167">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="3cfae-168">Ciò può causare l’instabilità del modello durante lo spostamento/ridimensionamento/rotazione.</span><span class="sxs-lookup"><span data-stu-id="3cfae-168">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <span data-ttu-id="3cfae-169">Ottimizzazione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="3cfae-169">Performance optimization</span></span>

<span data-ttu-id="3cfae-170">Tenere presenti le prestazioni durante la creazione dei contenuti e convalidarle nell'app Visualizzatore 3D su HoloLens per ottenere risultati ottimali.</span><span class="sxs-lookup"><span data-stu-id="3cfae-170">Keep performance in mind while authoring content and validate in the 3D Viewer app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="3cfae-171">Il visualizzatore 3D esegue il rendering dei contenuti in tempo reale e le prestazioni dipendono dalle funzionalità hardware di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-171">3D Viewer renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="3cfae-172">Molte variabile possono influire sulle prestazioni di un modello 3D.</span><span class="sxs-lookup"><span data-stu-id="3cfae-172">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="3cfae-173">Il visualizzatore 3D mostrerà un messaggio di avviso durante il caricamento se sono presenti più di 150.000 vertici o di 400 mesh.</span><span class="sxs-lookup"><span data-stu-id="3cfae-173">3D Viewer will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="3cfae-174">Le animazioni possono influire sulle prestazioni di altri modelli aperti.</span><span class="sxs-lookup"><span data-stu-id="3cfae-174">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="3cfae-175">Inoltre, esistono limiti rigidi per il numero totale di modelli, vertici e mesh che possono essere aperti contemporaneamente nel visualizzatore 3D, vedere [Limitazioni per file e modelli](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="3cfae-175">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="3cfae-176">Se il modello 3D non viene eseguito correttamente a causa della complessità del modello, prendere in considerazione:</span><span class="sxs-lookup"><span data-stu-id="3cfae-176">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="3cfae-177">Riduzione del numero di poligoni</span><span class="sxs-lookup"><span data-stu-id="3cfae-177">Reducing polygon count</span></span>
- <span data-ttu-id="3cfae-178">Riduzione del numero di ossa nelle animazioni</span><span class="sxs-lookup"><span data-stu-id="3cfae-178">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="3cfae-179">Evitare auto occlusione</span><span class="sxs-lookup"><span data-stu-id="3cfae-179">Avoiding self-occlusion</span></span>

<span data-ttu-id="3cfae-180">Il rendering su due lati è supportato nel visualizzatore 3D, anche se per motivi di prestazioni è disattivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3cfae-180">Double-sided rendering is supported in 3D Viewer, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="3cfae-181">Questa opzione può essere attivata tramite il pulsante **Fronte retro** nella pagina **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3cfae-181">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="3cfae-182">Per ottenere prestazioni ottimali, evitare il rendering su due lati nei contenuti.</span><span class="sxs-lookup"><span data-stu-id="3cfae-182">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <span data-ttu-id="3cfae-183">Convalida del modello 3D</span><span class="sxs-lookup"><span data-stu-id="3cfae-183">Validating your 3D model</span></span>

<span data-ttu-id="3cfae-184">Convalidare il modello aprendolo nel visualizzatore 3D su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-184">Validate your model by opening it in 3D Viewer on HoloLens.</span></span> <span data-ttu-id="3cfae-185">Selezionare il pulsante **Dettagli** per visualizzare le funzionalità del modello e i messaggi di avviso per i contenuti non supportato, se presenti.</span><span class="sxs-lookup"><span data-stu-id="3cfae-185">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <span data-ttu-id="3cfae-186">Rendering di modelli 3D con dimensioni reali</span><span class="sxs-lookup"><span data-stu-id="3cfae-186">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="3cfae-187">Per impostazione predefinita, il visualizzatore 3D mostra i modelli 3D con una dimensione e una posizione comode in rapporto all'utente.</span><span class="sxs-lookup"><span data-stu-id="3cfae-187">By default, 3D Viewer displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="3cfae-188">Tuttavia, se il rendering di un modello 3D con misure reali è importante, ad esempio quando si esaminano modelli di mobili per una stanza, l'autore del contenuto può inserire un contrassegnare nei metadati del file per impedire che l’applicazione o l’utente possano ridimensionare il modello.</span><span class="sxs-lookup"><span data-stu-id="3cfae-188">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="3cfae-189">Per impedire il ridimensionamento del modello, aggiungere un attributo personalizzato booleano a tutti gli oggetti nella scena denominata Microsoft_DisableScale e impostarlo come vero.</span><span class="sxs-lookup"><span data-stu-id="3cfae-189">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="3cfae-190">Il visualizzatore 3D rispetterà le informazioni di FbxSystemUnit contenute nel file FBX.</span><span class="sxs-lookup"><span data-stu-id="3cfae-190">3D Viewer will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="3cfae-191">Il ridimensionamento nel visualizzatore 3D è 1 m per unità FBX.</span><span class="sxs-lookup"><span data-stu-id="3cfae-191">Scale in 3D Viewer is 1 meter per FBX unit.</span></span>

## <span data-ttu-id="3cfae-192">Visualizzare i file FBX in HoloLens</span><span class="sxs-lookup"><span data-stu-id="3cfae-192">Viewing FBX files on HoloLens</span></span>

### <span data-ttu-id="3cfae-193">Aprire un file di FBX in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3cfae-193">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="3cfae-194">I file FBX possono essere aperti direttamente da un sito Web tramite Microsoft Edge in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-194">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="3cfae-195">In Microsoft Edge, passare alla pagina Web che contiene il file FBX che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="3cfae-195">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="3cfae-196">Selezionare il file per scaricarlo.</span><span class="sxs-lookup"><span data-stu-id="3cfae-196">Select the file to download it.</span></span>
1. <span data-ttu-id="3cfae-197">Una volta completato il download, selezionare il pulsante **Apri** in Microsoft Edge per aprire il file nel visualizzatore 3D.</span><span class="sxs-lookup"><span data-stu-id="3cfae-197">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer.</span></span>

<span data-ttu-id="3cfae-198">È possibile accedere e aprire nuovamente il file scaricato in un secondo momento usando l’opzione Download in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="3cfae-198">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="3cfae-199">Per salvare un modello 3D e garantirne l'accesso continuato, scaricare il file nel PC e salvarlo nell'account di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3cfae-199">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="3cfae-200">Il file può essere aperto dall'app OneDrive in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-200">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="3cfae-201">Alcuni siti Web con modelli FBX scaricabili, li forniscono in formato ZIP compresso.</span><span class="sxs-lookup"><span data-stu-id="3cfae-201">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="3cfae-202">Il visualizzatore 3D non può aprire direttamente i file ZIP.</span><span class="sxs-lookup"><span data-stu-id="3cfae-202">3D Viewer cannot open ZIP files directly.</span></span> <span data-ttu-id="3cfae-203">In alternativa, usare il PC per estrarre i file FBX e salvarli nell'account di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3cfae-203">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="3cfae-204">Il file può essere aperto dall'app OneDrive in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-204">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <span data-ttu-id="3cfae-205">Aprire un file FBX in OneDrive</span><span class="sxs-lookup"><span data-stu-id="3cfae-205">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="3cfae-206">È possibile aprire i file FBX in OneDrive usando l'app OneDrive in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-206">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="3cfae-207">Assicurarsi di aver installato OneDrive tramite l'app Microsoft Store in HoloLens e di aver già caricato il file FBX in OneDrive nel PC.</span><span class="sxs-lookup"><span data-stu-id="3cfae-207">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="3cfae-208">In OneDrive è possibile aprire i file FBX in HoloLens usando il visualizzatore 3D in due modi:</span><span class="sxs-lookup"><span data-stu-id="3cfae-208">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer in one of two ways:</span></span>

- <span data-ttu-id="3cfae-209">Avviare OneDrive in HoloLens e selezionare il file FBX per aprirlo nel visualizzatore 3D.</span><span class="sxs-lookup"><span data-stu-id="3cfae-209">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer.</span></span>
- <span data-ttu-id="3cfae-210">Avviare il visualizzatore 3D, simulare il tocco per visualizzare la barra degli strumenti e selezionare **Apri file**.</span><span class="sxs-lookup"><span data-stu-id="3cfae-210">Launch 3D Viewer, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="3cfae-211">Verrà avviato OneDrive, che consentirà di selezionare un file FBX.</span><span class="sxs-lookup"><span data-stu-id="3cfae-211">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <span data-ttu-id="3cfae-212">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="3cfae-212">Troubleshooting</span></span>

### <span data-ttu-id="3cfae-213">Visualizzo un avviso quando apro un modello 3D</span><span class="sxs-lookup"><span data-stu-id="3cfae-213">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="3cfae-214">Viene visualizzato un messaggio di avviso quando si prova ad aprire un modello 3D che contiene funzionalità non supportate dal visualizzatore 3D o se il modello è troppo complesso e ciò potrebbe influire sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3cfae-214">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="3cfae-215">Il visualizzatore 3D caricherà comunque il modello 3D, ma le prestazioni o la fedeltà visiva potrebbero essere compromesse.</span><span class="sxs-lookup"><span data-stu-id="3cfae-215">3D Viewer will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="3cfae-216">Per altre informazioni, vedere [Specifiche dei contenuti supportati](#supported-content-specifications) e [Ottimizzazione dei modelli 3D per il visualizzatore 3D](#optimizing-3d-models-for-3d-viewer).</span><span class="sxs-lookup"><span data-stu-id="3cfae-216">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer).</span></span>

### <span data-ttu-id="3cfae-217">Visualizzo un avviso e il modello 3D non viene caricato</span><span class="sxs-lookup"><span data-stu-id="3cfae-217">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="3cfae-218">Viene visualizzato un messaggio di errore quando il visualizzatore 3D non può caricare un modello 3D a causa della complessità o delle dimensioni del file oppure se il file FBX è danneggiato o non valido.</span><span class="sxs-lookup"><span data-stu-id="3cfae-218">You will see an error message when 3D Viewer cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="3cfae-219">Viene visualizzato un messaggio di errore anche se è stato raggiunto il limite del numero totale di modelli, vertici o mesh che è possibile aprire contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3cfae-219">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="3cfae-220">Per altre informazioni, vedere [Specifiche dei contenuti supportati](#supported-content-specifications) e [Limitazioni per file e modelli](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="3cfae-220">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

<span data-ttu-id="3cfae-221">Se si ritiene che il modello soddisfi le specifiche dei contenuti supportati e che non siano stati superati i limiti dei file o modelli, è possibile inviare il file FBX al team del visualizzatore 3D all’indirizzo holoapps@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3cfae-221">If you feel your model meets the supported content specifications and has not exceeded the file or model limitations, you may send your FBX file to the 3D Viewer team at holoapps@microsoft.com.</span></span> <span data-ttu-id="3cfae-222">Non siamo in grado di rispondere ai singoli messaggi, ma ricevere gli esempi di file che non vengono caricati correttamente aiuterà il team a migliorare le versioni future dell'app.</span><span class="sxs-lookup"><span data-stu-id="3cfae-222">We are not able to respond personally, but having examples of files that do not load properly will help our team improve on future versions of the app.</span></span>

### <span data-ttu-id="3cfae-223">Il modello 3D viene caricato ma non viene visualizzato come previsto</span><span class="sxs-lookup"><span data-stu-id="3cfae-223">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="3cfae-224">Se il modello 3D non ha l’aspetto previsto nel visualizzatore 3D, simulare il tocco per visualizzare la barra degli strumenti, poi selezionare **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3cfae-224">If your 3D model does not look as expected in 3D Viewer, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="3cfae-225">Gli elementi dei file non supportati dal visualizzatore 3D verranno evidenziate con messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="3cfae-225">Aspects of the file which are not supported by 3D Viewer will be highlighted as warnings.</span></span>

<span data-ttu-id="3cfae-226">I problemi più comuni che potrebbero verificarsi riguardano le trame mancanti, probabilmente perché non sono incorporate nel file FBX.</span><span class="sxs-lookup"><span data-stu-id="3cfae-226">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="3cfae-227">In questo caso, il modello apparirà bianco.</span><span class="sxs-lookup"><span data-stu-id="3cfae-227">In this case, the model will appear white.</span></span> <span data-ttu-id="3cfae-228">Questo problema può essere risolto nel processo di creazione esportando dallo strumento di creazione in formato FBX e selezionando l'opzione di incorporazione della trama.</span><span class="sxs-lookup"><span data-stu-id="3cfae-228">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="3cfae-229">Per altre informazioni, vedere [Specifiche dei contenuti supportati](#supported-content-specifications) e [Ottimizzazione dei modelli 3D per il visualizzatore 3D](#optimizing-3d-models-for-3d-viewer).</span><span class="sxs-lookup"><span data-stu-id="3cfae-229">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer).</span></span>

### <span data-ttu-id="3cfae-230">Durante la visualizzazione di un modello 3D, si verifica una diminuzione delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="3cfae-230">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="3cfae-231">Durante il caricamento e la visualizzazione di un modello 3D, le prestazioni possono essere interessate dalla complessità del modello, dal numero di modelli aperti contemporaneamente o dal numero di modelli con animazioni attive.</span><span class="sxs-lookup"><span data-stu-id="3cfae-231">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="3cfae-232">Per altre informazioni, vedere [Ottimizzazione dei modelli 3D per il visualizzatore 3D](#optimizing-3d-models-for-3d-viewer) e [Limitazioni per file e modelli](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="3cfae-232">For more info, see [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="3cfae-233">Quando apro un file FBX in HoloLens, non si apre in visualizzatore 3D</span><span class="sxs-lookup"><span data-stu-id="3cfae-233">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer</span></span>

<span data-ttu-id="3cfae-234">Il visualizzatore 3D viene associato automaticamente ai file con estensione FBX al momento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="3cfae-234">3D Viewer is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="3cfae-235">Se si prova ad aprire un file FBX e viene visualizzata una finestra di dialogo che indirizza a Microsoft Store significa che non si ha al momento un'app associata ai file con estensione FBX in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-235">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="3cfae-236">Verificare che il visualizzatore 3D sia installato.</span><span class="sxs-lookup"><span data-stu-id="3cfae-236">Verify that 3D Viewer is installed.</span></span> <span data-ttu-id="3cfae-237">Se non è installato, scaricarlo da Microsoft Store in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-237">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="3cfae-238">Se il visualizzatore 3D è già installato, avviarlo e poi riprovare ad aprire il file.</span><span class="sxs-lookup"><span data-stu-id="3cfae-238">If 3D Viewer is already installed, launch 3D Viewer, then try opening the file again.</span></span> <span data-ttu-id="3cfae-239">Se il problema persiste, disinstallare e reinstallare il visualizzatore 3D.</span><span class="sxs-lookup"><span data-stu-id="3cfae-239">If the issue persists, uninstall and reinstall 3D Viewer.</span></span> <span data-ttu-id="3cfae-240">Questa operazione consentirà di associare nuovamente i file con estensione FBX al visualizzatore 3D.</span><span class="sxs-lookup"><span data-stu-id="3cfae-240">This will re-associate the .fbx file extension with 3D Viewer.</span></span>

<span data-ttu-id="3cfae-241">Se si prova ad aprire un file FBX e viene aperta un'app diversa dal visualizzatore 3D, è probabile che l'app sia stata installata dopo il visualizzatore 3D e abbia rilevato l'associazione con l'estensione di file FBX.</span><span class="sxs-lookup"><span data-stu-id="3cfae-241">If attempting to open an FBX file opens an app other than 3D Viewer, that app was likely installed after 3D Viewer and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="3cfae-242">Se si preferisce che il visualizzatore 3D sia associato all'estensione di file FBX, disinstallare l’app e installarla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="3cfae-242">If you prefer 3D Viewer to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer.</span></span>

### <span data-ttu-id="3cfae-243">Il pulsante Apri file in visualizzatore 3D non avvia l'app</span><span class="sxs-lookup"><span data-stu-id="3cfae-243">The Open File button in 3D Viewer doesn't launch an app</span></span>

<span data-ttu-id="3cfae-244">Il pulsante **Apri file** aprirà l'app associata alla funzione di selezione dei file in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3cfae-244">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="3cfae-245">Se è installato OneDrive, il pulsante **Apri file** dovrebbe avviare OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3cfae-245">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="3cfae-246">Tuttavia, se al momento non è associata alcuna app alla funzione di selezione dei file installata in HoloLens, si verrà reindirizzati a Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="3cfae-246">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="3cfae-247">Se il pulsante **Apri file** avvia un'app diversa da OneDrive, è probabile che l'app sia stata installata dopo OneDrive e ha rilevato l'associazione con la funzione di selezione file.</span><span class="sxs-lookup"><span data-stu-id="3cfae-247">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="3cfae-248">Se si preferisce l’avvio di OneDrive quando si seleziona il pulsante **Apri file** nel visualizzatore 3D, disinstallare e reinstallare OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3cfae-248">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="3cfae-249">Se il pulsante **Apri file** non è attivo, è possibile che sia stato raggiunto il limite di modelli che è possibile aprire contemporaneamente in un visualizzatore 3D.</span><span class="sxs-lookup"><span data-stu-id="3cfae-249">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer at one time.</span></span> <span data-ttu-id="3cfae-250">Se si hanno 40 modelli aperti in visualizzatore 3D, è necessario chiuderli alcuni prima di riuscire ad aprire altri modelli.</span><span class="sxs-lookup"><span data-stu-id="3cfae-250">If you have 40 models open in 3D Viewer, you will need to close some before you will be able to open additional models.</span></span>

## <span data-ttu-id="3cfae-251">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3cfae-251">Additional resources</span></span>

- [<span data-ttu-id="3cfae-252">Forum del supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="3cfae-252">Support forums</span></span>](http://forums.hololens.com/categories/3d-viewer-beta)
- [<span data-ttu-id="3cfae-253">Avvisi di terze parti</span><span class="sxs-lookup"><span data-stu-id="3cfae-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
