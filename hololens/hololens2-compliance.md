---
title: HoloLens 2 Conformità e GDPR
description: Documentazione del GDPR
keywords: HoloLens, GDPR, privacy, informazioni personali
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 684a97a4fcdc3aaf830f164c54fb3079e296c78c
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637116"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 Informativa sulla privacy

Uno degli elementi principali del GDPR è la "protezione dei dati per progettazione". Questo concetto si applica in particolare ai dispositivi mobili, come il HoloLens 2, a causa della portabilità, delle connessioni Internet illimitate e dei canali di comunicazione aperti. Di conseguenza, la sicurezza del [](/hololens/security-architecture) HoloLens 2 è stata riprogettata per offrire sicurezza avanzata e innovative e protezione della privacy end-to-end, incorporando sia l'approccio di Microsoft alla privacy che alle normative [GDPR.](https://privacy.microsoft.com/)

 >[!NOTE]
> Questo documento non si applica HoloLens (prima generazione).

## <a name="privacy-overview"></a>Panoramica della privacy

HoloLens 2 è un computer Windows autonomo che esegue Windows Holographic, che esegue app e soluzioni in un ambiente di realtà mista immersiva. Può essere usato come dispositivo offline sicuro o distribuito come [dispositivo gestito](/mem/intune/fundamentals/windows-holographic-for-business) all'interno dell'organizzazione. Vedere i collegamenti seguenti per comprendere in che modo HoloLens 2 e Microsoft utilizzano e proteggono i dati:

1. Informativa sulla privacy di Microsoft  [- HoloLens:](https://privacy.microsoft.com/privacystatement) espandere la sezione Enterprise e developer nel menu di spostamento a sinistra e selezionare Enterprise software e **appliance** per sviluppatori. Passare alla **sezione HoloLens.**
2. [Windows 10 e il Servizi online](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & sulla conformità alla privacy](/windows/privacy/windows-10-and-privacy-compliance)
4. [Privacy e dati personali in Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Sicurezza di rete
Seguendo le HoloLens 2 [comuni di](/hololens/common-scenarios)distribuzione, i dati saranno protetti dalla conformità di livello internazionale di Azure insieme [all'integrazione](/azure/compliance/) degli standard legali/normativi. Se non si ha di Azure AD e Dynamics 365 Remote Assist, fare riferimento all'elenco di controllo per l'idoneità per la responsabilità di Azure e [Dynamics 365 per il GDPR.](/compliance/regulatory/gdpr-arc-azure-dynamics)

Inoltre, Windows Defender firewall offre funzionalità critiche per proteggere la connettività dei dispositivi. Con HoloLens 2, il firewall è sempre abilitato e non è possibile disabilitarlo a livello di codice o tramite l'interfaccia utente. Quando il HoloLens 2 viene distribuito come dispositivo gestito con [Intune,](/mem/intune/protect/device-compliance-get-started)sono disponibili altre funzionalità di conformità con l'integrazione per [Endpoint con Microsoft Intune](/mem/intune/protect/advanced-threat-protection) come soluzione Mobile Threat Defense.

Altre informazioni sulla sicurezza HoloLens 2 [e sull'architettura.](/hololens/security-architecture)

## <a name="os-security"></a>Sicurezza del sistema operativo
Gli aggiornamenti vengono emersi automaticamente (per impostazione predefinita) in modo che il HoloLens 2 sia sempre aggiornato con la versione più recente di Windows Holographic e con tutte le app installate. Per altre informazioni su come il sistema operativo è progettato in modo sicuro, vedere quanto segue:

1. [Separazione e isolamento dello stato](/hololens/security-state-separation-isolation)
1. [Sistema operativo senza amministratore](/hololens/security-adminless-os)
1. [Limitazione dell'uso delle password](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Sicurezza fisica
HoloLens 2 dispone di memoria flash protetta dalla [crittografia BitLocker](/hololens/security-encryption-data-protection). Il dispositivo e i relativi dati locali possono essere flashati offline usando [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) o cancellati in remoto tramite MDM se è stato distribuito come dispositivo gestito.

## <a name="data-protection"></a>Protezione dei dati
Windows aggiornamenti vengono eseguiti automaticamente (per impostazione predefinita) e [l'integrazione](/hololens/security-encryption-data-protection#Azure-integration) di Azure protegge i dati che si spostano tra se stesso e il cloud.

Quando si distribuiscono HoloLens 2 a client [esterni,](/hololens/hololens2-deployment-guide) Dynamics 365 Remote Assist che i dati e le risorse aziendali sensibili siano separati e sicuri.

La condivisione dei dati di diagnostica con Microsoft può essere configurata manualmente da MDM o dall'utente durante la Configurazione fuori rete. Sono disponibili due opzioni: Dati di diagnostica facoltativi e Dati di diagnostica obbligatori. Se l'impostazione di diagnostica originale deve essere modificata in un secondo momento per la risoluzione dei problemi, può essere modificata dall'utente in Impostazioni **-> Privacy -> Diagnostics & Feedback** o dall'amministratore IT (MDM) se è un dispositivo gestito. Per altre informazioni [su diagnostica, commenti e suggerimenti e privacy, Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> I log di diagnostica del dispositivo contengono informazioni personali, ad esempio su quali processi o applicazioni l'utente avvia durante le operazioni tipiche. Quando più utenti condividono un dispositivo HoloLens (ad esempio, gli utenti a cui a loro volta a loro volta a un dispositivo usano account Microsoft Azure Active Directory (Azure AD) diversi), i log di diagnostica possono contenere informazioni personali che si applicano a più utenti.

Esistono diversi [metodi di raccolta e criteri di conservazione dei dati](/hololens/hololens-diagnostic-logs) per raccogliere i dati di diagnostica dal HoloLens 2.  Per altre informazioni su come Microsoft raccoglie e usa i dati di diagnostica, vedere Informativa sulla privacy di [Microsoft -](https://privacy.microsoft.com/privacystatement) Diagnostica - Espandere **Windows** nel menu di spostamento a sinistra e selezionare **Diagnostica.** Passare alla **sezione** Diagnostica.
