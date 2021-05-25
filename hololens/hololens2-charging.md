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
# <a name="battery-and-charging"></a>Batteria e ricarica

Questa pagina offre informazioni dettagliate sulla ricarica HoloLens 2 e sull'uso di pacchetti di batteria esterni.

## <a name="included-charger"></a>Caricatore incluso

Il caricatore incluso in HoloLens 2 fornisce fino a 9 V @ 2A (18W). Quando possibile, è consigliabile addebitare usando il caricabatterie incluso.  

## <a name="specifications"></a>Specifiche

HoloLens 2 possono essere addebitati dalle origini [di alimentazione USB](https://www.usb.org/usb-charger-pd) fino a 27 Watt. Se l'origine è in grado di fornire almeno 10 Watt, il tempo operativo di HoloLens può essere esteso (potenzialmente all'infinito per alcuni carichi di lavoro). 

> [!NOTE]
> L'uso di un cavo di ricarica da USB-A a USB-C limiterà l'addebito a 7,5 Watt. Il tempo operativo verrà comunque esteso, ma non fino a quando si usa USB-C per C.

Quando HoloLens è in modalità standby, 18 Watt sono sufficienti per raggiungere la velocità di ricarica massima per la batteria interna. Quando HoloLens è in uso, la tariffa di addebito può essere ridotta perché HoloLens assegna priorità al funzionamento rispetto alla ricarica.

> [!IMPORTANT]
> È consigliabile che HoloLens 2 addebito minimo di 5 V/1,5A. I caricabatterie che non possono fornire almeno 5 V/1,5A non devono essere usati. 

## <a name="external-battery-packs"></a>Pacchetti di batteria esterni

I pacchetti di batteria che soddisfano le specifiche precedenti possono essere usati con HoloLens 2. Si noti tuttavia che alcune batterie USB-C si ricaricano e forniscono alimentazione tramite la stessa porta USB-C. È importante che questi pacchetti di batteria implementino [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) per assicurarsi che addebitino HoloLens anziché addebitarne l'addebito. 

## <a name="managing-heat"></a>Gestione del calore

Come per qualsiasi dispositivo, l'addebito di HoloLens genera calore. Più rapida è la carica, più calore viene generato. Inoltre, l'avvio di una carica a un livello di batteria inferiore genererà più calore rispetto all'avvio di una carica quando la batteria è per lo più piena. I clienti che devono usare HoloLens per lunghi periodi di tempo in ambienti ad accesso più caldo possono usare le tecniche seguenti:

- È possibile connettersi a HoloLens 2 a una fonte di alimentazione esterna anche quando la batteria interna è completamente carica.
- Quando una batteria esterna è esaurita, HoloLens continuerà a operare sulla batteria interna.    
- Se il calore è ancora un problema dopo aver seguito i passaggi precedenti, è consigliabile usare un caricatore o un pacchetto batteria che limita la ricarica a 1,5A. Si noti che questa opzione non fornirà il tempo di funzionamento perché la batteria interna continuerà a esaurimento lento.

## <a name="troubleshooting"></a>Risoluzione dei problemi


### <a name="hololens-charges-external-battery"></a>HoloLens addebita la batteria esterna
Se HoloLens 2 carica una batteria esterna anziché caricarla, significa che la batteria non implementa [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Il passaggio a un pacchetto batteria più recente è il modo consigliato per risolvere questo problema, ma in alternativa è possibile provare a passare a un cavo USB-A-C. Tenere presente che questo limiterà la tariffa di ricarica a 7,5 gb.
