---
title: Hardware HoloLens 2
description: Informazioni sui componenti che costituiscono il Microsoft HoloLens 2, l'evoluzione più recente di un computer Microsoft olografico senza tethering che esegue Windows 10.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 10/20/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: c1d83577400126903a80999c46ddaeabddaba029
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190379"
---
# <a name="about-hololens-2"></a>Informazioni HoloLens 2

![HoloLens 2 visualizzazione laterale.](images/hololens2-breakdown.png)

Microsoft HoloLens 2 è un computer olografico senzathering.  Perfeziona il percorso di elaborazione olografica avviato da HoloLens (prima generazione) per offrire un'esperienza più comoda e immersiva abbinata a più opzioni per la collaborazione nella realtà mista. HoloLens 2 viene eseguito nel sistema operativo [Windows Holographic,](hololens-release-notes.md)che si basa su una "versione" di Windows 10, che offre a utenti, amministratori e sviluppatori una piattaforma affidabile, a prestazioni e sicure. 

> [!NOTE]
> L'annuncio Windows 11 è stato incentrato sulla versione PC di Windows. Di recente è stato avviato un aggiornamento principale del sistema operativo per HoloLens 2 maggio 2021 e stiamo lavorando [a](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) una versione futura in base ai commenti e suggerimenti dei clienti per questo fallire.

È necessario un account utente per usare HoloLens 2.

## <a name="hololens-components"></a>HoloLens componenti

- **Visore**. Contiene i HoloLens e le informazioni visualizzate. È possibile ruotare il visore verso l'alto mentre si ruota il HoloLens.
- **Headband**. Per posizionare il HoloLens, usare la rotellina di regolazione per espandere la fascia. Dopo aver HoloLens, stringere la ruota di regolazione ruotando verso destra, fino a quando la fascia non è comoda.
- **Pulsanti luminosità**. Quando si indossa il HoloLens, i pulsanti di luminosità si trova sul lato sinistro del visore vicino al tempio.
- **Pulsanti volume**. Quando si indossano HoloLens, i pulsanti del volume si trova sul lato destro del visore vicino al tempio.
- **Pulsante di alimentazione**. Quando si copre HoloLens, il pulsante di alimentazione si trova sul lato destro della copertura esterna posteriore.
- **Porta USB-C**. Quando si copre HoloLens, la porta USB-C si trova sul lato destro della copertura esterna posteriore sotto il pulsante di alimentazione.

## <a name="in-the-box"></a>Nella casella

- **[Brow pad](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)**. È possibile rimuovere e sostituire il riempimento della fronte in base alle esigenze.
- **[Sovraccarico .](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)** Quando si è in grado di HoloLens durante lo spostamento, usare il sovraccarico per mantenere il dispositivo sul posto. Quando si usurano le HoloLens per periodi prolungati, il sovraccarico può rendere il dispositivo più a proprio agio da usurare.
- **[Caricatore USB-C e cavo](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)**. L'alimentatore si collega alla presa di alimentazione. Usare il cavo USB-C per collegare l'HoloLens all'alimentatore per la ricarica o per collegare il HoloLens al computer.
- **Microfibero evaso.** Usare per pulire la HoloLens visore.

### <a name="power-supply-details"></a>Dettagli dell'alimentatore

L'alimentatore e il cavo USB forniti con il dispositivo sono il meccanismo migliore supportato per la ricarica. L'alimentatore è un caricatore da 18W.  Fornisce 9 V a 2A.

La velocità e la velocità di ricarica possono variare a seconda dell'ambiente in cui è in esecuzione il dispositivo.

Per mantenere/far avanzare la percentuale di carica della batteria interna mentre il dispositivo è in funzione, è necessario collegarlo almeno a un caricatore da 15W.

## <a name="device-specifications"></a>Specifiche del dispositivo

### <a name="display"></a>Visualizza

|   | &nbsp; |
|---|---|
| **Ottica** | Lenti olografiche see-through (waveguide) |
| **Risoluzione olografica** | Motori leggeri 2k 3:2 |
| **Densità olografica** | >radianti da 2,5 k (punti luce per radianti) |
| **Rendering basato sugli occhi** | Ottimizzazione dello schermo per la posizione degli occhi 3D |

### <a name="sensors"></a>Sensori

