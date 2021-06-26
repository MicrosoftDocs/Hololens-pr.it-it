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
ms.openlocfilehash: 88687559310a9abc24f34c416880e02caf535177
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924520"
---
# <a name="about-hololens-2"></a>Informazioni HoloLens 2

![HoloLens 2 vista laterale](images/hololens2-breakdown.png)

Microsoft HoloLens 2 è un computer olografico senzathering.  Perfeziona il percorso di elaborazione olografica avviato da HoloLens (prima generazione) per offrire un'esperienza più comoda e immersiva associata a più opzioni per la collaborazione nella realtà mista. HoloLens 2 viene eseguito nel sistema operativo [Windows Holographic,](hololens-release-notes.md)che si basa su una "versione" di Windows 10, che offre a utenti, amministratori e sviluppatori una piattaforma affidabile, a prestazioni e sicure. 

> [!NOTE]
> Il recente annuncio di Windows 11 è stato incentrato sulla versione PC di Windows. Di recente è stato avviato un aggiornamento principale del sistema operativo per HoloLens 2 maggio 2021 e stiamo lavorando [a](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) una versione futura in base ai commenti e suggerimenti dei clienti per questo fallire.

È necessario un account utente per usare HoloLens 2.

## <a name="hololens-components"></a>Componenti di HoloLens

- **Visore**. Contiene i sensori e i display di HoloLens. Puoi ruotare il visore verso l'alto mentre hai indossato HoloLens.
- **Headband**. Per usare HoloLens, usa la rotellina di regolazione per espandere la fascia. Con HoloLens a posto, stringi la ruota di regolazione ruotando verso destra, fino a quando la fascia non è comoda.
- **Pulsanti luminosità**. Quando si indossa HoloLens, i pulsanti di luminosità si trova sul lato sinistro del visore vicino al tempio.
- **Pulsanti del volume**. Quando si indossa HoloLens, i pulsanti del volume si trova sul lato destro del visore vicino al tempio.
- **Pulsante di alimentazione**. Quando si copre HoloLens, il pulsante di alimentazione si trova sul lato destro della copertura esterna posteriore.
- **Porta USB-C**. Quando si copre HoloLens, la porta USB-C si trova sul lato destro della copertura esterna posteriore sotto il pulsante di alimentazione.

## <a name="in-the-box"></a>Nella casella

- **[Brow pad](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)**. È possibile rimuovere e sostituire il riempimento della fronte, in base alle esigenze.
- **[Sovraccarico .](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)** Quando si usa HoloLens mentre ci si sposta, usare il sovraccarico per mantenere il dispositivo sul posto. Quando si indossa HoloLens per periodi prolungati, il sovraccarico può rendere il dispositivo più a proprio agio.
- **[Caricatore USB-C e cavo](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)**. L'alimentatore si collega alla presa di alimentazione. Usa il cavo USB-C per connettere HoloLens all'alimentatore per la ricarica o per connettere HoloLens al computer.
- **Microfibero evaso.** Usare per pulire il visore HoloLens.

### <a name="power-supply-details"></a>Dettagli dell'alimentatore

L'alimentatore e il cavo USB forniti con il dispositivo sono il meccanismo migliore supportato per la ricarica. L'alimentatore è un caricatore da 18W.  Fornisce 9 V a 2A.

La velocità e la velocità di ricarica possono variare a seconda dell'ambiente in cui è in esecuzione il dispositivo.

Per mantenere/far avanzare la percentuale di carica della batteria interna mentre il dispositivo è in funzione, deve essere connesso almeno a un caricatore da 15W.

## <a name="device-specifications"></a>Specifiche del dispositivo

### <a name="display"></a>Visualizza

|   |   |
| - | - |
| Ottica | Lenti olografiche see-through (waveguide) |
| Risoluzione olografica | Motori leggeri 2k 3:2 |
| Densità olografica | >radianti da 2,5 k (punti luce per radianti) |
| Rendering basato sugli occhi | Ottimizzazione dello schermo per la posizione degli occhi 3D |

### <a name="sensors"></a>Sensori

|   |   |
| - | - |
| Tracciamento della testa | 4 fotocamere di luce visibili |
| Tracciamento oculare | 2 fotocamere a ir- |
| Profondità | Sensore di profondità time-of-flight da 1 MP |
| Unità di misura inerziale (IMU) | Accelerometro, giroscopio, magnetometro |
| Fotocamera | 8-MP stills, video 1080p30 |

