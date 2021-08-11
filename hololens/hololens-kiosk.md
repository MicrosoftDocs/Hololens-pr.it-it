---
title: Configurare l'HoloLens come chiosco multimediale
description: Informazioni su come configurare e usare una configurazione in modalità tutto schermo per bloccare le app HoloLens dispositivi.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e7f1efa99cc16b1003bd7063817451013ed2ec2661dbdf02edcd89c7984d0980
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663976"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurare l'HoloLens come chiosco multimediale

È possibile configurare un HoloLens in modo che funzioni come dispositivo per utilizzo fisso, detto anche chiosco multimediale, configurando il dispositivo per l'esecuzione in modalità tutto schermo. La modalità tutto schermo limita le applicazioni (o gli utenti) disponibili nel dispositivo. La modalità tutto schermo è una funzionalità pratica che è possibile usare per dedicare un dispositivo HoloLens alle app aziendali o per usare il dispositivo HoloLens in una demo di app.

Questo articolo fornisce informazioni sugli aspetti della configurazione della modalità tutto schermo specifici per HoloLens dispositivi. Per informazioni generali sui diversi tipi di chioschi in modalità tutto schermo basati su Windows e su come configurarli, vedere Configurare chioschi in modalità tutto schermo e segnali digitali Windows [desktop.](/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> La modalità tutto schermo determina quali app sono disponibili quando un utente accede al dispositivo. Tuttavia, la modalità tutto schermo non è un metodo di sicurezza. Non arresta l'apertura di un'altra app non consentita da un'app "consentita". Per bloccare l'apertura di app o processi, usare Windows Defender CSP di Controllo di applicazioni [(WDAC)](/windows/client-management/mdm/applicationcontrol-csp) per creare i criteri appropriati.
>
> Altre informazioni sull'servizi Microsoft per offrire agli utenti un livello di sicurezza avanzato che HoloLens 2 usa, altre informazioni sulla separazione e l'isolamento dello stato [- Protezioni di Defender.](security-state-separation-isolation.md#defender-protections) In altre informazioni su [come usare WDAC Windows PowerShell per consentire](/mem/intune/configuration/custom-profile-hololens)o bloccare le app HoloLens 2 dispositivi con Microsoft Intune .

È possibile usare la modalità tutto schermo in una configurazione con app singola o multi-app ed è possibile usare uno dei tre processi per configurare e distribuire la configurazione della modalità tutto schermo.

> [!IMPORTANT]  
> L'eliminazione della configurazione per più app rimuove i profili di blocco utente creati dalla funzionalità di accesso assegnata. Tuttavia, non vengono annullate tutte le modifiche dei criteri. Per ripristinare questi criteri, è necessario ripristinare le impostazioni predefinite del dispositivo.

## <a name="plan-the-kiosk-deployment"></a>Pianificare la distribuzione in modalità tutto schermo

Quando si pianifica il chiosco multimediale, è necessario essere in grado di rispondere alle domande seguenti. Ecco alcune decisioni da prendere in considerazione durante la lettura di questa pagina e alcune considerazioni per queste domande.
1. **Who verrà utilizzato il chiosco multimediale e quale tipo di [account](hololens-identity.md) verrà utilizzato?** Si tratta di una decisione che probabilmente è già stata presa e non deve essere modificata ai fini del chiosco multimediale, ma influirà sul modo in cui il chiosco multimediale verrà assegnato in un secondo momento.
1. **È necessario avere chioschi in modalità tutto schermo diversi per utente/gruppo o un chiosco multimediale non abilitato per alcuni?** In tal caso, è necessario creare il chiosco multimediale tramite XML. 
1. **Quante app saranno in modalità tutto schermo?** Se si hanno più app, è necessario un chiosco multimediale con più app. 
1. **Quali app saranno in modalità tutto schermo?** Usare l'elenco di AUMID riportato di seguito per aggiungere In-Box app personalizzate.
1. **Come si prevede di distribuire il chiosco multimediale?** Se si registra il dispositivo in MDM, è consigliabile usare MDM per distribuire il chiosco multimediale. Se non si usa MDM, la distribuzione con il pacchetto di provisioning è disponibile.  

### <a name="kiosk-mode-requirements"></a>Requisiti della modalità tutto schermo

È possibile configurare qualsiasi dispositivo HoloLens 2 per l'uso della modalità tutto schermo.

> [!IMPORTANT]
> La modalità tutto schermo è disponibile solo se il dispositivo ha Windows Holographic for Business. Tutti HoloLens 2 vengono forniti con Windows Holographic for Business e non sono presenti altre edizioni. Ogni HoloLens 2 dispositivi è in grado di eseguire la modalità tutto schermo predefinita.
>
> HoloLens dispositivi di prima generazione devono essere aggiornati sia in termini di build del sistema operativo che di edizione del sistema operativo. Di seguito sono riportate altre informazioni sull'aggiornamento di un HoloLens (prima generazione) [alla Windows Holographic for Business](hololens1-upgrade-enterprise.md) edizione. Per aggiornare un dispositivo HoloLens (prima generazione) per l'uso della modalità tutto schermo, è innanzitutto necessario assicurarsi che il dispositivo venga eseguito Windows 10 versione 1803 o successiva. Se è stato usato lo strumento di ripristino dei dispositivi di Windows per ripristinare la build predefinita del dispositivo HoloLens (prima generazione) o se sono stati installati gli aggiornamenti più recenti, il dispositivo è pronto per la configurazione.

> [!IMPORTANT]  
> Per proteggere i dispositivi eseguiti in modalità tutto schermo, è consigliabile aggiungere criteri di gestione dei dispositivi che disattivano funzionalità come la connettività USB. Controllare anche le impostazioni dell'anello di aggiornamento per assicurarsi che gli aggiornamenti automatici non si verifichino durante l'orario lavorativo.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Scegliere tra un chiosco multimediale con una singola app o più app in modalità tutto schermo

Un chiosco multimediale con una singola app avvia l'app specificata quando l'utente accede al dispositivo. La menu Start è disabilitata, così come Cortana. Un HoloLens 2 dispositivo non risponde al [movimento Avvia.](hololens2-basic-usage.md#start-gesture) Un HoloLens (prima generazione) non risponde al movimento [del fiore.](hololens1-basic-usage.md) Poiché è possibile eseguire una sola app, l'utente non può inserire altre app.

Un chiosco multimediale con più app visualizza menu Start quando l'utente accede al dispositivo. La configurazione della modalità tutto schermo determina quali app sono disponibili nel menu Start. È possibile usare un chiosco multimediale con più app per offrire agli utenti un'esperienza di facile comprensione presentando loro solo gli elementi che devono usare e rimuovendo gli elementi che non devono usare.

La tabella seguente elenca le funzionalità nelle diverse modalità tutto schermo.

| &nbsp; |Menu Start |Menu Azioni rapide |Fotocamera e video |Miracast |Cortana |Comandi vocali predefiniti |
| --- | --- | --- | --- | --- | --- | --- | 
|App singola in modalità tutto schermo |Disabled |Disabled |Disabled |Disabled   |Disabled |Abilitato<sup>1</sup> |
|Più app in modalità tutto schermo |Attivato |Abilitato<sup>2</sup> |Disponibile<sup>2</sup> |Disponibile<sup>2</sup> |Disponibile<sup>2, 3</sup>  |Abilitato<sup>1</sup> |

> <sup>1</sup> I comandi vocali correlati alle funzionalità disabilitate non funzionano.  
> <sup>2</sup> Per altre informazioni su come configurare queste funzionalità, vedere Selezionare le app in [modalità tutto schermo.](#plan-kiosk-apps)  
> <sup>3</sup> Anche se Cortana è disabilitato, i comandi vocali predefiniti sono abilitati.

La tabella seguente elenca le funzionalità di supporto per gli utenti delle diverse modalità tutto schermo.

| &nbsp; |Tipi di utente supportati | Accesso automatico | Più livelli di accesso |
| --- | --- | --- | --- |
|App singola in modalità tutto schermo | Account Microsoft (MSA) in Azure Active Directory (Azure AD) o account locale |Sì |No |
|Più app in modalità tutto schermo |Account Azure AD |No |Sì |

Per esempi su come usare queste funzionalità, vedere la tabella seguente.

|Usare un'app singola in modalità tutto schermo per: |Usare un chiosco multimediale con più app per: |
| --- | --- |
|Un dispositivo che esegue solo una Guida di Dynamics 365 per i nuovi dipendenti. |Un dispositivo che esegue guide e assistenza remota per una gamma di dipendenti. |
|Un dispositivo che esegue solo un'app personalizzata. |Un dispositivo che funziona come un chiosco multimediale per la maggior parte degli utenti (che esegue solo un'app personalizzata), ma funziona come un dispositivo standard per un gruppo specifico di utenti. |

### <a name="plan-kiosk-apps"></a>Pianificare app in modalità tutto schermo

Per informazioni generali su come scegliere le app in modalità tutto schermo, vedere Linee guida per la scelta di [un'app per l'accesso assegnato (modalità tutto schermo).](/windows/configuration/guidelines-for-assigned-access-app)

Se si usa l'Windows Portale di dispositivi per configurare un'app singola in modalità tutto schermo, selezionare l'app durante il processo di configurazione.  

Se si usa un sistema di gestione di dispositivi mobili (MDM) o un pacchetto di provisioning per configurare la modalità tutto schermo, si usa il provider di servizi di configurazione [AssignedAccess (CSP)](/windows/client-management/mdm/assignedaccess-csp) per specificare le applicazioni. Il provider di servizi di configurazione usa gli ID modello utente [applicazione (AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) per identificare le applicazioni. La tabella seguente elenca gli AUMID di alcune applicazioni in-box che è possibile usare in un chiosco multimediale con più app.

> [!IMPORTANT]
> La modalità tutto schermo determina quali app sono disponibili quando un utente accede al dispositivo. Tuttavia, la modalità tutto schermo non è un metodo di sicurezza. Non arresta l'apertura di un'altra app non consentita da un'app "consentita". Poiché questo comportamento non è limitato, le app possono comunque essere avviate da Microsoft Edge, Esplora file e Microsoft Store app. Se sono presenti app specifiche che non si vuole avviare da un chiosco multimediale, usare il provider di servizi di configurazione Windows Defender [Application Control (WDAC)](/windows/client-management/mdm/applicationcontrol-csp) per creare i criteri appropriati. 
> 
> Inoltre, la home page di realtà mista non può essere impostata come app in modalità tutto schermo.

<a id="aumids"></a>

|Nome dell'app |AUMID |
| --- | --- |
|Visualizzatore 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendario |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Fotocamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Selezione dispositivo in HoloLens (prima generazione) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Selezione dispositivo in HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Guide di Dynamics 365 |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Hub di &nbsp; Feedback |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Esplora file |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Posta |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Versione precedente Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|Nuovo Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> |&nbsp; |
|Film e TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |Microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Foto |Microsoft. Windows. \_Foto App 8wekyb3d8bbwe \! |
|Versione precedente Impostazioni |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nuovo Impostazioni |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Suggerimenti |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Per abilitare l'acquisizione di foto o video, è necessario abilitare l'app Fotocamera come app in modalità tutto schermo.  
> <sup>2</sup> Quando si abilita l'app Fotocamera, tenere presenti le condizioni seguenti:
> - Il menu Azioni rapide include i pulsanti Foto e Video.  
> - È anche consigliabile abilitare un'app (ad esempio Foto, Mail o OneDrive) in grado di interagire con o recuperare immagini.  
>  
> <sup>3</sup> Anche se non si abilita l'Cortana come app in modalità tutto schermo, vengono abilitati i comandi vocali predefiniti. Tuttavia, i comandi correlati alle funzionalità disabilitate non hanno alcun effetto.  
> <sup>4</sup> Non è possibile abilitare Miracast direttamente. Per abilitare la Miracast come app in modalità tutto schermo, abilitare l'app Fotocamera e l'app Selezione dispositivo.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Pianificare profili in modalità tutto schermo per utenti o gruppi

Quando si crea il file XML o si usa l'interfaccia utente di Intune per configurare un chiosco multimediale, è necessario considerare chi sarà l'utente della modalità tutto schermo. Una configurazione della modalità tutto schermo può essere limitata a un singolo account o a Azure AD gruppi. 

In genere i chioschi sono abilitati per un utente o un gruppo di utenti. Tuttavia, se si prevede di scrivere codice XML in modalità tutto schermo, è consigliabile prendere in considerazione l'accesso assegnato globale, in cui il chiosco multimediale viene applicato a livello di dispositivo indipendentemente dall'identità. Se questo è interessante, leggere [altre informazioni sui chioschi di accesso assegnati a livello globale.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Se si sta creando un file XML:
-   Molti utenti creano più profili in modalità tutto schermo e assegnano ognuno a utenti/gruppi diversi. Ad esempio, un chiosco multimediale per il gruppo di Azure AD con molte app e un visitatore con più app in modalità tutto schermo con un'app singola.
-   La configurazione della modalità tutto schermo sarà denominata **ID profilo** e avrà un GUID.
-   Il profilo verrà assegnato nella sezione configs specificando il tipo di utente e usando lo stesso GUID per **DefaultProfile Id**.
- Un file XML può essere creato ma comunque applicato a un dispositivo tramite MDM creando un profilo di configurazione del dispositivo URI OMA personalizzato e applicandolo HoloLens un gruppo di dispositivi usando il valore URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Se si crea un chiosco multimediale in Intune.
-   Ogni dispositivo può ricevere un solo profilo in modalità tutto schermo, in caso contrario creerà un conflitto e non riceverà alcuna configurazione della modalità tutto schermo. 
    -   Altri tipi di profili e criteri, ad esempio le restrizioni dei dispositivi non correlate al profilo di configurazione della modalità tutto schermo, non sono in conflitto con il profilo di configurazione della modalità tutto schermo.
-   La modalità tutto schermo verrà abilitata per tutti gli utenti che fanno parte del tipo Accesso utente, che verrà impostata con un utente o un Azure AD utenti. 
-   Dopo aver impostato la configurazione della modalità tutto schermo e aver selezionato Il tipo di accesso utente **(utenti** che possono accedere alla modalità tutto schermo) e le app, è necessario assegnare la configurazione del dispositivo a un gruppo. I gruppi assegnati determinano i dispositivi che ricevono la configurazione del dispositivo In modalità tutto schermo, ma non interagisce con se la modalità tutto schermo è abilitata o meno. 
    - Per una descrizione completa degli effetti dell'assegnazione dei profili di configurazione in Intune, vedere [Assegnare profili](/intune/configuration/device-profile-assign)utente e dispositivo in Microsoft Intune .

### <a name="select-a-deployment-method"></a>Selezionare un metodo di distribuzione

È possibile selezionare uno dei metodi seguenti per distribuire le configurazioni della modalità tutto schermo:

- [Microsoft Intune o un altro servizio di gestione di dispositivi mobili (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pacchetto di provisioning](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Portale di dispositivi di Windows](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Poiché questo metodo richiede che nel dispositivo sia abilitata la modalità sviluppatore, è consigliabile usarla solo a scopo dimostrativo.

La tabella seguente elenca le funzionalità e i vantaggi di ognuno dei metodi di distribuzione.

| &nbsp; |Eseguire la distribuzione usando Windows Portale di dispositivi |Eseguire la distribuzione usando un pacchetto di provisioning |Eseguire la distribuzione tramite MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Distribuire chioschi multimediale per app singole   | Sì           | Sì                  | Sì  |
|Distribuire più app in modalità tutto schermo    | No            | Sì                  | Sì  |
|Eseguire la distribuzione solo nei dispositivi locali | Sì           | Sì                  | No   |
|Eseguire la distribuzione usando la modalità sviluppatore |Necessario       | Facoltativo            | Facoltativo   |
|Eseguire la distribuzione usando Azure Active Directory (Azure AD)  | Facoltativo            | Facoltativo                   | Necessario  |
|Distribuire automaticamente      | No            | No                   | Sì  |
|Velocità di distribuzione            | Veloce       | Veloci                 | Lente |
|Distribuire su larga scala | Non consigliata    | Consigliato        | Consigliato |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Usare Microsoft Intune o un'altra soluzione MDM per configurare un'app singola o multiapp in modalità tutto schermo

Per configurare la modalità tutto schermo usando Microsoft Intune o un altro sistema MDM, seguire questa procedura.

1. [Preparare la registrazione dei dispositivi](#mdmenroll).
1. [Creare un profilo di configurazione tutto schermo](#mdmprofile).
1. Configurare il chiosco multimediale.
   - [Configurare le impostazioni per un chiosco multimediale a app singola.](#mdmconfigsingle)
   - [Configurare le impostazioni per un chiosco multimediale multi-app.](#mdmconfigmulti)
1. [Assegnare il profilo di configurazione della modalità tutto schermo a un gruppo](#mdmassign).
1. Distribuire i dispositivi.
   - [Distribuire un'app singola in modalità tutto schermo.](#mdmsingledeploy)
   - [Distribuire un chiosco multimediale multi-app.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, passaggio 1 &ndash; Preparare la registrazione dei dispositivi

È possibile configurare il sistema MDM per registrare automaticamente HoloLens dispositivi quando l'utente accede per la prima volta oppure fare in modo che gli utenti i dispositivi possano essere registrati manualmente. I dispositivi devono anche essere aggiunti al dominio Azure AD e assegnati ai gruppi appropriati.

Per altre informazioni su come registrare i dispositivi, vedere [Registrare](hololens-enroll-mdm.md) HoloLens nei metodi di registrazione MDM e [Intune per](/mem/intune/enrollment/windows-enrollment-methods)Windows dispositivi .

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, passaggio 2 &ndash; Creare un profilo di configurazione tutto schermo

1. Aprire il [portale di Azure](https://portal.azure.com/) e accedere all'account amministratore di Intune locale.
1. Selezionare **Microsoft Intune**  >  **configurazione del dispositivo - Profili**  >  **Crea profilo**.
1. Immettere un nome di profilo.
1. Selezionare **Platform**  >  **Windows 10 e versioni successive** e quindi selezionare Profile **type**  > **Device restrictions (Restrizioni del dispositivo).**
1. Selezionare **Configura**  >  **chiosco** multimediale e quindi selezionare una delle opzioni seguenti:
   - Per creare un chiosco multimediale a app singola, selezionare **Modalità tutto** schermo per  >  **app singola.**
   - Per creare un chiosco multimediale multi-app, selezionare **Modalità** tutto schermo modalità tutto schermo  >  **multi-app.**
1. Per avviare la configurazione della modalità tutto schermo, selezionare **Aggiungi**.

I passaggi successivi variano a seconda del tipo di chiosco multimediale desiderato. Per altre informazioni, selezionare una delle opzioni seguenti:  

- [Modalità tutto schermo con app singola](#mdmconfigsingle)
- [Più app in modalità tutto schermo](#mdmconfigmulti)

Per altre informazioni su come creare un profilo di configurazione della modalità tutto schermo, vedere Configurare Windows 10 e Windows Holographic for Business dispositivo per l'esecuzione come chiosco multimediale dedicato [con Intune.](/intune/configuration/kiosk-settings)

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, passaggio 3 (app singola) Configurare le impostazioni per &ndash;  un chiosco multimediale a app singola

Questa sezione riepiloga le impostazioni necessarie per un chiosco multimediale a app singola. Per altre informazioni, vedere gli articoli seguenti:

- Per informazioni su come configurare un profilo di configurazione della modalità tutto schermo in Intune, vedere [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Per altre informazioni sulle impostazioni disponibili per i chioschi in modalità tutto schermo per app singole in Intune, vedere Chioschi in modalità tutto [schermo per app singole](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Per altri servizi MDM, consultare la documentazione del provider per istruzioni. Se è necessario usare una configurazione XML personalizzata per configurare un chiosco multimediale nel servizio MDM, creare un file XML che definisce [la configurazione della modalità tutto schermo.](#ppkioskconfig)

1. Selezionare **Accesso utente digitare** Account utente locale e quindi immettere il nome utente dell'account locale (dispositivo) o dell'account Microsoft (MSA) che può accedere al  >  chiosco multimediale.
   > [!NOTE]  
   > I tipi di account utente con **accesso automatico** non sono supportati in Windows Holographic for Business.
1. Selezionare **Tipo di applicazione** App  >  **store** e quindi selezionare un'app dall'elenco.

Il passaggio successivo consiste [nell'assegnare](#mdmassign) il profilo a un gruppo.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, passaggio 3 (multi-app) &ndash; Configurare le impostazioni per una modalità tutto schermo multi-app

Questa sezione riepiloga le impostazioni necessarie per un chiosco multimediale multi-app. Per altre informazioni dettagliate, vedere gli articoli seguenti:

- Per informazioni su come configurare un profilo di configurazione della modalità tutto schermo in Intune, vedere [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Per altre informazioni sulle impostazioni disponibili per i chioschi in modalità tutto schermo multi-app in Intune, vedere [Chioschi in](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks) modalità tutto schermo per più app
- Per altri servizi MDM, consultare la documentazione del provider per istruzioni. Se è necessario usare una configurazione XML personalizzata per configurare un chiosco multimediale nel servizio MDM, creare un file XML che definisce [la configurazione della modalità tutto schermo.](#ppkioskconfig) Se si usa un file XML, assicurarsi di includere il [layout Start](#start-layout-for-hololens).  
- Facoltativamente, è possibile usare un layout Start personalizzato con Intune o altri servizi MDM. Per altre informazioni, vedere [Avviare il file di layout per MDM (Intune e altri).](#start-layout-file-for-mdm-intune-and-others)

1. Selezionare **Target Windows 10 nei dispositivi in modalità S**  >  **No**.  
>[!NOTE]  
> La modalità S non è supportata in Windows Holographic for Business.

1. Selezionare **Tipo di accesso utente** Azure AD utente o gruppo o Tipo di accesso utente HoloLens visitor e quindi aggiungere uno o più gruppi di utenti o  >     >  account.  

   Solo gli utenti che appartengono ai gruppi o agli account specificati in **Tipo di accesso utente** possono usare l'esperienza tutto schermo.

1. Selezionare una o più app usando le opzioni seguenti:
   - Per aggiungere un'app line-of-business caricata, selezionare **Aggiungi app dello Store** e quindi selezionare l'app desiderata.
   - Per aggiungere un'app specificando il relativo AUMID, selezionare **Aggiungi da AUMID** e quindi immettere il valore AUMID dell'app. [Vedere l'elenco degli AUMID disponibili](#aumids)

Il passaggio successivo consiste [nell'assegnare](#mdmassign) il profilo a un gruppo.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, passaggio 4 &ndash; Assegnare il profilo di configurazione tutto schermo a un gruppo

Usare la **pagina Assegnazioni** del profilo di configurazione tutto schermo per impostare la posizione in cui si vuole distribuire la configurazione della modalità tutto schermo. Nel caso più semplice, si assegna il profilo di configurazione tutto schermo a un gruppo che conterrà HoloLens dispositivo quando il dispositivo si registra in MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, passaggio 5 (app singola) &ndash; Distribuire un'app singola in modalità tutto schermo

Quando si usa un sistema MDM, è possibile registrare il dispositivo in MDM durante la configurazione del sistema operativo. Al termine della configurazione del sistema operativo, l'accesso al dispositivo è semplice.

Durante la configurazione del sistema operativo, seguire questa procedura:

1. Accedere usando l'account specificato nel profilo di configurazione della modalità tutto schermo.
1. Registrare il dispositivo. Assicurarsi che il dispositivo sia aggiunto al gruppo a cui è assegnato il profilo di configurazione tutto schermo.
1. Attendere il completamento della procedura guidata, il download e l'installazione dell'app dello Store e l'applicazione dei criteri. Riavviare quindi il dispositivo.

Al successivo accesso al dispositivo, l'app in modalità tutto schermo verrà avviata automaticamente.

Se la configurazione della modalità tutto schermo non è visualizzata a questo punto, [controllare lo stato dell'assegnazione](/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, passaggio 5 (multi-app) Distribuire una modalità tutto schermo &ndash; multi-app

Quando si usa un sistema MDM, è possibile aggiungere il dispositivo al tenant Azure AD e registrare il dispositivo in MDM durante la configurazione del sistema operativo. Se appropriato, fornire le informazioni di registrazione agli utenti in modo che siano disponibili durante il processo di Configurazione guidata.

> [!NOTE]  
> Se il profilo di configurazione della modalità tutto schermo è stato assegnato a un gruppo che contiene utenti, assicurarsi che uno di questi account utente sia il primo account ad accedere al dispositivo.

Durante la configurazione del sistema operativo, seguire questa procedura:

1. Accedere usando l'account appartenente al gruppo **Tipo di accesso** utente.
1. Registrare il dispositivo.
1. Attendere il download e l'installazione di tutte le app che fanno parte del profilo di configurazione tutto schermo. Attendere anche l'applicazione dei criteri.  
1. Al termine della configurazione guidata, è possibile installare altre app da Microsoft Store o tramite sideload. [App necessarie](/mem/intune/apps/apps-deploy#assign-an-app) per il gruppo a cui appartiene il dispositivo per l'installazione automatica.
1. Al termine dell'installazione, riavviare il dispositivo.

Al successivo accesso al dispositivo usando un account appartenente al tipo Di accesso **utente,** l'app in modalità tutto schermo dovrebbe essere avviata automaticamente.

Se la configurazione della modalità tutto schermo non è visualizzata a questo punto, [controllare lo stato dell'assegnazione](/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Usare un pacchetto di provisioning per configurare un'app singola o multi-app in modalità tutto schermo

Per configurare la modalità tutto schermo usando un pacchetto di provisioning, seguire questa procedura.

1. [Creare un file XML che definisce la configurazione della modalità tutto schermo.](#ppkioskconfig), incluso un [layout Start.](#start-layout-for-hololens)
2. [Aggiungere il file XML a un pacchetto di provisioning.](#ppconfigadd)
3. [Applicare il pacchetto di provisioning HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Pacchetto di provisioning, passaggio 1 &ndash; Creare un file XML di configurazione tutto schermo

Seguire le istruzioni generali per creare un file XML di configurazione tutto schermo [per Windows desktop, ad](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)eccezione dei seguenti:

- Non includere applicazioni Windows classiche (Win32). HoloLens non supporta queste applicazioni.
- Usare il [segnaposto Start layout XML](#start-layout-for-hololens) per HoloLens.
- Facoltativo: Aggiungere l'accesso guest alla configurazione della modalità tutto schermo

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Facoltativo: Aggiungere l'accesso guest alla configurazione della modalità tutto schermo

Nella sezione [ **Configs** del file XML](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)è possibile configurare un gruppo speciale denominato **Visitor** per consentire ai guest di usare il chiosco multimediale. Quando il chiosco multimediale è configurato per supportare il gruppo speciale **Visitor,** viene aggiunta un'opzione "**Guest**" alla pagina di accesso. **L'account** Guest non richiede una password e tutti i dati associati all'account vengono eliminati quando l'account si esce.

Per abilitare l'account **Guest,** aggiungere il frammento di codice seguente al codice XML di configurazione della modalità tutto schermo:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Abilitare l'accesso automatico dei visitatori

Nelle build Windows [Holographic, versione 21H1 e](hololens-release-notes.md#windows-holographic-version-21h1) versioni successiva:
- Le configurazioni AAD e Non ADD supportano entrambi gli account visitatore abilitati per l'accesso automatico per le modalità tutto schermo.

##### <a name="non-aad-configuration"></a>Configurazione non AAD

1. Creare un pacchetto di provisioning che:
    1. Configura le impostazioni di runtime/AssignedAccess per consentire gli account Visitor.
    1. Facoltativamente, registra il dispositivo in MDM (Impostazioni di runtime/Area di lavoro/Registrazioni) in modo che possa essere gestito in un secondo momento.
    1. Non creare un account locale
2. [Applicare il pacchetto di provisioning](hololens-provisioning.md).

##### <a name="aad-configuration"></a>Configurazione di AAD

I dispositivi aggiunti ad AAD configurati per la modalità tutto schermo possono accedere a un account Visitatore con un solo tocco pulsante dalla schermata di accesso. Dopo aver eseguito l'accesso all'account visitatore, il dispositivo non richiederà di nuovo l'accesso fino a quando il visitatore non viene disconnesso in modo esplicito dal menu Start o non viene riavviato il dispositivo.

L'accesso automatico del visitatore può essere gestito tramite [criteri URI OMA personalizzati:](/mem/intune/configuration/custom-settings-windows-10)

- Valore URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Criteri |Descrizione |Configurazioni 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Consente a un visitatore di accedere automaticamente a un chiosco multimediale. | 1 (Sì), 0 (No, impostazione predefinita). |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Layout di inizio segnaposto per HoloLens

Se si usa un [pacchetto di provisioning per](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) configurare un chiosco multimediale multi-app, la procedura richiede un layout Start. La personalizzazione del layout di avvio non è supportata in Windows Holographic for Business. Sarà quindi necessario usare un layout Start segnaposto.

> [!NOTE]  
> Poiché una modalità tutto schermo a app singola avvia l'app in modalità tutto schermo quando un utente esegue l'accesso, non usa un menu Start e non deve avere un layout Start.

> [!NOTE]  
> Se si usa [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) per configurare un chiosco multimediale multi-app, è possibile usare facoltativamente un layout Start. Per altre informazioni, vedere [File di layout Di avvio segnaposto per MDM (Intune e altri).](#start-layout-file-for-mdm-intune-and-others)

Per il layout Start, aggiungere la sezione **StartLayout** seguente al file XML di provisioning in modalità tutto schermo:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>File di layout Di avvio segnaposto per MDM (Intune e altri)

Salvare l'esempio seguente come file XML. È possibile usare questo file quando si configura la modalità tutto schermo multi-app in Microsoft Intune (o in un altro servizio MDM che fornisce un profilo tutto schermo).

> [!NOTE]
> Se è necessario usare un'impostazione personalizzata e una configurazione XML completa per configurare un chiosco multimediale nel servizio MDM, usare le istruzioni [di layout Start per un pacchetto di provisioning.](#start-layout-for-hololens)

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. pacchetto, passaggio 2 Aggiungere il file XML di &ndash; configurazione tutto schermo a un pacchetto di provisioning

1. Aprire [Windows Progettazione configurazione](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Selezionare **Provisioning avanzato,** immettere un nome per il progetto e quindi selezionare **Avanti.**
1. Selezionare **Windows 10 Holographic** e quindi selezionare **Avanti.**
1. Selezionare **Fine**. Si aprirà l'area di lavoro per il pacchetto.
1. Selezionare **Impostazioni di runtime**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. Nel riquadro centrale selezionare **Sfoglia** per individuare e selezionare il file XML di configurazione tutto schermo creato.

   ![Screenshot del campo MultiAppAssignedAccessSettings in Progettazione Windows configurazione](./images/multiappassignedaccesssettings.png)

1. **Facoltativo**. Se si vuole applicare il pacchetto di provisioning dopo la configurazione iniziale del dispositivo ed è già disponibile un utente amministratore nel dispositivo tutto schermo, ignorare questo passaggio. Selezionare **Impostazioni di runtime** &gt; **Account** &gt; **Utenti** e quindi creare un account utente. Specificare un nome utente e una password e quindi selezionare **UserGroup**  >  **Administrators**.  
  
     Usando questo account, è possibile visualizzare lo stato del provisioning e i log.  
1. **Facoltativo**. Se nel dispositivo in modalità tutto schermo è già presente un account non amministratore, ignorare questo passaggio. Selezionare **Impostazioni di runtime** &gt; **Account** &gt; **Utenti** e quindi creare un account utente locale. Assicurarsi che il nome utente sia lo stesso dell'account specificato nel codice XML di configurazione. Selezionare **UserGroup**  >  **Standard Users**.
1. Selezionare **Salva**  >  **file**.
1. Selezionare **Export**  >  Provisioning package (Esporta pacchetto di **provisioning)** e quindi Owner IT Admin   >  **(Amministratore IT proprietario).** In questo modo la precedenza di questo pacchetto di provisioning viene impostata su un livello superiore rispetto ai pacchetti di provisioning applicati a questo dispositivo da altre origini.
1. Selezionare **Avanti**.
1. Nella pagina **Sicurezza pacchetto di provisioning** selezionare un'opzione di sicurezza.
   > [!IMPORTANT]  
   > Se si seleziona **Abilita firma pacchetto,** è anche necessario selezionare un certificato valido da usare per la firma del pacchetto. A tale scopo, selezionare **Sfoglia** e selezionare il certificato che si vuole usare per firmare il pacchetto.
   
   > [!CAUTION]  
   > Non selezionare Abilita **crittografia pacchetti**. Nei HoloLens, questa impostazione causa l'esito negativo del provisioning.
1. Selezionare **Avanti**.
1. Specificare il percorso di output in cui si vuole inserire il pacchetto di provisioning quando viene compilato. Per impostazione predefinita, Windows Progettazione configurazione usa la cartella del progetto come percorso di output. Per modificare il percorso di output, selezionare **Sfoglia**. Al termine dell'operazione, scegliere **Avanti**.
1. Selezionare **Compila** per iniziare a compilare il pacchetto. La compilazione del pacchetto di provisioning non richiede molto tempo. Nella pagina di compilazione vengono visualizzate le informazioni sul progetto e l'indicatore di stato indica lo stato della compilazione.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Pacchetto di provisioning, passaggio 3 &ndash; Applicare il pacchetto di provisioning HoloLens

L'articolo "Configurare HoloLens usando un pacchetto di provisioning" fornisce istruzioni dettagliate per applicare il pacchetto di provisioning nelle circostanze seguenti:

- È possibile applicare inizialmente [un pacchetto di provisioning a HoloLens durante l'installazione di](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- È anche possibile [applicare un pacchetto di provisioning a HoloLens dopo l'installazione di](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Usare il Windows Portale di dispositivi per configurare un chiosco multimediale a app singola

Per configurare la modalità tutto schermo usando il Windows Portale di dispositivi, seguire questa procedura.

1. [Configurare il dispositivo HoloLens usare il](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)Windows Portale di dispositivi . Device Portal è un server Web in HoloLens a cui è possibile connettersi da un browser Web nel PC.

    > [!CAUTION]
    > Quando si configura HoloLens usare il Portale di dispositivi, è necessario abilitare la modalità sviluppatore nel dispositivo. La modalità sviluppatore in un dispositivo con Windows Holographic for Business consente di eseguire il side-load delle app. Tuttavia, questa impostazione crea un rischio che un utente possa installare app che non sono state certificate dal Microsoft Store. Gli amministratori possono bloccare la possibilità di abilitare la modalità sviluppatore usando l'impostazione **ApplicationManagement/AllowDeveloper Unlock** in [Policy CSP](/windows/client-management/mdm/policy-configuration-service-provider). [Ulteriori informazioni sulla modalità sviluppatore.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. In un computer connettersi al HoloLens tramite [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) o [USB.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Eseguire una delle operazioni seguenti:
   - Se ci si connette alla Windows Portale di dispositivi per la prima volta, [creare un nome utente e una password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Immettere il nome utente e la password impostati in precedenza.

    > [!TIP]
    > Se viene visualizzato un errore di certificato nel browser, seguire le seguenti [procedure per la risoluzione dei problemi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. Nell'Windows Portale di dispositivi selezionare Modalità **tutto schermo.**

1. Selezionare **Abilita modalità tutto schermo,** selezionare un'app da eseguire all'avvio del dispositivo e quindi selezionare **Salva.**

    ![Modalità tutto schermo](images/kiosk.png)
1. Riavviare HoloLens. Se la pagina di Portale di dispositivi è ancora aperta, è possibile **selezionare** Riavvia nella parte superiore della pagina.

> [!NOTE]
> La modalità tutto schermo può essere impostata tramite l'API REST di Portale di dispositivi eseguendo un post su /api/holographic/kioskmode/settings con un parametro della stringa di query obbligatorio ("kioskModeEnabled&quot; con valore &quot;true&quot; o &quot;false") e un parametro facoltativo ("startupApp" con un valore di nome pacchetto). Tenere presente che la Portale di dispositivi è destinata solo agli sviluppatori e non deve essere abilitata nei dispositivi non sviluppatori. L'API REST è soggetta a modifiche negli aggiornamenti/versioni future.

## <a name="more-information"></a>Altre informazioni

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Vedere come configurare un chiosco multimediale usando un pacchetto di provisioning.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Accesso assegnato globale - Modalità tutto schermo
- Riduzione della gestione delle identità per chiosco multimediale, abilitando il nuovo metodo Tutto schermo che applica la modalità tutto schermo a livello di sistema.

Questa nuova funzionalità consente a un amministratore IT di configurare un dispositivo HoloLens 2 per la modalità tutto schermo per più app applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che a loro volta apportare l'accesso al dispositivo. Per altri [dettagli su HoloLens nuova funzionalità, vedere](hololens-global-assigned-access-kiosk.md) la documentazione relativa HoloLens accesso in modalità tutto schermo assegnato a livello globale.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Avvio automatico di un'applicazione in modalità tutto schermo con più app 
- Esperienza mirata con l'avvio automatico dell'app, aumentando ulteriormente l'interfaccia utente e le selezioni di app scelte per le esperienze in modalità tutto schermo.

Si applica solo alla modalità tutto schermo con più app e solo 1 app può essere designata per l'avvio automatico usando l'attributo evidenziato seguente nella configurazione di Accesso assegnato. 

L'applicazione viene avviata automaticamente all'accesso dell'utente. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifiche del comportamento della modalità tutto schermo per la gestione degli errori
Quando si verificano errori durante l'applicazione della modalità tutto schermo, viene visualizzato il comportamento seguente:

- Prima di Windows Holographic, la versione 20H2 - HoloLens mostra tutte le applicazioni nel menu Start.
- Windows Holographic, versione 20H2: se un dispositivo ha una configurazione tutto schermo che è una combinazione di accesso assegnato a livello globale e accesso assegnato ai membri del gruppo AAD, se la determinazione dell'appartenenza al gruppo AAD non riesce, l'utente non visualizza alcun elemento nel menu Start.

![Immagine dell'aspetto della modalità tutto schermo in caso di errore.](images/hololens-kiosk-failure-behavior.png )


- A partire [da Windows Holographic, versione 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)la modalità tutto schermo cerca Accesso assegnato globale prima di visualizzare un menu Start vuoto. In caso di errori durante la modalità tutto schermo del gruppo AAD, l'esperienza in modalità tutto schermo verrà fallback a una configurazione tutto schermo globale, se presente.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Memorizzare nella cache Azure AD appartenenza al gruppo per la modalità tutto schermo offline

- Modalità tutto schermo più sicura eliminando le app disponibili in caso di errori in modalità tutto schermo.
- Abilitate le modalità tutto schermo offline da usare Azure AD gruppi per un massimo di 60 giorni.

Questo criterio controlla per quanti giorni è Azure AD possibile usare la cache di appartenenza ai gruppi per le configurazioni di accesso assegnato che Azure AD gruppi per l'utente connesso. Quando il valore di questo criterio è impostato solo su un valore maggiore di 0, la cache viene usata in caso contrario.  

Nome: Valore URI AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 giorni  
Max - 60 giorni 

Passaggi per usare correttamente questo criterio: 
1. Creare un profilo di configurazione del dispositivo per la modalità tutto schermo Azure AD gruppi e assegnarlo HoloLens dispositivi. 
1. Creare una configurazione personalizzata del dispositivo basata su URI OMA che imposta il valore del criterio sul numero di giorni desiderato (> 0) e assegnarlo HoloLens dispositivi. 
    1. Il valore URI deve essere immesso nella casella di testo OMA-URI come ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Il valore può essere compreso tra min/max consentito.
1. Registrare HoloLens dispositivi e verificare che entrambe le configurazioni siano applicate al dispositivo. 
1. Consentire Azure AD'accesso dell'utente 1 quando è disponibile Internet, dopo che l'utente ha eseguito l'accesso e Azure AD'appartenenza al gruppo è stata confermata correttamente, verrà creata la cache. 
1. Ora Azure AD'utente 1 può portare HoloLens offline e usarlo per la modalità tutto schermo, purché il valore dei criteri consenta X numero di giorni. 
1. I passaggi 4 e 5 possono essere ripetuti per qualsiasi altro utente di Azure AD N. Punto chiave è che qualsiasi utente di Azure AD deve accedere al dispositivo usando Internet in modo da poterlo determinare almeno una volta che è membro del gruppo Azure AD a cui è destinata la configurazione tutto schermo. 
 
> [!NOTE]
> Fino a quando non viene eseguito il passaggio 4 per un Azure AD si verifica un comportamento di errore indicato negli ambienti "disconnessi". 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Esempi di codice in modalità tutto schermo XML per HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Più app in modalità tutto schermo che hanno come destinazione Azure AD gruppo. 
Questo chiosco multimediale distribuisce un chiosco multimediale che per gli utenti nel gruppo Azure AD avrà un chiosco multimediale abilitato che include le 3 app: Impostazioni, Remote Assist e Hub di Feedback. Per modificare questo esempio in modo che sia usato immediatamente, assicurarsi di modificare il GUID evidenziato di seguito in modo che corrisponda a un gruppo Azure AD personalizzato. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Più app in modalità tutto schermo con destinazione Azure AD'account.
Questo chiosco multimediale distribuisce un chiosco multimediale per un singolo utente e avrà un chiosco multimediale abilitato che include le tre app: Impostazioni, Remote Assist e Hub di Feedback. Per modificare questo esempio per l'uso immediato, assicurarsi di modificare l'account evidenziato di seguito in modo che corrisponda a un account Azure AD proprio. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

