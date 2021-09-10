---
title: Configurare i CSP e la panoramica di Gestione dispositivi
description: Informazioni su come configurare csp, criteri e gestione dei dispositivi usando la gestione dei dispositivi mobili e i pacchetti di provisioning.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427078"
---
# <a name="configure-csps-and-device-management-overview"></a>Configurare i CSP e la panoramica di Gestione dispositivi

Gli amministratori IT possono definire e implementare le impostazioni dei criteri HoloLens 2. Le impostazioni di configurazione da usare varieranno in base allo scenario di distribuzione e i dispositivi aziendali offriranno al personale IT la più ampia gamma di opzioni di controllo. In Windows 10, i provider di servizi di configurazione (CSP) sono un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione nel dispositivo. Queste impostazioni corrispondono a chiavi del Registro di sistema o file. Alcuni provider di servizi di configurazione supportano il formato WAP, altri supportano SyncML e altri supportano entrambi.

Per altre informazioni sui Windows 10 Holographic di gestione dei dispositivi, vedere l'elenco completo dei CSP supportati nei HoloLens [dispositivi](/windows/client-management/mdm/configuration-service-provider-reference#hololens).
Gli amministratori IT possono anche gestire policy CSP nei dispositivi. Vedere l'elenco completo dei provider di servizi di sicurezza dei criteri [supportati da HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## <a name="configuration-methods"></a>Metodi di configurazione

### <a name="configure-with-mdm"></a>Configurare con MDM

I CSP e i criteri possono essere gestiti facilmente in qualsiasi dispositivo personale o aziendale registrato in un sistema MDM. Dopo aver registrato un dispositivo nella soluzione MDM, sarà possibile gestirvi il dispositivo o il set di dispositivi usando le configurazioni dei dispositivi. Altre informazioni su come gestire [i dispositivi HoloLens tramite MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Configurare con i pacchetti di provisioning

HoloLens 2 supporta anche l'impostazione di un set limitato di configurazioni CSP per HoloLens 2 dispositivi tramite pacchetti di provisioning personalizzati. I pacchetti di provisioning vengono in genere sfruttati per i dispositivi gestiti non MDM e devono essere applicati manualmente a ogni dispositivo. Leggere le informazioni sulla creazione di pacchetti [di provisioning personalizzati per HoloLens](hololens-provisioning.md).

## <a name="configurations"></a>Configurazioni

### <a name="common-device-restrictions"></a>Restrizioni comuni dei dispositivi

Alcune restrizioni del dispositivo sono semplici e disabilitano una funzionalità o una connessione al dispositivo. Per altre informazioni, vedere altre informazioni sulle [restrizioni comuni per i dispositivi.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Modalità tutto schermo

Usare la modalità tutto schermo per controllare quali identità hanno accesso alle app per impostazione predefinita. I chioschi in modalità tutto schermo possono essere usati per una singola app o più esperienze dell'interfaccia utente dell'app. Le configurazioni in modalità tutto schermo variano da una singola app per tutti gli utenti che usano il dispositivo a diverse selezioni di app per gruppi diversi. La modalità tutto schermo non arresta l'avvio di altre app da parte delle "app consentite" e non è mai stata prevista. Per altre [informazioni, vedere Modalità tutto schermo e come usarle.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Impostazioni Visibilità della pagina

Usare Impostazioni criteri dell'app per controllare quali identità hanno accesso alle impostazioni per impostazione predefinita. Usando questo criterio, Impostazioni'app può essere configurata in modo da visualizzare solo le pagine selezionate o nascondere tutte le pagine selezionate. [Informazioni su come configurare le pagine disponibili.](settings-uri-list.md)

Questa funzionalità è attualmente disponibile solo nelle [build Windows Insider.](hololens-insider.md) Assicurarsi che i dispositivi per cui si intende usare questa funzionalità siano nella build 19041.1349+.

### <a name="wdac"></a>WDAC

Usare la configurazione WDAC per controllare quali app/processi sono consentiti/non consentiti per l'avvio indipendentemente dal fatto che il sistema sia in modalità tutto schermo o meno.
[Vedere la panoramica per WDAC.](windows-defender-application-control-wdac.md)
