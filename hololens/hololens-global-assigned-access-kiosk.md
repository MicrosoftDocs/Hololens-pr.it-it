---
title: Accesso assegnato globale
description: Introduzione alla guida all'uso dell'URI OMA per i chioschi di accesso assegnati a livello globale con Intune e Progettazione configurazione Windows.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, accesso assegnato, chiosco multimediale
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640424"
---
# <a name="global-assigned-access--kiosk"></a>Accesso assegnato globale - Chiosco multimediale

Questa funzionalità configura un dispositivo HoloLens 2 modalità tutto schermo per più app, applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che a loro volta apportare l'accesso al dispositivo.

> [!NOTE]
> Questa funzionalità è attualmente disponibile solo nelle build Windows Insider. Se si vuole provare questa funzionalità prima che sia disponibile a livello generale nelle versioni HoloLens, leggere altre informazioni Windows [Insider.](hololens-insider.md)

## <a name="how-to-use-global-assigned-access-in-intune"></a>Come usare l'accesso assegnato globale in Intune?

> [!NOTE]
> Tenere presenti le aree contrassegnate con "<!-". Per queste aree sarà necessario apportare modifiche in base alle preferenze.

1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato come indicato di seguito e applicarlo HoloLens gruppo di dispositivi:

    Valore URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![URI OMA dell'accesso assegnato globale in Intune](images/global-assigned-access-omauri.png)

2. Per value, aggiornare e incollare il contenuto seguente:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Come usare l'accesso assegnato globale in Progettazione Windows configurazione?

1. Aggiornare e salvare il BLOB XML indicato in precedenza come file XML. 

2. Seguire la procedura descritta in [Usare un pacchetto di provisioning](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)per configurare una singola app o più app in modalità tutto schermo, in particolare la sezione "Prov. pacchetto, passaggio 2: aggiungere il file XML di configurazione della modalità tutto schermo a un pacchetto di provisioning" e fare riferimento al file XML salvato nel passaggio precedente.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>È possibile creare una configurazione in cui globale si applica a tutti e una configurazione separata si applica a 1 Azure AD account o Azure AD gruppo? 

Sì, fare riferimento all'esempio di BLOB XML riportato di seguito. Il profilo di accesso assegnato globale viene applicato HoloLens quando non viene trovato uno specifico per l'utente connesso, quindi è la configurazione predefinita della modalità tutto schermo per l'utente connesso.
Di seguito è riportato un esempio di BLOB XML da usare:

> [!NOTE]
> Tenere presenti le aree evidenziate contrassegnate con `<!-` . Per queste aree sarà necessario apportare modifiche in base alle preferenze.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Esclusione di DeviceOwners dal profilo di accesso assegnato globale

Questa funzionalità consente a un utente considerato["Proprietario](security-adminless-os.md)del dispositivo" HoloLens essere escluso dall'accesso assegnato globale. Per sfruttare i vantaggi di questa funzionalità, nel BLOB XML per la configurazione della modalità tutto schermo con più app verificare che siano state aggiunte righe evidenziate:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Altri esempi di accesso assegnato a livello globale

Questo è un esempio di accesso assegnato globale in modalità tutto schermo che, quando un utente esegue l'accesso, avrà un chiosco multimediale con più app con l'app Impostazioni, Hub di Feedback e Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Questo esempio è un chiosco multimediale con accesso assegnato globale che esclude il proprietario del dispositivo, quando un altro utente di Azure AD esegue l'accesso avrà un chiosco multimediale con più app con app Impostazioni, Hub di Feedback e Microsoft Edge. Questo chiosco multimediale include anche una configurazione secondaria per chiosco multimediale per un account Visitatore, che può essere connesso da chiunque nella schermata di blocco. Quando un utente accede all'account Visitor, avrà un chiosco multimediale con più app che include solo l Hub di Feedback app.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
