---
title: Guida alla valutazione di Windows Autopilot per HoloLens 2
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 3d98e67e79ae10b606c529adbda95dbb61b8fd15
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829444"
---
# Guida alla valutazione di Windows Autopilot per HoloLens 2

Quando si configurano i dispositivi HoloLens 2 per il programma Windows Autopilot, gli utenti possono seguire una semplice procedura per eseguire il provisioning dei dispositivi dal cloud.

Il programma Autopilot supporta la modalità di distribuzione automatica per eseguire il provisioning dei dispositivi HoloLens 2 come dispositivi condivisi nel tenant. La modalità di distribuzione automatica sfrutta l'immagine e i driver OEM preinstallati del dispositivo durante il processo di provisioning. Un utente può eseguire il provisioning del dispositivo senza lavorare sul dispositivo bensì utilizzando la Configurazione guidata.  

![Il processo di distribuzione automatica di Autopilot configura i dispositivi condivisi in modalità "headless" usando una connessione di rete.](./images/hololens-ap-intro.png)

Quando viene avviato il processo di distribuzione automatica di Autopilot, vengono seguiti i passaggi seguenti:

1. Aggiungere il dispositivo ad Azure Active Directory (Azure AD)
   > [!NOTE]  
   > Autopilot per HoloLens non supporta l’aggiunta ad Active Directory o ad Azure AD ibrido.
1. Utilizzare Azure AD per registrare il dispositivo in Microsoft Intune (o in un altro servizio MDM).
1. Eseguire il download dei criteri di destinazione del dispositivo, delle app, dei certificati e dei profili di rete di destinazione dell'utente.
1. Eseguire il provisioning del dispositivo.
1. Presentare la schermata di accesso all'utente.

## Windows Autopilot per HoloLens 2: attività iniziali

I passaggi seguenti riepilogano il processo di configurazione dell'ambiente per Windows Autopilot per HoloLens 2. Il resto di questa sezione contiene i dettagli della procedura.

1. Assicurarsi che siano soddisfatti i requisiti per Windows Autopilot per HoloLens.
1. Registrare il programma di Windows Autopilot per HoloLens 2.
1. Verificare che sia stata eseguita l’anteprima del tenant (registrato per partecipare al programma).
1. Registrare i dispositivi in Windows Autopilot.
1. Creare un gruppo di dispositivi.
1. Creare un profilo di distribuzione.
1. Verificare la configurazione ESP.
1. Configurare un profilo di configurazione personalizzato per i dispositivi HoloLens (problema noto).
1. Verificare lo stato del profilo dei dispositivi HoloLens.

