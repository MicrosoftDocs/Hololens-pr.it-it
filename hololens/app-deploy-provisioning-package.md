---
title: Pacchetto di provisioning
description: Informazioni sulla creazione di pacchetti di app, il provisioning, la distribuzione e la distribuzione di app aziendali per HoloLens dispositivi.
keywords: app, distribuzione di app, distribuzione di app aziendali, provisioning
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
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427201"
---
# <a name="provisioning-package"></a>Pacchetto di provisioning

I pacchetti di provisioning possono essere usati per preparare e configurare i dispositivi in un ambiente senza accesso alla gestione degli endpoint. Possono anche essere distribuiti in un dispositivo indipendentemente dall'identità dell'utente, dallo stato di registrazione, durante l'esperienza predefinita o applicando un pacchetto di provisioning durante [l'installazione](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)di .

## <a name="provisioning-packages-considerations"></a>Considerazioni sul provisioning dei pacchetti

* App non pubbliche
* Solo caricamento laterale USB
* Nessun aggiornamento automatico (richiede aggiornamenti manuali tramite PPKG)

Le app installate tramite un pacchetto di provisioning devono essere firmate da un certificato nell'archivio del computer locale. I pacchetti di provisioning possono installare certificati solo nell'archivio del dispositivo (computer locale). Di conseguenza, un'app e un certificato possono essere installati tramite lo stesso pacchetto di provisioning. Se si distribuisce il certificato da MDM o si esegue l'installazione tramite [Gestione](certificate-manager.md)certificati, assicurarsi di distribuire il certificato nell'archivio computer locale per firmare le app installate in questo modo.

Per informazioni di base sulla creazione di un pacchetto di provisioning per HoloLens dispositivi, vedere HoloLens [Provisioning](/hololens/hololens-provisioning). Per distribuire un'app, è necessario iniziare con il provisioning avanzato.

> [!NOTE]
> HoloLens (prima generazione) ha un supporto limitato per l'installazione di app (**UniversalAppInstall**) usando un pacchetto di provisioning. HoloLens (prima generazione) i dispositivi supportano solo l'installazione di un'app tramite PPKG solo durante la configurazione guidata e solo con le installazioni del contesto utente.

## <a name="setup"></a>Configurazione

In [Windows Configuration Designer seguire](https://www.microsoft.com/store/productId/9NBLGGH4TX22) questa procedura.

1. Impostare ApplicationManagement/AllowAllTrustedApps su "Sì". Vedere: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Passare a **UniversalAppInstall**  >  **UserContextApp** immettere **PackageFamilyName**. Vedere [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).

   È possibile usare Portale di dispositivi in un dispositivo in cui è già installata l'app. Visitare la pagina App e esaminare la riga PackageRelativeID, tutte le informazioni prima di "!" **PackageFamilyName** è .

3. Si noti quindi che è presente una nuova sezione, **ApplicationFile**. Usare questa area per caricare il bundle appx.

4. A seconda che l'app sia stata acquistata o creata una propria app LOB, sarà necessario caricare il file di licenza o il certificato di sicurezza.

    - Per il file di licenza: passare a **UniversalAppInstall**  >  **UserContextAppLicence** e immettere l'ID prodotto della licenza. Verrà creata una nuova sezione <b>LicenseProductID:</b><i>yourlicenseproductid,</i> selezionare questa nuova sezione e passare al percorso della licenza e caricarla.
        - Vedere [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - Per il file di sicurezza, passare a **Certificati** e selezionare il certificato da installare insieme al bundle .appx.

Assicurarsi di salvare il progetto in un percorso sicuro. Esportarlo come pacchetto **di provisioning.**   

Vedere anche: [Applicare il pacchetto di provisioning HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
