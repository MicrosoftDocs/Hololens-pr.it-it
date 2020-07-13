---
title: Wireless e Wi-Fi
description: Wireless e Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, wireless, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865775"
---
# <span data-ttu-id="ac67f-104">Wireless e Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ac67f-104">Wireless and Wi-Fi</span></span>

<span data-ttu-id="ac67f-105">La connettività LAN wireless di HoloLens 2 supporta una gamma incredibile degli standard di sicurezza più recenti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ac67f-105">HoloLens 2 Wireless LAN connectivity supports an impressive range of the latest Wi-Fi security standards, such as:</span></span>
  * <span data-ttu-id="ac67f-106">WPA2 (Wi-Fi Protected Access 2)</span><span class="sxs-lookup"><span data-stu-id="ac67f-106">WPA2 (Wi-Fi Protected Access 2)</span></span>  
  * <span data-ttu-id="ac67f-107">TEAP (Tunnel Extensible Authentication Protocol)</span><span class="sxs-lookup"><span data-stu-id="ac67f-107">TEAP (Tunnel Extensible Authentication Protocol)</span></span>  
  * <span data-ttu-id="ac67f-108">OWE (Opportunistic Wireless Encryption)</span><span class="sxs-lookup"><span data-stu-id="ac67f-108">OWE (Opportunistic Wireless Encryption)</span></span>

<span data-ttu-id="ac67f-109">TEAP, l'autenticazione alle reti aziendali di nuova generazione, consente di collegare in modo sicuro più credenziali in una singola operazione.</span><span class="sxs-lookup"><span data-stu-id="ac67f-109">TEAP, the next generation of enterprise network authentication, provides the ability to securely chain multiple credentials into a single transaction.</span></span>  <span data-ttu-id="ac67f-110">Ciò consente agli amministratori di applicare un approccio alla sicurezza più efficace, che richieda identità valide sia per la macchina che per l'utente durante la stessa transazione di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ac67f-110">This allows administrators to enforce a stronger security stance – one that requires valid identities for both machine and user during the same authentication transaction.</span></span>

<span data-ttu-id="ac67f-111">HoloLens 2 offre protocolli wireless moderni e Wi-Fi che consentono ai clienti di ottenere il massimo supporto.</span><span class="sxs-lookup"><span data-stu-id="ac67f-111">HoloLens 2 has modern wireless and Wi-Fi protocols that enable customers with maximum support.</span></span> <span data-ttu-id="ac67f-112">La radio HoloLens 2 è una soluzione Qualcomm WCN3990 in grado di offrire un'esperienza radio premium.</span><span class="sxs-lookup"><span data-stu-id="ac67f-112">The HoloLens 2 radio is a Qualcomm WCN3990 solution delivering a premium radio experience.</span></span> <span data-ttu-id="ac67f-113">La rete Wi-Fi supportata è 802.11 ac/n.</span><span class="sxs-lookup"><span data-stu-id="ac67f-113">The Wi-Fi supported is 802.11 ac/n.</span></span> <span data-ttu-id="ac67f-114">L'intervallo di frequenze non è configurabile dall'utente e varia in base al Paese di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="ac67f-114">The frequency range is not user configurable and depends on the country of use.</span></span> <span data-ttu-id="ac67f-115">Negli Stati Uniti, la rete Wi-Fi usa sia canali da 2,4 GHz (1-11) che 5 canali da 5 GHz (36-64, 100-165).</span><span class="sxs-lookup"><span data-stu-id="ac67f-115">In the United States, Wi-Fi uses both 2.4GHz (1-11) channels and 5GHz (36-64, 100-165) channels.</span></span> <span data-ttu-id="ac67f-116">Gli utenti e i dispositivi non possono creare elenchi consentiti/rifiutati per frequenze specifiche.</span><span class="sxs-lookup"><span data-stu-id="ac67f-116">Neither user nor device can make allow/deny lists for specific frequencies.</span></span> <span data-ttu-id="ac67f-117">Il Bluetooth SIC Core 5.0 dispone di un'antenna da 2,4 GHz dedicata per il Bluetooth che non viene condivisa con il Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ac67f-117">Bluetooth SIC Core 5.0 has a dedicated 2.4GHz antenna for Bluetooth which is not shared with Wi-Fi.</span></span> <span data-ttu-id="ac67f-118">Lo stack del software di HoloLens 2 supporta più protocolli e profili, tra cui HID, HOGP, A2DP e GATT.</span><span class="sxs-lookup"><span data-stu-id="ac67f-118">HoloLens 2’s software stack supports several protocols and profiles including HID, HOGP, A2DP, and GATT.</span></span> 

<span data-ttu-id="ac67f-119">Gli amministratori IT possono:</span><span class="sxs-lookup"><span data-stu-id="ac67f-119">IT admins can:</span></span> 
  * <span data-ttu-id="ac67f-120">Abilitare o limitare [l'accesso Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span><span class="sxs-lookup"><span data-stu-id="ac67f-120">Enable or restrict  [Bluetooth access](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span></span>
  * <span data-ttu-id="ac67f-121">Impostare i [nomi del dispositivo Bluetooth locale](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span><span class="sxs-lookup"><span data-stu-id="ac67f-121">Set [local Bluetooth device names](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span></span>
  * <span data-ttu-id="ac67f-122">Consentire ai [dispositivi di essere individuabili](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span><span class="sxs-lookup"><span data-stu-id="ac67f-122">Allow [devices to be discoverable](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span></span>
  * <span data-ttu-id="ac67f-123">Consentire o meno [le connessioni Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span><span class="sxs-lookup"><span data-stu-id="ac67f-123">Allow/disallow [Wi-Fi connections](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span></span> 
  * <span data-ttu-id="ac67f-124">Consentire o meno [la connessione a un Wi-Fi esterno alle reti del server MDM installato](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span><span class="sxs-lookup"><span data-stu-id="ac67f-124">Allow or disallow [connecting to Wi-Fi outside of MDM server-installed networks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span></span>
