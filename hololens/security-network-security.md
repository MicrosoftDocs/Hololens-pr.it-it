---
title: Sicurezza della rete
description: sicurezza della rete
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, rete, sicurezza della rete
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c88a9af7369a6a9d6fb115fb820c0a4da13eafdc
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865841"
---
# <span data-ttu-id="bf4fd-104">Sicurezza della rete</span><span class="sxs-lookup"><span data-stu-id="bf4fd-104">Network security</span></span>

## <span data-ttu-id="bf4fd-105">Protocolli di rete</span><span class="sxs-lookup"><span data-stu-id="bf4fd-105">Network protocols</span></span>

<span data-ttu-id="bf4fd-106">L'obsoleto sistema NetBIOS (Network Basic Input/Output System) era ampiamente usato in passato in scenari LAN, spesso per la risoluzione dei nomi in un computer e in cartelle condivise.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="bf4fd-107">Nel corso del tempo, infatti, NetBIOS si è rivelato vulnerabile agli attacchi multipli e la relativa adozione è diminuita in favore di altri protocolli più sicuri.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="bf4fd-108">Per rimuovere il problema della vulnerabilità, HoloLens 2 ha eliminato il codice correlato a NetBIOS dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="bf4fd-109">I protocolli TLS (Transport Layer Security) sono in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="bf4fd-110">Per stare al passo con i vari exploit di sicurezza che sono stati scoperti in quest'area, il settore informatico è passato a versioni più recenti ed efficaci.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="bf4fd-111">A causa del tempo necessario perché tutte le distribuzioni dei server adottino le nuove versioni del protocollo TLS, è possibile implementare un meccanismo di fallback che consenta al client e ai server nelle diverse versioni del protocollo predefinite di comunicare ancora durante il periodo di transizione.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

<span data-ttu-id="bf4fd-112">Tuttavia, tali meccanismi di fallback aumentano i rischi correlati alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-112">However, such fallback mechanisms increase security risks.</span></span> <span data-ttu-id="bf4fd-113">Una volta compreso questo problema, in HoloLens 2 il fallback da TLS 1.2 a TLS 1.1 o 1.0 è stato disabilitato e non è disponibile un'interfaccia utente per abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-113">Understanding this issue, in HoloLens 2 the fallback from TLS 1.2 to TLS 1.1 or 1.0 has been disabled, and there is no user interface to enable it.</span></span> <span data-ttu-id="bf4fd-114">Inoltre, durante la sincronizzazione TLS, il client richiederà un TLS 1.2 e non consentirà al server di eseguire il downgrade a una versione meno recente.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-114">Furthermore, during the TLS handshake, the client will ask for TLS 1.2, and does not allow the server to downgrade to a lower version.</span></span>

## <span data-ttu-id="bf4fd-115">Connettività sicura</span><span class="sxs-lookup"><span data-stu-id="bf4fd-115">Secure connectivity</span></span> 

<span data-ttu-id="bf4fd-116">Il firewall di Windows Defender offre funzionalità importanti per garantire la connettività dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-116">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="bf4fd-117">Con HoloLens 2, il firewall è sempre abilitato e non sono disponibili modi per disabilitarlo a livello di programmazione o tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-117">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="bf4fd-118">L'accesso remoto e la privacy della connessione ai client per dispositivi mobili possono essere assicurate tramite la [piattaforma di plug-in VPN UWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="bf4fd-118">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="bf4fd-119">I provider VPN di terze parti possono creare i loro plug-in usando le API WinRT, che verranno eseguite nel sandbox di AppContainer, eliminando la complessità e le problematiche spesso associate alla scrittura dei driver a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="bf4fd-119">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
