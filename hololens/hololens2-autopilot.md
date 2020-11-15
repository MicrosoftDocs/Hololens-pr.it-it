---
title: Windows Autopilot per HoloLens 2 (Anteprima privata)
description: Come configurare Autopilot nei dispositivi HoloLens 2.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: be9da0ec2f301705a0691bcfc9dcf9d75eac8922
ms.sourcegitcommit: cfbcdf562f949eef9cd797bbb08dfdf9f29e8fcd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168535"
---
# Windows Autopilot per HoloLens 2

Quando si configurano i dispositivi HoloLens 2 per il programma Windows Autopilot, gli utenti possono seguire una semplice procedura per eseguire il provisioning dei dispositivi dal cloud.

Il programma Autopilot supporta la modalità di distribuzione automatica per eseguire il provisioning dei dispositivi HoloLens 2 come dispositivi condivisi nel tenant. La modalità di distribuzione automatica sfrutta l'immagine e i driver OEM preinstallati del dispositivo durante il processo di provisioning. Un utente può eseguire il provisioning del dispositivo senza lavorare sul dispositivo bensì utilizzando la Configurazione guidata. Per altre informazioni su Windows Autopilot per Windows 10, fare clic [qui](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

Quando viene avviato il processo di distribuzione automatica di Autopilot, vengono seguiti i passaggi seguenti:

1. Aggiungere il dispositivo ad Azure Active Directory (Azure AD)

   > [!NOTE]  
   > Autopilot per HoloLens non supporta l’aggiunta ad Active Directory o ad Azure AD ibrido.
   
1. Utilizzare Azure AD per registrare il dispositivo in Microsoft Intune (o in un altro servizio MDM).

1. Eseguire il download dei criteri di destinazione del dispositivo, delle app, dei certificati e dei profili di rete di destinazione dell'utente.

1. Eseguire il provisioning del dispositivo.

1. Presentare la schermata di accesso all'utente.

## Anteprima privata di Windows Autopilot per HoloLens 2

Attenersi alla procedura seguente per configurare l'ambiente per l'anteprima privata:

1. Assicurarsi di soddisfare i requisiti per Windows Autopilot per HoloLens 2.

1. Registrarsi al programma di anteprima privata di Windows Autopilot per HoloLens 2.

1. Verificare che sia stata eseguita l’anteprima del tenant (registrato per partecipare al programma).

1. Registrare i dispositivi in Windows Autopilot.

1. Creare un gruppo di dispositivi.

1. Creare un profilo di distribuzione.

1. Verificare la configurazione ESP.

1. Configurare un profilo di configurazione personalizzato per i dispositivi HoloLens (problema noto).

1. Verificare lo stato del profilo dei dispositivi HoloLens.


### 1. Assicurarsi di soddisfare i requisiti per il Windows Autopilot per HoloLens 2

**Rivedere le sezioni seguenti dell'articolo sui requisiti di Windows Autopilot:**

