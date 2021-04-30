---
title: Condividere HoloLens con più persone
description: È possibile configurare HoloLens in modo che sia condiviso da più Azure Active Directory o da più utenti che usano un singolo account.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309547"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="68914-103">Condividere HoloLens con più persone</span><span class="sxs-lookup"><span data-stu-id="68914-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="68914-104">È comune condividere un dispositivo HoloLens con molte persone o avere molte persone che condividono un set di dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="68914-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="68914-105">Questo articolo descrive i diversi modi in cui è possibile condividere un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68914-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="68914-106">Condividere con più persone, ognuna con il proprio account</span><span class="sxs-lookup"><span data-stu-id="68914-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="68914-107">**Prerequisito:** il dispositivo HoloLens deve eseguire Windows 10 versione 1803 o successiva.</span><span class="sxs-lookup"><span data-stu-id="68914-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="68914-108">È anche necessario aggiornare HoloLens (prima generazione) [a Windows Holographic for Business](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="68914-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="68914-109">Quando usano i propri account Azure Active Directory (Azure AD), più utenti possono mantenere le proprie impostazioni utente e i dati utente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68914-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="68914-110">Per assicurarsi che più utenti possano usare i propri account in HoloLens, seguire questa procedura per configurarlo:</span><span class="sxs-lookup"><span data-stu-id="68914-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="68914-111">Assicurarsi che il dispositivo sia in esecuzione Windows 10 versione 1803 o successiva.</span><span class="sxs-lookup"><span data-stu-id="68914-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="68914-112">Se si usa un dispositivo HoloLens (prima generazione), aggiornare il dispositivo a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="68914-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="68914-113">Quando si configura il dispositivo, selezionare **My work or school owns it** and sign in by an Azure AD account .</span><span class="sxs-lookup"><span data-stu-id="68914-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="68914-114">Al termine dell'installazione, assicurarsi che le impostazioni dell'account (**Account**  >  **impostazioni**) includa **Altri utenti**.</span><span class="sxs-lookup"><span data-stu-id="68914-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="68914-115">Per usare HoloLens, ogni utente segue questa procedura:</span><span class="sxs-lookup"><span data-stu-id="68914-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="68914-116">Se il dispositivo è stato utilizzato da un altro utente, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="68914-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="68914-117">Premere una volta il pulsante di alimentazione per passare alla modalità standby, quindi premere di nuovo il pulsante di alimentazione per tornare alla schermata di blocco</span><span class="sxs-lookup"><span data-stu-id="68914-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="68914-118">HoloLens 2 utenti possono selezionare il riquadro utente dal menu Start per disconnettere l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="68914-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="68914-119">Usare le Azure AD dell'account per accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68914-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="68914-120">Se è la prima volta che si usa il dispositivo, è necessario [calibrare](hololens-calibration.md) HoloLens in base ai propri occhi.</span><span class="sxs-lookup"><span data-stu-id="68914-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="68914-121">Per visualizzare un elenco degli utenti del dispositivo o per rimuovere un utente dal dispositivo, passare a **Impostazioni**  >  **Account**  >  **Altri utenti.**</span><span class="sxs-lookup"><span data-stu-id="68914-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="68914-122">Condividere con più utenti, tutti usando lo stesso account</span><span class="sxs-lookup"><span data-stu-id="68914-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="68914-123">Più utenti possono anche condividere un dispositivo HoloLens usando un singolo account utente.</span><span class="sxs-lookup"><span data-stu-id="68914-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="68914-124">**In HoloLens 2**, quando un nuovo utente mette il dispositivo in testa per la prima volta (mantenendo lo stesso account connesso), il dispositivo richiede al nuovo utente di calibrare e personalizzare rapidamente l'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="68914-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="68914-125">Il dispositivo può archiviare le informazioni di calibrazione in modo che in futuro il dispositivo possa ottimizzare automaticamente la qualità e il comfort dell'esperienza di visualizzazione di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="68914-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="68914-126">Gli utenti non devono calibrare nuovamente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68914-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="68914-127">**In HoloLens (prima generazione)** gli utenti che condividono un account dovranno chiedere di eseguire la ricalibrazione nell'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="68914-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="68914-128">Altre informazioni sulla [calibrazione.](hololens-calibration.md)</span><span class="sxs-lookup"><span data-stu-id="68914-128">Read more about [calibration](hololens-calibration.md).</span></span>
