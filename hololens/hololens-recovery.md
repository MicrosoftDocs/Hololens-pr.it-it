---
title: Riavviare, reimpostare o ripristinare HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Come usare Advanced Recovery Companion per eseguire il flash di un'immagine per HoloLens 2.
keywords: procedura, riavvio, ripristino, ripristino, hard reset, soft reset, ciclo di alimentazione, HoloLens, arresto, arco, complementare per il ripristino avanzato
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: afd782df1c68e8441b14823e0d961317914140e3
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397362"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Riavviare, reimpostare o ripristinare HoloLens 2

## <a name="charge-the-device"></a>Caricare il dispositivo

>[!IMPORTANT]
> Prima di avviare qualsiasi procedura di risoluzione dei problemi, assicurarsi che al dispositivo venga addebitato un addebito dal **20 al 40%** della capacità della batteria, se possibile. Le [luci dell'indicatore](hololens2-setup.md#lights-that-indicate-the-battery-level) della batteria che si trovano sotto il pulsante di alimentazione sono un modo rapido per verificare la capacità della batteria senza accedere al dispositivo.

Usare il [caricabatterie](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) e il cavo USB Type-C fornito con il HoloLens 2 perché è il modo migliore per caricare il dispositivo. Il caricabatterie fornisce 18W di alimentazione (9 V a 2A). Usando il caricatore a parete fornito, HoloLens 2 i dispositivi possono ricaricare la batteria in meno di 65 minuti quando il dispositivo è in standby. Se questi accessori non sono disponibili, assicurarsi che il caricabatterie disponibile supporti almeno 15W di alimentazione.

> [!NOTE]
> Se possibile, evitare di usare un PC per caricare il dispositivo tramite USB, che è lento.

Se il dispositivo viene avviato e in esecuzione correttamente, è possibile controllare il livello di carica della batteria in tre modi:

- Dal menu principale dell'interfaccia utente del dispositivo HoloLens.
- Visualizzare il LED vicino al pulsante di accensione (per un addebito del 40%, dovrebbero essere visualizzati almeno due LED solidi).
    - Quando il dispositivo è in carica, l'indicatore della batteria si accende per indicare il livello di carica corrente.  L'ultima luce si dissolverà in entrata e in uscita per indicare la ricarica attiva.
    - Quando HoloLens è on, l'indicatore della batteria visualizza il livello della batteria in cinque incrementi.
    - Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%.
    - Se il livello della batteria è criticamente basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente e quindi si spegne.
- Nel PC host aprire **Esplora file** e cercare il dispositivo HoloLens 2 sul lato sinistro in Questo **PC.** Fare clic con il pulsante destro del mouse sul dispositivo e **scegliere Proprietà.** Verrà visualizzata una finestra di dialogo con il livello di carica della batteria.

   ![Una schermata HoloLens 2 proprietà mostra il livello di modifica della batteria](images/ResetRecovery2.png)

Se il dispositivo non può essere avviato nel menu di avvio, prendere nota dell'aspetto del LED e dell'enumerazione del dispositivo nel PC host. Seguire quindi la guida [alla risoluzione dei problemi](hololens-troubleshooting.md). Se lo stato del dispositivo non corrisponde ad alcuno degli stati [](hololens-recovery.md#hard-reset-procedure) elencati nella guida alla risoluzione dei problemi, eseguire la procedura di ripristino con il dispositivo connesso all'alimentatore, non al PC host. Attendere almeno un'ora per l'addebito del dispositivo.

## <a name="reset-the-device"></a>Reimpostare il dispositivo

In determinate circostanze potrebbe essere necessario reimpostare manualmente il dispositivo senza usare l'interfaccia utente del software.

### <a name="standard-procedure"></a>Procedura standard

1. Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.

2. Tenere premuto il **pulsante di** alimentazione per 15 secondi. Tutti i LED devono essere disattivati.

3. Attendere 2-3 secondi e quindi premere brevemente il **pulsante di** alimentazione. I LED vicini al pulsante di alimentazione si accenderanno e il dispositivo inizierà ad avviarsi.

4. Connettere il dispositivo al PC host e quindi aprire Gestione dispositivi. Ad Windows 10, premere **il tasto Windows** e quindi il tasto **X** e quindi selezionare **Gestione dispositivi.** Assicurarsi che il dispositivo enumeri correttamente *come Microsoft HoloLens* come illustrato nell'immagine seguente:

   ![HoloLens 2 responsabile devivo MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Procedura di reimpostazione rigida

Se la procedura di reimpostazione standard non ha funzionato, usare la procedura di reimpostazione rigida:

1. Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.

2. Tenere premuti **i pulsanti di risparmio**  +  **energia** del volume per 15 secondi. Il dispositivo verrà riavviato automaticamente.

4. Connettere il dispositivo al PC host.

5. Aprire Gestione dispositivi (per Windows 10 premere il **tasto Windows** e quindi il **tasto X** e quindi selezionare Gestione **dispositivi**). Assicurarsi che il dispositivo venga enumerato correttamente *Microsoft HoloLens* come illustrato nell'immagine seguente:

   ![HoloLens 2 dispositivo MicrosoftHoloLensRecovery maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Pulire il dispositivo

In situazioni straordinarie, potrebbe essere necessario "pulire flash" il HoloLens 2. Si noti che clean-reflash non dovrebbe influire sui problemi seguenti:
- [Uniformità dei colori di visualizzazione](hololens2-display.md)
- Avvio con audio ma nessun output di visualizzazione
- [Modello a 1-3-5 LED](hololens2-setup.md#lights-to-indicate-problems)
- [Surriscaldamento](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Arresti anomali del sistema operativo (diversi dagli arresti anomali dell'applicazione)

Esistono due modi per eseguire il reflash del dispositivo. Per entrambi, è prima [necessario installare Advanced Recovery Companion da Windows Store.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)

>[!WARNING]
>Se si rifiuta il dispositivo, tutti i dati personali, le app e le impostazioni verranno cancellati, incluse le informazioni di reimpostazione TPM.

Per impostazione predefinita, Advanced Recovery Companion è impostato per scaricare la [](hololens-release-notes.md#) build di rilascio delle funzionalità più recente. Vedere qui per leggere le note sulla versione per informazioni sulla versione più recente delle funzionalità. Per ottenere il pacchetto HoloLens 2 Full Flash Update (FFU) più recente per il reflash del dispositivo tramite Advanced Recovery Companion, fare clic qui per scaricare l'immagine HoloLens 2 [mensile più recente.](https://aka.ms/hololens2download) Questa versione è l'ultima build disponibile a livello generale.

Prima di avviare la procedura reflash, verificare che l'app sia installata e in esecuzione nel PC Windows 10 e sia pronta per rilevare il dispositivo. Assicurati anche che l'addebito di HoloLens sia minimo del 40%.

![HoloLens 2 schermata clean reflash](images/ARC1.png)

### <a name="normal-procedure"></a>Procedura normale

1. Mentre il dispositivo HoloLens è in esecuzione, connetterlo al PC Windows 10 in cui è stata aperta in precedenza l'app Complementare per il ripristino avanzato.
 
   Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:

   ![HoloLens 2 iniziale della reflash pulita](images/ARC2.png)

3. Selezionare il HoloLens 2 nell'interfaccia utente dell'app Advanced Recovery Companion e seguire le istruzioni per completare la reflash.

### <a name="manual-procedure"></a>Procedura manuale

Se il HoloLens 2 non viene avviato correttamente o se Advanced Recovery Companion non riesce a rilevare il dispositivo, potrebbe essere necessario impostare il dispositivo in modalità di ripristino:

1. Scollegare il cavo Type-C per scollegare il dispositivo dall'alimentatore o dal PC host.

2. Tenere premuto il **pulsante di** alimentazione per 15 secondi. Tutti i LED devono essere disattivati.

3. Mentre si preme **il pulsante del volume** verso l'alto, premere e rilasciare il **pulsante** di alimentazione per avviare il dispositivo. Attendere 15 secondi e quindi rilasciare il **pulsante di volume** in alto. Solo il LED centrale dei cinque LED si accende.

4. Connettere il dispositivo al PC host e aprire Gestione dispositivi. Ad esempio Windows 10 premere **il tasto Windows,** quindi **il tasto X** e quindi selezionare **Gestione** dispositivi. Assicurarsi che il dispositivo venga enumerato correttamente Microsoft HoloLens come illustrato nell'immagine seguente:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   Il dispositivo verrà rilevato automaticamente e l'interfaccia utente dell'app Advanced Recovery Companion avvia il processo di aggiornamento:

   ![HoloLens 2 schermata di reflash pulita](images/ARC2.png)

6. Selezionare il dispositivo HoloLens 2 nell'interfaccia utente dell'app Advanced Recovery Companion e quindi seguire le istruzioni per completare il reflash.

## <a name="troubleshoot-advanced-recovery-companion"></a>Risolvere i problemi di Advanced Recovery Companion

1. Assicurarsi che al dispositivo venga addebitato un addebito del 40% o superiore prima di provare a eseguire il flashing.

2. Verificare che il dispositivo sia sbloccato.

3. Se ARC non rileva il dispositivo, assicurarsi di potersi connettere al dispositivo tramite Esplora file sul PC. Se non è possibile;

    1.  È possibile che il dispositivo abbia criteri USB che disabilitano la connessione. In tal caso, provare [la modalità Flashing manuale.](hololens-recovery.md#manual-procedure)
    2.  Se non sono presenti criteri, provare un cavo USB diverso.

1. Verificare che nel dispositivo non sia visualizzato un modello a [1-3-5 LED.](hololens2-setup.md#lights-to-indicate-problems)

## <a name="download-arc-without-using-the-app-store"></a>Scaricare ARC senza usare l'App Store

Se l'ambiente IT impedisce l'uso dell'app di Windows Store o limita l'accesso al negozio al dettaglio, l'amministratore IT può rendere disponibile l'app tramite un percorso di distribuzione "offline".

 >[!NOTE]
 > - Gli amministratori IT possono anche distribuire questa app tramite System Center Gestione configurazione (SCCM) o Intune.
 > - Questa guida è incentrata su Advanced Recovery Companion, ma il processo può essere usato anche per altre app "offline".

Seguire questa procedura per abilitare il percorso di distribuzione:

1. Passare al [Microsoft Store per le aziende](https://businessstore.microsoft.com) e accedere usando un'Azure Active Directory identità.

1. Passare a **Gestisci - Impostazioni**. Attivare Mostra **app offline in** Esperienza di **acquisto**.

1. Passare a **Cercare il gruppo e** cercare Advanced Recovery [**_Companion._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)

1. Impostare License **Type (Tipo di** ***licenza) su* _offline_ _ e selezionare _ Manage (Gestisci).**

1. In **Scarica il pacchetto per l'uso offline** selezionare il secondo pulsante blu **Scarica.** Assicurarsi che l'estensione del file *sia appxbundle.*

    - In questa fase, se il PC desktop ha accesso a Internet, fare doppio clic sul pacchetto per installare l'app.

    - Se il PC di destinazione non ha connettività Internet, seguire questa procedura:
       1. Selezionare la licenza non codificata e quindi selezionare **Genera licenza**.
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
