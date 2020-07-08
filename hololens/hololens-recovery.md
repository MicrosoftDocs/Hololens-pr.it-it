---
title: Riavviare, reimpostare o ripristinare HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857764"
---
# Riavviare, reimpostare o ripristinare HoloLens

## Ricaricare il dispositivo

Prima di avviare una procedura di risoluzione dei problemi, se possibile, assicurati che il dispositivo sia caricato almeno tra il 20% e il 40%.

Assicurati di usare il caricabatterie e i cavi USB di tipo C forniti insieme al dispositivo HoloLens 2. Nel caso in cui non siano disponibili, assicurati che il caricabatterie disponibile possa supportare almeno 15 W di potenza.

> [!NOTE]
> Se possibile, non usare un PC per caricare il dispositivo tramite USB, perché i tempi di ricarica sono molti lunghi.

Se il dispositivo viene avviato correttamente ed è in esecuzione, puoi controllare la ricarica della tua batteria in tre modi.

1. Andando nel menu principale dell’interfaccia utente di HoloLens.
2. Controllando il LED che si trova vicino al tasto di accensione (per il 40%, dovresti vedere almeno due LED fissi). 
3. Aprendo Esplora file nel proprio PC host, e cercando il dispositivo HoloLens 2 a sinistra, sotto “Questo PC”.
    
      a. Fai clic con il pulsante destro del mouse sul nome del dispositivo e scegli Proprietà. Viene mostrata una finestra di dialogo che mostra il livello della batteria per il dispositivo in uso.

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

