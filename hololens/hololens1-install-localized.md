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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427181"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Installare le versioni localizzate HoloLens (prima generazione)

Per passare alla versione cinese o giapponese di HoloLens, è necessario usare lo strumento di ripristino del dispositivo Windows (WDRT) per scaricare la build per la lingua in un PC e quindi installarla nel HoloLens.

> [!IMPORTANT]
> L'uso di WDRT per installare le build in cinese o giapponese di HoloLens elimina i dati esistenti, ad esempio i file e le impostazioni personali, dal HoloLens. 

1. Nel PC scaricare e installare [l'Windows device recovery tool (WDRT)](https://support.microsoft.com/help/12379).
1. Scaricare il pacchetto per la lingua desiderata nel PC: [cinese semplificato](https://aka.ms/hololensdownload-ch) o [giapponese.](https://aka.ms/hololensdownload-jp)
1. Al termine del download, **selezionare** Esplora file  >  **Download**. Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.
1. Connessione il HoloLens al PC usando il cavo micro USB fornito. Anche se si usano altri cavi per connettere il HoloLens, questo funziona meglio.
1. Dopo che lo strumento rileva automaticamente il HoloLens, selezionare il Microsoft HoloLens riquadro.
1. Nella schermata successiva selezionare **Selezione** pacchetto manuale e selezionare il file di installazione che si trova nella cartella   decompressa nel passaggio 4. Cercare un file con estensione ".ffu". 
1. Selezionare **Installa software** e seguire le istruzioni. 
1. Dopo l'installazione della build, HoloLens l'installazione automatica. Posizionare il dispositivo e seguire le istruzioni di configurazione. 

Al termine dell'installazione, passare Impostazioni Update & Security Windows Programma Insider e verificare di essere configurati per ricevere le build di anteprima  >    >  più recenti. Analogamente alle build di anteprima in lingua inglese, Windows Programma Insider le versioni cinese e giapponese di HoloLens aggiornate con le build di anteprima più recenti.

> [!NOTE]
>  
> - Non è possibile usare l'app Impostazioni per modificare la lingua del sistema tra inglese, giapponese e cinese. Il flashing di una nuova build è l'unico modo supportato per modificare la lingua del sistema del dispositivo.
> - Sebbene sia possibile usare la tastiera Pinyin su schermo per immettere testo in cinese semplificato o giapponese, l'uso di una tastiera hardware Bluetooth per digitare testo in cinese semplificato o giapponese non è attualmente supportato.  Tuttavia, nel HoloLens cinese o giapponese è possibile continuare a usare una tastiera Bluetooth per digitare in inglese (per attivare o disattivare una tastiera hardware per digitare in inglese, premere il tasto ~).
