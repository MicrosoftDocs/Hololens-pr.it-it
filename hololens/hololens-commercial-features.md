---
title: Funzionalità commerciali
description: Informazioni sulle funzionalità Microsoft HoloLens Commercial Suite che semplificano la gestione dei dispositivi HoloLens da parte delle aziende.
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
keywords: HoloLens, commerciale, funzionalità, mdm, gestione di dispositivi mobili, modalità tutto schermo
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397862"
---
# <a name="commercial-features"></a>Funzionalità commerciali

HoloLens include funzionalità che semplificano la gestione dei dispositivi HoloLens da parte delle aziende.

Ogni HoloLens 2 dispositivo ha funzionalità commerciali disponibili.

HoloLens (prima generazione) è stato fornito con due opzioni di licenza, la licenza per sviluppatori e una licenza commerciale. Per sbloccare le funzionalità commerciali di HoloLens, eseguire l'aggiornamento dalla licenza per sviluppatori a una licenza commerciale. Per acquistare il Microsoft HoloLens Commercial Suite, contattare il responsabile account Microsoft locale.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Funzionalità commerciali chiave

- **Modalità tutto schermo.** Puoi usare HoloLens nelle esperienze demo o di presentare usando la modalità tutto schermo per limitare le app che possono essere eseguite.

  ![Con la modalità tutto schermo, HoloLens viene avviato direttamente nell'app di propria scelta.](images/201608-kioskmode-400px.png)

- **Gestione di dispositivi mobili (MDM) per HoloLens.** Il reparto IT può gestire più dispositivi HoloLens contemporaneamente usando soluzioni come Microsoft Intune. È possibile gestire le impostazioni, selezionare le app da installare e impostare configurazioni di sicurezza personalizzate in base alle esigenze dell'organizzazione.

  ![La gestione dei dispositivi mobili in HoloLens offre la gestione dei dispositivi di livello aziendale tra più dispositivi.](images/201608-enterprisemanagement-400px.png)

- **Windows Update per le aziende.** Windows Update per le aziende aggiornamenti del sistema operativo controllati per i dispositivi e il supporto per il canale di manutenzione a lungo termine.
- **Sicurezza dei dati.** La crittografia dei dati di BitLocker è abilitata in HoloLens per fornire lo stesso livello di protezione di qualsiasi altro dispositivo Windows.
- **Accesso all'attività.** Tutti gli utenti dell'organizzazione possono connettersi in remoto alla rete aziendale tramite una rete privata virtuale (VPN) in un dispositivo HoloLens. HoloLens può anche accedere alle Wi-Fi che richiedono credenziali.
- **Microsoft Store per le aziende.** Il reparto IT può anche configurare un archivio privato aziendale, contenente solo le app aziendali per l'utilizzo specifico di HoloLens. Distribuire in modo sicuro il software aziendale a un gruppo selezionato di utenti aziendali.

## <a name="feature-comparison-between-editions"></a>Confronto delle funzionalità tra le edizioni

|Funzionalità |HoloLens (prima generazione) Development Edition |HoloLens (prima generazione) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Crittografia dispositivo (BitLocker) | |✔️ |✔️ |
|Rete privata virtuale (VPN) | |✔️ |✔️ |
|[Modalità tutto schermo](hololens-kiosk.md) | |✔️ |✔️ |
|**Gestione e distribuzione** | | | |
|Gestione di dispositivi mobili | |✔️ |✔️ |
|Possibilità di bloccare l'annullamento della registrazione | |✔️ |✔️ |
|Accesso aziendale basato su certificati Wi-Fi | |✔️ |✔️ |
|Microsoft Store (consumer) |Consumer |Filtrare tramite MDM |Filtrare tramite MDM |
|[Portale di Business Store](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Sicurezza e identità** | | | |
|Accedere con un account Azure Active Directory (Azure AD) |✔️ |✔️ |✔️ |
|Accedere con l'account Microsoft (MSA) |✔️ |✔️ |✔️ |
|Credenziali di nuova generazione con sblocco PIN |✔️ |✔️ |✔️ |
|[Avvio sicuro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Manutenzione e supporto** | | | |
|Aggiornamenti automatici del sistema non appena arrivano |✔️ |✔️ |✔️ |
|[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term Servicing Channel (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Abilitazione delle funzionalità commerciali

L'amministratore IT dell'organizzazione può configurare funzionalità commerciali come Microsoft Store per le aziende, modalità tutto schermo e accesso Wi-Fi aziendale. La [Microsoft HoloLens](index.yml) documentazione fornisce istruzioni dettagliate per la registrazione dei dispositivi e l'installazione di app da Microsoft Store per le aziende.

## <a name="see-also"></a>Vedi anche

- [Microsoft HoloLens](index.yml)
- [Modalità tutto schermo](hololens-kiosk.md)
- [CSP supportati nei dispositivi HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store For Business e applicazioni line-of-business](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Uso delle app line-of-business](/microsoft-store/working-with-line-of-business-apps)
