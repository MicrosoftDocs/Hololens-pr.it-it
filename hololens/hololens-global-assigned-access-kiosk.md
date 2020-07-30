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
# <span data-ttu-id="14ca9-104">Accesso assegnato globale: chiosco</span><span class="sxs-lookup"><span data-stu-id="14ca9-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="14ca9-105">Questa funzionalità consente di configurare il dispositivo Hololens 2 per la modalità chiosco di più app applicabile a livello di sistema, senza affinità con alcuna identità del sistema e si applica a tutti gli utenti che accedono al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14ca9-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="14ca9-106">Questa funzionalità è attualmente disponibile solo nelle build di Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="14ca9-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="14ca9-107">Se si vuole provare la funzionalità prima che sia generalmente disponile nei rilasci di HoloLens, leggere altre informazioni sulle build di [Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="14ca9-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="14ca9-108">Come usare la funzionalità in Intune</span><span class="sxs-lookup"><span data-stu-id="14ca9-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="14ca9-109">Prestare attenzione alle aree contrassegnate con "<!-".</span><span class="sxs-lookup"><span data-stu-id="14ca9-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="14ca9-110">In queste aree sarà necessario apportare modifiche in base alle proprie preferenze.</span><span class="sxs-lookup"><span data-stu-id="14ca9-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="14ca9-111">Creare un profilo di configurazione del dispositivo URI OMA personalizzato come descritto di seguito e applicarlo al gruppo di dispositivi HoloLens: ![Accesso assegnato globale URI OMA in Intune</span><span class="sxs-lookup"><span data-stu-id="14ca9-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="14ca9-112">Per il valore, aggiornare e incollare il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="14ca9-112">For value, update and paste following content:</span></span> 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="14ca9-113">Uso in Progettazione configurazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="14ca9-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="14ca9-114">Eseguire l'aggiornamento e il salvataggio del BLOB XML come accennato in precedenza in formato XML.</span><span class="sxs-lookup"><span data-stu-id="14ca9-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="14ca9-115">Seguire la procedura descritta in [Uso di un pacchetto di provisioning per la configurazione di un chiosco multimediale con una o più app](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) e in particolare la sezione "Pacchetto di provisioning,</span><span class="sxs-lookup"><span data-stu-id="14ca9-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="14ca9-116">passaggio 2: Aggiunta del file XML di configurazione del chiosco al pacchetto di provisioning” e fare riferimento al file XML salvato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="14ca9-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="14ca9-117">È possibile creare una configurazione in cui l’accesso globale si applica a tutti gli utenti, ad eccezione di 1 account AAD o un gruppo AAD?</span><span class="sxs-lookup"><span data-stu-id="14ca9-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="14ca9-118">Sì, consultare il BLOB XML di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14ca9-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="14ca9-119">Il profilo di accesso assegnato globale viene applicato a Hololens quando non ne viene trovato uno specifico per l'utente connesso. Si tratta quindi della configurazione predefinita della modalità chiosco per l’utente connesso.</span><span class="sxs-lookup"><span data-stu-id="14ca9-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="14ca9-120">Ecco un esempio di BLOB XML da usare:</span><span class="sxs-lookup"><span data-stu-id="14ca9-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="14ca9-121">Tenere presente le aree evidenziate contrassegnate con <!- poiché sarà necessario apportare modifiche in base alle proprie preferenze.</span><span class="sxs-lookup"><span data-stu-id="14ca9-121">Please be aware of the highlighted areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="14ca9-122">Esclusione di DeviceOwners dal profilo di accesso assegnato globale</span><span class="sxs-lookup"><span data-stu-id="14ca9-122">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="14ca9-123">Questa funzionalità consente a un utente a cui è stato assegnato il ruolo di "[Proprietario del dispositivo](security-adminless-os.md)" di Hololens di essere escluso dall'accesso assegnato globale.</span><span class="sxs-lookup"><span data-stu-id="14ca9-123">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on Hololens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="14ca9-124">Per sfruttare questa funzionalità, nella configurazione BLOB XML per la configurazione di più app, verificare che le linee evidenziate vengano aggiunte:</span><span class="sxs-lookup"><span data-stu-id="14ca9-124">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span> 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
