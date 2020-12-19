---
title: Commenti e suggerimenti
description: È possibile creare feedback per gli sviluppatori di realtà miste HoloLens e Windows usando l'hub feedback.
ms.assetid: b9b24c72-ff86-44a9-b30d-dd76c49479a9
author: mattzmsft
ms.author: mazeller
ms.date: 12/17/2020
ms.custom:
- CI 116157
- CSSTroubleshooting
audience: ITPro
ms.prod: hololens
ms.topic: article
keywords: feedback, bug, problema, errore, risoluzione dei problemi, guida
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f8704b7e1b75cd08bc282eb0c2df22b8266cb9fd
ms.sourcegitcommit: e44f1f1ab708e5bd6c4c5b85ec449db2bc798be2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/18/2020
ms.locfileid: "11237276"
---
# Feedback per HoloLens

Usa l'hub feedback per comunicare le caratteristiche che ami, le caratteristiche che puoi eseguire senza e il modo migliore. Il team di progettazione USA lo stesso meccanismo internamente per tenere traccia e correggere i bug, quindi usa hub feedback per segnalare eventuali bug visualizzati. Stiamo ascoltando!

Hub di feedback è un ottimo modo per avvisare il team di ingegneri per i bug e per assicurarsi che gli aggiornamenti futuri siano più sani e sempre più esenti da bug. Tuttavia, l'hub di feedback non offre una risposta. Se hai bisogno di assistenza immediata, invia il tuo feedback, prendi nota del riepilogo che hai fornito per il tuo feedback e quindi segui il [supporto di HoloLens](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f) -usa la caratteristica **Condividi** nell'hub feedback per condividere un collegamento diretto all'URL. L'hub di feedback riceve molti dati ogni giorno: l'URL consente di identificare rapidamente il feedback.

> [!NOTE]  
>  
> - Verificare di avere la versione corrente dell'hub feedback. A tale scopo, selezionare **Avvia**  >  **Microsoft Store**e quindi selezionare i puntini di sospensione (**...**). Quindi, selezionare **download e aggiornamenti per**  >  **ottenere gli aggiornamenti**.  
>  
> - Per ottenere i dati migliori per la risoluzione dei problemi, è consigliabile impostare la telemetria del dispositivo su **facoltativo**. Puoi impostare questo valore durante l'esperienza di out-of-box (OOBE) oppure usando l'app Impostazioni. Per eseguire questa operazione usando impostazioni, selezionare **Avvia**  >  **Impostazioni**per la diagnostica delle  >  ****  >  **app**  >  **sulla**privacy.

## Usare l'hub di feedback

1. Usare il gesto **Start** per aprire il menu **Start** e quindi selezionare **Hub feedback**. L'app si apre nell'ambiente.

   ![App feedback nel menu Start di HoloLens](./images/hololens2-feedbackhub-tile.png)
   > [!NOTE]  
   > Se non Vedi **Hub di feedback**, seleziona **tutte le app** per visualizzare l'elenco completo delle app nel dispositivo.

1. Per verificare se un altro utente ha ricevuto un feedback simile, immettere alcune parole chiave relative all'argomento nella casella di ricerca **feedback** .
1. Se si trova un feedback simile, selezionarlo, aggiungere eventuali informazioni aggiuntive nella casella **Scrivi un commento** e quindi selezionare **votazione**.
1. Se non si trovano commenti simili, selezionare **Aggiungi nuovo feedback**.

   ![Aggiungere un nuovo feedback](./images/hololens-feedback-1.png)

1. In **Riepilogo del feedback**, immettere un breve riepilogo del feedback. Aggiungere quindi i dettagli nella casella **spiega in altro dettaglio** . Più dettagli fornisci, ad esempio come riprodurre il problema e l'effetto che ha, più è utile il feedback. Al termine, selezionare **Avanti**.

1. Selezionare un argomento da **scegliere una categoria**e quindi selezionare una sottocategoria da **selezionare una**sottocategoria. La tabella seguente descrive le categorie disponibili nella categoria olografica di Windows.

   > [!NOTE]  
   > **Clienti commerciali**: per segnalare un bug correlato a MDM, provisioning o qualsiasi altro aspetto della gestione dei dispositivi, selezionare la categoria **gestione aziendale** e la sottocategoria **dispositivo** .

   |Categoria |Descrizione |
   | --- | --- |
   |Tracciamento oculare |Feedback sul rilevamento degli occhi, l'accesso a iride o la calibrazione. |
   |Precisione, stabilità e affidabilità degli ologrammi |Feedback sul modo in cui gli ologrammi compaiono nello spazio. |
   |Avvio, posizionamento, modifica e chiusura delle app |Feedback sull'avvio o l'arresto di app 2D o 3D. |
   |Miracast |Feedback su Miracast. |
   |Spazi e persistenza |Feedback su come HoloLens riconosce gli spazi e mantiene gli ologrammi nello spazio. |
   |Menu Start ed elenco Tutte le app |Feedback sul menu **Start** e sull'elenco tutte le app. |
   |Mappatura di superfici |Feedback sul mapping delle superfici. |
   |Acquisizione di foto e registrazione di video |Feedback sulle acquisizioni di realtà miste. |
   |Riproduzione di ologrammi video |Feedback sulla riproduzione olografica video. |
   |Tutti gli altri problemi |Tutti gli altri problemi. |

1. Potrebbe essere richiesto di cercare un feedback simile. Se il problema è simile a quello di altri utenti, selezionare il feedback. In caso contrario, seleziona **nuovo feedback** e quindi scegli **Avanti**.

1. Se richiesto, selezionare la descrizione migliore del problema.

1. Allegare i dati rilevanti al feedback o riprodurre il problema. È possibile selezionare una delle opzioni seguenti:

   - **Allegare uno screenshot**. Selezionare questa opzione per allegare uno screenshot che illustra la situazione che si sta descrivendo.
   - **Allegare un file**. Selezionare questa opzione per allegare i file di dati. Se sono presenti file rilevanti per il problema o che potrebbero aiutarci a riprodurre il problema, allegarli.
   - **Ricreare il problema**. Selezionare questa opzione se si riesce a riprodurre il problema manualmente. Dopo aver selezionato **ricrea il problema**, eseguire le operazioni seguenti:  

     1. Selezionare **Includi dati** e verificare che siano elencati i tipi di dati più rilevanti. Nella maggior parte dei casi, le selezioni predefinite si basano sulla categoria e sottocategoria selezionata per il feedback.  
     1. Selezionare **Avvia registrazione**.

     1. Riprodurre il problema. Non preoccuparti se questo significa che devi inserire un'app immersiva. Al termine, si tornerà alla pagina feedback.
     1. Selezionare **Interrompi registrazione**. Dopo l'interruzione della registrazione, è possibile visualizzare i dati allegati al feedback per il team di progettazione.

1. Verificare di avere una connessione Internet attiva in modo da poter ricevere il feedback. Selezionare **Invia**e termina.

1. Usare il pulsante **Condividi** per condividere l'URL ridotto con il supporto Microsoft o i colleghi.