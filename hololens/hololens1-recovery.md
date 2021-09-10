---
title: Riavviare, reimpostare o ripristinare HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Come usare lo Windows di ripristino del dispositivo per eseguire il flash di un'immagine HoloLens prima generazione.
keywords: procedura, riavvio, ripristino, ripristino, hard reset, soft reset, ciclo di alimentazione, HoloLens, arresto, wdrt, strumento di ripristino del dispositivo Windows
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427884"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Riavviare, reimpostare o ripristinare HoloLens (prima generazione)

Se si verificano problemi con l'HoloLens, è possibile provare a riavviare o reimpostare il dispositivo o persino a eseguire il reflash del dispositivo usando il ripristino del dispositivo. Questo articolo illustra i passaggi di ripristino consigliati nell'ordine indicato.

Se si sta cercando di ripristinare un HoloLens 2, vedere Ripristino di un HoloLens 2 [,](hololens-recovery.md)in quanto il processo è diverso.

> [!NOTE]
> Questo articolo è in HoloLens e software. Se gli ologrammi non hanno **[](hololens-environment-considerations.md)** un aspetto giusto, vedere HoloLens considerazioni sull'ambiente per informazioni sui fattori che migliorano la qualità degli ologrammi.

## <a name="restart"></a>Riavvia

### <a name="do-a-safe-restart-by-using-cortana"></a>Eseguire un riavvio sicuro usando Cortana

Il modo più sicuro per riavviare il HoloLens è usare Cortana, che in genere è la prima cosa da provare quando si verifica un problema con HoloLens.

> [!NOTE] 
> Cortana non è disponibile in tutti i dispositivi.
> - Cortana è disponibile in tutti i HoloLens (prima generazione). 
> - Cortana disponibile nei dispositivi HoloLens 2 build precedenti all'aggiornamento Windows Holograpic versione 2004.

1. Attivare la HoloLens.
1. Assicurarsi che un utente sia connesso e che il dispositivo non sia in attesa di una password per sbloccarla.
2. Pronunciare "Hey Cortana, reboot" o "Hey Cortana, restart".
3. Cortana risponderà e chiederà di confermare. Attendere la riproduzione di un suono dopo la domanda e quindi pronunciare "Sì". Il dispositivo verrà riavviato.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Usare il pulsante di alimentazione per eseguire un riavvio sicuro

Se non è ancora possibile riavviare il dispositivo, provare a riavviarlo usando il **pulsante di** alimentazione:

1. Tenere premuto il **pulsante** di alimentazione per 5 secondi. Dopo 1 secondo, tutti e cinque i LED si illuminano e quindi si disattivano lentamente uno alla volta da destra a sinistra. Dopo 5 secondi, tutti i LED saranno spenti, a indicare che l'arresto è riuscito.
      
   > [!IMPORTANT]
   > Interrompere la pressione del pulsante immediatamente dopo che tutti i LED sono stati spenti.
1. Attendere 1 minuto per il completamento dell'arresto. L'arresto potrebbe essere ancora in corso anche dopo che gli schermi sono stati disattivati.
2. Accendere di nuovo il dispositivo premendo e tenendo premuto **il** pulsante di alimentazione per 1 secondo.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Eseguire un riavvio sicuro usando Windows Portale di dispositivi

> [!NOTE]
> Per questo processo, HoloLens deve essere configurato come dispositivo per sviluppatori. Per altre informazioni, [vedere Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal).

Se la procedura precedente non ha funzionato, provare a riavviare il dispositivo usando [Windows Portale di dispositivi](/windows/mixed-reality/using-the-windows-device-portal). Nell'angolo superiore destro trovare l'opzione per riavviare o arrestare il dispositivo.

### <a name="do-an-unsafe-forced-restart"></a>Eseguire un riavvio forzato non sicuro

Se i metodi precedenti non hanno riavviato il HoloLens, forzare un riavvio. Questo metodo equivale a rimuovere e reinstallare la batteria. È pericoloso perché potrebbe lasciare il dispositivo in uno stato danneggiato. In questo caso, sarà necessario eseguire il flash del HoloLens.  

> [!WARNING]
> Si tratta di un metodo potenzialmente dannoso e deve essere usato solo se i metodi citati in precedenza non funzionano.

1. Tenere premuto il **pulsante** di alimentazione per almeno 10 secondi.
   - È possibile tenere premuto il pulsante per più di 10 secondi.
   - È possibile ignorare qualsiasi attività LED.
1. Rilasciare il pulsante e attendere 2-3 secondi.
1. Tenere premuto il **pulsante di** accensione per 1 secondo.
1. Se si verificano ancora  problemi, premere il pulsante di alimentazione per 4 secondi, fino a quando tutti gli indicatori della batteria non svaniscono e lo schermo smette di visualizzare gli ologrammi. Attendere 1 minuto e quindi premere di nuovo il **pulsante** di accensione per accendere il dispositivo.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Tornare a una versione precedente - HoloLens (prima generazione)

In alcuni casi, potrebbe essere necessario tornare a una versione precedente del software HoloLens software. È possibile eseguire questa operazione usando lo strumento Windows ripristino del dispositivo per ripristinare HoloLens alla versione precedente.

