---
title: Registrare HoloLens in MDM
description: Informazioni su come iscriversi a HoloLens in gestione di dispositivi mobili (MDM) per semplificare la gestione di più dispositivi.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b9473f4e80f6438ef4c438711ac0de342c5327e1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283187"
---
# Registrare HoloLens in MDM

Puoi gestire più dispositivi Microsoft HoloLens simultaneamente usando soluzioni come [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Potrai gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell’organizzazione. Vedi [Gestire i dispositivi che eseguono Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), i [provider di servizi di configurazione (CSP) che sono supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e i [criteri supportati da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gestione di dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e della modalità tutto schermo, è disponibile solo quando [esegui l'aggiornamento a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requisiti

 L'organizzazione dovrà configurare la gestione di dispositivi mobili (MDM) per la gestione dei dispositivi HoloLens. Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.
 
## Diversi modi per iscriversi

A seconda del tipo di identità scelto durante la configurazione OOBE o post-accesso sono disponibili diversi metodi di registrazione. Per altre informazioni su ogni tipo di identità in HoloLens, visitare [Questa pagina](hololens-identity.md).

- Se Identity è Azure ad, è possibile che sia durante l'accesso all'app OOBE o **le impostazioni**di  ->  **Access o**il pulsante School  ->  **Connect** .
    - Per Azure AD, la registrazione automatica MDM si verifica solo se Azure AD è stato configurato con gli URL di registrazione.
- Se Identity è Azure AD e Device è stato pre-registrato con il server di Intune MDM con il profilo di configurazione specifico assegnato, quindi Azure AD-Join e la registrazione si verificheranno automaticamente durante la configurazione guidata.
    - Chiamato anche [flusso Autopilot](hololens2-autopilot.md) disponibile in [19041.1103 + Build](hololens-release-notes.md#windows-holographic-version-2004).
- Se l'identità è MSA, usare **le impostazioni**di  ->  **accesso all'app o al pulsante School**  ->  **Connect** .
    - Denominato anche flusso di Add work account (AWA).
- Se l'identità è un utente locale, usare **le impostazioni**  ->  di accesso all'app**o dell'Istituto**  ->  **di istruzione per la registrazione solo in collegamento Gestione dispositivi** .
    - Chiamata anche flusso di registrazione MDM puro.

Una volta che il dispositivo è stato registrato con il server MDM, l'app Impostazioni rifletterà ora che il dispositivo è registrato in gestione dispositivi.

## Registrazione automatica in MDM

Se l'organizzazione USA Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token di Azure AD per l'autenticazione (attualmente supportato solo in Microsoft Intune e nell'orologio), l'amministratore IT può configurare Azure AD per consentire automaticamente l'iscrizione a MDM dopo che l'utente ha eseguito l'accesso con il proprio account di Azure AD. [Informazioni su come configurare la registrazione di Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando è abilitata la registrazione automatica, non è necessaria alcuna registrazione manuale aggiuntiva. Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.

Quando un dispositivo è collegato AD Azure AD, può influire su chi ha considerato il [proprietario del dispositivo](security-adminless-os.md#device-owner).

## Annullare la registrazione di HoloLens da Intune

Per ulteriori informazioni su come annullare la registrazione di un dispositivo, visitare [Questa pagina](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment). 
