---
title: Registrare HoloLens in MDM
description: Informazioni su come registrare HoloLens gestione dei dispositivi mobili (MDM) per semplificare la gestione di più dispositivi.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b6206f7121d1ba78908d96f71c5c809ec97b06d5
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904345"
---
# <a name="enroll-hololens-in-mdm"></a>Registrare HoloLens in MDM

È possibile gestire più Microsoft HoloLens contemporaneamente usando soluzioni come [Microsoft Intune](/intune/windows-holographic-for-business). Sarà possibile gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell'organizzazione. Vedere Gestire i dispositivi che eseguono [Windows Holographic](/intune/windows-holographic-for-business)con Microsoft Intune , i provider di servizi di configurazione [supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)e i criteri supportati da [Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La gestione dei dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e in modalità tutto schermo, è disponibile solo quando si esegue l'aggiornamento [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisiti

 L'organizzazione dovrà avere la gestione dei dispositivi mobili (MDM) impostata per gestire i HoloLens mobili. Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.

## <a name="different-ways-to-enroll"></a>Diversi modi per la registrazione

A seconda del tipo di [identità](hololens-identity.md) scelto durante la Procedura guidata o dopo l'accesso, esistono diversi metodi di registrazione.

- Se l'identità è Azure AD, durante la Impostazioni OOBE o l'accesso **all'app** o  ->    ->  **all'istituto di** istruzione Connessione pulsante.
    - Ad Azure AD, [la registrazione MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) automatica viene eseguita solo se Azure AD è stato configurato con GLI URL di registrazione.

- Se Identity è Azure AD e il dispositivo è stato preregistrato nel server MDM di Intune con un profilo di configurazione specifico assegnato, azure AD-Join e la registrazione [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) automatica verranno eseguite durante la configurazione guidata.
    - Chiamato anche [flusso Di Autopilot](hololens2-autopilot.md) disponibile nelle [build 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).


- Se Identity è MSA, usare Impostazioni **app**  ->  **Access Work or School**  ->  **Connessione** pulsante.
    - Chiamato anche flusso Add Work Account (AWA).
- Se l'identità è Utente locale, l'uso Impostazioni **app**  ->  **Access Work or School** Enroll only in device management link (Registrazione aziendale o dell'istituto di istruzione) solo nel collegamento di gestione  ->  **dei** dispositivi.
    - Chiamato anche flusso di registrazione MDM puro.

Dopo la registrazione del dispositivo con il server MDM, l'app Impostazioni rifletterà che il dispositivo è registrato nella gestione dei dispositivi.

## <a name="auto-enrollment-in-mdm"></a>Registrazione automatica in MDM

Se l'organizzazione ha una sottoscrizione di [Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token Azure AD per l'autenticazione (attualmente supportata solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD per consentire automaticamente la registrazione MDM dopo che l'utente accede con il proprio account Azure AD. [Informazioni su come configurare la registrazione di Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando la registrazione automatica è abilitata, non è necessaria alcuna registrazione manuale aggiuntiva. Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.

Quando un dispositivo viene Azure AD aggiunto, può influire su chi ha considerato il [proprietario del dispositivo.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Annullare la registrazione HoloLens da Intune

A seconda del metodo di registrazione, la annullamento della registrazione del dispositivo potrebbe non essere disponibile.

Se il dispositivo è stato registrato con un account Azure AD o Autopilot, non è possibile annullarlo da Intune. Se si vuole annullare l'HoloLens da Azure AD o ricongiungerlo a un tenant diverso da quello Azure AD, è necessario [reimpostare/ripristinare](hololens-recovery.md#reset-the-device) il dispositivo.

Se il dispositivo è stato registrato da un account msa che ha aggiunto un account aziendale o da un account locale registrato solo nella gestione dei dispositivi, è possibile annullare la registrazione del dispositivo. Aprire il menu Start e quindi selezionare il pulsante Impostazioni **App**  ->  **Access Work or School**  ->  YourAccount Disconnect  ->  **(Disconnetti** account personale dell'istituto di istruzione).

## <a name="enrollment-troubleshooting"></a>Risoluzione dei problemi relativi alla registrazione

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Assicurarsi che all'utente sia assegnata una licenza valida

Fare riferimento a Risolvere Windows problemi di registrazione dei dispositivi [in](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) [](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) Microsoft Intune in particolare le sezioni seguenti, ad esempio Controllare le restrizioni del tipo di dispositivo e Assegnare una licenza valida [all'utente.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Assicurarsi che la registrazione MDM non sia bloccata per i Windows mobili

Per consentire la riuscita della registrazione, è necessario assicurarsi che i dispositivi HoloLens possano essere registrati. Poiché HoloLens è considerato un dispositivo Windows non sarà necessario applicare restrizioni di registrazione che potrebbero bloccare la distribuzione. [Esaminare questo elenco di restrizioni](/mem/intune/enrollment/enrollment-restrictions-set) e assicurarsi di poter registrare i dispositivi.