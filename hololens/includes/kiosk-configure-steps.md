---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2021
ms.locfileid: "129220820"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune app singola in modalità tutto schermo](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune app singola in modalità tutto schermo

1. Creare un profilo di configurazione <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Scegliere il modello per chiosco multimediale <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Scegliere se una singola app o più app in modalità tutto schermo e scegliere anche il tipo di destinazione dell'utente per la modalità tutto schermo <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Scegliere l'app da eseguire in modalità tutto schermo <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Lasciare il resto delle opzioni così come sono <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Scegliere a quali gruppi/dispositivi o utenti deve essere assegnato questo profilo di configurazione <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Esaminare e creare per salvare il profilo di configurazione
8. Eseguire la sincronizzazione MDM a partire da un dispositivo o da Intune per applicare la configurazione al dispositivo. [Sincronizzare i dispositivi](/mem/intune/remote-actions/device-sync#sync-a-device) da Intune o dal dispositivo **tramite account Impostazioni -> -> aziendale** o dell'istituto di istruzione ->selezionare l'account connesso **-> Info -> Sync**
9. Accedere come utente di destinazione per l'esperienza in modalità tutto schermo.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune di più app in modalità tutto schermo](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune di più app in modalità tutto schermo

1. Creare un profilo di configurazione <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Scegliere il modello per chiosco multimediale <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Scegliere se una singola app o più app in modalità tutto schermo e scegliere anche il tipo di destinazione dell'utente per la modalità tutto schermo <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Scegliere le app da eseguire in modalità tutto schermo <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Lasciare il resto delle opzioni così come sono <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Scegliere a quali gruppi/dispositivi o utenti deve essere assegnato questo profilo di configurazione <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Esaminare e creare per salvare il profilo di configurazione
8. Eseguire la sincronizzazione MDM a partire da un dispositivo o da Intune per applicare la configurazione al dispositivo. [Sincronizzare i dispositivi](/mem/intune/remote-actions/device-sync#sync-a-device) da Intune o dal dispositivo **tramite account Impostazioni -> -> aziendale** o dell'istituto di istruzione ->selezionare l'account connesso **-> Info -> Sync**
9. Accedere come utente di destinazione per l'esperienza in modalità tutto schermo.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune modello personalizzato](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Microsoft Intune modello personalizzato

1. Creare la configurazione XML per l'esperienza di chiosco multimediale desiderata. Per [iniziare,](../hololens-kiosk-reference.md#kiosk-xml-code-samples) vedere gli esempi qui.

1. Creare un profilo di configurazione personalizzato <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Specificare il nome del profilo di configurazione personalizzato e fare clic su "Aggiungi" nella sezione "Impostazioni di configurazione" per aggiungere le impostazioni URI OMA. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Specificare il nome delle impostazioni URI OMA.

    1. Nella casella di testo URI OMA immettere **./Device/Vendor/MSFT/AssignedAccess/Configuration**
    1. Scegliere Tipo di dati come **Stringa.**
    1. Nella casella di testo value (valore) copiare e incollare il file XML di configurazione dell'accesso assegnato (vedere i collegamenti di riferimento per esempi basati sullo scenario e aggiornare in base alle esigenze prima di copiare e incollare).
    1. Selezionare il pulsante Salva per salvare l'impostazione e la configurazione.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Scegliere a quali gruppi/dispositivi o utenti deve essere assegnato questo profilo di configurazione. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Esaminare e creare per salvare il profilo di configurazione.
1. Eseguire la sincronizzazione MDM a partire da un dispositivo o da Intune per applicare la configurazione al dispositivo. [Sincronizzare i dispositivi](/mem/intune/remote-actions/device-sync#sync-a-device) da Intune o dal dispositivo **tramite account Impostazioni -> -> aziendale** o dell'istituto di istruzione ->selezionare l'account connesso **-> Info -> Sync**
1. Accedere come utente di destinazione per l'esperienza in modalità tutto schermo.

# <a name="runtime-provisioning---multi-app"></a>[Provisioning in fase di esecuzione - App multipla](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>Provisioning in fase di esecuzione - App multipla

1. Creare la configurazione XML per l'esperienza di chiosco multimediale desiderata. Per [iniziare,](../hololens-kiosk-reference.md#kiosk-xml-code-samples) vedere gli esempi qui.

1. Aprire [Windows Progettazione configurazione](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Nella pagina Iniziale selezionare **Provisioning HoloLens dispositivi.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Selezionare **Provisioning HoloLens 2 dispositivi e quindi** selezionare Avanti. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Assegnare un nome al progetto. Facoltativamente, scrivere una descrizione. Selezionare **Fine** per continuare.

6. In basso a sinistra nella schermata selezionare **Passa all'editor avanzato.** Confermare il passaggio all'editor avanzato selezionando **Sì.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. Sul lato sinistro espandere Impostazioni di runtime, AssignedAccess e **selezionare MultiAppAssignedAccess.** <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Selezionare il pulsante **Sfoglia...** per aprire Esplora file. Selezionare il file XML in modalità tutto schermo configurato.

9. Selezionare **Esporta** e quindi **Pacchetto di provisioning.**

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Modificare il tipo di proprietario in **Amministratore IT.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Selezionare **Avanti** per tre volte. Selezionare quindi **Compila**.

12. Dopo la compilazione del pacchetto di provisioning, aprire la cartella Percorso di output. Il file con estensione ppkg è il pacchetto di provisioning. Passaggio facoltativo: salvare il progetto.

13. A questo punto è possibile applicare il pacchetto di provisioning. È possibile applicare [un pacchetto di provisioning a HoloLens](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) durante l'installazione o applicare un pacchetto di provisioning a HoloLens dopo [l'installazione di](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

14. Accedere come utente di destinazione per l'esperienza in modalità tutto schermo.

# <a name="runtime-provisioning---single-app"></a>[Provisioning in fase di esecuzione - App singola](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>Provisioning in fase di esecuzione - App singola

1. Aprire [Windows Progettazione configurazione](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Nella pagina Iniziale selezionare **Provisioning HoloLens dispositivi.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Selezionare **Provisioning HoloLens 2 dispositivi e quindi** selezionare Avanti. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Assegnare un nome al progetto. Facoltativamente, scrivere una descrizione. Selezionare **Fine** per continuare.

5. In basso a sinistra nella schermata selezionare **Passa all'editor avanzato.** Confermare il passaggio all'editor avanzato selezionando **Sì.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. Sul lato sinistro espandere Impostazioni di runtime, AssignedAccess e **selezionare AssignedAccessSettings.** <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Definire il chiosco multimediale nella casella di testo. Ad esempio, il codice seguente crea una singola app in modalità tutto schermo per un account locale denominato LocalAccount che è l'app delle impostazioni.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Selezionare **Esporta** e quindi **Pacchetto di provisioning.** <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Modificare il tipo di proprietario in **Amministratore IT.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Selezionare **Avanti** per tre volte. Selezionare quindi **Compila**.

11. Dopo la compilazione del pacchetto di provisioning, aprire la cartella Percorso di output. Il file con estensione ppkg è il pacchetto di provisioning. Passaggio facoltativo: salvare il progetto.

12. A questo punto è possibile applicare il pacchetto di provisioning. È possibile applicare [un pacchetto di provisioning a HoloLens](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) durante l'installazione o applicare un pacchetto di provisioning a HoloLens dopo [l'installazione di](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).