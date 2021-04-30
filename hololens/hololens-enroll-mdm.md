---
title: Registrare HoloLens in MDM
description: Informazioni su come registrare HoloLens nella gestione di dispositivi mobili (MDM) per semplificare la gestione di più dispositivi.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309713"
---
# <a name="enroll-hololens-in-mdm"></a>Registrare HoloLens in MDM

È possibile gestire più Microsoft HoloLens contemporaneamente usando soluzioni come [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Sarà possibile gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell'organizzazione. Vedere Gestire i dispositivi che eseguono [Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), i provider di servizi di configurazione [(CSP) supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)e i criteri supportati [da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La gestione dei dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e in modalità tutto schermo, è disponibile solo quando si esegue l'aggiornamento [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisiti

 Per gestire i dispositivi HoloLens, l'organizzazione dovrà avere la gestione dei dispositivi mobili (MDM). Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.
 
## <a name="different-ways-to-enroll"></a>Diversi modi per eseguire la registrazione

A seconda del tipo di [identità](hololens-identity.md) scelto durante la Procedura guidata o dopo l'accesso, esistono diversi metodi di registrazione.

- Se l'opzione Identità è Azure AD, durante la configurazione o le impostazioni di **Accesso all'app** il pulsante Work or School Connect (Accesso all'app aziendale  ->  **o dell'istituto di**  ->  **istruzione).**
    - Ad Azure AD, [la registrazione MDM automatica](hololens-enroll-mdm.md#auto-enrollment-in-mdm) viene eseguita solo se Azure AD è stato configurato con gli URL di registrazione.
     
- Se l'identità è Azure AD e il dispositivo è stato preregistrato con il server MDM di Intune con un profilo di configurazione specifico assegnato, durante la configurazione guidata verrà eseguita la registrazione automatica di Azure AD-Join [e MDM.](hololens-enroll-mdm.md#auto-enrollment-in-mdm)
    - Chiamato anche [flusso di Autopilot](hololens2-autopilot.md) disponibile nelle [build 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).
    

- Se Identity è MSA, usare il pulsante Settings App Access Work or School Connect (Accesso **all'app**  ->  **aziendale o dell'istituto**  ->  **di** istruzione Connect).
    - Chiamato anche flusso Add Work Account (AWA).
- Se Identità è Utente locale, usare il collegamento Impostazioni **Accesso all'app** Solo registrazione aziendale o dell'istituto di  ->    ->  istruzione nel collegamento **di gestione dei** dispositivi.
    - Chiamato anche flusso di registrazione MDM puro.

Dopo aver registrato il dispositivo con il server MDM, l'app Impostazioni rifletterà che il dispositivo è registrato nella gestione dei dispositivi.

## <a name="auto-enrollment-in-mdm"></a>Registrazione automatica in MDM

Se l'organizzazione ha una sottoscrizione [Di Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token Azure AD per l'autenticazione (attualmente supportata solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD per consentire automaticamente la registrazione MDM dopo l'accesso dell'utente con il proprio account Azure AD. [Informazioni su come configurare la registrazione di Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando la registrazione automatica è abilitata, non è necessaria alcuna registrazione manuale aggiuntiva. Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.

Quando un dispositivo viene Azure AD aggiunto, può influire su chi ha considerato il [proprietario del dispositivo.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Annullare la registrazione di HoloLens da Intune

A seconda del metodo di registrazione, la annullamento della registrazione del dispositivo potrebbe non essere disponibile.

Se il dispositivo è stato registrato con un account Azure AD o Autopilot, non è possibile annullarlo da Intune. Se si vuole scollegare HoloLens da Azure AD o ricongiungerlo a un tenant diverso da Azure AD, è necessario [reimpostare/ripristinare](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) il dispositivo.

Se il dispositivo è stato registrato da un account msa che ha aggiunto un account aziendale o da un account locale registrato solo nella gestione dei dispositivi, è possibile annullare la registrazione del dispositivo. Aprire il menu Start e quindi selezionare Impostazioni **Accesso all'app** Work  ->  **or School**  ->  YourAccount Disconnect  ->  **(Disconnetti** account).