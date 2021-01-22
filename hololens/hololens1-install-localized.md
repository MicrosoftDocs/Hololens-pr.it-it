---
title: Installare versioni localizzate di HoloLens
description: Informazioni su come installare le versioni localizzate di HoloLens (prima generazione), incluse le versioni in cinese e giapponese.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: af79e42477a3a317dde03a795c442fa31241600d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282977"
---
# <span data-ttu-id="cfae9-103">Installare versioni localizzate di HoloLens (prima generazione)</span><span class="sxs-lookup"><span data-stu-id="cfae9-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="cfae9-104">Per passare alla versione cinese o giapponese di HoloLens, dovrai usare Windows Device Recovery Tool (WDRT) per scaricare la build per la lingua in un PC e quindi installarla nel dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cfae9-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfae9-105">Quando si usa WDRT per installare la build cinese o giapponese di HoloLens, vengono eliminati da HoloLens i dati esistenti, ad esempio le impostazioni e i file personali.</span><span class="sxs-lookup"><span data-stu-id="cfae9-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="cfae9-106">Nel PC scarica e installa [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="cfae9-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="cfae9-107">Scarica il pacchetto per la lingua desiderata per il PC: [cinese semplificato](https://aka.ms/hololensdownload-ch) o [giapponese](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="cfae9-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="cfae9-108">Al termine del download, seleziona **Esplora file** > **Download**.</span><span class="sxs-lookup"><span data-stu-id="cfae9-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="cfae9-109">Fai clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e seleziona **Estrai tutto** > **Estratti** per decomprimerla.</span><span class="sxs-lookup"><span data-stu-id="cfae9-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="cfae9-110">Collega HoloLens al PC usando il cavo USB micro con cui è stato fornito il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cfae9-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="cfae9-111">Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.</span><span class="sxs-lookup"><span data-stu-id="cfae9-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="cfae9-112">Dopo che lo strumento avrà rilevato automaticamente il dispositivo HoloLens, seleziona il riquadro Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cfae9-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="cfae9-113">Nella schermata successiva scegli   **Manual package selection** e seleziona il file di installazione che si trova nella cartella decompressa nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="cfae9-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="cfae9-114">Cerca un file con estensione "ffu".</span><span class="sxs-lookup"><span data-stu-id="cfae9-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="cfae9-115">Seleziona **Installa software** e segui le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="cfae9-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="cfae9-116">Dopo l'installazione della build, viene avviata automaticamente la configurazione di HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cfae9-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="cfae9-117">Indossa il dispositivo e segui le istruzioni per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="cfae9-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="cfae9-118">Dopo aver completato la configurazione, vai a **Impostazioni** > **Aggiornamento e sicurezza** > **Programma Windows Insider**, quindi verifica di poter ricevere le ultime build in anteprima.</span><span class="sxs-lookup"><span data-stu-id="cfae9-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="cfae9-119">Come per le build in anteprima inglese, il Programma Windows Insider mantiene aggiornate le versioni cinese e giapponese di HoloLens con le build in anteprima più recenti.</span><span class="sxs-lookup"><span data-stu-id="cfae9-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="cfae9-120">Non puoi usare l'app Impostazioni per modificare la lingua del sistema tra inglese, giapponese e cinese.</span><span class="sxs-lookup"><span data-stu-id="cfae9-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="cfae9-121">Il flashing di una nuova build è l'unico modo supportato per cambiare la lingua del sistema del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cfae9-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="cfae9-122">Per immettere testo in cinese semplificato o giapponese, puoi usare la tastiera Pinyin su schermo, mentre l'uso di una tastiera hardware Bluetooth non è supportato al momento.</span><span class="sxs-lookup"><span data-stu-id="cfae9-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="cfae9-123">Nei dispositivi HoloLens cinesi o giapponesi puoi tuttavia continuare a usare una tastiera Bluetooth per digitare in inglese. Per attivare una tastiera hardware per digitare in inglese, premi il tasto ~.</span><span class="sxs-lookup"><span data-stu-id="cfae9-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
