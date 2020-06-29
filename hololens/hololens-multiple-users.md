---
title: Condividi HoloLens con più persone
description: È possibile configurare HoloLens in modo che vengano condivisi da più account di Azure Active Directory o da più utenti che usano un singolo account.
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829287"
---
# <span data-ttu-id="c4190-103">Condividi HoloLens con più persone</span><span class="sxs-lookup"><span data-stu-id="c4190-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="c4190-104">È comune condividere un HoloLens con molte persone o avere molte persone che condividono un set di dispositivi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c4190-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="c4190-105">In questo articolo vengono illustrati i diversi modi in cui è possibile condividere un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4190-105">This article describes the different ways in which you can share a device.</span></span>

## <span data-ttu-id="c4190-106">Condividere con più persone, ognuno con il proprio account</span><span class="sxs-lookup"><span data-stu-id="c4190-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="c4190-107">**Prerequisito**: il dispositivo HoloLens deve eseguire Windows 10, versione 1803 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c4190-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="c4190-108">HoloLens (1a generazione) deve anche essere [aggiornato a Windows olografico for business](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c4190-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="c4190-109">Quando usano gli account di Azure Active Directory (Azure AD), più utenti possono conservare le proprie impostazioni utente e i dati degli utenti nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4190-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="c4190-110">Per assicurarsi che più persone possano usare i propri account in HoloLens, eseguire le operazioni seguenti per configurarlo:</span><span class="sxs-lookup"><span data-stu-id="c4190-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="c4190-111">Verificare che il dispositivo esegua Windows 10, versione 1803 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c4190-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="c4190-112">Se si usa un dispositivo HoloLens (1a Gen), [aggiornare il dispositivo a Windows olografico for business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c4190-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="c4190-113">Quando configuri il dispositivo, seleziona il **mio lavoro o l'Istituto di istruzione proprietario** ed Esegui l'accesso usando un account di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="c4190-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="c4190-114">Dopo aver completato la configurazione, verificare che le impostazioni dell'account (account**delle impostazioni**  >  **Accounts**) includano **altri utenti**.</span><span class="sxs-lookup"><span data-stu-id="c4190-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="c4190-115">Per usare HoloLens, ogni utente segue questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c4190-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="c4190-116">Se un altro utente usa il dispositivo, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4190-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="c4190-117">Premere una volta il pulsante di alimentazione per passare alla modalità standby e quindi premere di nuovo il pulsante di alimentazione per tornare alla schermata di blocco</span><span class="sxs-lookup"><span data-stu-id="c4190-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="c4190-118">HoloLens 2 gli utenti possono selezionare il riquadro utente dal menu Start per disconnettersi dall'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="c4190-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="c4190-119">Usa le credenziali dell'account Azure AD per accedere al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4190-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="c4190-120">Se è la prima volta che si usa il dispositivo, è necessario [calibrare](hololens-calibration.md) HoloLens con i propri occhi.</span><span class="sxs-lookup"><span data-stu-id="c4190-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="c4190-121">Per visualizzare un elenco degli utenti del dispositivo o per rimuovere un utente dal dispositivo, passa a account **delle impostazioni**di  >  **Accounts**  >  **altri utenti**.</span><span class="sxs-lookup"><span data-stu-id="c4190-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <span data-ttu-id="c4190-122">Condividere con più persone, usando lo stesso account</span><span class="sxs-lookup"><span data-stu-id="c4190-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="c4190-123">Più utenti possono anche condividere un dispositivo HoloLens durante l'uso di un singolo account utente.</span><span class="sxs-lookup"><span data-stu-id="c4190-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="c4190-124">**In HoloLens 2**, quando un nuovo utente mette il dispositivo in testa per la prima volta (mantenendo lo stesso account connesso), il dispositivo chiede al nuovo utente di calibrare e personalizzare rapidamente l'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4190-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="c4190-125">Il dispositivo può archiviare le informazioni di calibrazione in modo che in futuro il dispositivo possa ottimizzare automaticamente la qualità e il comfort dell'esperienza di visualizzazione di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="c4190-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="c4190-126">Gli utenti non devono calibrare di nuovo il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4190-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="c4190-127">In **HoloLens (1a generazione)** gli utenti che condividono un account dovranno chiedere di ricalibrare l'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c4190-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="c4190-128">Per altre informazioni, vedere [calibrazione](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="c4190-128">Read more about [calibration](hololens-calibration.md).</span></span>
