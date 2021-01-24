---
title: Funzionalità commerciali
description: Informazioni sulle funzionalità di Microsoft HoloLens Commercial Suite che semplificano la gestione dei dispositivi HoloLens per le aziende.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, Commercial, funzionalità, MDM, gestione di dispositivi mobili, modalità tutto schermo
ms.openlocfilehash: 5aef764b1d7937832e162ab219131d8c3d768e68
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283447"
---
# Funzionalità commerciali

HoloLens include funzionalità che semplificano la gestione dei dispositivi HoloLens da parte delle aziende.

Ogni dispositivo HoloLens 2 dispone di funzionalità commerciali.

HoloLens (prima generazione) viene fornito con due opzioni di licenza: la licenza per sviluppatori e una licenza commerciale. Per sbloccare le funzionalità commerciali di HoloLens, esegui l'aggiornamento dalla licenza per sviluppatori a una licenza commerciale. Per acquistare Microsoft HoloLens Commercial Suite, contatta il tuo Account Manager designato da Microsoft.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## Principali funzionalità commerciali

- **Modalità tutto schermo.** Puoi usare HoloLens in modalità demo o di presentazione tramite la modalità tutto schermo, per limitare le app che possono essere eseguite.

  ![Con la modalità tutto schermo, HoloLens viene avviato direttamente nell'app di tua scelta.](images/201608-kioskmode-400px.png)

- **Gestione disponibili mobili (MDM) per HoloLens.** Il reparto IT può gestire più dispositivi HoloLens contemporaneamente usando soluzioni come Microsoft Intune. Puoi gestire le impostazioni, selezionare le app da installare e impostare le configurazioni di sicurezza adatte alle esigenze della tua organizzazione.

  ![Gestione dispositivi mobili in HoloLens offre la gestione dei dispositivi di livello enterprise su più dispositivi.](images/201608-enterprisemanagement-400px.png)

- **Windows Update per le aziende.** Windows Update per le aziende garantisce ai dispositivi aggiornamenti controllati del sistema operativo oltre al supporto di Long-Term Servicing Channel.
- **Sicurezza dei dati.** La crittografia dei dati di BitLocker è abilitata su HoloLens per assicurare lo stesso livello di protezione di qualsiasi altro dispositivo Windows.
- **Accesso al lavoro.** Tutti gli utenti dell'organizzazione possono connettersi in remoto alla rete aziendale tramite la rete privata virtuale (VPN) in un dispositivo HoloLens. HoloLens può anche accedere a reti Wi-Fi che richiedono credenziali.
- **Microsoft Store per le aziende.** Il reparto IT può anche configurare un archivio privato aziendale, che contiene solo le app della tua società per l'uso specifico di HoloLens. Distribuisci il software aziendale in modo sicuro a un gruppo selezionato di utenti aziendali.

## Confronto delle funzionalità tra le varie edizioni

|Funzionalità |HoloLens Development Edition |HoloLens Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Crittografia dispositivo (BitLocker) | |✔️ |✔️ |
|Rete privata virtuale (VPN) | |✔️ |✔️ |
|[Modalità tutto schermo](hololens-kiosk.md) | |✔️ |✔️ |
|**Gestione e distribuzione** | | | |
|Gestione dispositivi mobili (MDM) | |✔️ |✔️ |
|Possibilità di bloccare l'annullamento della registrazione | |✔️ |✔️ |
|Accesso Wi-Fi aziendale basato su certificato | |✔️ |✔️ |
|Microsoft Store (Consumer) |Consumer |Filtro tramite MDM |Filtro tramite MDM |
|[Portale Business Store](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Sicurezza e identità** | | | |
|Accesso tramite account di Azure Active Directory (Azure AD) |✔️ |✔️ |✔️ |
|Accesso tramite account Microsoft |✔️ |✔️ |✔️ |
|Credenziali di nuova generazione con sblocco PIN |✔️ |✔️ |✔️ |
|[Avvio protetto](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Assistenza e supporto tecnico** | | | |
|Aggiornamenti automatici del sistema man mano che arrivano |✔️ |✔️ |✔️ |
|[Windows Update per le aziende](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term Servicing Channel (LTSC) | |✔️ |✔️ |

## Abilitazione delle funzionalità commerciali

L'amministratore IT dell'organizzazione può configurare funzionalità commerciali come Microsoft Store per le aziende, la modalità tutto schermo e l'accesso Wi-Fi aziendale. La documentazione di [Microsoft HoloLens](index.yml) fornisce istruzioni dettagliate per la registrazione dei dispositivi e l'installazione di app da Microsoft Store per le aziende.

## Vedere anche

- [Microsoft HoloLens](index.yml)
- [Modalità tutto schermo](hololens-kiosk.md)
- [CSP supportati nei dispositivi HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store per le aziende e applicazioni line-of-business](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Uso delle app line-of-business](/microsoft-store/working-with-line-of-business-apps)
