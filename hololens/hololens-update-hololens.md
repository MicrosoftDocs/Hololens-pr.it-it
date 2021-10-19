---
title: Aggiornare HoloLens 2
description: Informazioni su come controllare il numero HoloLens build, rimanere aggiornati con gli aggiornamenti del dispositivo, partecipare al Programma Insider ed eseguire il rollback degli aggiornamenti.
keywords: procedura, aggiornamento, rollback, HoloLens, controllare la compilazione, numero di build
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151684"
---
# <a name="update-hololens-2"></a>Aggiornare HoloLens 2

## <a name="overview"></a>Panoramica

Microsoft si sta sempre lavorando a nuove funzionalità, correzioni di bug e aggiornamenti della sicurezza. Si verrà informati quando questi aggiornamenti saranno pronti.

In base alle preferenze, il HoloLens scaricherà e installerà automaticamente gli aggiornamenti di sistema ogni volta che è collegato all'alimentazione, connesso a Internet e anche in standby.

Per assicurarsi che il HoloLens sia sempre aggiornato, lasciarlo collegato al caricatore fornito con esso. Si vuole anche che il HoloLens sia connesso a Internet. In questo modo, verranno scaricati e installati automaticamente gli aggiornamenti di sistema. 

Con Windows Update, si controllano più aspetti del processo di aggiornamento, ad esempio quali dispositivi ottengono gli aggiornamenti in quale momento. Questo controllo è utile perché è possibile implementare gli aggiornamenti a un subset di HoloLens per i test. Quindi, implementare gli aggiornamenti per quelli rimanenti. In caso contrario, è possibile definire pianificazioni degli aggiornamenti diverse per diversi tipi di aggiornamenti.

## <a name="types-of-updates"></a>Tipi di aggiornamenti

Ad HoloLens, è possibile gestire automaticamente due tipi di aggiornamenti.

- Aggiornamenti delle funzionalità: rilasciati due volte all'anno.
- Aggiornamenti qualitativi: includono gli aggiornamenti critici della sicurezza. Vengono rilasciati ogni mese o in base alle esigenze.

Usare **Update** / **AllowAutoUpdate per** gestire l'analisi, il download e l'installazione degli aggiornamenti. 

## <a name="scheduling-updates"></a>Pianificazione degli aggiornamenti

È anche possibile impostare una pianificazione degli aggiornamenti. Può essere in un determinato giorno o ogni giorno in una determinata ora. Ad esempio, alle 17.00 o al di fuori dell'orario di attività.

Infine, alcune parole sulla pianificazione della strategia di aggiornamento. Sono supportati i rinvii degli aggiornamenti, pertanto è possibile decidere quanto tempo attendere dopo il rilascio di un aggiornamento da parte di Microsoft per installare l'aggiornamento nei dispositivi.

A volte a un'azienda piace provare prima tutte le nuove funzionalità per assicurarsi che tutto funzioni e che abbia familiarità con i nuovi aggiornamenti in modo che il team di supporto sia preparato. Dopo aver confermato che tutto è positivo, implementazione degli aggiornamenti per l'intera azienda. Associando subset di dispositivi a diversi criteri di rinvio, noti come anelli di aggiornamento, è possibile coordinare una strategia di implementazione degli aggiornamenti per l'organizzazione.

## <a name="hololens-update-tools"></a>HoloLens strumenti di aggiornamento

Questa sezione illustra in modo HoloLens per:

- controllo della disponibilità di aggiornamenti
- aggiornamento manuale dei HoloLens
- visualizzazione della versione corrente del sistema operativo (numero di build)
- rollback a un aggiornamento precedente

### <a name="check-for-updates-and-manually-update"></a>Verificare la disponibilità di aggiornamenti e aggiornarsi manualmente

È possibile verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.  Per visualizzare gli aggiornamenti disponibili e verificare la disponibilità di nuovi aggiornamenti:

1. Aprire l'app **Impostazioni**.
1. Passare a **Update & Security** Windows  >  **Update**.
1. Selezionare **Verifica disponibilità aggiornamenti**.

Se è disponibile un aggiornamento, verrà avviato il download della nuova versione. Al termine del download, selezionare il pulsante **Riavvia ora** per attivare l'installazione. Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.

Mentre il HoloLens installa l'aggiornamento, visualizza gli ingranaggi rotanti e un indicatore di stato. Non disattivare la HoloLens durante questo periodo di tempo. Verrà riavviato automaticamente al termine dell'installazione.

HoloLens applica un aggiornamento alla volta.  Se il HoloLens è più di una versione rispetto alla più recente, potrebbe essere necessario eseguire il processo di aggiornamento più volte per aggiornarlo completamente.

### <a name="check-your-operating-system-version-build-number"></a>Controllare la versione del sistema operativo (numero di build)

È possibile verificare il numero di versione del sistema (numero di build) aprendo **Impostazioni** e selezionando **Informazioni sul**  >  **sistema.**

### <a name="go-back-to-a-previous-version"></a>Tornare a una versione precedente

In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens. I passaggi consigliati sono:

1. Contattare il supporto tecnico per verificare se è possibile risolvere il problema.
    1. Assicurarsi che la **telemetria** facoltativa **o** completa sia abilitata, in modo da rendere il bug più fattibile e più facile da diagnosticare per i tecnici.
    1. In [File Feedback (Commenti e suggerimenti](hololens-feedback.md) file) è il più descrittivo possibile. Prendere nota del titolo o usare la funzionalità di condivisione per poter condividere il bug con il supporto tecnico.
    1. Contattare [il supporto](https://aka.ms/hlsupport)tecnico . Se il problema deve essere risolto tornando a una versione precedente, può fornire il FFU per eseguire il flashing del dispositivo.

1. In alternativa, è possibile [eseguire il reflash del HoloLens 2 con Advanced Recovery Companion.](hololens-recovery.md#clean-reflash-the-device)
    1.  Scegliere la versione in cui eseguire il flash: 
        1.  È possibile scaricare la [versione più HoloLens 2 recente.](https://aka.ms/hololens2download)
        1.  È possibile usare la build predefinita ospitata da ARC.
        1.  È possibile usare un supporto di compilazione fornito con .

> [!NOTE]
> Se si torna a una versione precedente, i file e le impostazioni personali vengono eliminati.

Inoltre, se si vuole mantenere la versione attualmente installata, è anche possibile sospendere manualmente [gli aggiornamenti](hololens-updates.md#pause-updates-via-device). In questo modo il team di progettazione avrà il tempo necessario per risolvere il problema.

## <a name="windows-insider-program-on-hololens"></a>Windows Programma Insider in HoloLens

Per visualizzare le funzionalità più recenti in HoloLens?  In tal caso, unire il Windows Programma Insider; Si otterrà l'accesso alle build di anteprima HoloLens aggiornamenti software prima che siano disponibili al pubblico generale.

[Ottenere Windows Insider Preview per Microsoft HoloLens](hololens-insider.md).