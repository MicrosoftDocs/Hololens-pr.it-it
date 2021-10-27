---
title: Preparare i certificati e i profili di rete per HoloLens 2
description: Informazioni su come configurare, usare, distribuire e risolvere i problemi dei certificati per la rete HoloLens 2 dispositivi di realtà mista.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: cf9e14ffbda01bb1fd9e788385f7b85884d1dc8c
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351618"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Preparare i certificati e i profili di rete per HoloLens 2

L'autenticazione basata su certificato è un requisito comune per i clienti che usano HoloLens 2. Potrebbero essere necessari certificati per accedere al Wi-Fi, per connettersi a soluzioni VPN o per accedere alle risorse interne dell'organizzazione.

Poiché i dispositivi HoloLens 2 sono in genere aggiunti a Azure Active Directory (Azure AD) e gestiti da Intune o da un altro provider MDM, è necessario distribuire tali certificati usando un'infrastruttura di certificati Simple Certificate Enrollment Protocol (SCEP) o PKCS (Public Key Cryptography Standard) integrata con la soluzione MDM. 

>[!NOTE]
> Se non si dispone di un provider MDM, è comunque possibile distribuire i certificati tramite un pacchetto di [provisioning](hololens-provisioning.md#create-the-provisioning-package) in Progettazione configurazione [Windows](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) o tramite [Certificate Manager](certificate-manager.md) passando Impostazioni > Update & Security > Certificate **Manager**.

## <a name="certificate-requirements"></a>Requisiti per i certificati
I certificati radice sono necessari per distribuire i certificati tramite un'infrastruttura SCEP o PKCS. Altre applicazioni e servizi nell'organizzazione potrebbero richiedere la distribuzione di certificati radice anche HoloLens 2 dispositivi. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi di connettività
Per consentire a un dispositivo di essere fornito automaticamente con la configurazione Wi-Fi per la rete aziendale, è necessario un Wi-Fi di configurazione. È possibile configurare Intune o un altro provider MDM per distribuire questi profili nei dispositivi. Se la sicurezza di rete richiede che i dispositivi siano parte del dominio locale, potrebbe anche essere necessario valutare l'infrastruttura di rete Wi-Fi per assicurarsi che sia compatibile con i dispositivi HoloLens 2 (i dispositivi HoloLens 2 sono aggiunti solo Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Distribuire l'infrastruttura di certificati
Se non esiste già un'infrastruttura SCEP o PKCS, è necessario prepararne una. Per supportare l'uso di certificati SCEP o PKCS per l'autenticazione, Intune richiede l'uso di un [connettore di certificati](/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Quando si usa SCEP con una CA Microsoft, è necessario configurare anche il servizio Registrazione dispositivi di rete [(NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Per altre informazioni, vedere [Configurare un profilo certificato per i dispositivi in Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Distribuire certificati e profilo Wi-Fi/VPN
Per distribuire certificati e profili, seguire questa procedura:

1.  Creare un profilo per ogni certificato radice e intermedio (vedere [Creare profili certificato attendibili).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Ognuno di questi profili deve avere una descrizione che includa una data di scadenza in formato GG/MM/AAAA. **I profili certificato senza una data di scadenza non verranno distribuiti.**

2.  Creare un profilo per ogni certificato SCEP o PKCS (vedere Creare un profilo certificato SCEP o Creare un profilo certificato [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Ognuno di questi profili deve avere una descrizione che includa una data di scadenza in formato GG/MM/AAAA. **I profili certificato senza una data di scadenza non verranno distribuiti.**

    > [!NOTE]
    > Poiché il HoloLens 2 è considerato per molti un dispositivo condiviso, più utenti per dispositivo, è consigliabile distribuire i certificati del dispositivo anziché i certificati utente per l'autenticazione Wi-Fi laddove possibile

3.  Creare un profilo per ogni rete Wi-Fi aziendale (vedere [Impostazioni Wi-Fi](/intune/wi-fi-settings-windows)per dispositivi Windows 10 e versioni successive). 

    > [!NOTE]
    > È consigliabile assegnare il Wi-Fi a [Gruppi](/mem/intune/configuration/device-profile-assign) di dispositivi anziché a Gruppi di utenti, laddove possibile. 

    > [!TIP]
    > È anche possibile esportare un profilo Wi-Fi lavoro da un PC Windows 10 nella rete aziendale. Questa esportazione crea un file XML con tutte le impostazioni correnti. Importare quindi questo file in Intune e usarlo come profilo Wi-Fi per i HoloLens 2 dispositivi. Vedere [Esportare e importare Wi-Fi impostazioni per Windows dispositivi.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Creare un profilo per ogni VPN aziendale (vedere Windows 10 e Windows impostazioni del dispositivo [Holographic](/intune/vpn-settings-windows-10)per aggiungere connessioni VPN con Intune).

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="issue---unable-to-connect-with-network-using-certificate-based-authentication"></a>Problema- Non è possibile connettersi alla rete usando l'autenticazione basata su certificati ###

**Sintomi**

Il dispositivo non riesce a stabilire una connessione di rete con l'autenticazione basata su certificato.

**Passaggi per la risoluzione dei problemi**

1. Nel caso in cui sia necessario convalidare la corretta distribuzione di un certificato, usare [Gestione](certificate-manager.md) certificati nel dispositivo per verificare che il certificato sia presente.  

    >[!WARNING]
    > Anche se è possibile visualizzare i certificati distribuiti da MDM in Gestione certificati, non è possibile disinstallarli in Gestione certificati. È necessario disinstallarli tramite MDM.

2. Solo per Intune, se Simple Certificate Enrollment Protocol (SCEP) viene usato per distribuire i certificati, assicurarsi che l'URL del server servizio Registrazione dispositivi di rete (NDES) sia raggiungibile dal dispositivo. [Per informazioni sulla configurazione, vedere Certificati SCEP in Intune.](/mem/intune/protect/certificates-profile-scep) Se viene usato CNAME anziché un dominio completo per il server NDES, assicurarsi che venga risolto correttamente digitando l'URL in un Web browser nel dispositivo.
