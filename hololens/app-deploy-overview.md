---
title: Panoramica-gestione delle app
description: app, gestione, gestione app
keywords: HoloLens, utente, account, app, gestione applicazioni,
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: eeed478970d08eff8789a9decd084f1863c6d7f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857954"
---
# Gestione delle app: Panoramica

È possibile distribuire le app in quattro percorsi diversi: **MDM (Mobile Device Management)**, **Microsoft Store per le aziende**, **Microsoft Store**o installarli tramite **provisioning**. 

## Gestione dispositivi mobili (MDM)

Una soluzione MDM consente ai responsabili IT e agli amministratori di installare automaticamente le proprie app line-of-business in privato o di acquistare app tramite lo Store per un gruppo di utenti. I dispositivi HoloLens funzionano meglio con Microsoft Endpoint Manager (Intune) per la [gestione delle applicazioni](app-deploy-intune.md). Intune offre anche agli utenti un controllo più accurato sulle app gestite da IT tramite l'esperienza scaricabile del portale aziendale.

> [!NOTE] 
> Le istruzioni seguenti si riferiscono agli utenti che vogliono gestire le proprie applicazioni con Intune. Microsoft consiglia di usare Intune per la gestione di applicazioni e dispositivi.
    
La gestione di dispositivi mobili (MDM) è applicabile per: 
* MDM distribuito + Portale aziendale 
* Linea di app business (non pubbliche)
* Installazione manuale delle applicazioni disponibili tramite portale aziendale
* Criteri di push-through MDM di amministrazione
* Aggiornamento automatico tramite MDM

## Microsoft Store per le aziende

[Microsoft Store for business](app-deploy-store-business.md) offre ai responsabili decisionali e agli amministratori delle aziende di trovare, acquisire, gestire e distribuire app gratuite e a pagamento. Gli amministratori IT possono gestire le app di Microsoft Store e le app line-of-business private in un unico inventario e assegnare e riutilizzare le licenze in base alle esigenze. Per altre informazioni, visitare [i prerequisiti per l'uso di Microsoft Store for business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).
    
Microsoft Store for business è applicabile per: 
* App pubbliche o line-of-business
* Installazione automatica delle applicazioni necessarie tramite MDM Association
* L'utente scarica manualmente le app
* Aggiornamento automatico

## App di Microsoft Store

Microsoft Store offre ai responsabili decisionali e agli amministratori delle aziende la ricerca, l'acquisizione, la gestione e la distribuzione di app pubbliche.
    
Questo Microsoft Store è applicabile per: 
* Solo app pubbliche
* L'utente scarica manualmente le app
* Aggiornamento automatico se connesso a Internet

Per altre informazioni, visita le [app dello Store olografico](https://docs.microsoft.com/hololens/holographic-store-apps).

## Installare tramite provisioning Packages

I [pacchetti di provisioning](app-deploy-provisioning-package.md) consentono di installare app personalizzate o di linea di business, consentendo ai professionisti IT e agli amministratori di installare rapidamente le app in un dispositivo locale tramite USB. Questa operazione può essere eseguita senza una connessione Internet e per qualsiasi tipo di identità.
    
L'installazione tramite pacchetti di provisioning è applicabile per: 
* Linea di app business (non pubbliche)
* App pubbliche (se è disponibile il programma di installazione offline)
* Solo caricamento laterale USB
* Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite il pacchetto di provisioning)