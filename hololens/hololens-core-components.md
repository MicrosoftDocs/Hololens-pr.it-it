---
title: Pianificazione HoloLens 2 distribuzione in un ambiente commerciale
description: Informazioni sulle esigenze di base per la distribuzione e la gestione di HoloLens in ambienti aziendali, tra cui l'infrastruttura, Azure Active Directory e la gestione dei dispositivi mobili.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032440"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Pianificazione HoloLens 2 distribuzione in un ambiente commerciale

## <a name="overview"></a>Panoramica

> [!NOTE]
> Questa panoramica ha lo scopo di aiutare i professionisti IT a comprendere le considerazioni per la distribuzione e la gestione Microsoft HoloLens 2 dispositivi all'interno di un'organizzazione. Per gli utenti finali dei dispositivi, vedere Get your HoloLens 2 ready to use to get started [(Prepararsi all'uso per](hololens2-setup.md) iniziare).

HoloLens 2 viene eseguito Windows 10 Holographic che offre alle organizzazioni tecnologie di gestione di dispositivi mobili e app solide, flessibili e integrate. Windows 10 Holographic supporta la gestione del ciclo di vita dei dispositivi end-to-end per offrire alle aziende il controllo su dispositivi, dati e app. Il HoloLens 2 può essere facilmente incorporato nelle procedure standard del ciclo di vita, dalla registrazione dei dispositivi, alla configurazione e alla gestione delle applicazioni fino alla manutenzione e al ritiro usando una soluzione completa di gestione dei dispositivi mobili.

I passaggi e il video seguenti possono essere utili per illustrare il processo di adozione HoloLens 2 all'interno dell'organizzazione.

| &nbsp; | &nbsp; |
|--|--|
| ![Passaggio 1.](images/1green.png)| <br/> **[Scenari di distribuzione comuni:](hololens-requirements.md)** comprendere gli scenari di distribuzione ed esplorare i componenti di base necessari per distribuire HoloLens 2 dispositivi. |
| ![Passaggio 2.](images/2green.png)| <br/> **[Preparazione:](#prepare)** acquisire familiarità con le informazioni di base sull'infrastruttura necessarie per HoloLens 2. |
| ![Passaggio 3.](images/3green.png) | <br/> **[Configurare:](#configure)** informazioni su come configurare i componenti essenziali per una distribuzione basata sul cloud. |
| ![Passaggio 4.](images/4green.png) | <br/> **[Distribuisci:](#deploy)** informazioni su come distribuire i dispositivi e distribuire le applicazioni in modo sicuro ed efficiente. |
| ![Passaggio 5.](images/5green.png) | <br/> **[Gestisci:](#maintain)** individuare gli elementi necessari per mantenere correttamente lo stato dei dispositivi HoloLens 2 e garantire la conformità ai criteri aziendali. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Preparare

Informazioni sui servizi di infrastruttura essenziali necessari per supportare il set completo di HoloLens 2 funzionalità.

| Componente | Descrizione |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Fornisce la gestione delle identità e degli accessi per HoloLens 2  |
| [Gestione dei dispositivi mobili](hololens-mdm-configure.md)| Gestisce HoloLens 2 dispositivi connessi al tenant  |
| [Rete Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi è disponibile e i dispositivi possono essere connessi a Internet  |

## <a name="configure"></a>Configurare

Usare Intune e Autopilot come soluzioni a tocco ridotto per registrare e configurare HoloLens 2 per il tenant Azure AD dell'organizzazione e MDM.

| Componente | Descrizione |
|-----------|------------|
| [Registrazione automatica](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Dopo l'accesso iniziale, i dispositivi vengono registrati automaticamente Azure AD e registrati in MDM  |
| [Licenze dell'applicazione](hololens2-cloud-connected-configure.md#application-licenses)| Può essere applicato a utenti, gruppi di utenti o gruppi di dispositivi  |
| [Utenti e gruppi di Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Consente di assegnare configurazioni e licenze per l'HoloLens 2  |

## <a name="deploy"></a>Distribuisci

Distribuire i HoloLens 2 e convalidarne la configurazione. 

| Componente | Descrizione |
|-----------|------------|
| [Convalida della registrazione](hololens2-corp-connected-deploy.md#enrollment-validation) | Verificare che il dispositivo sia Azure AD aggiunto da Impostazioni o dal portale di Azure |
| [Convalida del certificato](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Controllare le impostazioni e verificare che siano state distribuite correttamente |
| [Convalidare le installazioni dell'app](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Verificare che l'app sia presente e funzionante nel HoloLens 2 |

## <a name="maintain"></a>Effettuare la manutenzione

Usare Windows Update for Business insieme al sistema MDM o al Microsoft Store per mantenere aggiornata la flotta di HoloLens 2 e app.

| Componente | Descrizione |
|-----------|------------|
| [Aggiornare HoloLens 2](hololens-updates.md) | Configurare gli aggiornamenti in base alle esigenze Windows Updates for Business |
| [Aggiornare le app](app-deploy-overview.md) | Configurare tramite il sistema MDM o il Microsoft Store