|   | &nbsp; |
|---|---|
| **Tracciamento della testa** | 4 fotocamere di luce visibili |
| **Tracciamento oculare** | 2 fotocamere a ir- |
| **Livello nidificazione** | Sensore di profondità time-of-flight da 1 MP |
| **Unità di misura inerziale (IMU)** | Accelerometro, giroscopio, magnetometro |
| **Fotocamera** | 8-MP stills, video 1080p30 |

![HoloLens 2 Sensori.](images/hololens2-front-view.png)

> [!NOTE]
> Non coprire i sensori che vengono chiamati nell'immagine. Le fotocamere di rilevamento della testa hanno una fov molto ampia, non dovrebbero essere presenti elementi intorno a esse oltre a non coprire le fotocamere.

### <a name="audio-and-speech"></a>Audio e voce

|   | &nbsp; |
|---|---|
| **Array di microfoni** | 5 canali |
| **Altoparlanti** | Audio spaziale incorporato |

### <a name="compute-and-connectivity"></a>Calcolo e connettività

|   | &nbsp; |
|---|---|
| **Sistema su chip** | Dettagli della piattaforma di calcolo Qualcomm Snapdragon 850 [](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform) |
| **Unità di elaborazione olografica** | Unità di elaborazione olografica personalizzata di seconda generazione |
| **Memoria** | DRAM di sistema LPDDR4x da 4 GB |
| **Archiviazione** | UFS 2.1 da 64 GB |
| **Wi-Fi** | 802.11ac 2x2 |
| **Bluetooth** | 5.0 |
| **USB** | USB Type-C DRP |

### <a name="power"></a>Elettricità

