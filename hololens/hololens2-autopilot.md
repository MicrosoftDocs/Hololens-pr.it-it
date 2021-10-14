---
title: Windows Autopilot per HoloLens 2
description: Informazioni su come configurare, configurare e risolvere i problemi di Autopilot HoloLens 2 dispositivi.
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Pilota automatico
manager: sekerawa
ms.openlocfilehash: 05eb629e05395f04ddb8723d58d41db4161896fa
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964582"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot per HoloLens 2

## <a name="overview"></a>Panoramica

Per eseguire la distribuzione su larga scala, è consigliabile iniziare a Windows Autopilot. È considerato "low touch" perché semplifica notevolmente la configurazione HoloLens per gli utenti IT e finali. 

A livello generale, un amministratore IT crea in genere le configurazioni pronte per l'azienda e HoloLens 2 dispositivi nei portali MDM. Quando i dispositivi HoloLens 2 vengono avviati con configurazione guidata e si connettono a Internet, le configurazioni aziendali per il dispositivo HoloLens 2 registrato vengono scaricate e applicate automaticamente per rendere i dispositivi pronti per l'azienda senza alcun intervento dell'utente.

Per altre informazioni, vedere [Panoramica di Windows Autopilot | Microsoft Docs](/mem/autopilot/windows-autopilot) articolo.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Scenario di Autopilot supportato in HoloLens 2

> [!NOTE]
> La configurazione di Autopilot HoloLens in Microsoft Endpoint Manager è in fase di transizione **dall'anteprima pubblica** **alla disponibilità generale.** Tutti i tenant saranno in grado di configurare Autopilot nell'interfaccia di amministrazione mem.

A partire da Windows Holographic versione 2004, HoloLens 2 supporta la modalità [](/mem/autopilot/self-deploying) di distribuzione automatica di Windows Autopilot con Microsoft Intune (i mdm di terze parti non sono supportati). Questa configurazione riduce il sovraccarico di gestione dell'inventario, il costo delle chiamate di preparazione dei dispositivi e di supporto da parte dei dipendenti durante l'esperienza di configurazione. Per altre informazioni, [vedere Windows autopilot.](/mem/autopilot/windows-autopilot)

Come per i dispositivi Surface, è consigliabile che i clienti lavorino con Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (rivenditore o distributore) per registrare i dispositivi con il servizio Autopilot tramite Partner Center.

Quando un utente avvia il processo di distribuzione automatica di Autopilot, Autopilot completa i passaggi seguenti:

1. Aggiungere il dispositivo al Azure Active Directory (Azure AD). Autopilot per HoloLens non supporta l'aggiunta ad Active Directory o l'aggiunta Azure AD ibrida.

1. Usare Azure AD per registrare il dispositivo in Microsoft Endpoint Manager (o in un altro servizio MDM).

1. Scaricare e applicare criteri, certificati, profili di rete e applicazioni destinati ai dispositivi.

1. Presentare la schermata di accesso all'utente.

## <a name="configuring-autopilot-for-hololens-2"></a>Configurazione di Autopilot per HoloLens 2

Seguire questa procedura per configurare l'ambiente:

