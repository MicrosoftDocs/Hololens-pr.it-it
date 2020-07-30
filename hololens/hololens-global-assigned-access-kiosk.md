---
title: Accesso assegnato globale
description: Guida all'uso di URI OMA per chioschi di Accesso assegnato globale
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, accesso assegnato, chiosco
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1a0a3eb8ef3d21b34e13711bcc890af57e5ae2c2
ms.sourcegitcommit: 7c16570839893f4a4432286b13ae6d84c665d376
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2020
ms.locfileid: "10902301"
---
# Accesso assegnato globale: chiosco

Questa funzionalità consente di configurare il dispositivo Hololens 2 per la modalità chiosco di più app applicabile a livello di sistema, senza affinità con alcuna identità del sistema e si applica a tutti gli utenti che accedono al dispositivo. 

> [!NOTE]
> Questa funzionalità è attualmente disponibile solo nelle build di Windows Insider. Se si vuole provare la funzionalità prima che sia generalmente disponile nei rilasci di HoloLens, leggere altre informazioni sulle build di [Windows Insider](hololens-insider.md).
 
## Come usare la funzionalità in Intune 

> [!NOTE]
> Prestare attenzione alle aree contrassegnate con "<!-". In queste aree sarà necessario apportare modifiche in base alle proprie preferenze. 

1.  Creare un profilo di configurazione del dispositivo URI OMA personalizzato come descritto di seguito e applicarlo al gruppo di dispositivi HoloLens: ![Accesso assegnato globale URI OMA in Intune](images/global-assigned-access-omauri.png)

2.  Per il valore, aggiornare e incollare il contenuto seguente: 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Uso in Progettazione configurazione di Windows. 
 
1.  Eseguire l'aggiornamento e il salvataggio del BLOB XML come accennato in precedenza in formato XML. 

2.  Seguire la procedura descritta in [Uso di un pacchetto di provisioning per la configurazione di un chiosco multimediale con una o più app](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) e in particolare la sezione "Pacchetto di provisioning, passaggio 2: Aggiunta del file XML di configurazione del chiosco al pacchetto di provisioning” e fare riferimento al file XML salvato nel passaggio precedente. 

## È possibile creare una configurazione in cui l’accesso globale si applica a tutti gli utenti, ad eccezione di 1 account AAD o un gruppo AAD? 

Sì, consultare il BLOB XML di esempio seguente. Il profilo di accesso assegnato globale viene applicato a Hololens quando non ne viene trovato uno specifico per l'utente connesso. Si tratta quindi della configurazione predefinita della modalità chiosco per l’utente connesso. Ecco un esempio di BLOB XML da usare: 

> [!NOTE]
> Tenere presente le aree evidenziate contrassegnate con <!- poiché sarà necessario apportare modifiche in base alle proprie preferenze. 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Esclusione di DeviceOwners dal profilo di accesso assegnato globale

Questa funzionalità consente a un utente a cui è stato assegnato il ruolo di "[Proprietario del dispositivo](security-adminless-os.md)" di Hololens di essere escluso dall'accesso assegnato globale. Per sfruttare questa funzionalità, nella configurazione BLOB XML per la configurazione di più app, verificare che le linee evidenziate vengano aggiunte: 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
