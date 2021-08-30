---
title: HoloLens 2 Batteria e ricarica
description: Come caricare il HoloLens e usare i pacchetti di batteria esterni.
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
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189801"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 Batteria e ricarica

Questa pagina offre informazioni dettagliate sulla ricarica HoloLens 2 e sull'uso di pacchetti di batteria esterni.

## <a name="charging-the-device"></a>Addebito del dispositivo

Usare il [caricabatterie](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) e il cavo USB Type-C fornito con il HoloLens 2 perché è il modo migliore per caricare il dispositivo. Il caricatore incluso in HoloLens 2 fornisce fino a 9 V @ 2A (18W). Insieme al caricatore a parete fornito, i dispositivi HoloLens 2 ricaricare la batteria in meno di 65 minuti quando il dispositivo è in standby. Se questi accessori non sono disponibili, assicurarsi che il caricabatterie disponibile supporti almeno 15W di alimentazione.

> [!NOTE]
> Se possibile, evitare di usare un PC per caricare il dispositivo tramite USB, che è lento.

## <a name="checking-the-battery-charge-level"></a>Controllo del livello di carica della batteria
Se il dispositivo viene avviato correttamente e in esecuzione, è possibile controllare il livello di carica della batteria in tre modi:

- Dal menu principale dell'interfaccia utente HoloLens dispositivo.
- Visualizzare il LED vicino al pulsante di accensione (per un addebito del 40%, dovrebbero essere visualizzati almeno due LED solidi).
    - Quando il dispositivo è in carica, l'indicatore della batteria si accende per indicare il livello di carica corrente.  L'ultima luce si dissolverà in entrata e in uscita per indicare la ricarica attiva.
    - Quando il HoloLens è on, l'indicatore della batteria visualizza il livello della batteria in cinque incrementi.
    - Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%.
    - Se il livello della batteria è criticamente basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente e quindi si spegne.
- Nel PC host aprire **Esplora file** e cercare il dispositivo HoloLens 2 sul lato sinistro in Questo **PC**. Fare clic con il pulsante destro del mouse sul dispositivo e **scegliere Proprietà**. Verrà visualizzata una finestra di dialogo con il livello di carica della batteria.

   ![Una HoloLens 2 delle proprietà mostra il livello di modifica della batteria.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Specifiche alternative di addebito

HoloLens 2 possono essere addebitati dalle origini [di alimentazione USB](https://www.usb.org/usb-charger-pd) fino a 27 Watt. Se l'origine è in grado di fornire almeno 10 Watt, HoloLens tempo operativo può essere esteso (potenzialmente all'infinito per alcuni carichi di lavoro). 

> [!NOTE]
> L'uso di un cavo di ricarica da USB-A a USB-C limiterà la carica a 7,5 Watt. Il tempo operativo verrà comunque esteso, ma non fino a quando si usa USB-C per C.

Quando HoloLens in modalità standby, 18 Watt sono sufficienti per raggiungere la velocità di ricarica massima per la batteria interna. Quando HoloLens è in uso, la tariffa di addebito può essere ridotta HoloLens priorità operative rispetto all'addebito.

> [!IMPORTANT]
> È consigliabile HoloLens 2 addebito minimo di 5 V/1,5A. I caricabatterie che non possono fornire almeno 5 V/1,5A non devono essere usati. 

### <a name="external-battery-packs"></a>Pacchetti di batteria esterni

I pacchetti di batteria che soddisfano le specifiche precedenti possono essere usati con HoloLens 2. Si noti tuttavia che alcune batterie USB-C si ricaricano e forniscono alimentazione tramite la stessa porta USB-C. È importante che questi pacchetti di batteria implementino [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) per assicurarsi che addebitino HoloLens invece di addebitarne l'addebito. 

### <a name="managing-heat"></a>Gestione del calore

Come per qualsiasi dispositivo, la ricarica HoloLens genera calore. Più rapida è la carica, maggiore sarà il calore generato. Inoltre, l'avvio di un addebito a un livello inferiore della batteria genererà più calore rispetto all'avvio di una ricarica quando la batteria è per lo più piena. I clienti che devono operare HoloLens per lunghi periodi di tempo negli ambienti ad accesso caldo possono usare le tecniche seguenti:

- È possibile connettersi a HoloLens 2 a una fonte di alimentazione esterna anche quando la batteria interna è completamente carica.
- Quando una batteria esterna è esaurita, HoloLens continuerà a operare sulla batteria interna.    
- Se il calore è ancora un problema dopo i passaggi precedenti, provare a usare un caricabatterie o un pacchetto batteria che limita la ricarica a 1,5A. Si noti che questa opzione non fornirà la quantità di tempo di funzionamento perché la batteria interna continuerà a deplersi lentamente.

## <a name="troubleshooting"></a>Risoluzione dei problemi


### <a name="hololens-charges-external-battery"></a>HoloLens Addebita la batteria esterna
Se HoloLens 2 carica una batteria esterna anziché caricarla, significa che la batteria non implementa [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Il passaggio a un pacchetto di batteria più recente è il modo consigliato per risolvere questo problema, ma in alternativa è possibile provare a passare a un cavo USB-A a USB-C. Tenere presente che questo limiterà la tariffa di ricarica a 7,5 watt.
