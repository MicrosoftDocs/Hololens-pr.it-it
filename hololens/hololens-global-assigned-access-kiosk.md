---
title: Accesso assegnato globale
description: Guida introduttiva all'uso di OMA-URI per chioschi di accesso assegnato globale con Intune e Progettazione configurazione di Windows.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, accesso assegnato, chiosco
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283177"
---
# Accesso assegnato globale: chiosco

Questa caratteristica configura il dispositivo HoloLens 2 per la modalità Kiosk di più app, che è applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che accedono al dispositivo.

> [!NOTE]
> Questa caratteristica è attualmente disponibile solo nelle build Insider di Windows. Se si vuole provare questa caratteristica prima di essere generalmente disponibile nelle versioni di HoloLens, vedere altre informazioni sulle build [Insider di Windows](hololens-insider.md).

## Come usare l'accesso assegnato globale in Intune?

> [!NOTE]
> Prestare attenzione alle aree contrassegnate con "<!-". In queste aree sarà necessario apportare modifiche in base alle proprie preferenze.

1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato come descritto di seguito e applicarlo al gruppo di dispositivi HoloLens:

    Valore URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![URI OMA con accesso assegnato globale a Intune](images/global-assigned-access-omauri.png)

2. Per il valore, aggiornare e incollare il contenuto seguente:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Come usare l'accesso assegnato globale in Progettazione configurazione di Windows?

1. Eseguire l'aggiornamento e il salvataggio del BLOB XML come accennato in precedenza in formato XML. 

2. Seguire la procedura descritta in [Uso di un pacchetto di provisioning per la configurazione di un chiosco multimediale con una o più app](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) e in particolare la sezione "Pacchetto di provisioning, passaggio 2: Aggiunta del file XML di configurazione del chiosco al pacchetto di provisioning” e fare riferimento al file XML salvato nel passaggio precedente.

## È possibile creare una configurazione in cui l'accesso assegnato globale si applica a tutti e la configurazione separata si applica a un account Azure AD o un gruppo di annunci Azure AD? 

Sì, fare riferimento al BLOB XML di esempio seguente. Il profilo di accesso assegnato globale viene applicato in HoloLens quando uno specifico per l'utente firmato non viene trovato, quindi è la configurazione della modalità Kiosk predefinita per l'utente connesso.
Ecco un esempio di BLOB XML da usare:

> [!NOTE]
> Prestare attenzione alle aree evidenziate contrassegnate con `<!-`. In queste aree sarà necessario apportare modifiche in base alle proprie preferenze.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Esclusione di DeviceOwners dal profilo di accesso assegnato globale

Questa funzionalità consente l'esclusione dall'accesso assegnato globale a un utente considerato "[proprietario del dispositivo](security-adminless-os.md)" in HoloLens. Per sfruttare questa funzionalità, nella configurazione BLOB XML per la configurazione di più app, verificare che le linee evidenziate vengano aggiunte:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## Altri esempi di accesso assegnato globale

Questo è un esempio di chiosco di accesso assegnato globale in cui un utente all’accesso avrà un chiosco con più app: app Impostazioni, Hub di feedback e Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Questo è un esempio di chiosco di accesso assegnato globale con esclusione del proprietario del dispositivo, in cui qualsiasi altro utente AAD all’accesso avrà un chiosco con più app: app Impostazioni, Hub di feedback e Microsoft Edge. Questo chiosco include anche la configurazione di un chiosco secondario per un account visitatore, a cui può accedere chiunque dalla schermata di blocco. Quando un utente accede all'account del visitatore, avrà un chiosco multi-app che include solo l'app Hub Feedback.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
