---
title: Usare il clicker HoloLens
description: Questo articolo illustra come usare il clicker HoloLens, inclusi l'associazione, il caricamento e il ripristino del clicker.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 13b86c049ba8bb6ed67be202609d27c8d47ffc53
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829474"
---
# Usare il clicker HoloLens (prima generazione)

Il clicker è stato progettato specificamente per i dispositivi HoloLens (prima generazione) e offre una diversa modalità di interazione con gli ologrammi. È fornito con HoloLens (prima generazione), in una confezione distinta.

Usare il clicker invece dei movimenti delle mani per selezionare, scorrere, spostare e ridimensionare le app.

## Hardware e associazione del clicker

Il clicker HoloLens (prima generazione) è dotato di un indicatore luminoso e di un passante per le dita per facilitare la tenuta.

![Il clicker HoloLens](images/use-hololens-clicker-1.png)

### Indicatori luminosi del clicker

Ecco cosa indicano le luci sul clicker.

- **Bianco lampeggiante**. Il clicker è in modalità associazione.
- **Bianco lampeggiante rapido**. L’associazione ha avuto esito positivo.
- **Bianco fisso**. Il clicker è in carica.
- **Giallo lampeggiante**. La batteria è quasi scarica.
- **Giallo fisso**. Si è verificato un errore nel clicker ed è necessario riavviarlo. Fare clic sul pulsante di abbinamento e tenere premuto per 15 secondi.

### Associare il clicker al dispositivo HoloLens (prima generazione)

1. Usare la mano a fiore per passare ad **Avvia**, poi selezionare **Impostazioni** > **Dispositivi** e verificare che la funzione Bluetooth sia attiva.
1. Premere e tenere premuto il pulsante di associazione sul clicker finché lo stato della luce non sarà bianco fisso.
1. Nella schermata di associazione, seleziona **Clicker** > **Associa**.

### Caricare il clicker

Quando la batteria è quasi scarica, l'indicatore lampeggerà di colore giallo. Collegare il cavo micro USB a un alimentatore USB per caricare il dispositivo.

## Usare il clicker con HoloLens (prima generazione)

### Tenere il clicker

Per indossare il clicker, inserire il passante sul dito anulare o medio in modo che le porte micro USB siano rivolte verso il polso. Appoggiare il pollice nella rientranza.

![Come tenere il clicker](images/use-hololens-clicker-2.png)

### Movimenti del clicker

I movimenti dei clicker sono piccole rotazioni del polso, non i movimenti ampi usati per le mani in HoloLens. HoloLens riconosce i movimenti e fa clic anche quando il clicker si trova all'esterno dell’[inquadratura del movimento](hololens1-basic-usage.md), in modo che sia possibile tenerlo premuto nella posizione più comoda.

- **Selezionare**. Per selezionare un ologramma, un pulsante o un altro elemento, fissarlo e poi fare clic.

- **Fare clic e tenere**. Fare clic e tenere premuto il pollice verso il basso sul pulsante per eseguire le stesse operazioni di tocco e tenere premuto, ad esempio muovere o ridimensionare un ologramma.

- **Scorrere**. Nella barra dell'app selezionare **Strumento Scorri**. Fare clic e tenere premuto, poi ruotare il clicker verso l'alto, il basso, a sinistra o a destra. Per scorrere più rapidamente, allontanare la mano dal centro dello strumento di scorrimento.

- **Zoom**. Nella barra dell'app selezionare **Strumento Zoom**. Fare clic e tenere premuto, poi ruotare il clicker verso l’alto per fare zoom avanti o verso il basso per fare zoom indietro.

> [!TIP]
> Per fare zoom avanti o indietro quando si usa Microsoft Edge, fissare la pagina e fare doppio clic.

## Riavviare o ripristinare il clicker

Ecco cosa fare quando il clicker HoloLens non risponde o non funziona bene.

### Riavviare il clicker

Usare la punta di una penna per premere e tenere premuto il pulsante di associazione. Contemporaneamente, fare clic e tenere premuto il clicker per 15 secondi. Se il clicker era già associato con HoloLens, rimarrà associato dopo il riavvio.

Se il clicker non si attiva o avvia, provare a caricarlo usando il caricabatterie HoloLens. Se la batteria è quasi scarica, potrebbe essere necessario attendere alcuni minuti prima che la luce bianca si accenda.

### Associare nuovamente il clicker

Selezionare **Impostazioni** > **Dispositivi** e poi selezionare il clicker. Selezionare **Rimuovi**, attendere alcuni secondi, poi associare il clic nuovamente.

### Ripristinare il clicker

Se il riavvio o la riassociazione non riesce a risolvere il problema, Windows Device Recovery Tool consente il ripristino. Il processo di ripristino può richiedere del tempo e installerà la versione più recente del software del clicker. Per usare lo strumento, è necessario un computer che esegue Windows 10 o versione successiva con almeno 4 GB di spazio di archiviazione libero.

Per ripristinare il clicker:

1. Scarica e installa [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) sul tuo PC.
1. Connettere il clicker al computer usando il cavo micro USB fornito insieme a HoloLens.
1. Esegui Windows Device Recovery Tool e segui le istruzioni.

Se il clicker non viene rilevato automaticamente, selezionare **Il mio dispositivo non è stato rilevato** e seguire le istruzioni per attivare la modalità di ripristino del dispositivo.
