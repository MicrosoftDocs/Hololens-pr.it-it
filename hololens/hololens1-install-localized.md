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
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661821"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Installare le versioni localizzate HoloLens (prima generazione)

Per passare alla versione cinese o giapponese di HoloLens, è necessario usare lo strumento di ripristino dei dispositivi di Windows (WDRT) per scaricare la build per la lingua in un PC e quindi installarla nel HoloLens.

> [!IMPORTANT]
> L'uso di WDRT per installare le build in cinese o giapponese di HoloLens elimina i dati esistenti, ad esempio i file e le impostazioni personali, dal HoloLens. 

1. Nel PC scaricare e installare lo [strumento di ripristino Windows dispositivo (WDRT).](https://support.microsoft.com/help/12379)
1. Scaricare il pacchetto per la lingua desiderata nel PC: [cinese semplificato](https://aka.ms/hololensdownload-ch) o [giapponese.](https://aka.ms/hololensdownload-jp)
1. Al termine del download, **selezionare** Esplora file  >  **Download**. Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.
1. Connessione il HoloLens al PC usando il cavo micro USB fornito. Anche se si usano altri cavi per connettere i HoloLens, questo funziona meglio.
1. Dopo che lo strumento ha rilevato automaticamente HoloLens, selezionare il Microsoft HoloLens riquadro.
1. Nella schermata successiva selezionare Selezione manuale **del** pacchetto e selezionare il file di installazione che si trova nella cartella   decompressa nel passaggio 4. Cercare un file con estensione ".ffu". 
1. Selezionare **Installa software** e seguire le istruzioni. 
1. Dopo l'installazione della build, HoloLens automaticamente l'installazione. Posizionare il dispositivo e seguire le istruzioni di configurazione. 

Al termine dell'installazione, passare **a Impostazioni** Update & Security Windows Programma Insider e verificare di essere configurati per ricevere le build di anteprima più  >    >  recenti. Analogamente alle build di anteprima in lingua inglese, il Windows Programma Insider mantiene aggiornate le versioni in cinese e giapponese HoloLens aggiornate con le build di anteprima più recenti.

> [!NOTE]
>  
> - Non è possibile usare l'app Impostazioni per modificare la lingua del sistema tra inglese, giapponese e cinese. Il flashing di una nuova build è l'unico modo supportato per modificare la lingua del sistema del dispositivo.
> - Anche se è possibile usare la tastiera Pinyin su schermo per immettere testo in cinese semplificato o giapponese, l'uso di una tastiera hardware Bluetooth per digitare testo cinese semplificato o giapponese non è attualmente supportato.  Tuttavia, nell'HoloLens cinese o giapponese è possibile continuare a usare una tastiera Bluetooth per digitare l'inglese . Per attivare o disattivare la digitazione in inglese di una tastiera hardware, premere il tasto ~.
