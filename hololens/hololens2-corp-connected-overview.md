---
title: Guida alla distribuzione - Guida alla HoloLens 2 aziendale con Dynamics 365 Guides - Panoramica
description: Informazioni su come registrare HoloLens 2 dispositivi con Dynamics 365 Guides su una rete connessa aziendale.
keywords: HoloLens, gestione, connessa aziendale, Dynamics 365 Guides, AAD, Azure AD, MDM, gestione dei dispositivi mobili
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309773"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guida alla distribuzione - Guida alla HoloLens 2 aziendale con Dynamics 365 Guides - Panoramica

Questa guida consente ai professionisti IT di pianificare e distribuire dispositivi Microsoft HoloLens 2 con guide di Dynamics 365 alla propria organizzazione. Questa guida è ideale per i progetti pilota e le distribuzioni di produzione ed è simile alla guida [Scenario B: Distribuire all'interno della rete dell'organizzazione.](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) Dopo aver testato il modello di verifica, usare questa guida per procedere con l'integrazione di HoloLens nell'organizzazione.

In questa guida verrà illustrato come registrare i dispositivi nella gestione dei dispositivi esistente, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare una guida di Dynamics 365, nonché usare app line-of-business personalizzate dopo la configurazione del dispositivo. 

## <a name="prerequisites"></a>Prerequisiti

Dovrebbe essere già presente l'infrastruttura seguente:
- Wi-Fi
    - Rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud
    - Autenticazione del certificato basata su dispositivo.
- Azure Active Directory (Azure AD) Partecipare alla registrazione automatica MDM (Azure AD[necessaria una sottoscrizione P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
- Mdm (Intune) Gestito
    - Una o più applicazioni vengono distribuite tramite MDM.
- Rete 
    - Certificati (SCEP o PKCS)
    - Configurazione proxy
- Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
    - Sono supportati uno o più utenti per dispositivo.
- Diversi livelli di configurazioni di blocco del dispositivo applicate in base a casi d'uso specifici, da Completamente aperto a App singola in modalità tutto schermo.

## <a name="guides-licensing-and-requirements"></a>[Guida alle licenze e ai requisiti](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Account Azure AD
- Dynamics 365 Guides applications PC and HoloLens
- Sottoscrizione di Dynamics 365 Guides
    - Microsoft Dataverse (incluso)
    - Power Apps (incluso)
- Power BI Desktop
- Connettività di rete

![Diagramma della rete connessa Corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>Fasi della distribuzione
### <a name="prepare"></a>Preparare
> [!div class="checklist"]
>- [Informazioni sulle informazioni di base sull'infrastruttura per HoloLens 2 dispositivi.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Altre informazioni Azure AD e configurarne una, se non è necessario.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Informazioni sulla gestione delle identità e su come configurare al meglio Azure AD account.](hololens2-corp-connected-prepare.md#identity-management)
>- [Altre informazioni su MDM e configurazione con Intune se non ne è già disponibile una.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Acquisire familiarità con il Wi-Fi basato su certificati.](hololens2-corp-connected-prepare.md#certificates)
>- [Acquisire familiarità con proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Informazioni su come usare le app line-of-business.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Altre informazioni sul modo in cui è possibile usare le guide per l'organizzazione.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configurare
> [!div class="checklist"]
>- [Come creare utenti e gruppi.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Come configurare la registrazione automatica.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Come configurare certificati e profili Wi-Fi per la connettività Wi-Fi aziendale.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Caricare e assegnare pacchetti di app line-of-business (LOB).](hololens2-corp-connected-configure.md#app-deployment)
>- [Configurare le guide di Dynamics 365.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Come configurare la modalità tutto schermo (facoltativo).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Come configurare WDAC (facoltativo).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Distribuisci
> [!div class="checklist"]
>-  [Convalidare la registrazione tramite dispositivo e MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Convalidare Wi-Fi certificati.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Convalidare l'installazione dell'app LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Convalidare le guide tramite creazione e funzionamento.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Effettuare la manutenzione
> [!div class="checklist"]
>- [Aggiornare HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Come aggiornare le guide (app dello Store).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Come aggiornare le app LOB.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Piano di sviluppo.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Creazione di un piano di supporto.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opzioni di gestione dei dispositivi.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Passaggio successivo 
> [!div class="nextstepaction"]
> [Distribuzione connessa aziendale - Preparare](hololens2-corp-connected-prepare.md)
