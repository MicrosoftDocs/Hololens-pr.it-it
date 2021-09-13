---
title: Aggiornare HoloLens 2
description: Informazioni su come controllare il numero HoloLens build, rimanere aggiornati con gli aggiornamenti del dispositivo, partecipare al Programma Insider ed eseguire il rollback degli aggiornamenti.
keywords: procedura, aggiornamento, rollback, HoloLens, controllare la compilazione, numero di build
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033815"
---
# <a name="update-hololens-2"></a>Aggiornare HoloLens 2

## <a name="overview"></a>Panoramica

Microsoft si sta sempre lavorando a nuove funzionalità, correzioni di bug e aggiornamenti della sicurezza. Si verrà informati quando questi aggiornamenti saranno pronti.

In base alle preferenze, il HoloLens scaricherà e installerà automaticamente gli aggiornamenti di sistema ogni volta che è collegato all'alimentazione, connesso a Internet e anche in standby.

Per assicurarsi che il HoloLens sia sempre aggiornato, lasciarlo collegato al caricatore fornito con esso. Si vuole anche che i HoloLens siano connessi a Internet. In questo modo, verranno scaricati e installati automaticamente gli aggiornamenti di sistema. 

Con Windows update, si controllano più aspetti del processo di aggiornamento, ad esempio quali dispositivi ottengono gli aggiornamenti in quale momento. Questo controllo è utile perché è possibile implementare gli aggiornamenti in un subset di HoloLens per i test. Quindi, implementare gli aggiornamenti per quelli rimanenti. In caso contrario, è possibile definire pianificazioni degli aggiornamenti diverse per diversi tipi di aggiornamenti.

## <a name="types-of-updates"></a>Tipi di aggiornamenti

Ad HoloLens, è possibile gestire automaticamente due tipi di aggiornamenti. 

- Aggiornamenti delle funzionalità: rilasciati due volte all'anno.
- Aggiornamenti qualitativi: includono gli aggiornamenti critici della sicurezza. Vengono rilasciati ogni mese o in base alle esigenze.

Usare **Update** / **AllowAutoUpdate per** gestire l'analisi, il download e l'installazione degli aggiornamenti. 

## <a name="scheduling-updates"></a>Pianificazione degli aggiornamenti

È anche possibile impostare una pianificazione degli aggiornamenti. Può essere in un determinato giorno o ogni giorno in una determinata ora. Ad esempio, alle 17.00 o al di fuori dell'orario di attività.

Infine, alcune parole sulla pianificazione della strategia di aggiornamento. Sono supportati i rinvii degli aggiornamenti. È quindi possibile decidere quanto tempo attendere dopo il rilascio di un aggiornamento da parte di Microsoft per installare l'aggiornamento nei dispositivi.

In alcuni casi, un'azienda desidera provare prima tutte le nuove funzionalità per assicurarsi che tutto funzioni correttamente e abbia familiarità con i nuovi aggiornamenti in modo che il team di supporto sia preparato. Dopo aver confermato che tutto è positivo, implementazione degli aggiornamenti per l'intera azienda. Associando subset di dispositivi a diversi criteri di rinvio, noti come anelli di aggiornamento, è possibile coordinare una strategia di implementazione degli aggiornamenti per l'organizzazione.

## <a name="hololens-update-tools"></a>HoloLens strumenti di aggiornamento

Questa sezione illustra gli strumenti HoloLens per:

- controllo della disponibilità di aggiornamenti
- aggiornamento manuale HoloLens
- visualizzazione della versione corrente del sistema operativo (numero di build)
- rollback a un aggiornamento precedente

### <a name="check-for-updates-and-manually-update"></a>Verificare la disponibilità di aggiornamenti e aggiornarsi manualmente

È possibile verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.  Per visualizzare gli aggiornamenti disponibili e verificare la disponibilità di nuovi aggiornamenti:

