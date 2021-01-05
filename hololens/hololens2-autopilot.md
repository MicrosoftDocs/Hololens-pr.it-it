---
title: Windows Autopilot per HoloLens 2
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
ms.openlocfilehash: 98f35c52091a2d477a2f0852f66ad706498ad026
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253592"
---
# Windows Autopilot per HoloLens 2

A partire da Windows Holographic versione 2004, HoloLens 2 supporta la [modalità di distribuzione automatica](https://docs.microsoft.com/mem/autopilot/self-deploying) di Windows Autopilot. Gli amministratori possono configurare la Configurazione guidata in Microsoft Endpoint Manager e consentire agli utenti finali di preparare i dispositivi per l'uso aziendale con poca o nessuna interazione. Ciò riduce il costo generale di gestione dell'inventario, il costo della preparazione pratica del dispositivo e le chiamate di supporto da parte dei dipendenti durante l'esperienza di configurazione. Per altre informazioni su Windows Autopilot, fare clic [qui](https://docs.microsoft.com/mem/autopilot/windows-autopilot).

Allo stesso modo dei dispositivi Surface, è consigliabile che i clienti collaborino con il proprio [provider di soluzioni cloud](https://partner.microsoft.com/cloud-solution-provider) Microsoft (rivenditore o distributore) per registrare i dispositivi con il servizio Autopilot tramite il Centro per i partner. Altri metodi per la registrazione dei dispositivi sono illustrati in [questa](https://docs.microsoft.com/mem/autopilot/add-devices)sezione, anche l’uso dei partner di canale di Microsoft garantisce un percorso end-to-end più efficace.

> [!NOTE]
> A partire dal 20/11/2020, la configurazione di Autopilot per HoloLens in Microsoft Endpoint Manager passerà all'**anteprima pubblica**. I clienti non devono più iscriversi all'anteprima privata e tutti i tenant potranno configurare Autopilot nell'interfaccia di amministrazione MEM.

Quando viene avviato il processo di distribuzione automatica di Autopilot, Autopilot completa i passaggi seguenti:

1. Aggiungere il dispositivo ad Azure Active Directory (Azure AD) Si noti che Autopilot per HoloLens non supporta l’aggiunta ad Active Directory o ad Azure AD ibrido.

1. Usare Azure AD per registrare il dispositivo in Microsoft Endpoint Manager (o un altro servizio MDM).

1. Scaricare e applicare criteri, certificati, profili di rete e applicazioni mirati ai dispositivi.

1. Eseguire il provisioning del dispositivo.

1. Presentare la schermata di accesso all'utente.

## Configurazione di Autopilot per HoloLens 2

Seguire i passaggi seguenti per configurare l'ambiente:

1. [Verificare i requisiti per Windows Autopilot per HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Abilitare la registrazione automatica MDM automatica](#2-enable-automatic-mdm-enrollment)

1. [Registrare i dispositivi in Windows Autopilot.](#3-register-devices-in-windows-autopilot)

1. [Creare un gruppo di dispositivi.](#4-create-a-device-group)

1. [Creare un profilo di distribuzione.](#5-create-a-deployment-profile)

1. [Verificare la configurazione della pagina di stato di registrazione (ESP).](#6-verify-the-esp-configuration)

1. [Verificare lo stato del profilo dei dispositivi HoloLens.](#7-verify-the-profile-status-of-the-hololens-devices)

### 1. Rivedere i requisiti per Windows Autopilot per HoloLens 2

#### Rivedere le sezioni seguenti dell'articolo sui requisiti di Windows Autopilot:

- [Requisiti di rete](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [Requisiti di licenza](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [Requisiti di configurazione](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**Rivedere la sezione "[Requisiti](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" dell'articolo sulla modalità di distribuzione automatica di Windows Autopilot.** L'ambiente deve soddisfare questi requisiti, oltre ai requisiti standard di Windows Autopilot. Non è necessario rivedere le sezioni "Istruzioni dettagliate" e "Convalida" dell'articolo. Le procedure descritte più avanti in questo articolo forniscono i passaggi corrispondenti specifici di HoloLens.

Per informazioni su come registrare i dispositivi e configurare i profili, vedere [2. Registrare i dispositivi in Windows Autopilot](#3-register-devices-in-windows-autopilot) e [4. Creare un profilo di distribuzione](#5-create-a-deployment-profile) in questo articolo. Per configurare e gestire i profili in modalità di distribuzione automatica di Autopilot, assicurarsi di avere accesso all'interfaccia di amministrazione di [Microsoft Endpoint Manager](https://endpoint.microsoft.com).

#### Rivedere i requisiti del sistema operativo HoloLens:

- I dispositivi devono essere in [Windows Holographic, versione 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) o versioni successive. Per confermare la versione della build nel dispositivo o per eseguire nuovamente il flashing del sistema operativo più recente, è possibile usare [ARC (Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab). [Qui](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) è possibile trovare le istruzioni. I dispositivi distribuiti entro la fine di settembre 2020 hanno la versione 1903 di Windows Holographic preinstallata. Contattare il rivenditore per verificare i dispositivi predisposti per Autopilot siano inviati.

- Windows Holographic versione 2004 supporta solo Autopilot con connessione ethernet. Assicurarsi che HoloLens sia connesso a ethernet usando un adattatore "USB C a Ethernet" **prima di accenderlo**. All'avvio del dispositivo non è necessaria alcuna interazione con l'utente. Se si prevede di eseguire l'implementazione di Autopilot in più dispositivi HoloLens, è consigliabile pianificare l'infrastruttura dell’adattatore. Non è consigliabile usare l’hub USB, perché spesso è richiesta l'installazione di altri driver di terze parti che non sono supportati in HoloLens.

- [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) o versioni successive supporta Autopilot tramite Wi-Fi, anche se è comunque possibile usare adattatori ethernet. Per i dispositivi connessi tramite Wi-Fi, l'utente deve solo:

     - passare la scena del colibrì
     - scegliere la lingua e le impostazioni locali
     - eseguire la calibrazione degli occhi
     - stabilire una connessione di rete

- Windows Holographic versione 20H2 supporta il [CSP Tenantlockdown e Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), che blocca un dispositivo al tenant e assicura che il dispositivo rimanga associato al tenant in caso di reimpostazioni o cancellazioni accidentali o intenzionali.  

- Assicurarsi che i dispositivi non sono già membri di Azure AD e non sono registrati in Intune (o in un altro sistema MDM). Il processo di distribuzione automatica di Autopilot completa questi passaggi. Per fare in modo che tutte le informazioni relative al dispositivo siano pulite, controllare le pagine **Dispositivi** sia in Azure AD che nei portali di Intune. Tenere presente che la funzionalità "Converti tutti i dispositivi mirati in Autopilot" non è supportata in HoloLens al momento.  

### 2. abilitare la registrazione automatica MDM:

Affinché Autopilot abbia successo, è necessario abilitare la registrazione MDM automatica nel portale di Azure. In questo modo il dispositivo verrà abilitato per la registrazione senza utente.

In [Azure Portal](https://portal.azure.com/#home) selezionare **Azure Active Directory**  ->  **Mobilità (MDM e MAM)**  ->  **Microsoft Intune**. Configurare l'**ambito utente MDM** e infine sarà necessario selezionare **Tutti**.

Esaminare la seguente breve [guida sull'abilitazione della registrazione MDM automatica](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) oppure la [Guida rapida per la registrazione automatica](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) per ottenere altre informazioni per la configurazione.

### 3. registrare i dispositivi in Windows Autopilot

#### Ottenere l'hash hardware

È necessario registrare i dispositivi in Windows Autopilot precedentemente alla prima configurazione. Per la documentazione MEM sulla registrazione del dispositivo, vedere [Aggiunta di dispositivi a Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices).  

Esistono due modi principali per registrare i dispositivi HoloLens:

 - **Il rivenditore può registrare i dispositivi nel Centro per i partner quando si effettua un ordine.**

   > [!NOTE]  
   > Questo è il percorso consigliato per l'aggiunta di dispositivi al servizio Autopilot. [Ulteriori informazioni](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).  

 - **Recuperare l'hash hardware (noto anche come ID hardware) e registrare il dispositivo manualmente nell'interfaccia di amministrazione MEM**.

- **Recuperare l'hash hardware**

Il dispositivo registra l'hash hardware in un file CSV durante il processo di Configurazione guidata o in un secondo momento quando il proprietario del dispositivo avvia il processo di raccolta dei log di diagnostica (descritto nella procedura seguente). In genere, il proprietario del dispositivo è il primo utente che accede al dispositivo.

1. Avviare il dispositivo HoloLens 2.

1. Nel dispositivo premere contemporaneamente i pulsanti di **alimentazione** e di **volume giù** e quindi rilasciarli. Il dispositivo raccoglie sia i log di diagnostica che l’hash dell’hardware e li archivia in un gruppo di file con estensione .zip.

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

#### Registrare il dispositivo tramite MEM

1. Nell’[interfaccia di amministrazione di Microsoft Endpoint Manager](https://endpoint.microsoft.com), selezionare **Dispositivi** > **Windows** > **Registrazione di Windows** e quindi selezionare **Dispositivi** > **Importa** in **Programma di distribuzione di Windows Autopilot**.

1. In **Aggiungi dispositivi di Windows Autopilot** selezionare il file CSV di DeviceHash, quindi **Apri** e infine **Importa**.  

   > [!div class="mx-imgBorder"]
   > ![Usare il comando Importa per importare il codice hash dell’hardware.](./images/hololens-ap-hash-import.png)

1. Una volta completata l'importazione, selezionare **Dispositivi** > **Windows** > **Registrazione di Windows** > **Dispositivi** > **Sincronizza**. Il processo potrebbe richiedere alcuni minuti, a seconda del numero di dispositivi sincronizzati. Per vedere il dispositivo registrato, selezionare **Aggiorna**.  

   > [!div class="mx-imgBorder"]
   > ![Usare i comandi Sincronizza e Aggiorna per visualizzare l'elenco dei dispositivi.](./images/hololens-ap-devices-sync.png)  

### 4. creare un gruppo di dispositivi

1. Nell’[interfaccia di amministrazione di Microsoft Endpoint Manager](https://endpoint.microsoft.com), selezionare **Gruppi** > **Nuovo gruppo**.

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

### 5. creare un profilo di distribuzione

1. Nell’[interfaccia di amministrazione di Microsoft Endpoint Manager](https://endpoint.microsoft.com), selezionare**Dispositivi** > **Windows** > **Registrazione di Windows** > **Profili di distribuzione di Windows Autopilot** > **Crea profilo** > **HoloLens**.
   ![Il menu a discesa della voce “Crea profilo” include un elemento di HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Immettere il nome e la descrizione del profilo e quindi selezionare **Avanti**.  
   Dovrebbe essere visualizzato un elenco che include **HoloLens**. Se questa opzione non è presente, usare una delle opzioni di [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) per contattarci.

   > [!div class="mx-imgBorder"]
   > ![Aggiungere un nome e una descrizione del profilo](./images/hololens-ap-profile-name.png)

1. Nella pagina **Configurazione guidata (OOBE)**, la maggior parte delle impostazioni è preconfigurata per semplificare la configurazione guidata per la valutazione. È possibile configurare facoltativamente le impostazioni seguenti:  

   - **Lingua (area geografica)**: selezionare la lingua per la Configurazione guidata. È consigliabile selezionare una lingua dall'elenco di [lingue supportate per HoloLens 2](hololens2-language-support.md).
   - **Configurazione automatica della tastiera**: per assicurarsi che la tastiera corrisponda alla lingua selezionata, scegliere **Sì**.
   - **Applicare un modello di nome del dispositivo**: per impostare automaticamente il nome del dispositivo durante la Configurazione guidata, selezionare **Sì** e quindi immettere la frase e i segnaposto del modello in **Immettere un nome**. Ad esempio, immettere un prefisso e `%RAND:4%`&mdash;un segnaposto per un numero casuale di quattro cifre.
     > [!NOTE]  
     > Se si usa un modello di nome del dispositivo, il processo di Configurazione guidata riavvia il nuovo dispositivo ancora una volta dopo l’applicazione del nome del dispositivo e prima dell’aggiunta del dispositivo ad Azure AD. Il riavvio consente l’applicazione del nuovo nome.  

   > [!div class="mx-imgBorder"]
   > ![Configurare le impostazioni della Configurazione guidata.](./images/hololens-ap-profile-oobe.png)

1. Dopo aver configurato le impostazioni, selezionare **Avanti**.
1. Nella pagina **Tag degli ambiti** è possibile aggiungere facoltativamente i tag degli ambiti che si vogliono applicare al profilo. Per altre informazioni sui tag degli ambiti, vedere [Usare il controllo di accesso basato sui ruoli e i tag degli ambiti per l’IT distribuito](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Al termine, selezionare **Avanti**.
1. Nella pagina **Assegnazioni** selezionare **Gruppi selezionati** per **Assegna a**.
1. In **GRUPPI SELEZIONATI** scegliere **+ Seleziona gruppi da includere**.
1. Nell'elenco **Seleziona gruppi da includere** scegliere il gruppo di dispositivi creato per i dispositivi HoloLens di Autopilot e quindi selezionare **Avanti**.  
  
   Se si vogliono escludere i gruppi, scegliere **Seleziona gruppi da escludere** e scegliere i gruppi da escludere.

   > [!div class="mx-imgBorder"]
   > ![Assegnare un gruppo di dispositivi al profilo.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Nella pagina **Rivedi + Crea**, rivedere le impostazioni e quindi selezionare **Crea** per creare il profilo.  

   > [!div class="mx-imgBorder"]
   > ![Rivedere + Creare](./images/hololens-ap-profile-summ.png)

### 6. verificare la configurazione ESP

La Pagina dello stato di registrazione (ESP) visualizza lo stato del processo di configurazione completo del dispositivo, che viene eseguito quando un utente gestito da MDM accede a un dispositivo per la prima volta. Assicurarsi che la configurazione ESP sia analoga alla seguente e verificare che le assegnazioni siano corrette.  

> [!div class="mx-imgBorder"]
> ![Configurazione ESP](./images/hololens-ap-profile-settings.png)

### 7. verificare lo stato del profilo dei dispositivi HoloLens

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

        > [!IMPORTANT]  
       > I dispositivi che tentano di usare reti Wi-Fi in OOBE per Autopilot devono essere in [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Per i dispositivi che utilizzano adattatori Ethernet, è necessario connettere il dispositivo alla rete prima dell'avvio della Configurazione guidata. Il dispositivo determina se il provisioning avviene su un dispositivo di Autopilot mentre si trova nella prima schermata della Configurazione guidata. Se il dispositivo non riesce a connettersi alla rete o se si sceglie di non eseguire il provisioning come dispositivo di Autopilot, non sarà possibile passare al provisioning di Autopilot in un secondo momento. In alternativa, è necessario avviare questa procedura per eseguire il provisioning del dispositivo come dispositivo di Autopilot.

1. Il dispositivo dovrebbe avviare automaticamente la Configurazione guidata. Non interagire con la Configurazione guidata. Al contrario, è consigliabile attendere semplicemente. Consentire a HoloLens 2 di rilevare la connettività di rete e di completare automaticamente la Configurazione guidata. Il dispositivo può essere riavviato durante la Configurazione guidata. Le schermate della Configurazione guidata devono essere simili alle seguenti.

   ![Configurazione guidata: passaggio 1 ](./images/autopilot-welcome.jpg)
   ![Configurazione guidata: passaggio 2](./images/autopilot-step-complete.jpg)
   ![Configurazione guidata: passaggio 3](./images/autopilot-device-setup.jpg)

1. Alla fine della Configurazione guidata, è possibile accedere al dispositivo usando il nome utente e la password.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## Tenantlockdown CSP e Autopilot

I dispositivi HoloLens 2 supportano TenantLockdown CSP a partire da Windows Holographic versione 20H2. Questo CSP mantiene i dispositivi nel tenant dell'organizzazione, bloccandoli al tenant anche tramite il ripristino o l’esecuzione del flashing del dispositivo.

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP consente a HoloLens 2 di essere collegato alla registrazione MDM usando solo Autopilot. Una volta che il nodo RequireNetworkInOOBE del CSP TenantLockdown è impostato sul valore true o false (inizialmente impostato) su HoloLens 2, quel valore rimane sul dispositivo nonostante la riesecuzione del flashing, gli aggiornamenti del sistema operativo e così via.

Una volta che il nodo RequireNetworkInOOBE del CSP TenantLockdown è impostato su true in HoloLens 2, la Configurazione guidata attende a tempo indefinito che il profilo Autopilot venga scaricato e applicato correttamente, dopo la connettività di rete.

Una volta che il nodo RequireNetworkInOOBE del CSP TenantLockdown è impostato su true in HoloLens 2, le seguenti operazioni non sono consentite in Configurazione guidata:

- creazione di un utente locale usando il provisioning di runtime 
- esecuzione dell'operazione di aggiunta Azure AD tramite provisioning di runtime 
- selezione di chi possiede il dispositivo nell'esperienza di Configurazione guidata 

#### Come impostarlo usando Intune? 
1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato e specificare true per il nodo RequireNetworkInOOBE come mostrato di seguito.
Il valore OMA-URI deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Impostazione del blocco del tenant tramite OMA-URI](images/hololens-tenant-lockdown.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo al gruppo di dispositivi.

1. Rendere il dispositivo HoloLens 2 membro del gruppo creato nel passaggio precedente e attivare la sincronizzazione.  

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Una volta che la configurazione del dispositivo viene applicata correttamente al dispositivo HoloLens 2, gli effetti di TenantLockdown saranno attivi.

#### Come si annulla RequireNetworkInOOBE di TenantLockdown in HoloLens 2 usando Intune?

1. Rimuovere HoloLens 2 dal gruppo di dispositivi a cui è stata assegnata la configurazione di dispositivo precedente.

1. Creare un profilo di configurazione del dispositivo basato su URI OMA personalizzato e specificare false per RequireNetworkInOOBE come mostrato di seguito.
Il valore OMA-URI deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot dell'impostazione di RequireNetworkInOOBE su false tramite OMA URI in Intune](images/hololens-tenant-lockdown-false.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo al gruppo di dispositivi. 

1. Rendere il dispositivo HoloLens 2 membro del gruppo creato nel passaggio precedente e attivare la sincronizzazione.

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Una volta che la configurazione del dispositivo viene applicata correttamente al dispositivo HoloLens 2, gli effetti di TenantLockdown saranno inattivi.

#### Cosa succederebbe durante la Configurazione guidata, se il profilo di Autopilot non viene assegnato a HoloLens dopo che TenantLockdown è stato impostato su true? 
La Configurazione guidata attenderà a tempo indefinito il download del profilo di Autopilot e verrà visualizzata la seguente finestra di dialogo. Per rimuovere gli effetti di TenantLockdown, il dispositivo deve essere registrato con il suo tenant originale usando solo Autopilot e RequireNetworkInOOBE deve essere disattivato, come descritto nel passaggio precedente, prima che le restrizioni introdotte da TenantLockdown CSP vengano rimosse.

![Visualizzazione nel dispositivo per quando il criterio viene applicato al dispositivo.](images/hololens-autopilot-lockdown.png)

## Problemi noti e limitazioni

- Stiamo esaminando un problema in cui l'installazione dell'applicazione basata sul contesto del dispositivo configurata in MEM non si applica a HoloLens. [Maggiori informazioni sul contesto del dispositivo e sulle installazioni di contesto utente.](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Durante la configurazione di Autopilot tramite Wi-Fi, potrebbe essere presente un'istanza in cui il profilo di Autopilot non viene scaricato quando viene stabilita la connessione Internet per la prima volta. In questo caso viene presentato il contratto di licenza con l'utente finale (EULA) e l'utente può scegliere se procedere con l'esperienza di configurazione senza Autopilot. Per ritentare la configurazione con Autopilot, porre il dispositivo in modalità di sospensione e quindi accenderlo, oppure riavviare il dispositivo e riprovare.
- La funzionalità "Converti tutti i dispositivi mirati in Autopilot" non è supportata in HoloLens al momento.  

### Risoluzione dei problemi

Gli articoli seguenti possono essere una risorsa utile per ottenere altre informazioni e risolvere i problemi relativi ad Autopilot. Bisogna tenere presente che questi articoli si basano su Windows 10 Desktop e non tutte le informazioni possono essere applicate a HoloLens:

- [Problemi noti di Windows Autopilot](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Risolvere i problemi di registrazione dei dispositivi Windows in Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Conflitti tra criteri di Windows Autopilot](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## Feedback e supporto per Autopilot

Per inviare feedback e suggerimenti o segnalare problemi, usare uno dei metodi seguenti:

- Per assistenza sulla registrazione del dispositivo, contattare il rivenditore o il distributore.
- Per informazioni generali sul supporto tecnico per Windows Autopilot o per problemi come le assegnazioni del profilo, la creazione di gruppi o i controlli del portale MEM, [contattare il supporto di Microsoft Endpoint Manager](https://docs.microsoft.com/mem/get-support)  
- Se il dispositivo è registrato per il servizio Autopilot e il profilo è assegnato al portale MEM, contattare il [supporto](https://docs.microsoft.com/hololens/) di HoloLens (vedere la scheda "Supporto"). Aprire un ticket di supporto e, se applicabile, includere screenshot e log tramite l'acquisizione di [log diagnostici offline](hololens-diagnostic-logs.md#offline-diagnostics) durante l’esperienza di Configurazione guidata.
- Per segnalare un problema dal dispositivo, usare l'app Hub di Feedback su HoloLens. Nell'app Hub di Feedback selezionare la categoria **Gestione dell’impresa** > **Dispositivo**.
- Per fornire feedback generali su Autopilot per HoloLens, è possibile inviare questo [sondaggio](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)
