---
title: Microsoft Store per le aziende
description: Informazioni su come usare il Microsoft Store per le aziende pubblicare le applicazioni di realtà mista nell'azienda.
keywords: Microsoft Store per le aziende, msfb, distribuzione di app, store
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924325"
---
# <a name="microsoft-store-for-business"></a>Microsoft Store per le aziende

Il [Microsoft Store per le aziende](/microsoft-store/microsoft-store-for-business-overview) è progettato principalmente per i decision maker IT e gli amministratori di aziende o organizzazioni con un modo flessibile per trovare, acquisire, gestire e distribuire app gratuite e a pagamento in mercati specifici a dispositivi Windows 10 in volume. 

È possibile gestire Microsoft Store e le app line-of-business private in un unico inventario e assegnare e riallineare le licenze in base alle esigenze. È anche possibile scegliere il metodo di distribuzione migliore per l'organizzazione: assegnare direttamente le app a singoli utenti e team, pubblicare app in pagine private in Microsoft Store o connettersi con soluzioni di gestione per altre opzioni.

Quando Microsoft Store per le aziende viene usato da un utente finale, avvierà l'app Microsoft Store app. Dopo l'avvio, l'utente sarà in grado di selezionare la scheda con il nome dell'organizzazione e gli verranno quindi presentate le app disponibili per l'utente o il dispositivo.

> [!Note]
> Microsoft Store per le aziende scarica automaticamente (push) le app nei dispositivi. Tuttavia, le app del Microsoft Store per le aziende possono essere associate al server di gestione dei dispositivi (MDM) per la destinazione e la sincronizzazione delle app nei dispositivi.

Visitare le pagine seguenti per altre informazioni su come usare il Microsoft Store per le aziende:

* [Livelli di autorizzazioni usati per l'installazione di applicazioni](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Come aggiungere un'app a Store per le aziende](/mem/intune/apps/store-apps-windows)
* [Come assegnare app a gruppi di dipendenti](/mem/intune/apps/windows-store-for-business)

Per associare il Microsoft Store per le aziende, vedere [Associare il Microsoft Store per le aziende a Intune.](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)

> [!Tip]
> Altre informazioni sulla [distribuzione di app offline](/microsoft-store/distribute-offline-apps) quando si usano app come Advanced Recovery Companion (ARC) e Windows Configuration Designer (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Usare solo app dello Store privato per Microsoft Store

- Introdotto in [Windows Holographic, versione 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Il criterio RequirePrivateStoreOnly è stato abilitato per HoloLens. Questo criterio consente all'app Microsoft Store essere configurata in modo da visualizzare solo l'archivio privato configurato per l'organizzazione. Limitare l'accesso solo alle app rese disponibili.

Altre informazioni su [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Smart Retry for app updates (Nuovo tentativo intelligente per gli aggiornamenti dell'app)

- Introdotto in [Windows Holographic, versione 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Ora abilitato per HoloLens è un nuovo criterio che consente agli amministratori IT di impostare una data ricorrente o una data di riavvio per riavviare le app il cui aggiornamento non è riuscito perché l'app è in uso consentendo l'applicazione dell'aggiornamento. Questi possono essere impostati in base ad alcuni trigger diversi, ad esempio un'ora pianificata o l'accesso. Per altre informazioni su come usare questo criterio, vedere [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)