---
title: Preparare certificati e profili di rete per HoloLens 2
description: Come configurare e usare certificati per la rete nei dispositivi HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 460b6f42de7413e77eaec041a5ab6141ed959cf4
ms.sourcegitcommit: 9944fd2040fc1267ace1da1bd62ef36b68c7f318
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015523"
---
# Preparare certificati e profili di rete per HoloLens 2

L'autenticazione basata su certificato è un requisito comune per i clienti che usano HoloLens 2. Potrebbe essere necessario disporre di certificati per accedere alla rete Wi-Fi, per connettersi a soluzioni VPN o per accedere alle risorse interne dell'organizzazione.

Poiché i dispositivi HoloLens 2 sono in genere collegati a Azure Active Directory (Azure AD) e gestiti da Intune o da un altro provider MDM, sarà necessario distribuire tali certificati con un'infrastruttura SCEP (Simple Certification Protocol) o PKCS (Public Key Cryptography Standard) integrate con la soluzione MDM.

## Requisiti dei certificati
I certificati radice sono necessari per distribuire i certificati tramite un'infrastruttura SCEP o PKCS. Anche altre applicazioni e servizi dell'organizzazione possono richiedere la distribuzione dei certificati radice ai dispositivi di HoloLens 2. 

## Requisiti di connettività di rete Wi-Fi
Per consentire la configurazione automatica di un dispositivo con la configurazione Wi-Fi necessaria per la rete aziendale, è necessario un profilo di configurazione Wi-Fi. È possibile configurare Intune o un altro provider MDM per distribuire questi profili nei dispositivi. Se la sicurezza della rete richiede che i dispositivi facciano parte del dominio locale, potrebbe anche essere necessario valutare l'infrastruttura di rete Wi-Fi per assicurarsi che sia compatibile con i dispositivi di HoloLens 2 (i dispositivi HoloLens 2 sono collegati solo AD Azure AD).

## Distribuire infrastruttura di certificato.
Se non è già presente un'infrastruttura SCEP o PKCS, è necessario prepararne una. Per supportare l'uso dei certificati SCEP o PKCS per l'autenticazione, Intune richiede l'uso di un [connettore di certificato](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Se si usa SCEP con una CA Microsoft, è necessario configurare anche il [servizio di registrazione dei dispositivi di rete (registrazione dispositivi)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Per altre informazioni, vedere [Configurare il profilo di un certificato per i dispositivi in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)

## Distribuire certificati e profilo Wi-Fi/VPN
Per distribuire certificati e profili, eseguire le operazioni seguenti:
1.  Creare un profilo per ognuno dei certificati radice e intermedi. vedere [Creare profili di certificati attendibili](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles). Ognuno di questi profili deve contenere una descrizione che includa una data di scadenza nel formato gg/MM/AAAA. **I profili di certificato senza data di scadenza non verranno distribuiti.**
1.  Creare un profilo per ognuno dei certificati SCEP o PKCS. vedere [Creare un profilo di certificato SCEP attendibile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile). Ognuno di questi profili deve contenere una descrizione che includa una data di scadenza nel formato gg/MM/AAAA. **I profili di certificato senza data di scadenza non verranno distribuiti.**

> [!NOTE]
> Quando HoloLens 2 viene considerato come un dispositivo condiviso, più utenti per dispositivo, è consigliabile distribuire i certificati per dispositivi anziché i certificati utente per l'autenticazione Wi-Fi, se possibile.

3.  Creare un profilo per ogni rete Wi-Fi aziendale (vedere [le impostazioni Wi-Fi per Windows 10 e i dispositivi successivi](https://docs.microsoft.com/intune/wi-fi-settings-windows)). 
> [!NOTE]
> Se possibile, è consigliabile il profilo Wi-Fi[assegnato](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) ai gruppi di dispositivi anziché ai gruppi di utenti. 

> [!TIP]
> È anche possibile esportare un profilo Wi-Fi funzionante da un PC con Windows 10 nella rete aziendale. Questa esportazione crea un file XML con tutte le impostazioni correnti. Quindi, importare il file in Intune e usarlo come profilo Wi-Fi per i dispositivi HoloLens 2. Per i dispositivi Windows, vedere [Esportare e importare le impostazioni di Wi-Fi.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Creare un profilo per ogni VPN aziendale (vedere [Impostazioni dei dispositivi olografici per Windows 10 e Windows per aggiungere connessioni VPN con Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).




