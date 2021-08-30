---
title: Guida alla distribuzione - Connessione aziendale HoloLens 2 con Dynamics 365 Guides - Distribuzione
description: Informazioni su come configurare le distribuzioni di HoloLens 2 dispositivi su una rete aziendale connessa con Dynamics 365 Guides.
keywords: HoloLens, gestione, aziendale connessa, Dynamics 365 Guides, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189682"
---
# <a name="deploy---corporate-connected-guide"></a>Distribuzione - Guida alla connessione aziendale

Una parte importante di ogni distribuzione è garantire che la distribuzione sia configurata correttamente prima di testarla manualmente per garantire un'esperienza ottimale per l'utente finale.

Poiché si distribuisce il certificato Wi-Fi tramite MDM, è necessario configurare inizialmente HoloLens e registrare i dispositivi in una rete Wi-Fi aperta o in una rete che non richiede il certificato. Al termine HoloLens configurazione guidata e registrazione, il dispositivo riceverà il certificato di rete e loB configurati in precedenza e sarà possibile convalidare che entrambi siano stati ricevuti dal dispositivo.

Successivamente, sarà possibile confermare che è possibile creare e gestire una guida di test.

## <a name="enrollment-validation"></a>Convalida della registrazione

Ora che tutto è configurato correttamente per la Azure AD e la registrazione MDM, il resto dovrebbe essere uno snap. Saranno necessari una connessione Wi-Fi e il dispositivo HoloLens e uno degli account utente Azure AD configurati in precedenza.

