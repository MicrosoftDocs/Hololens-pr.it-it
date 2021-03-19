---
title: Sicurezza del sistema operativo senza amministratore
description: Scopri i sistemi operativi senza amministratore, i proprietari dei dispositivi e la sicurezza nei dispositivi di realtà mista HoloLens.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, senza amministratore, sistema operativo, sistema operativo senza amministratore, OS amministratore, OS senza amministratore, hololens 2, sicurezza hololens2,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: 257720deb27f3bbc301175ce2a4afa79001862d3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440337"
---
# <a name="admin-less-operating-system"></a>Sistema operativo senza amministratore

HoloLens 2 riduce al minimo la superficie per l'escalation dei privilegi disabilitando il supporto per il gruppo Administrators e limitando tutto il codice di applicazioni UWP di terze parti per l'esecuzione solo come utenti standard all'interno della sandbox AppContainer. A questo codice viene concesso solo l'accesso alle risorse protette da funzionalità manifestate esplicitamente nell'applicazione per un utente senza privilegi elevati oltre alle risorse accessibili a tutti gli AppContainer.
Queste funzionalità dell'applicazione continuano ad avere il modello di classificazione a tre livelli:
  * Generale
  * Restricted (Restrizioni)
  * Windows

I componenti di Windows possono anche usare la sandbox AppContainer con la piattaforma UWP di sistema. Per altre informazioni sulla piattaforma UWP (Universal Windows Platform), vedere la [Documentazione della piattaforma UWP (Universal Windows Platform)](https://docs.microsoft.com/windows/uwp/). Inoltre, i componenti di Windows con maggiori esigenze di riduzione dei privilegi, ad esempio le pagine di contenuti del browser o i parser, usano la sandbox LPAC (Less Privileged AppContainer), che interrompe l'accesso al set di risorse accessibile a tutti gli AppContainer.

## <a name="device-owner"></a>Proprietario del dispositivo

Infine, l'esecuzione di specifiche operazioni a livello di dispositivo, come l'aggiunta del dispositivo a un tenant o la gestione utenti, è consentita solo per i proprietari dei dispositivi. Questo gruppo viene popolato dagli utenti nel dispositivo attraverso una di queste operazioni:
  * Il primo utente nel dispositivo è sempre designato come proprietario. 
> [!IMPORTANT]
>Per gli utenti di Azure AD, l'eccezione a questa regola è che se il dispositivo è aggiunto ad Azure AD tramite Autopilot o la registrazione di Azure AD di massa, che usa un utente non reale. In questo caso, il primo utente AAD ad accedere al dispositivo potrebbe non essere automaticamente proprietario del dispositivo, a meno che l'utente non abbia assegnato il ruolo "amministratore globale" o "amministratore del dispositivo" nel portale di Azure. Per ulteriori informazioni, vedere la nota sotto.  

  * Quando un utente è innalzato al livello di proprietario nell'esperienza utente Impostazioni da un altro proprietario nel dispositivo.
  * Se il proprietario del dispositivo non è più disponibile, ad esempio ha lasciato l’azienda, e il dispositivo è stato aggiunto ad Azure AD, l'amministratore tenant può designare un altro utente come proprietario del dispositivo nel Portale di Azure. Gli amministratori globali e gli amministratori dei dispositivi di un tenant di Azure AD sono connessi in modo implicito come Proprietari nel dispositivo, senza necessità di eseguire le operazioni indicate sopra.  

 Gli amministratori IT possono gestire ciò a cui le app possono accedere tramite i criteri di [privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy). 

> [!NOTE]
> Per comprendere meglio chi diventa il proprietario di un dispositivo aggiunto ad Azure AD, vedere la [documentazione sull'assegnazione dell'amministratore locale](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (sostituendo "amministratore locale" con "proprietario del dispositivo", dato che in HoloLens non esiste l'amministratore).