1. [Esaminare i requisiti per Windows Autopilot per HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Abilitare la registrazione MDM automatica](#2-enable-automatic-mdm-enrollment)

1. (solo per Intune) [Assicurarsi che la registrazione MDM non sia bloccata per Windows dispositivi.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Registrare i dispositivi Windows Autopilot.](#4-register-devices-in-windows-autopilot)

1. [Creare un gruppo di dispositivi.](#5-create-a-device-group)

1. [Creare un profilo autopilot e assegnarlo al gruppo di dispositivi.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Creare la configurazione della pagina dello stato della registrazione (ESP) e assegnarla al gruppo di dispositivi.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Verificare lo stato del profilo dei HoloLens dispositivi.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Esaminare i requisiti per Windows Autopilot per HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Esaminare le sezioni seguenti dell'articolo Windows requisiti di Autopilot:

- [Requisiti di rete](/mem/autopilot/networking-requirements)  
- [Requisiti di licenza](/mem/autopilot/licensing-requirements)  
- [Requisiti di configurazione](/mem/autopilot/configuration-requirements)

**Vedere la sezione "[Requisiti](/windows/deployment/windows-autopilot/self-deploying#requirements)" dell'articolo Windows Autopilot Self-Deploying modalità predefinita.** L'ambiente deve soddisfare questi requisiti e i requisiti standard Windows Autopilot. Non è necessario esaminare le sezioni "Procedura dettagliata" e "Convalida" dell'articolo. Le procedure descritte più avanti in questo articolo forniscono i passaggi corrispondenti specifici per HoloLens.

Assicurarsi che i dispositivi non siano già membri di Azure AD e non siano registrati in Intune (o in un altro sistema MDM). Il processo di distribuzione automatica di Autopilot completa questi passaggi. Per assicurarsi che tutte le informazioni relative al dispositivo  siano pulite, controllare le pagine Dispositivi nei portali Azure AD e Intune. La funzionalità Convert all targeted devices to Autopilot" (Converti tutti i dispositivi di destinazione in Autopilot) non è HoloLens al momento.

#### <a name="review-hololens-os-requirements"></a>Esaminare HoloLens del sistema operativo:

Per verificare la versione della build nel dispositivo o eseguire il reflash al sistema operativo più recente, usare le istruzioni [ARC (Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) e la [reflash del dispositivo.](hololens-recovery.md) I dispositivi recapitati fino alla fine di settembre 2020 Windows holographic versione 1903 preinstallata. Contattare il rivenditore per assicurarsi che i dispositivi pronti per Autopilot siano spediti all'utente.

 Versione minima del sistema operativo | Funzionalità supportata | Commenti
 ------ | ------ | ------  
 [Windows Holographic, versione 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) o successiva | 1. Scenario di distribuzione automatica di Autopilot in HoloLens 2. | Il download del profilo autopilot è supportato solo tramite Ethernet. Assicurarsi che HoloLens sia connesso a ethernet usando una scheda "DA USB-C a Ethernet" prima **di accendere**.  Se si prevede l'implementazione di Autopilot in molti dispositivi HoloLens, è consigliabile pianificare l'infrastruttura della scheda. Non è consigliabile usare hub USB, perché spesso richiedono l'installazione di driver di terze parti che non sono supportati in HoloLens.
 [Windows Holographic, versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) o successiva | 1. Download del profilo autopilot tramite Wi-Fi. <br> 2. [CSP di blocco del tenant e Autopilot](#tenant-lockdown-csp-and-autopilot) per bloccare i dispositivi con il tenant specificato di Autopilot. | Se lo si desidera, è comunque possibile usare schede ethernet. Per i dispositivi connessi tramite Wi-Fi, l'utente deve solo: <ul> <li> Passare attraverso la scena del colibrì. </li> <li> Scegliere la lingua e le impostazioni locali. </li> <li> Eseguire la calibrazione oculare. </li> <li> Connettersi correttamente alla rete Wi-Fi desiderata. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Abilitare la registrazione MDM automatica:

Per il corretto completamento di Autopilot, è necessario abilitare la registrazione MDM automatica nel portale di Azure. In questo modo il dispositivo verrà registrato senza un utente.

Per altre informazioni sulla [configurazione,](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) vedere [](/mem/intune/enrollment/quickstart-setup-auto-enrollment) la breve guida seguente sull'abilitazione della registrazione automatica MDM o la Guida introduttiva alla registrazione automatica.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Assicurarsi che la registrazione MDM non sia bloccata per Windows dispositivi.

Per il corretto completamento di Autopilot, è necessario assicurarsi che i dispositivi HoloLens registrazione. Poiché HoloLens viene considerato un dispositivo Windows, non sarà necessario applicare restrizioni di registrazione che potrebbero bloccare la distribuzione. [Esaminare questo elenco di restrizioni](/mem/intune/enrollment/enrollment-restrictions-set) e assicurarsi che sia possibile registrare i dispositivi.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Registrare i dispositivi in Windows Autopilot

I dispositivi devono essere registrati in Windows Autopilot prima della prima configurazione.

Esistono tre modi principali per registrare HoloLens dispositivi:

 - **Il rivenditore può registrare i Partner Center quando si esegue un ordine.**

   > [!NOTE]  
   > Questo è il percorso consigliato per l'aggiunta di dispositivi al servizio Autopilot. [Altre informazioni](/mem/autopilot/partner-registration)  

 - **È possibile [inviare una richiesta di supporto](hololens2-autopilot-registration-support.md) direttamente a Microsoft.**
 - **Recuperare l'hash hardware (noto anche come ID hardware) e registrare manualmente il dispositivo nell'interfaccia di amministrazione di MEM.**

#### <a name="obtain-hardware-hash"></a>Ottenere l'hash hardware

È possibile recuperare l'hash hardware dal dispositivo. Il dispositivo registra l'hash hardware in un file CSV durante il processo di Configurazione guidata o in un secondo momento quando il proprietario del dispositivo avvia il processo di raccolta dei log di diagnostica (descritto nella procedura seguente). In genere, il proprietario del dispositivo è il primo utente ad accedere al dispositivo.

> [!WARNING]
> Nelle build precedenti alla 20H2, se è stata passata la Configurazione guidata e i dati di telemetria sono stati impostati su Richiesto, non è possibile raccogliere l'hash hardware per Autopilot tramite questo metodo. Per raccogliere l'hash hardware tramite questo metodo, impostare l'opzione di telemetria su Completo tramite l'app Impostazioni e selezionare **Diagnostica della**  >  **privacy.**

1. Avviare il HoloLens 2 dispositivo.

1. Nel dispositivo premere **contemporaneamente** i pulsanti Power (Alimentazione) e **Volume Down** (Volume in basso) e rilasciarli. Il dispositivo raccoglie i log di diagnostica e l'hash hardware e li archivia in un set di .zip file.

1. Per informazioni dettagliate e un video informativo su come eseguire questa operazione, vedere Diagnostica [offline.](hololens-diagnostic-logs.md#offline-diagnostics)

1. Usare un cavo USB-C per connettere il dispositivo a un computer.

1. Nel computer aprire Esplora file. Aprire <b>Questo \\ PC</b> < *HoloLens nome del dispositivo* Interno Archiviazione > <b> \\ \\ Documenti</b>e individuare il file AutopilotDiagnostics.zip.  

   > [!NOTE]  
   > Il .zip file potrebbe non essere immediatamente disponibile. Se il file non è ancora pronto, è possibile che venga visualizzato un file HoloLensDiagnostics.temp nella cartella Documenti. Per aggiornare l'elenco dei file, aggiornare la finestra.

1. Estrarre il contenuto del file AutopilotDiagnostics.zip.

1. Nei file estratti individuare il file CSV con prefisso "DeviceHash". Copiare il file in un'unità del computer in cui sarà possibile accedervi in un secondo momento.  

   > [!IMPORTANT]  
   > I dati nel file CSV devono usare l'intestazione e il formato di riga seguenti:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Registrare il dispositivo tramite MEM

1. [Nell Microsoft Endpoint Manager di amministrazione](https://endpoint.microsoft.com)selezionare Dispositivi Windows Windows registrazione e quindi selezionare Dispositivi Importa  >    >  in   >   **Programma Windows Autopilot Deployment.**

1. In Add Windows Autopilot devices (Aggiungi dispositivi **Autopilot)** selezionare il file DEVICEHash CSV, selezionare **Open**(Apri) e quindi **Import (Importa).**  

   > [!div class="mx-imgBorder"]
   > ![Usare il comando Import per importare l'hash hardware.](./images/hololens-ap-hash-import.png)

1. Al termine dell'importazione, selezionare **Dispositivi Windows**  >    >  **Windows la**  >  **sincronizzazione dei**  >  **dispositivi.** Il completamento del processo potrebbe richiedere alcuni minuti, a seconda del numero di dispositivi da sincronizzare. Per visualizzare il dispositivo registrato, selezionare **Aggiorna.**  

   > [!div class="mx-imgBorder"]
   > ![Usare i comandi Sincronizza e Aggiorna per visualizzare l'elenco dei dispositivi.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Creare un gruppo di dispositivi

1. [Nell Microsoft Endpoint Manager di amministrazione](https://endpoint.microsoft.com)selezionare Gruppi **Nuovo**  >  **gruppo.**

1. Per **Tipo di gruppo** selezionare **Sicurezza** e quindi immettere un nome e una descrizione per il gruppo.

1. Per **Tipo di appartenenza** selezionare **Assegnato** o **Dispositivo dinamico.**

1. Eseguire una delle operazioni seguenti:  

   - Se nel passaggio **precedente è** **stato** selezionato Assegnato per Tipo di appartenenza, selezionare Membri **e** quindi aggiungere i dispositivi Autopilot al gruppo. I dispositivi Autopilot non ancora registrati vengono elencati usando il numero di serie del dispositivo come nome del dispositivo.
   - Se nel passaggio precedente **è** stata selezionata l'opzione Dispositivi **dinamici** per Tipo di appartenenza, selezionare Membri dispositivo dinamico **e** quindi immettere in **Regola** avanzata un codice simile al seguente:
     - Se si vuole creare un gruppo che includa tutti i dispositivi AutoPilot, digitare: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Il campo tag di gruppo di Intune esegue il mapping **all'attributo OrderID** Azure AD dispositivi. Se si vuole creare un gruppo che includa tutti i dispositivi Autopilot con un tag di gruppo specifico (il Azure AD orderID del dispositivo), è necessario digitare:`(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Se si vuole creare un gruppo che includa tutti i dispositivi Autopilot con un ID ordine di acquisto specifico, digitare: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Queste regole hanno come destinazione attributi univoci per i dispositivi Autopilot.
1. Selezionare **Salva** e quindi **Crea.**

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Creare un profilo autopilot e assegnarlo al gruppo di dispositivi

1. [Nell Microsoft Endpoint Manager di amministrazione](https://endpoint.microsoft.com)selezionare Dispositivi Windows Windows registrazione Windows  >    >    >  **profili di distribuzione autopilot**  >    >  Crea profilo HoloLens .
   ![L'elenco a discesa Crea profilo include HoloLens elemento.](./images/hololens-ap-enrollment-profiles.png)

1. Immettere un nome e una descrizione per il profilo e quindi selezionare **Avanti.**  
   Verrà visualizzato un elenco che include **HoloLens**. Se questa opzione non è presente, usare una delle opzioni [commenti](hololens2-autopilot.md#feedback-and-support-for-autopilot) e suggerimenti per contattare Microsoft.

   > [!div class="mx-imgBorder"]
   > ![Aggiungere un nome e una descrizione del profilo.](./images/hololens-ap-profile-name.png)

1. Nella pagina **Configurazione** fuori rete la maggior parte delle impostazioni è preconfigurato per semplificare la Configurazione fuori rete per questa valutazione. Facoltativamente, è possibile configurare le impostazioni seguenti:  

   - **Lingua (area geografica):** selezionare la lingua per la Versione guidata. È consigliabile selezionare una lingua dall'elenco delle [lingue supportate per HoloLens 2](hololens2-language-support.md).
   - **Configura automaticamente la** tastiera: per assicurarsi che la tastiera corrisponda alla lingua selezionata, selezionare **Sì.**
   - **Applica** il modello di nome di dispositivo: per  impostare automaticamente il nome del dispositivo durante la Configurazione automatica, selezionare Sì e quindi immettere la frase modello e i segnaposto in **Immettere** un nome. Ad esempio, immettere un prefisso e un segnaposto per un numero casuale di quattro `%RAND:4%` &mdash; cifre.
     > [!NOTE]  
     > Se si usa un modello di nome di dispositivo, il processo di Configurazione Azure AD riavvia il dispositivo una volta dopo l'applicazione del nome del dispositivo. Questo riavvio consente di attivare il nuovo nome.  

   > [!div class="mx-imgBorder"]
   > ![Configurare le impostazioni della Configurazione guidata.](./images/hololens-ap-profile-oobe.png)

1. Dopo aver configurato le impostazioni, selezionare **Avanti.**
1. Nella pagina **Tag di** ambito aggiungere facoltativamente i tag di ambito da applicare a questo profilo. Per altre informazioni sui tag di ambito, vedere [Use role-based access control and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags.md) (Usare il controllo degli accessi in base al ruolo e i tag di ambito per l'IT distribuito). Al termine, selezionare **Avanti**.
1. Nella pagina **Assegnazioni** selezionare Gruppi **selezionati per** **Assegna a.**
1. In **GRUPPI SELEZIONATI** selezionare + Selezionare i gruppi per **includere**.
1. **Nell'elenco Selezionare i** gruppi da includere selezionare il gruppo di dispositivi creato per i dispositivi autopilot HoloLens e quindi selezionare **Avanti.**  
  
   Se si vogliono escludere gruppi, selezionare **Selezionare i gruppi** da escludere e selezionare i gruppi da escludere.

   > [!div class="mx-imgBorder"]
   > ![Assegnazione di un gruppo di dispositivi al profilo.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Nella pagina **Rivedi e crea** rivedere le impostazioni e quindi selezionare **Crea** per creare il profilo.  

   > [!div class="mx-imgBorder"]
   > ![Rivedi e crea.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Creare la configurazione della pagina dello stato della registrazione (ESP) e assegnarla al gruppo di dispositivi

La pagina Stato registrazione (ESP) visualizza lo stato del processo di configurazione completo del dispositivo che viene eseguito quando un utente gestito da MDM accede a un dispositivo per la prima volta. Assicurarsi che la configurazione esp sia simile alla seguente e verificare che le assegnazioni siano corrette.  

> [!div class="mx-imgBorder"]
> ![Configurazione esp.](./images/hololens-ap-profile-settings.png)

Per altre informazioni su ESP, vedere [Set up the Enrollment Status Page - Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Verificare lo stato del profilo dei HoloLens dispositivi

1. Nell Microsoft Endpoint Manager di amministrazione selezionare **Dispositivi**  >  **Windows**  >  **Windows registrazione**  >  **Dispositivi.**

1. Verificare che i dispositivi HoloLens siano elencati e che il relativo stato del profilo sia **Assegnato**.  

   > [!NOTE]  
   > L'assegnazione del profilo al dispositivo potrebbe richiedere alcuni minuti.  

   > [!div class="mx-imgBorder"]
   > ![Assegnazioni di dispositivi e profili.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot per l HoloLens 2'esperienza utente

Dopo aver completato le istruzioni precedenti, gli utenti HoloLens 2 eseguiranno l'esperienza seguente per effettuare il provisioning dei HoloLens seguenti:  

1. L'esperienza di Autopilot richiede l'accesso a Internet. Usare una delle opzioni seguenti per fornire l'accesso a Internet:

    - Connessione il dispositivo a una rete Wi-Fi in Configurazione automatica e quindi consentire al dispositivo di rilevare automaticamente l'esperienza di Autopilot. Questa è l'unica volta che sarà necessario interagire con la Configurazione guidata fino a quando l'esperienza di Autopilot non viene completata da sola.

    - Connessione dispositivo con Ethernet usando schede "da USB-C a Ethernet" per la connettività Internet cablata e HoloLens 2 completare automaticamente l'esperienza di Autopilot.

    - Connessione dispositivo con schede "da USB-C a Wi-Fi" per la connettività Internet wireless e HoloLens 2 completare automaticamente l'esperienza di Autopilot.

        > [!IMPORTANT]  
       > I dispositivi che tentano Wi-Fi reti virtuali nella Configurazione guidata per Autopilot devono essere in Windows [Holographic, versione 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > Per i dispositivi che usano schede ethernet è necessario connettere il dispositivo alla rete prima dell'avvio della Configurazione guidata. Il dispositivo determina se è in corso il provisioning come dispositivo Autopilot nella prima schermata della Configurazione automatica. Se il dispositivo non può connettersi alla rete o se si sceglie di non effettuare il provisioning del dispositivo come dispositivo Autopilot, non è possibile passare al provisioning di Autopilot in un secondo momento. È invece necessario avviare questa procedura per eseguire il provisioning del dispositivo come dispositivo Autopilot.

1. Il dispositivo dovrebbe avviare automaticamente la Configurazione automatica del sistema operativo. Non interagire con la Modalità tutto il sistema operativo.

    > [!IMPORTANT]
    > Non interagire con la Configurazione fuori programma o premere il pulsante di alimentazione per portare il sistema in standby/arresto, mentre Autopilot è in corso. Ciò potrebbe causare il non completamento del flusso di Autopilot.

   Consentire HoloLens 2 la connettività di rete e consentire il completamento automatico della Configurazione guidata. Il dispositivo può essere riavviato durante la Configurazione configurazione. Le schermate della Procedura guidata dovrebbero essere simili alle seguenti.

   ![Passaggio 1 della Procedura dettagliata. ](./images/autopilot-welcome.jpg)
    ![ Passaggio 2 della Procedura dettagliata. ](./images/autopilot-step-complete.jpg)
    ![ Passaggio 3 della Procedura dettagliata.](./images/autopilot-device-setup.jpg)

1. Al termine della Configurazione fuori rete, è possibile accedere al dispositivo usando il nome utente e la password.

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>Provider di servizi di configurazione e Autopilot per il blocco del tenant

HoloLens 2 supportano il provider di servizi di configurazione TenantLockdown a Windows Holographic, versione 20H2. Questo CSP mantiene i dispositivi nel tenant dell'organizzazione bloccandoli su tale tenant anche tramite reimpostazione o reflash del dispositivo.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP consente HoloLens 2 essere associato alla registrazione MDM usando solo Autopilot. Quando il nodo RequireNetworkInOOBE del provider di servizi di configurazione TenantLockdown è impostato sul valore true o false (inizialmente impostato) su HoloLens 2, tale valore rimane nel dispositivo nonostante la reflashing, gli aggiornamenti del sistema operativo e così via.

Quando il nodo RequireNetworkInOOBE dei CSP TenantLockdown è impostato su true in HoloLens 2, la Configurazione remota attende per un periodo illimitato che il profilo autopilot sia scaricato e applicato correttamente, dopo la connettività di rete.

Quando il nodo RequireNetworkInOOBE dei CSP TenantLockdown è impostato su true in HoloLens 2, le operazioni seguenti non sono consentite nella Configurazione operativa:

- Creazione di un utente locale con il provisioning di runtime
- Esecuzione di Azure AD'operazione di join tramite il provisioning di runtime
- Selezione del proprietario del dispositivo nell'esperienza di configurazione della configurazione

#### <a name="how-to-set-this-using-intune"></a>Come si imposta questa opzione con Intune?

1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato e specificare true per il nodo RequireNetworkInOOBE, come illustrato di seguito.
Il valore URI OMA deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Impostazione del blocco del tennant tramite URI OMA.](images/hololens-tenant-lockdown.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo a tale gruppo di dispositivi.

1. Impostare il HoloLens 2 del dispositivo del gruppo creato nel passaggio precedente e attivare la sincronizzazione.  

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Dopo che la configurazione del dispositivo è stata applicata HoloLens 2 dispositivo, gli effetti di TenantLockdown saranno attivi.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Come si annulla l'installazione di RequireNetworkInOOBE di TenantLockdown HoloLens 2 intune?

1. Rimuovere il HoloLens 2 dal gruppo di dispositivi a cui è stata assegnata in precedenza la configurazione del dispositivo creata in precedenza.

1. Creare un profilo di configurazione del dispositivo personalizzato basato su URI OMA e specificare false per RequireNetworkInOOBE, come illustrato di seguito.
Il valore URI OMA deve essere ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot dell'impostazione di RequireNetworkInOOBE su false tramite URI OMA in Intune.](images/hololens-tenant-lockdown-false.png)

1. Creare un gruppo e assegnare il profilo di configurazione del dispositivo a tale gruppo di dispositivi.

1. Impostare il HoloLens 2 del dispositivo del gruppo creato nel passaggio precedente e attivare la sincronizzazione.

Verificare nel portale di Intune che la configurazione del dispositivo sia stata applicata correttamente. Dopo che la configurazione del dispositivo è stata applicata HoloLens 2 dispositivo, gli effetti di TenantLockdown saranno inattivi.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Che cosa accade durante la Configurazione automatica, se il profilo di Autopilot non è assegnato in un HoloLens dopo che TenantLockdown è stato impostato su true?

La Configurazione remota attenderà per un periodo illimitato il download del profilo autopilot e verrà visualizzata la finestra di dialogo seguente. Per rimuovere gli effetti di TenantLockdown, il dispositivo deve essere prima registrato con il tenant originale usando solo Autopilot e RequireNetworkInOOBE deve essere rimosso come descritto nel passaggio precedente prima di rimuovere le restrizioni introdotte dal provider di servizi di configurazione TenantLockdown.

![Visualizzazione nel dispositivo per l'applicazione dei criteri nel dispositivo.](images/hololens-autopilot-lockdown.png)

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>Perché non è stata visualizzata l'esperienza di Autopilot anche se il profilo di Autopilot è stato assegnato in Intune?

Per impostazione predefinita, HoloLens 2 attende 15 secondi per rilevare Autopilot dopo aver rilevato Internet. Se entro 15 secondi non viene rilevato alcun profilo di Autopilot, significa che Autopilot non è stato individuato correttamente e verrà visualizzata la pagina EULA.

Riavviare il dispositivo e riprovare. Per altre informazioni, vedere [Problemi noti e limitazioni o](hololens2-autopilot.md#known-issues-and-limitations) Risoluzione dei [problemi.](hololens2-autopilot.md#troubleshooting)

## <a name="known-issues-and-limitations"></a>Limitazioni e problemi noti

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>Perché vengono visualizzati 0x80180014 durante Autopilot?

Si tratta di un errore visualizzato durante il processo Autopilot nel dispositivo. Questo problema illustrato si applica solo quando un HoloLens dispositivo ha eseguito le operazioni seguenti:

1. È già stato fatto almeno una volta con Autopilot.
1. È ora in corso la reimpostazione e il nuovo utilizzo per Autopilot.

L'esperienza di Autopilot avrà esito negativo con un errore specifico.

![HoloLens Codice di errore di Autopilot](images/autopilot-0x80180014-failure.jpg)

Quali passaggi è necessario eseguire per risolvere l'errore?

1. Seguire la procedura descritta in Risolvere i problemi di importazione e registrazione dei dispositivi [Autopilot](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) per rimuovere il dispositivo da Intune. L'amministratore di Intune dovrà eseguire questa attività.
1. Al termine del passaggio 1, riavviare il dispositivo e accedere.
1. Passare a **Impostazioni**  ->  **Ripristino & sicurezza**&  ->  **ripristino** e selezionare **Inizia.**
    1. Se si verificano problemi con i passaggi 2 & 3, vedere alternative alla reimpostazione del dispositivo in [Reset/Reflash HoloLens](hololens-recovery.md).

AutoPilot dovrebbe quindi essere registrato correttamente.

### <a name="troubleshooting"></a>Risoluzione dei problemi

Gli articoli seguenti possono essere una risorsa utile per ottenere altre informazioni e risolvere i problemi di Autopilot, tuttavia questi articoli si basano su Windows 10 Desktop e non tutte le informazioni possono essere applicabili a HoloLens:

- [Windows Autopilot - Problemi noti](/mem/autopilot/known-issues)
- [Risolvere i problemi di registrazione dei dispositivi Windows in Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Conflitti di criteri](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Commenti e supporto per Autopilot

Per inviare commenti e suggerimenti o segnalare problemi, usare uno dei metodi seguenti:

- Per supporto sulla registrazione del dispositivo, contattare il rivenditore o il distributore.
- Per richieste di supporto generali su Windows Autopilot o per problemi come le assegnazioni di profilo, la creazione di gruppi o i controlli del portale MEM, contattare Microsoft Endpoint Manager [supporto](/mem/get-support)  
- Se il dispositivo è registrato nel servizio Autopilot e il profilo è assegnato nel portale MEM, contattare il supporto HoloLens [(vedere](/hololens/) la scheda "Supporto"). Aprire un ticket di supporto e, se applicabile, includere screenshot e log acquisendo i log di [diagnostica offline](hololens-diagnostic-logs.md#offline-diagnostics) durante la configurazione predefinita.
- Per segnalare un problema dal dispositivo, usare l'app Hub di Feedback nel HoloLens. Nella Hub di Feedback selezionare la categoria **Enterprise**  >  **Gestione** dispositivi.
- Per fornire commenti e suggerimenti generali su Autopilot HoloLens, è possibile inviare questo [sondaggio](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Eliminare dispositivi di AutoPilot

Potrebbe essere necessario non usare più un dispositivo per Autopilot o registrare i dispositivi in un tenant diverso. Se si vuole eseguire questa operazione, leggere come [eliminare i dispositivi Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)
