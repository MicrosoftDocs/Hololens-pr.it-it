---
title: Trovare, installare e disinstallare applicazioni
description: Il Microsoft Store è l'origine per app e giochi che funzionano con HoloLens.  Altre informazioni su come trovare, installare e disinstallare le app olografiche.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, store, uwp, app, installare
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: bbbc60decb74942bd7930afb04297f78df33028a
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635858"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Trovare, installare e disinstallare applicazioni dal Microsoft Store

Il Microsoft Store è l'origine per le app e i giochi che funzionano con HoloLens. Quando si passa a Store nel HoloLens, tutte le app presenti verranno eseguite in esso.

Le app HoloLens usano la visualizzazione 2D o la visualizzazione olografica. Le app che usano la visualizzazione 2D sono simili a finestre e possono essere posizionate attorno all'utente. Le app che usano la visualizzazione olografica ti circondano e diventano l'unica app visualizzata.

HoloLens supporta molte applicazioni esistenti del Microsoft Store e nuove app create specificamente per HoloLens.  Questo articolo è in particolare sulle applicazioni olografiche del Microsoft Store.

Per altre informazioni sull'installazione e l'esecuzione di app personalizzate, vedere [Applicazioni olografiche personalizzate.](holographic-custom-apps.md)

## <a name="find-apps"></a>Trovare app

Aprire il Microsoft Store dal menu **Start.** Cercare quindi app e giochi. È possibile usare [i comandi](hololens-cortana.md) vocali per eseguire la ricerca pronunciando "Cerca", una volta aperta la finestra di ricerca, pronunciare "Inizia a dettare" e quindi, quando richiesto, iniziare a pronunciare i termini di ricerca.

> [!NOTE]
> I requisiti di sistema per HoloLens dispositivi sono basati sull'architettura della compilazione dell'app. Se una build di app per HoloLens (prima generazione) non è stata aggiornata con a una nuova UWP nello Store per includere il pacchetto dell'architettura ARM, non sarà disponibile per i dispositivi HoloLens 2. Analogamente, se un'app HoloLens 2 non include il pacchetto di architettura x86, non sarà disponibile per i dispositivi HoloLens (prima generazione). HoloLens architetture dei dispositivi:
> - x86 = HoloLens (prima generazione)
> - ARM = HoloLens 2

> [!NOTE]
> Il 12 gennaio 2021 le app seguenti raggiungeranno la fine del supporto HoloLens dispositivi. Si consiglia di usare il collegamento seguente nel dispositivo per usare la versione Web dell'app.

| App        | Collegamento                                          |
|------------|-----------------------------------------------|
| Excel per dispositivi mobili      | https://office.live.com/start/Excel.aspx      |
| Word mobile       | https://office.live.com/start/Word.aspx       |
| PowerPoint mobile | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a>Installare app

Per scaricare le app, è necessario accedere con un account Microsoft. Alcune app sono gratuite e possono essere scaricate immediatamente. Per le app che richiedono un acquisto, è necessario accedere a Store con il proprio account Microsoft e avere un metodo di pagamento valido.

> [!NOTE]
> L'account che si Microsoft Store non deve essere uguale all'account con cui è stato eseguito l'accesso. Se si usa un account aziendale o dell'istituto di istruzione nel HoloLens potrebbe essere necessario accedere con l'account personale nell'app dello Store per effettuare un acquisto.

