---
title: Installare versioni localizzate di HoloLens
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
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439012"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Installare versioni localizzate di HoloLens (prima generazione)

Per passare alla versione cinese o giapponese di HoloLens, dovrai usare Windows Device Recovery Tool (WDRT) per scaricare la build per la lingua in un PC e quindi installarla nel dispositivo HoloLens.

> [!IMPORTANT]
> Quando si usa WDRT per installare la build cinese o giapponese di HoloLens, vengono eliminati da HoloLens i dati esistenti, ad esempio le impostazioni e i file personali. 

1. Nel PC scarica e installa [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Scarica il pacchetto per la lingua desiderata per il PC: [cinese semplificato](https://aka.ms/hololensdownload-ch) o [giapponese](https://aka.ms/hololensdownload-jp).
1. Al termine del download, seleziona **Esplora file** > **Download**. Fai clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e seleziona **Estrai tutto** > **Estratti** per decomprimerla.
1. Collega HoloLens al PC usando il cavo USB micro con cui è stato fornito il dispositivo. Puoi anche usare altri cavi per collegare il tuo dispositivo HoloLens, ma questo funziona meglio.
1. Dopo che lo strumento avrà rilevato automaticamente il dispositivo HoloLens, seleziona il riquadro Microsoft HoloLens.
1. Nella schermata successiva scegli   **Manual package selection** e seleziona il file di installazione che si trova nella cartella decompressa nel passaggio 4. Cerca un file con estensione "ffu". 
1. Seleziona **Installa software** e segui le istruzioni. 
1. Dopo l'installazione della build, viene avviata automaticamente la configurazione di HoloLens. Indossa il dispositivo e segui le istruzioni per la configurazione. 

Dopo aver completato la configurazione, vai a **Impostazioni** > **Aggiornamento e sicurezza** > **Programma Windows Insider**, quindi verifica di poter ricevere le ultime build in anteprima. Come per le build in anteprima inglese, il Programma Windows Insider mantiene aggiornate le versioni cinese e giapponese di HoloLens con le build in anteprima più recenti.

> [!NOTE]
>  
> - Non puoi usare l'app Impostazioni per modificare la lingua del sistema tra inglese, giapponese e cinese. Il flashing di una nuova build è l'unico modo supportato per cambiare la lingua del sistema del dispositivo.
> - Per immettere testo in cinese semplificato o giapponese, puoi usare la tastiera Pinyin su schermo, mentre l'uso di una tastiera hardware Bluetooth non è supportato al momento.  Nei dispositivi HoloLens cinesi o giapponesi puoi tuttavia continuare a usare una tastiera Bluetooth per digitare in inglese. Per attivare una tastiera hardware per digitare in inglese, premi il tasto ~.
