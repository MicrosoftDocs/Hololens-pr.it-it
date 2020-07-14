---
title: sistema operativo senza amministratore e sicurezza
description: sistema operativo senza amministratore e sicurezza di hololens
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, senza amministratore, sistema operativo, sistema operativo senza amministratore, OS amministratore, OS senza amministratore, hololens 2, sicurezza hololens2,
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9243c6376348cfc3e0c44a049435a0f4b47fc6f7
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865766"
---
# Sistema operativo senza amministratore

HoloLens 2 riduce al minimo la superficie per l'escalation dei privilegi disabilitando il supporto per il gruppo Administrators e limitando tutto il codice di applicazioni UWP di terze parti per l'esecuzione solo come utenti standard all'interno della sandbox AppContainer. A questo codice viene concesso solo l'accesso alle risorse protette da funzionalità manifestate esplicitamente nell'applicazione per un utente senza privilegi elevati oltre alle risorse accessibili a tutti gli AppContainer.
Queste funzionalità dell'applicazione continuano ad avere il modello di classificazione a tre livelli:
  * Generale
  * Restricted (Restrizioni)
  * Windows

I componenti di Windows possono anche usare la sandbox AppContainer con la piattaforma UWP di sistema. Per altre informazioni sulla piattaforma UWP (Universal Windows Platform), vedere la [Documentazione della piattaforma UWP (Universal Windows Platform)](https://docs.microsoft.com/windows/uwp/). Inoltre, i componenti di Windows con maggiori esigenze di riduzione dei privilegi, ad esempio le pagine di contenuti del browser e i parser, usano la sandbox LPAC (Less Privileged AppContainer), che interrompe l'accesso al set di risorse accessibile a tutti gli AppContainer.

Infine, l'esecuzione di specifiche operazioni a livello di dispositivo, come l'aggiunta del dispositivo a un tenant o la gestione utenti, è consentita solo per i proprietari dei dispositivi. Questo gruppo viene popolato dagli utenti nel dispositivo attraverso una di queste operazioni:
  * Il primo utente nel dispositivo è sempre designato come proprietario. 
    * Se il dispositivo è aggiunto ad AAD, tuttavia, l'utente che ha eseguito l'aggiunta diventa il proprietario del dispositivo. Questo si applica, ad esempio, nel caso in cui un dispositivo viene aggiunto ad AAD tramite Autopilot, nel qual caso il primo utente che effettua l'accesso al dispositivo non ha aggiunto il dispositivo ad ADD e quindi non diventa il proprietario del dispositivo. Per comprendere meglio chi diventa il proprietario di un dispositivo aggiunto ad ADD, vedere la [documentazione sull'assegnazione dell'amministratore locale](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (sostituendo "amministratore locale" con "proprietario del dispositivo", dato che in HoloLens non esiste l'amministratore).
  * Quando un utente elevato a Proprietario dall'esperienza utente Impostazioni da un altro Proprietario nel dispositivo.
  * Se il proprietario del dispositivo non è più disponibile, ad esempio se lascia la società, e il dispositivo è stato aggiunto ad AAD, l'amministratore tenant può designare un altro utente come proprietario del dispositivo nel Portale di Azure.
Gli amministratori globali di un tenant di Azure AD sono connessi in modo implicito come Proprietari nel dispositivo, senza necessità di eseguire le operazioni indicate sopra. 

Gli amministratori IT possono gestire ciò a cui le app possono accedere tramite i criteri di [privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy). 
