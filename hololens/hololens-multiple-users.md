---
title: Condividere il HoloLens con più persone
description: È possibile configurare HoloLens condivisi da più account Azure Active Directory o da più utenti che usano un singolo account.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428198"
---
# <a name="share-your-hololens-with-multiple-people"></a>Condividere il HoloLens con più persone

## <a name="overview"></a>Panoramica
Le aziende spesso investono in molti dispositivi HoloLens condivisi. La modalità di HoloLens flessibile a seconda dei singoli requisiti. Ecco un esempio di alcune esperienze multi-utente: 

- I dispositivi a cui viene addebitato un Dynamics 365 Guides e consentono ai dipendenti di aprire l'app Impostazioni per apportare modifiche Wi-Fi necessarie, ma i criteri di visibilità Impostazioni pagina sono abilitati per limitare la quantità di pagine disponibili nell'app Impostazioni.
- I dispositivi che sono Remote Assist e l'app line-of-business che vengono noleggiati ad altre aziende. Questi dispositivi hanno chioschi in modalità tutto schermo che includono solo l'app e Remote Assist. WDAC viene usato per evitare che l'app Impostazioni e Microsoft Edge l'avvio. Incluso nel noleggio è disponibile un pacchetto di batteria USB-C per mantenere i dispositivi a pieno carico su più turni.
- Tutti i dispositivi sono impostati per Autopilot e scaricano tutte le app aziendali. Sono stati impostati alcuni profili di chiosco multimediale diversi, che hanno come destinazione Azure AD gruppi. Ogni utente accede al HoloLens usando le chiavi FIDO2 e accede al proprio account Azure AD e viene presentata un'esperienza personalizzata.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Condividere con più persone, ognuna con il proprio account

**Prerequisito:** il HoloLens deve essere in esecuzione Windows 10 versione 1803 o successiva.  HoloLens (prima generazione) è anche necessario eseguire l'aggiornamento [a Windows Holographic for Business](hololens-upgrade-enterprise.md).

Quando usano i propri account Azure Active Directory (Azure AD), più utenti possono mantenere le proprie impostazioni utente e i dati utente nel dispositivo.

Per assicurarsi che più utenti possano usare i propri account nel HoloLens, seguire questa procedura per configurarlo:

1. Assicurarsi che il dispositivo sia in esecuzione Windows 10 versione 1803 o successiva.
   > [!IMPORTANT]
   > Se si usa un dispositivo HoloLens (prima generazione), aggiornare il dispositivo a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Quando si configura il dispositivo, selezionare **My work or school owns it** and sign in by an Azure AD account .
1. Al termine dell'installazione, assicurarsi che le impostazioni dell'account (**Impostazioni**  >  **account**) includa **Altri utenti**.

Per usare HoloLens, ogni utente segue questa procedura:

1. Se il dispositivo è stato utilizzato da un altro utente, scegliere una delle opzioni seguenti:
   - Premere una volta il pulsante di alimentazione per passare alla modalità standby, quindi premere di nuovo il pulsante di alimentazione per tornare alla schermata di blocco
   - HoloLens 2 gli utenti possono selezionare il riquadro utente dal menu Start per disconnettere l'utente corrente.

1. Usare le Azure AD dell'account per accedere al dispositivo.  
    Se è la prima volta che si usa il [](hololens-calibration.md) dispositivo, è necessario calibrare HoloLens ai propri occhi.

Per visualizzare un elenco degli utenti del dispositivo o per rimuovere un utente dal dispositivo, passare a Impostazioni  >    >  **Account Altri utenti**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Condividere con più persone, usando tutti lo stesso account

Più utenti possono anche condividere un dispositivo HoloLens usando un singolo account utente.

**In HoloLens 2**, quando un nuovo utente mette il dispositivo in primo piano per la prima volta (mantenendo lo stesso account connesso), il dispositivo richiede al nuovo utente di calibrare e personalizzare rapidamente l'esperienza di visualizzazione. Il dispositivo può archiviare le informazioni di calibrazione in modo che in futuro il dispositivo possa ottimizzare automaticamente la qualità e il comfort dell'esperienza di visualizzazione di ogni utente. Gli utenti non devono calibrare nuovamente il dispositivo.

**Nella HoloLens (prima generazione)** gli utenti che condividono un account dovranno chiedere di eseguire la ricalibrazione nell'app Impostazioni locale.  Altre informazioni sulla [calibrazione.](hololens-calibration.md)