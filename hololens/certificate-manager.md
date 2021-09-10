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
ms.openlocfilehash: 8b1869e786e3f3324494cecbfd596f61811e1893
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427055"
---
# <a name="certificate-manager"></a>Gestione certificati

- Strumenti di controllo, diagnosi e convalida migliorati per la sicurezza e la conformità dei dispositivi tramite il nuovo gestore di certificati. Questa funzionalità consente di distribuire, risolvere i problemi e convalidare i certificati su larga scala in ambienti commerciali.

In Windows Holographic, versione 20H2, viene aggiunto un gestore di certificati nell'app HoloLens 2 Impostazioni. Passare a **Impostazioni > Aggiornare & certificati > sicurezza**. Questa funzionalità offre un modo semplice e semplice per visualizzare, installare e rimuovere i certificati nel dispositivo. Con il nuovo gestore di certificati, gli amministratori e gli utenti hanno ora migliorato gli strumenti di controllo, diagnosi e convalida per garantire che i dispositivi rimangano sicuri e conformi. 

-   **Controllo:** Possibilità di convalidare che un certificato sia stato distribuito correttamente o di confermare che è stato rimosso in modo appropriato. 
-   **Diagnosi:** Quando si verificano problemi, la convalida dell'esistenza dei certificati appropriati nel dispositivo consente di risparmiare tempo e facilita la risoluzione dei problemi. 
-   **Convalida:** La verifica che un certificato venga utilizzato per lo scopo previsto e funzioni può risparmiare molto tempo, in particolare negli ambienti commerciali prima di distribuire i certificati su larga scala.

Per trovare rapidamente un certificato specifico nell'elenco, sono disponibili opzioni per ordinare in base al nome, all'archivio o alla data di scadenza. Gli utenti possono anche cercare direttamente un certificato. Per visualizzare le proprietà dei singoli certificati, selezionare il certificato e fare clic su **Info**. 

L'installazione del certificato supporta attualmente i file con estensione cer e crt. I proprietari dei dispositivi possono installare i certificati nel computer locale e nell'utente corrente.  tutti gli altri utenti possono eseguire l'installazione solo in Utente corrente.

## <a name="to-install-a-certificate"></a>Per installare un certificato: 

1.  Connessione il HoloLens 2 a un PC.
1.  Inserire il file del certificato che si vuole installare in un percorso nel HoloLens 2.
1.  Passare a **Impostazioni App > Update & Security > Certificates** e selezionare Install a certificate (Installa un certificato).
1.  Fare **clic su Importa** file e passare al percorso in cui è stato salvato il certificato.
1.  Selezionare **Store Location (Posizione punto vendita).**
1.  Selezionare **Archivio certificati.**
1.  Fare clic su **Installa**.

Il certificato dovrebbe ora essere installato nel dispositivo.

![Visualizzatore certificati nell'app Impostazioni in Certificati.](images/certificate-viewer-device.jpg)

![Immagine che illustra come usare l'interfaccia utente del certificato per installare un certificato in Impostazioni.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Per rimuovere un certificato:

> [!WARNING]
> Usando Gestione certificati, gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia Impostazioni utente. Se un certificato è stato installato in altri mezzi, deve anche essere rimosso dallo stesso meccanismo e non può essere rimosso da Gestione certificati. Sebbene sia possibile visualizzare i certificati distribuiti da MDM in Gestione certificati, non è possibile disinstallarli in Gestione certificati. È necessario disinstallarli tramite MDM.

1. Passare a Impostazioni **App > Update and Security > Certificates**.
1. Cercare il certificato in base al nome nella casella di ricerca.
1. Selezionare il certificato.
1. Fare clic **su Rimuovi**
1. Selezionare **Sì** quando viene richiesta la conferma.

