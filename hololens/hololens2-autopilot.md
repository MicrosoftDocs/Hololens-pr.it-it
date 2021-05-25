---
title: Windows Autopilot per HoloLens 2
description: Informazioni su come configurare, configurare e risolvere i problemi di Autopilot nei HoloLens 2 dispositivi.
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
keywords: Pilota automatico
manager: jarrettr
ms.openlocfilehash: 9625f3fd1cd6a928f6bd20ba809c750c625143cf
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397742"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot per HoloLens 2

A partire da Windows Holographic versione 2004, HoloLens 2 supporta la modalità [self-deploying](https://docs.microsoft.com/mem/autopilot/self-deploying) Windows Autopilot con Microsoft Intune (non sono supportati IME di terze parti). Gli amministratori possono configurare l'esperienza di configurazione in Microsoft Endpoint Manager e consentire agli utenti finali di preparare i dispositivi per l'uso aziendale senza alcuna interazione. Ciò riduce l'overhead di gestione dell'inventario, il costo della preparazione del dispositivo hands-on e le chiamate di supporto dei dipendenti durante l'esperienza di installazione. Per altre informazioni, [vedere la documentazione Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

Come per i dispositivi Surface, è consigliabile che i clienti lavorino con Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (rivenditore o distributore) per ottenere i dispositivi registrati con il servizio Autopilot tramite Partner Center. Altri metodi per la registrazione [](https://docs.microsoft.com/mem/autopilot/add-devices) dei dispositivi sono descritti nella documentazione relativa all'aggiunta di dispositivi, anche se l'uso dei partner di canale Microsoft garantisce il percorso end-to-end più efficace.

> [!NOTE]
> A data del 20/11/2020 la configurazione di Autopilot per HoloLens in Microsoft Endpoint Manager sta per passare **all'anteprima pubblica.** I clienti non devono più registrarsi nell'anteprima privata e tutti i tenant potranno configurare Autopilot nell'interfaccia di amministrazione di MEM.

Quando un utente avvia il processo di distribuzione automatica di Autopilot, Autopilot completa i passaggi seguenti:

1. Aggiungere il dispositivo a Azure Active Directory (Azure AD). Si noti che Autopilot per HoloLens non supporta l'aggiunta ad Active Directory o Azure AD ibrido join.

1. Usare Azure AD per registrare il dispositivo in Microsoft Endpoint Manager (o in un altro servizio MDM).

1. Scaricare e applicare criteri, certificati, profili di rete e applicazioni destinati ai dispositivi.

1. Effettuare il provisioning del dispositivo.

1. Presentare la schermata di accesso all'utente.

## <a name="configuring-autopilot-for-hololens-2"></a>Configurazione di Autopilot per HoloLens 2

Per configurare l'ambiente, seguire questa procedura:

1. [Esaminare i requisiti per Windows Autopilot per HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Abilitare la registrazione MDM automatica](#2-enable-automatic-mdm-enrollment)

1. [Registrare i dispositivi Windows Autopilot.](#3-register-devices-in-windows-autopilot)

1. [Creare un gruppo di dispositivi.](#4-create-a-device-group)

1. [Creare un profilo di distribuzione.](#5-create-a-deployment-profile)

1. [Verificare la configurazione della pagina dello stato della registrazione (ESP).](#6-verify-the-esp-configuration)

1. [Verificare lo stato del profilo dei dispositivi HoloLens.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Esaminare i requisiti per Windows Autopilot per HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Esaminare le sezioni seguenti dell'articolo Windows Autopilot requisiti:

- [Requisiti di rete](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [Requisiti di licenza](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [Requisiti di configurazione](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**Vedere la sezione "[Requisiti](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" dell'articolo Windows Autopilot Self-Deploying modalità predefinita.** L'ambiente deve soddisfare questi requisiti, nonché i requisiti di Windows Autopilot standard. Non è necessario esaminare le sezioni "Procedura dettagliata" e "Convalida" dell'articolo. Le procedure descritte più avanti in questo articolo forniscono i passaggi corrispondenti specifici di HoloLens.

Per informazioni su come registrare i dispositivi e configurare i profili, vedere [2. Registrare i dispositivi Windows Autopilot](#3-register-devices-in-windows-autopilot) [e 4. Creare un profilo di distribuzione](#5-create-a-deployment-profile) in questo articolo. Per configurare e gestire i profili in modalità di distribuzione automatica di Autopilot, assicurarsi di avere accesso all'interfaccia di [amministrazione di Microsoft Endpoint Manager.](https://endpoint.microsoft.com)

#### <a name="review-hololens-os-requirements"></a>Esaminare i requisiti del sistema operativo HoloLens:

- I dispositivi devono essere [in Windows Holographic versione 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) o successiva. Per verificare la versione della build nel dispositivo o eseguire nuovamente il flash nel sistema operativo più recente, usare le istruzioni [ARC (Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) e il [dispositivo.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) Si noti che nei dispositivi recapitati fino alla fine di settembre 2020 è preinstallato Windows Holographic versione 1903. Contattare il rivenditore per assicurarsi che i dispositivi pronti per Autopilot siano spediti all'utente.

- Windows Holographic versione 2004 supporta solo Autopilot tramite connessione ethernet. Assicurarsi che HoloLens sia connesso a ethernet usando una scheda "DA USB-C a Ethernet" prima **di accendere**. All'avvio del dispositivo non è necessaria alcuna interazione dell'utente. Se si prevede l'implementazione di Autopilot in molti dispositivi HoloLens, è consigliabile pianificare l'infrastruttura della scheda. Non è consigliabile usare hub USB, perché spesso richiedono l'installazione di driver di terze parti aggiuntivi che non sono supportati in HoloLens.

- [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) o versioni successive supporta Autopilot su Wi-Fi, anche se è comunque possibile usare schede ethernet. Per i dispositivi connessi tramite Wi-Fi, l'utente deve solo:

     - Passare attraverso la scena del colibrì
     - Scegliere la lingua e le impostazioni locali
     - Eseguire la calibrazione oculare
     - Stabilire una connessione di rete

- Windows Holographic versione 20H2 supporta [Tenantlockdown CSP e Autopilot,](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)che bloccano un dispositivo in un tenant e assicurano che il dispositivo rimanga associato a tale tenant in caso di reimpostazioni o cancellazioni accidentali o intenzionali.  

- Assicurarsi che i dispositivi non siano già membri di Azure AD e non siano registrati in Intune (o in un altro sistema MDM). Il processo di distribuzione automatica di Autopilot completa questi passaggi. Per assicurarsi che tutte le informazioni relative al dispositivo  siano pulite, controllare le pagine Dispositivi nei portali Azure AD e Intune. Si noti che la funzionalità "Converti tutti i dispositivi di destinazione in Autopilot" non è attualmente supportata in HoloLens.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Abilitare la registrazione MDM automatica:

Per il corretto completamento di Autopilot, è necessario abilitare la registrazione MDM automatica nel portale di Azure. In questo modo il dispositivo verrà registrato senza un utente.

Nella finestra [portale di Azure](https://portal.azure.com/#home) selezionare **Azure Active Directory**  ->  **Mobility (MDM e MAM)**  ->  **Microsoft Intune**. Configurare quindi **l'ambito utente MDM.** Sarà quindi necessario selezionare **Tutti.**

Per altre informazioni sulla configurazione, vedere [](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) la breve guida seguente sull'abilitazione della registrazione automatica [MDM](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) o la Guida introduttiva alla registrazione automatica.

### <a name="3-register-devices-in-windows-autopilot"></a>3. Registrare i dispositivi in Windows Autopilot

I dispositivi devono essere registrati in Windows Autopilot prima della configurazione. Per la documentazione MEM sulla registrazione dei dispositivi, vedere [Aggiunta di dispositivi ad Autopilot.](https://docs.microsoft.com/mem/autopilot/add-devices)  

Esistono tre modi principali per registrare i dispositivi HoloLens:

 - **Il rivenditore può registrare i dispositivi Partner Center quando si esegue un ordine.**

   > [!NOTE]  
   > Questo è il percorso consigliato per l'aggiunta di dispositivi al servizio Autopilot. [Altre informazioni](https://docs.microsoft.com/mem/autopilot/partner-registration)  

 - **È possibile [inviare una richiesta di supporto](hololens2-autopilot-registration-support.md) direttamente a Microsoft.**
 - **Recuperare l'hash hardware (noto anche come ID hardware) e registrare manualmente il dispositivo nell'interfaccia di amministrazione di MEM.**

#### <a name="obtain-hardware-hash"></a>Ottenere l'hash hardware
Esistono due modi per recuperare l'hash hardware.
1. È possibile [inviare una richiesta di supporto](hololens2-autopilot-registration-support.md) direttamente a Microsoft.
2. È possibile recuperarlo dal dispositivo. Il dispositivo registra l'hash hardware in un file CSV durante il processo di Configurazione guidata o in un secondo momento quando un proprietario del dispositivo avvia il processo di raccolta dei log di diagnostica (descritto nella procedura seguente). In genere, il proprietario del dispositivo è il primo utente ad accedere al dispositivo.
     > [!WARNING]
     > Nelle compilazioni precedenti alla versione 20H2, se è stata passata la configurazione guidata e i dati di telemetria sono stati impostati su Obbligatorio, non è possibile raccogliere l'hash hardware per Autopilot tramite questo metodo. Per raccogliere l'hash hardware tramite questo metodo, impostare l'opzione di telemetria su Completo tramite l'app impostazioni e selezionare Privacy -> Diagnostica.

    1. Avviare il HoloLens 2 dispositivo.

    1. Nel dispositivo premere **contemporaneamente** i pulsanti Power **e Volume Down** e quindi rilasciarli. Il dispositivo raccoglie i log di diagnostica e l'hash hardware e li archivia in un set di file ZIP.

   1. Per informazioni dettagliate e un video informativo su come eseguire questa operazione, vedere Diagnostica [offline.](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Usare un cavo USB-C per connettere il dispositivo a un computer.

    1. Nel computer aprire Esplora file. Aprire **Documenti di archiviazione interna \\ \<*HoloLens device name*> \\ \\ del PC** e individuare il file AutopilotDiagnostics.zip file.  

       > [!NOTE]  
       > Il file ZIP potrebbe non essere immediatamente disponibile. Se il file non è ancora pronto, è possibile che venga visualizzato un file HoloLensDiagnostics.temp nella cartella Documenti. Per aggiornare l'elenco dei file, aggiornare la finestra.
    
    1. Estrarre il contenuto del file AutopilotDiagnostics.zip.

    1. Nei file estratti individuare il file CSV con prefisso "DeviceHash". Copiare il file in un'unità del computer in cui sarà possibile accedervi in un secondo momento.  

       > [!IMPORTANT]  
       > I dati nel file CSV devono usare l'intestazione e il formato di riga seguenti:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Registrare il dispositivo tramite MEM

1. Nell'Endpoint Manager di amministrazione di  [Microsoft](https://endpoint.microsoft.com)Endpoint Manager selezionare Dispositivi Registrazione Windows di Windows e quindi  >    >  selezionare **Dispositivi**  >  **Importa** in **Programma Windows Autopilot Deployment dispositivi.**

1. In **Aggiungi Windows Autopilot dispositivi** selezionare il file CSV DeviceHash, selezionare **Apri** e quindi **selezionare Importa.**  

   > [!div class="mx-imgBorder"]
   > ![Usare il comando Import per importare l'hash hardware.](./images/hololens-ap-hash-import.png)

1. Al termine dell'importazione, selezionare **Dispositivi**  >  **Registrazione**  >  **Windows**  >  **Dispositivi**  >  **Sincronizza.** Il completamento del processo potrebbe richiedere alcuni minuti, a seconda del numero di dispositivi da sincronizzare. Per visualizzare il dispositivo registrato, selezionare **Aggiorna.**  

   > [!div class="mx-imgBorder"]
   > ![Usare i comandi Sincronizza e Aggiorna per visualizzare l'elenco dei dispositivi.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Creare un gruppo di dispositivi

1. [Nell'interfaccia di amministrazione di Microsoft Endpoint Manager](https://endpoint.microsoft.com)selezionare **Gruppi**  >  **Nuovo gruppo.**

1. Per **Tipo di gruppo** selezionare **Sicurezza** e quindi immettere il nome e la descrizione del gruppo.

1. Per **Tipo di appartenenza** selezionare **Assegnato** o **Dispositivo dinamico**.

1. Eseguire una delle operazioni seguenti:  

   - Se nel passaggio precedente **è** **stata** selezionata l'opzione Assegnato per tipo di appartenenza, selezionare **Membri** e quindi aggiungere i dispositivi Autopilot al gruppo. I dispositivi Autopilot non ancora registrati vengono elencati usando il numero di serie del dispositivo come nome del dispositivo.
   - Se nel **passaggio**  precedente è stata selezionata l'opzione Dispositivi dinamici per Tipo di appartenenza, selezionare Membri del dispositivo dinamici **e** quindi immettere il codice in Regola **avanzata** simile al seguente:
     - Se si vuole creare un gruppo che includa tutti i dispositivi AutoPilot, digitare: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Il campo tag di gruppo di Intune viene mappato **all'attributo OrderID** Azure AD dispositivi. Se si vuole creare un gruppo che includa tutti i dispositivi Autopilot con un tag di gruppo specifico (il Azure AD orderID del dispositivo), è necessario digitare: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Se si vuole creare un gruppo che includa tutti i dispositivi Autopilot con un ID ordine di acquisto specifico, digitare: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Queste regole hanno come destinazione attributi univoci per i dispositivi Autopilot.
1. Selezionare **Salva** e quindi **Crea**.

### <a name="5-create-a-deployment-profile"></a>5. Creare un profilo di distribuzione

1. [Nell'interfaccia Endpoint Manager di amministrazione](https://endpoint.microsoft.com) di Microsoft selezionare Dispositivi Windows registrazione Windows Windows Autopilot profili di distribuzione  >    >    >    >  **Creare il profilo**  >  **HoloLens**.
   ![L'elenco a discesa Crea profilo include un elemento HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Immettere un nome e una descrizione del profilo e quindi selezionare **Avanti.**  
   Verrà visualizzato un elenco che include **HoloLens.** Se questa opzione non è presente, usare una delle opzioni [feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) per contattarci.

   > [!div class="mx-imgBorder"]
   > ![Aggiungere un nome e una descrizione del profilo](./images/hololens-ap-profile-name.png)

1. Nella pagina **Out-of-box experience (OOBE)** la maggior parte delle impostazioni è preconfigurato per semplificare la configurazione fuori rete per questa valutazione. Facoltativamente, è possibile configurare le impostazioni seguenti:  

   - **Lingua (area):** selezionare la lingua per La versione di OOBE. È consigliabile selezionare una lingua dall'elenco delle [lingue supportate per HoloLens 2](hololens2-language-support.md).
   - **Configura automaticamente la** tastiera: per assicurarsi che la tastiera corrisponda alla lingua selezionata, selezionare **Sì.**
   - **Applica** il modello di nome di dispositivo: per  impostare automaticamente il nome del dispositivo durante la Configurazione automatica, selezionare Sì e quindi immettere la frase modello e i segnaposto in **Immettere** un nome. Ad esempio, immettere un prefisso e un segnaposto per un numero casuale di quattro `%RAND:4%` &mdash; cifre.
     > [!NOTE]  
     > Se si usa un modello di nome di dispositivo, il processo di Configurazione in esecuzione riavvia il dispositivo un'altra volta dopo aver applicato il nome del dispositivo e prima di aggiungere il dispositivo Azure AD. Questo riavvio consente di attivare il nuovo nome.  

   > [!div class="mx-imgBorder"]
   > ![Configurare le impostazioni della Configurazione guidata](./images/hololens-ap-profile-oobe.png)

1. Dopo aver configurato le impostazioni, selezionare **Avanti.**
1. Nella pagina **Tag di** ambito aggiungere facoltativamente i tag di ambito da applicare a questo profilo. Per altre informazioni sui tag di ambito, vedere [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md) (Usare il controllo degli accessi in base al ruolo e i tag di ambito per l'IT distribuito). Al termine, selezionare **Avanti**.
1. Nella pagina **Assegnazioni** selezionare **Gruppi selezionati per** Assegna **a.**
1. In **GRUPPI SELEZIONATI** selezionare + Selezionare i gruppi per **includere**.
1. **Nell'elenco Selezionare** i gruppi da includere selezionare il gruppo di dispositivi creato per i dispositivi HoloLens di Autopilot e quindi selezionare **Avanti.**  
  
   Se si vogliono escludere gruppi, selezionare **Selezionare i gruppi** da escludere e selezionare i gruppi da escludere.

   > [!div class="mx-imgBorder"]
   > ![Assegnazione di un gruppo di dispositivi al profilo.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Nella pagina **Rivedi e crea** rivedere le impostazioni e quindi selezionare **Crea** per creare il profilo.  

   > [!div class="mx-imgBorder"]
   > ![Rivedi e crea](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. Verificare la configurazione esp

Nella pagina Stato registrazione (ESP) viene visualizzato lo stato del processo di configurazione completo del dispositivo che viene eseguito quando un utente gestito mdm accede a un dispositivo per la prima volta. Assicurarsi che la configurazione esp sia simile alla seguente e verificare che le assegnazioni siano corrette.  

> [!div class="mx-imgBorder"]
> ![Configurazione esp](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. Verificare lo stato del profilo dei dispositivi HoloLens

1. In Microsoft Endpoint Manager Admin Center selezionare **Dispositivi**  >    >  **windows registrazione**  >  **Dispositivi**.

1. Verificare che i dispositivi HoloLens siano elencati e che il relativo stato del profilo sia **Assegnato**.  

   > [!NOTE]  
   > L'assegnazione del profilo al dispositivo potrebbe richiedere alcuni minuti.  

   > [!div class="mx-imgBorder"]
   > ![Assegnazioni di dispositivi e profili.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot per HoloLens 2'esperienza utente

Una volta completate le istruzioni precedenti, HoloLens 2 utenti eseguiranno l'esperienza seguente per effettuare il provisioning dei dispositivi HoloLens:  

1. L'esperienza di Autopilot richiede l'accesso a Internet. Usare una delle opzioni seguenti per fornire l'accesso a Internet:

    - Connettere il dispositivo a una rete Wi-Fi configurazione automatica e quindi consentire al dispositivo di rilevare automaticamente l'esperienza di Autopilot. Questa è l'unica volta che sarà necessario interagire con La configurazione guidata finché l'esperienza di Autopilot non verrà completata da sola. Si noti che per impostazione predefinita HoloLens 2 tempo di attesa di 10 secondi per rilevare Autopilot dopo il rilevamento di Internet. Se entro 10 secondi non viene rilevato alcun profilo di autopilot, la Configurazione automatica non presenterà il servizio EULA. Se si verifica questo scenario, riavviare il dispositivo in modo da poter eseguire un altro tentativo per rilevare Autopilot. Si noti anche che la configurazione automatica può attendere per un periodo indefinito per Autopilot solo se il criterio TenantLockdown è impostato nel dispositivo.

    - Connettere il dispositivo con Ethernet usando schede "da USB-C a Ethernet" per la connettività Internet cablata e HoloLens 2 completare automaticamente l'esperienza di Autopilot.

    - Connettere il dispositivo con schede "da USB-C a Wifi" per la connettività Internet wireless e HoloLens 2 completare automaticamente l'esperienza di Autopilot.

        > [!IMPORTANT]  
       > I dispositivi che tentano di Wi-Fi in Configurazione guidata per Autopilot devono essere in [Windows Holographic versione 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > Per i dispositivi che usano schede ethernet è necessario connettere il dispositivo alla rete prima dell'avvio della Configurazione guidata. Il dispositivo determina se viene provisioning come dispositivo Autopilot durante la prima schermata della configurazione. Se il dispositivo non può connettersi alla rete o se si sceglie di non effettuare il provisioning del dispositivo come dispositivo Autopilot, non è possibile passare al provisioning di Autopilot in un secondo momento. È invece necessario avviare questa procedura per eseguire il provisioning del dispositivo come dispositivo Autopilot.

1. Il dispositivo dovrebbe avviare automaticamente la Configurazione automatica del sistema operativo. Non interagire con la Modalità tutto il sistema operativo. In alternativa, è possibile sedersi e distorsi. Consentire HoloLens 2 la connettività di rete e consentire il completamento automatico della Configurazione guidata. Il dispositivo può essere riavviato durante la Configurazione configurazione. Le schermate della Procedura guidata dovrebbero essere simili alle seguenti.

   ![OOBE step 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE step 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE step 3](./images/autopilot-device-setup.jpg)

1. Al termine della Configurazione fuori rete, è possibile accedere al dispositivo usando il nome utente e la password.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Provider di servizi di configurazione Tenantlockdown e Autopilot

HoloLens 2 supportano il provider di servizi di configurazione TenantLockdown a livello di Windows Holographic versione 20H2. Questo CSP mantiene i dispositivi nel tenant dell'organizzazione bloccandoli su tale tenant anche tramite reimpostazione o reflash del dispositivo.

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP consente HoloLens 2 essere associato alla registrazione MDM usando solo Autopilot. Quando il nodo RequireNetworkInOOBE del provider di servizi di configurazione TenantLockdown è impostato sul valore true o false (inizialmente impostato) su HoloLens 2, tale valore rimane nel dispositivo nonostante il nuovo flashing, gli aggiornamenti del sistema operativo e così via.

Dopo che il nodo RequireNetworkInOOBE dei CSP TenantLockdown è impostato su true in HoloLens 2, la Configurazione remota attende per un periodo illimitato che il profilo autopilot sia scaricato e applicato correttamente, dopo la connettività di rete.

Quando il nodo RequireNetworkInOOBE dei CSP TenantLockdown è impostato su true in HoloLens 2, le operazioni seguenti non sono consentite nella Configurazione operativa:

- Creazione di un utente locale con il provisioning di runtime 
- Esecuzione di Azure AD join tramite il provisioning di runtime 
- Selezione del proprietario del dispositivo nell'esperienza di configurazione della configurazione 

#### <a name="how-to-set-this-using-intune"></a>Come impostare questa opzione con Intune? 
1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato e specificare true per il nodo RequireNetworkInOOBE, come illustrato di seguito.
Il valore URI OMA deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Impostazione del blocco tennant tramite OMA-URI](images/hololens-tenant-lockdown.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo a tale gruppo di dispositivi.

1. Impostare il HoloLens 2 del dispositivo del gruppo creato nel passaggio precedente e attivare la sincronizzazione.  

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Dopo aver applicato correttamente la configurazione del dispositivo HoloLens 2 dispositivo, gli effetti di TenantLockdown saranno attivi.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Come impostare RequireNetworkInOOBE di TenantLockdown HoloLens 2 intune?

1. Rimuovere il HoloLens 2 dal gruppo di dispositivi a cui è stata assegnata in precedenza la configurazione del dispositivo creata in precedenza.

1. Creare un profilo di configurazione del dispositivo personalizzato basato su URI OMA e specificare false per RequireNetworkInOOBE, come illustrato di seguito.
Il valore URI OMA deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot dell'impostazione di RequireNetworkInOOBE su false tramite URI OMA in Intune](images/hololens-tenant-lockdown-false.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo a tale gruppo. 

1. Impostare il HoloLens 2 del dispositivo del gruppo creato nel passaggio precedente e attivare la sincronizzazione.

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Dopo aver applicato correttamente la configurazione del dispositivo HoloLens 2 dispositivo, gli effetti di TenantLockdown saranno inattivi.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Cosa accade durante la configurazione della configurazione automatica, se il profilo Autopilot non è assegnato in un HoloLens dopo che TenantLockdown è stato impostato su true? 
La configurazione del sistema operativo attenderà a tempo indeterminato il download del profilo Autopilot e verrà visualizzata la finestra di dialogo seguente. Per rimuovere gli effetti di TenantLockdown, il dispositivo deve essere registrato prima con il tenant originale usando solo Autopilot e RequireNetworkInOOOBE deve essere impostato come descritto nel passaggio precedente prima che le restrizioni introdotte da TenantLockdown CSP siano rimosse.

![Visualizzazione nel dispositivo per l'applicazione dei criteri nel dispositivo.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Problemi noti & limitazioni

- È in corso l'analisi di un problema a causa del quale l'installazione dell'applicazione basata sul contesto di dispositivo configurata in MEM non si applica a HoloLens. [Altre informazioni sulle installazioni del contesto di dispositivo e del contesto utente.](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Durante la configurazione di Autopilot tramite Wi-Fi, potrebbe essere presente un'istanza in cui il profilo di Autopilot non viene scaricato quando viene stabilita la connessione Internet per la prima volta. In questo caso viene presentato il contratto di licenza con l'utente finale e l'utente ha la possibilità di procedere con l'esperienza di installazione non Autopilot. Per ritentare la configurazione con Autopilot, mettere il dispositivo in stato di sospensione e quindi di accensione oppure riavviare il dispositivo e riprovare.
- La funzionalità "Converti tutti i dispositivi di destinazione in Autopilot" non è attualmente supportata in HoloLens.  

### <a name="troubleshooting"></a>Risoluzione dei problemi

Gli articoli seguenti possono essere una risorsa utile per ottenere altre informazioni e risolvere i problemi di Autopilot. Tenere tuttavia presente che questi articoli si basano su Windows 10 Desktop e che non tutte le informazioni possono essere valide per HoloLens:

- [Windows Autopilot: problemi noti](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Risolvere i problemi di registrazione dei dispositivi Windows in Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Conflitti di criteri](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Feedback e supporto per Autopilot

Per inviare commenti e suggerimenti o segnalare problemi, usare uno dei metodi seguenti:

- Per assistenza sulla registrazione del dispositivo, contattare il rivenditore o il distributore.
- Per richieste di supporto generale su Windows Autopilot o per problemi come le assegnazioni di profilo, la creazione di gruppi o i controlli del portale MEM, contattare il supporto [tecnico Microsoft Endpoint Manager](https://docs.microsoft.com/mem/get-support)  
- Se il dispositivo è registrato nel servizio Autopilot e il profilo è [](https://docs.microsoft.com/hololens/) assegnato nel portale MEM, contattare il supporto di HoloLens (vedere la scheda "Supporto"). Aprire un ticket di supporto e, se applicabile, includere screenshot e log acquisendo i log di [diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics) durante la configurazione predefinita.
- Per segnalare un problema dal dispositivo, usa l'app Hub di Feedback in HoloLens. Nella Hub di Feedback selezionare la **categoria Dispositivo**  >  **di gestione** aziendale.
- Per fornire commenti e suggerimenti generali su Autopilot per HoloLens, è possibile inviare questo [sondaggio](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)