1. Aprire l'app **Impostazioni**.
1. Passare a **Update & Security** Windows  >  **Update**.
1. Selezionare **Verifica disponibilità aggiornamenti**.

Se è disponibile un aggiornamento, verrà avviato il download della nuova versione. Al termine del download, selezionare il pulsante **Riavvia ora** per attivare l'installazione. Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.

Mentre il HoloLens installa l'aggiornamento, visualizza gli ingranaggi rotanti e un indicatore di stato. Non disattivare la HoloLens durante questo periodo di tempo. Verrà riavviato automaticamente al termine dell'installazione.

HoloLens applica un aggiornamento alla volta.  Se il HoloLens è più di una versione rispetto alla versione più recente, potrebbe essere necessario eseguire il processo di aggiornamento più volte per aggiornarlo completamente.

### <a name="check-your-operating-system-version-build-number"></a>Controllare la versione del sistema operativo (numero di build)

È possibile verificare il numero di versione del sistema (numero di build) aprendo **Impostazioni** e selezionare **Informazioni**  >  **sul sistema.**

### <a name="go-back-to-a-previous-version"></a>Tornare a una versione precedente

In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens. I passaggi consigliati sono:

1. Contattare il supporto tecnico per verificare se è possibile risolvere il problema.
    1. Assicurarsi che la **telemetria** facoltativa **o** completa sia abilitata, in modo da rendere il bug più fattibile e più facile da diagnosticare per i tecnici.
    1. [Il feedback dei](hololens-feedback.md) file è il più descrittivo possibile. Prendere nota del titolo o usare la funzionalità di condivisione per poter condividere il bug con il supporto tecnico.
    1. Contattare [il supporto](https://aka.ms/hlsupport)tecnico . Se il problema deve essere risolto tornando a una versione precedente, può fornire il FFU per eseguire il flashing del dispositivo.

1. Se l'operazione non funziona, reimpostare o ripristinare il HoloLens 2 [con Advanced Recovery Companion.](hololens-recovery.md)
    1. Nel PC scaricare [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dal Microsoft Store.
    1. Assicurarsi che non siano presenti telefoni o dispositivi Windows collegati al PC.
    1. Scegliere la versione in cui eseguire il flash:
        1. È possibile scaricare la [versione più HoloLens 2 recente.](https://aka.ms/hololens2download)
        1. È possibile usare la build predefinita ospitata da ARC. Se si sceglie questa opzione, ignorare il passaggio successivo.
        1. È possibile usare un supporto di compilazione fornito con .
    1. Al termine di questi download, **aprire** Esplora file  >  **Download**. Fare clic con il pulsante destro del mouse sulla cartella compressa scaricata e scegliere **Estrai** tutto  >   per decomprimerla.
    1. Connessione il HoloLens al PC usando un cavo DA USB A a USB-C. Anche se si usano altri cavi per connettere i HoloLens, questa soluzione funziona meglio.
    1. Advanced Recovery Companion rileva automaticamente il HoloLens. Selezionare il **Microsoft HoloLens** personalizzato.
    1. Nella schermata successiva selezionare Selezione manuale **del pacchetto** e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con `.ffu` estensione .
    1. Selezionare **Installa software** e seguire le istruzioni.

> [!NOTE]
> Se si torna a una versione precedente, i file e le impostazioni personali vengono eliminati.

Inoltre, se si vuole mantenere la versione attualmente installata, è anche possibile sospendere manualmente [gli aggiornamenti](hololens-updates.md#pause-updates-via-device). In questo modo il team di progettazione avrà il tempo necessario per risolvere il problema.

## <a name="windows-insider-program-on-hololens"></a>Windows Programma Insider in HoloLens

Per visualizzare le funzionalità più recenti in HoloLens?  In tal caso, unire il Windows Programma Insider; Si otterrà l'accesso alle build di anteprima HoloLens aggiornamenti software prima che siano disponibili al pubblico generale.

[Ottenere Windows Insider Preview per Microsoft HoloLens](hololens-insider.md).