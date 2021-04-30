---
title: Guida alla distribuzione - Distribuzione di applicazioni HoloLens 2 cloud su larga scala con Remote Assist - Configurare
description: Informazioni su come configurare le configurazioni per registrare i dispositivi HoloLens su una rete connessa al cloud su larga scala con Remote Assist.
keywords: HoloLens, gestione, connessa al cloud, Remote Assist, AAD, Azure AD, MDM, gestione dei dispositivi mobili
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309362"
---
# <a name="configure---cloud-connected-guide"></a>Configurare - Guida alla connessione al cloud

In questa sezione della guida verrà illustrato&#39;come configurare la registrazione automatica per il tenant e come applicare le licenze sia per Intune che per Remote Assist.

## <a name="azure-users-and-groups"></a>Utenti e gruppi di Azure

Azure e Intune con tale estensione, usa utenti e gruppi per assegnare configurazioni e licenze. Ai fini della convalida di questo flusso di distribuzione e della possibilità di effettuare una chiamata Remote Assist da un utente a un altro,&#39;saranno necessari due account utente.

È possibile creare un singolo gruppo di utenti allo scopo di assegnare le licenze. È possibile aggiungere entrambi gli utenti allo stesso gruppo e applicare una licenza per Intune Remote Assist a tale gruppo.

Se non si&#39;avere già accesso a due account Azure AD in un gruppo di utenti, è possibile usare . Ecco le guide introduttive per:

- [Come creare un utente](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Come creare un gruppo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Aggiungere utenti a un gruppo:](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) aggiungere gli utenti creati per creare un gruppo
- [Configurare Azure AD per consentire a un gruppo di utenti di](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) aggiungere dispositivi: assicurarsi che il nuovo gruppo di utenti abbia l'autorizzazione per registrare i dispositivi Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Registrazione automatica in HoloLens 2

Per un'esperienza uniforme e senza problemi, è possibile configurare Azure Active Directory Join (AADJ) e la registrazione automatica in Intune per i dispositivi HoloLens 2. In questo modo gli utenti potranno immettere le credenziali di accesso dell'organizzazione durante la Configurazione automatica del sistema operativo e registrarsi automaticamente con Azure AD e registrare il dispositivo in MDM.

Usando [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), è possibile selezionare i servizi ed esplorare alcune pagine fino a quando non è possibile selezionare Ottieni una versione di valutazione Premium. È possibile notare che non è Azure Active Directory Premium 1 e 2, per la registrazione automatica P1 è sufficiente. È possibile selezionare Intune, selezionare l'ambito utente per la registrazione automatica e selezionare il gruppo creato in precedenza.

Per informazioni dettagliate e passaggi completi, vedere la guida [su come abilitare la registrazione automatica per Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Licenze dell'applicazione

Una licenza dell'applicazione consente a un utente di installare le app acquistate dall'azienda o di eseguire l'aggiornamento da una versione di valutazione gratuita alla versione completa di un'app. Le licenze dell'applicazione possono essere applicate a utenti, gruppi di utenti o gruppi di dispositivi. È&#39;necessarie licenze Remote Assist per consentire agli utenti dell'organizzazione di usare Remote Assist. Ai fini di questa guida verranno assegnate Remote Assist licenze al gruppo di utenti creato in precedenza in Utenti e gruppi [di Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

I requisiti per le licenze possono essere diversi a seconda che l'utente chiami Remote Assist da un dispositivo o sia un collaboratore remoto di Microsoft Teams. Per impostazione predefinita, le caselle Remote Assist e Teams sono entrambe contrassegnate. Ai fini di questa guida, è consigliabile lasciare selezionate le caselle predefinite.

1. Altre informazioni sui diversi requisiti [di licenza e prodotto per ogni ruolo.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Esistono diversi tipi di licenze Remote Assist, quindi assicurarsi di ottenere quelle corrette per le proprie esigenze.
2. È&#39;necessario acquisire [la licenza](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Applicare le licenze](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) al gruppo.

## <a name="next-step"></a>Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud - Distribuire](hololens2-cloud-connected-deploy.md)