---
title: Sicurezza della rete
description: sicurezza della rete
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, rete, sicurezza della rete
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009424"
---
# <span data-ttu-id="9b737-104">Sicurezza della rete</span><span class="sxs-lookup"><span data-stu-id="9b737-104">Network security</span></span>

## <span data-ttu-id="9b737-105">Protocolli di rete</span><span class="sxs-lookup"><span data-stu-id="9b737-105">Network protocols</span></span>

<span data-ttu-id="9b737-106">L'obsoleto sistema NetBIOS (Network Basic Input/Output System) era ampiamente usato in passato in scenari LAN, spesso per la risoluzione dei nomi in un computer e in cartelle condivise.</span><span class="sxs-lookup"><span data-stu-id="9b737-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="9b737-107">Nel corso del tempo, infatti, NetBIOS si è rivelato vulnerabile a varie tipologie di attacchi e la sua rilevanza è diminuita in favore di altri protocolli più sicuri.</span><span class="sxs-lookup"><span data-stu-id="9b737-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="9b737-108">Per rimuovere il problema della vulnerabilità, HoloLens 2 ha eliminato il codice correlato a NetBIOS dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9b737-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="9b737-109">I protocolli TLS (Transport Layer Security) si evolvono di continuo.</span><span class="sxs-lookup"><span data-stu-id="9b737-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="9b737-110">Per stare al passo con i vari exploit di sicurezza che sono stati scoperti in quest'area, il settore informatico è passato a versioni più recenti ed efficaci.</span><span class="sxs-lookup"><span data-stu-id="9b737-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="9b737-111">A causa del tempo necessario perché tutti gli ambienti server adottino le nuove versioni del protocollo TLS, è possibile implementare un meccanismo di fallback che consenta al client e ai server nelle diverse versioni del protocollo predefinite di comunicare ancora durante il periodo di transizione.</span><span class="sxs-lookup"><span data-stu-id="9b737-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <span data-ttu-id="9b737-112">Connettività sicura</span><span class="sxs-lookup"><span data-stu-id="9b737-112">Secure connectivity</span></span> 

<span data-ttu-id="9b737-113">Windows Defender Firewall offre funzionalità importanti per garantire la connettività dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9b737-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="9b737-114">Con HoloLens 2, il firewall è sempre abilitato e non sono disponibili modi per disabilitarlo a livello di programmazione o tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="9b737-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="9b737-115">L'accesso remoto e la privacy della connessione ai client per dispositivi mobili possono essere assicurate tramite la [piattaforma di plug-in VPN UWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="9b737-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="9b737-116">I provider VPN di terze parti possono creare i loro plug-in usando le API WinRT, che verranno eseguite nel sandbox di AppContainer, eliminando la complessità e le problematiche spesso associate alla scrittura dei driver a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="9b737-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
