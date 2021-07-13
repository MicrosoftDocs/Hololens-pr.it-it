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
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639081"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="a73d5-103">Pianificazione HoloLens 2 distribuzione in un ambiente commerciale</span><span class="sxs-lookup"><span data-stu-id="a73d5-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="a73d5-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a73d5-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="a73d5-105">Questa panoramica ha lo scopo di aiutare i professionisti IT a comprendere le considerazioni per la distribuzione e la gestione Microsoft HoloLens 2 dispositivi all'interno di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a73d5-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="a73d5-106">Per gli utenti finali del dispositivo, vedere Get your HoloLens 2 ready to use to get started [(Prepararsi all'uso per](hololens2-setup.md) iniziare).</span><span class="sxs-lookup"><span data-stu-id="a73d5-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="a73d5-107">HoloLens 2 viene eseguito in Windows 10 Holographic che offre alle organizzazioni tecnologie di gestione di dispositivi mobili e app affidabili, flessibili e integrate.</span><span class="sxs-lookup"><span data-stu-id="a73d5-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="a73d5-108">Windows 10 Holographic supporta la gestione del ciclo di vita dei dispositivi end-to-end per offrire alle aziende il controllo su dispositivi, dati e app.</span><span class="sxs-lookup"><span data-stu-id="a73d5-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="a73d5-109">Il HoloLens 2 può essere facilmente incorporato nelle procedure standard del ciclo di vita, dalla registrazione dei dispositivi, alla configurazione e alla gestione delle applicazioni fino alla manutenzione e al ritiro usando una soluzione completa di gestione dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="a73d5-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="a73d5-110">I passaggi e il video seguenti possono essere utili per illustrare il processo di adozione HoloLens 2 all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a73d5-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![Passaggio 1](images/1green.png)| <br/> <span data-ttu-id="a73d5-112">**[Scenari di distribuzione comuni:](hololens-requirements.md)** comprendere gli scenari di distribuzione ed esplorare i componenti di base necessari per distribuire HoloLens 2 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a73d5-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Passaggio 2](images/2green.png)| <br/> <span data-ttu-id="a73d5-114">**[Preparazione:](#prepare)** acquisire familiarità con le informazioni di base sull'infrastruttura necessarie per HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a73d5-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Passaggio 3](images/3green.png) | <br/> <span data-ttu-id="a73d5-116">**[Configurare:](#configure)** informazioni su come configurare i componenti essenziali per una distribuzione basata sul cloud.</span><span class="sxs-lookup"><span data-stu-id="a73d5-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Passaggio 4](images/4green.png) | <br/> <span data-ttu-id="a73d5-118">**[Distribuisci:](#deploy)** informazioni su come distribuire i dispositivi e distribuire le applicazioni in modo sicuro ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="a73d5-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Passaggio 5](images/5green.png) | <br/> <span data-ttu-id="a73d5-120">**[Manutenzione:](#maintain)** individuare gli elementi necessari per mantenere correttamente lo stato dei dispositivi HoloLens 2 e garantire la conformità ai criteri aziendali.</span><span class="sxs-lookup"><span data-stu-id="a73d5-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="a73d5-121">Preparare</span><span class="sxs-lookup"><span data-stu-id="a73d5-121">Prepare</span></span>

<span data-ttu-id="a73d5-122">Informazioni sui servizi di infrastruttura essenziali necessari per supportare il set completo di HoloLens 2 funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a73d5-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="a73d5-123">Componente</span><span class="sxs-lookup"><span data-stu-id="a73d5-123">Component</span></span> | <span data-ttu-id="a73d5-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a73d5-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="a73d5-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="a73d5-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="a73d5-126">Fornisce la gestione delle identità e degli accessi per HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a73d5-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="a73d5-127">Gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="a73d5-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="a73d5-128">Gestisce HoloLens 2 dispositivi connessi al tenant</span><span class="sxs-lookup"><span data-stu-id="a73d5-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="a73d5-129">Rete Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a73d5-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="a73d5-130">Wi-Fi è disponibile e i dispositivi possono essere connessi a Internet</span><span class="sxs-lookup"><span data-stu-id="a73d5-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="a73d5-131">Configurare</span><span class="sxs-lookup"><span data-stu-id="a73d5-131">Configure</span></span>

<span data-ttu-id="a73d5-132">Usare Intune e Autopilot come soluzioni a tocco ridotto per la registrazione e la configurazione HoloLens 2 nel tenant di Azure AD dell'organizzazione e in MDM.</span><span class="sxs-lookup"><span data-stu-id="a73d5-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="a73d5-133">Componente</span><span class="sxs-lookup"><span data-stu-id="a73d5-133">Component</span></span> | <span data-ttu-id="a73d5-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a73d5-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="a73d5-135">Registrazione automatica</span><span class="sxs-lookup"><span data-stu-id="a73d5-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="a73d5-136">Dopo l'accesso iniziale, i dispositivi vengono registrati automaticamente Azure AD e registrati in MDM</span><span class="sxs-lookup"><span data-stu-id="a73d5-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="a73d5-137">Licenze dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a73d5-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="a73d5-138">Può essere applicato a utenti, gruppi di utenti o gruppi di dispositivi</span><span class="sxs-lookup"><span data-stu-id="a73d5-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="a73d5-139">Utenti e gruppi di Azure</span><span class="sxs-lookup"><span data-stu-id="a73d5-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="a73d5-140">Consente di assegnare configurazioni e licenze per l'HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a73d5-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="a73d5-141">Distribuisci</span><span class="sxs-lookup"><span data-stu-id="a73d5-141">Deploy</span></span>

<span data-ttu-id="a73d5-142">Distribuire i HoloLens 2 e convalidarne la configurazione.</span><span class="sxs-lookup"><span data-stu-id="a73d5-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="a73d5-143">Componente</span><span class="sxs-lookup"><span data-stu-id="a73d5-143">Component</span></span> | <span data-ttu-id="a73d5-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a73d5-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="a73d5-145">Convalida della registrazione</span><span class="sxs-lookup"><span data-stu-id="a73d5-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="a73d5-146">Verificare che il dispositivo sia Azure AD aggiunto da Impostazioni o dal portale di Azure</span><span class="sxs-lookup"><span data-stu-id="a73d5-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="a73d5-147">Convalida del certificato</span><span class="sxs-lookup"><span data-stu-id="a73d5-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="a73d5-148">Controllare le impostazioni e verificare che siano state distribuite correttamente</span><span class="sxs-lookup"><span data-stu-id="a73d5-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="a73d5-149">Convalidare le installazioni dell'app</span><span class="sxs-lookup"><span data-stu-id="a73d5-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="a73d5-150">Verificare che l'app sia presente e funzionante nel HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a73d5-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="a73d5-151">Effettuare la manutenzione</span><span class="sxs-lookup"><span data-stu-id="a73d5-151">Maintain</span></span>

<span data-ttu-id="a73d5-152">Usare Windows Update for Business insieme al sistema MDM o al Microsoft Store per mantenere aggiornata la flotta di HoloLens 2 e app.</span><span class="sxs-lookup"><span data-stu-id="a73d5-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="a73d5-153">Componente</span><span class="sxs-lookup"><span data-stu-id="a73d5-153">Component</span></span> | <span data-ttu-id="a73d5-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a73d5-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="a73d5-155">Aggiornare HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a73d5-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="a73d5-156">Configurare gli aggiornamenti in base alle esigenze Windows Updates for Business</span><span class="sxs-lookup"><span data-stu-id="a73d5-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="a73d5-157">Aggiornare le app</span><span class="sxs-lookup"><span data-stu-id="a73d5-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="a73d5-158">Configurare tramite il sistema MDM o il Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a73d5-158">Configure through your MDM system or the Microsoft Store</span></span>