- [Requisiti di rete](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [Requisiti di licenza](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [Requisiti di configurazione](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**Rivedere la sezione "[Requisiti](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" dell'articolo sulla modalità di distribuzione automatica di Windows Autopilot.** L'ambiente deve soddisfare questi requisiti, oltre ai requisiti standard di Windows Autopilot. Non è necessario rivedere le sezioni "Istruzioni dettagliate" e "Convalida" dell'articolo. Le procedure descritte più avanti in questo articolo forniscono i passaggi corrispondenti specifici di HoloLens. Per informazioni su come registrare i dispositivi e configurare i profili, vedere [4. Registrare i dispositivi in Windows Autopilot](#4-register-devices-in-windows-autopilot) e [6. Creare un profilo di distribuzione](#6-create-a-deployment-profile) in questo articolo. Queste sezioni contengono procedure specifiche per HoloLens.

> [!IMPORTANT]  
> Windows Autopilot per HoloLens 2 necessita di requisiti specifici del sistema operativo. Autopilot si basa sulla versione 2004 di Windows Holographic (build 19041.1103 o successiva) preinstallata nei dispositivi HoloLens. I dispositivi distribuiti entro la fine di settembre 2020 hanno la versione 1903 di Windows Holographic preinstallata. Contattare il proprio distributore per informazioni sui tempi di consegna dei dispositivi predisposti per Autopilot. Se si vuole partecipare all'anteprima privata, vedere le istruzioni e i requisiti riportati di seguito.

Informazioni specifiche su Autopilot per le versioni del sistema operativo HoloLens.
- Per usare Autopilot, è necessario che il dispositivo sia [Windows Holographic, versione 2004](hololens-release-notes.md#windows-holographic-version-2004) o versioni successive.

- Per usare Autopilot tramite Wi-Fi, il dispositivo deve avere[Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o più recente. Tuttavia, queste build possono ancora usare adattatori ethernet. 

- Nelle build [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2), è stata abilitata una nuova opzione di gestione dei dispositivi [Tenantlockdown CSP e Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).  

Se si vuole confermare la versione build sul dispositivo o aggiornarlo, collegarlo al PC Windows 10 e avviare [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8). 

**Se si vuole provare l’anteprima di Autopilot, prima di avviare il processo di configurazione guidata e di provisioning, accertarsi che i dispositivi HoloLens soddisfino i requisiti seguenti:**

- Assicurarsi che il dispositivo sia in Windows Holographic versione 2004 (Build 19041.1103 o versione successiva). Se il sistema operativo più recente non è preinstallato, è necessario eseguire manualmente l'aggiornamento usando il [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab). [Qui](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) è possibile trovare le istruzioni. 

- È necessario registrare i dispositivi in Windows Autopilot. Per informazioni su come registrare i dispositivi, vedere [4. Registrare i dispositivi in Windows Autopilot](#4-register-devices-in-windows-autopilot). Il percorso consigliato è quello di far registrare i dispositivi dal proprio distributore.  

- In [Windows Holographic, versione 2004](hololens-release-notes.md#windows-holographic-version-2004) i dispositivi devono essere connessi a Internet prima di attivare HoloLens e avviare il processo di provisioning di Autopilot. Connettere il dispositivo alla porta Ethernet con un adattatore "da USB-C a Ethernet" per una connettività internet cablata.

- In [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2), i dispositivi possono connettersi al Wi-Fi in Configurazione guidata per rilevare Autopilot. 

- I dispositivi non sono già membri di Azure AD e non sono registrati in Intune (o in un altro sistema MDM). Il processo di distribuzione automatica di Autopilot completa questi passaggi. Per fare in modo che tutte le informazioni relative al dispositivo siano pulite, controllare le pagine **Dispositivi** sia in Azure AD che nei portali di Intune.

- Per configurare e gestire i profili in modalità di distribuzione automatica di Autopilot, assicurarsi di avere accesso all'interfaccia di amministrazione di [Microsoft Endpoint Manager](https://endpoint.microsoft.com).


### 2. Registrarsi nel programma Windows Autopilot per HoloLens 2

**Per partecipare al programma, è necessario registrare il tenant al programma di anteprima privata. Ciò abilita i controlli dell'interfaccia utente di Intune specifici di HoloLens (noto anche come MEM) per Autopilot.** Per eseguire questa operazione, andare a [Richiesta di anteprima privata di Windows Autopilot per HoloLens](https://aka.ms/APHoloLensTAP) oppure usare il codice QR seguente per inviare una richiesta.  

![Codice QR di Autopilot](./images/hololens-ap-qrcode.png)  

Microsoft rilascia versione di anteprima dei tenant una volta la settimana. Una volta completata distribuzione di versioni di anteprima, riceverai una notifica tramite e-mail. 

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
   
   Dovrebbe essere visualizzato un elenco che include **HoloLens**. Se questa opzione non è presente, usare una delle opzioni di [Feedback](hololens2-autopilot.md#feedback-for-autopilot) per contattarci.

### 4. Registrare i dispositivi in Windows Autopilot

Nella fase di preparazione esistono due modi principali per registrare i dispositivi per Windows Autopilot: 

1. **Contattare il distributore o il rivenditore quando si effettua un ordine per la registrazione dei dispositivi**.

   oppure
   
2. **Recuperare l'hash hardware (noto anche come ID hardware) e registrare il dispositivo manualmente**. 

Per altre informazioni sulla registrazione del dispositivo, consultare la documentazione [Aggiunta di dispositivi a Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices).  

**Recuperare un codice hash dell’hardware del dispositivo**

Il dispositivo può registrare il codice hash dell’hardware in un file CSV durante il processo configurazione guidata o, in un secondo momento, quando il proprietario di un dispositivo avvia il processo di raccolta dei log di diagnostica (descritto nella procedura seguente). In genere, il proprietario del dispositivo è il primo utente che accede al dispositivo.

1. Avviare il dispositivo HoloLens 2.

1. Sul dispositivo premere contemporaneamente i pulsanti Arresta e Riduzione volume, quindi rilasciarli. Il dispositivo raccoglie sia i log di diagnostica che il codice hash dell’hardware e li archivia in un gruppo di file con estensione .zip. 

   1. Per i dettagli completi e un video di istruzioni su come eseguire questa operazione, leggere la sezione [Diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics). 
   
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

> [!div class="mx-imgBorder"]
> ![Configurazione ESP](./images/hololens-ap-profile-settings.png)

### 8. Verificare lo stato del profilo dei dispositivi HoloLens.

1. Nell'interfaccia di amministrazione di Microsoft Endpoint Manager selezionare **Dispositivi** > **Windows** > **Registrazione di Windows** > **Dispositivi**.

1. Verificare che i dispositivi HoloLens siano presenti nell'elenco e che lo stato del profilo sia **Assegnato**.  

   > [!NOTE]  
   > Potrebbe essere necessario attendere alcuni minuti prima che il profilo venga assegnato al dispositivo.  

   > [!div class="mx-imgBorder"]   
   > ![Assegnazioni di dispositivi e profilo.](./images/hololens-ap-devices-assignments.png)

## Esperienza utente di Windows Autopilot per HoloLens 2

Dopo aver completato la procedura indicata in precedenza, gli utenti HoloLens 2 eseguiranno il provisioning dei dispositivi HoloLens tramite l'esperienza seguente:  

1. L'esperienza Autopilot richiede l'accesso a Internet. Usare una delle seguenti opzioni per fornire accesso a Internet:

    - Connettere il dispositivo a una rete di Wi-Fi in Configurazione guidata e quindi consentire l'individuazione automatica dell'esperienza Autopilot. Questa è l'unica volta che si dovrà interagire con la Configurazione guidata finché l'esperienza Autopilot non viene completata autonomamente. Tenere presente che per impostazione predefinita HoloLens 2 attende 10 secondi per rilevare il Autopilot dopo il rilevamento di Internet. Se non viene rilevato alcun profilo Autopilot entro 10 secondi, la Configurazione guidata presenterà il contratto di licenza. Se si verifica questo scenario, riavviare il dispositivo in modo che sia possibile eseguire un altro tentativo per rilevare Autopilot. Tenere anche presente che la Configurazione guidata può attendere a tempo indefinito Autopilot solo se il criterio TenantLockdown è impostato nel dispositivo.
    
    - Connettere il dispositivo alla porta Ethernet con adattatori "da USB-C a Ethernet" per una connettività Internet cablata e lasciare che HoloLens 2 completi l'esperienza Autopilot automaticamente.
    
    - Connettere il dispositivo con adattatori "da USB-C a Wi-Fi" per una connettività Internet wireless e lasciare che HoloLens 2 completi l'esperienza Autopilot automaticamente.

       > [!NOTE]
       > L’uso di Autopilot avrà un effetto sul [proprietario del dispositivo](security-adminless-os.md#device-owner).
   
       > [!IMPORTANT]  
       > I dispositivi che tentano di usare reti Wi-Fi in OOBE per il Autopilot devono essere in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Per i dispositivi che utilizzano adattatori Ethernet, è necessario connettere il dispositivo alla rete prima dell'avvio della Configurazione guidata. Il dispositivo determina se il provisioning avviene su un dispositivo di Autopilot mentre si trova nella prima schermata della Configurazione guidata. Se il dispositivo non riesce a connettersi alla rete o se si sceglie di non eseguire il provisioning come dispositivo di Autopilot, non sarà possibile passare al provisioning di Autopilot in un secondo momento. In alternativa, è necessario avviare questa procedura per eseguire il provisioning del dispositivo come dispositivo di Autopilot.

1. Il dispositivo dovrebbe avviare automaticamente la Configurazione guidata. Non interagire con la Configurazione guidata. Al contrario, è consigliabile attendere semplicemente. Consentire a HoloLens 2 di rilevare la connettività di rete e di completare automaticamente la Configurazione guidata. Il dispositivo può essere riavviato durante la Configurazione guidata. Le schermate della Configurazione guidata devono essere simili alle seguenti.
   
   ![Configurazione guidata: passaggio 1 ](./images/autopilot-welcome.jpg)
   ![Configurazione guidata: passaggio 2](./images/autopilot-step-complete.jpg)
   ![Configurazione guidata: passaggio 3](./images/autopilot-device-setup.jpg)

1. Alla fine della Configurazione guidata, è possibile accedere al dispositivo usando il nome utente e la password.

   <br/><img src="./images/other-user.jpg" width="450" height="700" />

## Tenantlockdown CSP e Autopilot
- Mantiene i dispositivi nel tenant dell'organizzazione bloccandoli al tenant anche tramite il ripristino o l’esecuzione del flashing del dispositivo, con maggiore sicurezza, impedendo la creazione di account tramite provisioning. 

I dispositivi HoloLens 2 ora supportano TenantLockdown CSP a partire da Windows Holographic versione 20H2. 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP consente a HoloLens 2 di essere collegato alla registrazione MDM usando solo Autopilot. Una volta che il nodo RequireNetworkInOOBE del CSP TenantLockdown è impostato sul valore true o false (inizialmente impostato) su HoloLens 2, quel valore rimane sul dispositivo nonostante la riesecuzione del flashing, gli aggiornamenti del sistema operativo e così via. 

Una volta che il nodo RequireNetworkInOOBE del CSP TenantLockdown è impostato su true in HoloLens 2, la Configurazione guidata attende a tempo indefinito che il profilo Autopilot venga scaricato e applicato correttamente, dopo la connettività di rete. 

Una volta che il nodo RequireNetworkInOOBE del CSP TenantLockdown è impostato su true in HoloLens 2, le seguenti operazioni non sono consentite in Configurazione guidata: 
- creazione di un utente locale usando il provisioning di runtime 
- esecuzione dell'operazione di aggiunta AAD join tramite provisioning di runtime 
- selezione di chi possiede il dispositivo nell'esperienza di Configurazione guidata 

### Come impostarlo usando Intune? 
1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato e specificare true per il nodo RequireNetworkInOOBE come mostrato di seguito.
Il valore OMA-URI deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Impostazione del blocco del tenant tramite OMA-URI](images/hololens-tenant-lockdown.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo al gruppo di dispositivi. 

1. Rendere il dispositivo HoloLens 2 membro del gruppo creato nel passaggio precedente e attivare la sincronizzazione.  

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Una volta che la configurazione del dispositivo viene applicata correttamente al dispositivo HoloLens 2, gli effetti di TenantLockdown saranno attivi.

### Come si annulla RequireNetworkInOOBE di TenantLockdown in HoloLens 2 usando Intune? 
1. Rimuovere HoloLens 2 dal gruppo di dispositivi a cui è stata assegnata la configurazione di dispositivo precedente. 

1. Creare un profilo di configurazione del dispositivo basato su URI OMA personalizzato e specificare false per RequireNetworkInOOBE come mostrato di seguito. Il valore OMA-URI deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot dell'impostazione di RequireNetworkInOOBE su false tramite OMA URI in Intune](images/hololens-tenant-lockdown-false.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo al gruppo di dispositivi. 

1. Rendere il dispositivo HoloLens 2 membro del gruppo creato nel passaggio precedente e attivare la sincronizzazione.

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Una volta che la configurazione del dispositivo viene applicata correttamente al dispositivo HoloLens 2, gli effetti di TenantLockdown saranno inattivi. 

### Cosa succederebbe durante la Configurazione guidata, se il profilo di Autopilot non viene assegnato a HoloLens dopo che TenantLockdown è stato impostato su true? 
La Configurazione guidata attenderà a tempo indefinito il download del profilo di Autopilot e verrà visualizzata la seguente finestra di dialogo. Per rimuovere gli effetti di TenantLockdown, il dispositivo deve essere registrato con il suo tenant originale usando solo Autopilot e RequireNetworkInOOBE deve essere disattivato, come descritto nel passaggio precedente, prima che le restrizioni introdotte da TenantLockdown CSP vengano rimosse. 

![Visualizzazione nel dispositivo per quando il criterio viene applicato al dispositivo.](images/hololens-autopilot-lockdown.png)

## Problemi noti

- L'installazione dell'applicazione basata sul contesto del dispositivo configurata in Intune non funziona ancora.
- Durante la configurazione dell'Autopilot tramite Wi-Fi, potrebbe esserci un'istanza in cui il profilo Autopilot non viene scaricato quando viene stabilita la prima connessione Internet e viene presentato il Contratto di licenza con l'utente finale (EULA). In questo caso l'utente ha la possibilità di procedere con l’esperienza di installazione non-Autopilot. Per ritentare la configurazione con Autopilot, porre il dispositivo in modalità di sospensione e quindi accenderlo, oppure riavviare il dispositivo e riprovare.

### Risoluzione dei problemi

Gli articoli seguenti possono essere una risorsa utile per ottenere altre informazioni e risolvere i problemi relativi ad Autopilot. Bisogna tenere presente che questi articoli si basano su Windows 10 Desktop e non tutte le informazioni possono essere applicate a HoloLens:
- [Problemi noti di Windows Autopilot](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Risolvere i problemi di registrazione dei dispositivi Windows in Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Conflitti tra criteri di Windows Autopilot](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## Feedback per Autopilot

Per inviare feedback e suggerimenti o segnalare problemi, usare uno dei metodi seguenti:

- Usare l’app Hub di Feedback. Questa app è disponibile in un computer connesso a HoloLens. Nell'app Hub di Feedback selezionare la categoria **Gestione dell’impresa** > **Dispositivo**. Quando dai un feedback o segnali un problema, fornisci una descrizione dettagliata. Se possibile, includere screenshot e log.
- Se si verificano problemi in Intune durante la registrazione di un dispositivo o di un profilo Autopilot che non viene assegnato, aprire un ticket di supporto in [https://aka.ms/apsupport](https://aka.ms/apsupport) .
- Se si verificano problemi nel dispositivo HoloLens durante l'esperienza Autopilot, aprire un ticket di supporto in [https://aka.ms/hlsupport](https://aka.ms/hlsupport) con i [log di diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics).

  Fornire una descrizione dettagliata nel messaggio. Tuttavia, a meno che il personale di assistenza non lo chieda specificamente, non includere dati come screenshot o log. Questi dati possono includere informazioni private o personali.
