---
title: Batteria e ricarica
description: Come caricare HoloLens e usare i pacchetti di batteria esterni.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398973"
---
# <a name="battery-and-charging"></a><span data-ttu-id="fa528-103">Batteria e ricarica</span><span class="sxs-lookup"><span data-stu-id="fa528-103">Battery and Charging</span></span>

<span data-ttu-id="fa528-104">Questa pagina offre informazioni dettagliate sulla ricarica HoloLens 2 e sull'uso di pacchetti di batteria esterni.</span><span class="sxs-lookup"><span data-stu-id="fa528-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="included-charger"></a><span data-ttu-id="fa528-105">Caricatore incluso</span><span class="sxs-lookup"><span data-stu-id="fa528-105">Included Charger</span></span>

<span data-ttu-id="fa528-106">Il caricatore incluso in HoloLens 2 fornisce fino a 9 V @ 2A (18W).</span><span class="sxs-lookup"><span data-stu-id="fa528-106">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="fa528-107">Quando possibile, è consigliabile addebitare usando il caricabatterie incluso.</span><span class="sxs-lookup"><span data-stu-id="fa528-107">When possible, it's highly recommended to charge using the included charger.</span></span>  

## <a name="specifications"></a><span data-ttu-id="fa528-108">Specifiche</span><span class="sxs-lookup"><span data-stu-id="fa528-108">Specifications</span></span>

<span data-ttu-id="fa528-109">HoloLens 2 possono essere addebitati dalle origini [di alimentazione USB](https://www.usb.org/usb-charger-pd) fino a 27 Watt.</span><span class="sxs-lookup"><span data-stu-id="fa528-109">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="fa528-110">Se l'origine è in grado di fornire almeno 10 Watt, il tempo operativo di HoloLens può essere esteso (potenzialmente all'infinito per alcuni carichi di lavoro).</span><span class="sxs-lookup"><span data-stu-id="fa528-110">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="fa528-111">L'uso di un cavo di ricarica da USB-A a USB-C limiterà l'addebito a 7,5 Watt.</span><span class="sxs-lookup"><span data-stu-id="fa528-111">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="fa528-112">Il tempo operativo verrà comunque esteso, ma non fino a quando si usa USB-C per C.</span><span class="sxs-lookup"><span data-stu-id="fa528-112">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="fa528-113">Quando HoloLens è in modalità standby, 18 Watt sono sufficienti per raggiungere la velocità di ricarica massima per la batteria interna.</span><span class="sxs-lookup"><span data-stu-id="fa528-113">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="fa528-114">Quando HoloLens è in uso, la tariffa di addebito può essere ridotta perché HoloLens assegna priorità al funzionamento rispetto alla ricarica.</span><span class="sxs-lookup"><span data-stu-id="fa528-114">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa528-115">È consigliabile che HoloLens 2 addebito minimo di 5 V/1,5A.</span><span class="sxs-lookup"><span data-stu-id="fa528-115">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="fa528-116">I caricabatterie che non possono fornire almeno 5 V/1,5A non devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="fa528-116">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

## <a name="external-battery-packs"></a><span data-ttu-id="fa528-117">Pacchetti di batteria esterni</span><span class="sxs-lookup"><span data-stu-id="fa528-117">External Battery Packs</span></span>

<span data-ttu-id="fa528-118">I pacchetti di batteria che soddisfano le specifiche precedenti possono essere usati con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="fa528-118">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="fa528-119">Si noti tuttavia che alcune batterie USB-C si ricaricano e forniscono alimentazione tramite la stessa porta USB-C.</span><span class="sxs-lookup"><span data-stu-id="fa528-119">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="fa528-120">È importante che questi pacchetti di batteria implementino [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) per assicurarsi che addebitino HoloLens anziché addebitarne l'addebito.</span><span class="sxs-lookup"><span data-stu-id="fa528-120">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

## <a name="managing-heat"></a><span data-ttu-id="fa528-121">Gestione del calore</span><span class="sxs-lookup"><span data-stu-id="fa528-121">Managing Heat</span></span>

<span data-ttu-id="fa528-122">Come per qualsiasi dispositivo, l'addebito di HoloLens genera calore.</span><span class="sxs-lookup"><span data-stu-id="fa528-122">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="fa528-123">Più rapida è la carica, più calore viene generato.</span><span class="sxs-lookup"><span data-stu-id="fa528-123">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="fa528-124">Inoltre, l'avvio di una carica a un livello di batteria inferiore genererà più calore rispetto all'avvio di una carica quando la batteria è per lo più piena.</span><span class="sxs-lookup"><span data-stu-id="fa528-124">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="fa528-125">I clienti che devono usare HoloLens per lunghi periodi di tempo in ambienti ad accesso più caldo possono usare le tecniche seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa528-125">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="fa528-126">È possibile connettersi a HoloLens 2 a una fonte di alimentazione esterna anche quando la batteria interna è completamente carica.</span><span class="sxs-lookup"><span data-stu-id="fa528-126">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="fa528-127">Quando una batteria esterna è esaurita, HoloLens continuerà a operare sulla batteria interna.</span><span class="sxs-lookup"><span data-stu-id="fa528-127">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="fa528-128">Se il calore è ancora un problema dopo aver seguito i passaggi precedenti, è consigliabile usare un caricatore o un pacchetto batteria che limita la ricarica a 1,5A.</span><span class="sxs-lookup"><span data-stu-id="fa528-128">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="fa528-129">Si noti che questa opzione non fornirà il tempo di funzionamento perché la batteria interna continuerà a esaurimento lento.</span><span class="sxs-lookup"><span data-stu-id="fa528-129">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="fa528-130">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="fa528-130">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="fa528-131">HoloLens addebita la batteria esterna</span><span class="sxs-lookup"><span data-stu-id="fa528-131">HoloLens Charges External Battery</span></span>
<span data-ttu-id="fa528-132">Se HoloLens 2 carica una batteria esterna anziché caricarla, significa che la batteria non implementa [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="fa528-132">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="fa528-133">Il passaggio a un pacchetto batteria più recente è il modo consigliato per risolvere questo problema, ma in alternativa è possibile provare a passare a un cavo USB-A-C.</span><span class="sxs-lookup"><span data-stu-id="fa528-133">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="fa528-134">Tenere presente che questo limiterà la tariffa di ricarica a 7,5 gb.</span><span class="sxs-lookup"><span data-stu-id="fa528-134">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
