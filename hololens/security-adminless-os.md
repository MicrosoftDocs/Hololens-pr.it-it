---
title: Sicurezza del sistema operativo senza amministratore
description: Informazioni sui sistemi operativi senza amministrazione, sui proprietari dei dispositivi e sulla sicurezza HoloLens dispositivi di realtà mista.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, sistema operativo, sistema operativo senza amministratore, sistema operativo amministratore, sistema operativo senza amministratore, hololens 2, sicurezza hololens2,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f4fc79b7f51933418cdda8368c6b4b070e854dd0978754647ce864075c772cfd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665540"
---
# <a name="admin-less-operating-system"></a>Sistema operativo senza amministratore

HoloLens 2 riduce al minimo la superficie di attacco per l'escalation dei privilegi disabilitando il supporto per il gruppo Administrators e limitando tutto il codice dell'applicazione UWP di terze parti in modo che sia eseguito solo come utenti standard all'interno della sandbox AppContainer. A questo codice viene concesso l'accesso solo alle risorse protette dalle funzionalità esplicitamente manifestate nell'applicazione per un utente non elevato, oltre alle risorse accessibili a tutti gli AppContainer.
Queste funzionalità dell'applicazione continuano a avere il modello di classificazione a tre livelli:
  * Generale
  * Con restrizioni
  * Windows

Windows componenti possono anche sfruttare la sandbox AppContainer tramite UWP di sistema. Per altre informazioni sulla piattaforma UWP (Universal Windows Platform), vedere [la documentazione della piattaforma UWP.](/windows/uwp/) Inoltre, i componenti Windows con esigenze di riduzione dei privilegi maggiori (ad esempio pagine di contenuto del browser o parser) usano la sandbox LPAC (Less Privileged AppContainer), che consente di ridurre l'accesso al set di risorse accessibili a tutti gli AppContainer.

## <a name="device-owner"></a>Proprietario del dispositivo

Infine, l'esecuzione di operazioni specifiche a livello di dispositivo, ad esempio l'aggiunta del dispositivo a un tenant o la gestione degli utenti, è consentita solo per i "proprietari dei dispositivi". Questo gruppo viene popolato dagli utenti nel dispositivo tramite uno dei passaggi seguenti:
  * Il primo utente del dispositivo è sempre designato come proprietario. 
> [!IMPORTANT]
>Per Azure AD utenti, l'eccezione a questa regola è che se il dispositivo viene aggiunto Azure AD tramite Autopilot o la registrazione Azure AD bulk, che usa un utente non reale. In questo caso, il primo utente di AAD che accede al dispositivo potrebbe non essere automaticamente proprietario del dispositivo, a meno che tale utente non abbia il ruolo "amministratore globale" o "amministratore del dispositivo" assegnato in portale di Azure. Per altre informazioni, vedere la nota seguente.  

  * Quando un utente viene promosso come proprietario dall'esperienza Impostazioni UX da un altro proprietario nel dispositivo.
  * Se il proprietario del dispositivo non è più disponibile (lascia l'azienda) e il dispositivo viene aggiunto Azure AD, l'amministratore tenant può modificare il proprietario del dispositivo in un nuovo utente portale di Azure. Gli amministratori globali e gli amministratori Azure AD di un tenant vengono connessi in modo implicito come proprietari nel dispositivo senza richiedere uno dei passaggi precedenti.  

 Gli amministratori IT possono gestire le app a cui possono accedere tramite [i criteri sulla](/windows/client-management/mdm/policy-csp-privacy) privacy. 

> [!NOTE]
> Per altre informazioni su chi è stato reso proprietario di un dispositivo aggiunto Azure AD, vedere la documentazione "Assegna amministratore locale" (ma leggere ["Amministratore locale"](/azure/active-directory/devices/assign-local-admin) come "proprietario del dispositivo" perché l'amministratore non esiste HoloLens).