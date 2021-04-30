---
title: Installare le versioni localizzate di HoloLens
description: Informazioni su come installare le versioni localizzate di HoloLens (prima generazione), incluse le versioni in cinese e giapponese.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310062"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="deefd-103">Installare le versioni localizzate di HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="deefd-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="deefd-104">Per passare alla versione cinese o giapponese di HoloLens, è necessario usare windows Device Recovery Tool (WDRT) per scaricare la build per la lingua in un PC e quindi installarla in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="deefd-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="deefd-105">L'uso di WDRT per installare le build in cinese o giapponese di HoloLens elimina i dati esistenti, ad esempio file personali e impostazioni, da HoloLens.</span><span class="sxs-lookup"><span data-stu-id="deefd-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="deefd-106">Nel PC scaricare e installare [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="deefd-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="deefd-107">Scaricare il pacchetto per la lingua desiderata nel PC: [cinese semplificato](https://aka.ms/hololensdownload-ch) o [giapponese.](https://aka.ms/hololensdownload-jp)</span><span class="sxs-lookup"><span data-stu-id="deefd-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="deefd-108">Al termine del download, **selezionare** Esplora file  >  **Download**.</span><span class="sxs-lookup"><span data-stu-id="deefd-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="deefd-109">Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="deefd-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="deefd-110">Connettere HoloLens al PC usando il cavo micro USB fornito.</span><span class="sxs-lookup"><span data-stu-id="deefd-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="deefd-111">Anche se si usano altri cavi per connettere HoloLens, questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="deefd-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="deefd-112">Dopo che lo strumento rileva automaticamente HoloLens, selezionare il Microsoft HoloLens riquadro.</span><span class="sxs-lookup"><span data-stu-id="deefd-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="deefd-113">Nella schermata successiva selezionare **Selezione** pacchetto manuale e selezionare il file di installazione che si trova nella cartella   decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="deefd-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="deefd-114">Cercare un file con estensione ".ffu".</span><span class="sxs-lookup"><span data-stu-id="deefd-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="deefd-115">Selezionare **Installa software** e seguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="deefd-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="deefd-116">Dopo l'installazione della build, viene avviata automaticamente l'installazione di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="deefd-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="deefd-117">Posizionare il dispositivo e seguire le istruzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="deefd-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="deefd-118">Al termine dell'installazione, passare a Impostazioni Aggiornamento & Sicurezza Programma Windows Insider e verificare di essere configurati per ricevere le build di  >    >  anteprima più recenti.</span><span class="sxs-lookup"><span data-stu-id="deefd-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="deefd-119">Come le build di anteprima in lingua inglese, Programma Windows Insider le versioni in cinese e giapponese di HoloLens aggiornate con le build di anteprima più recenti.</span><span class="sxs-lookup"><span data-stu-id="deefd-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="deefd-120">Non è possibile usare l'app Impostazioni per modificare la lingua del sistema tra inglese, giapponese e cinese.</span><span class="sxs-lookup"><span data-stu-id="deefd-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="deefd-121">Il flashing di una nuova build è l'unico modo supportato per modificare la lingua del sistema del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="deefd-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="deefd-122">Anche se è possibile usare la tastiera Pinyin su schermo per immettere testo cinese semplificato o giapponese, l'uso di una tastiera hardware Bluetooth per digitare testo cinese semplificato o giapponese non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="deefd-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="deefd-123">Tuttavia, su HoloLens cinese o giapponese, puoi continuare a usare una tastiera Bluetooth per digitare l'inglese (per attivare o disattivare la digitazione di una tastiera hardware in inglese, premi il tasto ~).</span><span class="sxs-lookup"><span data-stu-id="deefd-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
