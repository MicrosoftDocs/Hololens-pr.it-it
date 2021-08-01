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
ms.openlocfilehash: 273dcd2180225cf953686ed1c2e5b6524996dba3
ms.sourcegitcommit: 78e5f26014e55c13fee9c2b75a80810fd2e77877
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2021
ms.locfileid: "115009358"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot per HoloLens 2

> [!NOTE]
> La configurazione di Autopilot HoloLens in Microsoft Endpoint Manager è in fase di transizione **dall'anteprima pubblica** **alla disponibilità generale.** Tutti i tenant saranno in grado di configurare Autopilot nell'interfaccia di amministrazione mem.

A partire da Windows Holographic versione 2004, HoloLens 2 supporta la modalità [](/mem/autopilot/self-deploying) di distribuzione automatica di Windows Autopilot con Microsoft Intune (non sono supportati i mdm di terze parti). Gli amministratori possono configurare la Configurazione guidata in Microsoft Endpoint Manager e consentire agli utenti finali di preparare i dispositivi per l'uso aziendale senza alcuna interazione. In questo modo si riducono il sovraccarico di gestione dell'inventario, il costo delle chiamate di preparazione dei dispositivi e di supporto da parte dei dipendenti durante l'esperienza di configurazione. Per altre informazioni, [vedere Windows autopilot.](/mem/autopilot/windows-autopilot)

Come per i dispositivi Surface, è consigliabile che i clienti lavorino con Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (rivenditore o distributore) per registrare i dispositivi con il servizio Autopilot tramite Partner Center. Altri metodi per la registrazione [](/mem/autopilot/add-devices) dei dispositivi sono descritti nella documentazione relativa all'aggiunta di dispositivi, anche se l'uso dei partner di canale Microsoft garantisce il percorso end-to-end più efficace.



Quando un utente avvia il processo di distribuzione automatica di Autopilot, Autopilot completa i passaggi seguenti:

1. Aggiungere il dispositivo al Azure Active Directory (Azure AD). Si noti che Autopilot per HoloLens non supporta l'aggiunta ad Active Directory o Azure AD ibrido join.

1. Usare Azure AD per registrare il dispositivo in Microsoft Endpoint Manager (o in un altro servizio MDM).

1. Scaricare e applicare criteri, certificati, profili di rete e applicazioni destinati ai dispositivi.

1. Effettuare il provisioning del dispositivo.

1. Presentare la schermata di accesso all'utente.

## <a name="configuring-autopilot-for-hololens-2"></a>Configurazione di Autopilot per HoloLens 2

Seguire questa procedura per configurare l'ambiente:

