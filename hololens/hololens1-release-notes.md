---
title: Note sulla versione di HoloLens di prima generazione
description: Informazioni sugli aggiornamenti in ogni nuova versione di HoloLens.
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
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "108310072"
---
# <a name="hololens-1st-gen-release-notes"></a>Note sulla versione di HoloLens di prima generazione

## <a name="hololens-1st-gen-long-term-servicing"></a>Manutenzione a lungo termine di HoloLens (prima generazione)
HoloLens (prima generazione) è in stato Long Term Servicing (LTS). Gli aggiornamenti futuri saranno incentrati sui problemi e sulle correzioni per la sicurezza, mantenendo la parità delle funzionalità con il Windows 10 Holographic, versione 1809 per HoloLens (prima generazione).

Per gli sviluppatori, ciò significa che le app HoloLens (prima generazione) non supporteranno l'API OpenXR.  Questi visori VR rimangono supportati in Unity 2019 LTS con il back-end dell'API WinRT per l'intero ciclo di vita di Unity 2019 LTS fino alla metà del 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, versione 1809

> **Si applica a:** HoloLens (prima generazione)

| Funzionalità | Dettagli |
|---|---|
| **Menu Azioni rapide** | Quando si è in un'app, il movimento di Bloom aprirà ora un menu Azioni rapide per accedere rapidamente alle funzionalità di sistema di uso comune senza dover uscire dall'app. <br> Per informazioni sul menu Azioni rapide in modalità tutto schermo, vedi Configurare [HoloLens in](hololens-kiosk.md) modalità tutto schermo.<br><br> |
| **Arrestare l'acquisizione di video dal menu Avvia o dalle azioni rapide** | Se si avvia l'acquisizione di video dal menu menu Start o azioni rapide, sarà possibile arrestare la registrazione dalla stessa posizione. Non dimenticare che è sempre possibile eseguire questa operazione anche con i comandi vocali. |
| **Progetto in un dispositivo abilitato per Miracast** | Proiettare il contenuto di HoloLens in un dispositivo Surface nelle vicinanze o in tv/monitor se si usa l'adattatore Microsoft Display.  In **Start** selezionare **Connetti** e quindi selezionare il dispositivo in cui si vuole eseguire il progetto. **Nota:** Puoi distribuire HoloLens per usare la proiezione Miracast senza abilitare la modalità sviluppatore. |
| **Nuove notifiche** | Visualizzare e rispondere agli avvisi popup di notifica in HoloLens, proprio come in un PC. Guardare con lo sguardo per rispondere o ignorarli oppure, se si è in un'esperienza immersiva, usare il movimento bloom. |
| **Sovrimpressione di HoloLens**<br>(selezione file, tastiera, dialoghe e così via) | Quando si usano app immersive, verranno ora visualizzati sovrapposizioni, ad esempio tastiera, dialoghe, selezione file e così via. |
| **Interfaccia utente di sovrapposizione dei commenti e suggerimenti visivi per la modifica del volume** | Quando si usano i pulsanti volume su/giù in HoloLens, viene visualizzata una visualizzazione visiva del livello del volume. |
| **Nuova interfaccia utente per l'avvio del dispositivo** | Durante il processo di avvio è stato aggiunto un indicatore di caricamento per fornire un feedback visivo sul caricamento del sistema. Riavviare il dispositivo per visualizzare il nuovo indicatore di caricamento, ovvero tra il messaggio "Hello" e il logo di avvio di Windows. |
| **Condivisione nelle vicinanze** | Aggiunta dell'esperienza Condivisione nelle vicinanze di Windows, che consente di condividere un'acquisizione con un dispositivo Windows nelle vicinanze. Quando si acquisisce una foto o un video in HoloLens (o si usa il pulsante condividi da un'app come Microsoft Edge), selezionare un dispositivo Windows vicino con cui condividere. |
| **Condividere da Microsoft Edge** | Il pulsante Condividi è ora disponibile nelle Microsoft Edge in HoloLens. In Microsoft Edge selezionare **Condividi**. Usare il selettore di condivisione HoloLens per condividere il contenuto Web. |

#### <a name="for-international-customers"></a>Per i clienti internazionali

| Funzionalità | Dettagli |
| --- | --- |
| Compilazioni localizzate in cinese e giapponese | Usa HoloLens con l'interfaccia utente localizzata per il cinese semplificato o il giapponese, inclusi la tastiera Pinyin localizzata, la dettatura e i comandi vocali.<br>[Informazioni su come installare le versioni in cinese e giapponese di HoloLens.](hololens1-install-localized.md) |
| Sintesi vocale (TTS) | La funzionalità di sintesi vocale supporta ora il cinese, il giapponese e l'inglese. |

#### <a name="for-administrators"></a>Per amministratori

| Funzionalità |  Dettagli  |
|---|----|
| [Abilitare il provisioning post-installazione](hololens-provisioning.md) | È ora possibile applicare un pacchetto di provisioning di runtime in qualsiasi momento usando **Impostazioni**. |
| Accesso assegnato con Azure AD gruppi | È ora possibile usare i gruppi Azure AD per la configurazione dell'accesso assegnato a Windows per configurare la configurazione della modalità tutto schermo con una o più app. |
| Pin sign-in on profile switch from sign-in screen (Passaggio pin di accesso al profilo dalla schermata di accesso) | L'accesso con PIN è ora disponibile per **Altro utente.** |
| Accedere con l'Provider di credenziali Web usando la password | È ora possibile selezionare l'opzione Di accesso a Globo per avviare l'accesso Web con la password. Nella schermata di accesso selezionare **Opzioni di** accesso e quindi l'opzione Globo per avviare l'accesso Web. Immettere il nome utente, se necessario, quindi la password. <br>**Nota:** È possibile scegliere di ignorare qualsiasi opzione pin/smart card quando richiesto durante l'accesso Web. |
| Leggere le informazioni sull'hardware del dispositivo tramite MDM in modo che i dispositivi possano essere monitorati in base al numero di serie | Gli amministratori IT possono visualizzare e tenere traccia di HoloLens in base al numero di serie del dispositivo nella console MDM. Per la disponibilità delle funzionalità e le istruzioni, vedere la documentazione mdm. |
| Impostare il nome del dispositivo HoloLens tramite MDM (ridenominazione) | Gli amministratori IT possono visualizzare e rinominare i dispositivi HoloLens nella console MDM. Per la disponibilità delle funzionalità e le istruzioni, vedere la documentazione mdm. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 versione 1803 per Microsoft HoloLens

> **Si applica a:** HoloLens (prima generazione)

Windows 10, versione 1803, è il primo aggiornamento delle funzionalità Windows Holographic for Business dalla versione Windows 10, versione 1607. Questo aggiornamento introduce le modifiche seguenti:

- In precedenza, era possibile verificare che la licenza di aggiornamento per Commercial Suite fosse stata applicata al dispositivo HoloLens controllando se la VPN era un'opzione disponibile nel dispositivo. A questo **punto, Il**  >  **sistema** delle **impostazioni** Windows Holographic for Business dopo l'applicazione della licenza di aggiornamento. [Informazioni su come sbloccare Windows Holographic for Business funzionalità](hololens1-upgrade-enterprise.md).

- È possibile visualizzare il numero di build del sistema operativo nelle proprietà del dispositivo nell'app Esplora file e in Windows [Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- Il provisioning di un dispositivo HoloLens è ora più semplice con la nuova procedura guidata **Provisioning di dispositivi HoloLens** nello strumento Progettazione configurazione Windows. Nella procedura guidata è possibile configurare l'esperienza di installazione e le connessioni di rete, impostare la modalità sviluppatore e ottenere token Azure AD in blocco. [Informazioni su come usare la procedura guidata di provisioning semplice per HoloLens.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Quando si crea un account locale in un pacchetto di provisioning, la password non scade più ogni 42 giorni.

- È possibile [configurare HoloLens](hololens-kiosk.md)come app singola o multi-app in modalità tutto schermo. La modalità tutto schermo multi-app consente di configurare holoLens in modo da eseguire solo le app specificate e impedisce agli utenti di apportare modifiche.

- Media Transfer Protocol (MTP) è abilitato in modo da poter connettere il dispositivo HoloLens a un PC tramite USB e trasferire i file tra HoloLens e il PC. È anche possibile usare l'app Esplora file per spostare ed eliminare file da HoloLens.

- In precedenza, dopo aver eseguito l'accesso al dispositivo con un account Azure Active Directory (Azure AD), era necessario aggiungere l'accesso aziendale **in** **Impostazioni** per ottenere l'accesso alle risorse aziendali. A questo punto, si accede con un account Azure AD e la registrazione viene eseguita automaticamente.

- Prima di accedere, è possibile scegliere l'icona di rete sotto il campo della password per scegliere una rete Wi-Fi a cui connettersi. È anche possibile connettersi a una rete guest, ad esempio in un hotel, in un centro conferenze o in un'azienda.

- È ora possibile condividere [facilmente HoloLens con più utenti](hololens-multiple-users.md) usando Azure AD account.

- Quando l'installazione o l'accesso non riesce, scegliere la nuova **opzione Raccogli informazioni** per ottenere i log di diagnostica per la risoluzione dei problemi.

- I singoli utenti possono sincronizzare la posta elettronica aziendale senza registrare il dispositivo nella gestione di dispositivi mobili (MDM). È possibile usare il dispositivo con un account Microsoft, scaricare e installare l'app Posta elettronica e aggiungere direttamente un account di posta elettronica.

- È possibile controllare lo stato di sincronizzazione MDM per un dispositivo **in** Impostazioni Account Accesso a Informazioni aziendali  >    >  **o**  >  **dell'istituto di istruzione.** Nella sezione **Stato sincronizzazione dispositivo** è possibile avviare una sincronizzazione, visualizzare le aree gestite da MDM e creare ed esportare un report di diagnostica avanzato.
