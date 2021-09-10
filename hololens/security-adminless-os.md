---
title: Sicurezza del sistema operativo senza amministratore
description: Informazioni sui sistemi operativi senza amministratore, sui proprietari dei dispositivi e sulla sicurezza HoloLens dispositivi di realtà mista.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428189"
---
# <a name="admin-less-operating-system"></a>Sistema operativo senza amministratore

HoloLens 2 riduce al minimo la superficie di attacco per l'escalation dei privilegi disabilitando il supporto per il gruppo Administrators e limitando tutto il codice dell'applicazione UWP di terze parti in modo che sia eseguito solo come utenti standard all'interno della sandbox AppContainer. A questo codice viene concesso solo l'accesso alle risorse protette dalle funzionalità esplicitamente manifeste nell'applicazione per un utente nonlevato, oltre alle risorse accessibili a tutti gli AppContainer.
Queste funzionalità dell'applicazione continuano a avere il modello di classificazione a tre livelli:
  * Generale
  * Con restrizioni
  * Windows

Windows componenti possono anche sfruttare la sandbox AppContainer tramite IWP di sistema. Per altre informazioni sulla piattaforma UWP (Universal Windows Platform), vedere [la documentazione della piattaforma UWP.](/windows/uwp/) Inoltre, i componenti Windows con esigenze di riduzione dei privilegi maggiori (ad esempio pagine di contenuto del browser o parser) usano la sandbox Disa con privilegi inferiori, che interrompe l'accesso al set di risorse accessibili a tutti gli AppContainer.

## <a name="device-owner"></a>Proprietario del dispositivo

Infine, l'esecuzione di operazioni specifiche a livello di dispositivo, ad esempio l'aggiunta del dispositivo a un tenant o la gestione degli utenti, è consentita solo per i "proprietari di dispositivi". Questo gruppo viene popolato dagli utenti nel dispositivo tramite uno dei passaggi seguenti:
  * Il primo utente del dispositivo è sempre designato come proprietario. 
> [!IMPORTANT]
>Per Azure AD utenti Azure AD, l'eccezione a questa regola è che se il dispositivo viene aggiunto tramite Autopilot o la registrazione Azure AD in blocco, che usa un utente non reale. In questo caso, il primo utente di AAD che accede al dispositivo potrebbe non essere automaticamente proprietario del dispositivo, a meno che tale utente non abbia il ruolo di "amministratore globale" o "amministratore del dispositivo" assegnato in portale di Azure. Per altre informazioni, vedere la nota seguente.  

  * Quando un utente viene alzato di livello a proprietario dal Impostazioni'esperienza utente da un altro proprietario nel dispositivo.
  * Se il proprietario del dispositivo non è più disponibile (lascia l'azienda) e il dispositivo viene aggiunto Azure AD, l'amministratore tenant può modificare il proprietario del dispositivo in un nuovo utente in portale di Azure. Gli amministratori globali e gli amministratori dei dispositivi di un tenant Azure AD vengono connessi in modo implicito come proprietari nel dispositivo senza richiedere uno dei passaggi precedenti.  

 Gli amministratori IT possono gestire le app a cui possono accedere tramite [criteri di privacy.](/windows/client-management/mdm/policy-csp-privacy) 

> [!NOTE]
> Per altre informazioni su chi è il proprietario di un dispositivo aggiunto a un Azure AD, vedere la documentazione "Assegna amministratore locale", ma leggere ["Amministratore locale"](/azure/active-directory/devices/assign-local-admin) come "proprietario del dispositivo" perché l'amministratore non esiste in HoloLens.