![HoloLens 2 sensori](images/hololens2-front-view.png)

> [!NOTE]
> Non coprire i sensori che vengono chiamati nell'immagine. Le fotocamere di rilevamento della testa hanno una fov molto ampia, non dovrebbero essere presenti elementi intorno a esse oltre a non coprire le fotocamere.

### <a name="audio-and-speech"></a>Audio e voce

|   |   |
| - | - |
| Matrice di microfoni | 5 canali |
| Altoparlanti | Audio spaziale incorporato |

### <a name="compute-and-connectivity"></a>Calcolo e connettività

|   |   |
| - | - |
| Sistema su chip | Dettagli della piattaforma di calcolo Qualcomm Snapdragon 850 [](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform) |
| Unità di elaborazione olografica | Unità di elaborazione olografica personalizzata di seconda generazione |
| Memoria | DRAM di sistema LPDDR4x da 4 GB |
| Archiviazione | UFS 2.1 da 64 GB |
| WiFi | 802.11ac 2x2 |
| Bluetooth | 5.0 |
| USB | USB Type-C DRP |

### <a name="power"></a>Potenza

|   |   |
| - | - |
| Durata della batteria | 2-3 ore di utilizzo attivo. Fino a due settimane di tempo di standby. |
| Tecnologia della batteria | [Batterie al litio](https://www.microsoft.com/download/details.aspx?id=43388) |
| Comportamento di addebito | Completamente funzionante durante l'addebito |
| Tipo di raffreddamento | Raffreddamento passivo (senza ventole) |
| Power draw | Per mantenere/far avanzare la percentuale di carica della batteria interna mentre il dispositivo è in funzione, deve essere connesso almeno a un caricatore da 15W. |

### <a name="fit"></a>Ambito d'uso

|   |   |
| - | - |
| Ridimensionamento | Dimensioni singole con banda regolabile.  Si adatta agli occhiali da vista |
| Peso | 566 grammi |

## <a name="device-capabilities"></a>Funzionalità di dispositivo

### <a name="human-understanding"></a>Riconoscimento del fattore umano

|   |   |
| - | - |
| Tracciamento mano | Modello a due mani completamente articolato, manipolazione diretta |
| Tracciamento oculare | Rilevamento in tempo reale |
| Chiamata vocale | Comando e controllo sul dispositivo; Linguaggio naturale Cortana con connettività Internet |

### <a name="environment-understanding"></a>Informazioni sull'ambiente

|   |   |
| - | - |
| Rilevamento di sei gradi di libertà (6DoF) | Rilevamento posizionale su scala globale |
| Mapping spaziale | Mesh dell'ambiente in tempo reale |
| Acquisizione in realtà mista (MRC, Mixed Reality Capture) | Foto e video dell'ologramma misto e dell'ambiente fisico |

## <a name="pre-installed-software"></a>Software preinstallato

|   |   |
| - | - |
| Sistema operativo Windows Holographic | Con [il sistema operativo Windows Holographic,](hololens-release-notes.md)Windows 10 utenti potranno usare alcune app e giochi in un ambiente di realtà mista tramite il HoloLens 2.
| Visualizzatore 3D | [Visualizzatore 3D](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab) consente di visualizzare facilmente modelli e animazioni 3D in tempo reale.|
| Cortana | [Cortana,](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab)l'assistente per la produttività personale, consente di rimanere sempre al corrente di ciò che conta e di risparmiare tempo per trovare ciò che serve.  |
| Guide di Dynamics 365 |  [Dynamics 365 Guides consente](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab) ai dipendenti di apprendere più rapidamente nuove competenze nei dispositivi HoloLens. |
| Dynamics 365 Remote Assist | [Microsoft Dynamics 365 Remote Assist](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab) consente ai tecnici di collaborare e risolvere i problemi con i collaboratori remoti usando Microsoft Teams o Dynamics 365 Remote Assist.  |
| Hub di Feedback | [Hub di Feedback](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab) consente di inviare commenti e suggerimenti su Windows e sulle app condividendo i suggerimenti o i problemi.  |
| Esplora file | Esplora file fornisce un'interfaccia utente grafica per l'accesso ai file system. |
| Posta elettronica e calendario | Le [app Posta e](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab) Calendario consentono di rimanere aggiornati sulla posta elettronica, gestire la pianificazione e rimanere in contatto con i contatti. |  
| Microsoft Edge | Microsoft Edge prestazioni di livello mondiale con maggiore privacy, maggiore produttività e più valore durante l'esplorazione. |
| Microsoft Store | Il [Microsoft Store](https://www.microsoft.com) è l'origine di accesso per app e giochi che funzionano con HoloLens.|
| Film e TV | [Film & TV](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab) offre l'intrattenimento più recente in un'app semplice, veloce ed elegante. |
| OneDrive | [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab) consente di accedere e modificare i file da tutti i dispositivi ovunque ci si trovi.  |
| Foto| [Foto](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab) consente di visualizzare e modificare foto e video, creare film e creare album.  |
| Impostazioni | L'app Impostazioni è la posizione in cui è possibile personalizzare in dettaglio il funzionamento di Windows Holographic.  |
| Suggerimenti | [I](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab) suggerimenti consentono di eseguire operazioni sorprendente e meno note che è possibile eseguire in Windows Holographic. |

## <a name="device-certifications"></a>Certificazioni dei dispositivi

### <a name="safety"></a>Sicurezza

* [Sicurezza del prodotto](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [Avvisi e istruzioni sulla sicurezza dei prodotti](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* Sicurezza oculare: HoloLens 2 è stato testato e conforme ai requisiti di protezione dall'impatto di base di ANSI Z87.1, CSA Z94.3 ed EN 166.
* [Informazioni SAR](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>Informazioni sulle normative
[HoloLens Regulatory](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): include informazioni su temperatura, eliminazione, interferenze radio e TV e altro ancora.

## <a name="warranty-information"></a>Informazioni sulla garanzia

Microsoft HoloLens 2 viene fornito con una garanzia limitata [standard.](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5) 


L'acquisto è [soggetto Microsoft Store condizioni per l'utilizzo e la vendita.](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1) Tutte le vendite sono finali. Nessun rimborso.

Acquistando HoloLens 2 accetti il contratto [di licenza software.](https://www.microsoft.com/Useterms/)

Non destinato all'uso da parte di minori di 13 anni.

## <a name="package-dimensions"></a>Dimensioni pacchetto

|      Misura               |      Metrica Unità     |      Unità imperiali     |
|--------------------------------|-----------------------|-------------------------|
|     Lunghezza unità                |     378,97 mm          |     14,920 pollici       |
|     Larghezza unità                 |     247,90 mm          |     9,760 pollici        |
|     Profondità unità                 |     163,07 mm          |     6,420 pollici        |
|     Peso unitario                |     2,878 kg           |     6,344 lbs           |
|     Lunghezza del corriere esterno    |     446,00 mm          |     17,559 pollici       |
|     Larghezza mittente esterno     |     257,99 mm          |     10,157 pollici       |
|     Profondità del mittente esterno     |     172,01 mm          |     6,772 pollici        |
|     Peso mittente esterno    |     3,284 kg           |     7,240 lbs           |

> [!NOTE]
> - Unità: la scatola nera in stile vendita HoloLens 2 viene venduta.
> - Spedizioniere esterno: i pacchetti di spedizione di protezione intorno all'unità.

## <a name="finding-the-serial-number"></a>Ricerca del numero di serie

Il numero di serie HoloLens 2 dispositivi viene stampato sotto la visiera.

1. Alzare la visiera del dispositivo.
1. Guarda vicino al rilievo della fronte.
1. È possibile trovare il numero di serie che si trova vicino alla cernie.

<img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

Il numero di serie è disponibile anche tramite un PC connesso:

1. Collegare il dispositivo
1. Passare a **Questo PC** in Esplora file
1. Fare clic con il pulsante destro **del mouse e** selezionare Proprietà del dispositivo HoloLens
1. Verrà visualizzato il numero di serie del dispositivo, come illustrato nello screenshot seguente.

<img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Confrontare HoloLens 2 edizioni](hololens2-options.md)

> [!div class="nextstepaction"]
> [Configurare e avviare il HoloLens 2](hololens2-setup.md)
