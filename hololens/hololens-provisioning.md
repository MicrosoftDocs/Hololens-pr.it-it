---
title: Configurare HoloLens usando un pacchetto di provisioning (HoloLens)
description: Il provisioning di Windows rende molto semplice per gli amministratori IT configurare i dispositivi per gli utenti finali senza la creazione di immagini.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d9a0901a916ec33c076eeae33b680406a45f7feefe82442da1f346e78bc9b383
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663838"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Configurare HoloLens usando un pacchetto di provisioning

[Windows provisioning consente](/windows/configuration/provisioning-packages/provisioning-packages) agli amministratori IT di configurare facilmente i dispositivi degli utenti finali senza creare immagini. Windows Progettazione configurazione è uno strumento per la configurazione di immagini e impostazioni di runtime che vengono quindi integrate nei pacchetti di provisioning.

Alcune delle configurazioni HoloLens che è possibile applicare in un pacchetto di provisioning includono le seguenti:

- Eseguire l'aggiornamento [a Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Configurare un account locale
- Configurare una connessione Wi-Fi
- Applicare certificati al dispositivo
- Abilitare la modalità sviluppatore
- Configurare la modalità tutto schermo seguendo le [istruzioni dettagliate](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

## <a name="provisioning-package-hololens-wizard"></a>Procedura guidata di provisioning HoloLens pacchetto

La HoloLens guidata consente di configurare le impostazioni seguenti in un pacchetto di provisioning:

- Eseguire l'aggiornamento all'edizione Enterprise

    > [!NOTE]
    > Questa opzione deve essere usata solo per HoloLens dispositivi di prima generazione. Impostazioni in un pacchetto di provisioning vengono applicati solo se il pacchetto di provisioning include una licenza di aggiornamento dell'edizione a Windows Holographic for Business o se il dispositivo è già stato aggiornato [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- Configurare la HoloLens prima esperienza (Configurazione guidata)
- Configurare la rete Wi-Fi rete
- Registrare il dispositivo in Azure Active Directory o creare un account locale
- Aggiungere certificati
- Abilitare la modalità sviluppatore
- Configurare la modalità tutto schermo seguendo le [istruzioni dettagliate](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

> [!WARNING]
> È necessario eseguire Windows Progettazione configurazione in Windows 10 per configurare Azure Active Directory registrazione usando una delle procedure guidate.

I pacchetti di provisioning possono includere istruzioni e criteri di gestione, connessioni di rete personalizzate e criteri e altro ancora.

> [!TIP]
> Usare la procedura guidata desktop per creare un pacchetto con le impostazioni comuni, quindi passare all'editor avanzato per aggiungere altre impostazioni, app, criteri e così via.

## <a name="steps-for-creating-provisioning-packages"></a>Passaggi per la creazione di pacchetti di provisioning

1. **Opzione 1: da** [Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Sono incluse HoloLens 2 funzionalità.
2. **Opzione 2:** [da Windows Assessment and Deployment Kit (ADK) per Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Se si installa Windows Progettazione configurazione da Windows ADK, selezionare **Progettazione** configurazione nella finestra di dialogo Selezionare le funzionalità **da** installare. Questa opzione non include HoloLens 2 funzionalità.

> [!NOTE]
> Se si è in grado di usare un PC offline che richiede l'accesso a Progettazione configurazione di Windows, seguire le istruzioni per l'installazione dell'app offline (hololens-recovery.md#downloading-arc-without-using-the-app-store) per Advanced Recovery Companion. Selezionare Windows Progettazione configurazione. 

### <a name="2-create-the-provisioning-package"></a>2. Creare il pacchetto di provisioning

Usare lo Windows Progettazione configurazione per creare un pacchetto di provisioning.

1. Aprire progettazione Windows (per impostazione predefinita, %windir%\Programmi (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Selezionare **Provisioning HoloLens dispositivi .**

   ![Progettazione immagine e configurazione - Opzioni per Start](images/icd-create-options-1703.png)

3. Assegnare un nome al progetto e **selezionare Fine.**

4. Leggere le istruzioni nella **pagina Introduzione** e selezionare **Avanti.** Le pagine per il provisioning desktop illustrano i passaggi seguenti.
  
> [!IMPORTANT]
> Quando crei un pacchetto di provisioning potresti includere informazioni riservate nei file di progetto e nel file del pacchetto di provisioning (con estensione PPKG). Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati. Devi archiviare i file del progetto in un luogo sicuro ed eliminare i file del progetto quando non sono più necessari.

### <a name="configure-settings"></a>Configurare le impostazioni

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Individuare e selezionare il file di licenza Enterprise per aggiornare l'HoloLens edizione.</br></br>È anche possibile attivare <strong>o disattivare</strong> <strong>Sì o No</strong> per nascondere parti della prima esperienza.</br></br>Per configurare il dispositivo senza la necessità di connettersi a una rete Wi-Fi, impostare Skip Wi-Fi setup (Ignora Wi-Fi <strong>configurazione)</strong> su <strong>On (Attivato).</strong></br></br>Selezionare un'area e un fuso orario in cui verrà usato il dispositivo. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>In questa sezione è possibile immettere i dettagli della rete Wi-Fi wireless a cui il dispositivo deve connettersi automaticamente. A tale scopo, selezionare Su <strong>,</strong>immettere l'SSID, il tipo di rete (<strong>Open</strong> o <strong>WPA2-Personal</strong>) e (se <strong>WPA2-Personal</strong>) la password per la rete wireless.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>È possibile registrare il dispositivo Azure Active Directory o creare un account locale nel dispositivo</br></br>Prima di usare una procedura guidata Windows Configuration Designer per configurare la registrazione Azure AD in blocco, configurare <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">Azure AD'aggiunta all'organizzazione.</a> Il <strong>numero massimo di dispositivi per</strong> impostazione utente nel tenant di Azure AD determina quante volte è possibile usare il token in blocco che si ottiene nella procedura guidata. Per registrare il dispositivo in Azure AD, selezionare l'opzione e immettere un nome descrittivo per il token in blocco che verrà visualizzato tramite la procedura guidata. Impostare una data di scadenza per il token (il massimo è di 30 giorni dalla data in cui si ottiene il token). Selezionare <strong>Get bulk token (Ottieni token in blocco).</strong> Nella finestra <strong>Let&#39;'accesso</strong> immettere un account che abbia le autorizzazioni per aggiungere un dispositivo Azure AD e quindi la password. Selezionare <strong>Accept (Accetta)</strong> Windows Configuration Designer (Progettazione configurazione) per le autorizzazioni necessarie. </br></br>Per creare un account locale, selezionare l'opzione e immettere un nome utente e una password. </br></br><strong>Importante:</strong> <br />(Solo Windows 10 versione 1607) Se si crea un account locale nel pacchetto di provisioning, è necessario modificare la password usando l'app <strong>Impostazioni</strong> ogni 42 giorni. Se la password non viene modificata entro tale periodo, l'account potrebbe essere bloccato ed è impossibile accedervi.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Per effettuare il provisioning del dispositivo con un certificato, fare clic <strong>su Aggiungi un certificato.</strong> Immettere un nome per il certificato, quindi individuare e selezionare il certificato da usare.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Selezionare <strong>Sì</strong> o <strong>No</strong> per abilitare la modalità sviluppatore nel HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Ulteriori informazioni sulla modalità sviluppatore.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Non impostare una password per proteggere il pacchetto di provisioning. Se il pacchetto di provisioning è protetto da una password, il provisioning HoloLens dispositivo avrà esito negativo.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Al termine, selezionare **Crea**. Sono necessari solo alcuni secondi. Quando il pacchetto viene compilato, il percorso in cui è archiviato viene visualizzato come collegamento ipertestuale nella parte inferiore della pagina.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Creare un pacchetto di provisioning per HoloLens usando il provisioning avanzato

> [!NOTE]
> Un pacchetto di provisioning creato in **Provisioning** avanzato non deve includere una licenza di aggiornamento dell'edizione per Windows Holographic for Business per applicarlo correttamente a un HoloLens (prima generazione). [Altre informazioni su Windows Holographic for Business per HoloLens (prima generazione).](hololens1-upgrade-enterprise.md)

1. Nella pagina Windows iniziale di Progettazione configurazione selezionare **Provisioning avanzato.**
2. Nella finestra **Immetti dettagli progetto**, specifica un nome e la posizione del progetto. Facoltativamente, immetti una breve descrizione del progetto.

3. Selezionare **Avanti**.

4. Nella finestra **Scegliere le impostazioni da visualizzare e** configurare selezionare **Windows 10 Holographic** e quindi selezionare **Avanti.**

5. Selezionare **Fine**.

6. Espandere **Impostazioni di** runtime e personalizzare il pacchetto usando una delle impostazioni [descritte più avanti in questo articolo.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Solo Windows 10 versione 1607) Se si crea un account locale nel pacchetto di provisioning, è necessario modificare la password usando l'app **Impostazioni** ogni 42 giorni. Se la password non viene modificata entro tale periodo, l'account potrebbe essere bloccato ed è impossibile accedervi. Se l'account utente viene bloccato, è necessario [eseguire un ripristino completo del dispositivo](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).

7. Selezionare **File**  >  **Salva.**

8. Leggere l'avviso che indica che i file di progetto possono contenere informazioni riservate e selezionare **OK.**

    > [!IMPORTANT]
    > Quando crei un pacchetto di provisioning potresti includere informazioni riservate nei file di progetto e nel file del pacchetto di provisioning (con estensione PPKG). Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati. Devi archiviare i file del progetto in un luogo sicuro ed eliminare i file del progetto quando non sono più necessari.
    
9. Selezionare **Esporta**  >  **pacchetto di provisioning.**

10. Impostare **Proprietario su** Amministratore **IT.** In questo modo la precedenza di questo pacchetto di provisioning viene impostata su un valore superiore rispetto al provisioning dei pacchetti applicati a questo dispositivo da altre origini. Selezionare **Avanti**.

11. Imposta un valore per **Versione pacchetto**.

    > [!TIP]
    > Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.

12. In **Selezionare i dettagli di sicurezza per il pacchetto di provisioning** selezionare **Avanti.**

    > [!WARNING]
    > Se si crittografa il pacchetto di provisioning, il provisioning HoloLens dispositivo avrà esito negativo.  

13. Selezionare **Avanti** per specificare il percorso di output in cui si vuole inserire il pacchetto di provisioning dopo la compilazione. Per impostazione predefinita, Windows Progettazione configurazione usa la cartella del progetto come percorso di output.

    Facoltativamente, è possibile selezionare **Sfoglia per** modificare il percorso di output predefinito.

14. Selezionare **Avanti**.

15. Selezionare **Compila** per iniziare a compilare il pacchetto. Le informazioni del progetto vengono visualizzate nella pagina di compilazione e la barra di stato indica lo stato della compilazione.

16. Al termine della compilazione, selezionare **Fine.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Applicare un pacchetto di provisioning al HoloLens durante l'installazione

HoloLens 2 dispositivi in Windows Holographic, versione 2004 o build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) o successiva, possono usare un'unità USB per applicare un pacchetto di provisioning. È sufficiente copiare il file con estensione ppkg nella radice dell'unità USB. I pacchetti di provisioning verranno applicati solo se sono nella radice dell'unità USB. Più pacchetti di provisioning presenti verranno applicati in sequenza.

HoloLens 2 dispositivi Windows [Holographic versione 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o successiva hanno funzionalità più nuove per semplificare e semplificare questo processo rendendolo automatico. Esaminare le sezioni seguenti:

- [Avvio automatico del provisioning da USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Confermare automaticamente i pacchetti di provisioning nella Configurazione automatica](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Provisioning automatico senza usare l'interfaccia utente](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Usare il cavo USB per connettere il dispositivo a un PC (o a un'unità USB per HoloLens 2 come indicato in precedenza) e quindi avviare il dispositivo. Non continuare oltre la **pagina Primo momento con interazione** della Modalità fuori sistema.   
    - Nella HoloLens (prima generazione) questa pagina contiene una casella blu. 
    - Nella HoloLens 2 questa pagina contiene il colibrì.

2. Premi brevemente e rilascia i pulsanti di **abbassamento del volume** e **Alimentazione** simultaneamente. 

3. HoloLens visualizzato come dispositivo in Esplora file nel PC.

4. In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.

5. Premere e rilasciare brevemente i **pulsanti Volume Down** (Volume in basso) e **Power** (Alimentazione) contemporaneamente nella pagina First interactable moment (Primo momento **intervienibile)** di OOBE.

6. Il dispositivo chiede se si considera attendibile il pacchetto e si vuole applicarlo. Confermare che consideri attendibile il pacchetto.

7. Potrai vedere se il pacchetto è stato applicato correttamente o meno. Se l'applicazione non è riuscita, è possibile correggere il pacchetto e riprovare. Se ha avuto esito positivo, continua con la Configurazione guidata.

> [!NOTE]
> Se il dispositivo è stato acquistato prima di agosto 2016, sarà necessario accedere al dispositivo usando un account Microsoft, ottenere l'aggiornamento più recente del sistema operativo e quindi reimpostare il sistema operativo per applicare il pacchetto di provisioning.

### <a name="auto-launch-provisioning-from-usb"></a>Avvio automatico del provisioning da USB

- Processi automatizzati che consentono una minore interazione da parte dell'utente, quando durante la Configurazione automatica vengono usate unità USB con pacchetti di provisioning.

Prima di questa versione, gli utenti dovevano avviare manualmente la schermata di provisioning durante la Configurazione manuale per eseguire il provisioning usando una combinazione di pulsanti. Gli utenti possono ora ignorare la combinazione di pulsanti usando un pacchetto di provisioning in un'unità di archiviazione USB. 

1. Collegare l'unità USB con il pacchetto di provisioning durante il primo momento di interazione della Configurazione guidata
1. Quando il dispositivo è pronto per il provisioning, viene aperta automaticamente la richiesta con la pagina di provisioning. 

Nota: se un'unità USB viene lasciata collegata durante l'avvio del dispositivo, la Configurazione guidata enumera il dispositivo di archiviazione USB esistente, nonché verifica la connessione di altri dispositivi.

Leggere le informazioni [sull'applicazione dei pacchetti di provisioning durante la Configurazione manuale.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confermare automaticamente i pacchetti di provisioning nella Configurazione automatica
- Processo automatizzato che consente una minore interazione dell'utente. Quando viene visualizzata la pagina Pacchetto di provisioning, vengono applicati automaticamente tutti i pacchetti elencati.

Quando viene visualizzata la schermata principale del provisioning, la Configurazione automatica del sistema operativo esegue il conto alla rovescia di 10 secondi prima di avviare automaticamente l'applicazione di tutti i pacchetti di provisioning. Gli utenti possono comunque confermare o annullare entro 10 secondi dalla verifica dei pacchetti previsti.

### <a name="automatic-provisioning-without-using-ui"></a>Provisioning automatico senza usare l'interfaccia utente
- Processi automatici combinati per ridurre le interazioni dei dispositivi per il provisioning. 

Combinando l'avvio automatico del provisioning dai dispositivi USB e la conferma automatica dei pacchetti di provisioning, un utente può effettuare automaticamente il provisioning dei dispositivi HoloLens 2 senza usare l'interfaccia utente del dispositivo o addirittura senza dover usare il dispositivo. È possibile continuare a usare la stessa unità USB e lo stesso pacchetto di provisioning per più dispositivi. Ciò è utile per la distribuzione di più dispositivi contemporaneamente nella stessa area. 

1. [Creare un pacchetto di provisioning](hololens-provisioning.md) usando Windows Progettazione [configurazione](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copiare il pacchetto in un'unità di archiviazione USB.
1. [Eseguire il flash HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) alla [build 19041.1361 o versione più recente.](https://aka.ms/hololens2previewdownload) 
1. Quando [Advanced Recovery Companion ha](https://www.microsoft.com/store/productId/9P74Z35SFRS8) completato il flashing del dispositivo, scollegare il cavo USB-C. 
1. Collegare l'unità USB al dispositivo.
1. Quando il HoloLens 2 viene avviato nella Configurazione guidata, rileverà automaticamente il pacchetto di provisioning nell'unità USB e avvierà la pagina di provisioning.
1. Dopo 10 secondi il dispositivo applicherà automaticamente il pacchetto di provisioning. 

Il dispositivo è ora configurato e verrà visualizzata la schermata Provisioning completato.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Applicare/rimuovere un pacchetto di provisioning da HoloLens dopo l'installazione

> [!NOTE]
> Questi passaggi si applicano a tutti HoloLens 2 e dispositivi HoloLens (prima generazione) in Windows Holographic, versione 1809 e successive.

Nel PC seguire questa procedura:
1. Creare un pacchetto di provisioning come descritto in [Creare un pacchetto di provisioning](hololens-provisioning.md)per HoloLens usando la HoloLens guidata .
2. Connessione il HoloLens dispositivo a un PC usando un cavo USB. HoloLens visualizzato come dispositivo in Esplora file nel PC.
3. Trascinare e rilasciare il pacchetto di provisioning nella cartella Documenti nel HoloLens.

Nel HoloLens seguire questa procedura:
1. Passare a **Impostazioni** > **Account** > **Accedi all'azienda o all'istituto di istruzione**. 
2. In **Impostazioni Impostazioni** selezionare Aggiungi o rimuovi un pacchetto di **provisioning.**
3. Nella pagina successiva selezionare Aggiungi un pacchetto **per** avviare la selezione file e selezionare il pacchetto di provisioning. Se la cartella è vuota, assicurarsi di selezionare **Questo dispositivo e** quindi **Documenti.**

Dopo l'applicazione, il pacchetto viene visualizzato nell'elenco **Pacchetti installati**. Per visualizzare i dettagli del pacchetto o rimuoverlo dal dispositivo, selezionare il pacchetto elencato.

## <a name="what-you-can-configure"></a>Cosa è possibile configurare

I pacchetti di provisioning di pacchetti utilizzano i provider di servizi di configurazione (CSP). Se non hai familiarità con questo tipo di provider, vedi [Introduzione ai provider di servizi di configurazione (CSP) per i professionisti IT](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

In progettazione Windows, quando si crea un pacchetto di provisioning per Windows Holographic, le impostazioni **in** Personalizzazioni disponibili si basano sui CSP supportati in [Windows Holographic.](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) La tabella seguente descrive le impostazioni che potresti voler configurare per HoloLens.

![Impostazioni di runtime comuni per HoloLens](images/icd-settings.png)

| Impostazione | Descrizione |
| --- | --- |
| **Certificati** | Distribuire un certificato in HoloLens.  |
| **ConnectivityProfiles** | Distribuire un profilo Wi-Fi in HoloLens.   |
| **EditionUpgrade** | [Eseguire l'aggiornamento Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Criteri** | Consentire o impedire la modalità sviluppatore in HoloLens. [Criteri supportati da Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Installazione dell'app tramite il pacchetto di provisioning

Le app possono essere installate tramite pacchetti di provisioning HoloLens 2 dispositivi. In questo modo è possibile usare un pacchetto facilmente riutilizzabile per distribuire le app. Leggere le istruzioni complete per la [distribuzione di app tramite provisioning di pacchetti](app-deploy-provisioning-package.md).  

> [!NOTE]
> HoloLens (prima generazione) ha un supporto limitato per l'installazione di app (**UniversalAppInstall**) tramite un pacchetto di provisioning. HoloLens dispositivi di prima generazione supportano solo l'installazione di un'app tramite PPKG solo durante la Configurazione guidata e solo con installazioni del contesto utente.
