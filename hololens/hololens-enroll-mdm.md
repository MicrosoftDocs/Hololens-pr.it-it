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
ms.openlocfilehash: a368c622c137374ea9cc544490d3492fa9d3f8c1
ms.sourcegitcommit: 749d617f3f0ce3e6363ff6cd1a03f87b9280f418
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "122979356"
---
# <a name="enroll-hololens-in-mdm"></a>Registrare HoloLens in MDM

È possibile gestire più Microsoft HoloLens dispositivi contemporaneamente usando soluzioni come [Microsoft Intune](/intune/windows-holographic-for-business). Sarà possibile gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell'organizzazione. Vedere Gestire i dispositivi che eseguono [Windows Holographic](/intune/windows-holographic-for-business)con Microsoft Intune , i provider di servizi di configurazione [(CSP) supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)e i criteri supportati [da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La gestione dei dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e in modalità tutto schermo, è disponibile solo quando si esegue [l'aggiornamento a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisiti

 L'organizzazione dovrà avere la gestione dei dispositivi mobili (MDM) impostata per gestire i HoloLens mobili. Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.

## <a name="different-ways-to-enroll"></a>Diversi modi per eseguire la registrazione

A seconda del tipo di [identità](hololens-identity.md) scelto durante la Procedura guidata o dopo l'accesso, esistono diversi metodi di registrazione.

- Se l'identità è Azure AD, durante la Gestione Impostazioni o **l'accesso all'app,** Connessione aziendale o  ->    ->  **dell'istituto di** istruzione.
    - Ad Azure AD, [la registrazione MDM automatica](hololens-enroll-mdm.md#auto-enrollment-in-mdm) viene eseguita solo se Azure AD è stato configurato con gli URL di registrazione.

- Se l'identità è Azure AD e il dispositivo è stato preregistrato con il server MDM [](hololens-enroll-mdm.md#auto-enrollment-in-mdm) di Intune con un profilo di configurazione specifico assegnato, durante la configurazione guidata verrà eseguita la registrazione mdm automatica e azure AD-Join.
    - Chiamato anche [flusso di Autopilot](hololens2-autopilot.md) Disponibile nelle [build 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).


- Se Identity è MSA, usare il pulsante Impostazioni App Access Work or School (Accesso **all'app** aziendale  ->    ->  **o Connessione dell'istituto di** istruzione).
    - Chiamato anche flusso Add Work Account (AWA).
- Se Identity è Local User (Identità) è Local User (Utente locale), Impostazioni **collegamento App** Access Work or School Enroll only (Registrazione aziendale o dell'istituto di  ->    ->  **istruzione) solo nel collegamento di gestione dei** dispositivi.
    - Chiamato anche flusso di registrazione MDM puro.

Dopo che il dispositivo è stato registrato nel server MDM, l'app Impostazioni rifletterà che il dispositivo è registrato nella gestione dei dispositivi.

## <a name="auto-enrollment-in-mdm"></a>Registrazione automatica in MDM

Se l'organizzazione ha una sottoscrizione di [Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token Azure AD per l'autenticazione (attualmente supportata solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD per consentire automaticamente la registrazione MDM dopo che l'utente accede con il proprio account Azure AD. [Informazioni su come configurare la registrazione di Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando la registrazione automatica è abilitata, non è necessaria alcuna registrazione manuale aggiuntiva. Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.

Quando un dispositivo viene aggiunto Azure AD può influire su chi ha considerato il [proprietario del dispositivo.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Annullare la registrazione HoloLens da Intune

A seconda del metodo di registrazione, l'annullamento della registrazione del dispositivo potrebbe non essere disponibile.

Se il dispositivo è stato registrato con un account Azure AD o Autopilot, non è possibile annullarlo da Intune. Se si vuole annullare l'HoloLens da Azure AD o ricongiungerlo a un tenant diverso da Azure AD, è necessario [reimpostare/ripristinare](hololens-recovery.md#reset-the-device) il dispositivo.

Se il dispositivo è stato registrato da un account msa che ha aggiunto un account aziendale o da un account locale registrato solo nella gestione dei dispositivi, è possibile annullare la registrazione del dispositivo. Aprire il menu Start e quindi selezionare il Impostazioni **App**  ->  **Access Work or School** YourAccount Disconnect (Disconnetti account personale o dell'istituto  ->    ->  **di** istruzione).

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Assicurarsi che la registrazione MDM non sia bloccata per Windows dispositivi

Per consentire la registrazione, è necessario assicurarsi che i dispositivi HoloLens possano essere registrati. Poiché HoloLens è considerato un Windows dispositivo, non sarà necessario che non siano presenti restrizioni di registrazione che potrebbero bloccare la distribuzione. [Esaminare questo elenco di restrizioni](/mem/intune/enrollment/enrollment-restrictions-set) e assicurarsi che sia possibile registrare i dispositivi.