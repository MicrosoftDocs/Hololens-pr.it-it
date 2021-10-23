---
title: Registrare HoloLens in MDM
description: Informazioni su come registrare HoloLens nella gestione di dispositivi mobili (MDM) per semplificare la gestione di più dispositivi.
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
ms.openlocfilehash: 9f466abe45a1a9ad676f8dd6a94244473c084be7
ms.sourcegitcommit: 38b5e4d92da6fc5d6a6a2ef875644d6db2cce822
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "130202880"
---
# <a name="enroll-hololens-in-mdm"></a>Registrare HoloLens in MDM

È possibile gestire più Microsoft HoloLens contemporaneamente usando soluzioni come [Microsoft Intune](/intune/windows-holographic-for-business). Sarà possibile gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza personalizzate in base alle esigenze dell'organizzazione. Vedere Gestire i dispositivi che eseguono [Windows Holographic](/intune/windows-holographic-for-business)con Microsoft Intune , i provider di servizi di configurazione [(CSP) supportati in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)e i criteri supportati [da Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La gestione dei dispositivi mobili (MDM), incluse le funzionalità VPN, Bitlocker e in modalità tutto schermo, è disponibile solo quando si esegue l'aggiornamento [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisiti

 L'organizzazione dovrà avere la gestione dei dispositivi mobili (MDM) impostata per gestire i HoloLens mobili. Il provider MDM può essere Microsoft Intune o un provider di terze parti che usa le API di Microsoft MDM.

## <a name="different-ways-to-enroll"></a>Diversi modi per eseguire la registrazione

A seconda del tipo di [identità](hololens-identity.md) scelto durante la Procedura guidata o dopo l'accesso, esistono diversi metodi di registrazione.

- Se l'identità è Azure AD, durante la Gestione Impostazioni o **l'accesso all'app** il Connessione aziendale  ->    ->  **o dell'istituto di** istruzione.
    - Ad Azure AD, [la registrazione MDM automatica](hololens-enroll-mdm.md#auto-enrollment-in-mdm) viene eseguita solo se Azure AD è stato configurato con gli URL di registrazione.

- Se l'identità è Azure AD e il dispositivo è stato preregistrato con il server MDM di Intune con un profilo di configurazione specifico assegnato, durante la configurazione guidata verrà eseguita la registrazione automatica AD-Join Azure AD-Join [MDM.](hololens-enroll-mdm.md#auto-enrollment-in-mdm)
    - Chiamato anche [flusso di Autopilot](hololens2-autopilot.md) Disponibile nelle [build 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).


- Se Identity è MSA, usare il pulsante Impostazioni App Access Work or School (Accesso **all'app** aziendale  ->    ->  **Connessione dell'istituto di** istruzione).
    - Chiamato anche flusso Add Work Account (AWA).
- Se l'identità è Utente locale, usare il collegamento Impostazioni **accesso all'app** Solo registrazione aziendale o dell'istituto di istruzione nella  ->    ->  **gestione dei** dispositivi.
    - Chiamato anche flusso di registrazione MDM puro.

Dopo aver registrato il dispositivo con il server MDM, l'app Impostazioni rifletterà che il dispositivo è registrato nella gestione dei dispositivi.

## <a name="auto-enrollment-in-mdm"></a>Registrazione automatica in MDM

Se l'organizzazione ha una sottoscrizione di [Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) e una soluzione MDM che accetta un token Azure AD per l'autenticazione (attualmente supportata solo in Microsoft Intune e AirWatch), l'amministratore IT può configurare Azure AD consentire automaticamente la registrazione MDM dopo che l'utente accede con il Azure AD account. [Informazioni su come configurare la registrazione Azure AD e](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) [l'integrazione di Azure Active Directory con MDM](/windows/client-management/mdm/azure-active-directory-integration-with-mdm) per informazioni dettagliate.

Quando la registrazione automatica è abilitata, non è necessaria alcuna registrazione manuale aggiuntiva. Quando l'utente accede con un account Azure AD, il dispositivo viene registrato in MDM dopo aver completato l'esperienza di prima esecuzione.

Quando un dispositivo viene aggiunto Azure AD può influire su chi ha considerato il [proprietario del dispositivo.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Annullare la registrazione HoloLens da Intune

A seconda del metodo di registrazione, l'annullamento della registrazione del dispositivo potrebbe non essere disponibile.

Se il dispositivo è stato registrato con un account Azure AD o Autopilot, non è possibile annullarlo da Intune. Se si vuole annullare l'HoloLens da Azure AD o ricongiungerlo a un tenant diverso da Azure AD, è necessario reimpostare [o](hololens-recovery.md#restart-the-device) ripristinare il dispositivo.

Se il dispositivo è stato registrato da un account msa che ha aggiunto un account aziendale o da un account locale registrato solo nella gestione dei dispositivi, è possibile annullare la registrazione del dispositivo. Aprire il menu Start e quindi selezionare il Impostazioni **App**  ->  **Access Work or School**  ->  YourAccount Disconnect  ->  **(Disconnetti** account personale o dell'istituto di istruzione).

## <a name="enrollment-troubleshooting"></a>Risoluzione dei problemi di registrazione

### <a name="ensure-device-is-successfully-connected-to-internet-before-attempting-enrollment-post-oobe"></a>Verificare che il dispositivo sia connesso a Internet prima di provare a eseguire la registrazione dopo la configurazione guidata

Dopo che l'utente ha eseguito l'accesso, verificare la connessione Internet visitando qualsiasi sito Web con connessione Internet nel dispositivo.

### <a name="ensure-that-azure-active-directory-aad-join-is-not-disabled-in-your-aad-tenant"></a>Assicurarsi che Azure Active Directory join (AAD) non sia disabilitato nel tenant AAD

Fare riferimento [a Configurare le impostazioni del dispositivo](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) per informazioni sulle opzioni disponibili in portale di Azure.

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Assicurarsi che all'utente sia assegnata una licenza valida

Vedere Risolvere i Windows problemi di registrazione dei dispositivi [Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) in [](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) particolare nelle sezioni seguenti, ad esempio Controllare le restrizioni del tipo di dispositivo e Assegnare una licenza [valida all'utente.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Assicurarsi che la registrazione MDM non sia bloccata per i Windows mobili

Per consentire la registrazione, è necessario assicurarsi che i dispositivi HoloLens possano essere registrati. Poiché HoloLens è considerato un Windows dispositivo, non sarà necessario che non siano presenti restrizioni di registrazione che potrebbero bloccare la distribuzione. [Esaminare questo elenco di restrizioni](/mem/intune/enrollment/enrollment-restrictions-set) e assicurarsi che sia possibile registrare i dispositivi.
