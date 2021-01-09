---
title: Riavviare, reimpostare o ripristinare HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Come usare Advanced Recovery Companion per installare un file immagine su HoloLens 2.
keywords: guida, riavvio, reset, ripristino, ripristino manuale, ripristino automatico, ciclo di alimentazione, HoloLens, spegnimento, arc, advanced recovery companion
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
ms.openlocfilehash: 7845a00d1141fb721683c4e3f2a884ed0c37c735
ms.sourcegitcommit: 33911e3b405732d0d31a27039c8f590d52b647c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "11254833"
---
# Riavviare, reimpostare o ripristinare HoloLens 2

## Caricare il dispositivo

Prima di avviare una procedura di risoluzione dei problemi, accertarsi che il dispositivo sia caricato almeno dal 20 al 40% della capacità della batteria, se possibile. Assicurarsi di usare il caricabatterie e i cavi USB di tipo C forniti insieme al dispositivo HoloLens 2. L'alimentatore e il cavo USB da C a C forniti con il dispositivo sono il modo migliore per ricaricare HoloLens 2. Il caricabatterie fornisce 18 W di alimentazione (9V a 2A). Con il caricabatterie a parete in dotazione, i dispositivi HoloLens 2 possono caricare completamente la batteria in meno di 65 minuti quando il dispositivo è in standby. In caso questi non fossero disponibili, assicurarsi che il caricabatterie disponibile possa supportare almeno 15 W di potenza.

> [!NOTE]
> Se possibile, evitare di usare un PC per caricare il dispositivo tramite USB, visto che tale processo sarebbe lento.

Se il dispositivo viene avviato correttamente ed è in esecuzione, è possibile controllare il livello di carica della batteria in tre modi:

- Dal menu principale dell’interfaccia utente di HoloLens.
- Controllare il LED che si trova vicino al tasto di accensione (con il 40% di carica, si dovrebbero vedere almeno due LED fissi). 
    - Quando il dispositivo è in carica, l'indicatore della batteria si illumina per indicare il livello di carica corrente.  L'ultima luce si accenderà e spegnerà per indicare che la ricarica è attiva.
    - Quando il dispositivo HoloLens è acceso, l'indicatore della batteria mostra il livello di batteria in cinque incrementi.
    - Quando solo una delle cinque luci è accesa, il livello della batteria è inferiore al 20%.
    - Se il livello della batteria è molto basso e tenti di accendere il dispositivo, una luce lampeggia per un breve periodo, quindi scompare.
- Aprire **Esplora file** sul proprio PC host, e cercare il dispositivo HoloLens 2 a sinistra, sotto **Questo PC**. Fare clic con il pulsante destro del mouse sul dispositivo e selezionare **Proprietà**. Una finestra di dialogo mostrerà il livello di carica della batteria.

   ![Schermata delle proprietà di HoloLens 2 che mostra il livello di variazione della batteria](images/ResetRecovery2.png)

