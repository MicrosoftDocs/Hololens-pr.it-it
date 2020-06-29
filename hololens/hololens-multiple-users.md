---
title: Condividi HoloLens con più persone
description: È possibile configurare HoloLens in modo che vengano condivisi da più account di Azure Active Directory o da più utenti che usano un singolo account.
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829287"
---
# Condividi HoloLens con più persone

È comune condividere un HoloLens con molte persone o avere molte persone che condividono un set di dispositivi HoloLens.  In questo articolo vengono illustrati i diversi modi in cui è possibile condividere un dispositivo.

## Condividere con più persone, ognuno con il proprio account

**Prerequisito**: il dispositivo HoloLens deve eseguire Windows 10, versione 1803 o successiva.  HoloLens (1a generazione) deve anche essere [aggiornato a Windows olografico for business](hololens-upgrade-enterprise.md).

Quando usano gli account di Azure Active Directory (Azure AD), più utenti possono conservare le proprie impostazioni utente e i dati degli utenti nel dispositivo.

Per assicurarsi che più persone possano usare i propri account in HoloLens, eseguire le operazioni seguenti per configurarlo:

1. Verificare che il dispositivo esegua Windows 10, versione 1803 o successiva.
   > [!IMPORTANT]
   > Se si usa un dispositivo HoloLens (1a Gen), [aggiornare il dispositivo a Windows olografico for business](hololens1-upgrade-enterprise.md).
1. Quando configuri il dispositivo, seleziona il **mio lavoro o l'Istituto di istruzione proprietario** ed Esegui l'accesso usando un account di Azure ad.
1. Dopo aver completato la configurazione, verificare che le impostazioni dell'account (account**delle impostazioni**  >  **Accounts**) includano **altri utenti**.

Per usare HoloLens, ogni utente segue questa procedura:

1. Se un altro utente usa il dispositivo, eseguire una delle operazioni seguenti:
   - Premere una volta il pulsante di alimentazione per passare alla modalità standby e quindi premere di nuovo il pulsante di alimentazione per tornare alla schermata di blocco
   - HoloLens 2 gli utenti possono selezionare il riquadro utente dal menu Start per disconnettersi dall'utente corrente.

1. Usa le credenziali dell'account Azure AD per accedere al dispositivo.  
    Se è la prima volta che si usa il dispositivo, è necessario [calibrare](hololens-calibration.md) HoloLens con i propri occhi.

Per visualizzare un elenco degli utenti del dispositivo o per rimuovere un utente dal dispositivo, passa a account **delle impostazioni**di  >  **Accounts**  >  **altri utenti**.

## Condividere con più persone, usando lo stesso account

Più utenti possono anche condividere un dispositivo HoloLens durante l'uso di un singolo account utente.

**In HoloLens 2**, quando un nuovo utente mette il dispositivo in testa per la prima volta (mantenendo lo stesso account connesso), il dispositivo chiede al nuovo utente di calibrare e personalizzare rapidamente l'esperienza di visualizzazione. Il dispositivo può archiviare le informazioni di calibrazione in modo che in futuro il dispositivo possa ottimizzare automaticamente la qualità e il comfort dell'esperienza di visualizzazione di ogni utente. Gli utenti non devono calibrare di nuovo il dispositivo.

In **HoloLens (1a generazione)** gli utenti che condividono un account dovranno chiedere di ricalibrare l'app Impostazioni.  Per altre informazioni, vedere [calibrazione](hololens-calibration.md).
