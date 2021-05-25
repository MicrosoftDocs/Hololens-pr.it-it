---
title: Windows Autopilot supporto della registrazione per HoloLens 2
description: Informazioni su come ottenere il supporto della registrazione per Autopilot HoloLens 2 dispositivi.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Pilota automatico
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398974"
---
# <a name="hololens-2-registration-support-for-autopilot"></a><span data-ttu-id="23094-104">HoloLens 2 supporto della registrazione per Autopilot</span><span class="sxs-lookup"><span data-stu-id="23094-104">HoloLens 2 Registration Support for Autopilot</span></span>

<span data-ttu-id="23094-105">I clienti e i provider di soluzioni cloud Microsoft possono ora registrare HoloLens 2 dispositivi inviando direttamente le richieste Supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23094-105">Customers and Microsoft Cloud Solution Providers (CSPs) can now register HoloLens 2 devices by directly submitting requests to Microsoft Support.</span></span> <span data-ttu-id="23094-106">Questa pagina illustra i requisiti per gli scenari di registrazione di Autopilot supportati seguenti:</span><span class="sxs-lookup"><span data-stu-id="23094-106">This page outlines the requirements for the following supported Autopilot registration scenarios:</span></span>

- <span data-ttu-id="23094-107">**HoloLens 2 registrazione di Device Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="23094-107">**HoloLens 2 Device Autopilot Registration**.</span></span> <span data-ttu-id="23094-108">Invia la richiesta per registrare HoloLens 2 dispositivi in Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="23094-108">Submits request to register HoloLens 2 devices into Windows Autopilot.</span></span>
- <span data-ttu-id="23094-109">**HoloLens 2 richiesta hash hardware del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="23094-109">**HoloLens 2 Device Hardware Hash Request**.</span></span> <span data-ttu-id="23094-110">Invia la richiesta a Supporto tecnico Microsoft di fornire hash hardware che i clienti o i CSP possono usare per registrare automaticamente i dispositivi tramite Microsoft Intune o Microsoft Partner Center.</span><span class="sxs-lookup"><span data-stu-id="23094-110">Submits request to Microsoft Support to provide you with hardware hashes that customers or CSPs can use to self-register devices via Microsoft Intune or the Microsoft Partner Center.</span></span>
- <span data-ttu-id="23094-111">**HoloLens 2 dispositivo Autopilot Deregistration**.</span><span class="sxs-lookup"><span data-stu-id="23094-111">**HoloLens 2 Device Autopilot Deregistration**.</span></span> <span data-ttu-id="23094-112">Invia la richiesta di eliminazione dei dispositivi Windows Autopilot, in genere usata negli scenari di fine vita del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23094-112">Submits request to delete devices from Windows Autopilot, typically used in device end of life scenarios.</span></span>

<span data-ttu-id="23094-113">Nella tabella seguente vengono fornite informazioni dettagliate sulle informazioni che è necessario raccogliere prima *di* inviare richieste di registrazione Supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23094-113">The following table details the information you will need to collect *prior* to submitting registration requests to Microsoft Support.</span></span>

| <span data-ttu-id="23094-114">Informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="23094-114">Required Information</span></span> | <span data-ttu-id="23094-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23094-115">Description</span></span> | <span data-ttu-id="23094-116">Registrazione di Autopilot</span><span class="sxs-lookup"><span data-stu-id="23094-116">Autopilot Registration</span></span>  | <span data-ttu-id="23094-117">Richiesta hash hardware</span><span class="sxs-lookup"><span data-stu-id="23094-117">Hardware Hash Request</span></span> | <span data-ttu-id="23094-118">Annullamento della registrazione di Autopilot</span><span class="sxs-lookup"><span data-stu-id="23094-118">Autopilot Deregistration</span></span> |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  <span data-ttu-id="23094-119">Azure Active Directory Tenant ID</span><span class="sxs-lookup"><span data-stu-id="23094-119">Azure Active Directory Tenant ID</span></span>    |    <span data-ttu-id="23094-120">L Azure Active Directory ID tenant è un identificatore univoco globale (GUID) diverso dal nome o dal dominio dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23094-120">Your Azure Active Directory tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain.</span></span>    <span data-ttu-id="23094-121">Per trovare l'ID tenant accedere al [portale di Azure.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="23094-121">To find your Tenant ID sign into the [Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>    |     <span data-ttu-id="23094-122">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-122">✔️</span></span>                         |                              |                         <span data-ttu-id="23094-123">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-123">✔️</span></span>                        |
|  <span data-ttu-id="23094-124">Azure Active Directory dominio</span><span class="sxs-lookup"><span data-stu-id="23094-124">Azure Active Directory Domain Name</span></span>    |   <span data-ttu-id="23094-125">Nome di dominio di primo livello. ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="23094-125">Your top-level domain name; for example, contoso.com.</span></span>    |     <span data-ttu-id="23094-126">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-126">✔️</span></span>                         |                              |                         <span data-ttu-id="23094-127">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-127">✔️</span></span>                        |
|  <span data-ttu-id="23094-128">Prova di proprietà</span><span class="sxs-lookup"><span data-stu-id="23094-128">Proof of Ownership</span></span>    |   <span data-ttu-id="23094-129">Verificare la prova di proprietà caricando la fattura originale in formato PDF.</span><span class="sxs-lookup"><span data-stu-id="23094-129">Verify proof of ownership by uploading the original bill of sale or invoice in PDF format.</span></span> <span data-ttu-id="23094-130">Gli screenshot non vengono accettati.</span><span class="sxs-lookup"><span data-stu-id="23094-130">Screenshots are not accepted.</span></span> <span data-ttu-id="23094-131">La fattura o la fattura deve includere quanto segue: Numeri di serie del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23094-131">The bill of sale or invoice must include the following: Device serial numbers.</span></span> <span data-ttu-id="23094-132">Nome della società.</span><span class="sxs-lookup"><span data-stu-id="23094-132">Company name.</span></span>     |     <span data-ttu-id="23094-133">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-133">✔️</span></span>                         |              <span data-ttu-id="23094-134">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-134">✔️</span></span>                |                         <span data-ttu-id="23094-135">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-135">✔️</span></span>                        |
|  <span data-ttu-id="23094-136">Numeri di serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="23094-136">Device serial numbers</span></span>    |   <span data-ttu-id="23094-137">Caricare il file di Excel in formato CSV con ogni numero di serie del dispositivo in una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="23094-137">Upload Excel file in CSV format with each device serial number in a new line.</span></span>     |     <span data-ttu-id="23094-138">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-138">✔️</span></span>                         |              <span data-ttu-id="23094-139">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-139">✔️</span></span>                |                         <span data-ttu-id="23094-140">✔️</span><span class="sxs-lookup"><span data-stu-id="23094-140">✔️</span></span>                        |

## <a name="submit-support-requests"></a><span data-ttu-id="23094-141">Inviare richieste di supporto</span><span class="sxs-lookup"><span data-stu-id="23094-141">Submit support requests</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="23094-142">Inviare il supporto per la registrazione di Autopilot per HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="23094-142">Submit Autopilot Registration Support for HoloLens 2</span></span>](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)