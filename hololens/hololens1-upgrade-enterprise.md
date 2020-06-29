---
title: Sbloccare le funzionalità di Windows Holographic for Business
description: Quando si esegue l'aggiornamento a Windows olografico for business, HoloLens offre funzionalità aggiuntive progettate per le aziende.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829335"
---
# Sbloccare le funzionalità di Windows Holographic for Business

> [!IMPORTANT]
> Questa pagina si applica solo a HoloLens 1st Gen.

Microsoft HoloLens è disponibile in *Development Edition*, che esegue Windows olografico (un'edizione di Windows 10 progettata per HoloLens) e nella [suite commerciale](hololens-commercial-features.md), che offre funzionalità aggiuntive progettate per le aziende.

Quando acquisti la versione Commercial Suite, ricevi una licenza che aggiorna Windows Holographic a Windows Holographic for Business. Puoi applicare questa licenza al dispositivo usando il [provider di gestione di dispositivi mobili (MDM)](#edition-upgrade-by-using-mdm) dell'organizzazione o un pacchetto di [provisioning](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> In Windows 10, versione 1803, è possibile verificare che HoloLens sia stato aggiornato all'edizione aziendale selezionando sistema di **Impostazioni**  >  **System**.

## Aggiornamento dell'edizione tramite MDM

La licenza enterprise può essere applicata da qualsiasi provider MDM che supporta il [provider di servizi di configurazione (CSP) di WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx). La versione più recente dell'API MDM per Microsoft supporterà CSP WindowsLicensing.

Per istruzioni dettagliate sull'aggiornamento di HoloLens con Microsoft Intune, vedere [aggiornare i dispositivi che eseguono Windows olografico in Windows olografico for business](https://docs.microsoft.com/intune/holographic-upgrade).

 In altri provider MDM, i passaggi specifici per la configurazione e la distribuzione dei criteri possono variare.

## Aggiornamento dell'edizione con un pacchetto di provisioning

I pacchetti di provisioning sono file creati dallo strumento Progettazione configurazione di Windows che applicano una configurazione specifica a un dispositivo.

### Creare un pacchetto di provisioning che consente di aggiornare l'edizione di Windows Holographic

1. [Creare un pacchetto di provisioning per HoloLens.](hololens-provisioning.md)
1. Vai a **Impostazioni di runtime** > **EditionUpgrade** e seleziona **EditionUpgradeWithLicense**.

    ![Aggiornare l'edizione con le impostazioni di licenza selezionate](images/icd1.png)

1. Trovare il file di licenza XML fornito quando è stata acquistata la famiglia di prodotti commerciali.

    > [!NOTE]
    > È possibile configurare le [impostazioni aggiuntive nel pacchetto di provisioning](hololens-provisioning.md).

1. Scegliere **Salva**dal menu **file** . 

1. Leggere l'avviso che i file di progetto possono contenere informazioni riservate e fare clic su **OK**.

    > [!IMPORTANT]
    > Quando si compila un pacchetto di provisioning, è possibile includere informazioni riservate nei file di progetto e nel pacchetto di provisioning (file con estensione ppkg). Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati. È consigliabile archiviare i file di progetto in un percorso sicuro ed eliminare i file di progetto quando non sono più necessari.

1. Scegli **Pacchetto di provisioning** dal menu **Esporta**.

1. Modificare il **proprietario** dell' **amministratore IT**, impostando la precedenza del pacchetto di provisioning su un valore superiore rispetto ad altri applicati a questo dispositivo da origini diverse e quindi selezionare **Avanti**.

1. Imposta un valore per **Versione pacchetto**.

    > [!TIP]
    > Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.

1. In **selezionare dettagli di sicurezza per il pacchetto di provisioning**selezionare **Avanti**.

1. Selezionare **Avanti** per specificare la posizione di output in cui si vuole inserire il pacchetto di provisioning dopo la compilazione. Per impostazione predefinita, Progettazione immagini e configurazione di Windows usa la cartella di progetto come percorso di output.

    Facoltativamente, è possibile selezionare **Sfoglia** per modificare la posizione di output predefinita.

1. Seleziona **Avanti**.

1. Selezionare **Compila** per iniziare a creare il pacchetto. La pagina di compilazione Visualizza le informazioni sul progetto e la barra di stato indica lo stato della compilazione.

1. Al termine della compilazione, selezionare **fine**.

### Applicare il pacchetto di provisioning a HoloLens

1. Usando il cavo USB, connettere il dispositivo a un PC. Avviare il dispositivo, ma non continuare oltre la pagina **adatta** dell'esperienza di configurazione iniziale (la prima pagina con la casella blu). Nel PC HoloLens viene visualizzato come dispositivo in Esplora file.

    > [!NOTE]
    > Se il dispositivo HoloLens è in esecuzione in Windows 10, versione 1607 o precedente, aprire Esplora file premendo brevemente e rilasciando contemporaneamente i pulsanti **volume giù** e **alimentazione** nel dispositivo.

1. In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.

1. Mentre HoloLens è ancora nella pagina **Fit** , premere brevemente e rilasciare di nuovo contemporaneamente i pulsanti **volume giù** e **Power** .

1. HoloLens chiede se si ritiene attendibile il pacchetto e si desidera applicarlo. Confermare che consideri attendibile il pacchetto.

1. Potrai vedere se il pacchetto è stato applicato correttamente o meno. Se non è stata applicata correttamente, è possibile correggere il pacchetto e riprovare. In caso di esito positivo, procedere con la configurazione del dispositivo.
