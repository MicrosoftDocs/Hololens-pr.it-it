---
title: Condividere il HoloLens con più persone
description: È possibile configurare HoloLens condivisi da più account Azure Active Directory o da più utenti che usano un singolo account.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600730"
---
# <a name="share-your-hololens-with-multiple-people"></a>Condividere il HoloLens con più persone

## <a name="overview"></a>Panoramica

Le aziende spesso investono in molti dispositivi HoloLens condivisi. La modalità di HoloLens è flessibile a seconda dei singoli requisiti. Ecco un esempio di alcune esperienze multi-utente:

- Una flotta di HoloLens 2 viene impostata tramite Windows Autopilot per HoloLens 2, con un portfolio coerente di applicazioni aziendali in ogni dispositivo. Sono stati impostati alcuni profili in modalità tutto schermo diversi, che hanno come destinazione Azure AD diversi. Ogni utente accede al HoloLens usando le chiavi FIDO2 e accedendo al proprio account Azure AD e viene presentato con un'esperienza personalizzata.
- Un fornitore di software indipendente (ISV) noleggia dispositivi HoloLens 2 con D365 Remote Assist e la relativa applicazione line-of-business (LOB) all'azienda di un cliente. Questi dispositivi sono configurati per chioschi multimediale che includono solo l'app LOB e Remote Assist e sono condivisi tra più utenti finali. WDAC viene usato per evitare che l'app Impostazioni e Microsoft Edge l'avvio. Incluso nel noleggio è disponibile un pacchetto batteria USB-C per mantenere i dispositivi completamente a carico su più turni.
- Un utente finale di un'azienda tenta di apportare modifiche al Bluetooth nel dispositivo in modo che possa connettere un nuovo dispositivo, ma i criteri Visibilità Impostazioni pagina sono abilitati per limitare la visualizzazione della pagina Dispositivi. È comunque consentito l'accesso ad altre pagine in base alle esigenze, ad esempio Wi-Fi in modo che possano usare Remote Assist in più posizioni con lo stesso HoloLens.

## <a name="best-practices"></a>Procedure consigliate

Quando si pianifica la condivisione dei dispositivi, è necessario tenere presenti diverse considerazioni per ottimizzare l'ambiente dei dispositivi in base alle esigenze aziendali.

