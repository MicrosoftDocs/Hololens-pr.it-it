---
title: HoloLens 2 Privacy e protezione dei dati
description: Documentazione sulla privacy
keywords: HoloLens, GDPR, privacy, informazioni personali, protezione dei dati
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032619"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2 Privacy e protezione dei dati

Uno degli elementi principali del GDPR è la "protezione dei dati in base alla progettazione". Questo concetto si applica in particolare ai dispositivi mobili, come HoloLens 2, a causa della portabilità, delle connessioni Internet illimitate e dei canali di comunicazione aperti. Di conseguenza, la sicurezza del [](/hololens/security-architecture) HoloLens 2 è stata riprogettata per fornire sicurezza avanzata e innovative e protezione della privacy, end-to-end, incorporando sia l'approccio di Microsoft alla privacy che alle normative [GDPR.](https://privacy.microsoft.com/)

 >[!NOTE]
> Questo documento non si applica a HoloLens (prima generazione).

## <a name="privacy-overview"></a>Panoramica sulla privacy

HoloLens 2 è un computer Windows autonomo, che esegue Windows Holographic, che esegue app e soluzioni in un ambiente di realtà mista immersiva. Può essere usato come dispositivo offline sicuro o distribuito come [dispositivo gestito all'interno](/mem/intune/fundamentals/windows-holographic-for-business) dell'organizzazione. Vedere i collegamenti seguenti per comprendere in che modo HoloLens 2 e Microsoft utilizzano e proteggono i dati:

1. Informativa sulla privacy microsoft [- HoloLens:](https://privacy.microsoft.com/privacystatement) espandere la sezione Enterprise e sviluppatore nel menu di spostamento a sinistra e selezionare Enterprise software e **appliance** per sviluppatori.  Passare alla sezione **HoloLens.**
2. [Windows 10 e il Servizi online](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & Privacy Compliance Guide (Guida alla conformità alla privacy di Windows 10 &)](/windows/privacy/windows-10-and-privacy-compliance)
4. [Privacy e dati personali in Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Sicurezza di rete
Seguendo le HoloLens 2 [comuni](/hololens/common-scenarios)di distribuzione, i dati saranno protetti dalla conformità di livello mondiale di Azure insieme [all'integrazione](/azure/compliance/) degli standard legali/normativi. Se non si ha Azure AD e Dynamics 365 Remote Assist, fare riferimento all'elenco di controllo di conformità alla responsabilità di Azure e [Dynamics 365 per GDPR.](/compliance/regulatory/gdpr-arc-azure-dynamics)

Inoltre, Windows Defender Firewall offre funzionalità critiche per proteggere la connettività dei dispositivi. Con HoloLens 2, il firewall è sempre abilitato e non è possibile disabilitarlo a livello di codice o tramite l'interfaccia utente. Quando il HoloLens 2 viene distribuito come dispositivo gestito con [Intune,](/mem/intune/protect/device-compliance-get-started)sono disponibili altre funzionalità di conformità con l'integrazione per Endpoint con [Microsoft Intune](/mem/intune/protect/advanced-threat-protection) come soluzione Mobile Threat Defense.

Altre informazioni sulla sicurezza HoloLens 2 [e sull'architettura.](/hololens/security-architecture)

## <a name="os-security"></a>Sicurezza del sistema operativo
Gli aggiornamenti vengono emersi automaticamente (per impostazione predefinita) in modo che il HoloLens 2 sia sempre aggiornato con la versione più recente di Windows Holographic e di tutte le app installate. Per altre informazioni su come il sistema operativo è progettato in modo sicuro, vedere quanto segue:

1. [Separazione e isolamento dello stato](/hololens/security-state-separation-isolation)
1. [Sistema operativo senza amministratore](/hololens/security-adminless-os)
1. [Limitazione dell'uso delle password](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Sicurezza fisica
HoloLens 2 memoria flash protetta dalla crittografia [BitLocker.](/hololens/security-encryption-data-protection) Il dispositivo e i relativi dati locali possono essere flash offline usando [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) o cancellati in remoto tramite MDM se è stato distribuito come dispositivo gestito.

## <a name="data-protection"></a>Protezione dei dati
Windows gli aggiornamenti vengono eseguiti automaticamente (per impostazione predefinita) e [l'integrazione](/hololens/security-encryption-data-protection#Azure-integration) di Azure protegge i dati che viaggiano tra se stesso e il cloud.

Quando si distribuiscono HoloLens 2 client [esterni,](/hololens/hololens2-deployment-guide) Dynamics 365 Remote Assist che i dati e le risorse aziendali sensibili siano separati e sicuri.

La condivisione dei dati di diagnostica con Microsoft può essere configurata manualmente da MDM o dall'utente durante la configurazione. Sono disponibili due opzioni: Dati di diagnostica facoltativi e Dati di diagnostica obbligatori. Se l'impostazione di diagnostica originale deve essere modificata in un secondo momento per la risoluzione dei problemi, può essere modificata dall'utente in **Impostazioni -> Privacy -> Diagnostics & Feedback** o it admin (MDM) se è un dispositivo gestito. Vedere altre informazioni [su diagnostica, feedback e privacy in Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> I log di diagnostica dei dispositivi contengono informazioni personali, ad esempio sui processi o le applicazioni avviati dall'utente durante le operazioni tipiche. Quando più utenti condividono un dispositivo HoloLens (ad esempio, gli utenti a tale dispositivo a cui a loro volta a loro volta usano account Microsoft Azure Active Directory (Azure AD) diversi, i log di diagnostica possono contenere informazioni personali applicabili a più utenti.

Esistono diversi [metodi di raccolta e criteri di conservazione dei](/hololens/hololens-diagnostic-logs) dati per la raccolta dei dati di diagnostica dal HoloLens 2.  Per altre informazioni su come Microsoft raccoglie e usa i dati di diagnostica, vedere Informativa sulla privacy microsoft [-](https://privacy.microsoft.com/privacystatement) Diagnostica **-** espandere Windows nel menu di spostamento a sinistra e selezionare **Diagnostica**. Passare alla **sezione** Diagnostica.
