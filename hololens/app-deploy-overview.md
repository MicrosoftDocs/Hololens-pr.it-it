---
title: Panoramica - Gestione delle app
description: Introduzione a una panoramica della gestione delle app di realtà mista con la gestione dei dispositivi mobili, Microsoft Store per le aziende e il provisioning dei pacchetti.
keywords: HoloLens, utente, account, app, gestione delle applicazioni,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 019700c7e35f31c234c9fe69870cae54b3364b631253c37a17d8eaa0fe3053bd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665234"
---
# <a name="app-management-overview"></a>Gestione delle app: Panoramica

È possibile distribuire le app in quattro percorsi diversi: Gestione di dispositivi mobili **(MDM),** **Microsoft Store per le aziende**, **Microsoft Store** o installandole tramite **provisioning** di .

## <a name="mobile-device-management-mdm"></a>Gestione di dispositivi mobili

Una soluzione MDM consente ai decision maker IT e agli amministratori di installare (eseguire il push) privatamente delle app line-of-business o di acquistare app all'interno dello Store per un gruppo di utenti. HoloLens i dispositivi funzionano meglio con Microsoft Endpoint Manager (Intune) per la [gestione delle applicazioni](app-deploy-intune.md). Intune offre anche agli utenti un controllo più granulare sulle app gestite dall'IT tramite Portale aziendale'esperienza scaricabile.

> [!NOTE]
> Le istruzioni seguenti sono per gli utenti che vogliono gestire le proprie applicazioni con Intune. Microsoft consiglia di usare Intune per la gestione di applicazioni e dispositivi.

La gestione dei dispositivi mobili (MDM) è applicabile per:

* MDM distribuito + Portale aziendale
* App line-of-business (non pubbliche)
* Installazione manuale delle applicazioni disponibili tramite Portale aziendale
* Push dell'amministratore tramite criteri MDM
* Aggiornamento automatico tramite MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store per le aziende

Il [Microsoft Store per le aziende](app-deploy-store-business.md) i decision maker IT e gli amministratori delle aziende per trovare, acquisire, gestire e distribuire app gratuite e a pagamento. Gli amministratori IT possono gestire Microsoft Store e le app line-of-business private in un unico inventario, oltre ad assegnare e riutilizzare le licenze in base alle esigenze. Per altre informazioni, vedere [Prerequisiti per l'uso del Microsoft Store per le aziende](/microsoft-store/prerequisites-microsoft-store-for-business).

Il Microsoft Store per le aziende è applicabile per:

* App pubbliche o line-of-business
* Installazione automatica delle applicazioni necessarie tramite l'associazione MDM
* L'utente scarica manualmente le app
* Aggiornamento automatico

## <a name="microsoft-store-apps"></a>App del Microsoft Store

Il Microsoft Store i decision maker IT e gli amministratori delle aziende per trovare, acquisire, gestire e distribuire le app pubbliche.

Questo Microsoft Store è applicabile per:

* Solo app pubbliche
* L'utente scarica manualmente le app
* Aggiornamento automatico se connesso a Internet

Per altre informazioni, visitare [App di Holographic Store.](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Eseguire l'installazione tramite pacchetti di provisioning

[I pacchetti](app-deploy-provisioning-package.md) di provisioning consentono di installare app personalizzate o line-of-business, consentendo a professionisti IT e amministratori di installare rapidamente le app in uno o più dispositivi locali tramite USB. Questa installazione può essere eseguita senza una connessione Internet e per qualsiasi tipo di identità.

L'installazione tramite pacchetti di provisioning è applicabile per:

* App line-of-business/auto-sviluppate (non pubbliche)
* App pubbliche (se il programma di installazione offline è disponibile)
* Solo side loading USB
* Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite il pacchetto di provisioning)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Installare app in HoloLens 2 tramite Programma di installazione app

L'uso Programma di installazione app utenti può avere un'esperienza semplice per l'installazione di app nei dispositivi locali o la condivisione di un'app con un altro utente che non ha familiarità con altri metodi di installazione delle app HoloLens. [](app-deploy-app-installer.md) Questa operazione può essere eseguita senza dover abilitare la modalità sviluppatore o usare Portale di dispositivi. Si tratta di un metodo semplice per distribuire un'app completamente compilata. Indipendentemente dal fatto che si voglia semplicemente eseguire la demo dell'app a un altro utente con un HoloLens o se si vuole distribuire l'app, questo metodo funziona facilmente.

L'installazione tramite Programma di installazione app è applicabile per:

* App line-of-business/auto-sviluppate (non pubbliche)
* Solo side load
* Non richiede la modalità sviluppatore o il portale per dispositivi
* Installazione facile per l'utente finale