Se il dispositivo non si trova attualmente in uno stato delle impostazioni predefinite, è possibile eseguire il [reflash del dispositivo.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Una volta che il dispositivo è in configurazione di configurazione, è necessario iniziare a interagire e seguire le richieste.

2. Connessione a una rete Wi-Fi aperta che non richiede certificati per l'aggiunta al Wi-Fi. In questo modo il dispositivo può scaricare il certificato da usare nella rete dell'organizzazione Wi-Fi dopo la configurazione iniziale.

3. La richiesta critica verrà visualizzata quando viene richiesto **Who proprietario di questa HoloLens?** Selezionare **L'account aziendale o dell'istituto di** istruzione è proprietario e immettere le credenziali Azure AD'account.

4. Quando la registrazione ha esito positivo, verrà richiesto di configurare un PIN. Questo PIN è univoco per questo dispositivo per questo utente. Verranno anche richieste le analisi Iris, i dati vocali e le impostazioni di telemetria e infine si potrà imparare ad aprire il menu Start e completare la configurazione guidata.

5. Dopo aver atterrato in Mixed Reality Home, aprire il menu Start usando il movimento **Start** appena appreso.

6. Selezionare **l Impostazioni app** e selezionare **Sistema**. La prima informazione che verrà visualizzata è il nome del dispositivo, che per il dispositivo HoloLens 2 sarà &quot; HOLOLENS, seguito &quot; da una stringa di sei caratteri.

7. Prendere nota di questo nome.

    ![HoloLens 2 Impostazioni schermata.](./images/hololens2-settings-about.jpg)

8. Verificare che il dispositivo sia stato aggiunto correttamente Azure AD. Esistono due modi:

    1.  L Impostazioni app. Da **Impostazioni** account Accedere   ->  **all'istituto di istruzione o all'istituto di istruzione.** Da questa schermata è possibile verificare che la registrazione sia stata eseguita correttamente selezionando Connesso a &quot; nameofAAD&#39;'Azure AD. Connesso da *yourusername@nameofAAD.onmicrosoft.com* . In questo modo il dispositivo verrà aggiunto all'organizzazione&#39;'Azure AD.

    1. Oggetto [portale di Azure](https://portal.azure.com/#home). Passare a **Azure Active Directory**  ->  **Dispositivi**  ->  **Tutti i dispositivi** e cercare il nome del dispositivo. In Tipo di join verrà visualizzato come "Azure AD aggiunto".
        ![Verificare il tipo di join Azure AD.](./images/hololens2-devices-all-devices.png)

9. Verificare che il dispositivo sia registrato con MDM. Esistono due modi:

    1. Da **Impostazioni** selezionare **Account** Accesso  ->  **all'istituto di istruzione o all'istituto di istruzione.** Da questa schermata è possibile verificare che la registrazione sia stata eseguita correttamente selezionando Connesso a &quot; nameofAAD&#39;'Azure AD. Connesso da *yourusername@nameofAAD.onmicrosoft.com* . Da questo account aziendale o dell'istituto di istruzione di Access selezionare &quot; Connesso a nameofAAD&#39;account Azure AD. Connesso da yourusername@nameofAAD.onmicrosoft.com &quot; e selezionare il **pulsante** Informazioni.

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Accedere e selezionare Dispositivi  **e quindi**  Tutti  **i dispositivi**. Da qui, è possibile cercare il HoloLens dispositivo&#39;nome. Dovrebbe essere possibile visualizzare i HoloLens elencati in Intune.

        ![Verificare gestito da Intune in Azure AD.](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi convalida del certificato

A questo punto, il dispositivo dovrebbe aver ricevuto il Wi-Fi certificato. La convalida più semplice possibile è tentare di connettersi alla Wi-Fi per cui si&#39;ricevuto il certificato. Aprire l'app **Impostazioni** e passare a **Rete &amp; Internet**  ->  **Wi-Fi** e selezionare la connessione Wi-Fi. Una volta connessi, aprire l'app Microsoft Edge e confermare che è possibile passare a un sito Web.

Per verificare di aver ricevuto il certificato nel dispositivo, è possibile usare [Gestione certificati](/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Convalidare l'installazione dell'app LOB

Per visualizzare lo stato di avanzamento dell'installazione di un'app gestita, è possibile verificare se l'app è installata o Impostazioni. Configurando un'app LOB come installazione necessaria per il gruppo, dopo aver registrato il HoloLens con un utente nel gruppo assegnato, l'app verrà scaricata automaticamente nel HoloLens.

Aprire il menu Start e selezionare **Tutte le app.** A seconda del numero di app disponibili, potrebbe essere necessario usare i pulsanti **pagina su** o **pagina** giù.

Per convalidare l'installazione dell'app nel dispositivo, è possibile farlo tramite account **Impostazioni** Accesso aziendale o dell'istituto di istruzione, selezionare l'account e quindi il pulsante Informazioni e scorrere verso il basso per visualizzare diverse configurazioni e app applicate al dispositivo da  ->    ->  MDM. 

Per convalidare l'installazione da Intune, passare alla pagina App del portale [MEM](https://endpoint.microsoft.com/#home)-> Tutte le app  ->     -> *TheNameOfYourApp* Device install status (Tutte le app TheNameOfYourApp  ->  **Device install status).**

Vedere altre informazioni: [Distribuzione di app di Intune per HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Convalidare Dynamics 365 Guides

Sono disponibili modalità per l'app Guides HoloLens, creazione e funzionamento. È necessario completare la creazione di una guida prima di operarla.

### <a name="authoring-the-guide"></a>Creazione della guida

Non è necessario eseguire molto per questa convalida rapida. È sufficiente selezionare la guida preparata nel PC. È necessario ancorare la [guida](/dynamics365/mixed-reality/guides/hololens-app-anchor), per una convalida rapida è possibile usare un ancoraggio olografico. Successivamente, è necessario [inserire i passaggi e i modelli](/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Sarà necessario il ruolo **Creazione** per accedere al PC e creare nel HoloLens. Il ruolo Operatore è di sola lettura e non ha accesso all'app per PC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Uso della guida

Dopo aver installato gli ologrammi, è possibile testare il funzionamento della guida. 
- Selezionare **la modalità operatore**
- Fare clic sui passaggi della guida.

Per indicazioni più approfondite su come usare una guida, vedere queste risorse:

[Panoramica del funzionamento di una guida in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-overview)

[Orientarsi con la scheda Passaggio come operatore in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Passaggio successivo 
> [!div class="nextstepaction"]
> [Distribuzione connessa aziendale - Manutenzione](hololens2-corp-connected-maintain.md)
