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
ms.date: 03/10/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c10f07a6caeae6f2e8ace41d345c3ad11901621a
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052645"
---
# Configurare HoloLens usando un pacchetto di provisioning

[Windows provisioning](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) consente agli amministratori IT di configurare i dispositivi per gli utenti finali senza immagini. Windows Configuration designer è uno strumento per configurare le immagini e le impostazioni di runtime che vengono quindi integrate in pacchetti di provisioning.

Alcune delle configurazioni di HoloLens che è possibile applicare in un pacchetto di provisioning includono le seguenti:

- Eseguire l'aggiornamento a Windows olografico for business [qui](hololens1-upgrade-enterprise.md)
- Configurare un account locale
- Configurare una connessione Wi-Fi
- Applicare certificati al dispositivo
- Abilitare la modalità sviluppatore
- Configurare la modalità Kiosk (le istruzioni dettagliate per la configurazione della modalità Kiosk possono essere trovate [qui](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

## Creazione guidata pacchetto di provisioning HoloLens

La procedura guidata di HoloLens consente di configurare le impostazioni seguenti in un pacchetto di provisioning:

- Eseguire l'aggiornamento a Enterprise Edition

    > [!NOTE]
    > Questa operazione deve essere usata solo per i dispositivi HoloLens 1st Gen. Le impostazioni in un pacchetto di provisioning vengono applicate solo se il pacchetto di provisioning include una licenza per l'aggiornamento a Windows olografico per le aziende o se [il dispositivo è già stato aggiornato a Windows olografico for business](hololens1-upgrade-enterprise.md).

- Configurare la prima esperienza di HoloLens (OOBE)
- Configurare la rete Wi-Fi
- Registrare il dispositivo in Azure Active Directory oppure creare un account locale
- Aggiungere certificati
- Abilitare la modalità sviluppatore
- Configurare la modalità Kiosk. Le istruzioni dettagliate per la configurazione della modalità Kiosk possono essere trovate [qui](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

> [!WARNING]
> Devi eseguire Progettazione configurazione di Windows in Windows 10 per configurare la registrazione di Azure Active Directory utilizzando una delle procedure guidate.

I pacchetti di provisioning possono includere istruzioni e criteri di gestione, connessioni e criteri di rete personalizzati e altro ancora.

> [!TIP]
> Usa la procedura guidata desktop per creare un pacchetto con le impostazioni comuni, quindi passa all'editor avanzato per aggiungere altre impostazioni, app, criteri e così via.

## Procedura per la creazione di pacchetti di provisioning

1. **Opzione 1:** [da Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Questo include le funzionalità di HoloLens 2.
2. **Opzione 2:** [da Windows Assessment and Deployment Kit (ADK) per Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Se si installa Windows Configuration designer da Windows ADK, selezionare **progettazione configurazione** nella finestra di dialogo **selezionare le caratteristiche da installare** . Questa opzione non include le funzionalità di HoloLens 2.

> [!NOTE]
> Se si è certi che si utilizzerà un PC offline che deve avere accesso a Windows Configuration designer, seguire [l'installazione dell'](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) app offline per il compagno di ripristino avanzato, ma per rendere Windows Confiugration Desinger invece la selezione. 

### 2. creare il pacchetto di provisioning

Utilizza lo strumento Progettazione configurazione di Windows per creare un pacchetto di provisioning.

1. Apri Progettazione configurazione di Windows (per impostazione predefinita, %windir%\Programmi (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Selezionare **provision HoloLens Devices**.

   ![Progettazione immagine e configurazione - Opzioni per Start](images/icd-create-options-1703.png)

3. Assegnare un nome al progetto e selezionare **fine**.

4. Leggere le istruzioni nella pagina **Guida introduttiva** e selezionare **Avanti**. Le pagine per il provisioning desktop consentono di eseguire i passaggi seguenti.
  
> [!IMPORTANT]
> Quando crei un pacchetto di provisioning potresti includere informazioni riservate nei file di progetto e nel file del pacchetto di provisioning (con estensione PPKG). Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati. Devi archiviare i file del progetto in un luogo sicuro ed eliminare i file del progetto quando non sono più necessari.

### Configurare le impostazioni

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Individuare e selezionare il file di licenza aziendale per aggiornare la HoloLens Edition.</br></br>È anche possibile attivare <strong> o disattivare Sì </strong> o <strong> No </strong> per nascondere parti della prima esperienza.</br></br>Per configurare il dispositivo senza la necessità di connettersi a una rete Wi-Fi, attivare o disattivare la <strong> configurazione Wi-Fi </strong> <strong> </strong> .</br></br>Selezionare un'area geografica e un fuso orario in cui verrà usato il dispositivo. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>In questa sezione è possibile immettere i dettagli della rete wireless Wi-Fi a cui il dispositivo deve connettersi automaticamente. A tale scopo, selezionare <strong> attivata </strong> , immettere il SSID, il tipo di rete ( <strong> aperto </strong> o <strong> WPA2-personale </strong> ) e (se <strong> WPA2-personale </strong> ) la password per la rete wireless.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>È possibile registrare il dispositivo in Azure Active Directory oppure creare un account locale nel dispositivo</br></br>Prima di utilizzare una procedura guidata di Progettazione configurazione di Windows per configurare la registrazione in blocco in Azure AD, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">configura l'aggiunta di Azure AD nella tua organizzazione</a>. L'impostazione <strong>Numero massimo di dispositivi per utente</strong> nel tenant di Azure AD determina quante volte può essere utilizzato il token di massa recuperato nella procedura guidata. Per registrare il dispositivo in Azure AD, seleziona l'opzione corrispondente e immetti un nome descrittivo per il token di massa che otterrai utilizzando la procedura guidata. Imposta una data di scadenza per il token (il valore massimo è di 30 giorni dalla data di recupero del token). Selezionare <strong> Ottieni token in blocco </strong> . Nella <strong> finestra Let&#39;s è stato effettuato l'accesso </strong> , immettere un account che disponga delle autorizzazioni per l'aggiunta di un dispositivo a Azure ad e quindi la password. Selezionare <strong> accetta </strong> per assegnare a Windows Configuration designer le autorizzazioni necessarie. </br></br>Per creare un account locale, seleziona tale opzione e immetti un nome utente e una password. </br></br><strong>Importante:</strong> <br />(Solo per Windows 10 versione 1607) Se crei un account locale nel pacchetto di provisioning, devi modificare la password usando l' <strong> </strong> app impostazioni ogni 42 giorni. Se la password non viene modificata entro tale periodo, l'account potrebbe essere bloccato ed è impossibile accedervi.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Per effettuare il provisioning del dispositivo con un certificato, fai clic su <strong>Aggiungi certificato</strong>. Immetti un nome per il certificato, quindi individua e seleziona il certificato da utilizzare.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Attivare <strong> o disattivare Sì </strong> o <strong> No </strong> per abilitare la modalità sviluppatore in HoloLens. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Scopri di più sulla Modalità sviluppatore.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br>Non impostare una password per proteggere il pacchetto di provisioning. Se il pacchetto di provisioning è protetto da una password, il provisioning del dispositivo HoloLens non riuscirà.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Al termine, selezionare **Crea**. L'operazione richiede solo pochi secondi. Al termine della compilazione del pacchetto, il percorso in cui è archiviato il pacchetto è visualizzato come collegamento ipertestuale nella parte inferiore della pagina.

### 3. creare un pacchetto di provisioning per HoloLens con il provisioning avanzato

> [!NOTE]
> Un pacchetto di provisioning creato in **provisioning avanzato** non deve includere una licenza di aggiornamento per l'edizione di Windows olografico per le aziende per applicarsi con successo a un HoloLens (1a generazione). [Per altre informazioni, vedere Windows olografic for business per HoloLens (1st Gen)](hololens1-upgrade-enterprise.md).

1. Nella pagina iniziale di Progettazione configurazione di Windows seleziona **Provisioning avanzato**.
2. Nella finestra **Immetti dettagli progetto**, specifica un nome e la posizione del progetto. Facoltativamente, immetti una breve descrizione del progetto.

3. Seleziona **Avanti**.

4. Nella finestra **scegliere le impostazioni da visualizzare e configurare** selezionare **Windows 10 olografico**e quindi fare clic su **Avanti**.

5. Selezionare **fine**.

6. Espandere **impostazioni di runtime** e personalizzare il pacchetto usando le impostazioni [descritte più avanti in questo articolo](#what-you-can-configure).

    > [!IMPORTANT]
    > (Solo per Windows 10 versione 1607) Se crei un account locale nel pacchetto di provisioning, devi modificare la password usando l'app **Impostazioni** ogni 42 giorni. Se la password non viene modificata entro tale periodo, l'account potrebbe essere bloccato ed è impossibile accedervi. Se l'account utente viene bloccato, è necessario [eseguire un ripristino completo del dispositivo](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).

7. Selezionare **File**  >  **Salva**file.

8. Leggere l'avviso che i file di progetto possono contenere informazioni riservate e scegliere **OK**.

    > [!IMPORTANT]
    > Quando crei un pacchetto di provisioning potresti includere informazioni riservate nei file di progetto e nel file del pacchetto di provisioning (con estensione PPKG). Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati. Devi archiviare i file del progetto in un luogo sicuro ed eliminare i file del progetto quando non sono più necessari.
    
9. Selezionare **Esporta**  >  **pacchetto di provisioning**.

10. Modificare il **proprietario** dell' **amministratore IT**. In questo articolo viene impostata la precedenza di questo pacchetto di provisioning superiore ai pacchetti di provisioning applicati a questo dispositivo da altre origini. Seleziona **Avanti**.

11. Imposta un valore per **Versione pacchetto**.

    > [!TIP]
    > Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.

12. Nella finestra **di dialogo Seleziona dettagli di sicurezza per il pacchetto di provisioning**selezionare **Avanti**.

    > [!WARNING]
    > Se effettui la crittografia del pacchetto di provisioning, il provisioning di HoloLens non riuscirà.  

13. Selezionare **Avanti** per specificare la posizione di output in cui si vuole inserire il pacchetto di provisioning dopo la compilazione. Per impostazione predefinita, Progettazione configurazione di Windows usa la cartella di progetto come percorso di output.

    Facoltativamente, è possibile selezionare **Sfoglia** per modificare la posizione di output predefinita.

14. Seleziona **Avanti**.

15. Selezionare **Compila** per iniziare a creare il pacchetto. Le informazioni del progetto vengono visualizzate nella pagina di compilazione e la barra di stato indica lo stato della compilazione.

16. Al termine della compilazione, selezionare **fine**.

<span id="apply" />

## Applicare un pacchetto di provisioning a HoloLens durante l'installazione

HoloLens 2 dispositivi nella build [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) o versione successiva, possono usare un'unità USB per applicare un pacchetto di provisioning. Basta copiare il file con estensione ppkg nella radice dell'unità USB. I pacchetti di provisioning verranno applicati solo se sono nella radice dell'unità USB. Il pacchetto di provisioning multiplo presente verrà applicato in sequenza.

1. Usare il cavo USB per connettere il dispositivo a un PC (o un'unità USB per HoloLens 2 come accennato in precedenza), quindi avviare il dispositivo. Non continuare oltre la prima pagina del **momento interattivo** di Oobe.   
    - In HoloLens (1a generazione) Questa pagina contiene una casella blu. 
    - In HoloLens 2 Questa pagina contiene il colibrì.

2. Premi brevemente e rilascia i pulsanti di **abbassamento del volume** e **Alimentazione** simultaneamente. 

3. HoloLens viene visualizzato come dispositivo in Esplora file nel PC.

4. In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.

5. Premere brevemente e rilasciare di nuovo contemporaneamente i pulsanti **volume giù** e **Power** mentre nella **prima pagina del momento interattivo** della configurazione guidata.

6. Il dispositivo chiede se si ritiene attendibile il pacchetto e si desidera applicarlo. Confermare che consideri attendibile il pacchetto.

7. Potrai vedere se il pacchetto è stato applicato correttamente o meno. Se l'applicazione non è riuscita, è possibile correggere il pacchetto e riprovare. Se ha avuto esito positivo, continua con la Configurazione guidata.

> [!NOTE]
> Se il dispositivo è stato acquistato prima di agosto 2016, è necessario accedere al dispositivo usando un account Microsoft, ottenere l'aggiornamento più recente del sistema operativo e quindi reimpostare il sistema operativo per applicare il pacchetto di provisioning.

## Applicare un pacchetto di provisioning a HoloLens dopo l'installazione

> [!NOTE]
> Questa procedura si applica solo a Windows 10, versione 1809.

Nel PC seguire questa procedura:
1. Creare un pacchetto di provisioning come descritto in [creare un pacchetto di provisioning per HoloLens usando la procedura guidata HoloLens](hololens-provisioning.md).
2. Connettere il dispositivo HoloLens a un PC usando un cavo USB. HoloLens viene visualizzato come dispositivo in Esplora file nel PC.
3. Trascinare e rilasciare il pacchetto di provisioning nella cartella documenti in HoloLens.

Nella HoloLens seguire questa procedura:
1. Accedere a **Settings**  >  **account**di  >  **accesso o a scuola**. 
2. In **impostazioni correlate**selezionare **Aggiungi o Rimuovi un pacchetto di provisioning**.
3. Nella pagina successiva selezionare **Aggiungi un pacchetto** per avviare la selezione file e selezionare il pacchetto di provisioning. Se la cartella è vuota, verificare di aver selezionato **questo dispositivo** e selezionare **documenti**.

Dopo aver applicato il pacchetto, viene visualizzato nell'elenco dei **pacchetti installati**. Per visualizzare i dettagli del pacchetto o per rimuovere il pacchetto dal dispositivo, selezionare il pacchetto elencato.

## Configurazioni possibili

I pacchetti di provisioning di pacchetti utilizzano i provider di servizi di configurazione (CSP). Se non hai familiarità con questo tipo di provider, vedi [Introduzione ai provider di servizi di configurazione (CSP) per i professionisti IT](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

In Progettazione configurazione di Windows, quando crei un pacchetto di provisioning per Windows Holographic, le impostazioni in **Personalizzazioni disponibili** sono basate su [Provider di servizi di configurazione supportati in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). La tabella seguente descrive le impostazioni che potresti voler configurare per HoloLens.

![Impostazioni di runtime comuni per HoloLens](images/icd-settings.png)

| Impostazione | Descrizione |
| --- | --- |
| **Certificati** | Distribuire un certificato in HoloLens.  |
| **ConnectivityProfiles** | Distribuire un profilo Wi-Fi in HoloLens.   |
| **EditionUpgrade** | [Aggiornamento a Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Criteri** | Consentire o impedire la modalità sviluppatore in HoloLens. [Criteri supportati da Windows Holographic for Business](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## Installare app tramite il pacchetto di provisioning

Le app possono essere installate tramite pacchetti di provisioning nei dispositivi HoloLens 2. Questo consente un pacchetto facilmente riutilizzabile che puoi usare per aiutarti a distribuire le tue app. Leggere le istruzioni complete per la [distribuzione delle app tramite il provisioning dei pacchetti](app-deploy-provisioning-package.md).  

> [!NOTE]
> HoloLens (1a generazione) ha un supporto limitato per l'installazione di app (**UniversalAppInstall**) usando un pacchetto di provisioning. I dispositivi HoloLens (1a Gen) supportano solo l'installazione di un'app tramite PPKG solo durante la configurazione guidata e solo con le installazioni di contesto utente.
