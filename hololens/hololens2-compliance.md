---
title: HoloLens 2 conformità e PILR
description: Documentazione di PILR
keywords: HoloLens, PILR, privacy, PII
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
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324874"
---
# Informativa sulla privacy di HoloLens 2

Uno degli elementi principali di PILR è "protezione dei dati tramite progettazione". Questo concetto si applica soprattutto ai dispositivi mobili, come HoloLens 2, a causa della loro portabilità, connessioni Internet illimitate e canali di comunicazione aperti. La [sicurezza](https://docs.microsoft.com/hololens/security-architecture) di HoloLens 2 è stata riprogettata per assicurare una protezione avanzata e innovativa per la sicurezza e la privacy, che incorpora sia l'approccio Microsoft per la [privacy che le normative PILR](https://privacy.microsoft.com/).

 >[!NOTE]
> Questo documento non si applica a HoloLens (1st Gen).

## Panoramica sulla privacy

HoloLens 2 è un computer Windows indipendente, che esegue Windows olografico, che esegue App e soluzioni in un ambiente di realtà mista immersiva. Può essere usato come dispositivo offline sicuro o distribuito come [dispositivo gestito](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) all'interno dell'organizzazione. Per informazioni su come usare HoloLens 2 e Microsoft e proteggere i dati, vedere i collegamenti seguenti:
1. [Informativa sulla privacy Microsoft-HoloLens](https://privacy.microsoft.com/privacystatement) -espandere la sezione **Enterprise e Developer** nel menu di spostamento a sinistra e selezionare **software e appliance aziendali e per sviluppatori**. Accedere alla sezione **HoloLens** .
2.  [Windows 10 e i tuoi servizi online](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 e conformità in materia di privacy: guida](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Privacy e dati personali in Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## Sicurezza di rete
Dopo gli scenari di [distribuzione comuni](https://docs.microsoft.com/hololens/common-scenarios)di HoloLens 2, i dati verranno protetti dalla [conformità di classe mondiale di Azure](https://docs.microsoft.com/azure/compliance/) insieme all'integrazione di standard legali/normativi. Se si è nuovi ad Azure AD e Dynamics 365 Remote Assist, fare riferimento all' [elenco di controllo di conformità di Azure e dynamics 365 per il PILR](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics).

Inoltre, Windows Defender Firewall offre funzionalità critiche per garantire la connettività del dispositivo. Con HoloLens 2, il firewall è sempre abilitato e non sono disponibili modi per disabilitarlo a livello di programmazione o tramite l'interfaccia utente. Quando HoloLens 2 viene distribuito come dispositivo gestito tramite [Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started), è disponibile una maggiore funzionalità di conformità con Integration for [endpoint con Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) come soluzione per la difesa delle minacce per dispositivi mobili. 

Leggi altre informazioni sulla [sicurezza e l'architettura](https://docs.microsoft.com/hololens/security-architecture)di HoloLens 2.

## Sicurezza del sistema operativo
Gli aggiornamenti vengono eseguiti automaticamente (per impostazione predefinita) in modo che il HoloLens 2 sia sempre aggiornato con l'ultima versione di Windows olografico e tutte le app installate. Per altre informazioni su come il sistema operativo è stato progettato in modo sicuro, vedere quanto segue:
1. [Separazione e isolamento dello stato](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Sistema operativo senza amministratore](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Limitare l'uso delle password](https://docs.microsoft.com/hololens/security-limiting-password-use)

## Sicurezza fisica
HoloLens 2 include la memoria flash protetta dalla [crittografia BitLocker](https://docs.microsoft.com/hololens/security-encryption-data-protection). Il dispositivo e i relativi dati locali possono essere infiammati offline usando il [compagno di ripristino avanzato](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) o eliminati in remoto tramite MDM se è stato distribuito come dispositivo gestito.

## Protezione dei dati
Gli aggiornamenti di Windows vengono eseguiti automaticamente (per impostazione predefinita) e l' [integrazione di Azure](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) protegge i dati che viaggiano tra sé e il cloud. 

Quando si distribuisce HoloLens 2 a client esterni, [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) garantisce che i dati e le risorse aziendali sensibili siano separati e sicuri. 

La condivisione dei dati di diagnostica con Microsoft può essere configurata manualmente da MDM o dall'utente durante la configurazione guidata. Esistono due opzioni: i dati di diagnostica facoltativi e i dati di diagnostica necessari. Se l'impostazione di diagnostica originale deve essere modificata in un secondo momento per scopi di risoluzione dei problemi, può essere modificata dall'utente in **Impostazioni-> privacy-> diagnostica & feedback** o l'amministratore IT (MDM) se è un dispositivo gestito. Per altre informazioni [, vedere diagnostica, feedback e privacy in Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> I log di diagnostica del dispositivo contengono informazioni personali, ad esempio i processi o le applicazioni che l'utente avvia durante le operazioni tipiche. Quando più utenti condividono un dispositivo HoloLens, ad esempio gli utenti accedono allo stesso dispositivo usando diversi account di Microsoft Azure Active Directory (Azure AD), i log di diagnostica potrebbero contenere informazioni personali che si applicano a più utenti.

 

Sono disponibili [diversi metodi di raccolta e criteri di conservazione dei dati](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) per la raccolta di dati diagnostici da HoloLens 2.  Per altre informazioni sul modo in cui Microsoft raccoglie e usa i dati di diagnostica, vedere [informativa sulla privacy Microsoft-diagnostica](https://privacy.microsoft.com/privacystatement) -espandere **Windows** nel menu di spostamento a sinistra e selezionare **diagnostica**. Accedere alla sezione **diagnostica** .
