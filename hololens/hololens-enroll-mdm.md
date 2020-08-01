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
ms.openlocfilehash: 1dd6c2e6cde980b86ac810f82d27b3b88f20f336
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903222"
---
# Registrare HoloLens in MDM

Puoi gestire più dispositivi Microsoft HoloLens simultaneamente usando soluzioni come [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Potrai gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell’organizzazione. Vedi [Gestire i dispositivi che eseguono Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), i [provider di servizi di configurazione (CSP) che sono supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e i [criteri supportati da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gestione di dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e della modalità tutto schermo, è disponibile solo quando [esegui l'aggiornamento a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requisiti

 L'organizzazione dovrà configurare la gestione di dispositivi mobili (MDM) per la gestione dei dispositivi HoloLens. Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.
 
## Diversi modi per iscriversi

A seconda del tipo di identità scelto durante la configurazione OOBE o post-accesso sono disponibili diversi metodi di registrazione. Per altre informazioni su ogni tipo di identità in HoloLens, visitare [Questa pagina](hololens-identity.md).

- Se Identity è AAD, è possibile che durante l'accesso all'app OOBE o **le impostazioni**di  ->  **Access o**il pulsante School  ->  **Connect** .
    - Per AAD, la registrazione automatica MDM si verifica solo se AAD è stato configurato con gli URL di registrazione.
- Se l'identità è AAD e il dispositivo è stato pre-registrato con Intune MDM server con il profilo di configurazione specifico assegnato, quindi AAD-join e registrazione si verificheranno automaticamente durante la configurazione guidata.
    - Chiamato anche [flusso Autopilot](hololens2-autopilot.md) disponibile in [19041.1103 + Build](hololens-release-notes.md#windows-holographic-version-2004).
- Se l'identità è MSA, usare **le impostazioni**di  ->  **accesso all'app o al pulsante School**  ->  **Connect** .
    - Denominato anche flusso di Add work account (AWA).
- Se l'identità è un utente locale, usare **le impostazioni**  ->  di accesso all'app**o dell'Istituto**  ->  **di istruzione per la registrazione solo in collegamento Gestione dispositivi** .
    - Chiamata anche flusso di registrazione MDM puro.

Una volta che il dispositivo è stato registrato con il server MDM, l'app Impostazioni rifletterà ora che il dispositivo è registrato in gestione dispositivi.

## Registrazione automatica in MDM

Se l'organizzazione usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token AAD per l'autenticazione (attualmente supportato solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD in modo da consentire automaticamente la registrazione MDM dopo l'accesso dell'utente con l'account Azure AD. [Informazioni su come configurare la registrazione di Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando è abilitata la registrazione automatica, non è necessaria alcuna registrazione manuale aggiuntiva. Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.

## Annullare la registrazione di HoloLens da Intune

Per ulteriori informazioni su come annullare la registrazione di un dispositivo, visitare [Questa pagina](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment). 
