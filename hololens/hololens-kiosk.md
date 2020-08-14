---
title: Configurare il dispositivo HoloLens come chiosco
description: Usa una configurazione Kiosk per bloccare le app in HoloLens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f5c45477ab33064afe30e275f8b0003bc6022eac
ms.sourcegitcommit: bdbaed42dd9ecbd0ed9517de2e98a0465f584c1d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929852"
---
# Configurare il dispositivo HoloLens come chiosco

Puoi configurare un dispositivo HoloLens in modo che funzioni come dispositivo a scopo fisso, detto anche *chiosco*, configurando il dispositivo per l'esecuzione in modalità Kiosk. La modalità Kiosk limita le applicazioni (o gli utenti) disponibili nel dispositivo. La modalità Kiosk è una caratteristica comoda che puoi usare per dedicare un dispositivo HoloLens alle app aziendali o per usare il dispositivo HoloLens in una demo dell'app.

Questo articolo fornisce informazioni sugli aspetti della configurazione del chiosco specifici per i dispositivi HoloLens. Per informazioni generali sui diversi tipi di chioschi multimediali basati su Windows e su come configurarli, vedere [configurare i chioschi e i segni digitali nelle edizioni desktop di Windows](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> La modalità Kiosk determina quali app sono disponibili quando un utente accede al dispositivo. La modalità Kiosk tuttavia non è un metodo di sicurezza. Non interrompe un'app "consentita" dall'aprire un'altra app non consentita. Per bloccare le app o i processi da aprire, usare il [CSP WDAC (Windows Defender Application Control)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) per creare criteri appropriati.  

Puoi usare la modalità Kiosk in una configurazione Single-app o multi-app ed è possibile usare uno dei tre processi per configurare e distribuire la configurazione del chiosco.

> [!IMPORTANT]  
> Eliminando la configurazione multiapp vengono rimossi i profili di blocco degli utenti creati dalla funzionalità di accesso assegnata. Tuttavia, non ripristina tutte le modifiche ai criteri. Per ripristinare questi criteri, è necessario reimpostare il dispositivo sulle impostazioni di fabbrica.

## Pianificare la distribuzione di Kiosk

### Requisiti per la modalità Kiosk

Puoi configurare qualsiasi dispositivo HoloLens 2 per usare la modalità Kiosk.

Per configurare un dispositivo di HoloLens (1a generazione) in modo da usare la modalità Kiosk, è prima di tutto necessario verificare che il dispositivo esegua Windows 10, versione 1803 o una versione successiva. Se è stato usato lo strumento ripristino dispositivi Windows per recuperare il dispositivo HoloLens (1a Gen) nella Build predefinita o se sono stati installati gli aggiornamenti più recenti, il dispositivo è pronto per la configurazione.

> [!IMPORTANT]  
> Per proteggere i dispositivi eseguiti in modalità Kiosk, valutare l'aggiunta di criteri di gestione dei dispositivi che disattivano funzionalità come la connettività USB. Controlla inoltre le impostazioni della suoneria di aggiornamento per verificare che gli aggiornamenti automatici non si verifichino durante le ore lavorative.

### Scegliere tra un chiosco di app singole o un chiosco multiapp

Un chiosco Single-app avvia l'app specificata quando l'utente accede al dispositivo. Il menu Start è disabilitato, così come Cortana. Un dispositivo HoloLens 2 non risponde al gesto [iniziale](hololens2-basic-usage.md#start-gesture) . Un dispositivo HoloLens (1a generazione) non risponde al gesto della [fioritura](hololens1-basic-usage.md) . Poiché può essere eseguita solo un'app, l'utente non può inserire altre app.

Un chiosco multi-app Visualizza il menu Start quando l'utente accede al dispositivo. La configurazione di Kiosk determina quali app sono disponibili nel menu Start. Puoi usare un chiosco multiapp per offrire un'esperienza di facile comprensione agli utenti, presentando loro solo gli elementi che devono usare e rimuovendo gli elementi che non devono usare.

Nella tabella seguente sono elencate le funzionalità delle funzionalità delle diverse modalità Kiosk.

| &nbsp; |Menu Start |Menu azioni rapide |Fotocamera e video |Miracast |Cortana |Comandi vocali predefiniti |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Chiosco Single-app |Disabilitato |Disabilitato   |Disabilitato |Disabilitato   |Disabilitato |Abilitato <sup> 1</sup> |
|Chiosco multi-app |Abilitato |Abilitato <sup> 2</sup> |Disponibile <sup> 2</sup> |Disponibile <sup> 2</sup> |Disponibile <sup> 2, 3</sup>  |Abilitato <sup> 1</sup> |

> <sup>1 i </sup> comandi vocali correlati alle funzionalità disabilitate non funzioneranno.  
> <sup>2 </sup> per altre informazioni su come configurare queste funzionalità, vedere [selezionare app Kiosk](#plan-kiosk-apps).  
> <sup>3 </sup> anche se Cortana è disabilitato, i comandi vocali predefiniti sono abilitati.

Nella tabella seguente sono elencate le caratteristiche di supporto degli utenti delle diverse modalità Kiosk.

| &nbsp; |Tipi di utenti supportati | Accesso automatico | Più livelli di accesso |
| --- | --- | --- | --- |
|Chiosco Single-app |Account del servizio gestito (MSA) in Azure Active Directory (AAD) o account locale |Sì |No |
|Chiosco multi-app |Account AAD |No |Sì |

Per esempi su come usare queste funzionalità, vedere la tabella seguente.

|Usare un chiosco per le app singole per: |Usare un chiosco multi-app per: |
| --- | --- |
|Un dispositivo che esegue solo una guida di Dynamics 365 per i nuovi dipendenti. |Dispositivo che esegue sia guide che assistenza remota per un intervallo di dipendenti. |
|Un dispositivo che esegue solo un'app personalizzata. |Dispositivo che funge da chiosco per la maggior parte degli utenti (in cui è in uso solo un'app personalizzata), ma funziona come dispositivo standard per un gruppo specifico di utenti. |

### Pianificare le app Kiosk

Per informazioni generali su come scegliere le app Kiosk, Vedi [linee guida per la scelta di un'app per l'accesso assegnato (modalità Kiosk)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).

Se usi Windows Device Portal per configurare un chiosco di app singole, seleziona l'app durante il processo di configurazione.  

Se si usa un sistema di gestione di dispositivi mobili (MDM) o un pacchetto di provisioning per configurare la modalità Kiosk, è possibile usare il [provider del servizio di configurazione di AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) per specificare le applicazioni. Il CSP usa l' [ID del modello utente (aumid) Application](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) per identificare le applicazioni. Nella tabella seguente sono elencate le Aumid di alcune applicazioni in-box che è possibile usare in un chiosco multiapp.

> [!CAUTION]
> Non è possibile selezionare l'app shell come app Kiosk. Inoltre, ti consigliamo di **non** selezionare Microsoft Edge, Microsoft Store o Esplora file come app Kiosk.  

<a id="aumids"></a>

|Nome dell'app |AUMID |
| --- | --- |
|Visualizzatore 3D |Microsoft. Microsoft3DViewer \ _8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Calendar |Microsoft. windowscommunicationsapps \ _8wekyb3d8bbwe \! Microsoft. felici. Calendar |
|Fotocamera <sup> 1, 2</sup> |HoloCamera \ _cw5n1h2txyewy \ \! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft. 549981C3F5F10 \ _8wekyb3d8bbwe \! App |
|Selezione dispositivo in HoloLens (1a generazione) |HoloDevicesFlow \ _cw5n1h2txyewy \ \! HoloDevicesFlow |
|Selezione dispositivo in HoloLens 2 |Microsoft. Windows. DevicesFlowHost \ _cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft. Dynamics365. Guides \ _8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \ _8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|Hub di feedback &nbsp; |Microsoft. WindowsFeedbackHub \ _8wekyb3d8bbwe \! App |
|Esplora file |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |Microsoft. windowscommunicationsapps_8wekyb3d8bbwe! Microsoft. felici. mail |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|Film e TV |Microsoft. ZuneVideo \ _8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |Microsoft. microsoftskydrive \ _8wekyb3d8bbwe \! App |
|Foto |Microsoft. Windows. photos \ _8wekyb3d8bbwe \! App |
|Impostazioni |HolographicSystemSettings \ _cw5n1h2txyewy \ \! App |
|Suggerimenti |Microsoft. HoloLensTips \ _8wekyb3d8bbwe \! HoloLensTips |

> <sup>1 </sup> per abilitare l'acquisizione di foto o video, è necessario abilitare l'app fotocamera come app Kiosk.  
> <sup>2 </sup> quando si Abilita l'app fotocamera, tenere presente le condizioni seguenti:
> - Il menu azioni rapide include i pulsanti foto e video.  
> - Dovresti anche abilitare un'app (ad esempio foto, posta o OneDrive) in grado di interagire o recuperare le immagini.  
>  
> <sup>3 </sup> anche se non si Abilita Cortana come app Kiosk, i comandi vocali incorporati sono abilitati. Tuttavia, i comandi correlati alle funzionalità disabilitate non hanno effetto.  
> <sup>4 </sup> non è possibile abilitare direttamente Miracast. Per abilitare Miracast come app Kiosk, Abilita l'app videocamera e l'app selezione dispositivi.

### Pianificare i gruppi di utenti e dispositivi

In un ambiente MDM si usano i gruppi per gestire le configurazioni dei dispositivi e l'accesso degli utenti. 

Il profilo configurazione Kiosk include l'impostazione del **tipo di accesso utente** . Il **tipo di accesso utente** identifica l'utente (o il gruppo che contiene gli utenti) che può usare l'app o i apps aggiunti. Se un utente accede usando un account che non è incluso nel profilo di configurazione, l'utente non può usare le app nel chiosco.  

> [!NOTE]  
> Il **tipo di accesso utente** di un chiosco Single-app specifica un singolo account utente. Questo è il contesto utente in cui viene eseguito il chiosco. Il **tipo di accesso utente** di un chiosco multiapp può specificare uno o più account utente o gruppi che possono usare il chiosco.

Prima di poter distribuire la configurazione del chiosco in un dispositivo, è necessario *assegnare* il profilo di configurazione Kiosk a un gruppo che contiene il dispositivo o un utente che può accedere al dispositivo. Questa impostazione produce un comportamento come il seguente.

- Se il dispositivo è un membro del gruppo assegnato, la configurazione del chiosco viene distribuita al dispositivo la prima volta che un utente accede al dispositivo.  
- Se il dispositivo non è un membro del gruppo assegnato, ma un utente che fa parte di tale gruppo effettua l'accesso, la configurazione del chiosco viene distribuita al dispositivo in quel momento.

Per una descrizione completa degli effetti dell'assegnazione dei profili di configurazione in Intune, vedere [assegnare profili utente e di dispositivo in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

> [!NOTE]  
> Gli esempi seguenti descrivono i chioschi multimediali per le app. I chioschi Single-app si comportano in modo simile, ma solo un account utente ottiene l'esperienza del chiosco.

**Esempio 1**

Si usa un singolo gruppo (gruppo 1) per i dispositivi e gli utenti. Un dispositivo e gli utenti A, B e C sono membri di questo gruppo. Configurare il profilo di configurazione del chiosco nel modo seguente:  

- **Tipo di accesso utente**: gruppo 1
- **Gruppo assegnato**: gruppo 1

Indipendentemente dal fatto che l'utente accede prima al dispositivo (e passa attraverso l'esperienza di fuori casella o la configurazione guidata), viene distribuita al dispositivo. Gli utenti A, B e C possono accedere al dispositivo e ottenere l'esperienza del chiosco.

**Esempio 2**

I dispositivi sono contraenti per due fornitori diversi che hanno bisogno di esperienze Kiosk diverse. Entrambi i fornitori hanno utenti e si vuole consentire a tutti gli utenti di accedere ai chioschi sia dal proprio fornitore che dall'altro fornitore. I gruppi vengono configurati come segue:

- Gruppo di dispositivi 1:
  - Dispositivo 1 (fornitore 1)
  - Dispositivo 2 (fornitore 1)

- Gruppo di dispositivi 2:
  - Dispositivo 3 (Vendor 2)
  - Dispositivo 4 (Vendor 2)

- Gruppo utenti:
  - Utente A (fornitore 1)
  - Utente B (Vendor 2)

Si creano due profili di configurazione Kiosk con le impostazioni seguenti:

- Kiosk profile 1:
   - **Tipo di accesso utente**: gruppo utenti
   - **Gruppo assegnato**: gruppo di dispositivi 1

- Kiosk profile 2:
   - **Tipo di accesso utente**: gruppo utenti
   - **Gruppo assegnato**: gruppo di dispositivi 2

Queste configurazioni producono i risultati seguenti:

- Quando un utente accede al dispositivo 1 o al dispositivo 2, Intune distribuisce Kiosk profile 1 a tale dispositivo.
- Quando un utente accede al dispositivo 3 o al dispositivo 4, Intune distribuisce Kiosk profile 2 al dispositivo.
- L'utente A e l'utente B possono accedere a uno dei quattro dispositivi. Se accede al dispositivo 1 o al dispositivo 2, Visualizza l'esperienza del chiosco di vendor 1. Se accedono al dispositivo 3 o al dispositivo 4, vedranno l'esperienza del chiosco di vendor 2.

#### Conflitti di profilo

Se due o più profili di configurazione di Kiosk sono destinati allo stesso dispositivo, sono in conflitto. Nel caso dei dispositivi gestiti da Intune, Intune non applica alcuno dei profili in conflitto.

Altri tipi di profili e criteri, ad esempio le restrizioni dei dispositivi non correlati al profilo di configurazione Kiosk, non sono in conflitto con il profilo di configurazione del chiosco.

### Selezionare un metodo di distribuzione

Puoi selezionare uno dei metodi seguenti per distribuire le configurazioni di Kiosk:

- [Microsoft Intune o un altro servizio di gestione di dispositivi mobili (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pacchetto di provisioning](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Poiché questo metodo richiede che la modalità sviluppatore sia abilitata nel dispositivo, è consigliabile usarla solo per le dimostrazioni.

Nella tabella seguente sono elencate le funzionalità e i vantaggi di ognuno dei metodi di distribuzione.

| &nbsp; |Distribuire tramite Windows Device Portal |Distribuire usando un pacchetto di provisioning |Distribuire tramite MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Distribuire chioschi per app singole   | Sì           | Sì                  | Sì  |
|Distribuire chioschi multimediali per più app    | No            | Sì                  | Sì  |
|Distribuire solo ai dispositivi locali | Sì           | Sì                  | No   |
|Distribuire usando la modalità sviluppatore |Obbligatorio       | Non necessario            | Non necessario   |
|Distribuire usando Azure Active Directory (AAD)  | Non necessario            | Non necessario                   | Obbligatorio  |
|Distribuzione automatica      | No            | No                   | Sì  |
|Velocità di distribuzione            | Più veloce       | Velocità                 | Lento |
|Distribuire in scala | Non raccomandato    | Non raccomandato        | Consigliato |

## Usare Microsoft Intune o un altro MDM per configurare un chiosco Single-app o multi-app

Per configurare la modalità Kiosk con Microsoft Intune o un altro sistema MDM, eseguire la procedura seguente.

1. [Preparare la registrazione dei dispositivi](#mdmenroll).
1. [Creare un profilo di configurazione Kiosk](#mdmprofile).
1. Configurare il chiosco.
   - [Configurare le impostazioni per un chiosco di app singole](#mdmconfigsingle).
   - [Configurare le impostazioni per un chiosco multi-app](#mdmconfigmulti).
1. [Assegnare il profilo di configurazione Kiosk a un gruppo](#mdmassign).
1. Distribuire i dispositivi.
   - [Distribuire un chiosco Single-app](#mdmsingledeploy).
   - [Distribuire un chiosco multi-app](#mdmmultideploy).

### <a id="mdmenroll"></a>MDM, passaggio 1 &ndash; preparare la registrazione dei dispositivi

Puoi configurare il sistema MDM per la registrazione automatica dei dispositivi HoloLens quando l'utente accede prima o se gli utenti iscrivono i dispositivi manualmente. I dispositivi devono essere aggiunti anche al dominio di Azure AD e assegnati ai gruppi appropriati.

Per altre informazioni su come eseguire la registrazione dei dispositivi, vedere [registrazione di HoloLens nei](hololens-enroll-mdm.md) metodi di iscrizione a MDM e [Intune per i dispositivi Windows](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).

### <a id="mdmprofile"></a>MDM, passaggio 2 &ndash; creare un profilo di configurazione Kiosk

1. Aprire il portale di [Azure](https://portal.azure.com/) e accedere all'account di amministratore di Intune.
1. Selezionare Configurazione dispositivi **Microsoft Intune**  >  **-profili**per  >  **creare il profilo**.
1. Immettere il nome di un profilo.
1. Selezionare **Platform**  >  **Windows 10 e versioni successive**e quindi selezionare **il tipo di profilo restrizioni per il**  > **dispositivo**.
1. Selezionare **Configura**  >  **Kiosk**e quindi selezionare una delle opzioni seguenti:
   - Per creare un chiosco Single-app, seleziona Kiosk in **modalità Kiosk**  >  **Single-app**.
   - Per creare un chiosco multiapp, selezionare Kiosk **Kiosk Mode**  >  **multi-app**in modalità Kiosk.
1. Per iniziare a configurare il chiosco, selezionare **Aggiungi**.

I passaggi successivi variano a seconda del tipo di chiosco desiderato. Per altre informazioni, selezionare una delle opzioni seguenti:  

- [Chiosco Single-app](#mdmconfigsingle)
- [Chiosco multi-app](#mdmconfigmulti)

Per altre informazioni su come creare un profilo di configurazione Kiosk, vedere [impostazioni del dispositivo Windows 10 e Windows olografico per le aziende per l'esecuzione come chiosco dedicato con Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).

### <a id="mdmconfigsingle"></a>MDM, passaggio 3 (Single-app) &ndash;  configurare le impostazioni per un chiosco di app singole

Questa sezione riepiloga le impostazioni richieste da un chiosco per app singole. Per altri dettagli, vedere gli articoli seguenti:

- Per informazioni su come configurare un profilo di configurazione Kiosk in Intune, vedere [come configurare la modalità Kiosk con Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Per altre informazioni sulle impostazioni disponibili per i chioschi per le app singole in Intune, vedere [singoli chioschi di app a schermo intero](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Per altri servizi MDM, vedere le istruzioni nella documentazione del provider. Se devi usare una configurazione XML personalizzata per configurare un chiosco nel servizio MDM, [Crea un file XML che definisce la configurazione del chiosco](#ppkioskconfig).

1. Selezionare **User logon type**l'  >  **account utente locale**tipo di accesso utente e quindi immettere il nome utente dell'account locale (dispositivo) o dell'account Microsoft (MSA) che può accedere al chiosco.
   > [!NOTE]  
   > I tipi di account utente di **Autologon** non sono supportati in Windows olografico for business.
1. Selezionare **Application type**  >  **App Store**tipo applicazione e quindi selezionare un'app nell'elenco.

Il passaggio successivo consiste nell' [assegnare](#mdmassign) il profilo a un gruppo.

### <a id="mdmconfigmulti"></a>MDM, passaggio 3 (multi-app) &ndash; configurare le impostazioni per un chiosco multiapp

Questa sezione riepiloga le impostazioni necessarie per un chiosco multiapp. Per informazioni più dettagliate, vedere gli articoli seguenti:

- Per informazioni su come configurare un profilo di configurazione Kiosk in Intune, vedere [come configurare la modalità Kiosk con Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Per altre informazioni sulle impostazioni disponibili per i chioschi multimediali per più app in Intune, Vedi [chioschi](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks) multimediali per più app
- Per altri servizi MDM, vedere le istruzioni nella documentazione del provider. Se devi usare una configurazione XML personalizzata per configurare un chiosco nel servizio MDM, [Crea un file XML che definisce la configurazione del chiosco](#ppkioskconfig). Se si usa un file XML, assicurarsi di includere il [layout Start](#start-layout-for-hololens).  
- Puoi facoltativamente usare un layout Start personalizzato con Intune o altri servizi MDM. Per altre informazioni, vedere [avviare il file di layout per MDM (Intune e altri)](#start-layout-file-for-mdm-intune-and-others).

1. Selezionare **destinazione Windows 10 in dispositivi in modalità S**  >  **No**.  
   >[!NOTE]  
   > La modalità S non è supportata in Windows olografico for business.
1. Selezionare **tipo di accesso utente**  >  **Azure ad User o Group** o **User Access Type**  >  **HoloLens Visitor**e quindi aggiungere uno o più gruppi di utenti o account.  

   Solo gli utenti che appartengono ai gruppi o agli account specificati nel **tipo di accesso utente** possono usare l'esperienza Kiosk.

1. Selezionare una o più app usando le opzioni seguenti:
   - Per aggiungere un'app line-of-business caricata, selezionare **Aggiungi App Store** e quindi selezionare l'app desiderata.
   - Per aggiungere un'app specificando il relativo AUMID, seleziona **Aggiungi per AUMID** e quindi immetti il AUMID dell'app. [Vedere l'elenco di Aumid disponibili](#aumids)

Il passaggio successivo consiste nell' [assegnare](#mdmassign) il profilo a un gruppo.

### <a id="mdmassign"></a>MDM, passaggio 4 &ndash; assegnare il profilo di configurazione Kiosk a un gruppo

Usare la pagina **assegnazioni** del profilo di configurazione Kiosk per impostare il punto in cui si vuole distribuire la configurazione del chiosco. Nel caso più semplice, puoi assegnare il profilo di configurazione Kiosk a un gruppo che conterrà il dispositivo HoloLens quando il dispositivo si iscrive in MDM.

### <a id="mdmsingledeploy"></a>MDM, passaggio 5 (Single-app) &ndash; distribuire un chiosco Single-app

Quando si usa un sistema MDM, è possibile registrare il dispositivo in MDM durante la configurazione guidata. Dopo il completamento della configurazione, l'accesso al dispositivo è facile.

Durante la configurazione guidata seguire questa procedura:

1. Accedere usando l'account specificato nel profilo di configurazione Kiosk.
1. Registrare il dispositivo. Assicurarsi che il dispositivo venga aggiunto al gruppo a cui è assegnato il profilo di configurazione Kiosk.
1. Attendere che OOBE finisca, per l'App Store da scaricare e installare e per applicare i criteri. Quindi riavvia il dispositivo.

La volta successiva che si accede al dispositivo, l'app Kiosk dovrebbe iniziare automaticamente.

Se a questo punto la configurazione del chiosco non è visibile, [verificare lo stato delle assegnazioni](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a id="mdmmultideploy"></a>MDM, passaggio 5 (multi-app) &ndash; distribuire un chiosco multi-app

Quando si usa un sistema MDM, è possibile aggiungere il dispositivo al tenant di Azure AD e registrare il dispositivo in MDM durante la configurazione guidata. Se necessario, fornisci le informazioni di registrazione agli utenti in modo che siano disponibili durante il processo di configurazione.

> [!NOTE]  
> Se il profilo di configurazione di Kiosk è stato assegnato a un gruppo che contiene utenti, verificare che uno di questi account utente sia il primo account per accedere al dispositivo.

Durante la configurazione guidata seguire questa procedura:

1. Accedere usando l'account che appartiene al gruppo tipo di **accesso utente** .
1. Registrare il dispositivo.
1. Attendere le app che fanno parte del profilo di configurazione Kiosk per il download e l'installazione. Attendi inoltre che vengano applicati i criteri.  
1. Dopo aver completato la configurazione, è possibile installare altre app da Microsoft Store o da sideload. [App necessarie](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) per il gruppo a cui appartiene il dispositivo per l'installazione automatica.
1. Al termine dell'installazione, riavviare il dispositivo.

La volta successiva che si accede al dispositivo usando un account che appartiene al **tipo di accesso dell'utente**, l'app Kiosk dovrebbe essere avviata automaticamente.

Se a questo punto la configurazione del chiosco non è visibile, [verificare lo stato delle assegnazioni](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## Usare un pacchetto di provisioning per configurare un chiosco Single-app o multi-app

Per configurare la modalità Kiosk usando un pacchetto di provisioning, eseguire la procedura seguente.

1. [Creare un file XML che definisca la configurazione Kiosk](#ppkioskconfig), incluso un [layout Start](#start-layout-for-hololens).
2. [Aggiungere il file XML a un pacchetto di provisioning.](#ppconfigadd)
3. [Applicare il pacchetto di provisioning a HoloLens.](#ppapply)

### <a id="ppkioskconfig"></a>Pacchetto di provisioning, passaggio 1 &ndash; creare un file XML di configurazione Kiosk

Seguire [le istruzioni generali per creare un file XML di configurazione del chiosco per Windows Desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), ad eccezione di quanto segue:

- Non includere le applicazioni Windows classiche (Win32). HoloLens non supporta queste applicazioni.
- Usare il [formato XML di layout di inizio segnaposto](#start-layout-for-hololens) per HoloLens.
- Facoltativo: aggiungere l'accesso guest alla configurazione del chiosco

#### <a id="ppkioskguest"></a>Facoltativo: aggiungere l'accesso guest alla configurazione del chiosco

Nella sezione [ **configs** del file XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)puoi configurare un gruppo speciale denominato **visitatore** per consentire agli utenti di usare il chiosco. Quando il chiosco è configurato per supportare il gruppo speciale del **visitatore** , viene aggiunta un'opzione "**Guest**" alla pagina di accesso. L'account **Guest** non richiede una password e tutti i dati associati all'account vengono eliminati quando l'account si disconnette.

Per abilitare l'account **Guest** , aggiungere il frammento di codice seguente all'XML di configurazione del chiosco:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>Layout inizio segnaposto per HoloLens

Se si usa un [pacchetto di provisioning](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) per configurare un chiosco multiapp, la procedura richiede un layout Start. La personalizzazione del layout Start non è supportata in Windows Olografic for business. Dovrai quindi usare un layout Start segnaposto.

> [!NOTE]  
> Poiché un chiosco di una singola app avvia l'app Kiosk quando un utente accede, non usa un menu Start e non deve avere un layout di inizio.

> [!NOTE]  
> Se si usa [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) per configurare un chiosco multiapp, è possibile usare facoltativamente un layout Start. Per altre informazioni, Vedi [file di layout inizio segnaposto per MDM (Intune e altri)](#start-layout-file-for-mdm-intune-and-others).

Per il layout Start, aggiungere la sezione **StartLayout** seguente al file XML di provisioning del chiosco:

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>File di layout Start segnaposto per MDM (Intune e altri)

Salvare l'esempio seguente come file XML. Puoi usare questo file quando configuri il chiosco multiapp di Microsoft Intune (o in un altro servizio MDM che fornisce un profilo Kiosk).

> [!NOTE]
> Se è necessario usare un'impostazione personalizzata e una configurazione XML completa per configurare un chiosco nel servizio MDM, usare le [istruzioni per il layout iniziale per un pacchetto di provisioning](#start-layout-for-hololens).

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

### <a id="ppconfigadd"></a>Prov. pacchetto, passaggio 2 &ndash; aggiungere il file XML di configurazione del chiosco a un pacchetto di provisioning

1. Aprire [Windows Configuration designer](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Selezionare **provisioning avanzato**, immettere un nome per il progetto e quindi selezionare **Avanti**.
1. Selezionare **Windows 10 olografico**e quindi fare clic su **Avanti**.
1. Selezionare **fine**. Si aprirà l'area di lavoro per il pacchetto.
1. Selezionare **impostazioni di runtime**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. Nel riquadro centrale selezionare **Sfoglia** per individuare e selezionare il file XML di configurazione del chiosco creato.

   ![Screenshot del campo MultiAppAssignedAccessSettings in Progettazione configurazione di Windows](./images/multiappassignedaccesssettings.png)

1. **Facoltativo**. Se si vuole applicare il pacchetto di provisioning dopo la configurazione iniziale del dispositivo e un utente di amministratore è già disponibile nel dispositivo Kiosk, ignorare questo passaggio. Selezionare utenti account **delle impostazioni di runtime** &gt; **Accounts** &gt; **Users**e quindi creare un account utente. Specificare un nome utente e una password e quindi selezionare **UserGroup**  >  **amministratori**di UserGroup.  
  
     Usando questo account, è possibile visualizzare lo stato di provisioning e i registri.  
1. **Facoltativo**. Se si ha già un account non amministratore nel dispositivo Kiosk, ignorare questo passaggio. Selezionare utenti account **delle impostazioni di runtime** &gt; **Accounts** &gt; **Users**e quindi creare un account utente locale. Verificare che il nome utente sia lo stesso dell'account specificato nel codice XML di configurazione. Selezionare **UserGroup**  >  **utenti standard**di UserGroup.
1. Selezionare **File**  >  **Salva**file.
1. Selezionare **Esporta**  >  **pacchetto di provisioning**e quindi selezionare **proprietario**  >  **amministratore IT**. In questo articolo viene impostata la precedenza di questo pacchetto di provisioning superiore al provisioning dei pacchetti applicati a questo dispositivo da altre origini.
1. Seleziona **Avanti**.
1. Nella pagina di **sicurezza del pacchetto di provisioning** selezionare un'opzione di sicurezza.
   > [!IMPORTANT]  
   > Se si seleziona **Abilita firma del pacchetto**, è necessario selezionare anche un certificato valido da usare per la firma del pacchetto. A questo scopo, selezionare **Sfoglia** e selezionare il certificato che si vuole usare per firmare il pacchetto.
   
   > [!CAUTION]  
   > Non selezionare **Abilita crittografia pacchetto**. Nei dispositivi HoloLens questa impostazione causa un errore di provisioning.
1. Seleziona **Avanti**.
1. Specificare il percorso di output in cui si vuole che venga compilato il pacchetto di provisioning. Per impostazione predefinita, Progettazione configurazione di Windows usa la cartella di progetto come percorso di output. Se si vuole modificare la posizione di output, selezionare **Sfoglia**. Al termine, selezionare **Avanti**.
1. Selezionare **Compila** per iniziare a creare il pacchetto. La compilazione del pacchetto di provisioning non richiede molto tempo. La pagina di compilazione Visualizza le informazioni sul progetto e la barra di stato indica lo stato della compilazione.

### <a id="ppapply"></a>Pacchetto di provisioning, passaggio 3 &ndash; applicare il pacchetto di provisioning a HoloLens

L'articolo "Configura HoloLens usando un pacchetto di provisioning" fornisce istruzioni dettagliate per applicare il pacchetto di provisioning nelle circostanze seguenti:

- È possibile [applicare inizialmente un pacchetto di provisioning a HoloLens durante l'installazione](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- È anche possibile [applicare un pacchetto di provisioning a HoloLens dopo l'installazione](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).

## Usare Windows Device Portal per configurare un chiosco di app singole

Per configurare la modalità Kiosk tramite Windows Device Portal, eseguire la procedura seguente.

> [!IMPORTANT]
> La modalità Kiosk è disponibile solo se il dispositivo è installato [Windows olografico per le aziende](hololens1-upgrade-enterprise.md) .

1. [Configurare il dispositivo HoloLens per l'uso di Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Device Portal è un server Web in HoloLens a cui è possibile connettersi da un browser Web nel PC.

    > [!CAUTION]
    > Quando si configura HoloLens per l'uso di Device Portal, è necessario abilitare la modalità sviluppatore nel dispositivo. La modalità sviluppatore in un dispositivo con Windows olografico per le aziende consente di caricare le app con caricamento laterale. Tuttavia, questa impostazione crea un rischio che un utente possa installare app che non sono state certificate da Microsoft Store. Gli amministratori possono bloccare la possibilità di abilitare la modalità sviluppatore usando l'impostazione di **sblocco ApplicationManagement/AllowDeveloper** nel [CSP dei criteri](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider). [Scopri di più sulla Modalità sviluppatore.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. In un computer connettersi al HoloLens tramite [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) o [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Effettua una delle seguenti operazioni:
   - Se ci si connette a Windows Device Portal per la prima volta, [creare un nome utente e una password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Immettere il nome utente e la password configurati in precedenza.

    > [!TIP]
    > Se viene visualizzato un errore di certificato nel browser, seguire le seguenti [procedure per la risoluzione dei problemi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. In Windows Device Portal selezionare **modalità Kiosk**.

1. Selezionare **Abilita modalità Kiosk**, selezionare un'app da eseguire all'avvio del dispositivo e quindi selezionare **Salva**.

    ![Modalità tutto schermo](images/kiosk.png)
1. Riavviare HoloLens. Se la pagina del portale del dispositivo è ancora aperta, è possibile selezionare **Riavvia** nella parte superiore della pagina.

## Altre informazioni

Guarda come configurare un chiosco usando un pacchetto di provisioning.  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
