---
title: Registrare HoloLens in MDM
description: Registrare HoloLens nella gestione di dispositivi mobili (MDM) per una gestione più semplice di più dispositivi.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828691"
---
# Registrare HoloLens in MDM

Puoi gestire più dispositivi Microsoft HoloLens simultaneamente usando soluzioni come [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Potrai gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell’organizzazione. Vedi [Gestire i dispositivi che eseguono Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), i [provider di servizi di configurazione (CSP) che sono supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e i [criteri supportati da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gestione di dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e della modalità tutto schermo, è disponibile solo quando [esegui l'aggiornamento a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requisiti

 L'organizzazione dovrà configurare la gestione di dispositivi mobili (MDM) per la gestione dei dispositivi HoloLens. Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.

## Registrazione automatica in MDM

Se l'organizzazione usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token AAD per l'autenticazione (attualmente supportato solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD in modo da consentire automaticamente la registrazione MDM dopo l'accesso dell'utente con l'account Azure AD. [Informazioni su come configurare la registrazione di Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando è abilitata la registrazione automatica, non è necessaria alcuna registrazione manuale aggiuntiva. Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.

## Effettuare la registrazione tramite l'app Impostazioni

 Quando il dispositivo non è registrato in MDM durante l'esperienza di prima esecuzione, l'utente può registrare manualmente il dispositivo con il server MDM dell'organizzazione mediante l'app Impostazioni.

1. Andare a **Impostazioni** > **Account** > **Accesso società**.
1. Selezionare **Registrati per la gestione dei dispositivi** e immettere l'account dell'organizzazione. Si verrà reindirizzati nella pagina di accesso dell'organizzazione.
1. Dopo l'autenticazione riuscita al server MDM, viene visualizzato un messaggio di conferma.

Il dispositivo è ora registrato nel server MDM. L'app Impostazioni rifletterà ora la registrazione del dispositivo nella gestione dei dispositivi.

## Annullare la registrazione di HoloLens da Intune

Non puoi [annullare la registrazione](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens da Intune in modalità remota. Se l'amministratore annulla la registrazione del dispositivo tramite MDM, il dispositivo verrà eliminato dal dashboard di Intune.
