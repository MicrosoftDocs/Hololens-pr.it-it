---
title: Configurare i DSN e la panoramica sulla gestione dei dispositivi
description: Come configurare CSP, criteri e gestione dei dispositivi.
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
ms.openlocfilehash: 4c31f7f92116031535a2dc2860e3f048a2311a39
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016788"
---
# Configurare i DSN e la panoramica sulla gestione dei dispositivi

Gli amministratori IT possono definire e implementare le impostazioni dei criteri in HoloLens 2. Le impostazioni di configurazione da usare varieranno in base allo scenario di distribuzione e i dispositivi aziendali offriranno al personale IT la più ampia gamma di opzioni di controllo. In Windows 10, i provider di servizi di configurazione (CSP) sono un'interfaccia per leggere, impostare, modificare o eliminare le impostazioni di configurazione nel dispositivo. Queste impostazioni corrispondono a chiavi del Registro di sistema o file. Alcuni provider di servizi di configurazione supportano il formato WAP, alcuni supportano SyncML e alcuni supportano entrambi. 

Per altre informazioni sui CSP per la gestione di dispositivi olografici di Windows 10, vedere l'elenco completo dei [CSP supportati nei dispositivi HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Gli amministratori IT possono anche gestire i criteri CSP nei dispositivi, vedere l'elenco completo dei [DSN sui criteri supportati da HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## Metodi di configurazione

### Configurare con MDM
I CSP e i criteri possono essere facilmente gestiti in qualsiasi dispositivo personale o aziendale registrato in un sistema MDM. Una volta che un dispositivo è stato registrato nella soluzione MDM, sarà possibile gestire il dispositivo o un set di dispositivi tramite le configurazioni di dispositivo. Leggi altre informazioni su come [gestire i dispositivi HoloLens tramite MDM](hololens-mdm-configure.md).

### Configurare con i pacchetti di provisioning
HoloLens 2 supporta inoltre l'impostazione di un set limitato di configurazioni CSP per i dispositivi HoloLens 2 tramite pacchetti di provisioning personalizzati. I pacchetti di provisioning vengono in genere sfruttati per i dispositivi gestiti non MDM e richiedono l'applicazione manuale a ogni dispositivo. Leggere informazioni sulla creazione [di pacchetti di provisioning personalizzati per HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning). 

## Configurazioni 

### Restrizioni comuni per i dispositivi
Alcune restrizioni dei dispositivi sono semplici e disabilitano una funzionalità o una connessione al dispositivo. Per altre informazioni, vedere altre informazioni sulle [restrizioni dei dispositivi comuni.](hololens-common-device-restrictions.md)

### Modalità Kiosk
Usa la modalità Kiosk per controllare le identità che hanno accesso alle app per impostazione predefinita. I chioschi possono essere usati per una singola app o per un'esperienza dell'interfaccia utente per più app. Le configurazioni di Kiosk variano da una singola app per chiunque usi il dispositivo, a selezioni diverse di app per gruppi diversi. Questo non impedisce che "app consentite" lancino altre app e non siano state progettate per sempre. Per altre informazioni, [iniziare a leggere le modalità Kiosk e come usarle](hololens-kiosk.md).

### Visibilità pagina impostazioni
Usare i criteri delle app impostazioni per controllare le identità che hanno accesso alle impostazioni per impostazione predefinita. Con questo criterio l'app impostazioni può essere configurata in modo da visualizzare solo le pagine di selezione oppure nascondere tutte le pagine selezionate. [Informazioni su come configurare le pagine disponibili](settings-uri-list.md).

Questa caratteristica è attualmente solo avalible in [Windows Insider Builds](hololens-insider.md). Verificare che i dispositivi a cui si intende usare questo articolo siano in Build 19041.1349 +.

### WDAC
Usa la configurazione di WDAC per controllare quali app/processi sono consentiti/non consentiti per essere avviati indipendentemente dal fatto che il sistema sia in modalità Kiosk o meno.
[Vedere la panoramica per WDAC.](windows-defender-application-control-wdac.md)
