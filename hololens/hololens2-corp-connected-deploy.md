---
title: Guida alla distribuzione - Connessione aziendale HoloLens 2 con Dynamics 365 Guides - Distribuisci
description: Informazioni su come configurare le distribuzioni di HoloLens 2 su una rete connessa aziendale con Dynamics 365 Guides.
keywords: HoloLens, gestione, aziendale connesso, Dynamics 365 Guides, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.openlocfilehash: 7df2b00b2d87be7b9ad4a5d84c83251ec0ebec4d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033491"
---
# <a name="deploy---corporate-connected-guide"></a>Distribuire - Guida alla connessione aziendale

Una parte importante di ogni distribuzione è garantire che la distribuzione sia configurata correttamente prima di testarla per garantire un'esperienza uniforme per l'utente finale.

Poiché si distribuisce il certificato Wi-Fi tramite MDM, è necessario configurare inizialmente HoloLens e registrare i dispositivi in una rete Wi-Fi aperta o in una rete che non richiede il certificato. Al termine della configurazione guidata e della registrazione del HoloLens, il dispositivo riceverà il certificato di rete e loB configurati in precedenza e sarà possibile verificare che entrambi siano stati ricevuti dal dispositivo.

Successivamente, sarà possibile confermare che è possibile creare e usare una guida di test.

## <a name="enrollment-validation"></a>Convalida della registrazione

Ora che tutti gli elementi sono configurati correttamente per Azure AD e la registrazione MDM, il resto dovrebbe essere uno snap. Sono necessari una connessione Wi-Fi e il dispositivo HoloLens e uno degli account utente configurati Azure AD precedenza.