### 1. Assicurarsi di soddisfare i requisiti per il Windows Autopilot per HoloLens
Per le informazioni più aggiornate su come partecipare al programma, rivedere le [Note sulla versione di Windows Insider](hololens-insider.md#windows-insider-release-notes).

Rivedere le sezioni seguenti dell'articolo sui requisiti di Windows Autopilot:

- [Requisiti di rete](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [Requisiti di licenza](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [Requisiti di configurazione](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)
> [!IMPORTANT]  
> A differenza di altri programmi di Windows Autopilot, Windows Autopilot per HoloLens 2 necessita di requisiti specifici del sistema operativo.

Rivedere la sezione "[Requisiti](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" dell'articolo sulla modalità di distribuzione automatica di Windows Autopilot. L'ambiente deve soddisfare questi requisiti, oltre ai requisiti standard di Windows Autopilot.

> [!NOTE]  
> Non è necessario rivedere le sezioni "Istruzioni dettagliate" e "Convalida" dell'articolo. Le procedure descritte più avanti in questo articolo forniscono i passaggi corrispondenti specifici di HoloLens.

> [!IMPORTANT]  
> Per informazioni su come registrare i dispositivi e configurare i profili, vedere [4. Registrare i dispositivi in Windows Autopilot](#4-register-devices-in-windows-autopilot) e [6. Creare un profilo di distribuzione](#6-create-a-deployment-profile) in questo articolo. Queste sezioni contengono procedure specifiche per HoloLens.

Prima di avviare il processo di configurazione guidata e di provisioning, accertarsi che i dispositivi HoloLens soddisfino i requisiti seguenti:

- I dispositivi non sono già membri di Azure AD e non sono registrati in Intune (o in un altro sistema MDM). Il processo di distribuzione automatica di Autopilot completa questi passaggi. Per fare in modo che tutte le informazioni relative al dispositivo siano pulite, controllare le pagine **Dispositivi** sia in Azure AD che in Intune.
- Ogni dispositivo può connettersi a Internet. È possibile usare le schede "USB C a Ethernet" per la connettività internet cablata o le schede "USB C a WiFi" per la connettività Internet wireless. 
- Ogni dispositivo può connettersi tramite cavo USB-C e il computer deve avere l’[Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) installato.
- Ogni dispositivo deve avere l’ultimo aggiornamento di Windows: Windows 10, versione 19041.1002.200107-0909 o una versione più recente

Per configurare e gestire i profili in modalità di distribuzione automatica di Autopilot, assicurarsi di avere accesso all'interfaccia di amministrazione di [Microsoft Endpoint Manager](https://endpoint.microsoft.com).

### 2. Registrarsi nel programma Windows Autopilot per HoloLens 2

Per partecipare al programma, è necessario usare un tenant in anteprima per HoloLens. Per eseguire questa operazione, andare a [Richiesta di anteprima privata di Windows Autopilot per HoloLens](https://aka.ms/APHoloLensTAP) oppure usare il codice QR seguente per inviare una richiesta.  

![Codice QR di Autopilot](./images/hololens-ap-qrcode.png)  

Durante la richiesta, tenere a portata di mano le seguenti informazioni:

- Dominio tenant
- ID tenant
- Numero di dispositivi HoloLens 2 che partecipano alla valutazione
- Numero di dispositivi HoloLens 2 che si prevede di distribuire usando la modalità di distribuzione automatica di Autopilot

### 3. Verificare che il tenant sia in anteprima

Per verificare che il tenant sia in anteprima per il programma di Autopilot dopo aver inviato la richiesta, procedere come segue:

1. Accedere all'interfaccia di amministrazione di [Microsoft Endpoint Manager](https://endpoint.microsoft.com).
1. Selezionare **Dispositivi** > **Windows** > **Registrazione di Windows** > **Profili di distribuzione di Windows Autopilot** > **Crea profilo**.  
   
   ![Il menu a discesa della voce “Crea profilo” include un elemento di HoloLens.](./images/hololens-ap-enrollment-profiles.png)
  Dovrebbe essere visualizzato un elenco che include **HoloLens**. Se questa opzione non è presente, usare una delle opzioni di [Feedback](#feedback) per contattarci.

### 4. Registrare i dispositivi in Windows Autopilot

Per registrare un dispositivo HoloLens nel programma di Windows Autopilot, è necessario ottenere il codice hash dell’hardware del dispositivo, detto anche ID hardware. Il dispositivo può registrare il codice hash dell’hardware in un file CSV durante il processo configurazione guidata o, in un secondo momento, quando il proprietario di un dispositivo avvia il processo di raccolta dei log di diagnostica (descritto nella procedura seguente). In genere, il proprietario del dispositivo è il primo utente che accede al dispositivo.

**Recuperare un codice hash dell’hardware del dispositivo**

1. Avviare il dispositivo HoloLens 2.
1. Sul dispositivo premere contemporaneamente i pulsanti Arresta e Riduzione volume, quindi rilasciarli. Il dispositivo raccoglie sia i log di diagnostica che il codice hash dell’hardware e li archivia in un gruppo di file con estensione .zip.
1. Usare un cavo USB-C per connettere il dispositivo a un computer.
1. Sul computer aprire Esplora file. Aprire **Questo PC\\\<\<*HoloLens device name*>\\Spazio di archiviazione interno\\Documenti** e individuare il file AutopilotDiagnostics.zip.  

   > [!NOTE]  
   > Il file con estensione .zip potrebbe non essere immediatamente disponibile. Se il file non è ancora pronto, è possibile che venga visualizzato un file HoloLensDiagnostics.temp nella cartella Documenti. Per aggiornare l'elenco di file, aggiornare la finestra.

1. Estrarre il contenuto del file AutopilotDiagnostics.zip.
1. Nei file estratti individuare il file CSV con prefisso del nome "DeviceHash". Copiare il file in un'unità del computer in cui è possibile accedervi in seguito.  
   > [!IMPORTANT]  
   > I dati nel file CSV devono usare le intestazioni e i formati di riga seguenti:
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**Registrare il dispositivo in Windows Autopilot**

1. Nell'interfaccia di amministrazione di Microsoft Endpoint Manager selezionare **Dispositivi** > **Windows** > **Registrazione di Windows**, quindi selezionare **Dispositivi** > **Importa** nel **Programma di distribuzione di Windows Autopilot**.

1. In **Aggiungi dispositivi di Windows Autopilot** selezionare il file CSV di DeviceHash, quindi **Apri**e infine **Importa**.  
   
   ![Usare il comando Importa per importare il codice hash dell’hardware.](./images/hololens-ap-hash-import.png)
1. Una volta completata l'importazione, selezionare **Dispositivi** > **Windows** > **Registrazione di Windows** > **Dispositivi** > **Sincronizza**. Il processo potrebbe richiedere alcuni minuti, a seconda del numero di dispositivi sincronizzati. Per vedere il dispositivo registrato, selezionare **Aggiorna**.  
   
   ![Usare i comandi Sincronizza e Aggiorna per visualizzare l'elenco dei dispositivi.](./images/hololens-ap-devices-sync.png)  

### 5. Creare un gruppo di dispositivi

1. Nell'interfaccia di amministrazione di Microsoft Endpoint Manager selezionare **Gruppi** > **Nuovo gruppo**.
1. Per il **Tipo di gruppo** selezionare **Sicurezza** e quindi immettere il nome e la descrizione del gruppo.
1. Per il **Tipo di appartenenza** selezionare **Assegnato** o **Dispositivo dinamico**.
1. Effettua una delle seguenti operazioni:  
   
   - Se è stato selezionato **Assegnato** per il **Tipo di appartenenza** nel passaggio precedente, selezionare **Membri** e quindi aggiungere i dispositivi di Autopilot al gruppo. I dispositivi di Autopilot che non sono stati ancora registrati vengono elencati usando il numero di serie del dispositivo come nome del dispositivo.
   - Se è stato selezionato **Dispositivi dinamici** per il **Tipo di appartenenza** nel passaggio precedente, selezionare **Membri dei dispositivi dinamici**e quindi immettere il codice nelle **Regole avanzate** simili alle seguenti:
     - Se si vuole creare un gruppo che includa tutti i dispositivi Autopilot digitare: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Mappe di campo dei tag di gruppo di Intune per l’attributo **OrderID** nei dispositivi Azure AD. Se si vuole creare un gruppo che includa tutti i dispositivi di Autopilot con un tag di gruppo specifico (come OrderID del dispositivo di Azure AD), è necessario digitare: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Se si vuole creare un gruppo che includa tutti i dispositivi di Autopilot con un ID ordine acquisto specifico, digitare: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Queste regole si riferiscono ad attributi univoci per i dispositivi di Autopilot.
1. Selezionare **Salva** e quindi **Crea**.

### 6. Creare un profilo di distribuzione

1. Nell'interfaccia di amministrazione di Microsoft Endpoint Manager selezionare **Dispositivi** > **Windows** > **Registrazione di Windows** > **Profili di configurazione di Windows Autopilot** > **Crea profilo** > **Hololens**.
1. Immettere il nome e la descrizione del profilo e quindi selezionare **Avanti**.  
   
   ![Aggiungere un nome e una descrizione del profilo](./images/hololens-ap-profile-name.png)
1. Nella pagina **Configurazione guidata (OOBE)**, la maggior parte delle impostazioni è preconfigurata per semplificare la configurazione guidata per la valutazione. È possibile configurare facoltativamente le impostazioni seguenti:  

   - **Lingua (area geografica)**: selezionare la lingua per la Configurazione guidata. È consigliabile selezionare una lingua dall'elenco di [lingue supportate per HoloLens 2](hololens2-language-support.md).
   - **Configurazione automatica della tastiera**: per assicurarsi che la tastiera corrisponda alla lingua selezionata, scegliere **Sì**.
   - **Applicare un modello di nome del dispositivo**: per impostare automaticamente il nome del dispositivo durante la Configurazione guidata, selezionare **Sì** e quindi immettere la frase e i segnaposto del modello in **Immettere un nome**. Ad esempio, immettere un prefisso e `%RAND:4%`&mdash;un segnaposto per un numero casuale di quattro cifre.
     > [!NOTE]  
     > Se si usa un modello di nome del dispositivo, il processo di Configurazione guidata riavvia il nuovo dispositivo ancora una volta dopo l’applicazione del nome del dispositivo e prima dell’aggiunta del dispositivo ad Azure AD. Il riavvio consente l’applicazione del nuovo nome.  

   ![Configurare le impostazioni della Configurazione guidata.](./images/hololens-ap-profile-oobe.png)
1. Dopo aver configurato le impostazioni, selezionare **Avanti**.
1. Nella pagina **Tag degli ambiti** è possibile aggiungere facoltativamente i tag degli ambiti che si vogliono applicare al profilo. Per altre informazioni sui tag degli ambiti, vedere [Usare il controllo di accesso basato sui ruoli e i tag degli ambiti per l’IT distribuito](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Al termine, selezionare **Avanti**.
1. Nella pagina **Assegnazioni** selezionare **Gruppi selezionati** per **Assegna a**.
1. In **GRUPPI SELEZIONATI** scegliere **+ Seleziona gruppi da includere**.
1. Nell'elenco **Seleziona gruppi da includere** scegliere il gruppo di dispositivi creato per i dispositivi HoloLens di Autopilot e quindi selezionare **Avanti**.  
  
   Se si vogliono escludere i gruppi, scegliere **Seleziona gruppi da escludere** e scegliere i gruppi da escludere.

   ![Assegnare un gruppo di dispositivi al profilo.](./images/hololens-ap-profile-assign-devicegroup.png)
1. Nella pagina **Rivedi + Crea**, rivedere le impostazioni e quindi selezionare **Crea** per creare il profilo.  
   
   ![Rivedi + Crea](./images/hololens-ap-profile-summ.png)

### 7. Verificare la configurazione ESP

La Pagina dello stato di registrazione (ESP) visualizza lo stato del processo di configurazione completo del dispositivo, che viene eseguito quando un utente gestito da MDM accede a un dispositivo per la prima volta. Assicurarsi che la configurazione ESP sia analoga alla seguente e verificare che le assegnazioni siano corrette.  

![Configurazione ESP](./images/hololens-ap-profile-settings.png)

### 8. Verificare lo stato del profilo dei dispositivi HoloLens.

1. Nell'interfaccia di amministrazione di Microsoft Endpoint Manager selezionare **Dispositivi** > **Windows** > **Registrazione di Windows** > **Dispositivi**.
1. Verificare che i dispositivi HoloLens siano presenti nell'elenco e che lo stato del profilo sia **Assegnato**.  
   > [!NOTE]  
   > Potrebbe essere necessario attendere alcuni minuti prima che il profilo venga assegnato al dispositivo.  
   
   ![Assegnazioni di dispositivi e profilo.](./images/hololens-ap-devices-assignments.png)

## Esperienza utente di Windows Autopilot per HoloLens 2

Gli utenti di HoloLens possono seguire questi passaggi per eseguire il provisioning di dispositivi HoloLens.  

1. Usare il cavo USB-C per connettere il dispositivo HoloLens a un computer in cui è installato il Companion di ripristino avanzato (ARC) ed è stato eseguito il corretto download dell’aggiornamento di Windows.
1. Usare il Companion di ripristino avanzato per attivare la versione appropriata di Windows nel dispositivo.
1. Connettere il dispositivo alla rete e quindi riavviare il dispositivo.  
   > [!IMPORTANT]  
   > È necessario connettere il dispositivo alla rete prima dell'avvio della Configurazione guidata (OOBE). Il dispositivo determina se il provisioning avviene su un dispositivo di Autopilot mentre si trova nella prima schermata della Configurazione guidata. Se il dispositivo non riesce a connettersi alla rete o se si sceglie di non eseguire il provisioning come dispositivo di Autopilot, non sarà possibile passare al provisioning di Autopilot in un secondo momento. In alternativa, è necessario avviare questa procedura per eseguire il provisioning del dispositivo come dispositivo di Autopilot.

   Il dispositivo dovrebbe avviare automaticamente la Configurazione guidata. Non interagire con la Configurazione guidata. Al contrario, è consigliabile attendere semplicemente. Consentire a HoloLens 2 di rilevare la connettività di rete e di completare automaticamente la Configurazione guidata. Il dispositivo può essere riavviato durante la Configurazione guidata. Le schermate della Configurazione guidata devono essere simili alle seguenti.
   
   ![Passaggio 1 della Configurazione guidata](./images/hololens-ap-uex-1.png)
   ![Passaggio 2 della Configurazione guidata](./images/hololens-ap-uex-2.png)
   ![Passaggio 3 della Configurazione guidata](./images/hololens-ap-uex-3.png)
   ![Passaggio 4 della Configurazione guidata](./images/hololens-ap-uex-4.png)

Alla fine della Configurazione guidata, è possibile accedere al dispositivo usando il nome utente e la password.

  ![Passaggio 5 della Configurazione guidata](./images/hololens-ap-uex-5.png)

## Problemi noti

- Non è possibile installare applicazioni che usano il contesto di sicurezza dispositivi.

## Feedback

Per inviare feedback e suggerimenti o segnalare problemi, usare uno dei metodi seguenti:

- Usare l’app Hub di Feedback. Questa app è disponibile in un computer connesso a HoloLens. Nell'app Hub di Feedback selezionare la categoria **Gestione dell’impresa** > **Dispositivo**.  

  Quando dai un feedback o segnali un problema, fornisci una descrizione dettagliata. Se possibile, includere screenshot e log.
- Inviare un messaggio di posta elettronica all’indirizzo [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com). Per l'oggetto del messaggio di posta elettronica, immettere **\<*Tenant*> Feedback di valutazione di Autopilot per HoloLens 2**, (in cui \<*Tenant*> è il nome del tenant di Intune).

  Fornire una descrizione dettagliata nel messaggio. Tuttavia, a meno che il personale di assistenza non lo chieda specificamente, non includere dati come screenshot o log. Questi dati possono includere informazioni private o personali.
