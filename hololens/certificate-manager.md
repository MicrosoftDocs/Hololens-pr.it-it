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
# <a name="certificate-manager"></a>Gestione certificati

- Strumenti di controllo, diagnosi e convalida migliorati per la sicurezza e la conformità dei dispositivi tramite il nuovo Gestore certificati. Questa funzionalità consente di distribuire, risolvere i problemi e convalidare i certificati su larga scala in ambienti commerciali.

In Windows Holographic versione 20H2 viene aggiunto un gestore di certificati nell'app HoloLens 2 impostazioni. Passare a **Impostazioni > aggiornamento & sicurezza > certificati**. Questa funzionalità offre un modo semplice e semplice per visualizzare, installare e rimuovere i certificati nel dispositivo. Con il nuovo gestore di certificati, gli amministratori e gli utenti hanno ora migliorato gli strumenti di controllo, diagnosi e convalida per garantire che i dispositivi rimangano sicuri e conformi. 

-   **Controllo:** Possibilità di convalidare la corretta distribuzione di un certificato o di verificare che sia stato rimosso in modo appropriato. 
-   **Diagnosi:** Quando si verificano problemi, la convalida dell'esistenza dei certificati appropriati nel dispositivo consente di risparmiare tempo e di risolvere i problemi. 
-   **Convalida:** La verifica che un certificato sia utile e funzionale può risparmiare tempo significativo, in particolare negli ambienti commerciali prima di distribuire i certificati su larga scala.

Per trovare rapidamente un certificato specifico nell'elenco, sono disponibili opzioni per ordinare in base al nome, all'archivio o alla data di scadenza. Gli utenti possono anche cercare direttamente un certificato. Per visualizzare le singole proprietà del certificato, selezionare il certificato e fare clic su **Info**. 

L'installazione del certificato attualmente supporta i file con estensione cer e crt. I proprietari dei dispositivi possono installare i certificati nel computer locale e nell'utente corrente.  tutti gli altri utenti possono eseguire l'installazione solo in Utente corrente. Gli utenti possono rimuovere solo i certificati installati direttamente dall'interfaccia utente delle impostazioni. Se un certificato è stato installato con altri mezzi, deve essere rimosso anche dallo stesso meccanismo.

## <a name="to-install-a-certificate"></a>Per installare un certificato: 

1.  Connettere il HoloLens 2 a un PC.
1.  Inserire il file del certificato che si vuole installare in un percorso nel HoloLens 2.
1.  Passare a **Impostazioni App > Aggiorna & certificati > sicurezza** e selezionare Installa un certificato.
1.  Fare **clic su Importa** file e passare al percorso in cui è stato salvato il certificato.
1.  Selezionare **Store Location (Posizione punto vendita).**
1.  Selezionare **Archivio certificati.**
1.  Fare clic su **Installa**.

Il certificato dovrebbe ora essere installato nel dispositivo.

## <a name="to-remove-a-certificate"></a>Per rimuovere un certificato: 
>[!WARNING]
> Sebbene sia possibile visualizzare i certificati distribuiti da MDM in Gestione certificati, non è possibile disinstallarli in Gestione certificati. È necessario disinstallarli tramite MDM.
1. Passare a **Impostazioni App > aggiornamento e certificati > sicurezza**.
1. Cercare il certificato in base al nome nella casella di ricerca.
1. Selezionare il certificato.
1. Fare clic **su Rimuovi**
1. Selezionare **Sì** quando viene richiesta la conferma.



![Visualizzatore certificati nell'app Impostazioni in Certificati](images/certificate-viewer-device.jpg)

![Immagine che illustra come usare l'interfaccia utente del certificato per installare un certificato in Impostazioni.](images/certificate-device-install.jpg)
