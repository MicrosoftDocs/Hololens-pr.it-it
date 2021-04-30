---
title: Condividere HoloLens con più persone
description: È possibile configurare HoloLens in modo che sia condiviso da più Azure Active Directory o da più utenti che usano un singolo account.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309547"
---
# <a name="share-your-hololens-with-multiple-people"></a>Condividere HoloLens con più persone

È comune condividere un dispositivo HoloLens con molte persone o avere molte persone che condividono un set di dispositivi HoloLens.  Questo articolo descrive i diversi modi in cui è possibile condividere un dispositivo.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Condividere con più persone, ognuna con il proprio account

**Prerequisito:** il dispositivo HoloLens deve eseguire Windows 10 versione 1803 o successiva.  È anche necessario aggiornare HoloLens (prima generazione) [a Windows Holographic for Business](hololens-upgrade-enterprise.md).

Quando usano i propri account Azure Active Directory (Azure AD), più utenti possono mantenere le proprie impostazioni utente e i dati utente nel dispositivo.

Per assicurarsi che più utenti possano usare i propri account in HoloLens, seguire questa procedura per configurarlo:

1. Assicurarsi che il dispositivo sia in esecuzione Windows 10 versione 1803 o successiva.
   > [!IMPORTANT]
   > Se si usa un dispositivo HoloLens (prima generazione), aggiornare il dispositivo a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Quando si configura il dispositivo, selezionare **My work or school owns it** and sign in by an Azure AD account .
1. Al termine dell'installazione, assicurarsi che le impostazioni dell'account (**Account**  >  **impostazioni**) includa **Altri utenti**.

Per usare HoloLens, ogni utente segue questa procedura:

1. Se il dispositivo è stato utilizzato da un altro utente, eseguire una delle operazioni seguenti:
   - Premere una volta il pulsante di alimentazione per passare alla modalità standby, quindi premere di nuovo il pulsante di alimentazione per tornare alla schermata di blocco
   - HoloLens 2 utenti possono selezionare il riquadro utente dal menu Start per disconnettere l'utente corrente.

1. Usare le Azure AD dell'account per accedere al dispositivo.  
    Se è la prima volta che si usa il dispositivo, è necessario [calibrare](hololens-calibration.md) HoloLens in base ai propri occhi.

Per visualizzare un elenco degli utenti del dispositivo o per rimuovere un utente dal dispositivo, passare a **Impostazioni**  >  **Account**  >  **Altri utenti.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Condividere con più utenti, tutti usando lo stesso account

Più utenti possono anche condividere un dispositivo HoloLens usando un singolo account utente.

**In HoloLens 2**, quando un nuovo utente mette il dispositivo in testa per la prima volta (mantenendo lo stesso account connesso), il dispositivo richiede al nuovo utente di calibrare e personalizzare rapidamente l'esperienza di visualizzazione. Il dispositivo può archiviare le informazioni di calibrazione in modo che in futuro il dispositivo possa ottimizzare automaticamente la qualità e il comfort dell'esperienza di visualizzazione di ogni utente. Gli utenti non devono calibrare nuovamente il dispositivo.

**In HoloLens (prima generazione)** gli utenti che condividono un account dovranno chiedere di eseguire la ricalibrazione nell'app Impostazioni.  Altre informazioni sulla [calibrazione.](hololens-calibration.md)