1. [Esaminare i requisiti per Windows Autopilot per HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Abilitare la registrazione MDM automatica](#2-enable-automatic-mdm-enrollment)

1. [Registrare i dispositivi Windows Autopilot.](#3-register-devices-in-windows-autopilot)

1. [Creare un gruppo di dispositivi.](#4-create-a-device-group)

1. [Creare un profilo di distribuzione.](#5-create-a-deployment-profile)

1. [Verificare la configurazione della pagina dello stato della registrazione (ESP).](#6-verify-the-esp-configuration)

1. [Verificare lo stato del profilo dei HoloLens dispositivi.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Esaminare i requisiti per Windows Autopilot per HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Esaminare le sezioni seguenti dell'articolo Windows requisiti di Autopilot:

- [Requisiti di rete](/mem/autopilot/networking-requirements)  
- [Requisiti di licenza](/mem/autopilot/licensing-requirements)  
- [Requisiti di configurazione](/mem/autopilot/configuration-requirements)

**Vedere la sezione "[Requisiti](/windows/deployment/windows-autopilot/self-deploying#requirements)" dell'articolo Windows Autopilot Self-Deploying modalità di rilevamento.** L'ambiente deve soddisfare questi requisiti, nonché i requisiti standard Windows Autopilot. Non è necessario esaminare le sezioni "Procedura dettagliata" e "Convalida" dell'articolo. Le procedure descritte più avanti in questo articolo forniscono i passaggi corrispondenti specifici per HoloLens.

Per informazioni su come registrare i dispositivi e configurare i profili, vedere [2. Registrare i dispositivi Windows Autopilot](#3-register-devices-in-windows-autopilot) e [4. Creare un profilo di distribuzione](#5-create-a-deployment-profile) in questo articolo. Per configurare e gestire i profili in modalità di distribuzione automatica di Autopilot, assicurarsi di avere accesso all'interfaccia Microsoft Endpoint Manager [di amministrazione](https://endpoint.microsoft.com).

#### <a name="review-hololens-os-requirements"></a>Esaminare HoloLens del sistema operativo:

- I dispositivi devono essere [Windows Holographic versione 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) o successiva. Per verificare la versione della build nel dispositivo o eseguire nuovamente il flash nel sistema operativo più recente, usare le istruzioni [ARC (Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) e il [dispositivo.](/hololens/hololens-recovery#clean-reflash-the-device) Si noti che i dispositivi recapitati fino alla fine di settembre 2020 Windows holographic versione 1903 preinstallata. Contattare il rivenditore per assicurarsi che i dispositivi pronti per Autopilot siano spediti all'utente.

- Windows Holographic versione 2004 supporta solo Autopilot tramite connessione ethernet. Assicurarsi che HoloLens sia connesso a ethernet usando una scheda "DA USB-C a Ethernet" prima **di accendere**. All'avvio del dispositivo non è necessaria alcuna interazione dell'utente. Se si prevede l'implementazione di Autopilot in molti dispositivi HoloLens, è consigliabile pianificare l'infrastruttura della scheda. Non è consigliabile usare hub USB, perché spesso richiedono l'installazione di driver di terze parti aggiuntivi che non sono supportati in HoloLens.

- [Windows Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) o versioni successive supportano Autopilot su Wi-Fi, anche se è comunque possibile usare schede ethernet. Per i dispositivi connessi tramite Wi-Fi, l'utente deve solo:

     - Passare attraverso la scena del colibrì
     - Scegliere la lingua e le impostazioni locali
     - Eseguire la calibrazione oculare
     - Stabilire una connessione di rete

- Windows Holographic versione 20H2 supporta [Tenantlockdown CSP e Autopilot,](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)che blocca un dispositivo in un tenant e garantisce che il dispositivo rimanga associato a tale tenant in caso di reimpostazioni o cancellazioni accidentali o intenzionali.  

- Assicurarsi che i dispositivi non siano già membri di Azure AD e non siano registrati in Intune (o in un altro sistema MDM). Il processo di distribuzione automatica di Autopilot completa questi passaggi. Per assicurarsi che tutte le informazioni relative al dispositivo  siano pulite, controllare le pagine Dispositivi nei portali Azure AD e Intune. Si noti che la funzionalità "Converti tutti i dispositivi di destinazione in Autopilot" non è HoloLens al momento.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Abilitare la registrazione MDM automatica:

Per il corretto completamento di Autopilot, è necessario abilitare la registrazione MDM automatica nel portale di Azure. In questo modo il dispositivo verrà registrato senza un utente.

Nella finestra [portale di Azure](https://portal.azure.com/#home) selezionare **Azure Active Directory**  ->  **Mobility (MDM e MAM)**  ->  **Microsoft Intune**. Configurare quindi **l'ambito utente MDM,** sarà necessario selezionare **Tutti.**

Per altre informazioni sulla configurazione, vedere [](/mem/intune/enrollment/quickstart-setup-auto-enrollment) la breve guida seguente sull'abilitazione della registrazione automatica [MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) o la Guida introduttiva alla registrazione automatica.

### <a name="3-register-devices-in-windows-autopilot"></a>3. Registrare i dispositivi in Windows Autopilot

I dispositivi devono essere registrati in Windows Autopilot prima della prima configurazione. Per la documentazione MEM sulla registrazione dei dispositivi, vedere [Adding devices to Autopilot (Aggiunta di dispositivi ad Autopilot).](/mem/autopilot/add-devices)  

Esistono tre modi principali per registrare HoloLens dispositivi:

 - **Il rivenditore può registrare i Partner Center quando si esegue un ordine.**

   > [!NOTE]  
   > Questo è il percorso consigliato per l'aggiunta di dispositivi al servizio Autopilot. [Altre informazioni](/mem/autopilot/partner-registration)  

 - **È possibile [inviare una richiesta di supporto](hololens2-autopilot-registration-support.md) direttamente a Microsoft.**
 - **Recuperare l'hash hardware (noto anche come ID hardware) e registrare manualmente il dispositivo nell'interfaccia di amministrazione di MEM.**

#### <a name="obtain-hardware-hash"></a>Ottenere l'hash hardware
Esistono due modi per recuperare l'hash hardware.
1. È possibile [inviare una richiesta di supporto](hololens2-autopilot-registration-support.md) direttamente a Microsoft.
2. È possibile recuperarlo dal dispositivo. Il dispositivo registra l'hash hardware in un file CSV durante il processo di Configurazione guidata o in un secondo momento quando il proprietario del dispositivo avvia il processo di raccolta dei log di diagnostica (descritto nella procedura seguente). In genere, il proprietario del dispositivo è il primo utente ad accedere al dispositivo.
     > [!WARNING]
     > Nelle build precedenti alla 20H2, se è stata passata la Configurazione guidata e i dati di telemetria sono stati impostati su Richiesto, non è possibile raccogliere l'hash hardware per Autopilot tramite questo metodo. Per raccogliere l'hash hardware tramite questo metodo, impostare l'opzione di telemetria su Completo tramite l'app Impostazioni e selezionare Privacy -> Diagnostica.

    1. Avviare il HoloLens 2 dispositivo.

    1. Nel dispositivo premere **contemporaneamente** i pulsanti Power (Alimentazione) e **Volume Down** (Volume in basso) e quindi rilasciarli. Il dispositivo raccoglie i log di diagnostica e l'hash hardware e li archivia in un set di .zip file.

   1. Per informazioni dettagliate e un video informativo su come eseguire questa operazione, vedere Diagnostica [offline.](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Usare un cavo USB-C per connettere il dispositivo a un computer.

    1. Nel computer aprire Esplora file. Aprire **This PC Internal Archiviazione Documents \\ \<*HoloLens device name*> \\ \\ (Documenti interni del** PC) e individuare il file AutopilotDiagnostics.zip.  

       > [!NOTE]  
       > Il .zip file potrebbe non essere immediatamente disponibile. Se il file non è ancora pronto, è possibile che venga visualizzato un file HoloLensDiagnostics.temp nella cartella Documenti. Per aggiornare l'elenco dei file, aggiornare la finestra.
    
    1. Estrarre il contenuto del file AutopilotDiagnostics.zip.

    1. Nei file estratti individuare il file CSV con prefisso "DeviceHash". Copiare il file in un'unità del computer in cui sarà possibile accedervi in un secondo momento.  

       > [!IMPORTANT]  
       > I dati nel file CSV devono usare l'intestazione e il formato di riga seguenti:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Registrare il dispositivo tramite MEM

1. [Nell Microsoft Endpoint Manager di amministrazione](https://endpoint.microsoft.com)selezionare Dispositivi Windows Windows registrazione e quindi selezionare Dispositivi Importa in  >    >     >   **Programma Windows Autopilot Deployment.**

1. In Add Windows Autopilot devices (Aggiungi dispositivi **Autopilot)** selezionare il file DeviceHash CSV, **selezionare Open**(Apri) e quindi **Import (Importa).**  

   > [!div class="mx-imgBorder"]
   > ![Usare il comando Import per importare l'hash hardware.](./images/hololens-ap-hash-import.png)

1. Al termine dell'importazione, selezionare **Dispositivi**  >  **Windows**  >  **Windows**  >  **Sincronizzazione**  >  **dispositivi**. Il completamento del processo potrebbe richiedere alcuni minuti, a seconda del numero di dispositivi da sincronizzare. Per visualizzare il dispositivo registrato, selezionare **Aggiorna**.  

   > [!div class="mx-imgBorder"]
   > ![Usare i comandi Sincronizza e Aggiorna per visualizzare l'elenco dei dispositivi.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Creare un gruppo di dispositivi

1. [Nell Microsoft Endpoint Manager di amministrazione](https://endpoint.microsoft.com)selezionare **Gruppi**  >  **Nuovo gruppo.**

1. Per **Tipo di gruppo** selezionare **Sicurezza** e quindi immettere il nome e la descrizione del gruppo.

1. Per **Tipo di appartenenza** selezionare **Assegnato** o **Dispositivo dinamico**.

1. Eseguire una delle operazioni seguenti:  

   - Se nel passaggio precedente **è** **stata** selezionata l'opzione Assegnato per tipo di appartenenza, selezionare **Membri** e quindi aggiungere dispositivi Autopilot al gruppo. I dispositivi Autopilot non ancora registrati vengono elencati usando il numero di serie del dispositivo come nome del dispositivo.
   - Se nel **passaggio**  precedente è stata selezionata l'opzione Dispositivi dinamici per Tipo di appartenenza, selezionare Membri del dispositivo dinamici **e** quindi immettere il codice in Regola **avanzata** simile al seguente:
     - Se si vuole creare un gruppo che includa tutti i dispositivi AutoPilot, digitare: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Il campo tag di gruppo di Intune viene mappato **all'attributo OrderID** Azure AD dispositivi. Se si vuole creare un gruppo che includa tutti i dispositivi Autopilot con un tag di gruppo specifico (il Azure AD orderID del dispositivo), è necessario digitare: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Se si vuole creare un gruppo che includa tutti i dispositivi Autopilot con un ID ordine di acquisto specifico, digitare: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Queste regole hanno come destinazione attributi univoci per i dispositivi Autopilot.
1. Selezionare **Salva** e quindi **Crea**.

### <a name="5-create-a-deployment-profile"></a>5. Creare un profilo di distribuzione

1. [Nell'Microsoft Endpoint Manager di amministrazione](https://endpoint.microsoft.com)selezionare Dispositivi Windows Windows registrazione Windows profili di  >    >    >  **distribuzione Autopilot**  >  **Creare**  >  profili HoloLens .
   ![L'elenco a discesa Crea profilo include HoloLens elemento.](./images/hololens-ap-enrollment-profiles.png)

1. Immettere un nome e una descrizione del profilo e quindi selezionare **Avanti.**  
   Verrà visualizzato un elenco che **include** HoloLens . Se questa opzione non è presente, usare una delle opzioni [feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) per contattarci.

   > [!div class="mx-imgBorder"]
   > ![Aggiungere un nome e una descrizione del profilo](./images/hololens-ap-profile-name.png)

1. Nella pagina **Out-of-box experience (OOBE)** la maggior parte delle impostazioni è preconfigurato per semplificare la configurazione fuori rete per questa valutazione. Facoltativamente, è possibile configurare le impostazioni seguenti:  

   - **Lingua (area geografica):** selezionare la lingua per La versione di OOBE. È consigliabile selezionare una lingua dall'elenco delle [lingue supportate per HoloLens 2](hololens2-language-support.md).
   - **Configura automaticamente la tastiera:** per assicurarsi che la tastiera corrisponda alla lingua selezionata, selezionare **Sì.**
   - **Applica** il modello di nome del dispositivo: per  impostare automaticamente il nome del dispositivo durante la Configurazione automatica, selezionare Sì e quindi immettere la frase del modello e i segnaposto in **Immettere** un nome, ad esempio immettere un prefisso e un segnaposto per un numero casuale a quattro `%RAND:4%` &mdash; cifre.
     > [!NOTE]  
     > Se si usa un modello di nome di dispositivo, il processo di configurazione della configurazione del sistema operativo riavvia il dispositivo un'altra volta dopo aver applicato il nome del dispositivo e prima che il dispositivo venga Azure AD. Questo riavvio consente di attivare il nuovo nome.  

   > [!div class="mx-imgBorder"]
   > ![Configurare le impostazioni di Configurazione guidata](./images/hololens-ap-profile-oobe.png)

1. Dopo aver configurato le impostazioni, selezionare **Avanti.**
1. Nella pagina **Tag ambito** aggiungere facoltativamente i tag di ambito da applicare a questo profilo. Per altre informazioni sui tag di ambito, vedere [Use role-based access control and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags.md) (Usare il controllo degli accessi in base al ruolo e i tag di ambito per l'IT distribuito). Al termine, selezionare **Avanti**.
1. Nella pagina **Assegnazioni** selezionare **Gruppi selezionati per** Assegna **a**.
1. In **GRUPPI SELEZIONATI** selezionare + Selezionare i gruppi da **includere.**
1. **Nell'elenco Selezionare i gruppi** da includere selezionare il gruppo di dispositivi creato per i dispositivi HoloLens Autopilot e quindi selezionare **Avanti.**  
  
   Per escludere i gruppi, selezionare **Selezionare** i gruppi da escludere e selezionare i gruppi da escludere.

   > [!div class="mx-imgBorder"]
   > ![Assegnazione di un gruppo di dispositivi al profilo.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Nella pagina **Rivedi e crea** rivedere le impostazioni e quindi selezionare **Crea** per creare il profilo.  

   > [!div class="mx-imgBorder"]
   > ![Rivedere e creare](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. Verificare la configurazione esp

La pagina Stato registrazione (ESP) visualizza lo stato del processo di configurazione completo del dispositivo eseguito quando un utente gestito MDM accede a un dispositivo per la prima volta. Assicurarsi che la configurazione esp sia simile alla seguente e verificare che le assegnazioni siano corrette.  

> [!div class="mx-imgBorder"]
> ![Configurazione esp](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. Verificare lo stato del profilo dei HoloLens dispositivi

1. Nell Microsoft Endpoint Manager admin center selezionare **Dispositivi**  >  **Windows**  >  **Windows dispositivi**  >  .

1. Verificare che i HoloLens siano elencati e che il relativo stato del profilo sia **Assegnato**.  

   > [!NOTE]  
   > L'assegnazione del profilo al dispositivo potrebbe richiedere alcuni minuti.  

   > [!div class="mx-imgBorder"]
   > ![Assegnazioni di dispositivi e profili.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot per l HoloLens 2'esperienza utente

Una volta completate le istruzioni precedenti, gli utenti HoloLens 2 eseguiranno l'esperienza seguente per effettuare il provisioning dei HoloLens dispositivi:  

1. L'esperienza di Autopilot richiede l'accesso a Internet. Usare una delle opzioni seguenti per fornire l'accesso a Internet:

    - Connessione il dispositivo in una rete Wi-Fi configurazione automatica e quindi lasciare che rilevi automaticamente l'esperienza di Autopilot. Questa è l'unica volta che sarà necessario interagire con La configurazione guidata finché l'esperienza di Autopilot non viene completata da sola. Si noti che per impostazione HoloLens 2 attende 10 secondi per rilevare Autopilot dopo il rilevamento di Internet. Se non viene rilevato alcun profilo di autopilot entro 10 secondi, la Configurazione automatica presenterà il servizio EULA. Se si verifica questo scenario, riavviare il dispositivo in modo da poter eseguire un altro tentativo per rilevare Autopilot. Si noti anche che la configurazione automatica può attendere per un periodo indefinito per Autopilot solo se nel dispositivo è impostato il criterio TenantLockdown.

    - Connessione dispositivo con Ethernet usando schede "da USB-C a Ethernet" per la connettività Internet cablata e HoloLens 2 completare automaticamente l'esperienza di Autopilot.

    - Connessione dispositivo con schede "da USB-C a Wifi" per la connettività Internet wireless e HoloLens 2 completare automaticamente l'esperienza di Autopilot.

        > [!IMPORTANT]  
       > I dispositivi che tentano di Wi-Fi in Configurazione guidata per Autopilot devono essere Windows [Holographic, versione 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > Per i dispositivi che usano schede ethernet è necessario connettere il dispositivo alla rete prima dell'avvio della Configurazione guidata. Il dispositivo determina se è in corso il provisioning come dispositivo Autopilot durante la prima schermata della configurazione. Se il dispositivo non è in grado di connettersi alla rete o se si sceglie di non effettuare il provisioning del dispositivo come dispositivo Autopilot, non è possibile passare al provisioning di Autopilot in un secondo momento. È invece necessario avviare questa procedura per eseguire il provisioning del dispositivo come dispositivo Autopilot.

1. Il dispositivo dovrebbe avviare automaticamente la Configurazione automatica del sistema operativo. Non interagire con La versione di OOBE. Invece sedersi, indietro e relax! Consentire HoloLens 2 la connettività di rete e consentirla di completare automaticamente la configurazione guidata. Il dispositivo può essere riavviato durante la configurazione del sistema operativo. Le schermate di OOBE dovrebbero essere simili alle seguenti.

   ![Passaggio 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE passaggio 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE passaggio 3](./images/autopilot-device-setup.jpg)

1. Al termine della Configurazione fuori rete, è possibile accedere al dispositivo usando il nome utente e la password.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP e Autopilot

HoloLens 2 dispositivi supportano TenantLockdown CSP a Windows Holographic, versione 20H2. Questo provider di servizi di configurazione mantiene i dispositivi nel tenant dell'organizzazione bloccandoli a tale tenant anche tramite la reimpostazione o il reflash del dispositivo.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP consente HoloLens 2 essere associato alla registrazione MDM usando solo Autopilot. Quando il nodo RequireNetworkInOOBE del provider di servizi di configurazione TenantLockdown è impostato su true o false (inizialmente impostato) su HoloLens 2, tale valore rimane nel dispositivo nonostante il nuovo flashing, gli aggiornamenti del sistema operativo e così via.

Dopo che il nodo RequireNetworkInOOBE dei CSP TenantLockdown è impostato su true in HoloLens 2, la configurazione del servizio OOBE attende a tempo indefinito che il profilo Autopilot sia scaricato e applicato correttamente, dopo la connettività di rete.

Quando il nodo RequireNetworkInOOBE dei CSP TenantLockdown è impostato su true HoloLens 2, le operazioni seguenti non sono consentite in Configurazione configurazione di sistema:

- Creazione di un utente locale tramite il provisioning di runtime 
- Esecuzione Azure AD'operazione di join tramite il provisioning di runtime 
- Selezione del proprietario del dispositivo nell'esperienza di configurazione del sistema operativo 

#### <a name="how-to-set-this-using-intune"></a>Come impostare questa opzione con Intune? 
1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato e specificare true per il nodo RequireNetworkInOOBE, come illustrato di seguito.
Il valore URI OMA deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Impostazione del blocco tennant tramite OMA-URI](images/hololens-tenant-lockdown.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo a tale gruppo di dispositivi.

1. Rendere il HoloLens 2 membro del dispositivo del gruppo creato nel passaggio precedente e attivare la sincronizzazione.  

Verificare che la configurazione del dispositivo sia stata applicata correttamente nel portale di Intune. Dopo aver applicato correttamente la configurazione del dispositivo HoloLens 2 dispositivo, gli effetti di TenantLockdown saranno attivi.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Come impostare RequireNetworkInOOBE di TenantLockdown HoloLens 2 intune?

1. Rimuovere il HoloLens 2 dal gruppo di dispositivi a cui è stata assegnata in precedenza la configurazione del dispositivo creata in precedenza.

1. Creare un profilo di configurazione del dispositivo personalizzato basato su URI OMA e specificare false per RequireNetworkInOOBE, come illustrato di seguito.
Il valore URI OMA deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot dell'impostazione di RequireNetworkInOOBE su false tramite URI OMA in Intune](images/hololens-tenant-lockdown-false.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo a tale gruppo. 

1. Rendere il HoloLens 2 membro del dispositivo del gruppo creato nel passaggio precedente e attivare la sincronizzazione.

Verificare che la configurazione del dispositivo sia stata applicata correttamente nel portale di Intune. Dopo che la configurazione del dispositivo è stata applicata HoloLens 2 dispositivo, gli effetti di TenantLockdown saranno inattivi.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Cosa accade durante la configurazione della configurazione automatica, se il profilo Autopilot non è assegnato in un HoloLens dopo che TenantLockdown è stato impostato su true? 
La configurazione del sistema operativo attenderà a tempo indeterminato il download del profilo Autopilot e verrà visualizzata la finestra di dialogo seguente. Per rimuovere gli effetti di TenantLockdown, il dispositivo deve essere registrato prima con il tenant originale usando solo Autopilot e RequireNetworkInOOOBE deve essere impostato come descritto nel passaggio precedente prima che le restrizioni introdotte da TenantLockdown CSP siano rimosse.

![Visualizzazione nel dispositivo per quando i criteri vengono applicati al dispositivo.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Problemi noti & limitazioni

- È in corso l'analisi di un problema a causa del quale l'installazione dell'applicazione basata sul contesto di dispositivo configurata in MEM non si applica HoloLens. [Altre informazioni sulle installazioni del contesto di dispositivo e del contesto utente.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Durante la configurazione di Autopilot tramite Wi-Fi, potrebbe essere presente un'istanza in cui il profilo Autopilot non viene scaricato quando viene stabilita la connessione Internet per la prima volta. In questo caso viene presentato il Contratto di licenza con l'utente finale e l'utente ha la possibilità di procedere con l'esperienza di installazione non Autopilot. Per ritentare la configurazione con Autopilot, mettere il dispositivo in sospensione e quindi accensione oppure riavviare il dispositivo e riprovare.
- La funzionalità "Convert all targeted devices to Autopilot" (Converti tutti i dispositivi di destinazione in Autopilot) non è HoloLens attualmente.  

### <a name="troubleshooting"></a>Risoluzione dei problemi

Gli articoli seguenti possono essere una risorsa utile per ottenere altre informazioni e risolvere i problemi di Autopilot, tuttavia tenere presente che questi articoli sono basati su Windows 10 Desktop e che non tutte le informazioni possono essere applicabili a HoloLens:

- [Windows Autopilot - Problemi noti](/mem/autopilot/known-issues)
- [Risolvere i problemi di registrazione dei dispositivi Windows in Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Conflitti di criteri](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Commenti e supporto per Autopilot

Per inviare commenti e suggerimenti o segnalare problemi, usare uno dei metodi seguenti:

- Per supporto sulla registrazione del dispositivo, contattare il rivenditore o il distributore.
- Per informazioni di supporto generale su Windows Autopilot o per problemi come assegnazioni di profilo, creazione di gruppi o controlli del portale MEM, contattare Microsoft Endpoint Manager [supporto tecnico](/mem/get-support)  
- Se il dispositivo è registrato nel servizio Autopilot e il profilo viene assegnato nel portale MEM, contattare il supporto HoloLens [(vedere](/hololens/) la scheda "Supporto"). Aprire un ticket di supporto e, se applicabile, includere screenshot e log acquisendo log [di diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics) durante la configurazione predefinita.
- Per segnalare un problema dal dispositivo, usare l'app Hub di Feedback nel dispositivo HoloLens. In Hub di Feedback selezionare la categoria Enterprise **Dispositivo di**  >  **gestione.**
- Per inviare commenti e suggerimenti generali su Autopilot HoloLens, è possibile inviare questo [sondaggio](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Eliminare dispositivi di AutoPilot

È possibile che non si voglia più usare un dispositivo per Autopilot o registrare i dispositivi in un tenant diverso. Se si vuole eseguire questa operazione, leggere h[ow per eliminare i dispositivi Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)