|   | &nbsp; |
|---|---|
| **Durata della batteria** | 2-3 ore di utilizzo attivo. Fino a due settimane di tempo di standby. |
| **Tecnologia della batteria** | [Batterie al litio](https://www.microsoft.com/download/details.aspx?id=43388) |
| **Comportamento di addebito** | Completamente funzionante durante l'addebito |
| **Tipo di raffreddamento** | Raffreddamento passivo (senza ventole) |
| **Power draw** | Per mantenere/far avanzare la percentuale di carica della batteria interna mentre il dispositivo è in funzione, è necessario collegarlo almeno a un caricatore da 15W. |

### <a name="fit"></a>Ambito d'uso

|   | &nbsp; |
|---|---|
| **Ridimensionamento** | Dimensione singola con banda regolabile.  Si adatta agli occhiali |
| **Weight** | 566 grammi |

## <a name="device-capabilities"></a>Funzionalità di dispositivo

### <a name="human-understanding"></a>Riconoscimento del fattore umano

|   | &nbsp; |
|---|---|
| **Tracciamento mano** | Modello a due mani completamente articolato, manipolazione diretta |
| **Tracciamento oculare** | Rilevamento in tempo reale |
| **Chiamata vocale** | Comando e controllo sul dispositivo; Cortana linguaggio naturale con connettività Internet |

### <a name="environment-understanding"></a>Comprensione dell'ambiente

|   | &nbsp; |
|---|---|
| **Rilevamento di Sei gradi di libertà (6DoF)** | Rilevamento posizionale su scala globale |
| **Mapping spaziale** | Mesh dell'ambiente in tempo reale |
| **Acquisizione in realtà mista (MRC, Mixed Reality Capture)** | Foto e video di ambienti fisici e ologrammi misti |

## <a name="pre-installed-software"></a>Software preinstallato

| &nbsp; | &nbsp; |
|---|---|
| **Windows Sistema operativo olografico** | Con Windows sistema operativo [Holographic,](hololens-release-notes.md)gli utenti Windows 10 potranno usare alcune app e giochi in un ambiente di realtà mista tramite il HoloLens 2.
| **Visualizzatore 3D** | [Visualizzatore 3D](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab) consente di visualizzare facilmente modelli e animazioni 3D in tempo reale.|
| **Cortana** | [Cortana](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab), l'assistente per la produttività personale, consente di rimanere sempre al corrente di ciò che conta e di risparmiare tempo per trovare ciò che serve.  |
| **Guide di Dynamics 365** |  [Dynamics 365 Guides](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab) consente ai dipendenti di acquisire più rapidamente nuove competenze HoloLens dispositivi. |
| **Dynamics 365 Remote Assist** | [Microsoft Dynamics 365 Remote Assist](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab) consente ai tecnici di collaborare e risolvere i problemi con i collaboratori remoti usando Microsoft Teams o Dynamics 365 Remote Assist.  |
| **Hub di Feedback** | [Hub di Feedback](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab) consente di inviare commenti e suggerimenti Windows app condividendo i suggerimenti o i problemi.  |
| **Esplora file** | Esplora file fornisce un'interfaccia utente grafica per l'accesso ai file system. |
| **Posta e calendario** | Le [app Posta e](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab) Calendario consentono di rimanere aggiornati sulla posta elettronica, gestire la pianificazione e rimanere in contatto con i contatti. |
| **Microsoft Edge** | Microsoft Edge offre prestazioni di livello superiore con maggiore privacy, maggiore produttività e maggiore valore durante l'esplorazione. |
| **Microsoft Store** | Il [Microsoft Store](https://www.microsoft.com) è l'origine da usare per app e giochi che funzionano con HoloLens.|
| **Film & TV** | [Film & TV](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab) offre l'intrattenimento più recente in un'unica app semplice, veloce ed elegante. |
| **OneDrive** | [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab) consente di accedere e modificare i file da tutti i dispositivi ovunque ci si trovi.  |
| **Foto** | [Foto](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab) consente di visualizzare e modificare foto e video, creare film e creare album.  |
| **Impostazioni** | L Impostazioni app è la posizione in cui si personalizza il funzionamento Windows holographic.  |
| **Suggerimenti** | [Suggerimenti](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab) consente di eseguire operazioni inaspettate e meno note in Windows olografica. |

## <a name="device-certifications"></a>Certificazioni dei dispositivi

### <a name="safety"></a>Sicurezza

* [Sicurezza del prodotto](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [Avvisi e istruzioni sulla sicurezza del prodotto](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* Sicurezza oculare: HoloLens 2 è stato testato ed è conforme ai requisiti di protezione dall'impatto di base di ANSI Z87.1, CSA Z94.3 ed EN 166.
* [Informazioni SAR](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>Informazioni sulle normative
[HoloLens normative:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)include informazioni su temperatura, eliminazione, interferenze radio e TV e altro ancora.

## <a name="warranty-information"></a>Informazioni sulla garanzia

Microsoft HoloLens 2 viene fornito con una garanzia limitata [standard.](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5) 


L'acquisto è soggetto [Microsoft Store condizioni per l'utilizzo e la vendita.](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1) Tutte le vendite sono finali. Nessun rimborso.

Acquistando HoloLens 2 si accetta il contratto [di licenza software](https://www.microsoft.com/Useterms/).

Non destinato all'uso da parte di minori di 13 anni.

## <a name="package-dimensions"></a>Dimensioni del pacchetto

|      Misura               |      Metrica Unità     |      Unità di misura     |
|--------------------------------|-----------------------|-------------------------|
|     Lunghezza unità                |     378,97 mm          |     14,920 pollici       |
|     Larghezza unità                 |     247,90 mm          |     9,760 pollici        |
|     Profondità unità                 |     163,07 mm          |     6,420 pollici        |
|     Peso unità                |     2,878 kg           |     6,344 lbs           |
|     Lunghezza del shipper esterno    |     446,00 mm          |     17,559 pollici       |
|     Larghezza speditore esterno     |     257,99 mm          |     10,157 pollici       |
|     Profondità del shipper esterno     |     172,01 mm          |     6,772 pollici        |
|     Peso mittente esterno    |     3,284 kg           |     7,240 lbs           |

> [!NOTE]
> - Unità: la scatola nera di tipo retail HoloLens 2 viene venduta.
> - Mittente esterno: i pacchetti di spedizione di protezione intorno all'unità.

## <a name="finding-the-serial-number"></a>Ricerca del numero di serie

Il numero di serie HoloLens 2 dispositivi viene stampato sotto il visore.

1. Elevare il visore del dispositivo verso l'alto.
1. Osservare il riempimento della fronte.
1. È possibile trovare il numero di serie vicino alla cernicina.

   <img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

Il numero di serie è disponibile anche tramite un PC connesso:

1. Collegare il dispositivo
1. Passare a **Questo PC** in Esplora file
1. Fare clic con il pulsante destro **del mouse e** scegliere Proprietà HoloLens dispositivo
1. Verrà visualizzato il numero di serie del dispositivo, come illustrato nello screenshot seguente.

   <br/><img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Confrontare HoloLens 2 edizioni](hololens2-options.md)

> [!div class="nextstepaction"]
> [Configurare e avviare l'HoloLens 2](hololens2-setup.md)
