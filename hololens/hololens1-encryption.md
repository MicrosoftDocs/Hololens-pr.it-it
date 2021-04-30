---
title: Crittografia BitLocker di HoloLens
description: Informazioni su come abilitare la crittografia dei dispositivi Bitlocker per proteggere i file archiviati nei dispositivi di realtà mista HoloLens.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 268c3650b85e7e7f102618ccc5a94c25de54dcfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309064"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>Crittografia BitLocker di HoloLens (prima generazione)

HoloLens (prima generazione) e HoloLens 2 entrambi supportano la crittografia dei dispositivi con BitLocker, tuttavia BitLocker è sempre abilitato HoloLens 2.

Questo articolo consente di abilitare e gestire BitLocker in HoloLens (prima generazione).

In HoloLens (prima generazione) è possibile abilitare la crittografia dei dispositivi BitLocker manualmente o usando la gestione dei dispositivi mobili (MDM). Seguire queste istruzioni per abilitare [la crittografia dei dispositivi BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) per proteggere i file e le informazioni archiviate in HoloLens. La crittografia dei dispositivi consente di proteggere i dati usando il metodo di crittografia AES-CBC 128, equivalente al metodo [EncryptionMethodByDriveType 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) nel provider del servizio di configurazione BitLocker . Il personale che dispone della chiave di crittografia corretta, ad esempio una password, può decrittografarla o eseguire un ripristino dei dati.

## <a name="enable-device-encryption-using-mdm"></a>Abilitare la crittografia dei dispositivi tramite MDM

È possibile usare il provider di Gestione dispositivi mobili (MDM) per applicare un criterio che richiede la crittografia del dispositivo. Il criterio da usare è [l'impostazione Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in Policy CSP.

[Vedere le istruzioni per abilitare la crittografia dei dispositivi Microsoft Intune.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Per altri strumenti MDM, vedere la documentazione del provider MDM per istruzioni. Se il provider MDM richiede UN URI personalizzato per la crittografia del dispositivo, usare la configurazione seguente:

- **Nome**: un nome a scelta
- **Descrizione:** facoltativo
- **URI OMA**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Tipo di dati**: integer
- **Valore**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Abilitare la crittografia dei dispositivi usando un pacchetto di provisioning

I pacchetti di provisioning sono file creati dallo strumento Progettazione configurazione di Windows che applicano una configurazione specificata a un dispositivo. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Creare un pacchetto di provisioning che aggiorna l'edizione Windows Holographic e abilita la crittografia

1. [Creare un pacchetto di provisioning per HoloLens.](hololens-provisioning.md)
1. Passare a **Impostazioni di runtime**  >  **Criteri**  >  **Sicurezza** e **selezionare RichiediDispositivaCrittografia.**

    ![Richiedi l'impostazione di crittografia del dispositivo configurata su Sì](images/device-encryption.png)

1. Trovare il file di licenza XML fornito al momento dell'acquisto di Commercial Suite.

1. Individua e seleziona il file di licenza XML fornito al momento dell'acquisto di Commercial Suite.
    > [!NOTE]
    > È possibile configurare le [impostazioni aggiuntive nel pacchetto di provisioning](hololens-provisioning.md).

1. Scegliere **Save** (Salva) dal menu **File**. 

1. Leggere l'avviso che spiega che i file di progetto possono contenere informazioni riservate e fare clic su **OK.**

    > [!IMPORTANT]
    > Quando si compila un pacchetto di provisioning, è possibile includere informazioni riservate nei file di progetto e nel file del pacchetto di provisioning (con estensione ppkg). Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati. È consigliabile archiviare i file di progetto in un percorso sicuro ed eliminare i file di progetto quando non sono più necessari.

1. Fai clic su **Pacchetto di provisioning** nel menu **Esporta**.
1. Impostare **Proprietario** su **Amministratore IT,** che imposta la precedenza di questo pacchetto di provisioning su un valore superiore rispetto al provisioning dei pacchetti applicati al dispositivo da altre origini e quindi selezionare **Avanti.**
1. Imposta un valore per **Versione pacchetto**.

    > [!TIP]
    > Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.

1. In **Seleziona i dettagli di sicurezza per il pacchetto di provisioning**, fai clic su **Avanti**.
1. Fai clic su **Next** per specificare il percorso di output in cui vuoi posizionare il pacchetto di provisioning creato. Per impostazione predefinita, Progettazione immagine e configurazione di Windows usa la cartella di progetto come percorso di output.

    Facoltativamente, puoi fare clic su Sfoglia per modificare il percorso di output predefinito.

1. Fare clic su **Avanti**.
1. Fai clic su **Build** per iniziare a compilare il pacchetto. Le informazioni del progetto vengono visualizzate nella pagina di compilazione e la barra di stato indica lo stato della compilazione.
1. Al termine della compilazione, fai clic su **Fine**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Applicare il pacchetto di provisioning a HoloLens

1. Connettere il dispositivo tramite USB a un PC e avviare  il dispositivo, ma non continuare oltre la pagina adatta dell'esperienza di configurazione iniziale (la prima pagina con la casella blu).
1. Premi brevemente e rilascia i pulsanti di **abbassamento del volume** e **Alimentazione** simultaneamente.
1. HoloLens verrà visualizzato come un dispositivo in Esplora File nel PC.
1. In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.
1. Premi brevemente e rilascia nuovamente i pulsanti di **abbassamento del volume** e **Alimentazione** simultaneamente mentre sei nella pagina **adatta**.
1. Il dispositivo ti chiederà se consideri attendibile il pacchetto e vuoi applicarlo. Confermare che consideri attendibile il pacchetto.
1. Potrai vedere se il pacchetto è stato applicato correttamente o meno. Se l'applicazione non è riuscita, è possibile correggere il pacchetto e riprovare. Se l'operazione ha esito positivo, procedere con la configurazione del dispositivo.

> [!NOTE]
> Se il dispositivo è stato acquistato prima di agosto 2016, è necessario accedere al dispositivo con un account Microsoft, ottenere l'aggiornamento più recente del sistema operativo e quindi reimpostare il sistema operativo per applicare il pacchetto di provisioning.

## <a name="verify-device-encryption"></a>Verificare la crittografia del dispositivo

La crittografia è invisibile all'utente in HoloLens. Per verificare lo stato di crittografia del dispositivo:

- In HoloLens passare a Impostazioni  >  **Sistema**  >  **Informazioni su**. **BitLocker** è **abilitato** se il dispositivo è crittografato. 

    ![Schermata Informazioni su che mostra BitLocker abilitato](images/about-encryption.png)
