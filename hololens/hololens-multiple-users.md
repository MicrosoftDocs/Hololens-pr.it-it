---
title: Condividere i HoloLens con più persone
description: È possibile configurare HoloLens condivisi da più account Azure Active Directory o da più utenti che usano un singolo account.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663081"
---
# <a name="share-your-hololens-with-multiple-people"></a>Condividere i HoloLens con più persone

È comune condividere un'HoloLens con molte persone o fare in modo che molte persone conosino un set di HoloLens dispositivi.  Questo articolo descrive i diversi modi in cui è possibile condividere un dispositivo.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Condividere con più persone, ognuna usando il proprio account

**Prerequisito:** il HoloLens deve eseguire Windows 10 versione 1803 o successiva.  HoloLens (prima generazione) è anche necessario eseguire [l'aggiornamento a Windows Holographic for Business](hololens-upgrade-enterprise.md).

Quando usano i propri account Azure Active Directory (Azure AD), più utenti possono mantenere le proprie impostazioni utente e i propri dati utente nel dispositivo.

Per assicurarsi che più utenti possano usare i propri account nel HoloLens, seguire questa procedura per configurarlo:

1. Verificare che il dispositivo sia in esecuzione Windows 10 versione 1803 o successiva.
   > [!IMPORTANT]
   > Se si usa un HoloLens di prima generazione, aggiornare il dispositivo a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Quando si configura il dispositivo, selezionare **My work or school owns it** and sign in by an Azure AD account (L'account aziendale o dell'istituto di istruzione è proprietario e accedere con un account Azure AD aziendale.
1. Al termine dell'installazione, assicurarsi che le impostazioni dell'account (**Impostazioni**  >  **account**) **includano Altri utenti**.

Per usare HoloLens, ogni utente segue questa procedura:

1. Se il dispositivo è stato utilizzato da un altro utente, eseguire una delle operazioni seguenti:
   - Premere il pulsante di alimentazione una volta per passare alla modalità standby e quindi premere di nuovo il pulsante di alimentazione per tornare alla schermata di blocco
   - HoloLens 2 utenti possono selezionare il riquadro utente dal menu Start per disconnettere l'utente corrente.

1. Usare le Azure AD dell'account per accedere al dispositivo.  
    Se è la prima volta che si usa [](hololens-calibration.md) il dispositivo, è necessario calibrare HoloLens ai propri occhi.

Per visualizzare un elenco degli utenti del dispositivo o per rimuovere un utente dal dispositivo, passare a Impostazioni  >  **Account**  >  **altri utenti.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Condividere con più utenti, tutti usando lo stesso account

Più utenti possono anche condividere un HoloLens dispositivo usando un singolo account utente.

**In HoloLens 2,** quando un nuovo utente mette il dispositivo in testa per la prima volta (mantenendo lo stesso account connesso), il dispositivo richiede al nuovo utente di calibrare e personalizzare rapidamente l'esperienza di visualizzazione. Il dispositivo può archiviare le informazioni di calibrazione in modo che in futuro il dispositivo possa ottimizzare automaticamente la qualità e il comfort dell'esperienza di visualizzazione di ogni utente. Gli utenti non devono calibrare nuovamente il dispositivo.

**Nella HoloLens (prima generazione)** gli utenti che condividono un account dovranno chiedere di eseguire la ricalibrazione nell'app Impostazioni app.  Altre informazioni sulla [calibrazione.](hololens-calibration.md)
