---
title: Gestione certificati
description: Informazioni su come installare, gestire e rimuovere manualmente i certificati HoloLens 2 dispositivi di realtà mista.
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
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397452"
---
# <a name="certificate-manager"></a><span data-ttu-id="026ad-103">Gestione certificati</span><span class="sxs-lookup"><span data-stu-id="026ad-103">Certificate Manager</span></span>

- <span data-ttu-id="026ad-104">Strumenti di controllo, diagnosi e convalida migliorati per la sicurezza e la conformità dei dispositivi tramite il nuovo Gestore certificati.</span><span class="sxs-lookup"><span data-stu-id="026ad-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="026ad-105">Questa funzionalità consente di distribuire, risolvere i problemi e convalidare i certificati su larga scala in ambienti commerciali.</span><span class="sxs-lookup"><span data-stu-id="026ad-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="026ad-106">In Windows Holographic versione 20H2 viene aggiunto un gestore di certificati nell'app HoloLens 2 impostazioni.</span><span class="sxs-lookup"><span data-stu-id="026ad-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="026ad-107">Passare a **Impostazioni > aggiornamento & sicurezza > certificati**.</span><span class="sxs-lookup"><span data-stu-id="026ad-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="026ad-108">Questa funzionalità offre un modo semplice e semplice per visualizzare, installare e rimuovere i certificati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="026ad-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="026ad-109">Con il nuovo gestore di certificati, gli amministratori e gli utenti hanno ora migliorato gli strumenti di controllo, diagnosi e convalida per garantire che i dispositivi rimangano sicuri e conformi.</span><span class="sxs-lookup"><span data-stu-id="026ad-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="026ad-110">**Controllo:** Possibilità di convalidare la corretta distribuzione di un certificato o di verificare che sia stato rimosso in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="026ad-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="026ad-111">**Diagnosi:** Quando si verificano problemi, la convalida dell'esistenza dei certificati appropriati nel dispositivo consente di risparmiare tempo e di risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="026ad-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="026ad-112">**Convalida:** La verifica che un certificato sia utile e funzionale può risparmiare tempo significativo, in particolare negli ambienti commerciali prima di distribuire i certificati su larga scala.</span><span class="sxs-lookup"><span data-stu-id="026ad-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="026ad-113">Per trovare rapidamente un certificato specifico nell'elenco, sono disponibili opzioni per ordinare in base al nome, all'archivio o alla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="026ad-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="026ad-114">Gli utenti possono anche cercare direttamente un certificato.</span><span class="sxs-lookup"><span data-stu-id="026ad-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="026ad-115">Per visualizzare le singole proprietà del certificato, selezionare il certificato e fare clic su **Info**.</span><span class="sxs-lookup"><span data-stu-id="026ad-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="026ad-116">L'installazione del certificato attualmente supporta i file con estensione cer e crt.</span><span class="sxs-lookup"><span data-stu-id="026ad-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="026ad-117">I proprietari dei dispositivi possono installare i certificati nel computer locale e nell'utente corrente.  tutti gli altri utenti possono eseguire l'installazione solo in Utente corrente.</span><span class="sxs-lookup"><span data-stu-id="026ad-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="026ad-118">Gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia utente delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="026ad-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="026ad-119">Se un certificato è stato installato con altri mezzi, deve essere rimosso anche dallo stesso meccanismo.</span><span class="sxs-lookup"><span data-stu-id="026ad-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="026ad-120">Per installare un certificato:</span><span class="sxs-lookup"><span data-stu-id="026ad-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="026ad-121">Connettere il HoloLens 2 a un PC.</span><span class="sxs-lookup"><span data-stu-id="026ad-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="026ad-122">Inserire il file del certificato che si vuole installare in un percorso nel HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="026ad-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="026ad-123">Passare a **Impostazioni App > Aggiorna & certificati > sicurezza** e selezionare Installa un certificato.</span><span class="sxs-lookup"><span data-stu-id="026ad-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="026ad-124">Fare **clic su Importa** file e passare al percorso in cui è stato salvato il certificato.</span><span class="sxs-lookup"><span data-stu-id="026ad-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="026ad-125">Selezionare **Store Location (Posizione punto vendita).**</span><span class="sxs-lookup"><span data-stu-id="026ad-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="026ad-126">Selezionare **Archivio certificati.**</span><span class="sxs-lookup"><span data-stu-id="026ad-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="026ad-127">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="026ad-127">Click **Install**.</span></span>

<span data-ttu-id="026ad-128">Il certificato dovrebbe ora essere installato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="026ad-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="026ad-129">Per rimuovere un certificato:</span><span class="sxs-lookup"><span data-stu-id="026ad-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="026ad-130">Sebbene sia possibile visualizzare i certificati distribuiti da MDM in Gestione certificati, non è possibile disinstallarli in Gestione certificati.</span><span class="sxs-lookup"><span data-stu-id="026ad-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="026ad-131">È necessario disinstallarli tramite MDM.</span><span class="sxs-lookup"><span data-stu-id="026ad-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="026ad-132">Passare a **Impostazioni App > aggiornamento e certificati > sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="026ad-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="026ad-133">Cercare il certificato in base al nome nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="026ad-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="026ad-134">Selezionare il certificato.</span><span class="sxs-lookup"><span data-stu-id="026ad-134">Select the certificate.</span></span>
1. <span data-ttu-id="026ad-135">Fare clic **su Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="026ad-135">Click **Remove**</span></span>
1. <span data-ttu-id="026ad-136">Selezionare **Sì** quando viene richiesta la conferma.</span><span class="sxs-lookup"><span data-stu-id="026ad-136">Select **Yes** when prompted for confirmation.</span></span>



![Visualizzatore certificati nell'app Impostazioni in Certificati](images/certificate-viewer-device.jpg)

![Immagine che illustra come usare l'interfaccia utente del certificato per installare un certificato in Impostazioni.](images/certificate-device-install.jpg)
