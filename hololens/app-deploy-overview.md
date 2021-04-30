---
title: Panoramica - Gestione delle app
description: Introduzione a una panoramica della gestione delle app di realtà mista con la gestione dei dispositivi mobili, Microsoft Store per le aziende e i pacchetti di provisioning.
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309282"
---
# <a name="app-management-overview"></a>Gestione app: panoramica

È possibile distribuire le app in quattro percorsi diversi: Gestione dispositivi mobili **(MDM),** **Microsoft Store per le aziende**, **Microsoft Store** o installandole tramite **Provisioning**.

## <a name="mobile-device-management-mdm"></a>Gestione di dispositivi mobili

Una soluzione MDM consente ai decision maker IT e agli amministratori di installare (eseguire il push) in privato delle app line-of-business o di acquistare app tramite lo Store per un gruppo di utenti. I dispositivi HoloLens funzionano meglio con Microsoft Endpoint Manager (Intune) per la [gestione delle applicazioni.](app-deploy-intune.md) Intune offre anche agli utenti un controllo più granulare sulle app gestite dall'IT Portale aziendale'esperienza scaricabile.

> [!NOTE]
> Le istruzioni seguenti sono per gli utenti che vogliono gestire le applicazioni con Intune. Microsoft consiglia di usare Intune per la gestione di applicazioni e dispositivi.

Gestione di dispositivi mobili (MDM) è applicabile per:

* MDM distribuito + Portale aziendale
* App line-of-business (non pubbliche)
* Installazione manuale delle applicazioni disponibili tramite Portale aziendale
* Push dell'amministratore tramite i criteri MDM
* Aggiornamento automatico tramite MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store per le aziende

Il [Microsoft Store per le aziende](app-deploy-store-business.md) fornisce ai decision maker IT e agli amministratori delle aziende la ricerca, l'acquisizione, la gestione e la distribuzione di app gratuite e a pagamento. Gli amministratori IT possono gestire Microsoft Store app e app line-of-business private in un unico inventario, oltre ad assegnare e riutilizzare le licenze in base alle esigenze. Per altre informazioni, vedere [Prerequisiti per l'uso dell'Microsoft Store per le aziende](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).

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

Per altre informazioni, visitare [App di Holographic Store.](https://docs.microsoft.com/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Eseguire l'installazione tramite pacchetti di provisioning

[I pacchetti](app-deploy-provisioning-package.md) di provisioning consentono di installare app personalizzate o line-of-business, consentendo a professionisti IT e amministratori di installare rapidamente le app in uno o più dispositivi locali tramite USB. Questa installazione può essere eseguita senza una connessione Internet e per qualsiasi tipo di identità.

L'installazione tramite pacchetti di provisioning è applicabile per:

* App line-of-business/auto-sviluppate (non pubbliche)
* App pubbliche (se il programma di installazione offline è disponibile)
* Solo side loading USB
* Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite il pacchetto di provisioning)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Installare app in HoloLens 2 tramite Programma di installazione app

L'uso Programma di installazione app utenti può avere un'esperienza semplice per l'installazione di app nei dispositivi locali o la condivisione di un'app con un altro utente che non ha familiarità con altri metodi di installazione delle app in HoloLens. [](app-deploy-app-installer.md) Questa operazione può essere eseguita senza dover abilitare la modalità sviluppatore o usare Portale di dispositivi. Si tratta di un metodo semplice per distribuire un'app completamente compilata. Indipendentemente dal fatto che si voglia semplicemente eseguire la demo dell'app a un altro utente con un holoLens o se si vuole distribuire l'app, questo metodo funziona facilmente.

L'installazione tramite Programma di installazione app è applicabile per:

* App line-of-business/self-developed (non pubbliche)
* Solo caricamento laterale
* Non richiede la modalità sviluppatore o il portale dispositivi
* Facile da installare per l'utente finale
