---
title: Guida alla distribuzione-cloud connected HoloLens 2 distribuzione in scala con assistenza remota-configura
description: Come configurare le configurazioni per la registrazione dei dispositivi HoloLens tramite una rete connessa al cloud
keywords: HoloLens, gestione, cloud connected, Remote Assist, AAD, Azure AD, MDM, gestione di dispositivi mobili
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196323"
---
# Configura-Guida connessa al cloud

In questa sezione della Guida&#39;verrà illustrato come configurare la registrazione automatica per il tenant e come applicare le licenze sia per Intune che per assistenza remota.

## Utenti e gruppi di Azure

Azure e Intune da tale estensione usano utenti e gruppi per consentire l'assegnazione di configurazioni e licenze. Per la convalida di questo flusso di distribuzione e la possibilità di effettuare una chiamata di assistenza remota da un utente a un altro, è&#39;necessario avere 2 account utente.

Possiamo creare un singolo gruppo di utenti allo scopo di assegnare licenze. Possiamo unire entrambi gli utenti allo stesso gruppo e applicare una licenza per Intune e assistenza remota a tale gruppo.

Se Don&#39;t ha già accesso a due account AAD in un gruppo di utenti che è possibile usare; Ecco le guide introduttive per:

- [Come creare un utente](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Come creare un gruppo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Aggiungere utenti a un gruppo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) : aggiungere utenti creati per creare un gruppo
- [Configurare AAD per consentire a un gruppo di utenti di accedere ai dispositivi](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) : verificare che il nuovo gruppo di utenti disponga delle autorizzazioni per la registrazione di dispositivi su AAD

## Registrazione automatica su HoloLens 2

Per avere un'esperienza uniforme e fluida, è possibile usare la configurazione di Azure Active Directory join (AADJ) e la registrazione automatica a Intune per i dispositivi HoloLens 2. In questo modo gli utenti potranno semplicemente immettere le credenziali di accesso dell'organizzazione durante la configurazione guidata e registrarsi automaticamente con AAD e registrare il dispositivo in MDM.

Usando [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home) possiamo selezionare i servizi e navigare in poche pagine fino a quando non potremo selezionare Ottieni una versione di valutazione Premium. È molto importante notare che in Azure Active Directory Premium 1 e 2 è sufficiente la registrazione automatica P1. Siamo in grado di selezionare Intune e selezionare l'ambito utente per la registrazione automatica e selezionare il gruppo creato in precedenza.

Per informazioni complete e passaggi, leggere la guida su [come abilitare la registrazione automatica per Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## Licenze per le applicazioni

Una licenza per l'applicazione consente a un utente di installare le app acquistate dalla società o di eseguire l'aggiornamento da una versione di valutazione gratuita a quella completa di un'app. Le licenze per le applicazioni possono essere applicate a utenti, gruppi di utenti o gruppi di dispositivi. Per gli utenti dell'organizzazione, è&#39;necessario usare le licenze remote assist. Ai fini della presente guida verrà assegnata una licenza per l'assistenza remota al gruppo di utenti creato in precedenza in [Azure Users and groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).

I requisiti per le licenze possono variare a seconda che l'utente effettui la chiamata assistita remota da un dispositivo o sia un collaboratore remoto di Microsoft teams. Per impostazione predefinita, le caselle di controllo Remote assist e teams sono entrambe contrassegnate. Per gli scopi di questa guida, consigliamo di uscire dalle caselle predefinite selezionate.

1. Leggi altre informazioni sui diversi [requisiti di licenza e prodotto per ogni ruolo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Esistono diversi tipi di licenze remote Assist, quindi assicurati di ottenere quelle corrette per le tue esigenze.
2. È&#39;necessario [acquisire la licenza](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Applicare le licenze](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) al gruppo.

## Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud-distribuzione](hololens2-cloud-connected-deploy.md)