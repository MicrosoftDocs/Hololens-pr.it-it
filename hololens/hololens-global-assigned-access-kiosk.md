---
title: Accesso assegnato globale
description: Guida all'uso di URI OMA per chioschi di Accesso assegnato globale
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
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253203"
---
# <span data-ttu-id="63305-104">Accesso assegnato globale: chiosco</span><span class="sxs-lookup"><span data-stu-id="63305-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="63305-105">Questa caratteristica configura il dispositivo HoloLens 2 per la modalità Kiosk di più app, che è applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che accedono al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="63305-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="63305-106">Questa caratteristica è attualmente disponibile solo nelle build Insider di Windows.</span><span class="sxs-lookup"><span data-stu-id="63305-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="63305-107">Se si vuole provare questa caratteristica prima di essere generalmente disponibile nelle versioni di HoloLens, vedere altre informazioni sulle build [Insider di Windows](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="63305-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <span data-ttu-id="63305-108">Come usare l'accesso assegnato globale in Intune?</span><span class="sxs-lookup"><span data-stu-id="63305-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="63305-109">Prestare attenzione alle aree contrassegnate con "<!-".</span><span class="sxs-lookup"><span data-stu-id="63305-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="63305-110">In queste aree sarà necessario apportare modifiche in base alle proprie preferenze.</span><span class="sxs-lookup"><span data-stu-id="63305-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="63305-111">Creare un profilo di configurazione del dispositivo URI OMA personalizzato come descritto di seguito e applicarlo al gruppo di dispositivi HoloLens:</span><span class="sxs-lookup"><span data-stu-id="63305-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="63305-112">Valore URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="63305-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > ![URI OMA con accesso assegnato globale a Intune](images/global-assigned-access-omauri.png)

2. <span data-ttu-id="63305-114">Per il valore, aggiornare e incollare il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="63305-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="63305-115">Come usare l'accesso assegnato globale in Progettazione configurazione di Windows?</span><span class="sxs-lookup"><span data-stu-id="63305-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="63305-116">Eseguire l'aggiornamento e il salvataggio del BLOB XML come accennato in precedenza in formato XML.</span><span class="sxs-lookup"><span data-stu-id="63305-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="63305-117">Seguire la procedura descritta in [Uso di un pacchetto di provisioning per la configurazione di un chiosco multimediale con una o più app](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) e in particolare la sezione "Pacchetto di provisioning,</span><span class="sxs-lookup"><span data-stu-id="63305-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="63305-118">passaggio 2: Aggiunta del file XML di configurazione del chiosco al pacchetto di provisioning” e fare riferimento al file XML salvato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="63305-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <span data-ttu-id="63305-119">È possibile creare una configurazione in cui l'accesso assegnato globale si applica a tutti e la configurazione separata si applica a un account Azure AD o un gruppo di annunci Azure AD?</span><span class="sxs-lookup"><span data-stu-id="63305-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="63305-120">Sì, fare riferimento al BLOB XML di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="63305-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="63305-121">Il profilo di accesso assegnato globale viene applicato in HoloLens quando uno specifico per l'utente firmato non viene trovato, quindi è la configurazione della modalità Kiosk predefinita per l'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="63305-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="63305-122">Ecco un esempio di BLOB XML da usare:</span><span class="sxs-lookup"><span data-stu-id="63305-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="63305-123">Prestare attenzione alle aree evidenziate contrassegnate con `<!-`.</span><span class="sxs-lookup"><span data-stu-id="63305-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="63305-124">In queste aree sarà necessario apportare modifiche in base alle proprie preferenze.</span><span class="sxs-lookup"><span data-stu-id="63305-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="63305-125">Esclusione di DeviceOwners dal profilo di accesso assegnato globale</span><span class="sxs-lookup"><span data-stu-id="63305-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="63305-126">Questa funzionalità consente l'esclusione dall'accesso assegnato globale a un utente considerato "[proprietario del dispositivo](security-adminless-os.md)" in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="63305-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="63305-127">Per sfruttare questa funzionalità, nella configurazione BLOB XML per la configurazione di più app, verificare che le linee evidenziate vengano aggiunte:</span><span class="sxs-lookup"><span data-stu-id="63305-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <span data-ttu-id="63305-128">Altri esempi di accesso assegnato globale</span><span class="sxs-lookup"><span data-stu-id="63305-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="63305-129">Questo è un esempio di chiosco di accesso assegnato globale in cui un utente all’accesso avrà un chiosco con più app: app Impostazioni, Hub di feedback e Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="63305-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="63305-130">Questo è un esempio di chiosco di accesso assegnato globale con esclusione del proprietario del dispositivo, in cui qualsiasi altro utente AAD all’accesso avrà un chiosco con più app: app Impostazioni, Hub di feedback e Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="63305-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="63305-131">Questo chiosco include anche la configurazione di un chiosco secondario per un account visitatore, a cui può accedere chiunque dalla schermata di blocco.</span><span class="sxs-lookup"><span data-stu-id="63305-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="63305-132">Quando un utente accede all'account del visitatore, avrà un chiosco multi-app che include solo l'app Hub Feedback.</span><span class="sxs-lookup"><span data-stu-id="63305-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
