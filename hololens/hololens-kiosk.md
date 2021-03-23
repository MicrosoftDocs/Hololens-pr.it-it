---
title: Configurare il dispositivo HoloLens come chiosco
description: Scopri come configurare e usare una configurazione tutto schermo per bloccare le app nei dispositivi HoloLens.
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
ms.openlocfilehash: a043b2f96bec6127d52622b4662279c777df6f8f
ms.sourcegitcommit: e1dd3d79d763d02d4fe04c82d8f49e8f9d85ee4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445376"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurare il dispositivo HoloLens come chiosco

Puoi configurare un dispositivo HoloLens in modo che funzioni ** come dispositivo a uso fisso, denominato anche chiosco multimediale, configurando il dispositivo per l'esecuzione in modalità tutto schermo. La modalità tutto schermo limita le applicazioni (o gli utenti) disponibili nel dispositivo. La modalità tutto schermo è una funzionalità comoda che puoi usare per dedicare un dispositivo HoloLens alle app aziendali o per usare il dispositivo HoloLens in una demo dell'app.

Questo articolo fornisce informazioni sugli aspetti della configurazione del chiosco multimediale specifici per i dispositivi HoloLens. Per informazioni generali sui diversi tipi di chioschi multimediale basati su Windows e su come configurarli, vedere [Configure kiosks and digital signs on Windows desktop editions.](https://docs.microsoft.com/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> La modalità tutto schermo determina quali app sono disponibili quando un utente accede al dispositivo. Tuttavia, la modalità tutto schermo non è un metodo di sicurezza. Non arresta l'apertura di un'altra app "consentita" non consentita. Per impedire l'apertura di app o processi, usa Windows Defender [CSP WDAC (Application Control)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) per creare i criteri appropriati.
>
> Altre informazioni sui servizi Microsoft per offrire agli utenti un livello avanzato di sicurezza utilizzato da HoloLens 2, altre informazioni sulla separazione e l'isolamento dello stato [- Protezioni di Defender.](security-state-separation-isolation.md#defender-protections) Oppure scopri come usare WDAC e Windows PowerShell per consentire o bloccare le app nei dispositivi [HoloLens 2 con Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

Puoi usare la modalità tutto schermo in una configurazione a singola app o multi-app e puoi usare uno dei tre processi per configurare e distribuire la configurazione tutto schermo.

> [!IMPORTANT]  
> L'eliminazione della configurazione multi-app rimuove i profili di blocco utente creati dalla funzionalità di accesso assegnato. Tuttavia, non vengono annullate tutte le modifiche ai criteri. Per ripristinare questi criteri, devi ripristinare le impostazioni di fabbrica del dispositivo.

## <a name="plan-the-kiosk-deployment"></a>Pianificare la distribuzione di chioschi multimediale

Quando si pianifica il chiosco multimediale, è necessario essere in grado di rispondere alle domande seguenti. Ecco alcune decisioni da prendere in considerazione durante la lettura di questa pagina e alcune considerazioni per queste domande.
1. **Chi verrà utilizzato dal chiosco multimediale e quale tipo di [account](hololens-identity.md) verrà utilizzato?** Si tratta di una decisione che probabilmente hai già preso e che non dovrebbe essere adattata per il chiosco multimediale, ma influirà sulla modalità di assegnazione del chiosco multimediale in un secondo momento.
1. **È necessario avere chioschi multimediale diversi per utente/gruppo o un chiosco multimediale non abilitato per alcuni?** In tal caso, è necessario creare il chiosco multimediale tramite XML. 
1. **Quante app saranno presenti nel chiosco multimediale?** Se hai più di un'app, avrai bisogno di un chiosco multimediale multi-app. 
1. **Quali app saranno nel chiosco multimediale?** Usa il nostro elenco di AUMID di seguito per aggiungere eventuali app In-Box oltre alle tue.
1. **Come si prevede di distribuire il chiosco multimediale?** Se stai registrando il dispositivo in MDM, ti consigliamo di usare MDM per distribuire il chiosco multimediale. Se non si usa MDM, è disponibile la distribuzione con il pacchetto di provisioning.  

### <a name="kiosk-mode-requirements"></a>Requisiti per la modalità tutto schermo

Puoi configurare qualsiasi dispositivo HoloLens 2 per l'uso della modalità tutto schermo.

> [!IMPORTANT]
> La modalità tutto schermo è disponibile solo se il dispositivo dispone di Windows Holographic for Business. Tutti i dispositivi HoloLens 2 vengono forniti con Windows Holographic for Business e non esistono altre edizioni. Ogni dispositivo HoloLens 2 è in grado di eseguire la modalità tutto schermo.
>
> I dispositivi HoloLens (prima generazione) devono essere aggiornati sia in termini di build del sistema operativo che di edizione del sistema operativo. Ecco altre informazioni sull'aggiornamento di un'edizione di HoloLens (prima generazione) a [Windows Holographic for Business.](hololens1-upgrade-enterprise.md) Per aggiornare un dispositivo HoloLens (prima generazione) per l'uso della modalità tutto schermo, devi prima assicurarti che il dispositivo eserciti Windows 10, versione 1803 o versione successiva. Se hai usato lo strumento ripristino dispositivi Windows per ripristinare la build predefinita del dispositivo HoloLens (prima generazione) o se hai installato gli aggiornamenti più recenti, il dispositivo è pronto per la configurazione.

> [!IMPORTANT]  
> Per proteggere i dispositivi che vengono eseguiti in modalità tutto schermo, valuta la possibilità di aggiungere criteri di gestione dei dispositivi che disattivano funzionalità come la connettività USB. Controllare inoltre le impostazioni dell'anello di aggiornamento per assicurarsi che gli aggiornamenti automatici non si verifichino durante l'orario di ufficio.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Decidere tra un chiosco multimediale con una singola app o un chiosco multimediale multi-app

Un chiosco multimediale con una singola app avvia l'app specificata quando l'utente accede al dispositivo. Il menu Start è disabilitato, così come Cortana. Un dispositivo HoloLens 2 non risponde al gesto [Start.](hololens2-basic-usage.md#start-gesture) Un dispositivo HoloLens (prima generazione) non risponde al gesto [bloom.](hololens1-basic-usage.md) Poiché solo un'app può essere eseguita, l'utente non può inserire altre app.

Un chiosco multimediale multi-app visualizza il menu Start quando l'utente accede al dispositivo. La configurazione del chiosco multimediale determina quali app sono disponibili nel menu Start. Puoi usare un chiosco multimediale multi-app per offrire agli utenti un'esperienza di facile comprensione presentando loro solo gli elementi che devono usare e rimuovendo gli elementi che non devono usare.

Nella tabella seguente sono elencate le funzionalità nelle diverse modalità tutto schermo.

| &nbsp; |Menu Start |Menu Azioni rapide |Fotocamera e video |Miracast |Cortana |Comandi vocali predefiniti |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Chiosco multimediale con app singola |Disabilitato |Disabilitato   |Disabilitato |Disabilitato   |Disabilitato |Abilitato <sup> 1</sup> |
|Chiosco con più app |Abilitato |Abilitato <sup> 2</sup> |Disponibile <sup> 2</sup> |Disponibile <sup> 2</sup> |Disponibile <sup> 2, 3</sup>  |Abilitato <sup> 1</sup> |

> <sup>1 </sup> I comandi vocali correlati alle funzionalità disabilitate non funzionano.  
> <sup>2 </sup> Per ulteriori informazioni su come configurare queste funzionalità, vedi Selezionare le app [chiosco multimediale.](#plan-kiosk-apps)  
> <sup>3 </sup> Anche se Cortana è disabilitata, i comandi vocali incorporati sono abilitati.

Nella tabella seguente sono elencate le funzionalità di supporto per gli utenti delle diverse modalità tutto schermo.

| &nbsp; |Tipi di utenti supportati | Accesso automatico | Più livelli di accesso |
| --- | --- | --- | --- |
|Chiosco multimediale con app singola |Account del servizio gestito (MSA) in Azure Active Directory (Azure AD) o account locale |Sì |No |
|Chiosco con più app |Account Azure AD |No |Sì |

Per esempi su come usare queste funzionalità, vedere la tabella seguente.

|Usa un chiosco multimediale con una singola app per: |Usare un chiosco multimediale multi-app per: |
| --- | --- |
|Dispositivo che esegue solo una Guida di Dynamics 365 per i nuovi dipendenti. |Dispositivo che esegue sia Guide che Assistenza remota per un'ampia gamma di dipendenti. |
|Dispositivo che esegue solo un'app personalizzata. |Dispositivo che funziona come chiosco multimediale per la maggior parte degli utenti (che esegue solo un'app personalizzata), ma funziona come dispositivo standard per un gruppo specifico di utenti. |

### <a name="plan-kiosk-apps"></a>Pianificare le app chiosco multimediale

Per informazioni generali su come scegliere le app chiosco multimediale, vedi Linee guida per la scelta di [un'app per l'accesso assegnato (modalità tutto schermo).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Se usi Windows Device Portal per configurare un chiosco multimediale con una singola app, seleziona l'app durante il processo di installazione.  

Se usi un sistema di gestione dei dispositivi mobili (MDM) o un pacchetto di provisioning per configurare la modalità tutto schermo, usi il provider di servizi di configurazione [AssignedAccess (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) per specificare le applicazioni. Il provider di servizi di configurazione usa gli ID modello utente [dell'applicazione (AUMID)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) per identificare le applicazioni. Nella tabella seguente sono elencati gli AUMID di alcune applicazioni in-box che puoi usare in un chiosco multimediale multi-app.

> [!IMPORTANT]
> La modalità tutto schermo determina quali app sono disponibili quando un utente accede al dispositivo. Tuttavia, la modalità tutto schermo non è un metodo di sicurezza. Non arresta l'apertura di un'altra app "consentita" non consentita. Poiché questo comportamento non viene limitato, le app possono comunque essere avviate da Edge, Esplora file e le app di Microsoft Store. Se ci sono app specifiche che non vuoi avviare da un chiosco multimediale, usa [Windows Defender Application Control (WDAC) per](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) creare i criteri appropriati. 
> 
> Inoltre, la home page di realtà mista non può essere impostata come app tutto schermo.

<a id="aumids"></a>

|Nome app |AUMID |
| --- | --- |
|Visualizzatore 3D |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\! Microsoft.Microsoft3DViewer |
|Calendario |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|Fotocamera <sup> 1, 2</sup> |HoloCamera\_cw5n1h2txyewy\! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\! App |
|Selezione dispositivi in HoloLens (prima generazione) |HoloDevicesFlow\_cw5n1h2txyewy\! HoloDevicesFlow |
|Selezione dispositivi in HoloLens 2 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\! Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\! Microsoft.RemoteAssist |
|Hub &nbsp; di Feedback |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\! App |
|Esplora file |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|Film e TV |Microsoft.ZuneVideo\_8wekyb3d8bbwe\! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\! App |
|Foto |Microsoft.Windows.Foto\_8wekyb3d8bbwe\! App |
|Impostazioni |HolographicSystemSettings\_cw5n1h2txyewy\! App |
|Suggerimenti |Microsoft.HoloLensTips\_8wekyb3d8bbwe\! HoloLensTips |

> <sup>1 </sup> Per abilitare l'acquisizione di foto o video, devi abilitare l'app Fotocamera come app tutto schermo.  
> <sup>2 </sup> Quando abiliti l'app Fotocamera, verifica le condizioni seguenti:
> - Il menu Azioni rapide include i pulsanti Foto e Video.  
> - Devi anche abilitare un'app (ad esempio Foto, Mail o OneDrive) in grado di interagire con o recuperare immagini.  
>  
> <sup>3 </sup> Anche se non abiliti Cortana come app tutto schermo, i comandi vocali incorporati sono abilitati. Tuttavia, i comandi correlati alle funzionalità disabilitate non hanno alcun effetto.  
> <sup>4 </sup> Non è possibile abilitare Miracast direttamente. Per abilitare Miracast come app tutto schermo, abilita l'app Fotocamera e l'app Selezione dispositivi.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Pianificare profili chiosco multimediale per utenti o gruppi

Quando si crea il file XML o si usa l'interfaccia utente di Intune per configurare un chiosco multimediale, è necessario considerare chi sarà l'utente del chiosco multimediale. Una configurazione tutto schermo può essere limitata a un singolo account o a gruppi di Azure AD. 

In genere i chioschi sono abilitati per un utente o un gruppo di utenti. Tuttavia, se si prevede di scrivere un chiosco XML personalizzato, è consigliabile prendere in considerazione l'accesso assegnato globale, in cui il chiosco multimediale viene applicato a livello di dispositivo indipendentemente dall'identità. Se questo ti fa appello, [leggi altre informazioni sui chioschi di accesso assegnato globale.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Se si sta creando un file XML:
-   Molti utenti creano più profili kiosk e assegnano ognuno a utenti/gruppi diversi. Ad esempio, un chiosco multimediale per il gruppo di Azure AD con molte app e un visitatore con un chiosco multimediale con più app con un'app singolare.
-   La configurazione del chiosco multimediale sarà denominata **ID profilo** e avrà un GUID.
-   Il profilo verrà assegnato nella sezione configs specificando il tipo di utente e utilizzando lo stesso GUID per **DefaultProfile Id.**
- Un file XML può essere creato ma comunque applicato a un dispositivo tramite MDM creando un profilo di configurazione del dispositivo URI OMA personalizzato e applicandolo al gruppo di dispositivi HoloLens usando il valore URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Se si crea un chiosco multimediale in Intune.
-   Ogni dispositivo può ricevere un solo profilo kiosk, altrimenti creerà un conflitto e non riceverà alcuna configurazione kiosk. 
    -   Altri tipi di profili e criteri, ad esempio restrizioni per i dispositivi non correlati al profilo di configurazione del chiosco multimediale, non sono in conflitto con il profilo di configurazione del chiosco multimediale.
-   Il chiosco multimediale verrà abilitato per tutti gli utenti che fanno parte del tipo Accesso utente, che verrà impostato con un utente o un gruppo di Azure AD. 
-   Dopo aver impostato la configurazione del chiosco multimediale e aver selezionato il tipo di accesso utente **(gli** utenti che possono accedere al chiosco multimediale) e le app, la configurazione del dispositivo deve comunque essere assegnata a un gruppo. I gruppi assegnati determinano i dispositivi che ricevono la configurazione del dispositivo Kiosk, ma non interagiscono con se il chiosco multimediale è abilitato o meno. 
    - Per una descrizione completa degli effetti dell'assegnazione dei profili di configurazione in Intune, vedere Assegnare profili utente [e dispositivo in Microsoft Intune.](https://docs.microsoft.com/intune/configuration/device-profile-assign)

### <a name="select-a-deployment-method"></a>Selezionare un metodo di distribuzione

È possibile selezionare uno dei metodi seguenti per distribuire le configurazioni di chiosco multimediale:

- [Microsoft Intune o un altro servizio di gestione dei dispositivi mobili (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pacchetto di provisioning](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Poiché questo metodo richiede che la modalità sviluppatore sia abilitata nel dispositivo, ti consigliamo di usarla solo per le dimostrazioni.

Nella tabella seguente sono elencate le funzionalità e i vantaggi di ognuno dei metodi di distribuzione.

| &nbsp; |Distribuire tramite Windows Device Portal |Distribuire tramite un pacchetto di provisioning |Distribuire tramite MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Distribuire chioschi multimediale con una singola app   | Sì           | Sì                  | Sì  |
|Distribuire chioschi multimediale multi-app    | No            | Sì                  | Sì  |
|Distribuire solo nei dispositivi locali | Sì           | Sì                  | No   |
|Distribuire tramite la modalità sviluppatore |Obbligatorio       | Non necessario            | Non necessario   |
|Distribuire tramite Azure Active Directory (Azure AD)  | Non necessario            | Non necessario                   | Obbligatorio  |
|Distribuisci automaticamente      | No            | No                   | Sì  |
|Velocità di distribuzione            | Velocità       | Velocità                 | Lento |
|Distribuire su larga scala | Non consigliato    | Consigliato        | Consigliato |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Usare Microsoft Intune o un'altra soluzione MDM per configurare un chiosco multimediale con una singola app o multi-app

Per configurare la modalità tutto schermo usando Microsoft Intune o un altro sistema MDM, segui questa procedura.

1. [Preparare la registrazione dei dispositivi](#mdmenroll).
1. [Creare un profilo di configurazione tutto schermo](#mdmprofile).
1. Configurare il chiosco multimediale.
   - [Configurare le impostazioni per un chiosco multimediale con una singola app.](#mdmconfigsingle)
   - [Configurare le impostazioni per un chiosco multimediale multi-app.](#mdmconfigmulti)
1. [Assegnare il profilo di configurazione del chiosco multimediale a un gruppo](#mdmassign).
1. Distribuire i dispositivi.
   - [Distribuire un chiosco multimediale con un'unica app.](#mdmsingledeploy)
   - [Distribuire un chiosco multimediale multi-app](#mdmmultideploy).

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, passaggio 1 &ndash; Preparare la registrazione dei dispositivi

Puoi configurare il sistema MDM per registrare automaticamente i dispositivi HoloLens quando l'utente accede per la prima volta oppure fare in modo che gli utenti la registrano manualmente. I dispositivi devono inoltre essere aggiunti al dominio di Azure AD e assegnati ai gruppi appropriati.

Per altre informazioni su come registrare i dispositivi, vedi [Registrare HoloLens in MDM](hololens-enroll-mdm.md) e Metodi di registrazione [di Intune per i dispositivi Windows.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, passaggio 2 &ndash; Creare un profilo di configurazione di chiosco multimediale

1. Aprire il [portale di Azure](https://portal.azure.com/) e accedere all'account di amministratore di Intune.
1. Selezionare **Configurazione dei dispositivi**di Microsoft Intune -  >  **Profili**  >  **Crea profilo**.
1. Immettere un nome di profilo.
1. Seleziona **Piattaforma**  >  **Windows 10 e versioni successive**e quindi seleziona Tipo di **profilo**  > **Restrizioni dispositivo.**
1. Selezionare **Configura**  >  **chiosco**multimediale e quindi selezionare una delle opzioni seguenti:
   - Per creare un chiosco multimediale con una singola app, seleziona **Chiosco multimediale**  >  **per app singola.**
   - Per creare un chiosco multimediale multi-app, seleziona **Tutto**schermo in modalità tutto schermo  >  **multi-app.**
1. Per avviare la configurazione del chiosco multimediale, selezionare **Aggiungi**.

I passaggi successivi variano a seconda del tipo di chiosco multimediale desiderato. Per ulteriori informazioni, selezionare una delle opzioni seguenti:  

- [Chiosco multimediale con app singola](#mdmconfigsingle)
- [Chiosco con più app](#mdmconfigmulti)

Per altre informazioni su come creare un profilo di configurazione di chiosco multimediale, vedi Impostazioni dei dispositivi [Windows 10 e Windows Holographic for Business](https://docs.microsoft.com/intune/configuration/kiosk-settings)da eseguire come chiosco multimediale dedicato con Intune.

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, passaggio 3 (singola app) Configurare le impostazioni per un &ndash;  chiosco multimediale con una singola app

Questa sezione riepiloga le impostazioni necessarie per un chiosco multimediale con una singola app. Per ulteriori informazioni, vedere gli articoli seguenti:

- Per informazioni su come configurare un profilo di configurazione di chiosco multimediale in Intune, vedere Come configurare la modalità tutto schermo [con Microsoft Intune.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Per altre informazioni sulle impostazioni disponibili per chioschi in modalità tutto schermo in Intune, vedi Chioschi app a [schermo intero](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Per altri servizi MDM, vedere le istruzioni nella documentazione del provider. Se devi usare una configurazione XML personalizzata per configurare un chiosco multimediale nel servizio MDM, crea un file XML che definisce [la configurazione del chiosco multimediale.](#ppkioskconfig)

1. Selezionare **Tipo di**accesso utente Account utente locale e quindi immettere il nome utente dell'account locale (dispositivo) o dell'account Microsoft (MSA) che può accedere al  >  **** chiosco multimediale.
   > [!NOTE]  
   > **I tipi di** account utente di Accesso automatico non sono supportati in Windows Holographic for Business.
1. Seleziona **Tipo di applicazione**App dello  >  **Store**e quindi seleziona un'app nell'elenco.

Il passaggio successivo consiste [nell'assegnare](#mdmassign) il profilo a un gruppo.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, passaggio 3 (multi-app) &ndash; Configurare le impostazioni per un chiosco multimediale multi-app

Questa sezione riepiloga le impostazioni necessarie per un chiosco multimediale multi-app. Per informazioni più dettagliate, vedere gli articoli seguenti:

- Per informazioni su come configurare un profilo di configurazione di chiosco multimediale in Intune, vedere Come configurare la modalità tutto schermo [con Microsoft Intune.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Per altre informazioni sulle impostazioni disponibili per chioschi multimediale multi-app in Intune, vedi [Chioschi multimediale multi-app](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Per altri servizi MDM, vedere le istruzioni nella documentazione del provider. Se devi usare una configurazione XML personalizzata per configurare un chiosco multimediale nel servizio MDM, crea un file XML che definisce [la configurazione del chiosco multimediale.](#ppkioskconfig) Se usi un file XML, assicurati di includere il [layout della schermata Start.](#start-layout-for-hololens)  
- Facoltativamente, puoi usare un layout della schermata Start personalizzato con Intune o altri servizi MDM. Per altre informazioni, vedi [File di layout della schermata Start per MDM (Intune e altri).](#start-layout-file-for-mdm-intune-and-others)

1. Seleziona **Destinazione Windows 10 nei dispositivi in modalità S**  >  **No.**  
   >[!NOTE]  
   > La modalità S non è supportata in Windows Holographic for Business.
1. Selezionare **User logon type**Azure AD user or  >  **group** or User logon **type**  >  **HoloLens visitor**e quindi aggiungere uno o più gruppi di utenti o account.  

   Solo gli utenti che appartengono ai gruppi o agli account specificati in **Tipo di accesso utente** possono utilizzare l'esperienza chiosco multimediale.

1. Seleziona una o più app usando le opzioni seguenti:
   - Per aggiungere un'app line-of-business caricata, seleziona **Aggiungi app dello Store** e quindi seleziona l'app desiderata.
   - Per aggiungere un'app specificando il relativo AUMID, seleziona **Aggiungi da AUMID** e quindi immetti L'AUMID dell'app. [Vedi l'elenco degli AUMID disponibili](#aumids)

Il passaggio successivo consiste [nell'assegnare](#mdmassign) il profilo a un gruppo.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, passaggio 4 &ndash; Assegnare il profilo di configurazione del chiosco multimediale a un gruppo

Utilizzare la **pagina Assegnazioni** del profilo di configurazione del chiosco multimediale per impostare la posizione in cui si desidera distribuire la configurazione del chiosco multimediale. Nel caso più semplice, assegni il profilo di configurazione tutto schermo a un gruppo che conterrà il dispositivo HoloLens quando il dispositivo si registra in MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, passaggio 5 (singola app) &ndash; Distribuire un chiosco multimediale con una singola app

Quando usi un sistema MDM, puoi registrare il dispositivo in MDM durante la configurazione automatica. Al termine della Configurazione utente, l'accesso al dispositivo è semplice.

Durante la Configurazione utente, attenersi alla seguente procedura:

1. Accedi usando l'account specificato nel profilo di configurazione del chiosco multimediale.
1. Registrare il dispositivo. Assicurati che il dispositivo sia aggiunto al gruppo a cui è assegnato il profilo di configurazione del chiosco multimediale.
1. Attendere il completamento della Procedura guidata, il download e l'installazione dell'app dello Store e l'applicazione dei criteri. Quindi riavvia il dispositivo.

Al successivo accesso al dispositivo, l'app tutto schermo dovrebbe avviarsi automaticamente.

Se non vedi la configurazione del chiosco multimediale a questo punto, [controlla lo stato dell'assegnazione.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, passaggio 5 (multi-app) &ndash; Distribuire un chiosco multimediale multi-app

Quando usi un sistema MDM, puoi aggiungere il dispositivo al tenant di Azure AD e registrare il dispositivo in MDM durante la configurazione automatica. Se appropriato, fornire le informazioni di registrazione agli utenti in modo che siano disponibili durante il processo di configurazione guidata.

> [!NOTE]  
> Se hai assegnato il profilo di configurazione tutto schermo a un gruppo che contiene utenti, assicurati che uno di questi account utente sia il primo account ad accedere al dispositivo.

Durante la Configurazione utente, attenersi alla seguente procedura:

1. Accedere utilizzando l'account appartenente al gruppo **Tipo di accesso** utente.
1. Registrare il dispositivo.
1. Attendi che le app che fanno parte del profilo di configurazione del chiosco multimediale siano scaricate e installate. Attendere inoltre che i criteri siano applicati.  
1. Al termine della Configurazione guidata, puoi installare altre app da Microsoft Store o tramite sideload. [App necessarie](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) per il gruppo a cui appartiene il dispositivo per l'installazione automatica.
1. Al termine dell'installazione, riavvia il dispositivo.

Al successivo accesso al dispositivo usando un account appartenente al tipo Accesso **utente,** l'app tutto schermo dovrebbe essere avviata automaticamente.

Se non vedi la configurazione del chiosco multimediale a questo punto, [controlla lo stato dell'assegnazione.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Usare un pacchetto di provisioning per configurare un chiosco multimediale con una singola app o multi-app

Per configurare la modalità tutto schermo usando un pacchetto di provisioning, segui questi passaggi.

1. [Creare un file XML che definisce la configurazione del chiosco multimediale,](#ppkioskconfig)incluso un [layout della schermata Start.](#start-layout-for-hololens)
2. [Aggiungi il file XML a un pacchetto di provisioning.](#ppconfigadd)
3. [Applica il pacchetto di provisioning a HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Pacchetto di provisioning, passaggio 1 &ndash; Creare un file XML di configurazione di chiosco multimediale

Segui le istruzioni generali per creare un file XML di configurazione tutto schermo [per Desktop di Windows,](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)ad eccezione dei seguenti:

- Non includere le applicazioni classiche di Windows (Win32). HoloLens non supporta queste applicazioni.
- Usa il [segnaposto XML del layout della](#start-layout-for-hololens) schermata Start per HoloLens.
- Facoltativo: aggiungere l'accesso guest alla configurazione del chiosco multimediale

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Facoltativo: aggiungere l'accesso guest alla configurazione del chiosco multimediale

Nella sezione [ **Configs** del file XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)è possibile configurare un gruppo speciale denominato **Visitor** per consentire agli utenti guest di utilizzare il chiosco multimediale. Quando il chiosco multimediale è configurato per supportare il gruppo speciale **Visitatore,** alla pagina di accesso viene aggiunta un'opzione "**Guest**". **L'account** Guest non richiede una password e tutti i dati associati all'account vengono eliminati quando l'account si esce.

Per abilitare l'account **Guest,** aggiungi il frammento di codice seguente al codice XML di configurazione del chiosco multimediale:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Layout della schermata Start segnaposto per HoloLens

Se usi un pacchetto [di provisioning per](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) configurare un chiosco multimediale multi-app, la procedura richiede un layout della schermata Start. La personalizzazione del layout della schermata Start non è supportata in Windows Holographic for Business. Di conseguenza, dovrai usare un layout della schermata Start segnaposto.

> [!NOTE]  
> Poiché un chiosco multimediale con un'unica app avvia l'app tutto schermo quando un utente accede, non usa un menu Start e non deve avere un layout della schermata Start.

> [!NOTE]  
> Se usi [MDM per](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) configurare un chiosco multimediale multi-app, puoi usare facoltativamente un layout della schermata Start. Per altre informazioni, vedi [File di layout della schermata Start segnaposto per MDM (Intune e altri).](#start-layout-file-for-mdm-intune-and-others)

Per il layout della schermata Start, aggiungi la sezione **StartLayout** seguente al file XML di provisioning del chiosco multimediale:

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>File di layout della schermata Start segnaposto per MDM (Intune e altri)

Salvare l'esempio seguente come file XML. È possibile usare questo file quando si configura il chiosco multimediale multi-app in Microsoft Intune (o in un altro servizio MDM che fornisce un profilo tutto schermo).

> [!NOTE]
> Se devi usare un'impostazione personalizzata e una configurazione XML completa per configurare un chiosco multimediale nel servizio MDM, usa le istruzioni per il layout della [schermata Start per un pacchetto di provisioning.](#start-layout-for-hololens)

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. pacchetto, passaggio 2 Aggiungere il file XML di &ndash; configurazione del chiosco multimediale a un pacchetto di provisioning

1. Aprire [Progettazione configurazione di Windows.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Selezionare **Provisioning avanzato,** immettere un nome per il progetto e quindi selezionare **Avanti.**
1. Seleziona **Windows 10 Holographic**e quindi seleziona **Avanti.**
1. Selezionare **Fine.** Si aprirà l'area di lavoro per il pacchetto.
1. Selezionare **Impostazioni di runtime**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. Nel riquadro centrale selezionare **Sfoglia** per individuare e selezionare il file XML di configurazione del chiosco multimediale creato.

   ![Screenshot del campo MultiAppAssignedAccessSettings in Progettazione configurazione di Windows](./images/multiappassignedaccesssettings.png)

1. **Facoltativo**. Se vuoi applicare il pacchetto di provisioning dopo la configurazione iniziale del dispositivo ed è già disponibile un utente amministratore nel dispositivo tutto schermo, ignora questo passaggio. Selezionare **Impostazioni di runtime** &gt; **Account** &gt; **Utenti**e quindi creare un account utente. Specificare un nome utente e una password, quindi selezionare **UserGroup**  >  **Administrators.**  
  
     Utilizzando questo account, è possibile visualizzare lo stato del provisioning e i log.  
1. **Facoltativo**. Se hai già un account non amministratore nel dispositivo tutto schermo, ignora questo passaggio. Selezionare **Impostazioni di runtime** &gt; **Account** &gt; **Utenti**e quindi creare un account utente locale. Verificare che il nome utente sia lo stesso dell'account specificato nel codice XML di configurazione. Selezionare **UserGroup**  >  **Standard Users**.
1. Selezionare **Salva**  >  **file**.
1. Seleziona **Esporta**  >  **pacchetto di provisioning**e quindi seleziona **Proprietario**  >  **amministratore IT.** In questo modo viene impostata la precedenza di questo pacchetto di provisioning superiore ai pacchetti di provisioning applicati a questo dispositivo da altre origini.
1. Seleziona **Avanti**.
1. Nella pagina **Sicurezza pacchetto di provisioning** seleziona un'opzione di sicurezza.
   > [!IMPORTANT]  
   > Se si seleziona **Abilita firma pacchetto**, è inoltre necessario selezionare un certificato valido da utilizzare per la firma del pacchetto. A tale scopo, selezionare **Sfoglia** e selezionare il certificato che si desidera utilizzare per firmare il pacchetto.
   
   > [!CAUTION]  
   > Non selezionare Abilita **crittografia pacchetto**. Nei dispositivi HoloLens, questa impostazione causa l'esito negativo del provisioning.
1. Seleziona **Avanti**.
1. Specifica il percorso di output in cui vuoi che il pacchetto di provisioning vada quando viene creato. Per impostazione predefinita, Progettazione configurazione di Windows usa la cartella di progetto come percorso di output. Se si desidera modificare il percorso di output, selezionare **Sfoglia**. Al termine, selezionare **Avanti**.
1. Seleziona **Compila** per iniziare a compilare il pacchetto. La compilazione del pacchetto di provisioning non richiede molto tempo. Nella pagina di compilazione vengono visualizzate le informazioni sul progetto e l'indicatore di stato indica lo stato della compilazione.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Pacchetto di provisioning, passaggio 3 &ndash; Applicare il pacchetto di provisioning a HoloLens

L'articolo "Configurare HoloLens tramite un pacchetto di provisioning" fornisce istruzioni dettagliate per applicare il pacchetto di provisioning nelle circostanze seguenti:

- Inizialmente puoi applicare [un pacchetto di provisioning a HoloLens durante l'installazione.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Puoi anche applicare [un pacchetto di provisioning a HoloLens dopo l'installazione.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Usare Windows Device Portal per configurare un chiosco multimediale con una singola app

Per configurare la modalità tutto schermo tramite Windows Device Portal, segui questi passaggi.

1. [Configurare il dispositivo HoloLens per l'uso di Windows Device Portal.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Device Portal è un server Web in HoloLens a cui è possibile connettersi da un browser Web nel PC.

    > [!CAUTION]
    > Quando si configura HoloLens per l'uso di Device Portal, è necessario abilitare la modalità sviluppatore nel dispositivo. La modalità sviluppatore in un dispositivo con Windows Holographic for Business ti consente di caricare le app in modalità side-load. Tuttavia, questa impostazione crea un rischio che un utente possa installare app che non sono state certificate da Microsoft Store. Gli amministratori possono bloccare la possibilità di abilitare la modalità sviluppatore utilizzando l'impostazione **ApplicationManagement/AllowDeveloper Unlock** nel [CSP Criteri.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [Scopri di più sulla Modalità sviluppatore.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. In un computer, connettersi a HoloLens tramite [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) o [USB.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Effettua una delle seguenti operazioni:
   - Se ci si connette a Windows Device Portal per la prima volta, [creare un nome utente e una password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Immettere il nome utente e la password precedentemente impostati.

    > [!TIP]
    > Se viene visualizzato un errore di certificato nel browser, seguire le seguenti [procedure per la risoluzione dei problemi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. In Windows Device Portal seleziona **Modalità tutto schermo.**

1. Seleziona **Abilita modalità tutto schermo,** seleziona un'app da eseguire all'avvio del dispositivo e quindi seleziona **Salva.**

    ![Modalità tutto schermo](images/kiosk.png)
1. Riavviare HoloLens. Se la pagina Portale dispositivi è ancora aperta, puoi selezionare **Riavvia** nella parte superiore della pagina.

> [!NOTE]
> La modalità tutto schermo può essere impostata tramite l'API REST di Device Portal eseguendo un post su /api/holographic/kioskmode/settings con un parametro stringa di query obbligatorio ("kioskModeEnabled" con un valore "true" o "false") e un parametro facoltativo ("startupApp" con il valore di un nome di pacchetto). Tieni presente che Device Portal è destinato solo agli sviluppatori e non deve essere abilitato nei dispositivi non sviluppatori. L'API REST è soggetta a modifiche negli aggiornamenti/rilasci futuri.

## <a name="more-information"></a>Altre informazioni

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Guarda come configurare un chiosco multimediale usando un pacchetto di provisioning.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Accesso assegnato globale - Modalità tutto schermo
- Gestione delle identità ridotta per Chiosco multimediale, abilitando il nuovo metodo Kiosk che applica la modalità tutto schermo a livello di sistema.

Questa nuova funzionalità consente a un amministratore IT di configurare un dispositivo HoloLens 2 per la modalità tutto schermo per più app applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che accodati al dispositivo. Per ulteriori informazioni su questa nuova funzionalità, vedi la documentazione relativa al chiosco multimediale con accesso assegnato globale di [HoloLens.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Avvio automatico di un'applicazione in modalità tutto schermo con più app 
- Esperienza mirata con l'avvio automatico dell'app, aumentando ulteriormente le selezioni di interfaccia utente e app scelte per le esperienze in modalità tutto schermo.

Si applica solo alla modalità tutto schermo per più app e solo 1 app può essere designata per l'avvio automatico usando l'attributo evidenziato di seguito nella configurazione di Accesso assegnato. 

L'applicazione viene avviata automaticamente all'accesso dell'utente. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifiche al comportamento della modalità tutto schermo per la gestione degli errori
- Modalità tutto schermo più sicura eliminando le app disponibili in caso di errori in modalità tutto schermo. 

In precedenza, quando si verificano errori durante l'applicazione della modalità tutto schermo, HoloLens mostrava tutte le applicazioni nel menu Start. Ora in Windows Holographic versione 20H2 in caso di errori nessuna app verrà visualizzata nel menu Start come indicato di seguito: 

![Immagine dell'aspetto della modalità tutto schermo in caso di errore.](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Memorizzare nella cache l'appartenenza al gruppo di Azure AD per chiosco multimediale offline
- Abilitati chioschi offline da usare con i gruppi di Azure AD per un massimo di 60 giorni.

Questo criterio controlla per quanti giorni è consentito usare la cache di appartenenza ai gruppi di Azure AD per le configurazioni di accesso assegnato per i gruppi di Azure AD per l'utente connesso. Quando questo valore del criterio è impostato su un valore maggiore di 0, viene utilizzata la cache in caso contrario.  

Nome: Valore URI AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 giorni  
Max - 60 giorni 

Passaggi per utilizzare correttamente questo criterio: 
1. Crea un profilo di configurazione del dispositivo per chiosco multimediale con gruppi di Azure AD e assegnalo ai dispositivi HoloLens. 
1. Crea una configurazione personalizzata del dispositivo basata su URI OMA che imposta questo valore del criterio sul numero di giorni desiderato (> 0) e assegnalo ai dispositivi HoloLens. 
    1. Il valore URI deve essere immesso nella casella di testo URI OMA come ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Il valore può essere compreso tra min /max consentito.
1. Registrare i dispositivi HoloLens e verificare che entrambe le configurazioni siano applicate al dispositivo. 
1. Consenti all'utente di Azure AD 1 di accedere quando è disponibile Internet, dopo che l'utente ha eseguito l'accesso e l'appartenenza al gruppo di Azure AD è stata confermata correttamente, verrà creata la cache. 
1. Ora l'utente 1 di Azure AD può portare HoloLens offline e usarlo per la modalità tutto schermo, purché il valore del criterio consenta il numero X di giorni. 
1. I passaggi 4 e 5 possono essere ripetuti per qualsiasi altro utente di Azure AD N. Il punto chiave qui è che qualsiasi utente di Azure AD deve accedere al dispositivo usando Internet in modo che almeno una volta possiamo determinare che sono membri del gruppo di Azure AD a cui è destinata la configurazione kiosk. 
 
> [!NOTE]
> Fino a quando non viene eseguito il passaggio 4 per un utente di Azure AD, si verifica un comportamento di errore menzionato in ambienti "disconnessi". 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Esempi di codice chiosco multimediale XML per HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Modalità tutto schermo per più app per un gruppo di Azure AD. 
Questo chiosco multimediale distribuisce un chiosco multimediale che per gli utenti del gruppo di Azure AD avrà un chiosco multimediale abilitato che include le 3 app: Impostazioni, Assistenza remota e Hub di Feedback. Per modificare questo esempio per l'uso immediato, assicurati di modificare il GUID evidenziato di seguito in modo che corrisponda a un proprio gruppo di Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Modalità tutto schermo per più app per l'account Azure AD.
Questo chiosco multimediale distribuisce un chiosco multimediale per un singolo utente, avrà un chiosco multimediale abilitato che include le 3 app: Impostazioni, Assistenza remota e Hub di Feedback. Per modificare questo esempio in modo che sia usato immediatamente, assicurati di modificare l'account evidenziato di seguito in modo che corrisponda a un account Azure AD personalizzato. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

