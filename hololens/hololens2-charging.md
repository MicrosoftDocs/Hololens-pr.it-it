---
title: HoloLens 2 Batteria e ricarica
description: Come caricare le HoloLens e usare le batterie esterne.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428586"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 Batteria e ricarica

Questa pagina offre informazioni dettagliate sull'addebito HoloLens 2 e sull'uso di pacchetti di batteria esterni.

## <a name="charging-the-device"></a>Addebito del dispositivo

Usare il caricatore e il cavo [USB Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) fornito con il HoloLens 2, perché è il modo migliore per caricare il dispositivo. Il charger incluso in HoloLens 2 offre fino a 9 V @ 2A (18W). Insieme al caricatore a pareti fornito, i HoloLens 2 possono caricare la batteria in meno di 65 minuti quando il dispositivo è in standby. Se questi accessori non sono disponibili, assicurarsi che il caricatore disponibile sia in grado di supportare almeno 15W di alimentazione.

> [!NOTE]
> Se possibile, evitare di usare un PC per caricare il dispositivo tramite USB, che è lento.

## <a name="checking-the-battery-charge-level"></a>Controllo del livello di carica della batteria
Se il dispositivo viene avviato correttamente e in esecuzione, esistono tre modi per controllare il livello di carica della batteria:

- Dal menu principale dell'interfaccia utente HoloLens dispositivo.
- Visualizzare il LED vicino al pulsante di alimentazione (per una carica del 40%, dovrebbero essere visualizzati almeno due LED solidi).
    - Quando il dispositivo è in carica, l'indicatore della batteria si accende per indicare il livello di carica corrente.  L'ultima luce si dissolve in entrata e in uscita per indicare l'addebito attivo.
    - Quando la HoloLens è on, l'indicatore della batteria visualizza il livello della batteria in cinque incrementi.
    - Quando è accese solo una delle cinque luci, il livello della batteria è inferiore al 20%.
    - Se il livello della batteria è molto basso e si tenta di accendere il dispositivo, una luce lampeggia brevemente, quindi si esce.
- Nel PC host aprire **Esplora file** e cercare il dispositivo HoloLens 2 sul lato sinistro in Questo **PC.** Fare clic con il pulsante destro del mouse sul dispositivo e **scegliere Proprietà.** Verrà visualizzata una finestra di dialogo con il livello di carica della batteria.

   ![Una HoloLens 2 delle proprietà mostra il livello di modifica della batteria.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Specifiche di addebito alternative

HoloLens 2 possono essere addebitati da origini [usb per](https://www.usb.org/usb-charger-pd) il recapito di energia fino a 27 Punti. Se l'origine è in grado di fornire almeno 10 IoT, HoloLens tempo operativo può essere esteso (potenzialmente all'infinito per alcuni carichi di lavoro). 

> [!NOTE]
> L'uso di un cavo di ricarica da USB-A a USB-C limiterà la carica a 7,5 Gb. Il tempo operativo continuerà a essere esteso, ma non fino a quando si usa USB-C per C.

Quando HoloLens è in modalità standby, 18 Standby sono sufficienti per raggiungere la velocità massima di ricarica per la batteria interna. Quando HoloLens è in uso, la tariffa di addebito può essere ridotta perché HoloLens priorità di funzionamento rispetto all'addebito.

> [!IMPORTANT]
> È consigliabile che HoloLens 2 un addebito minimo di 5 V/1,5A. I caricatori che non possono fornire almeno 5 V/1,5A non devono essere usati. 

### <a name="external-battery-packs"></a>Alimentatore esterno

I pacchetti di batteria che soddisfano le specifiche precedenti possono essere usati con HoloLens 2. Si noti tuttavia che alcuni alimentatore USB-C si caricano e forniscono alimentazione attraverso la stessa porta USB-C. È importante che questi pacchetti di batteria implementino [TRY. SRC per](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) assicurarsi che addebitino HoloLens invece di addebitarlo. 

### <a name="managing-heat"></a>Gestione del calore

Come per qualsiasi dispositivo, la ricarica HoloLens genera calore. Più rapida è la carica, più calore viene generato. Inoltre, l'avvio di una carica a un livello di batteria inferiore genererà più calore rispetto all'avvio di una carica quando la batteria è per lo più piena. I clienti che devono operare HoloLens per lunghi periodi di tempo in ambienti ad accesso più caldo possono usare le tecniche seguenti:

- È possibile connettersi a HoloLens 2 alimentatore esterno anche quando la batteria interna è completamente carica.
- Quando una batteria esterna è esaurita, HoloLens continua a operare sulla batteria interna.    
- Se il calore è ancora un problema dopo aver seguito i passaggi precedenti, è consigliabile usare un caricatore o un pacchetto batteria che limita la ricarica a 1,5A. Si noti che questa opzione non fornirà il tempo di funzionamento perché la batteria interna si esaurimenterà lentamente.

## <a name="troubleshooting"></a>Risoluzione dei problemi


### <a name="hololens-charges-external-battery"></a>HoloLens Addebita la batteria esterna
Se HoloLens 2 carica una batteria esterna anziché caricarla, significa che la batteria non implementa [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Il passaggio a un pacchetto batteria più recente è il modo consigliato per risolvere questo problema, ma in alternativa è possibile provare a passare a un cavo USB-A-C. Tenere presente che questo limiterà la tariffa di ricarica a 7,5 gb.
