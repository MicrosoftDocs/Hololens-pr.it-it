---
title: Pacchetto di provisioning
description: app, distribuzione di app, demployment dell'app Enterprise, provisioning
keywords: app, distribuzione di app, demployment dell'app Enterprise, provisioning
author: v-jodben
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
ms.openlocfilehash: 7417f9e8cf1921d9fdb57dbd96fff094e21c44f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857953"
---
# Pacchetto di provisioning

I pacchetti di provisioning possono essere usati per preparare e configurare i dispositivi in un ambiente senza accedere alla gestione degli endpoint. Possono anche essere distribuiti in un dispositivo indipendentemente dall'identità dell'utente, dallo stato di registrazione, durante l'esperienza fuori sede (OOBE) o [applicando un pacchetto di provisioning durante l'installazione](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## Considerazioni sul provisioning di pacchetti:
* App non pubbliche
* Solo caricamento laterale USB
* Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite PPKGs)

> [!NOTE] 
> Per informazioni sulle nozioni di base sulla creazione di un pacchetto di provisioning per i dispositivi HoloLens, visitare il [provisioning di HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning). Per distribuire un'app, devi iniziare con il provisioning avanzato. 

## Installazione

In [Windows Configuration designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) seguire 4 passaggi.

1. Impostare ApplicationManagement/AllowAllTrustedApps su "Sì". Vedere: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).
2. In **UniversalAppInstall**  >  **UserContextAppLicense** immettere il **packageFamilyName**. Vedere [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Vedere anche: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - Se non si conosce questa operazione, è possibile usare Device Portal in un dispositivo a cui è già stata installata l'app. Visita la pagina delle app e guarda la linea PackageRelativeID, tutte le informazioni prima del "!" È il **packageFamilyName**.
3. Si vedrà quindi che si ha una nuova sezione, **ApplicationFile**. Usare questa area per caricare il bundle di appx. 
4. A seconda di se l'app è stata acquistata o è stata creata una propria app LOB, sarà necessario caricare il file di licenza o il certificato di sicurezza.
    - Per il file di licenza: in **UniversalAppInstall**  >  **UserContextAppLience** e passare al percorso della licenza e caricarlo. 
    - Per file di sicurezza, passare a **certificati** e selezionare il certificato da installare insieme al bundle. appx. 

Assicurarsi di salvare il progetto in una posizione sicura. Quindi **esportalo** come **pacchetto di provisioning**.  
    
Vedere anche: [applicare il pacchetto provisiong a HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
