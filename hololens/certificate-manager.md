---
title: Gestione certificati
description: Informazioni su come installare, gestire e rimuovere manualmente i certificati in HoloLens 2 dispositivi di realtà mista.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283687"
---
# <span data-ttu-id="76748-103">Gestione certificati</span><span class="sxs-lookup"><span data-stu-id="76748-103">Certificate Manager</span></span>

- <span data-ttu-id="76748-104">Strumenti di controllo, diagnosi e convalida migliorati per la sicurezza e la conformità dei dispositivi tramite il nuovo gestore di certificati.</span><span class="sxs-lookup"><span data-stu-id="76748-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="76748-105">Questa funzionalità consentirà di distribuire, risolvere i problemi e convalidare i certificati in scala in ambienti commerciali.</span><span class="sxs-lookup"><span data-stu-id="76748-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="76748-106">In Windows olografico, versione 20H2, aggiungiamo un gestore di certificati nell'app impostazioni di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="76748-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="76748-107">Accedere a **impostazioni > aggiornare i certificati di > di sicurezza &**.</span><span class="sxs-lookup"><span data-stu-id="76748-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="76748-108">Questa funzionalità consente di visualizzare, installare e rimuovere certificati nel dispositivo in modo semplice e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="76748-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="76748-109">Con il nuovo gestore di certificati, gli amministratori e gli utenti hanno ora strumenti di controllo, diagnosi e convalida migliorati per garantire che i dispositivi rimangano sicuri e conformi.</span><span class="sxs-lookup"><span data-stu-id="76748-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="76748-110">**Controllo:** Possibilità di verificare che un certificato sia distribuito correttamente o per verificare che sia stato rimosso in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="76748-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="76748-111">**Diagnosi:** In caso di problemi, verifica che i certificati appropriati esistano nel dispositivo per risparmiare tempo e consente di risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="76748-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="76748-112">**Convalida:** Verificare che un certificato serva lo scopo previsto ed è funzionale, può risparmiare tempo significativo, in particolare in ambienti commerciali prima di distribuire i certificati su scala più ampia.</span><span class="sxs-lookup"><span data-stu-id="76748-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="76748-113">Per trovare rapidamente un certificato specifico nell'elenco, sono disponibili opzioni per ordinare in base al nome, all'archivio o alla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="76748-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="76748-114">Gli utenti possono anche cercare direttamente un certificato.</span><span class="sxs-lookup"><span data-stu-id="76748-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="76748-115">Per visualizzare le singole proprietà del certificato, selezionare il certificato e fare clic su **informazioni**.</span><span class="sxs-lookup"><span data-stu-id="76748-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="76748-116">L'installazione del certificato supporta attualmente i file con estensione CER e CRT.</span><span class="sxs-lookup"><span data-stu-id="76748-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="76748-117">I proprietari di dispositivi possono installare i certificati nel computer locale e nell'utente corrente;  tutti gli altri utenti possono essere installati solo nell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="76748-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="76748-118">Gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia utente delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="76748-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="76748-119">Se un certificato è stato installato con altri mezzi, deve essere rimosso anche dallo stesso meccanismo.</span><span class="sxs-lookup"><span data-stu-id="76748-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="76748-120">Per installare un certificato:</span><span class="sxs-lookup"><span data-stu-id="76748-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="76748-121">Connettere il HoloLens 2 a un PC.</span><span class="sxs-lookup"><span data-stu-id="76748-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="76748-122">Posizionare il file di certificato che si vuole installare in un percorso di HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="76748-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="76748-123">Passare all' **app impostazioni > aggiornare i certificati di & sicurezza >** e selezionare installa un certificato.</span><span class="sxs-lookup"><span data-stu-id="76748-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="76748-124">Fare clic su **Importa file** e passare alla posizione in cui è stato salvato il certificato.</span><span class="sxs-lookup"><span data-stu-id="76748-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="76748-125">Selezionare **posizione archivio**.</span><span class="sxs-lookup"><span data-stu-id="76748-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="76748-126">Selezionare **archivio certificati**.</span><span class="sxs-lookup"><span data-stu-id="76748-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="76748-127">Fai clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="76748-127">Click **Install**.</span></span>

<span data-ttu-id="76748-128">Il certificato dovrebbe ora essere installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76748-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="76748-129">Per rimuovere un certificato:</span><span class="sxs-lookup"><span data-stu-id="76748-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="76748-130">Passare all' **app impostazioni > aggiornamento e sicurezza > certificati**.</span><span class="sxs-lookup"><span data-stu-id="76748-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="76748-131">Cercare il certificato per nome nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="76748-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="76748-132">Selezionare il certificato.</span><span class="sxs-lookup"><span data-stu-id="76748-132">Select the certificate.</span></span>
1. <span data-ttu-id="76748-133">Fare clic su **Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="76748-133">Click **Remove**</span></span>
1. <span data-ttu-id="76748-134">Selezionare **Sì** quando viene richiesto di confermare.</span><span class="sxs-lookup"><span data-stu-id="76748-134">Select **Yes** when prompted for confirmation.</span></span>


![Visualizzatore certificati nell'app impostazioni in Ceritifcates](images/certificate-viewer-device.jpg)

![Immagine che Mostra come usare l'interfaccia utente del certificato per installare un certificato in impostazioni.](images/certificate-device-install.jpg)