Se non è possibile avviare il dispositivo nel menu di avvio, prendi nota dei LED e della numerazione del PC host, e segui la Guida alla risoluzione dei problemi (https://docs.microsoft.com/hololens/hololens-troubleshooting). Se lo stato del dispositivo non rientra in uno degli stati elencati nella Guida alla risoluzione dei problemi, esegui la **procedura di reimpostazione** senza riconnettere il dispositivo al PC host, ma connetterlo all’alimentazione. Attendere almeno un’ora che il dispositivo si ricarichi.

## Reimpostare il dispositivo

In alcuni casi, all’utente può essere richiesto di reimpostare manualmente il dispositivo, senza l’interfaccia utente del software. 

### Procedura standard
1. Scollega il dispositivo dall’alimentatore o dal PC host scollegando il cavo di tipo C.

2. Tieni premuto il **tasto di accensione** per 15 secondi. Tutti i LED devono essere spenti.

3. Attendi 2-3 secondi e premi brevemente il **pulsante di accensione**, i LED vicini al pulsante di accensione si accendono e il dispositivo inizia ad avviarsi. 

4. Connetti il dispositivo al PC host aprendo Gestione dispositivi (su Windows 10, premi il tasto **“Windows”** e quindi **“x”**, e fai poi clic su “Gestione dispositivi”) verificando che il dispositivo sia correttamente indicato come Microsoft HoloLens, come mostrato nelle immagini seguenti:

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### Procedura di reimpostazione manuale

Se la procedura di reimpostazione standard non funziona, è possibile usare la procedura di reimpostazione manuale.

1. Scollega il dispositivo dall’alimentatore o dal PC host scollegando il cavo di tipo C.

2. Tieni premuto **volume giù + tasto di accensione** per 15 secondi.

3. Il dispositivo viene riavviato automaticamente. 

4. Connetti il dispositivo al PC host aprendo Gestione dispositivi (su Windows 10, premi il tasto **“Windows”** e quindi **“x”**, e fai poi clic su “Gestione dispositivi”) verificando che il dispositivo sia correttamente indicato come Microsoft HoloLens, come mostrato nelle immagini seguenti.

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## Ripristino manuale del dispositivo

In situazioni straordinarie potrebbe essere necessario ripristinare manualmente il dispositivo. Ci sono due modi per ripristinare un dispositivo HoloLens2. Per tutte le procedure di ripristino, ti verrà chiesto di [installare l’app Advanced Recovery Companion tramite Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8). Se si ripristina il dispositivo, tutti i dati personali, le app e le impostazioni verranno eliminati, compreso il ripristino del TPM.

Advanced Recovery Companion scarica automaticamente la build di [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004). Se desideri scaricare il file FFU più recente di HoloLens 2 per ripristinare il dispositivo con Advanced Recovery Companion, lo puoi scaricare da [qui](https://aka.ms/hololens2download). Il file FFU viene tenuto aggiornato, e corrisponde alla build più recente disponibile. 

Prima di avviare la procedura di ripristino, verifica che l’app sia installata ed in esecuzione nel PC con Windows 10, e che sia pronta a rilevare il dispositivo.

![Ripristino manuale di HoloLens 2](images/ARC1.png)

### Procedura normale

1. Mentre il dispositivo HoloLens è acceso, connetterlo a un PC con Windows 10 su cui l’app Advanced Recovery Companion sia in esecuzione.

2. Il dispositivo verrà rilevato automaticamente, e l’interfaccia utente dell'app Advanced Recovery Companion sarà aggiornata nel modo seguente:

![Ripristino manuale di HoloLens 2](images/ARC2.png)

3. Seleziona il dispositivo HoloLens2 nell’interfaccia dell'app Advanced Recovery Companion, e segui le istruzioni per completare il ripristino.

### Procedura manuale

Se il dispositivo non si avvia correttamente, potrebbe essere necessario attivare la modalità di ripristino sull’HoloLens 2.

1. Scollega il dispositivo dall’alimentatore o dal PC host scollegando il cavo di tipo C. 

2. Tieni premuto il **tasto di accensione** per 15 secondi. Tutti i LED devono spegnersi. 

3. Mentre premi il pulsante **Volume più**, premi e rilascia il **tasto di accensione** per avviare il boot sul dispositivo. Attendi 15 secondi prima di rilasciare il pulsante Volume più. Dei 5 LED che si trovano sul dispositivo, si accende soltanto il LED centrale.

4. Connetti il dispositivo al PC host aprendo Gestione dispositivi (su Windows 10, premi il tasto **“Windows”** e quindi **“x”**, e fai poi clic su “Gestione dispositivi”) verificando che il dispositivo sia correttamente indicato come Microsoft HoloLens, come mostrato nell’immagine sottostante.

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. Il dispositivo viene rilevato automaticamente, e l'interfaccia utente dell’app Advanced Recovery Companion viene aggiornata come indicato di seguito:

![Ripristino manuale di HoloLens 2](images/ARC2.png)

6. Seleziona il dispositivo HoloLens 2 nell’interfaccia dell’app Advanced Recovery Companion, e segui le istruzioni per completare il ripristino.

## Download di ARC senza usare Windows Store

Se un ambiente IT impedisce l'uso dell’app Windows Store o limita l'accesso al negozio online, gli amministratori IT possono rendere disponibile l’app attraverso altri percorsi di distribuzione offline. 

- Questo processo può essere usato anche per altre app, come illustrato nel passaggio 2. Questa guida si concentra sulle funzionalità avanzate di ripristino, ma è possibile modificarle per altre app offline.  

Questo percorso di distribuzione può essere abilitato con la procedura seguente:
1.  Vai al sito web di [Store For Business](https://businessstore.microsoft.com) e accedi con un’identità di Azure Active Directory.
1.  Vai a **Gestione – Impostazioni**, e attiva **Mostra app offline** in **Esperienza di shopping** come descritto in https://businessstore.microsoft.com/manage/settings/shop 
1.  Vai **Compra per il gruppo** e cerca l’app [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1.  Cambia il valore della casella **Tipo licenza** su offline e fai clic su **Gestisci**.
1.  Nella sezione “Scarica il pacchetto per l’uso offline”, fai clic sul pulsante **“Scarica”**. Verifica che l’estensione del file sia .appxbundle.
1.  In questa fase, se il PC desktop è connesso a internet, ti basta fare doppio clic e installarlo. 
1.  Gli amministratori IT possono anche distribuire l’app con System Center Configuration Manager (SCCM) o Intune.
1.  Se il PC di destinazione non può connettersi a internet, sono necessari alcuni passaggi aggiuntivi: 
    1.  Seleziona la licenza non codificata e fai clic su **“Genera licenza”**, e clicca poi su **“Scarica”** in **“Framework necessari”**. 
    1.  I PC senza accesso a internet dovranno usare DISM per applicare il pacchetto con i file e la licenza. In un prompt dei comandi con privilegi di amministrazione, scrivi:

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> Il numero della versione di questo codice d’esempio potrebbe non corrispondere alla versione effettiva. Puoi anche specificare un percorso di scaricamento diverso da quello mostrato nell’esempio. Assicurati di apportare le modifiche necessarie.

> [!TIP]
> Se pianifichi di usare Advanced Recovery Companion per installare un file FFU offline, può essere utile scaricare localmente l’immagine di ripristino: qui trovi [il file immagine più recente di HoloLens 2](https://aka.ms/hololens2download). 

Altre risorse
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


