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
# Gestione certificati

- Strumenti di controllo, diagnosi e convalida migliorati per la sicurezza e la conformità dei dispositivi tramite il nuovo gestore di certificati. Questa funzionalità consentirà di distribuire, risolvere i problemi e convalidare i certificati in scala in ambienti commerciali.

In Windows olografico, versione 20H2, aggiungiamo un gestore di certificati nell'app impostazioni di HoloLens 2. Accedere a **impostazioni > aggiornare i certificati di > di sicurezza &**. Questa funzionalità consente di visualizzare, installare e rimuovere certificati nel dispositivo in modo semplice e intuitivo. Con il nuovo gestore di certificati, gli amministratori e gli utenti hanno ora strumenti di controllo, diagnosi e convalida migliorati per garantire che i dispositivi rimangano sicuri e conformi. 

-   **Controllo:** Possibilità di verificare che un certificato sia distribuito correttamente o per verificare che sia stato rimosso in modo appropriato. 
-   **Diagnosi:** In caso di problemi, verifica che i certificati appropriati esistano nel dispositivo per risparmiare tempo e consente di risolvere i problemi. 
-   **Convalida:** Verificare che un certificato serva lo scopo previsto ed è funzionale, può risparmiare tempo significativo, in particolare in ambienti commerciali prima di distribuire i certificati su scala più ampia.

Per trovare rapidamente un certificato specifico nell'elenco, sono disponibili opzioni per ordinare in base al nome, all'archivio o alla data di scadenza. Gli utenti possono anche cercare direttamente un certificato. Per visualizzare le singole proprietà del certificato, selezionare il certificato e fare clic su **informazioni**. 

L'installazione del certificato supporta attualmente i file con estensione CER e CRT. I proprietari di dispositivi possono installare i certificati nel computer locale e nell'utente corrente;  tutti gli altri utenti possono essere installati solo nell'utente corrente. Gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia utente delle impostazioni. Se un certificato è stato installato con altri mezzi, deve essere rimosso anche dallo stesso meccanismo.

## Per installare un certificato: 

1.  Connettere il HoloLens 2 a un PC.
1.  Posizionare il file di certificato che si vuole installare in un percorso di HoloLens 2.
1.  Passare all' **app impostazioni > aggiornare i certificati di & sicurezza >** e selezionare installa un certificato.
1.  Fare clic su **Importa file** e passare alla posizione in cui è stato salvato il certificato.
1.  Selezionare **posizione archivio**.
1.  Selezionare **archivio certificati**.
1.  Fai clic su **Installa**.

Il certificato dovrebbe ora essere installato nel dispositivo.

## Per rimuovere un certificato: 
1. Passare all' **app impostazioni > aggiornamento e sicurezza > certificati**.
1. Cercare il certificato per nome nella casella di ricerca.
1. Selezionare il certificato.
1. Fare clic su **Rimuovi**
1. Selezionare **Sì** quando viene richiesto di confermare.


![Visualizzatore certificati nell'app impostazioni in Ceritifcates](images/certificate-viewer-device.jpg)

![Immagine che Mostra come usare l'interfaccia utente del certificato per installare un certificato in impostazioni.](images/certificate-device-install.jpg)
