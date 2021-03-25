---
title: Guida alla distribuzione - HoloLens 2 connesso all'azienda con le guide di Dynamics 365 - Distribuzione
description: Scopri come configurare le distribuzioni di dispositivi HoloLens 2 su una rete connessa aziendale con le guide di Dynamics 365.
keywords: HoloLens, gestione, corporate connected, Guide dynamics 365, AAD, Azure AD, MDM, Gestione dispositivi mobili
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448573"
---
# <a name="deploy---corporate-connected-guide"></a>Distribuire - Guida aziendale connessa

Una parte importante di ogni distribuzione è garantire che la distribuzione sia configurata correttamente prima di testarla manualmente per garantire un'esperienza ottimale per l'utente finale.

Poiché stiamo distribuendo il certificato Wi-Fi tramite MDM, dobbiamo inizialmente configurare HoloLens e registrare i dispositivi in una rete Wi-Fi aperta o in una rete che non richiede il certificato. Dopo che HoloLens ha completato la configurazione guidata e registrato, il dispositivo riceverà il certificato di rete e loB configurati in precedenza e saremo in grado di convalidare entrambi i messaggi ricevuti dal dispositivo.

In seguito, potrai confermare di poter creare e gestire una guida di test.

## <a name="enrollment-validation"></a>Convalida registrazione

Ora che tutto è configurato correttamente per La registrazione di Azure AD e MDM, il resto dovrebbe essere uno snap. Sarà necessaria una connessione Wi-Fi e il dispositivo HoloLens e uno degli account utente di Azure AD configurati in precedenza.

