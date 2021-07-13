---
title: Sicurezza di rete
description: sicurezza di rete
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, rete, sicurezza di rete
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640492"
---
# <a name="network-security"></a><span data-ttu-id="362ca-104">Sicurezza di rete</span><span class="sxs-lookup"><span data-stu-id="362ca-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="362ca-105">Protocolli di rete</span><span class="sxs-lookup"><span data-stu-id="362ca-105">Network protocols</span></span>

<span data-ttu-id="362ca-106">Il netBIOS obsoleto (Network Basic Input/Output System) è stato ampiamente usato in passato negli scenari LAN, spesso per fornire la risoluzione dei nomi a un computer e a cartelle condivise.</span><span class="sxs-lookup"><span data-stu-id="362ca-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="362ca-107">Ma nel corso del tempo, NetBIOS si è dimostrato vulnerabile a più attacchi e la sua pertinenza è diminuita a favore di altri protocolli più sicuri.</span><span class="sxs-lookup"><span data-stu-id="362ca-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="362ca-108">Per rimuovere questo problema di vulnerabilità, HoloLens 2 il codice correlato a NetBIOS dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="362ca-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="362ca-109">I protocolli TLS (Transport Layer Security) sono in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="362ca-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="362ca-110">Per tenere il passo con i vari exploit di sicurezza scoperti in questa area, il settore informatico è diventato versioni più recenti ed efficaci.</span><span class="sxs-lookup"><span data-stu-id="362ca-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="362ca-111">A causa del tempo necessario per tutte le distribuzioni del server per adottare le nuove versioni del protocollo TLS, è possibile implementata un meccanismo di fallback che consente al client e ai server in versioni del protocollo predefinite diverse di essere ancora in grado di comunicare durante il periodo di transizione.</span><span class="sxs-lookup"><span data-stu-id="362ca-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="362ca-112">Proteggere la connettività</span><span class="sxs-lookup"><span data-stu-id="362ca-112">Secure connectivity</span></span> 

<span data-ttu-id="362ca-113">Il Windows Defender firewall offre funzionalità critiche per proteggere la connettività dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="362ca-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="362ca-114">Con HoloLens 2, il firewall è sempre abilitato e non è possibile disabilitarlo a livello di codice o tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="362ca-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="362ca-115">L'accesso remoto e la privacy della connessione per i client mobili possono essere garantiti tramite la piattaforma [plug-in VPN UWP](/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="362ca-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="362ca-116">I provider VPN di terze parti possono creare plug-in personalizzati usando API WinRT che verranno eseguite all'interno della sandbox AppContainer, eliminando la complessità e i problemi spesso associati alla scrittura di driver a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="362ca-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
