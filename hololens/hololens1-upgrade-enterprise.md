---
title: Sbloccare Windows Holographic for Business funzionalità
description: Quando si esegue l'Windows Holographic for Business, HoloLens offre funzionalità aggiuntive progettate per le aziende.
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
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189189"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Sbloccare Windows Holographic for Business funzionalità

> [!IMPORTANT]
> Questa pagina si applica solo HoloLens prima generazione.

Microsoft HoloLens è disponibile in *Development Edition,* che esegue Windows Holographic (un'edizione di Windows 10 progettata per HoloLens) e in [Commercial Suite,](hololens-commercial-features.md)che offre funzionalità aggiuntive progettate per le aziende.

Quando si acquista Commercial Suite, si riceve una licenza che aggiorna Windows Holographic a Windows Holographic for Business. È possibile applicare questa licenza al dispositivo usando il provider di gestione dei dispositivi mobili [(MDM)](#edition-upgrade-by-using-mdm) dell'organizzazione o un pacchetto [di provisioning](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> In Windows 10 versione 1803 è possibile verificare che il HoloLens sia stato aggiornato all'edizione Business selezionando **Impostazioni**  >  **System**.

## <a name="edition-upgrade-by-using-mdm"></a>Aggiornamento dell'edizione tramite MDM

La licenza enterprise può essere applicata da qualsiasi provider MDM che supporta il [provider di servizi di configurazione (CSP) di WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx). La versione più recente dell'API MDM per Microsoft supporterà CSP WindowsLicensing.

Per istruzioni dettagliate sull'aggiornamento di HoloLens tramite Microsoft Intune, vedere Aggiornare i dispositivi che eseguono Windows [Holographic a Windows Holographic for Business](/intune/holographic-upgrade).

 In altri provider MDM, i passaggi specifici per la configurazione e la distribuzione dei criteri possono variare.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Aggiornamento dell'edizione tramite un pacchetto di provisioning

I pacchetti di provisioning sono file creati dallo Windows Progettazione configurazione che applicano una configurazione specificata a un dispositivo.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Creare un pacchetto di provisioning che consente di aggiornare l'edizione di Windows Holographic

1. [Creare un pacchetto di provisioning per HoloLens.](hololens-provisioning.md)
1. Passare a **Impostazioni di runtime**  >  **EditionUpgrade e** selezionare **EditionUpgradeWithLicense**.

    ![Aggiornare l'edizione con l'impostazione di licenza selezionata.](images/icd1.png)

1. Trovare il file di licenza XML fornito al momento dell'acquisto di Commercial Suite.

    > [!NOTE]
    > È possibile configurare le [impostazioni aggiuntive nel pacchetto di provisioning](hololens-provisioning.md).

1. Scegliere **Save** (Salva) dal menu **File**. 

1. Leggere l'avviso che indica che i file di progetto possono contenere informazioni riservate e fare clic su **OK.**

    > [!IMPORTANT]
    > Quando si compila un pacchetto di provisioning, è possibile includere informazioni riservate nei file di progetto e nel file del pacchetto di provisioning (con estensione ppkg). Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati. È consigliabile archiviare i file di progetto in un percorso sicuro ed eliminare i file di progetto quando non sono più necessari.

1. Scegli **Pacchetto di provisioning** dal menu **Esporta**.

1. Impostare **Proprietario** su **Amministratore IT,** che imposta la precedenza di questo pacchetto di provisioning su un valore superiore rispetto ad altri applicati al dispositivo da origini diverse e quindi selezionare **Avanti.**

1. Imposta un valore per **Versione pacchetto**.

    > [!TIP]
    > Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.

1. In **Selezionare i dettagli di sicurezza per il pacchetto di provisioning** selezionare **Avanti.**

1. Selezionare **Avanti** per specificare il percorso di output in cui si vuole inserire il pacchetto di provisioning dopo la compilazione. Per impostazione predefinita, Progettazione immagine e configurazione di Windows usa la cartella di progetto come percorso di output.

    Facoltativamente, è possibile selezionare **Sfoglia per** modificare il percorso di output predefinito.

1. Selezionare **Avanti**.

1. Selezionare **Compila** per avviare la compilazione del pacchetto. Nella pagina di compilazione vengono visualizzate le informazioni sul progetto e l'indicatore di stato indica lo stato di compilazione.

1. Al termine della compilazione, selezionare **Fine.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Applicare il pacchetto di provisioning a HoloLens

1. Usando il cavo USB, connettere il dispositivo a un PC. Avviare il dispositivo, ma non  continuare oltre la pagina adatta dell'esperienza di configurazione iniziale (la prima pagina con la casella blu). Nel PC il HoloLens visualizzato come dispositivo in Esplora file.

    > [!NOTE]
    > Se il dispositivo HoloLens esegue Windows 10 versione 1607 o precedente, aprire Esplora file premendo brevemente e  rilasciando i pulsanti Volume down (Volume in basso) e **Power** (Alimentazione) simultaneamente sul dispositivo.

1. In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.

1. Mentre HoloLens è ancora nella  pagina adatta, premere e rilasciare brevemente i pulsanti **Volume down** (Volume in basso) e **Power (Alimentazione)** contemporaneamente.

1. HoloLens se si considera attendibile il pacchetto e si vuole applicarlo. Confermare che consideri attendibile il pacchetto.

1. Potrai vedere se il pacchetto è stato applicato correttamente o meno. Se non è stato applicato correttamente, è possibile correggere il pacchetto e riprovare. In caso di esito positivo, procedere con la configurazione del dispositivo.
