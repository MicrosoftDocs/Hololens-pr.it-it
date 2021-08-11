---
title: Accesso assegnato globale
description: Introduzione alla guida all'uso di OMA-URI per i chioschi in modalità tutto schermo con Intune e Progettazione configurazione windows.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, accesso assegnato, tutto schermo
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d36192e7f65f7fe2ccc7ff8699484a19b3d5d3a7ccab0167d2dbdcaf64bb5880
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664029"
---
# <a name="global-assigned-access--kiosk"></a>Accesso assegnato globale - Tutto schermo

Questa funzionalità configura il dispositivo HoloLens 2 modalità tutto schermo per più app, applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che a loro volta apportare l'accesso al dispositivo.

> [!NOTE]
> Questa funzionalità è attualmente disponibile solo nelle Windows Insider. Se si vuole provare questa funzionalità prima che sia disponibile a livello generale nelle versioni HoloLens, leggere altre informazioni sulle build insider Windows [Insider.](hololens-insider.md)

## <a name="how-to-use-global-assigned-access-in-intune"></a>Come usare l'accesso assegnato globale in Intune?

> [!NOTE]
> Tenere presenti le aree contrassegnate con "<!-". Queste aree richiedono di apportare modifiche in base alle preferenze.

1. Creare un profilo di configurazione del dispositivo URI OMA personalizzato come indicato di seguito e applicarlo HoloLens gruppo di dispositivi:

    Valore URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![URI OMA per l'accesso assegnato globale in Intune](images/global-assigned-access-omauri.png)

2. Per value, aggiornare e incollare il contenuto seguente:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Come usare l'accesso assegnato globale in Windows Configuration Designer?

1. Aggiornare e salvare il BLOB XML indicato in precedenza come file XML. 

2. Seguire la procedura descritta in Usare un pacchetto di provisioning per configurare un'app singola o [multi-app](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)in modalità tutto schermo, in particolare la sezione "Prov. pacchetto, passaggio 2: aggiungere il file XML di configurazione tutto schermo a un pacchetto di provisioning" e fare riferimento al file XML salvato nel passaggio precedente.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>È possibile creare una configurazione in cui globale si applica a tutti gli utenti e una configurazione separata si applica a 1 account Azure AD o Azure AD gruppo? 

Sì, fare riferimento al BLOB XML di esempio seguente. Il profilo di accesso assegnato globale viene applicato HoloLens quando non viene trovato uno specifico per l'utente connesso, quindi è la configurazione predefinita della modalità tutto schermo per l'utente connesso.
Ecco un esempio di BLOB XML da usare:

> [!NOTE]
> Tenere presenti le aree evidenziate contrassegnate con `<!-` . Queste aree richiedono di apportare modifiche in base alle preferenze.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Esclusione di DeviceOwners dal profilo di accesso assegnato globale

Questa funzionalità consente a un utente considerato "Proprietario[del](security-adminless-os.md)dispositivo" HoloLens di essere escluso dall'accesso assegnato globale. Per sfruttare questa funzionalità, nel BLOB XML per la configurazione in modalità tutto schermo per più app verificare che siano state aggiunte righe evidenziate:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Altri esempi di accesso assegnato globale

Si tratta di un esempio di chiosco multimediale Con accesso assegnato globale che, quando un utente accede, avrà un chiosco multimediale multi-app con app Impostazioni, Hub di Feedback e Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Questo esempio è un chiosco di accesso assegnato globale che esclude il proprietario del dispositivo, quando qualsiasi altro utente di Azure AD accede avrà un chiosco multimediale multi-app con app Impostazioni, Hub di Feedback e Microsoft Edge. Questo chiosco multimediale include anche una configurazione della modalità tutto schermo secondaria per un account Visitatore, che può essere eseguito l'accesso da parte di chiunque nella schermata di blocco. Quando un utente accede all'account Visitor, avrà un chiosco multimediale multi-app che include solo l'app Hub di Feedback app.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