- [Identità e autenticazione](#identity-and-authentication)
- [Gestione dei dispositivi](#device-management)
- [Gestione avanzata dei dispositivi - Modalità tutto schermo e WDAC](#advanced-device-management---kiosk-and-wdac)
- [Gestione fisica](#physical-management)

### <a name="identity-and-authentication"></a>[Identità e autenticazione](hololens-identity.md)

Se si prevede di avere più account in un dispositivo, saranno disponibili Azure AD con tutte le modalità di autenticazione. Questi metodi di autenticazione saranno basati su [Windows Hello](/windows-hardware/design/device-experiences/windows-hello), incluse le chiavi Iris e FIDO2.

- Le chiavi di sicurezza FIDO 2 sono eccellenti se si hanno più dispositivi, molti utenti o si usano costantemente nuovi dispositivi.
- Se sono presenti 10 o meno utenti, Iris è una soluzione rapida per l'accesso degli utenti che in precedenza hanno eseguito l'accesso allo stesso dispositivo.

### <a name="device-management"></a>[Gestione dei dispositivi](hololens-csp-policy-overview.md)

Se i dispositivi vengono condivisi tra gli utenti, è probabile che si vogliano usare le restrizioni dei dispositivi. Usando la gestione dei dispositivi è possibile impostare alcuni criteri per consentire agli utenti di usare il dispositivo, gestire gli aggiornamenti o limitare le attività che il dispositivo può eseguire. È consigliabile esaminare le [restrizioni comuni dei dispositivi](hololens-common-device-restrictions.md)e verificare se queste raccomandazioni sembrano adattarsi all'organizzazione. Quando si conoscono i criteri da usare, è possibile applicarli tramite microsoft [Endpoint Manager (MDM)](hololens-mdm-configure.md) o pacchetti di provisioning.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Gestione avanzata dei dispositivi - [Modalità tutto schermo](hololens-kiosk.md) e [WDAC](windows-defender-application-control-wdac.md)

In alcuni casi, è possibile limitare le applicazioni a cui gli utenti finali possono accedere. È possibile limitare le app presentate dagli utenti nel menu Start usando la [modalità tutto schermo](hololens-kiosk.md). La modalità tutto schermo può essere configurata per presentare menu Start diversi in base a utenti, gruppi di Azure o tipi di utenti speciali. ad esempio il visitatore o l'esclusione dei proprietari di dispositivi. È possibile scegliere più app o una sola app. Un chiosco multimediale con più app non arresta l'avvio di un'altra app, quindi se lo Store o un'altra app è disponibile, gli utenti possono comunque avviare un'altra app.

È anche possibile arrestare completamente l'avvio di app o servizi [usando Windows Defender Application Control (WDAC)](windows-defender-application-control-wdac.md) per limitare le app. WDAC è diverso da Kiosk, perché non modifica l'interfaccia utente di HoloLens ma non consente l'avvio di un'app bloccata.

[La Impostazioni della](settings-uri-list.md) pagina è un altro modo per aggiungere restrizioni a un dispositivo. Nel caso in cui sia necessario concedere agli utenti l'accesso ad alcune pagine nell'app Impostazioni, ma non tutto è possibile usare Visibilità Impostazioni pagina per limitare l'accesso. Ciò è utile, ad esempio, se gli utenti devono modificare il Wi-Fi, ma non si vuole che accedono alla pagina Account.

### <a name="physical-management"></a>Gestione fisica

Quando si condivide il dispositivo tra più utenti, è necessario tenere presenti alcune considerazioni fisiche.

- Assicurarsi che i dispositivi addebitino tra i turni.
- Se un dispositivo è necessario per un turno e deve durare più turni, prendere in considerazione l'uso di una batteria esterna all'inizio di un turno, mentre il dispositivo ha ancora una carica significativa in base alle direzioni di [gestione del calore.](hololens2-charging.md#managing-heat)
- Quando si archiviano i dispositivi, mantenerli collegati e collegati a una rete. Questo è il modo migliore per garantire gli aggiornamenti del sistema operativo e dell'app.
- Considerare come si prevede di [pulire il dispositivo tra](hololens2-maintenance.md) gli utenti.
- Per un dispositivo con un singolo utente condiviso se si usa un PIN/password condiviso per un singolo utente, non inserire il PIN o la password sul lato del dispositivo.
- Per più dispositivi con un singolo utente condiviso, usare vari PIN/password.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Condividere con più persone, ognuna usando il proprio account

I singoli Azure Active Directory (Azure AD) sono il caso d'uso di identità preferito e più sicuro per HoloLens 2 utenti. Quando si usano i propri Azure AD, più utenti possono mantenere le proprie impostazioni utente e i propri dati utente nel dispositivo. È possibile accedere a un solo utente alla volta. Quando un utente esegue l'accesso, HoloLens l'utente precedente.

Per assicurarsi che più utenti possano usare i propri account nel HoloLens, seguire questa procedura per configurarlo:

1. Quando si [configura il dispositivo,](hololens2-start.md)selezionare **My work or school owns it** and sign in by an Azure AD account (L'account aziendale o dell'istituto di istruzione è proprietario e accedere con un account Azure AD aziendale.
1. Al termine dell'installazione, assicurarsi che le impostazioni dell'account (Impostazioni > account) **includano Altri utenti**.

> [!NOTE]
> Se il dispositivo non è stato configurato con un account [](hololens-recovery.md) Azure AD, è necessario reimpostarlo o reimpostarlo e configurarlo correttamente.

Per usare HoloLens, ogni utente segue questa procedura:

1. Se il dispositivo è stato utilizzato da un altro utente, scegliere una delle opzioni seguenti:
   - Premere il pulsante di alimentazione una volta per passare alla modalità standby, quindi premere di nuovo il pulsante di alimentazione per tornare alla schermata di blocco
   - Selezionare il riquadro utente **dal** menu Start o scegliere Disconnetto dal menu **Power** per disconnettere l'utente corrente.

1. Usare le Azure AD dell'account per accedere al dispositivo.  
    - Se è la prima volta che si usa il [](hololens-calibration.md) dispositivo, verrà chiesto di calibrare il HoloLens ai propri occhi.
    - Se in precedenza è stato usato il dispositivo:
        - [Windows Holographic, versione 20H2, build 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) o successiva, lo schermo si adatta perfettamente alla qualità e a un'esperienza di visualizzazione comoda.
        - Le build precedenti necessitano di calibrazione manuale per adattarsi agli occhi.

> [!TIP]
> Se un utente non ha ancora eseguito l'accesso a un dispositivo, provare uno di questi due metodi per un accesso più veloce:
>
> - **Chiave di sicurezza FIDO 2:** la chiave di sicurezza FIDO2 verrà riconosciuta automaticamente e l'utente non dovrà digitare le credenziali utente o usare l'autenticazione a più fattori. Questo è il metodo più rapido per accedere a un nuovo dispositivo.
> - **Autenticazione Web:** quando si accede a un nuovo  dispositivo, è possibile selezionare il collegamento Accedi da un altro dispositivo che genera un codice di 9 caratteri che è possibile usare [in aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) per accedere come utente nel dispositivo o digitare il nome utente e la password usando una tastiera per comodità.

Per visualizzare un elenco degli utenti del dispositivo o per rimuovere un utente dal dispositivo, passare a Impostazioni  >  **Account**  >  **altri utenti.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Condividere con più utenti, tutti usando lo stesso account

Più utenti possono anche condividere un dispositivo HoloLens usando un singolo account utente. Anche se è preferibile HoloLens utenti di accedere al dispositivo con le proprie identità (account Azure AD), questa non è un'opzione disponibile in alcune organizzazioni.

Sono disponibili due metodi per i dispositivi condivisi:

- **Più utenti finali che condividono 1** dispositivo: un dispositivo HoloLens viene allocato a uno spazio designato in cui qualsiasi dipendente può usare il dispositivo. Ad esempio, una stanza pulita o una suite di prodotti.

- **Più utenti finali che condividono più** dispositivi: HoloLens si trova in uno spazio di archiviazione condiviso in cui i dipendenti possono usare qualsiasi dispositivo. Ad esempio, un distributore di olio o una concessionaria/rivenditore di auto.

Quando un nuovo utente inserisce il dispositivo per la prima volta mantenendo lo stesso account connesso, il dispositivo richiede all'utente di calibrare e personalizzare rapidamente l'esperienza di visualizzazione. Il dispositivo archivierà le informazioni di calibrazione per ottimizzare automaticamente la qualità e il comfort dell'esperienza di visualizzazione di ogni utente. Gli utenti non dovranno calibrare nuovamente il dispositivo.
