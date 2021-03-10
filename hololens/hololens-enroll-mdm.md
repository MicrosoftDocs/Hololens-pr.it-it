---
title: Registrare HoloLens in MDM
description: Scopri come registrare HoloLens nella gestione di dispositivi mobili (MDM) per una gestione più semplice di più dispositivi.
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
ms.openlocfilehash: 4042cce40bea2c3d52d6ffc5d2908f6fde7cf222
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400676"
---
# <a name="enroll-hololens-in-mdm"></a>Registrare HoloLens in MDM

Puoi gestire più dispositivi Microsoft HoloLens contemporaneamente usando soluzioni come [Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business) Potrai gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell’organizzazione. Vedi [Gestire i dispositivi che eseguono Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), i [provider di servizi di configurazione (CSP) che sono supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e i [criteri supportati da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gestione di dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e della modalità tutto schermo, è disponibile solo quando [esegui l'aggiornamento a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisiti

 Per gestire i dispositivi HoloLens, l'organizzazione dovrà configurare Gestione di dispositivi mobili (MDM, Mobile Device Management). Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.
 
## <a name="different-ways-to-enroll"></a>Diversi modi per eseguire la registrazione

A seconda del tipo di [identità](hololens-identity.md) scelto durante la Procedura guidata o dopo l'accesso, esistono diversi metodi di registrazione.

- Se l'identità è Azure AD, allora durante la configurazione predefinita o il pulsante **Impostazioni accesso app**lavoro o  ->  **School**  ->  **Connect.**
    - Per Azure AD, [la registrazione automatica di MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) si verifica solo se Azure AD è stato configurato con gli URL di registrazione. 
     
- Se l'identità è Azure AD e il dispositivo è stato preregistrato con il server MDM intune a cui è assegnato un profilo di configurazione specifico, Azure AD-Join e la registrazione [automatica di MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) verrà eseguita durante la configurazione guidata.
    - Denominato anche [flusso Autopilot](hololens2-autopilot.md) disponibile nelle [build 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Se l'identità è MSA, usa il pulsante Impostazioni **accesso app**lavoro  ->  **o School**  ->  **Connect.**
    - Denominato anche flusso Add Work Account (AWA).
- Se l'identità è Utente locale, usare Impostazioni **accesso app**Lavoro o  ->  **Iscrizione**  ->  **all'istituto di istruzione solo nel collegamento di gestione dei** dispositivi.
    - Chiamato anche flusso di registrazione MDM pura.

Dopo la registrazione del dispositivo con il server MDM, l'app Impostazioni rifletterà che il dispositivo è registrato nella gestione dei dispositivi.

## <a name="auto-enrollment-in-mdm"></a>Registrazione automatica in MDM

Se l'organizzazione ha una sottoscrizione [di Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token Azure AD per l'autenticazione (attualmente supportato solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD per consentire automaticamente la registrazione MDM dopo l'accesso dell'utente con il proprio account Azure AD. [Informazioni su come configurare la registrazione di Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando è abilitata la registrazione automatica, non è necessaria alcuna registrazione manuale aggiuntiva. Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.

Quando un dispositivo è aggiunto ad Azure AD, può influire su chi considera il proprietario [del dispositivo.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Annullare la registrazione di HoloLens da Intune

Anche se HoloLens 2 è un dispositivo Windows 10, non può essere semplicemente rimosso da Intune. Se vuoi scollegare HoloLens da Azure AD o ricongiungerlo a un [](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) tenant diverso da quello di Azure AD, devi reimpostare/riequiliminare il dispositivo.