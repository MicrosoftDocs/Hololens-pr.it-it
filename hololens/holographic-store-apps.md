---
title: Trovare, installare e disinstallare applicazioni
description: Il Microsoft Store è l'origine per app e giochi che funzionano con HoloLens.  Altre informazioni su come trovare, installare e disinstallare app olografiche.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3442da500e7554d7f97db2178cbaceeecad143ac
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036064"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Trovare, installare e disinstallare applicazioni dal Microsoft Store

Il Microsoft Store è l'origine di accesso per app e giochi che funzionano con HoloLens. Quando si passa a Store nel HoloLens, tutte le app presenti verranno eseguite su di esso.

Le app HoloLens la visualizzazione 2D o la visualizzazione olografica. Le app che usano la visualizzazione 2D hanno un aspetto simile alle finestre e possono essere posizionate in tutto il mondo. Le app che usano la visualizzazione olografica circondano l'utente e diventano l'unica app visualizzata.

HoloLens supporta molte applicazioni esistenti dal Microsoft Store e nuove app create appositamente per HoloLens.  Questo articolo è in particolare sulle applicazioni olografiche Microsoft Store.

Per altre informazioni sull'installazione e l'esecuzione di app personalizzate, vedere [Applicazioni olografiche personalizzate](holographic-custom-apps.md).

## <a name="find-apps"></a>Trovare app

Aprire il Microsoft Store dal menu **Start.** Cercare quindi app e giochi. È possibile usare [i comandi](hololens-cortana.md) vocali per eseguire la ricerca pronunciando "Cerca", quando si apre la finestra di ricerca pronunciare "Inizia a dettare" e quindi, quando richiesto, iniziare a pronunciare i termini di ricerca.

> [!NOTE]
> I requisiti di sistema per HoloLens dispositivi sono basati sull'architettura della compilazione dell'app. Se una build di app per HoloLens (prima generazione) non è stata aggiornata con una nuova UWP nello Store per includere il pacchetto di architettura arm, non sarà disponibile per i dispositivi HoloLens 2. Analogamente, se un'app HoloLens 2 non include il pacchetto di architettura x86, non sarà disponibile per i dispositivi HoloLens (prima generazione). HoloLens architetture dei dispositivi:
>
> - x86 = HoloLens (prima generazione)
> - ARM = HoloLens 2

> [!NOTE]
> Il 12 gennaio 2021 le app seguenti raggiungeranno la fine del supporto HoloLens dispositivi. Si consiglia di usare il collegamento seguente nel dispositivo per usare la versione Web dell'app.

| App        | Collegamento                                          |
|------------|-----------------------------------------------|
| Excel per dispositivi mobili      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word per dispositivi mobili       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint per dispositivi mobili | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> L OneDrive app non è attualmente supportata per gli account Azure AD in HoloLens. È consigliabile scaricare l'app Microsoft OneDrive PWA app. [Seguire questa procedura per scaricare l'app.]

## <a name="install-apps"></a>Installare app

Per scaricare le app, è necessario accedere con un account Microsoft. Alcune app sono gratuite e possono essere scaricate immediatamente. Per le app che richiedono un acquisto, è necessario accedere a Store con il account Microsoft e avere un metodo di pagamento valido.

> [!NOTE]
> L'account Microsoft Store non deve essere uguale all'account con cui è stato eseguito l'accesso. Se si usa un account aziendale o dell'istituto di istruzione nel HoloLens, potrebbe essere necessario accedere con il proprio account personale nell'app Dello Store per effettuare un acquisto.

