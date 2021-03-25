---
title: Guida alla distribuzione - HoloLens 2 connesso all'azienda con guide di Dynamics 365 - Panoramica
description: Scopri come registrare i dispositivi HoloLens 2 con le guide di Dynamics 365 su una rete connessa aziendale.
keywords: HoloLens, gestione, corporate connected, Guide dynamics 365, AAD, Azure AD, MDM, Gestione dispositivi mobili
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448571"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guida alla distribuzione - Corporate Connected HoloLens 2 con guide di Dynamics 365 - Panoramica

Questa guida consente ai professionisti IT di pianificare e distribuire i dispositivi Microsoft HoloLens 2 con le guide di Dynamics 365 (guide) all'organizzazione. Questa guida è ideale per le distribuzioni pilota e di produzione ed è simile allo [scenario B: Distribuire all'interno](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) della guida di rete dell'organizzazione. Dopo aver testato il modello di prova, usare questa guida per procedere con l'integrazione di HoloLens nell'organizzazione.

In questa guida verrà illustrato come registrare i dispositivi nella gestione dei dispositivi esistente, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di utilizzare una guida di Dynamics 365, oltre a usare app line-of-business personalizzate dopo la configurazione del dispositivo. 

## <a name="prerequisites"></a>Prerequisiti

Dovrebbe essere già presente l'infrastruttura seguente:
- Wi-Fi
    - Rete aziendale interna con accesso alle risorse interne e accesso limitato a Internet o ai servizi cloud
    - Autenticazione del certificato basata su dispositivo.
- Aggiunta ad Azure Active Directory (Azure AD) con registrazione automatica MDM (è necessaria la[sottoscrizione di Azure AD P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
- Mdm (Intune) Gestito
    - Una o più applicazioni vengono distribuite tramite MDM.
- Rete 
    - Certificati (SCEP o PKCS)
    - Configurazione del proxy
- Gli utenti a cui si accede con il proprio account aziendale (Azure AD)
    - È supportato uno o più utenti per dispositivo.
- Diversi livelli di configurazioni di blocco dei dispositivi applicati in base a casi di uso specifici, da Completamente aperto a Chiosco app singolo.

## [<a name="guides-licensing-and-requirements"></a>Guide licenze e requisiti](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Account Azure AD
- Applicazioni Dynamics 365 Guides PC e HoloLens
- Abbonamento a Dynamics 365 Guides
    - Microsoft Dataverse (incluso)
    - Power Apps (incluso)
- Power BI Desktop
- Connettività di rete

![Diagramma della rete connessa corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>Fasi della distribuzione
### <a name="prepare"></a>Preparazione
> [!div class="checklist"]
>- [Informazioni sugli elementi essenziali dell'infrastruttura per i dispositivi HoloLens 2.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Scopri di più su Azure AD e configurarne uno se non lo hai.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Informazioni sulla gestione delle identità e su come configurare al meglio gli account Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [Altre informazioni su MDM e configurazione con Intune se non ne hai già una pronta.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Acquisire familiarità con il Wi-Fi basato su certificato.](hololens2-corp-connected-prepare.md#certificates)
>- [Acquisire familiarità con Proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Informazioni su come usare le app line-of-business.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Ulteriori informazioni sul modo in cui è possibile utilizzare le guide per l'organizzazione.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configura
> [!div class="checklist"]
>- [Come creare utenti e gruppi.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Come configurare la registrazione automatica.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Come configurare i certificati Wi-Fi e i profili per la connettività Wi-Fi aziendale.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Caricare e assegnare pacchetti di app line-of-business (LOB).](hololens2-corp-connected-configure.md#app-deployment)
>- [Setup Dynamics 365 Guides.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Come configurare la modalità tutto schermo (facoltativo).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Come configurare WDAC (facoltativo).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Distribuisci
> [!div class="checklist"]
>-  [Convalidare la registrazione tramite dispositivo e MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Convalidare Wi-Fi certificati.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Convalidare l'installazione dell'app LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Convalidare le guide tramite la creazione e il funzionamento.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Gestione
> [!div class="checklist"]
>- [Aggiornare HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Come aggiornare le guide (archiviare le app).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Come aggiornare le app LOB.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Piano di sviluppo.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Creazione di un piano di supporto.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opzioni di gestione dei dispositivi.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Passaggio successivo 
> [!div class="nextstepaction"]
> [Distribuzione connessa all'azienda - Preparare](hololens2-corp-connected-prepare.md)
