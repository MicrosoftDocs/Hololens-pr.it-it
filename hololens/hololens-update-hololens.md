---
title: Aggiornare HoloLens 2
description: Informazioni su come controllare il numero HoloLens build, mantenersi aggiornati con gli aggiornamenti dei dispositivi, partecipare al programma Insiders ed eseguire il rollback degli aggiornamenti.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427909"
---
# <a name="update-hololens-2"></a>Aggiornare HoloLens 2

## <a name="overview"></a>Panoramica

Sono sempre in corso nuove funzionalità, correzioni di bug e aggiornamenti della sicurezza. Si verrà informati quando questi aggiornamenti sono pronti.

In base alle preferenze, il HoloLens scarica e installa automaticamente gli aggiornamenti di sistema ogni volta che è collegato all'alimentazione, connesso a Internet e anche in standby.

Per assicurarsi che il HoloLens sia sempre aggiornato, lasciarlo collegato al caricabatterie fornito con esso. Si vuole anche che il HoloLens connesso a Internet. In questo modo, scarica e installa automaticamente gli aggiornamenti di sistema. 

Con Windows di aggiornamento, si controllano più aspetti del processo di aggiornamento, ad esempio i dispositivi che ottengono gli aggiornamenti in quale momento. Questo controllo è utile perché è possibile implementare gli aggiornamenti in un subset di HoloLens per il test. Implementare quindi gli aggiornamenti per quelli rimanenti. In caso contrario, è possibile definire pianificazioni di aggiornamento diverse per diversi tipi di aggiornamenti.

## <a name="types-of-updates"></a>Tipi di aggiornamenti

Ad HoloLens, è possibile gestire automaticamente due tipi di aggiornamenti. 

- Aggiornamenti delle funzionalità: rilasciati due volte all'anno.
- Aggiornamenti qualitativi: includono gli aggiornamenti critici della sicurezza. Vengono rilasciati mensilmente o in base alle esigenze.

Usare **Update** / **AllowAutoUpdate** per gestire l'analisi, il download e l'installazione degli aggiornamenti. 

## <a name="scheduling-updates"></a>Pianificazione degli aggiornamenti

È anche possibile impostare una pianificazione degli aggiornamenti. Può essere in un determinato giorno, o ogni giorno, in un determinato momento. Ad esempio, alle 17:00 o al di fuori degli orari di attività.

Infine, alcune parole sulla pianificazione della strategia di aggiornamento. Sono supportati i rinvii degli aggiornamenti. È quindi possibile decidere per quanto tempo attendere dopo il rilascio di un aggiornamento da parte di Microsoft per installare l'aggiornamento nei dispositivi.

A volte, a un'azienda piace provare prima tutte le nuove funzionalità per assicurarsi che tutto funzioni e che abbia familiarità con i nuovi aggiornamenti in modo che il team di supporto sia preparato. Dopo aver confermato che è tutto a posto, gli aggiornamenti vengono estensitivi per l'intera azienda. Associando subset dei dispositivi a criteri di rinvio diversi, noti come anelli di aggiornamento, è possibile coordinare una strategia di implementazione degli aggiornamenti per l'organizzazione.

## <a name="hololens-update-tools"></a>HoloLens strumenti di aggiornamento

Questa sezione illustra in modo più HoloLens strumenti per:

- controllo della disponibilità di aggiornamenti
- aggiornamento manuale HoloLens
- visualizzazione della versione corrente del sistema operativo (numero di build)
- rollback a un aggiornamento precedente

### <a name="check-for-updates-and-manually-update"></a>Verificare la disponibilità di aggiornamenti e aggiornare manualmente

È possibile verificare la disponibilità di aggiornamenti in qualsiasi momento nelle impostazioni.  Per visualizzare gli aggiornamenti disponibili e verificare la presenza di nuovi aggiornamenti:

1. Aprire l'app **Impostazioni**.
1. Passare a **Update & Security** Windows Update (Aggiorna Windows  >  **Sicurezza).**
1. Selezionare **Verifica disponibilità aggiornamenti**.

