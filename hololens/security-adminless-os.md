---
title: Sicurezza del sistema operativo senza amministratore
description: Informazioni sui sistemi operativi senza amministrazione, sui proprietari dei dispositivi e sulla sicurezza HoloLens dispositivi di realtà mista.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, sistema operativo, sistema operativo senza amministratore, sistema operativo amministratore, sistema operativo senza amministratore, hololens 2, sicurezza hololens2,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639404"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="928b4-104">Sistema operativo senza amministratore</span><span class="sxs-lookup"><span data-stu-id="928b4-104">Admin-less operating system</span></span>

<span data-ttu-id="928b4-105">HoloLens 2 riduce al minimo la superficie di attacco per l'escalation dei privilegi disabilitando il supporto per il gruppo Administrators e limitando tutto il codice dell'applicazione UWP di terze parti in modo che sia eseguito solo come utenti standard all'interno della sandbox AppContainer.</span><span class="sxs-lookup"><span data-stu-id="928b4-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="928b4-106">A questo codice viene concesso l'accesso solo alle risorse protette dalle funzionalità esplicitamente manifestate nell'applicazione per un utente non elevato, oltre alle risorse accessibili a tutti gli AppContainer.</span><span class="sxs-lookup"><span data-stu-id="928b4-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="928b4-107">Queste funzionalità dell'applicazione continuano a avere il modello di classificazione a tre livelli:</span><span class="sxs-lookup"><span data-stu-id="928b4-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="928b4-108">Generale</span><span class="sxs-lookup"><span data-stu-id="928b4-108">General</span></span>
  * <span data-ttu-id="928b4-109">Con restrizioni</span><span class="sxs-lookup"><span data-stu-id="928b4-109">Restricted</span></span>
  * <span data-ttu-id="928b4-110">Windows</span><span class="sxs-lookup"><span data-stu-id="928b4-110">Windows</span></span>

<span data-ttu-id="928b4-111">Windows componenti possono anche sfruttare la sandbox AppContainer tramite UWP di sistema.</span><span class="sxs-lookup"><span data-stu-id="928b4-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="928b4-112">Per altre informazioni sulla piattaforma UWP (Universal Windows Platform), vedere la [documentazione della piattaforma UWP.](/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="928b4-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](/windows/uwp/).</span></span> <span data-ttu-id="928b4-113">Inoltre, i componenti Windows con esigenze di riduzione dei privilegi maggiori (ad esempio pagine di contenuto del browser o parser) usano la sandbox LPAC (Less Privileged AppContainer), che consente di ridurre l'accesso al set di risorse accessibili a tutti gli AppContainer.</span><span class="sxs-lookup"><span data-stu-id="928b4-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="928b4-114">Proprietario del dispositivo</span><span class="sxs-lookup"><span data-stu-id="928b4-114">Device owner</span></span>

<span data-ttu-id="928b4-115">Infine, l'esecuzione di operazioni specifiche a livello di dispositivo, ad esempio l'aggiunta del dispositivo a un tenant o la gestione degli utenti, è consentita solo per i "proprietari dei dispositivi".</span><span class="sxs-lookup"><span data-stu-id="928b4-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="928b4-116">Questo gruppo viene popolato dagli utenti nel dispositivo tramite uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="928b4-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="928b4-117">Il primo utente del dispositivo è sempre designato come proprietario.</span><span class="sxs-lookup"><span data-stu-id="928b4-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="928b4-118">Per Azure AD utenti, l'eccezione a questa regola è che se il dispositivo viene aggiunto Azure AD tramite Autopilot o la registrazione Azure AD bulk, che usa un utente non reale.</span><span class="sxs-lookup"><span data-stu-id="928b4-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="928b4-119">In questo caso, il primo utente di AAD che accede al dispositivo potrebbe non essere automaticamente proprietario del dispositivo, a meno che tale utente non abbia il ruolo "amministratore globale" o "amministratore del dispositivo" assegnato in portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="928b4-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="928b4-120">Per altre informazioni, vedere la nota seguente.</span><span class="sxs-lookup"><span data-stu-id="928b4-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="928b4-121">Quando un utente viene promosso come proprietario dall'esperienza Impostazioni UX da un altro proprietario nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="928b4-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="928b4-122">Se il proprietario del dispositivo non è più disponibile (lascia l'azienda) e il dispositivo viene aggiunto Azure AD, l'amministratore tenant può modificare il proprietario del dispositivo in un nuovo utente portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="928b4-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="928b4-123">Gli amministratori globali e gli amministratori Azure AD di un tenant vengono connessi in modo implicito come proprietari nel dispositivo senza richiedere uno dei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="928b4-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="928b4-124">Gli amministratori IT possono gestire le app a cui possono accedere tramite [i criteri sulla](/windows/client-management/mdm/policy-csp-privacy) privacy.</span><span class="sxs-lookup"><span data-stu-id="928b4-124">IT administrators can manage what apps can access through [Privacy](/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="928b4-125">Per altre informazioni su chi è stato reso proprietario di un dispositivo aggiunto Azure AD, vedere la documentazione "Assegna amministratore locale" (ma leggere ["Amministratore locale"](/azure/active-directory/devices/assign-local-admin) come "proprietario del dispositivo" perché l'amministratore non esiste HoloLens).</span><span class="sxs-lookup"><span data-stu-id="928b4-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>