Se il dispositivo non si trova attualmente in uno stato delle impostazioni predefinite, è il momento giusto per eseguire il [reflash del dispositivo.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Una volta che il dispositivo è in configurazione configurazione, è necessario iniziare a interagire e a seguire le istruzioni.

2. Connessione a una rete Wi-Fi aperta che non richiede certificati per l'aggiunta al Wi-Fi. In questo modo il dispositivo può scaricare il certificato da usare nel dispositivo dell'Wi-Fi dopo l'installazione iniziale.

3. Il prompt critico sarà quando viene chiesto se **Who è proprietario di HoloLens?** Selezionare My work or school owns it (L'account aziendale o **dell'istituto di** istruzione è proprietario) e immettere Azure AD credenziali dell'account.

4. Al termine della registrazione, verrà richiesto di configurare un PIN. Questo PIN è univoco per questo dispositivo per questo utente. Verranno anche richieste le scansioni Iris, i dati vocali e le impostazioni di telemetria e infine si sarà in grado di imparare ad aprire il menu Start e completare la Configurazione guidata.

5. Quando si apre la home page della realtà mista, apri il menu Start usando il **movimento Start** appena appreso.

6. Selezionare **l'app Impostazioni** e selezionare **Sistema.** La prima informazione che verrà visualizzata è il nome del dispositivo, che per il dispositivo HoloLens 2 sarà &quot; HOLOLENS, seguito da una stringa di sei &quot; caratteri.

7. Prendere nota di questo nome.

    ![HoloLens 2 Impostazioni precedente.](./images/hololens2-settings-about.jpg)

8. Verificare che il dispositivo sia stato aggiunto correttamente Azure AD. Esistono due modi:

    1.  App Impostazioni. In  Impostazioni **account** Accedere  ->  **all'account di lavoro o dell'istituto di istruzione.** Da questa schermata è possibile verificare che la registrazione sia stata completata correttamente. Vedere Connected &quot; to nameofAAD&#39;'s Azure AD (Connesso a nameofAAD Azure AD). Connesso da *yourusername@nameofAAD.onmicrosoft.com* . In questo modo si verificherà che il dispositivo sia stato aggiunto&#39;'Azure AD.

    1. Oggetto [portale di Azure](https://portal.azure.com/#home). Passare a **Azure Active Directory**  ->  **Dispositivi Tutti** i  ->  **dispositivi** e cercare il nome del dispositivo. In Tipo di join verrà visualizzato come "Azure AD aggiunto".
        ![Verificare il tipo di join Azure AD.](./images/hololens2-devices-all-devices.png)

9. Verificare che il dispositivo sia registrato con MDM. Esistono due modi:

    1. Da **Impostazioni** selezionare **Account** Accedi  ->  **all'account di lavoro o dell'istituto di istruzione.** Da questa schermata è possibile verificare che la registrazione sia stata completata correttamente. Vedere Connected &quot; to nameofAAD&#39;'s Azure AD (Connesso a nameofAAD Azure AD). Connesso da *yourusername@nameofAAD.onmicrosoft.com* . Da questo account di accesso aziendale o dell'istituto di istruzione selezionare Connesso &quot; a nameofAAD&#39;'Azure AD. Connesso da yourusername@nameofAAD.onmicrosoft.com &quot; e selezionare il **pulsante** Informazioni.

    1. [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home). Accedere e selezionare Dispositivi **e** quindi **Tutti i dispositivi.** Da qui è possibile cercare il nome HoloLens dispositivo&#39;nome. Dovrebbe essere possibile visualizzare i dati HoloLens elencati in Intune.

        ![Verificare che sia gestito da Intune in Azure AD.](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi convalida del certificato

A questo punto, il dispositivo dovrebbe aver ricevuto il Wi-Fi certificato. La convalida più semplice possibile è tentare di connettersi alla connessione Wi-Fi per cui si&#39;ricevuto il certificato. Aprire l'app **Impostazioni,** passare a Rete **&amp; Internet**  ->  **Wi-Fi** e selezionare la connessione Wi-Fi. Una volta connessi, aprire l'app Microsoft Edge e verificare che sia possibile passare a un sito Web.

Per verificare di aver ricevuto il certificato nel dispositivo, è possibile usare Gestione [certificati](/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Convalidare l'installazione dell'app LOB

Per visualizzare lo stato di avanzamento dell'installazione di un'app gestita, è possibile verificare se l'app è installata o Impostazioni. Configurando un'app LOB come installazione necessaria per il gruppo, dopo aver registrato il HoloLens con un utente nel gruppo assegnato, l'app verrà scaricata automaticamente nel HoloLens.

Aprire il menu Start e selezionare **Tutte le app.** A seconda del numero di app disponibili, potrebbe essere necessario usare i pulsanti pagina **su** **o pagina** giù.

Per convalidare l'installazione dell'app nel dispositivo, è possibile farlo tramite account **di Impostazioni** Accesso aziendale o dell'istituto di istruzione, selezionare l'account, quindi il pulsante Informazioni e scorrere verso il basso per visualizzare diverse configurazioni e app applicate al dispositivo da  ->    ->  MDM. 

Per convalidare l'installazione da Intune, passare alla pagina app [->](https://endpoint.microsoft.com/#home)app del portale MEM  ->     -> *TheNameOfYourApp* Device install status (Nome Del dispositivo  ->  **app).**

Vedere altre informazioni: [Distribuzione di app di Intune per HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Convalidare Dynamics 365 Guides

Sono disponibili modalità per l'app Guides HoloLens, creazione e funzionamento. È necessario completare la creazione di una guida prima di operarla.

### <a name="authoring-the-guide"></a>Creazione della guida

Non è necessario eseguire molte azioni per questa convalida rapida. È sufficiente selezionare la guida preparata nel PC. Sarà necessario ancorare [la guida](/dynamics365/mixed-reality/guides/hololens-app-anchor), per una convalida rapida è possibile usare un ancoraggio olografico. Successivamente, è necessario inserire [i passaggi e i modelli](/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Sarà necessario il ruolo **Creazione per** accedere al PC e creare nel HoloLens. Il ruolo Operatore è di sola lettura e non ha accesso all'app per PC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Uso della guida

Dopo aver installato gli ologrammi, è possibile testare la guida. 
- Selezionare **la modalità operatore**
- Fare clic sui passaggi della guida.

Per indicazioni più dettagliate su come usare una guida, vedere queste risorse:

[Panoramica del funzionamento di una guida in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-overview)

[Orientarsi con la scheda Passaggio come operatore in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Passaggio successivo 
> [!div class="nextstepaction"]
> [Distribuzione connessa aziendale - Manutenzione](hololens2-corp-connected-maintain.md)
