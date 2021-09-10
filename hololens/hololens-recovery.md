---
title: Riavviare, reimpostare o ripristinare HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Come usare Advanced Recovery Companion per eseguire il flash di un'immagine per HoloLens 2.
keywords: procedura, riavvio, ripristino, ripristino, hard reset, soft reset, ciclo di alimentazione, HoloLens, arresto, arco, complementare per il ripristino avanzato
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 08/30/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: e9aad32891bb093cbce18671b76549788b19afcb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427830"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Riavviare, reimpostare o ripristinare HoloLens 2

>[!IMPORTANT]
> Prima di avviare qualsiasi procedura di risoluzione dei problemi, assicurarsi che al dispositivo venga addebitato un addebito dal **20 al 40%** della capacità della batteria, se possibile. Le [luci dell'indicatore della](hololens2-setup.md#lights-that-indicate-the-battery-level) batteria posizionate sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.

Usare il [caricabatterie](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) e il cavo USB Type-C fornito con il HoloLens 2 perché è il modo migliore per caricare il dispositivo. Il caricabatterie fornisce 18W di alimentazione (9 V a 2A). Usando il caricabatterie a parete fornito, i dispositivi HoloLens 2 ricaricare la batteria in meno di 65 minuti quando il dispositivo è in standby. Se questi accessori non sono disponibili, assicurarsi che il caricabatterie disponibile supporti almeno 15W di alimentazione.

> [!NOTE]
> Se possibile, evitare di usare un PC per caricare il dispositivo tramite USB, che è lento.

Se il dispositivo viene avviato correttamente e in esecuzione, è possibile controllare il livello di carica della batteria in tre modi:

- Dal menu principale dell'interfaccia utente HoloLens dispositivo.
- Visualizzare il LED vicino al pulsante di accensione (per un addebito del 40%, dovrebbero essere visualizzati almeno due LED solidi).
    - Quando il dispositivo è in carica, l'indicatore della batteria si accende per indicare il livello di carica corrente.  L'ultima luce si dissolverà in entrata e in uscita per indicare la ricarica attiva.
    - Quando il HoloLens è on, l'indicatore della batteria visualizza il livello della batteria in cinque incrementi.
    - Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%.
    - Se il livello della batteria è criticamente basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente e quindi si spegne.
- Nel PC host aprire **Esplora file** e cercare il dispositivo HoloLens 2 sul lato sinistro in Questo **PC**. Fare clic con il pulsante destro del mouse sul dispositivo e **scegliere Proprietà**. Verrà visualizzata una finestra di dialogo con il livello di carica della batteria.

   ![Una HoloLens 2 delle proprietà mostra il livello di modifica della batteria.](images/ResetRecovery2.png)

Se il dispositivo non è in grado di avviare il menu di avvio, prendere nota dell'aspetto del LED e dell'enumerazione del dispositivo nel PC host. Seguire quindi la guida [alla risoluzione dei problemi](hololens-troubleshooting.md). Se lo stato del dispositivo non corrisponde a uno degli stati [](hololens-recovery.md#hard-reset-procedure) elencati nella guida alla risoluzione dei problemi, eseguire la procedura di ripristino con il dispositivo connesso all'alimentatore e non con il PC host. Attendere almeno un'ora per l'addebito del dispositivo.

## <a name="reset-the-device"></a>Reimpostare il dispositivo

In determinate circostanze, potrebbe essere necessario reimpostare manualmente il dispositivo senza usare l'interfaccia utente del software.

### <a name="standard-procedure"></a>Procedura standard

1. Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.

2. Tenere premuto il **pulsante** di alimentazione per 15 secondi. Tutti i LED devono essere spenti.

3. Attendere 2-3 secondi e quindi premere brevemente il **pulsante di** alimentazione. I LED vicini al pulsante di accensione si accenderanno e il dispositivo inizierà ad avviarsi.

4. Connessione il dispositivo nel PC host e quindi aprire Gestione dispositivi. Per Windows 10, premere il **Windows** e quindi **il tasto X** e quindi selezionare Gestione **dispositivi.** Assicurarsi che il dispositivo enumi correttamente *come Microsoft HoloLens* come illustrato nell'immagine seguente:

   ![HoloLens 2 MicrosoftHoloLensRecovery devive manager.](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Procedura di reimpostazione rigida

Se la procedura di reimpostazione standard non ha funzionato, usare la procedura di reimpostazione rigida:

1. Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.

1. Tenere **premuti i pulsanti di** risparmio  +  **energia** del volume per 15 secondi. Il dispositivo verrà riavviato automaticamente.

1. Connessione il dispositivo al PC host.

1. Aprire Gestione dispositivi (per Windows 10 premere **Windows** e quindi **il tasto X** e quindi selezionare **Gestione dispositivi**). Assicurarsi che il dispositivo enumi correttamente *come Microsoft HoloLens* come illustrato nell'immagine seguente:

   ![HoloLens 2 MicrosoftHoloLensRecovery Device Maanger 2.](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Pulire il dispositivo

In situazioni straordinarie, potrebbe essere necessario "pulire flash" il HoloLens 2. Si noti che clean-reflash non dovrebbe influire sui problemi seguenti:

- [Uniformità dei colori di visualizzazione](hololens2-display.md)
- Avvio con audio ma nessun output di visualizzazione
- [Modello a 1-3-5 LED](hololens2-setup.md#lights-to-indicate-problems)
- [Surriscaldamento](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Arresti anomali del sistema operativo (diversi dagli arresti anomali dell'applicazione)

Esistono due modi per eseguire il reflash del dispositivo. Per entrambi, è prima necessario [installare Advanced Recovery Companion da Windows Store.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)

>[!WARNING]
>Se si rifiuta il dispositivo, tutti i dati personali, le app e le impostazioni verranno cancellati, incluse le informazioni di reimpostazione TPM.

Per impostazione predefinita, Advanced Recovery Companion è impostato per scaricare la build di rilascio delle funzionalità più recente. Per altre informazioni sulla versione più recente delle funzionalità, vedere le [HoloLens 2 sulla versione.](hololens-release-notes.md) Per ottenere il pacchetto HoloLens 2 full flash update (FFU) più recente per il reflash del dispositivo tramite Advanced Recovery Companion, scaricare l'immagine HoloLens 2 mensile più recente: [https://aka.ms/hololens2download](https://aka.ms/hololens2download) . Questa versione è la build disponibile a livello generale più recente.

Prima di avviare la procedura di reflash, assicurarsi che l'app sia installata e in esecuzione nel PC Windows 10 e pronta per rilevare il dispositivo. Assicurarsi anche che al HoloLens sia addebitato un minimo del 40%.

![HoloLens 2 schermata del reflash pulito.](images/ARC1.png)

### <a name="normal-procedure"></a>Procedura normale

1. Mentre il HoloLens è in esecuzione, connetterlo al PC Windows 10 in cui è stata aperta in precedenza l'app Advanced Recovery Companion.

   Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:

   ![HoloLens 2 schermata iniziale del reflash pulito.](images/ARC2.png)

1. Selezionare il dispositivo HoloLens 2 nell'interfaccia utente dell'app Advanced Recovery Companion e seguire le istruzioni per completare il reflash.

### <a name="manual-procedure"></a>Procedura manuale

Potrebbe essere necessario impostare il dispositivo in modalità di ripristino se:

- Il HoloLens 2 non viene avviato correttamente
- Advanced Recovery Companion non è in grado di rilevare il dispositivo
- Non si conosce più la password o il PIN per un dispositivo con un solo utente

1. Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.

2. Tenere premuto il **pulsante** di alimentazione per 15 secondi. Tutti i LED devono essere spenti.

3. Mentre si preme il **pulsante di** accensione del volume, premere e **rilasciare** il pulsante di accensione per avviare il dispositivo. Attendere 15 secondi e quindi rilasciare il **pulsante volume up.** Solo il LED centrale dei cinque LED si accende.

4. Connessione il dispositivo nel PC host e aprire Gestione dispositivi. Ad esempio Windows 10 premere il **Windows** e quindi **il tasto X** e quindi selezionare Gestione **dispositivi.** Assicurarsi che il dispositivo enumi correttamente come Microsoft HoloLens come illustrato nell'immagine seguente:

   ![HoloLens 2 MicrosoftHoloLensRecovery.](images/MicrosoftHoloLensRecovery.png)

   Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:

   ![HoloLens 2 schermata di reflash pulita.](images/ARC2.png)

6. Selezionare il dispositivo HoloLens 2 nell'interfaccia utente dell'app Advanced Recovery Companion e quindi seguire le istruzioni per completare il reflash.

## <a name="troubleshoot-advanced-recovery-companion"></a>Risolvere i problemi di Advanced Recovery Companion

1. Assicurarsi che il dispositivo venga addebitato al 40% o più prima di provare a eseguire il flash.

1. Controllare che il dispositivo sia sbloccato.

1. Verificare che il dispositivo sia collegato direttamente al PC host, non a un hub.

1. Se il dispositivo non viene visualizzato come dispositivo di HoloLens/HoloLens in Driver bus seriali universali, controllare:
    1. **Porte**, come dispositivo Qualcomm HS-USB
    1. **Altri dispositivi**, come dispositivo QUSB_BULK: nel PC host mancano i driver necessari per rilevare il HoloLens. Fare clic con il pulsante destro del mouse e selezionare Aggiorna driver e cercare i driver online o selezionare Aggiornamenti facoltativi nelle impostazioni Windows [Aggiorna](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674). Dopo aver scaricato il driver, ARC dovrebbe essere in grado di rilevarlo.

1. Se ARC non rileva il dispositivo, assicurarsi di potersi connettere al dispositivo tramite Esplora file sul PC. Se non è possibile;

    1. È possibile che il dispositivo abbia criteri USB che disabilitano la connessione. In tal caso, provare [la modalità Flashing manuale.](hololens-recovery.md#manual-procedure)
    2. Se non sono presenti criteri, provare un cavo USB diverso.

1. Verificare che nel dispositivo non sia visualizzato un modello a [1-3-5 LED.](hololens2-setup.md#lights-to-indicate-problems)

## <a name="download-arc-without-using-the-app-store"></a>Scaricare ARC senza usare l'App Store

Se l'ambiente IT impedisce l'uso dell'app Windows Store o limita l'accesso al punto vendita al dettaglio, l'amministratore IT può rendere disponibile l'app tramite un percorso di distribuzione "offline".

 >[!NOTE]
 > - Gli amministratori IT possono anche distribuire questa app tramite System Center Configuration Manager (SCCM) o Intune.
 > - Questa guida è incentrata su Advanced Recovery Companion, ma il processo può essere usato anche per altre app "offline".

Per abilitare il percorso di distribuzione, seguire questa procedura:

1. Passare [all'Microsoft Store per le aziende](https://businessstore.microsoft.com) e accedere usando un'Azure Active Directory identità.

1. Passare a **Gestisci - Impostazioni**. Attivare Mostra **app offline in** Esperienza di **acquisto.**

1. Passare a **Cercare il gruppo e** cercare Advanced Recovery [**_Companion._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)

1. Impostare **License Type (Tipo di** ***licenza) su* _offline_ _ e selezionare _ Manage (Gestisci).**

1. In **Scarica il pacchetto per l'uso offline** selezionare il secondo pulsante blu **Scarica.** Assicurarsi che l'estensione del file *sia appxbundle.*

    - In questa fase, se il PC desktop ha accesso a Internet, fare doppio clic sul pacchetto per installare l'app.

    - Se il PC di destinazione non ha connettività Internet, seguire questa procedura:
       1. Selezionare la licenza non codificata e quindi selezionare **Genera licenza.**
       2. In **Framework necessari selezionare** **Scarica.**
       3. Usare Gestione e manutenzione immagini distribuzione per applicare il pacchetto con la dipendenza e la licenza. Da un prompt dei comandi dell'amministratore eseguire il comando seguente:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Il numero di versione in questo esempio di codice potrebbe non corrispondere alla versione attualmente disponibile. È anche possibile che sia stato scelto un percorso di download diverso rispetto all'esempio. Apportare eventuali modifiche al comando in base alle esigenze.

> [!TIP]
> Quando si prevede di usare Advanced Recovery Companion per installare un FFU offline, può essere utile scaricare l'immagine flash. [**Scaricare l'immagine corrente per HoloLens 2**](https://aka.ms/hololens2download).

Altre risorse:

- [Distribuire app offline](/microsoft-store/distribute-offline-apps) 
- [Opzioni della riga di comando per la manutenzione del pacchetto dell'app Gestione e manutenzione immagini distribuzione (con estensione appx o appxbundle)](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
