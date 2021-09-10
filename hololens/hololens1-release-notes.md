---
title: HoloLens note sulla versione di prima generazione
description: Informazioni sugli aggiornamenti in ogni nuova HoloLens versione.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427552"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens note sulla versione di prima generazione

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (prima generazione) Manutenzione a lungo termine
HoloLens (prima generazione) è stato inserito lo stato long term servicing (LTS). Gli aggiornamenti futuri saranno incentrati su problemi e correzioni di sicurezza, mantenendo la parità delle funzionalità con la versione Windows 10 Holographic, versione 1809 per HoloLens (prima generazione).

Per gli sviluppatori, ciò significa che HoloLens app di prima generazione non supporteranno l'API OpenXR.  Questi visori rimangono supportati in Unity 2019 LTS con il back-end dell'API WinRT per l'intero ciclo di vita di Unity 2019 LTS fino alla metà del 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, versione 1809

> **Si applica a:** HoloLens (prima generazione)

| Funzionalità | Dettagli |
|---|---|
| **Menu Azioni rapide** | Quando si usa un'app, il movimento Bloom aprirà ora un menu Azioni rapide per accedere rapidamente alle funzionalità di sistema usate di frequente senza dover uscire dall'app. <br> Per informazioni sul menu Azioni rapide [in modalità tutto schermo, vedere](hololens-kiosk.md) Configurare HoloLens modalità tutto schermo.<br><br> |
| **Arrestare l'acquisizione video dal menu Start o azioni rapide** | Se si avvia l'acquisizione video dal menu menu Start o azioni rapide, sarà possibile arrestare la registrazione dalla stessa posizione. Non dimenticare che è sempre possibile eseguire questa operazione anche con i comandi vocali. |
| **Project a un dispositivo Miracast abilitato** | Project il HoloLens in un dispositivo Surface vicino o tv/monitor se si usa l'adattatore Microsoft Display.  In **Start** **selezionare** Connessione e quindi selezionare il dispositivo in cui si vuole eseguire il progetto. **Nota:** È possibile distribuire HoloLens usare la proiezione Miracast senza abilitare la modalità sviluppatore. |
| **Nuove notifiche** | Visualizzare e rispondere agli avvisi popup di notifica HoloLens, proprio come si fa in un PC. Guardare con lo sguardo per rispondere o ignorarli oppure, se si è in un'esperienza immersiva, usare il movimento bloom. |
| **HoloLens sovrimpressione**<br>(selezione file, tastiera, dialoghe e così via) | Quando si usano app immersive, verranno ora visualizzati sovrapposizioni, ad esempio tastiera, dialoghe, selezione file e così via. |
| **Interfaccia utente di sovrapposizione dei commenti e suggerimenti visivi per la modifica del volume** | Quando si usano i pulsanti volume su/giù nel HoloLens verrà visualizzata una visualizzazione visiva del livello del volume. |
| **Nuova interfaccia utente per l'avvio del dispositivo** | Durante il processo di avvio è stato aggiunto un indicatore di caricamento per fornire un feedback visivo sul caricamento del sistema. Riavviare il dispositivo per visualizzare il nuovo indicatore di caricamento, ovvero tra il messaggio "Hello" e il logo Windows di avvio. |
| **Condivisione nelle vicinanze** | Aggiunta dell'esperienza Windows condivisione nelle vicinanze, che consente di condividere un'acquisizione con un dispositivo Windows vicino. Quando si acquisisce una foto o un video HoloLens (o si usa il pulsante condividi da un'app come Microsoft Edge), selezionare un dispositivo Windows vicino con cui condividere. |
| **Condividere da Microsoft Edge** | Il pulsante Condividi è ora disponibile nelle finestre Microsoft Edge in HoloLens. In Microsoft Edge selezionare **Condividi**. Usare la HoloLens di condivisione per condividere il contenuto Web. |

#### <a name="for-international-customers"></a>Per i clienti internazionali

| Funzionalità | Dettagli |
| --- | --- |
| Compilazioni localizzate in cinese e giapponese | Usare HoloLens con l'interfaccia utente localizzata per il cinese semplificato o il giapponese, inclusi i comandi vocali, la dettatura e la tastiera Pinyin localizzati.<br>[Informazioni su come installare le versioni cinese e giapponese di HoloLens.](hololens1-install-localized.md) |
| Sintesi vocale (TTS) | La funzionalità sintesi vocale supporta ora il cinese, il giapponese e l'inglese. |

#### <a name="for-administrators"></a>Per amministratori

| Funzionalità |  Dettagli  |
|---|----|
| [Abilitare il provisioning post-installazione](hololens-provisioning.md) | È ora possibile applicare un pacchetto di provisioning di runtime in qualsiasi momento **usando Impostazioni**. |
| Accesso assegnato con gruppi Azure AD predefiniti | È ora possibile usare i gruppi Azure AD per la configurazione Windows'accesso assegnato per configurare la configurazione in modalità tutto schermo per app singole o multiapp. |
| Pin sign-in on profile switch from sign-in screen | L'accesso CON PIN è ora disponibile per **Altri utenti.** |
| Accedere con l'Provider di credenziali Web usando la password | È ora possibile selezionare l'opzione di accesso Globe per avviare l'accesso Web con la password. Nella schermata di accesso selezionare **Opzioni di** accesso e selezionare l'opzione Globe per avviare l'accesso Web. Immettere il nome utente, se necessario, quindi la password. <br>**Nota:** È possibile scegliere di ignorare le opzioni PIN/Smartcard quando richiesto durante l'accesso Web. |
| Leggere le informazioni sull'hardware del dispositivo tramite MDM in modo che i dispositivi possano essere monitorati in base al numero di serie | Gli amministratori IT possono visualizzare e tenere traccia HoloLens numero di serie del dispositivo nella console MDM. Per la disponibilità delle funzionalità e le istruzioni, vedere la documentazione mdm. |
| Impostare HoloLens nome del dispositivo tramite MDM (ridenominazione) | Gli amministratori IT possono visualizzare e rinominare HoloLens dispositivi mobili nella console MDM. Per la disponibilità delle funzionalità e le istruzioni, vedere la documentazione mdm. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 versione 1803 per Microsoft HoloLens

> **Si applica a:** HoloLens (prima generazione)

Windows 10, versione 1803, è il primo aggiornamento delle funzionalità Windows Holographic for Business dalla versione Windows 10, versione 1607. Questo aggiornamento introduce le modifiche seguenti:

- In precedenza, era possibile verificare che la licenza di aggiornamento per Commercial Suite fosse stata applicata al dispositivo HoloLens controllando se la VPN era un'opzione disponibile nel dispositivo. A questo **punto, Impostazioni**  >  **sistema** visualizza Windows Holographic for Business dopo l'applicazione della licenza di aggiornamento.  [Informazioni su come sbloccare Windows Holographic for Business funzionalità .](hololens1-upgrade-enterprise.md)

- È possibile visualizzare il numero di build del sistema operativo nelle proprietà del dispositivo nell'app Esplora file e in [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- Il provisioning HoloLens dispositivo è ora più semplice con la nuova procedura guidata **Provisioning HoloLens dispositivi** nello strumento Windows Configuration Designer. Nella procedura guidata è possibile configurare l'esperienza di installazione e le connessioni di rete, impostare la modalità sviluppatore e ottenere token Azure AD in blocco. [Informazioni su come usare la procedura guidata di provisioning semplice per HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Quando si crea un account locale in un pacchetto di provisioning, la password non scade più ogni 42 giorni.

- È possibile configurare HoloLens come app singola o [multi-app](hololens-kiosk.md)in modalità tutto schermo. La modalità tutto schermo multi-app consente di configurare un HoloLens per eseguire solo le app specificate e impedisce agli utenti di apportare modifiche.

- Media Transfer Protocol (MTP) è abilitato in modo da poter connettere il dispositivo HoloLens a un PC tramite USB e trasferire i file tra HoloLens e il PC. È anche possibile usare l'app Esplora file per spostare ed eliminare file dall'interno HoloLens.

- In precedenza, dopo aver eseguito l'accesso al dispositivo con un account Azure Active Directory (Azure AD),  era necessario aggiungere l'accesso aziendale **in** Impostazioni per ottenere l'accesso alle risorse aziendali. A questo punto, si accede con un account Azure AD la registrazione avviene automaticamente.

- Prima di accedere, è possibile scegliere l'icona di rete sotto il campo della password per scegliere un'altra Wi-Fi rete a cui connettersi. È anche possibile connettersi a una rete guest, ad esempio in un hotel, in un centro conferenze o in un'azienda.

- È ora possibile condividere [facilmente HoloLens con più utenti](hololens-multiple-users.md) usando Azure AD account.

- Quando l'installazione o l'accesso non riesce, scegliere la nuova **opzione Raccogli informazioni** per ottenere i log di diagnostica per la risoluzione dei problemi.

- I singoli utenti possono sincronizzare la posta elettronica aziendale senza registrare il dispositivo nella gestione dei dispositivi mobili (MDM). È possibile usare il dispositivo con un account Microsoft, scaricare e installare l'app Mail e aggiungere direttamente un account di posta elettronica.

- È possibile controllare lo stato di sincronizzazione MDM per un dispositivo **in** Impostazioni  >    >  **account aCcedono alle informazioni aziendali o dell'istituto di**  >  **istruzione.** Nella sezione **Stato sincronizzazione dispositivo** è possibile avviare una sincronizzazione, visualizzare le aree gestite da MDM e creare ed esportare un report di diagnostica avanzato.
