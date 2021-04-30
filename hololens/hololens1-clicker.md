---
title: Usare il clicker HoloLens
description: Questo articolo illustra come usare il clicker HoloLens, tra cui l'associazione dei clic, l'addebito e il ripristino.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310002"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>Usare il clicker HoloLens (prima generazione)

Il clicker è stato progettato specificamente per HoloLens (prima generazione) e offre un altro modo per interagire con gli ologrammi. Viene fornito con HoloLens (prima generazione), in una casella separata.

Usarlo al posto dei movimenti della mano per selezionare, scorrere, spostare e ridimensionare le app.

## <a name="clicker-hardware-and-pairing"></a>Hardware e associazione clicker

Il clicker HoloLens (prima generazione) ha un ciclo di dita per semplificare la presa e una luce indicatore.

![Clicker di HoloLens](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>Indicatori indicatore del clicker

Ecco cosa significano le luci sul clicker.

- **Lampeggiante bianco**. Il clicker è in modalità di associazione.
- **Bianco lampeggiante veloce.** Associazione riuscita.
- **Bianco a tinta** unita. Il clicker sta ricaricando.
- **Lampeggiante ambra**. La batteria è scarica.
- **Ambra solida.** Il clicker ha rilevato un errore ed è necessario riavviarlo. Quando si preme il pulsante di associazione, fare clic e tenere premuto per 15 secondi.

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>Associare il clicker a HoloLens (prima generazione)

1. Usare il movimento bloom per passare a **Start,** quindi selezionare **Impostazioni**  >  **Dispositivi** e verificare che Bluetooth sia on.
1. Sul clicker premere e tenere premuto il pulsante di associazione fino a quando la luce di stato lampeggia bianca.
1. Nella schermata di associazione selezionare **Coppia clicker**  >  .

### <a name="charge-the-clicker"></a>Addebitare il clicker

Quando la batteria del clicker è scarica, l'indicatore della batteria lampeggia ambrato. Collegare il cavo MICRO USB a un alimentatore USB per caricare il dispositivo.

## <a name="use-the-clicker-with-hololens-1st-gen"></a>Usare il clicker con HoloLens (prima generazione)

### <a name="hold-the-clicker"></a>Tenere premuto il pulsante

Per posizionare il clicker, far scorrere il ciclo sull'anello o sul dito medio in modo che la porta MICRO USB si volti verso il polso. Posizionare il pollice nel rientro.

![Come tenere premuto il clicker](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>Movimenti del clicker

I movimenti del clicker sono piccole rotazioni del polso, non i movimenti più grandi usati per i movimenti della mano di HoloLens. HoloLens riconosce i movimenti e i clic anche se [](hololens1-basic-usage.md)il clicker si trova all'esterno del frame del movimento, quindi è possibile tenere il clicker nella posizione più comoda.

- **Selezionare**. Per selezionare un ologramma, un pulsante o un altro elemento, guardarlo e quindi fare clic.

- **Fare clic e tenere premuto**. Fare clic e tenere premuto il cursore sul pulsante per eseguire alcune delle stesse operazioni che si farebbe con tocco e tenere premuto, ad esempio spostare o ridimensionare un ologramma.

- **Scorrere**. Sulla barra dell'app selezionare **Strumento di scorrimento.** Fare clic e tenere premuto, quindi ruotare il clicker verso l'alto, verso il basso, a sinistra o a destra. Per scorrere più velocemente, spostare la mano più lontano dal centro dello strumento di scorrimento.

- **Zoom**. Sulla barra dell'app selezionare **Strumento zoom.** Fare clic e tenere premuto, quindi ruotare il clicker verso l'alto per fare zoom avanti o verso il basso per fare zoom indietro.

> [!TIP]
> Per fare zoom avanti o indietro quando si usa Microsoft Edge, osservare una pagina e fare doppio clic.

## <a name="restart-or-recover-the-clicker"></a>Riavviare o ripristinare il clicker

Ecco alcuni aspetti da provare se il clicker HoloLens non risponde o non funziona correttamente.

### <a name="restart-the-clicker"></a>Riavviare il clicker

Usare la punta di una penna per tenere premuto il pulsante di associazione. Allo stesso tempo, fare clic e tenere premuto il clic per 15 secondi. Se il clicker è già stato associato a HoloLens, rimarrà associato dopo il riavvio.

Se il clicker non si attiva o riavvia, prova ad addebitarlo usando il charger HoloLens. Se la batteria è molto bassa, l'attivazione della luce dell'indicatore bianco potrebbe richiedere alcuni minuti.

### <a name="re-pair-the-clicker"></a>Riasssare il clicker

Selezionare **Impostazioni**  >  **Dispositivi** e selezionare il clicker. Selezionare **Rimuovi**, attendere alcuni secondi, quindi associare di nuovo il clicker.

### <a name="recover-the-clicker"></a>Ripristinare il clicker

Se il riavvio e la ria associazione del clicker non consentono di risolvere il problema, lo strumento Ripristino dispositivi Windows consente di ripristinarlo. Il processo di ripristino potrebbe richiedere tempo e installerà la versione più recente del software clicker. Per usare lo strumento, è necessario un computer che esegue Windows 10 o versione successiva con almeno 4 GB di spazio di archiviazione disponibile.

Per ripristinare il clicker:

1. Scaricare e installare windows [Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) nel computer.
1. Connettere il clicker al computer usando il cavo MICRO USB fornito con HoloLens.
1. Eseguire lo strumento Ripristino dispositivi Windows e seguire le istruzioni.

Se il clicker non viene rilevato automaticamente, selezionare Il dispositivo **non** è stato rilevato e seguire le istruzioni per impostare la modalità di ripristino del dispositivo.
