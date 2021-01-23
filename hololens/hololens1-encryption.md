---
title: Crittografia BitLocker di HoloLens
description: Scopri come abilitare la crittografia del dispositivo Bitlocker per proteggere i file archiviati nei dispositivi holoLens in realtà mista.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284027"
---
# Crittografia BitLocker di HoloLens (Prima generazione)

HoloLens (prima generazione) e HoloLens 2 supportano entrambi la crittografia del dispositivo con BitLocker, tuttavia, BitLocker è sempre abilitato in HoloLens 2.

Questo articolo ti aiuterà a abilitare e gestire BitLocker in HoloLens (prima generazione).

In HoloLens (prima generazione) puoi abilitare la crittografia dei dispositivi BitLocker manualmente o usando la gestione dei dispositivi mobili (MDM). Segui queste istruzioni per abilitare la crittografia del dispositivo [BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) per proteggere i file e le informazioni archiviati in HoloLens. La crittografia del dispositivo consente di proteggere i dati usando il metodo di crittografia AES-CBC 128, che equivale al metodo [3 EncryptionMethodByDriveType](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) nel provider di servizi di configurazione BitLocker. Il personale che dispone della chiave di crittografia corretta ,ad esempio una password, può decrittografarla o eseguire un ripristino dei dati.

## Abilitare la crittografia del dispositivo tramite MDM

Puoi usare il provider di gestione dei dispositivi mobili (MDM) per applicare un criterio che richiede la crittografia del dispositivo. Il criterio da usare è [l'impostazione Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) nel CSP Policy.

[Vedere le istruzioni per abilitare la crittografia del dispositivo con Microsoft Intune.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Per altri strumenti MDM, vedi le istruzioni nella documentazione del tuo provider MDM. Se il provider MDM richiede UN URI personalizzato per la crittografia del dispositivo, usa la configurazione seguente:

- **Nome**: un nome di tua scelta
- **Descrizione**: facoltativa
- **URI OMA**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Tipo di dati:** intero
- **Valore**: `1`

## Abilitare la crittografia del dispositivo usando un pacchetto di provisioning

I pacchetti di provisioning sono file creati dallo strumento Progettazione configurazione di Windows che applicano una configurazione specifica a un dispositivo. 

### Creare un pacchetto di provisioning che aggiorna l'edizione di Windows Holographic e abilita la crittografia

1. [Creare un pacchetto di provisioning per HoloLens.](hololens-provisioning.md)
1. Vai a **Impostazioni di runtime** > **Criteri** > **Sicurezza** e seleziona **RequireDeviceEncryption**.

    ![L'impostazione di crittografia del dispositivo deve essere configurata su Sì](images/device-encryption.png)

1. Trova il file di licenza XML fornito al momento dell'acquisto di Commercial Suite.

1. Individua e seleziona il file di licenza XML fornito al momento dell'acquisto di Commercial Suite.
    > [!NOTE]
    > È possibile configurare le [impostazioni aggiuntive nel pacchetto di provisioning](hololens-provisioning.md).

1. Scegli **Salva** dal menu **File**. 

1. Leggere l'avviso che spiega che i file di progetto possono contenere informazioni riservate e fare clic su **OK.**

    > [!IMPORTANT]
    > Quando si crea un pacchetto di provisioning, è possibile includere informazioni riservate nei file di progetto e nel file del pacchetto di provisioning (con estensione ppkg). Anche se hai la possibilità di crittografare il file con estensione PPKG, i file di progetto non vengono crittografati. È consigliabile archiviare i file di progetto in un percorso sicuro ed eliminarli quando non sono più necessari.

1. Fai clic su **Pacchetto di provisioning** nel menu **Esporta**.
1. Modifica **Proprietario** in **Amministratore IT** per assegnare a questo pacchetto di provisioning una precedenza maggiore rispetto agli altri pacchetti di provisioning applicati al dispositivo da altre origini, quindi seleziona **Avanti**.
1. Imposta un valore per **Versione pacchetto**.

    > [!TIP]
    > Puoi apportare modifiche a pacchetti esistenti e modificare il numero di versione per aggiornare pacchetti applicati in precedenza.

1. In **Seleziona i dettagli di sicurezza per il pacchetto di provisioning**, fai clic su **Avanti**.
1. Fai clic su **Avanti** per specificare il percorso di output in cui vuoi posizionare il pacchetto di provisioning creato. Per impostazione predefinita, Progettazione immagini e configurazione di Windows usa la cartella di progetto come percorso di output.

    Facoltativamente, puoi fare clic su Sfoglia per modificare il percorso di output predefinito.

1. Fai clic su **Avanti**.
1. Fai clic su **Build** per iniziare a compilare il pacchetto. Le informazioni del progetto vengono visualizzate nella pagina di compilazione e la barra di stato indica lo stato della compilazione.
1. Al termine della compilazione, fai clic su **Fine**.

### Applicare il pacchetto di provisioning a HoloLens

1. Connetti il dispositivo tramite USB a un PC e avvia il dispositivo, ma non proseguire oltre la pagina **adatta** di Configurazione guidata (la prima pagina con il riquadro blu).
1. Premi brevemente e rilascia i pulsanti di **abbassamento del volume** e **Arresta** simultaneamente.
1. HoloLens verrà visualizzato come un dispositivo in Esplora File nel PC.
1. In Esplora File, trascinare e rilasciare il pacchetto di provisioning (.ppkg) nell'archiviazione del dispositivo.
1. Premi brevemente e rilascia nuovamente i pulsanti di **abbassamento del volume** e **Alimentazione** simultaneamente mentre sei nella pagina **adatta**.
1. Il dispositivo ti chiederà se consideri attendibile il pacchetto e vuoi applicarlo. Confermare che consideri attendibile il pacchetto.
1. Potrai vedere se il pacchetto è stato applicato correttamente o meno. Se l'applicazione non è riuscita, puoi correggere il pacchetto e riprovare. Se ha avuto esito positivo, continua con la Configurazione guidata.

> [!NOTE]
> Se il dispositivo è stato acquistato prima di agosto 2016, dovrai accedere con un account Microsoft, ottenere l'aggiornamento più recente del sistema operativo e quindi reimpostare il sistema operativo per applicare il pacchetto di provisioning.

## Verificare la crittografia dispositivo

La crittografia è invisibile all'utente in HoloLens. Per verificare lo stato della crittografia del dispositivo:

- In HoloLens vai a **Impostazioni** > **Sistema** > **Informazioni su**. **BitLocker** è **abilitato** se il dispositivo è crittografato. 

    ![Informazioni sulla schermata che mostra BitLocker abilitato](images/about-encryption.png)