Se il dispositivo non riesce a eseguire il boot al menu di avvio, prendere nota dell'aspetto del LED e dell'elenco dei dispositivi sul PC host. Seguire quindi le [istruzioni per la risoluzione dei problemi](https://docs.microsoft.com/hololens/hololens-troubleshooting). Se lo stato del dispositivo non rientra tra quelli elencati nella guida alla risoluzione dei problemi, eseguire la [procedura di reimpostazione forzata](hololens-recovery.md#hard-reset-procedure) connettendo il dispositivo all’alimentazione anziché al PC host. Attendere almeno un’ora che il dispositivo si ricarichi.

## Reimpostare il dispositivo

In alcuni casi, all’utente può essere richiesto di reimpostare manualmente il dispositivo, senza l’utilizzo dell’interfaccia utente del software.

### Procedura standard

1. Scollegare il dispositivo dall’alimentatore o dal PC host scollegando il cavo di Tipo C.

2. Tenere premuto il pulsante di **accensione** per 15 secondi. Tutti i LED devono essere spenti.

3. Attendere 2-3 secondi, quindi premere brevemente il pulsante di **accensione**. I LED vicini al pulsante di accensione si accenderanno e il dispositivo inizierà ad avviarsi.

4. Connettere il dispositivo al PC host e quindi aprire Gestione Dispositivo. (Per Windows 10, premere il tasto **Windows** e quindi il tasto **X**, selezionando successivamente **Gestione Dispositivo**.) Verificare che il dispositivo sia correttamente indicato come *Microsoft HoloLens* come mostrato nell’immagine seguente:

   ![HoloLens 2 MicrosoftHoloLensRecovery device manager](images/MicrosoftHoloLens_DeviceManager.png)

### Procedura di reimpostazione manuale

Se la procedura di reimpostazione standard non funziona, è possibile usare la procedura di reimpostazione forzata:

1. Scollegare il dispositivo dall’alimentatore o dal PC host scollegando il cavo di Tipo C.

2. Tenere premuti i pulsanti **volume verso il basso** + e**accensione** per 15 secondi. Il dispositivo verrà riavviato automaticamente.

4. Connettere il dispositivo al PC host.
5. Aprire Gestione Dispositivo (per Windows 10 premere il tasto **Windows** e quindi **X** e successivamente selezionare **Gestione Dispositivo**). Verificare che il dispositivo sia correttamente indicato come *Microsoft HoloLens* come mostrato nell’immagine seguente:

   ![HoloLens 2 MicrosoftHoloLensRecovery device manager 2](images/MicrosoftHoloLens_DeviceManager.png)

## Riconfigurare il dispositivo

In situazioni straordinarie potrebbe essere necessario riconfigurare HoloLens 2. Tenere presente che la riconfigurazione non condiziona questi problemi:
- [Uniformità del colore dello schermo](hololens2-display.md)
- Avvio con i suoni ma senza segnale video
- [Pattern LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems)
- [Surriscaldamento](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Arresti anomali del sistema operativo (distinti dagli arresti delle applicazioni)

Ci sono due modi per riconfigurare il dispositivo. Per entrambi,è necessario installare prima [Advanced Recovery Companion da Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Se si riconfigura il dispositivo, tutti i dati personali, le app e le impostazioni verranno eliminate, comprese le informazioni sul ripristino del TPM.

Per impostazione predefinita, Advanced Recovery Companion è impostato per scaricare la build dell'ultimo release funzionale, controllare qui per leggere le [Note sulla versione](hololens-release-notes.md#) per informazioni sull'ultimo release funzionale. Per ottenere il pacchetto più recente di HoloLens 2 Full Flash Update (FFU) per reflashare il dispositivo tramite Advanced Recovery Companion, [fare clic qui per scaricare l'ultima immagine mensile di HoloLens 2](https://aka.ms/hololens2download). Questa versione è generalmente la build più recente disponibile.

Prima di avviare la procedura di riconfigurazione, assicurarsi che l’app sia installata ed in esecuzione su un PC dotato di Windows 10 e pronto a rilevare il dispositivo. Inoltre, assicurarsi che HoloLens sia caricato almeno al 40%.

![Schermata di riconfigurazione di HoloLens 2](images/ARC1.png)

### Procedura normale

1. Mentre il dispositivo HoloLens è acceso, connetterlo a un PC dotato di Windows 10 su cui l’app Advanced Recovery Companion sia già in esecuzione.
 
   Il dispositivo verrà rilevato automaticamente, e l'interfaccia utente dell’app Advanced Recovery Companion avvierà l’aggiornamento:

   ![Schermata iniziale di riconfigurazione di HoloLens 2](images/ARC2.png)

3. Seleziona il dispositivo HoloLens 2 nell’interfaccia dell’app Advanced Recovery Companion, e segui le istruzioni per completare la riconfigurazione.

### Procedura manuale

Se HoloLens 2 non si avvia correttamente, potrebbe essere necessario attivare la modalità di ripristino:

1. Scollegare il dispositivo dall’alimentatore o dal PC host scollegando il cavo di Tipo C.

2. Tenere premuto il pulsante di **accensione** per 15 secondi. Tutti i LED devono spegnersi.

3. Mentre si tiene premuto il pulsante **volume verso l’alto**, premere e rilasciare il tasto di **accensione** per avviare il dispositivo. Attendere 15 secondi e, successivamente, rilasciare il pulsante **volume verso l’alto**. Dei cinque LED, dovrebbe illuminarsi solo quello centrale.

4. Connettere il dispositivo al PC host e aprire Gestione Dispositivo. (Per Windows 10, premere il tasto **Windows** e quindi il tasto **X**, selezionando successivamente **Gestione Dispositivo**.) Verificare che il dispositivo sia correttamente indicato come Microsoft HoloLens come mostrato nell’immagine seguente:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   Il dispositivo verrà rilevato automaticamente, e l'interfaccia utente dell’app Advanced Recovery Companion avvierà l’aggiornamento:

   ![Schermo di riconfigurazione di HoloLens 2](images/ARC2.png)

6. Selezionare il dispositivo HoloLens 2 nell’interfaccia utente dell’app Advanced Recovery Companion e seguire le istruzioni per completare la riconfigurazione.

## Download di ARC senza l’utilizzo dell’app store

Se l’ambiente IT impedisce l'uso dell’app Windows Store o limita l'accesso al negozio online, gli amministratori IT possono rendere disponibile l’app attraverso altri percorsi di distribuzione offline.

 >[!NOTE]
 > - Gli amministratori IT possono anche distribuire l’app attraverso il System Center Configuration Manager (SCCM) o Intune.
 > - Questa guida si concentra sull’Advanced Recovery Companion, ma è possibile utilizzare lo stesso processo per altre app “offline”.

Per abilitare il percorso di distribuzione, seguire questa procedura:
1. Passare al [Microsoft Store per le aziende](https://businessstore.microsoft.com) ed accedere usando un'identità Azure Active Directory.

1. Passare a **Gestione-impostazioni**. Attivare **Mostra le app offline** **nell’esperienza Shopping**.
1. Accedere a **Shop for My Group**e cercare [ * *_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1. Cambiare il _ *tipo di licenza** in **_offline_*_ e selezionare _ * Manage * *.
1. In **Scarica il pacchetto per l’uso offline**, selezionare il pulsante **Download**. Verificare che l’estensione del file sia *.appxbundle*.

    - A questo punto, se il PC è connesso a internet, un doppio clic sul pacchetto avvierà l’installazione dell’app.

    - Se il PC non è connesso a Internet, procedere come segue:
       1. Selezionare la licenza decodificata e quindi selezionare **Crea licenza**.
       2. In **Framework Necessari**, selezionare **Download**.
       3. Usare DISM per applicare al pacchetto la dipendenza e la licenza. Da un prompt dei comandi con privilegi di amministratore, eseguire il seguente comando:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > Il numero della versione di questo codice d’esempio potrebbe non corrispondere alla versione attualmente disponibile. Si potrebbe aver scelto anche un percorso di download diverso da quello mostrato nell’esempio. Modificare il comando in base alle proprie esigenze.

> [!TIP]
> Se si prevede di usare l’Advanced Recovery Companion per installare una FFU offline, può essere utile scaricare l'immagine flash. [**Scaricare l'immagine corrente per HoloLens 2**](https://aka.ms/hololens2download).

Altre risorse
- [Distribuire app offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [Pacchetto di app DISM (appx o appxbundle) opzioni di manutenzione della riga di comando](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