Se è disponibile un aggiornamento, inizierà a scaricare la nuova versione. Al termine del download, selezionare il pulsante **Riavvia ora** per attivare l'installazione. Se il dispositivo è inferiore al 40% e non è collegato, il riavvio non avvia l'installazione dell'aggiornamento.

Mentre il HoloLens sta installando l'aggiornamento, verranno visualizzati ingranaggi rotanti e un indicatore di stato. Non disattivare la HoloLens durante questo periodo. Verrà riavviato automaticamente al termine dell'installazione.

HoloLens applica un aggiornamento alla volta.  Se il HoloLens è più di una versione rispetto alla versione più recente, potrebbe essere necessario eseguire più volte il processo di aggiornamento per aggiornarlo completamente.

### <a name="check-your-operating-system-version-build-number"></a>Controllare la versione del sistema operativo (numero di build)

È possibile verificare il numero di versione del sistema (numero di **build)** aprendo Impostazioni e selezionando **Informazioni**  >  **sul sistema.**

### <a name="go-back-to-a-previous-version"></a>Tornare a una versione precedente

In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens software. I passaggi consigliati sono:

1. Contattare il supporto tecnico per verificare se è possibile risolvere il problema.
    1. Assicurarsi che **la telemetria** facoltativa **o** completa sia abilitata, in modo da rendere il bug più gestibile e più semplice da diagnosticare per i tecnici.
    1. [Il feedback dei](hololens-feedback.md) file è il più descrittivo possibile. Prendere nota del titolo o usare la funzionalità di condivisione per condividere il bug con il supporto tecnico.
    1. Contattare [il supporto](https://aka.ms/hlsupport)tecnico . Se il problema è quello che deve essere risolto tornando a una versione precedente, possono fornire l'FFU per eseguire il flashing del dispositivo.

1. Se non funziona, reimpostare o convertire il HoloLens 2 [con Advanced Recovery Companion.](hololens-recovery.md)
    1. Nel PC scaricare [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dal Microsoft Store.
    1. Assicurarsi di non avere telefoni o dispositivi Windows collegati al PC.
    1. Scegliere la versione in cui si vuole eseguire il flash:
        1. È possibile scaricare la [versione più recente HoloLens 2 versione](https://aka.ms/hololens2download).
        1. È possibile usare la compilazione predefinita ospitata da ARC. Se si sceglie questa opzione, ignorare il passaggio successivo.
        1. È possibile usare un supporto di compilazione fornito con .
    1. Al termine di questi download, **aprire** Esplora file  >  **Download**. Fare clic con il pulsante destro del mouse sulla cartella compressa scaricata e scegliere **Estrai** tutto  >   per decomprimerla.
    1. Connessione il HoloLens al PC usando un cavo da USB A a USB-C. Anche se si usano altri cavi per connettere il HoloLens, questo funziona meglio.
    1. Advanced Recovery Companion rileva automaticamente il HoloLens. Selezionare il **Microsoft HoloLens** riquadro.
    1. Nella schermata successiva selezionare **Selezione** pacchetto manuale e quindi selezionare il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con `.ffu` l'estensione .
    1. Selezionare **Installa software** e seguire le istruzioni.

> [!NOTE]
> Tornando a una versione precedente, i file e le impostazioni personali vengono eliminati.

Inoltre, se si vuole rimanere nella versione attualmente installata, è anche possibile sospendere manualmente [gli aggiornamenti](hololens-updates.md#pause-updates-via-device). In questo modo il team di progettazione avrà il tempo di risolvere il problema.

## <a name="windows-insider-program-on-hololens"></a>Windows Programma Insider in HoloLens

Per visualizzare le funzionalità più recenti in HoloLens?  In tal caso, aggiungere il Windows Programma Insider; Si otterrà l'accesso alle build di anteprima HoloLens aggiornamenti software prima che siano disponibili per il pubblico generale.

[Ottenere Windows Insider Preview per Microsoft HoloLens](hololens-insider.md).