> [!NOTE]
> Tornando a una versione precedente, i file e le impostazioni personali vengono eliminati.

Per tornare a una versione precedente di HoloLens 1, seguire questa procedura:

1. Assicurarsi di non avere telefoni o dispositivi Windows collegati al PC.
1. Nel PC scaricare [l'Windows device recovery tool (WDRT)](https://support.microsoft.com/help/12379).
1. Scaricare il [pacchetto HoloLens di ripristino dell'aggiornamento dell'anniversario.](https://aka.ms/hololensrecovery)
1. Al termine dei download, aprire **Esplora file**  >  **Download**. Fare clic con il pulsante destro del mouse sulla cartella compressa appena scaricata e scegliere **Estrai** tutto  >   per decomprimerla.
1. Connessione il HoloLens al PC usando il cavo micro USB con cui è stato fornito. Anche se si usano altri cavi per connettere il HoloLens, questo funziona meglio.
1. WDRT rileverà automaticamente il HoloLens. Selezionare il **Microsoft HoloLens** riquadro.
1. Nella schermata successiva selezionare **Selezione** pacchetto manuale e scegliere il file di installazione contenuto nella cartella decompressa nel passaggio 4. Cercare un file con estensione ffu.
1. Selezionare **Installa software** e seguire le istruzioni.

> [!NOTE]
> Se WDRT non rileva il HoloLens, provare a riavviare il PC. Se non funziona, selezionare Il dispositivo **non** è stato rilevato, **selezionare** Microsoft HoloLens e quindi seguire le istruzioni.

## <a name="reset-to-factory-settings"></a>Ripristinare le impostazioni predefinite

> [!NOTE]
> La batteria richiede almeno un addebito del 40% per la reimpostazione.

Se il HoloLens ha ancora un problema, provare a reimpostarlo sullo stato factory. Questo passaggio mantiene la versione del Windows software Holographic installato in esso e restituisce tutto il resto alle impostazioni predefinite.

>[!WARNING]
> Se si reimposta il dispositivo, tutti i dati personali, le app e le impostazioni verranno cancellati, incluse le informazioni di reimpostazione TPM. La reimpostazione installerà solo la versione installata più recente di Windows Holographic. Sarà necessario ripetere tutti i passaggi di inizializzazione (calibrare, connettersi al Wi-Fi, creare un account utente, scaricare le app e così via).

1. Aprire l Impostazioni app e quindi selezionare **Aggiorna**  >  **ripristino**.
1. Selezionare **l'opzione Reimposta** dispositivo e leggere il messaggio di conferma.
1. Confermare la reimpostazione. Il dispositivo verrà riavviato e verrà visualizzato un set di ingranaggi rotanti e un indicatore di stato.
1. Attendere circa 30 minuti per il completamento del processo. Al termine, il dispositivo verrà riavviato nell'esperienza "predefinita".

## <a name="reinstall-the-operating-system"></a>Reinstallare il sistema operativo

Se il dispositivo ha ancora problemi dopo il riavvio e la reimpostazione, è possibile usare uno strumento di ripristino nel computer per reinstallare il HoloLens del sistema operativo e del firmware.  

I dati HoloLens necessario per la reimpostazione vengono in pacchetto in un aggiornamento flash completo (FFU), simile a un file con estensione iso, wim o vhd. [Informazioni sui formati di file di immagine FFU.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

È possibile installare un nuovo sistema operativo nel HoloLens (prima generazione) usando lo strumento di ripristino Windows dispositivo. Prima di usare questo strumento, verificare se il riavvio o la reimpostazione HoloLens il problema.

Il processo di ripristino può richiedere del tempo. Al termine, verrà installata la versione più recente Windows software Holographic.

Per usare lo strumento, è necessario un computer Windows 10 o versione successiva con almeno 4 GB di spazio di archiviazione disponibile. Non è possibile eseguire questo strumento in una macchina virtuale.

### <a name="recover-your-hololens"></a>Ripristinare il HoloLens

1. Scaricare e installare lo [strumento Windows ripristino dispositivi](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) nel computer.
1. Connessione il HoloLens (prima generazione) al computer usando il cavo MICRO USB fornito con il HoloLens.
1. Aprire lo strumento Windows ripristino del dispositivo e seguire le istruzioni.

Se il HoloLens (prima generazione) non viene rilevato automaticamente, selezionare **Il dispositivo non è stato rilevato.** Seguire quindi le istruzioni per impostare la modalità di ripristino del dispositivo.

### <a name="manual-flashing-mode"></a>Modalità flash manuale

Se il dispositivo non viene rilevato, seguire questa procedura per attivarla:

1. Scollegare il dispositivo da qualsiasi fonte di alimentazione.
1. Se il dispositivo è spento, tenere premuto **il** pulsante di alimentazione fino a quando non si spegne completamente.
2. Tenere premuto **il pulsante del volume** e toccare brevemente il pulsante **di** alimentazione. Il dispositivo dovrebbe avviarsi e visualizzare solo il LED centrale.
3. Collegare il dispositivo al PC.
4. Aprire lo strumento Windows ripristino del dispositivo.
5. Selezionare **Il dispositivo non è stato rilevato** e quindi **HoloLens**. 
6. Seguire le istruzioni per ripristinare il dispositivo.