> [!TIP]
> Per configurare un metodo di pagamento, passare a Account.microsoft.com [e](https://account.microsoft.com/) selezionare **Pagamento &** opzioni di  >  **pagamento**  >  **Aggiungi un'opzione di pagamento**.

1. Per aprire il menu [ **Start,**](holographic-home.md)eseguire un [movimento start o](/hololens/hololens2-basic-usage#start-gesture) [bloom](hololens1-basic-usage.md) HoloLens (prima generazione).

1. Selezionare l Microsoft Store app. Dopo l'apertura dell'app Store:
   1. Usare la barra di ricerca per cercare le applicazioni.
   1. Selezionare app o app essenziali appositamente HoloLens da una delle categorie curate.
   1. In alto a destra nell'app Store selezionare il pulsante **"..."** e quindi selezionare **Libreria** per visualizzare tutte le app acquistate in precedenza.

1. Selezionare **Scarica** o **Installa** nella pagina dell'applicazione (potrebbe essere necessario un acquisto).

### <a name="install-microsoft-onedrive-pwa-app"></a>Installare l Microsoft OneDrive PWA app

Prerequisiti: l'utente ha già aggiunto il dispositivo HoloLens 2 al tenant di lavoro.

1. Aprire il menu Start e avviare il browser Edge.

    ![Menu Start](images/office-pwa-1.jpg)

1. Nel HoloLens passare a [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) e immettere le credenziali dell'account aziendale

    ![Accesso al lavoro](images/office-pwa-2.jpg)

1. Dopo aver eseguito l'accesso al portale OneDrive Web, attendere da 30 a 60 secondi per visualizzare PWA di download

    ![PWA pulsante Installa](images/office-pwa-3.jpg)

1. Selezionare il pulsante PWA download e installare l'app

    ![Richiesta di installazione](images/office-pwa-4.jpg)

1. Chiudere il browser Edge e dal menu Start  selezionare il pulsante Tutte le app e avviare l'app OneDrive PWA etichettata **Microsoft OneDrive**

    ![Tutte le app che mostrano entrambe le app.](images/office-pwa-5.jpg)

> [!NOTE]
> "Microsoft OneDrive" è l'app PWA in cui "OneDrive" è la UWP meno recente.

1. Sarà quindi possibile visualizzare i file OneDrive file.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Vedere anche: [Abilitazione dei caricamenti automatici OneDrive per le aziende](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Aggiornare le app

Per aggiornare un'app installata dal Microsoft Store, è possibile aggiornare l'app dall'app Microsoft Store app. Per le app installate per Microsoft Store per le aziende, è anche possibile aggiornare tali app dal Microsoft Store per le aziende.

1. Per aprire il menu [ **Start,**](holographic-home.md)eseguire un [movimento start o](/hololens/hololens2-basic-usage#start-gesture) [bloom](hololens1-basic-usage.md) HoloLens (prima generazione).

1. Selezionare l'app Store.

1. Cercare in alto a destra nell'app Store.

1. Selezionare il **pulsante "..."** o "Altro".

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store screenshot dell'app.](images/store-update-1.png)

1. Selezionare **Download e aggiornamenti.**
    1. Se il dispositivo ha identificato in precedenza gli aggiornamenti, potrebbero essere presenti una freccia verso il basso e un numero che rappresenta gli aggiornamenti in sospeso.

1. Selezionare **Ottieni aggiornamenti**. Il dispositivo ora cerca gli aggiornamenti e li imposta per il download e l'installazione.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store screenshot dell'app per ottenere gli aggiornamenti.](images/store-update-2.png.jpg)

> [!NOTE]
> Se le app nel dispositivo sono state distribuite dall'organizzazione, possono essere aggiornate tramite gli stessi metodi di gestione delle app commerciali. Se questo si applica alla situazione, leggere altre informazioni tramite la panoramica della distribuzione di [app commerciali.](app-deploy-overview.md)
>
> Se si vuole aggiornare un'app personalizzata che è stata caricata o distribuita in sideloaded, è necessario usare lo stesso metodo con la versione aggiornata dell'app. Per altre informazioni sull'installazione e l'esecuzione di app personalizzate, vedere [Applicazioni olografiche personalizzate.](holographic-custom-apps.md)

## <a name="uninstall-apps"></a>Disinstallazione di app

Esistono tre modi per disinstallare le applicazioni. È possibile disinstallare le applicazioni tramite Microsoft Store, menu Start o da Impostazioni.

> [!WARNING]
> Non è possibile disinstallare un'app di sistema o il Microsoft Store stesso.

> [!IMPORTANT]
> Se il HoloLens 2 ha più utenti, è necessario accedere come utente che ha installato l'app per disinstallarla.

### <a name="uninstall-from-the-microsoft-store"></a>Disinstallare dal Microsoft Store

Aprire il Microsoft Store dal menu **Start** e quindi cercare l'applicazione da disinstallare.  Nella pagina Store ogni applicazione installata ha un **pulsante Disinstalla.**

### <a name="uninstall-from-the-start-menu"></a>Eseguire la disinstallazione dal menu Start

Passare all'app nel menu **Start** o nell'elenco **All apps**. Selezionare e tenere premuto fino a quando non viene visualizzato il menu, quindi selezionare **Uninstall**.

### <a name="uninstall-from-settings"></a>Eseguire la disinstallazione dalle impostazioni

Nel menu **Start** selezionare Impostazioni > **app.** Trovare l'app nell'elenco, selezionarla e quindi fare clic su **Uninstall**.

Se non è possibile disinstallare un'app, inviare [commenti e suggerimenti](/hololens/hololens-feedback) usando il Hub di Feedback.
