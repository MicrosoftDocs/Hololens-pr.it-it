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
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="4ceed-104">Accesso assegnato globale - Chiosco multimediale</span><span class="sxs-lookup"><span data-stu-id="4ceed-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="4ceed-105">Questa funzionalità configura un dispositivo HoloLens 2 modalità tutto schermo per più app, applicabile a livello di sistema, non ha affinità con alcuna identità nel sistema e si applica a tutti gli utenti che a loro volta apportare l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ceed-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="4ceed-106">Questa funzionalità è attualmente disponibile solo nelle build Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="4ceed-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="4ceed-107">Se si vuole provare questa funzionalità prima che sia disponibile a livello generale nelle versioni HoloLens, leggere altre informazioni Windows [Insider.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="4ceed-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="4ceed-108">Come usare l'accesso assegnato globale in Intune?</span><span class="sxs-lookup"><span data-stu-id="4ceed-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="4ceed-109">Tenere presenti le aree contrassegnate con "<!-".</span><span class="sxs-lookup"><span data-stu-id="4ceed-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="4ceed-110">Per queste aree sarà necessario apportare modifiche in base alle preferenze.</span><span class="sxs-lookup"><span data-stu-id="4ceed-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="4ceed-111">Creare un profilo di configurazione del dispositivo URI OMA personalizzato come indicato di seguito e applicarlo HoloLens gruppo di dispositivi:</span><span class="sxs-lookup"><span data-stu-id="4ceed-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="4ceed-112">Valore URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="4ceed-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4ceed-113">![URI OMA dell'accesso assegnato globale in Intune](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="4ceed-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="4ceed-114">Per value, aggiornare e incollare il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="4ceed-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="4ceed-115">Come usare l'accesso assegnato globale in Progettazione Windows configurazione?</span><span class="sxs-lookup"><span data-stu-id="4ceed-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="4ceed-116">Aggiornare e salvare il BLOB XML indicato in precedenza come file XML.</span><span class="sxs-lookup"><span data-stu-id="4ceed-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="4ceed-117">Seguire la procedura descritta in [Usare un pacchetto di provisioning](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)per configurare una singola app o più app in modalità tutto schermo, in particolare la sezione "Prov.</span><span class="sxs-lookup"><span data-stu-id="4ceed-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="4ceed-118">pacchetto, passaggio 2: aggiungere il file XML di configurazione della modalità tutto schermo a un pacchetto di provisioning" e fare riferimento al file XML salvato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="4ceed-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="4ceed-119">È possibile creare una configurazione in cui globale si applica a tutti e una configurazione separata si applica a 1 Azure AD account o Azure AD gruppo?</span><span class="sxs-lookup"><span data-stu-id="4ceed-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="4ceed-120">Sì, fare riferimento all'esempio di BLOB XML riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4ceed-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="4ceed-121">Il profilo di accesso assegnato globale viene applicato HoloLens quando non viene trovato uno specifico per l'utente connesso, quindi è la configurazione predefinita della modalità tutto schermo per l'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="4ceed-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="4ceed-122">Di seguito è riportato un esempio di BLOB XML da usare:</span><span class="sxs-lookup"><span data-stu-id="4ceed-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="4ceed-123">Tenere presenti le aree evidenziate contrassegnate con `<!-` .</span><span class="sxs-lookup"><span data-stu-id="4ceed-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="4ceed-124">Per queste aree sarà necessario apportare modifiche in base alle preferenze.</span><span class="sxs-lookup"><span data-stu-id="4ceed-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="4ceed-125">Esclusione di DeviceOwners dal profilo di accesso assegnato globale</span><span class="sxs-lookup"><span data-stu-id="4ceed-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="4ceed-126">Questa funzionalità consente a un utente considerato["Proprietario](security-adminless-os.md)del dispositivo" HoloLens essere escluso dall'accesso assegnato globale.</span><span class="sxs-lookup"><span data-stu-id="4ceed-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="4ceed-127">Per sfruttare i vantaggi di questa funzionalità, nel BLOB XML per la configurazione della modalità tutto schermo con più app verificare che siano state aggiunte righe evidenziate:</span><span class="sxs-lookup"><span data-stu-id="4ceed-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="4ceed-128">Altri esempi di accesso assegnato a livello globale</span><span class="sxs-lookup"><span data-stu-id="4ceed-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="4ceed-129">Questo è un esempio di accesso assegnato globale in modalità tutto schermo che, quando un utente esegue l'accesso, avrà un chiosco multimediale con più app con l'app Impostazioni, Hub di Feedback e Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="4ceed-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="4ceed-130">Questo esempio è un chiosco multimediale con accesso assegnato globale che esclude il proprietario del dispositivo, quando un altro utente di Azure AD esegue l'accesso avrà un chiosco multimediale con più app con app Impostazioni, Hub di Feedback e Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="4ceed-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="4ceed-131">Questo chiosco multimediale include anche una configurazione secondaria per chiosco multimediale per un account Visitatore, che può essere connesso da chiunque nella schermata di blocco.</span><span class="sxs-lookup"><span data-stu-id="4ceed-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="4ceed-132">Quando un utente accede all'account Visitor, avrà un chiosco multimediale con più app che include solo l Hub di Feedback app.</span><span class="sxs-lookup"><span data-stu-id="4ceed-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
