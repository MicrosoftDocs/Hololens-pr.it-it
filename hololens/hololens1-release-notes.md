---
title: Note sulla versione di HoloLens 1st (gen)
description: Informazioni sugli aggiornamenti in ogni nuova versione di HoloLens.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/12/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: ab67962efdafe3f39097210d60589dc6db715837
ms.sourcegitcommit: c870802ea75a9dd602319c59fedb124f80c19b71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "11136171"
---
# Note sulla versione di HoloLens 1st (gen)

## Manutenzione a lungo termine di HoloLens (1a generazione)
HoloLens (1a generazione) ha immesso lo stato Long Term Servicing (LTS). Gli aggiornamenti futuri si consentiranno di risolvere i problemi e le correzioni di sicurezza, mantenendo la parità di funzionalità con la versione olografica di Windows 10, Release 1809 per HoloLens (1a generazione).

Per gli sviluppatori, ciò significa che le app HoloLens (1a Gen) non supportano l'API OpenXR.  Questi auricolari restano supportati in Unity 2019 LTS con il backend per l'API WinRT per il ciclo di vita completo di Unity 2019 LTS fino alla metà di 2022.

### Windows 10 olografico, versione 1809

> **Si applica a:** HoloLens (1a generazione)

| Funzionalità | Dettagli |
|---|---|
| **Menu azioni rapide** | Quando ci si trova in un'app, il gesto di Bloom apre ora un menu azioni rapide per consentire l'accesso rapido alle funzionalità di sistema usate di frequente senza dover uscire dall'app. <br> Vedere [configurare HoloLens in modalità Kiosk](hololens-kiosk.md) per informazioni sul menu azioni rapide in modalità Kiosk.<br><br> |
| **Interrompere l'acquisizione di video dal menu avvia o azioni rapide** | Se si avvia l'acquisizione video dal menu Start o dal menu azioni rapide, è possibile interrompere la registrazione dalla stessa posizione. Non dimenticare che puoi sempre eseguire questa operazione anche con i comandi vocali. |
| **Progetto in un dispositivo abilitato per Miracast** | Proiettare il contenuto di HoloLens in un dispositivo Surface o in una TV/monitor vicino se si usa la scheda video Microsoft.  In **Start**selezionare **Connetti**e quindi selezionare il dispositivo in cui si vuole proiettare il progetto. **Nota:** Puoi distribuire HoloLens per usare la proiezione Miracast senza abilitare la modalità sviluppatore. |
| **Nuove notifiche** | Visualizzare e rispondere ai popup di notifica in HoloLens, proprio come in un PC. Guardare per rispondere o licenziare (o se ci si trova in un'esperienza immersiva, usare il gesto di fioritura). |
| **Sovrapposizioni HoloLens**<br>(selezione file, tastiera, finestre di dialogo e così via) | Ora vedrai sovrapposizioni come la tastiera, le finestre di dialogo, la selezione file e così via quando usi le app immersive. |
| **Interfaccia utente di sovrapposizione di feedback visivo per la modifica del volume** | Quando si usano i pulsanti volume su/giù in HoloLens, verrà visualizzata una visualizzazione del livello del volume. |
| **Nuova interfaccia utente per l'avvio del dispositivo** | Durante il processo di avvio è stato aggiunto un indicatore di caricamento per ottenere un feedback visivo che il sistema sta caricando. Riavviare il dispositivo per visualizzare il nuovo indicatore di caricamento, ovvero tra il messaggio "Hello" e il logo Windows Boot. |
| **Condivisione vicina** | Aggiunta dell'esperienza di condivisione di Windows nelle vicinanze, che consente di condividere un'acquisizione con un dispositivo Windows nelle vicinanze. Quando si acquisisce una foto o un video in HoloLens (o si usa il pulsante Condividi da un'app come Microsoft Edge), selezionare un dispositivo Windows nelle vicinanze da condividere. |
| **Condivisione da Microsoft Edge** | Il pulsante Condividi è ora disponibile in Microsoft Edge Windows in HoloLens. In Microsoft Edge selezionare **Condividi**. Usare il selettore di condivisione HoloLens per condividere contenuto Web. |

#### Per clienti internazionali

| Funzionalità | Dettagli |
| --- | --- |
| Build cinesi e giapponesi localizzate | USA HoloLens con l'interfaccia utente localizzata per il cinese semplificato o giapponese, inclusi la tastiera, la dettatura e i comandi vocali pinyin localizzati.<br>[Informazioni su come installare le versioni cinese e giapponese di HoloLens.](hololens1-install-localized.md) |
| Sintesi vocale (TTS) | La caratteristica sintesi vocale ora supporta il cinese, il giapponese e l'inglese. |

#### Per gli amministratori

| Funzionalità |  Dettagli  |
|---|----|
| [Abilitare il provisioning post-installazione](hololens-provisioning.md) | Ora puoi applicare un pacchetto di provisioning di runtime in qualsiasi momento usando **le impostazioni**. |
| Accesso assegnato ai gruppi di Azure AD | Ora puoi usare i gruppi di Azure AD per la configurazione dell'accesso assegnato a Windows per configurare la configurazione di un chiosco single o multi-app. |
| PIN Sign-in nel passaggio di profilo dalla schermata di accesso | Il PIN Sign-in è ora disponibile per **altri utenti**. |
| Accedere con il provider di credenziali Web tramite la password | Ora è possibile selezionare l'opzione di accesso globale per avviare il Web Sign-in con la password. Nella schermata di accesso selezionare **Opzioni di accesso** e selezionare l'opzione Globe per avviare il Web Sign-in. Immettere il nome utente, se necessario, quindi la password. <br>**Nota:** È possibile scegliere di ignorare le opzioni di PIN/smartcard quando richiesto durante l'accesso Web. |
| Leggere le informazioni sull'hardware del dispositivo attraverso MDM in modo che i dispositivi possano essere rilevati per numero seriale | Gli amministratori IT possono vedere e tenere traccia di HoloLens in base al numero seriale del dispositivo nella console MDM. Vedere la documentazione di MDM per la disponibilità delle funzionalità e le istruzioni. |
| Impostare il nome del dispositivo HoloLens tramite MDM (Rename) | Gli amministratori IT possono vedere e rinominare i dispositivi HoloLens nella console MDM. Vedere la documentazione di MDM per la disponibilità delle funzionalità e le istruzioni. |

### Windows 10, versione 1803 per Microsoft HoloLens

> **Si applica a:** HoloLens (1a generazione)

Windows 10, versione 1803, è il primo aggiornamento delle funzionalità di Windows olografico per le aziende sin dalla sua pubblicazione in Windows 10, versione 1607. Questo aggiornamento introduce le modifiche seguenti:

- In precedenza, si poteva solo verificare che la licenza di aggiornamento per Commercial Suite fosse stata applicata al dispositivo HoloLens controllando se VPN fosse un'opzione disponibile nel dispositivo. Ora, **Settings**  >  il**sistema** di impostazioni visualizzerà **Windows olografico for business** dopo l'applicazione della licenza di aggiornamento. [Informazioni su come sbloccare le funzionalità di Windows olografiche per le aziende](hololens1-upgrade-enterprise.md).

- Puoi visualizzare il numero di build del sistema operativo in Proprietà dispositivo nell'app Esplora file e nello [strumento di ripristino di dispositivi Windows (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- Il provisioning di un dispositivo HoloLens è ora più semplice con la procedura guidata nuovo **provision HoloLens Devices** nello strumento Windows Configuration designer. Nella procedura guidata è possibile configurare l'esperienza di configurazione e le connessioni di rete, impostare la modalità sviluppatore e ottenere token di Azure AD in blocco. [Informazioni su come usare la procedura guidata di provisioning semplice per HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Quando si crea un account locale in un pacchetto di provisioning, la password non scade più ogni 42 giorni.

- Puoi [configurare HoloLens come chiosco Single-app o multi-app](hololens-kiosk.md). La modalità Kiosk multi-app consente di configurare un HoloLens per eseguire solo le app specificate e impedisce agli utenti di apportare modifiche.

- Il protocollo MTP (Media Transfer Protocol) è abilitato in modo che sia possibile connettere il dispositivo HoloLens a un PC tramite USB e trasferire file tra HoloLens e il PC. Puoi anche usare l'app Esplora file per trasferire ed eliminare file dall'interno di HoloLens.

- In precedenza, dopo avere effettuato l'accesso al dispositivo con un account di Azure Active Directory (Azure AD), è stato quindi necessario **aggiungere l'accesso al lavoro** nelle **Impostazioni** per accedere alle risorse aziendali. A questo punto, accedi con un account di Azure AD e la registrazione avviene automaticamente.

- Prima di accedere, è possibile scegliere l'icona di rete sotto il campo password per scegliere una rete di Wi-Fi diversa a cui connettersi. È anche possibile connettersi a una rete Guest, ad esempio in un hotel, un centro conferenze o un'azienda.

- Ora puoi condividere facilmente [HoloLens con più persone](hololens-multiple-users.md) usando gli account di Azure ad.

- Quando la configurazione o l'accesso non riesce, scegliere la nuova opzione **raccolta informazioni** per ottenere i registri diagnostici per la risoluzione dei problemi.

- I singoli utenti possono sincronizzare la posta elettronica aziendale senza registrare il proprio dispositivo in MDM (Mobile Device Management). Puoi usare il dispositivo con un account Microsoft, scaricare e installare l'app posta e aggiungere un account di posta elettronica direttamente.

- Puoi controllare lo stato di sincronizzazione di MDM per un dispositivo in account di **Impostazioni**di  >  **Accounts**  >  **Access o**  >  **informazioni**dell'Istituto di istruzione. Nella sezione **stato sincronizzazione dispositivo** è possibile avviare una sincronizzazione, vedere aree gestite da MDM e creare ed esportare un report di diagnostica avanzata.