> [!TIP]
> Per configurare un metodo di pagamento, passare a Account.microsoft.com e [selezionare](https://account.microsoft.com/) Opzioni di pagamento & **pagamento**  >    >  **Aggiungi un'opzione di pagamento.**

1. Per aprire il menu [ **Start**](holographic-home.md), eseguire un [movimento Start](/hololens/hololens2-basic-usage#start-gesture) o un movimento [di HoloLens](hololens1-basic-usage.md) (prima generazione).

1. Selezionare l Microsoft Store app. Dopo l'apertura dell'app dello Store:
   1. Usare la barra di ricerca per cercare le applicazioni. 
   1. Selezionare le app essenziali o le app appositamente HoloLens da una delle categorie curate.
   1. In alto a destra nell'app Dello Store selezionare il pulsante **"..."** e quindi selezionare **Libreria** per visualizzare le app acquistate in precedenza.

1. Selezionare **Scarica** o **Installa** nella pagina dell'applicazione (potrebbe essere necessario un acquisto).

## <a name="update-apps"></a>Aggiornare le app

Per aggiornare un'app installata dal Microsoft Store, è possibile aggiornare l'app dalla Microsoft Store app. Per le app installate per Microsoft Store per le aziende, è anche possibile aggiornare tali app dal Microsoft Store per le aziende. 

1. Per aprire il menu [ **Start**](holographic-home.md), eseguire un [movimento Start](/hololens/hololens2-basic-usage#start-gesture) o un movimento [di HoloLens](hololens1-basic-usage.md) (prima generazione).

1. Selezionare l'app dello Store.

1. Esaminare l'angolo in alto a destra dell'app Dello Store. 

1. Selezionare il **pulsante "..."** o "Vedi altro".

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store screenshot dell'app.](images/store-update-1.png)

1. Selezionare **Download e aggiornamenti.**
    1. Se il dispositivo ha identificato in precedenza gli aggiornamenti, potrebbero essere presenti una freccia rivolta verso il basso e un numero che rappresenta gli aggiornamenti in sospeso.

1. Selezionare **Ottieni aggiornamenti.** Il dispositivo ora cerca gli aggiornamenti e li imposta per il download e l'installazione. 
 
   > [!div class="mx-imgBorder"]
   > ![Microsoft Store screenshot dell'app per ottenere gli aggiornamenti.](images/store-update-2.png.jpg)

> [!NOTE]
> Se le app nel dispositivo sono state distribuite dall'organizzazione, possono essere aggiornate tramite gli stessi metodi di gestione delle app commerciali. Se questo vale per la situazione specifica, leggere altre informazioni nella panoramica [della distribuzione di app commerciali.](app-deploy-overview.md)
>
> Se si vuole aggiornare un'app personalizzata che è stata sideloaded o distribuita, è necessario usare lo stesso metodo con la versione aggiornata dell'app. Per altre informazioni sull'installazione e l'esecuzione di app personalizzate, vedere [Applicazioni olografiche personalizzate.](holographic-custom-apps.md)

## <a name="uninstall-apps"></a>Disinstallazione di app

Esistono tre modi per disinstallare le applicazioni. È possibile disinstallare le applicazioni tramite Microsoft Store, menu Start o da Impostazioni. 

> [!WARNING]
> Non è possibile disinstallare un'app di sistema o il Microsoft Store stesso.

> [!IMPORTANT]
> Se il HoloLens 2 ha più utenti, è necessario essere connessi come utente che ha installato l'app per disinstallarla. 

### <a name="uninstall-from-the-microsoft-store"></a>Disinstallare dal Microsoft Store

Aprire il Microsoft Store dal menu **Start** e quindi cercare l'applicazione da disinstallare.  Nella pagina Store ogni applicazione installata ha un **pulsante Disinstalla.**

### <a name="uninstall-from-the-start-menu"></a>Eseguire la disinstallazione dal menu Start

Passare all'app nel menu **Start** o nell'elenco **All apps**. Selezionare e tenere premuto fino a quando non viene visualizzato il menu, quindi selezionare **Uninstall**.

### <a name="uninstall-from-settings"></a>Eseguire la disinstallazione dalle impostazioni
Nel menu **Start** selezionare Impostazioni **-> App.** Trovare l'app nell'elenco, selezionarla e quindi fare clic su **Uninstall**.

Se non è possibile disinstallare un'app, inviare [commenti e suggerimenti](/hololens/hololens-feedback) usando il Hub di Feedback.