Se il dispositivo non è attualmente in uno stato delle impostazioni di fabbrica, ora è il momento giusto per [rifare il dispositivo.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Una volta che il dispositivo è in Configurazione computer, dovrai iniziare a interagire e seguire le istruzioni visualizzate.

2. Connettersi a una rete Wi-Fi aperta che non richiede certificati per l'aggiunta al Wi-Fi. In questo modo il dispositivo può scaricare il certificato da usare nell'organizzazione Wi-Fi dopo la configurazione iniziale.

3. Il prompt critico sarà quando ti viene chiesto **chi è il proprietario di questo HoloLens?** Selezionare **L'istituto di istruzione o l'istituto di istruzione è proprietario** e immettere le credenziali dell'account Azure AD.

4. Quando la registrazione ha esito positivo, ti verrà richiesto di configurare un PIN. Questo PIN è univoco per questo dispositivo per questo utente. Verranno inoltre richieste le analisi Iris, i dati vocali e le impostazioni di telemetria e, infine, sarà possibile imparare ad aprire il menu Start e completare la Configurazione guidata.

5. Una volta che sei atterrato in Mixed Reality Home, apri il menu Start usando il gesto **Start** appena appreso.

6. Seleziona **l'app** Impostazioni e seleziona **Sistema.** La prima informazione che vedrai è il nome del dispositivo, che per il dispositivo HoloLens 2 sarà &quot; HOLOLENS- seguito &quot; da una stringa di sei caratteri.

7. Prendere nota di questo nome.

    ![Schermata Impostazioni holoLens 2](./images/hololens2-settings-about.jpg)

8. Verificare che il dispositivo sia stato aggiunto correttamente ad Azure AD. Esistono due modi.

    1.  App Impostazioni. In **Impostazioni selezionare** Account **Accesso**  ->  **all'istituto di istruzione o all'istituto di istruzione.** Da questa schermata, è possibile verificare che la registrazione sia stata eseguita correttamente, vedere &quot; Connected to nameofAAD&#39;'s Azure AD. Connesso da *yourusername@nameofAAD.onmicrosoft.com*. In questo modo verrà verificato che il dispositivo sia aggiunto all'organizzazione&#39;Azure AD.

    1. Il [portale di Azure](https://portal.azure.com/#home). Vai a **Dispositivi di Azure Active Directory**Tutti i  ->  ****  ->  **dispositivi**e cerca il nome del dispositivo. In Tipo di partecipazione, verrà visualizzato come "Aggiunta ad Azure AD".
        ![Verificare il tipo di partecipazione in Azure AD](./images/hololens2-devices-all-devices.png)

9. Verifica che il dispositivo sia registrato con MDM. Esistono due modi.

    1. In **Impostazioni selezionare**Account **Accesso**  ->  **all'istituto di istruzione o all'istituto di istruzione.** Da questa schermata, è possibile verificare che la registrazione sia stata eseguita correttamente, vedere &quot; Connected to nameofAAD&#39;'s Azure AD. Connesso da *yourusername@nameofAAD.onmicrosoft.com*. Da questo account aziendale o dell'istituto di istruzione di Access selezionando &quot; Connesso a nameofAAD&#39;azure AD. Connesso tramite yourusername@nameofAAD.onmicrosoft.com &quot; e seleziona il **pulsante Info.**

    1. [Interfaccia di amministrazione di Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Accedi e seleziona  **Dispositivi e**  quindi Tutti  **i dispositivi**. Da qui puoi cercare il dispositivo HoloLens&#39;nome. Dovresti essere in grado di visualizzare holoLens elencato in Intune.

        ![Verificare gestito da Intune in Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi convalida del certificato

A questo punto, il dispositivo dovrebbe aver ricevuto il Wi-Fi certificato. La convalida più semplice possibile è tentare di connettersi alla connessione Wi-Fi per cui&#39;ricevuto il certificato. Apri l'app **Impostazioni** e passa a **Rete &amp; Internet**  ->  **Wi-Fi** e seleziona la connessione Wi-Fi. Dopo la connessione, apri l'app Microsoft Edge e verifica di poter accedere a un sito Web.

Per verificare di aver ricevuto il certificato nel dispositivo, puoi usare [Gestione certificati.](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>Convalidare l'installazione dell'app LOB

Per visualizzare l'avanzamento dell'installazione di un'app gestita, vedi se l'app è installata o controlla Impostazioni. Configurando un'app LOB come installazione necessaria per il gruppo, dopo aver registrato HoloLens con un utente nel gruppo assegnato, l'app verrà scaricata automaticamente in HoloLens.

Apri il menu Start e seleziona **Tutte le app.** A seconda del numero di app disponibili, potrebbe essere necessario usare i pulsanti **pagina** su **o pagina** giù.

Per convalidare l'installazione dell'app nel **** dispositivo, puoi farlo tramite Impostazioni Account Accedi all'istituto di istruzione o all'istituto di istruzione; seleziona l'account, quindi il pulsante Informazioni e scorri verso il basso per visualizzare diverse configurazioni e app applicate al dispositivo da  ->  ****  ->  **** MDM. ****

Per convalidare l'installazione da Intune, passare alla pagina App del portale [MEM](https://endpoint.microsoft.com/#home)-> Tutte le app  ->  **** ****  -> *TheNameOfYourApp*  ->  **Device install status.**

Altre informazioni: [Distribuzione di app intune per HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Convalidare le guide di Dynamics 365

Esistono modalità per l'app Guide in HoloLens, creazione e modifica e funzionamento. Dovrai completare la creazione di una guida prima di poterla utilizzare.

### <a name="authoring-the-guide"></a>Creazione della guida

Non è necessario eseguire molte azioni per questa convalida rapida. Basta selezionare la guida preparata nel PC. Dovrai ancorare [la](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)guida, per una convalida rapida puoi usare un ancoraggio olografico. Successivamente, è consigliabile [posizionare i passaggi e i modelli](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Sarà necessario il **ruolo Creazione e modifica** per accedere al PC e creare in HoloLens. Il ruolo Operatore è di sola lettura e non ha accesso all'app PC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Utilizzo della guida

Dopo aver installato gli ologrammi, puoi testare l'uso della guida. 
- Seleziona **modalità operatore**
- Fai clic sui passaggi della guida.

Per indicazioni più approfondite su come utilizzare una guida, vedere queste risorse:

[Panoramica dell'utilizzo di una guida nelle guide di Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Orientarsi con la scheda Passaggio come operatore nelle guide di Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Passaggio successivo 
> [!div class="nextstepaction"]
> [Distribuzione connessa aziendale - Manutenzione](hololens2-corp-connected-maintain.md)
