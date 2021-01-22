---
title: Pacchetto di provisioning
description: Informazioni su come creare pacchetti di app, provisioning, distribuzione e distribuzione di app Enterprise per dispositivi HoloLens.
keywords: app, distribuzione di app, distribuzione di app Enterprise, provisioning
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283697"
---
# Pacchetto di provisioning

I pacchetti di provisioning possono essere usati per preparare e configurare i dispositivi in un ambiente senza accedere alla gestione degli endpoint. Possono anche essere distribuiti in un dispositivo indipendentemente dall'identità dell'utente, dallo stato di registrazione, durante l'esperienza fuori sede (OOBE) o [applicando un pacchetto di provisioning durante l'installazione](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## Considerazioni sul provisioning di pacchetti:

* App non pubbliche
* Solo caricamento laterale USB
* Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite PPKGs)

Le app installate tramite un pacchetto di provisioning devono essere firmate da un certificato nell'archivio del computer locale. Il provisioning dei pacchetti può installare solo i certificati nello Store del dispositivo (computer locale), quindi un'app e un certificato possono essere installati tramite lo stesso pacchetto di provisioning. Se si distribuisce il certificato da MDM o si esegue l'installazione tramite [Gestione certificati](certificate-manager.md), assicurarsi di distribuire il certificato nell'archivio del computer locale per firmare le app installate in questo modo.

Per informazioni sulle nozioni di base sulla creazione di un pacchetto di provisioning per i dispositivi HoloLens, visitare il [provisioning di HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning). Per distribuire un'app, devi iniziare con il provisioning avanzato.

> [!NOTE]
> HoloLens (1a generazione) ha un supporto limitato per l'installazione di app (**UniversalAppInstall**) usando un pacchetto di provisioning. I dispositivi HoloLens (1a Gen) supportano solo l'installazione di un'app tramite PPKG solo durante la configurazione guidata e solo con le installazioni di contesto utente.

## Installazione

In [Windows Configuration designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) seguire quattro passaggi.

1. Impostare ApplicationManagement/AllowAllTrustedApps su "Sì". Vedere: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Passare a **UniversalAppInstall**  >  **UserContextAppLicense** immettere il **packageFamilyName**. Vedere [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Vedere anche: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Puoi usare Device Portal in un dispositivo a cui hai già installato l'app. Visita la pagina delle app e guarda la linea PackageRelativeID, tutte le informazioni prima del "!" È il **packageFamilyName**.

3. Si vedrà quindi che si ha una nuova sezione, **ApplicationFile**. Usare questa area per caricare il bundle di appx.

4. A seconda di se l'app è stata acquistata o è stata creata una propria app LOB, sarà necessario caricare il file di licenza o il certificato di sicurezza.

    - Per il file di licenza: passare a **UniversalAppInstall**  >  **UserContextAppLicence** e passare al percorso della licenza e caricarlo.
    - Per il file di sicurezza, passare a **certificati** e selezionare il certificato da installare accanto al bundle appx.

Assicurarsi di salvare il progetto in una posizione sicura. Quindi **esportalo** come **pacchetto di provisioning**.  

Vedere anche: [applicare il pacchetto di provisioning a HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
