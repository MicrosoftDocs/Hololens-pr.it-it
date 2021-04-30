---
title: Istruzioni per il contributo
description: Informazioni su come contribuire alla documentazione di HoloLens nella piattaforma docs.microsoft.com usando Markdown in versione GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309218"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="e6b7e-103">Contribuire alla documentazione di HoloLens</span><span class="sxs-lookup"><span data-stu-id="e6b7e-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="e6b7e-104">Benvenuti nella documentazione [di HoloLens](https://github.com/MicrosoftDocs/Hololens).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="e6b7e-105">Tutti gli articoli creati o modificati in questo repo **saranno visibili al pubblico.**</span><span class="sxs-lookup"><span data-stu-id="e6b7e-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="e6b7e-106">I documenti di HoloLens vengono visualizzati nella piattaforma docs.microsoft.com, che usa Markdown basato su GitHub con le funzionalità markdig.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="e6b7e-107">Il contenuto modificato in questo repo viene formattato in pagine stilizzate che vengono mostrate in https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="e6b7e-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="e6b7e-108">Questa pagina illustra i passaggi di base e le linee guida per contribuire e i collegamenti alle nozioni di base di Markdown.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="e6b7e-109">Grazie per il tuo contributo.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="e6b7e-110">Repository disponibili</span><span class="sxs-lookup"><span data-stu-id="e6b7e-110">Available repos</span></span>

| <span data-ttu-id="e6b7e-111">Nome del repository</span><span class="sxs-lookup"><span data-stu-id="e6b7e-111">Repository name</span></span> | <span data-ttu-id="e6b7e-112">URL</span><span class="sxs-lookup"><span data-stu-id="e6b7e-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="e6b7e-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="e6b7e-113">HoloLens</span></span> | [<span data-ttu-id="e6b7e-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="e6b7e-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="e6b7e-115">Realtà mista</span><span class="sxs-lookup"><span data-stu-id="e6b7e-115">Mixed Reality</span></span> | [<span data-ttu-id="e6b7e-116">MicrosoftDocs/mixed-reality</span><span class="sxs-lookup"><span data-stu-id="e6b7e-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="e6b7e-117">Guida per gli appassionati di VR</span><span class="sxs-lookup"><span data-stu-id="e6b7e-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="e6b7e-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="e6b7e-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="e6b7e-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e6b7e-119">Before you start</span></span>

<span data-ttu-id="e6b7e-120">Se non è già presente, è necessario creare [un account GitHub.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="e6b7e-121">Se si è un dipendente Microsoft, collegare l'account GitHub all'alias Microsoft nel portale [Microsoft Open Source.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="e6b7e-122">Partecipare alle **organizzazioni "Microsoft"** **e "MicrosoftDocs".**</span><span class="sxs-lookup"><span data-stu-id="e6b7e-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="e6b7e-123">Quando si configura l'account GitHub, è consigliabile adottare anche queste precauzioni di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="e6b7e-124">Creare una [password complessa per l'account GitHub.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="e6b7e-125">Abilitare [l'autenticazione a due fattori.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="e6b7e-126">Salvare i [codici di ripristino](https://github.com/settings/auth/recovery-codes) in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="e6b7e-127">Aggiornare le [impostazioni del profilo pubblico](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="e6b7e-128">Impostare il nome e provare a impostare Indirizzo di posta *elettronica pubblico* su Non *visualizzare l'indirizzo di posta elettronica.*</span><span class="sxs-lookup"><span data-stu-id="e6b7e-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="e6b7e-129">È consigliabile caricare un'immagine del profilo perché viene visualizzata un'anteprima nelle pagine della documentazione a cui si contribuisce.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="e6b7e-130">Se si prevede di usare la riga di comando, è consigliabile [configurare Git Gestione credenziali per Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="e6b7e-131">In questo modo, non sarà necessario immettere la password ogni volta che si apporta un contributo.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="e6b7e-132">Il sistema di pubblicazione è associato a GitHub, quindi questi passaggi sono importanti.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="e6b7e-133">L'utente verrà elencato come autore o collaboratore per ogni articolo usando l'alias GitHub.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="e6b7e-134">Modifica di un articolo esistente</span><span class="sxs-lookup"><span data-stu-id="e6b7e-134">Editing an existing article</span></span>

<span data-ttu-id="e6b7e-135">Usare il flusso di lavoro seguente per apportare aggiornamenti *a un articolo* esistente tramite GitHub in un Web browser:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="e6b7e-136">Passare all'articolo che si vuole modificare nella cartella "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="e6b7e-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="e6b7e-137">Selezionare il pulsante di modifica (icona a forma di matita) in alto a destra, che crea automaticamente una copia di un ramo eliminabile dal ramo "master".</span><span class="sxs-lookup"><span data-stu-id="e6b7e-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Modificare un articolo.](images/editpage.png)
   
3. <span data-ttu-id="e6b7e-139">Modificare il contenuto dell'articolo in base alle ["nozioni di base su Markdown".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="e6b7e-140">Aggiornare i metadati all'inizio di ogni articolo:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="e6b7e-141">**title:** titolo della pagina visualizzato nella scheda del browser quando viene visualizzato l'articolo.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="e6b7e-142">I titoli di pagina vengono usati per seO e indicizzazione, quindi non modificare il titolo a meno che non sia necessario (anche se questo è meno importante prima che la documentazione venga pubblicata).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="e6b7e-143">**description:** scrivere una breve descrizione del contenuto dell'articolo, che migliora seO e individuazione.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="e6b7e-144">**author:** se si è il proprietario primario della pagina, aggiungere qui l'alias GitHub.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="e6b7e-145">**ms.author:** se si è il proprietario primario della pagina, aggiungere qui l'alias Microsoft (non è necessario , ma @microsoft.com solo l'alias).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="e6b7e-146">**ms.date:** aggiornare la data se si aggiunge contenuto principale alla pagina, ma non per correzioni come chiarimenti, formattazione, grammatica o ortografia.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="e6b7e-147">**keywords:** le parole chiave sono di aiuto in SEO (ottimizzazione del motore di ricerca).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="e6b7e-148">Aggiungere parole chiave, separate da una virgola e uno spazio, specifiche per l'articolo, ma senza punteggiatura dopo l'ultima parola chiave nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="e6b7e-149">Non è necessario aggiungere parole chiave globali che si applicano a tutti gli articoli, perché vengono gestite altrove.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="e6b7e-150">Dopo aver completato le modifiche all'articolo, scorrere verso il basso e selezionare **Proponi modifica file**.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="e6b7e-151">Nella pagina successiva selezionare Crea **richiesta pull per** unire il ramo creato automaticamente in "master".</span><span class="sxs-lookup"><span data-stu-id="e6b7e-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="e6b7e-152">Ripetere i passaggi precedenti per l'articolo successivo da modificare.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="e6b7e-153">Ridenominazione o eliminazione di un articolo esistente</span><span class="sxs-lookup"><span data-stu-id="e6b7e-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="e6b7e-154">Se la modifica rinomina o elimina un articolo esistente, assicurarsi di aggiungere un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="e6b7e-155">In questo modo, chiunque abbia un collegamento all'articolo esistente finirà comunque nel posto giusto.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="e6b7e-156">I reindirizzamenti vengono gestiti dal .openpublishing.redirection.jsfile nella radice del repo.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="e6b7e-157">Per aggiungere un reindirizzamento .openpublishing.redirection.js, aggiungere una voce alla `redirections` matrice:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="e6b7e-158">è `source_path` il percorso del repository relativo all'articolo precedente che si sta rimuovendo.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="e6b7e-159">Assicurarsi che il percorso inizi con `mixed-reality-docs` e termini con `.md` .</span><span class="sxs-lookup"><span data-stu-id="e6b7e-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="e6b7e-160">è `redirect_url` l'URL pubblico relativo dall'articolo precedente al nuovo articolo.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="e6b7e-161">Assicurarsi che questo URL non contenga o , perché fa riferimento **all'URL** pubblico `mixed-reality-docs` e non al percorso del `.md` repository.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="e6b7e-162">È consentito il collegamento a una sezione all'interno del nuovo articolo `#section` tramite .</span><span class="sxs-lookup"><span data-stu-id="e6b7e-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="e6b7e-163">Se necessario, è anche possibile usare un percorso assoluto per un altro sito.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="e6b7e-164">`redirect_document_id` indica se si vuole mantenere l'ID documento dal file precedente.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="e6b7e-165">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-165">The default is `false`.</span></span> <span data-ttu-id="e6b7e-166">Usare `true` se si vuole mantenere il valore `ms.documentid` dell'attributo dall'articolo reindirizzato.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="e6b7e-167">Se si mantiene l'ID documento, i dati, ad esempio le visualizzazioni pagina e le classificazioni, verranno trasferiti all'articolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="e6b7e-168">Eseguire questa operazione se il reindirizzamento è principalmente una ridenominazione e non un puntatore a un articolo diverso che copre solo parte dello stesso contenuto.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="e6b7e-169">Se si aggiunge un reindirizzamento, assicurarsi di eliminare anche il file precedente.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="e6b7e-170">Creazione di un nuovo articolo</span><span class="sxs-lookup"><span data-stu-id="e6b7e-170">Creating a new article</span></span>

<span data-ttu-id="e6b7e-171">Usare il flusso di lavoro *seguente per creare nuovi* articoli nel repository della documentazione tramite GitHub in un Web browser:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="e6b7e-172">Creare un fork dal ramo "master" Di MicrosoftDocs/realtà mista (usando il pulsante **Fork** in alto a destra).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Creare una copia con fork del ramo master.](images/forkbranch.png)
   
2. <span data-ttu-id="e6b7e-174">Nella cartella "mixed-reality-docs" selezionare **Crea nuovo file** in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="e6b7e-175">Creare un nome di pagina per l'articolo (usare trattini anziché spazi e non usare segni di punteggiatura o apostrofi) e aggiungere ".md"</span><span class="sxs-lookup"><span data-stu-id="e6b7e-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Assegnare un nome alla nuova pagina.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="e6b7e-177">Assicurarsi di creare il nuovo articolo dalla cartella "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="e6b7e-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="e6b7e-178">È possibile verificarlo controllando "/mixed-reality-docs/" nella nuova riga del nome file.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="e6b7e-179">Nella parte superiore della nuova pagina aggiungere il blocco di metadati seguente:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-179">At the top of your new page, add the following metadata block:</span></span>

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. <span data-ttu-id="e6b7e-180">Compilare i campi dei metadati pertinenti in base alle istruzioni nella [sezione precedente.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="e6b7e-181">Scrivere il contenuto dell'articolo [usando le nozioni di base di Markdown.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="e6b7e-182">Aggiungere una `## See also` sezione nella parte inferiore dell'articolo con collegamenti ad altri articoli pertinenti.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="e6b7e-183">Al termine, selezionare **Commit new file (Esegui commit nuovo file).**</span><span class="sxs-lookup"><span data-stu-id="e6b7e-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="e6b7e-184">Selezionare **Nuova richiesta pull** e unire il ramo 'master' del fork in MicrosoftDocs/mixed-reality 'master' (assicurarsi che la freccia sia rivolta nel modo corretto).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Creare una richiesta pull dal fork in MicrosoftDocs/realtà mista](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="e6b7e-186">Nozioni di base su Markdown</span><span class="sxs-lookup"><span data-stu-id="e6b7e-186">Markdown basics</span></span>

<span data-ttu-id="e6b7e-187">Le risorse seguenti consentono di imparare a modificare la documentazione usando il linguaggio Markdown:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="e6b7e-188">Informazioni di base su Markdown</span><span class="sxs-lookup"><span data-stu-id="e6b7e-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="e6b7e-189">Risorse aggiuntive per la scrittura di Markdown per docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e6b7e-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="e6b7e-190">Aggiunta di tabelle</span><span class="sxs-lookup"><span data-stu-id="e6b7e-190">Adding tables</span></span>

<span data-ttu-id="e6b7e-191">A causa del modo in cui docs.microsoft.com stili, non hanno bordi o stili personalizzati, anche se si prova css inline.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="e6b7e-192">Sembra funzionare per un breve periodo di tempo, ma alla fine la piattaforma rimuoverà lo stile dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="e6b7e-193">Pianificare in anticipo e mantenere le tabelle semplici.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="e6b7e-194">[Ecco un sito che semplifica le tabelle Markdown.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="e6b7e-195">[L'estensione Docs Markdown per Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) semplifica anche la generazione di tabelle se si usa Visual Studio Code (vedere di [seguito)](#using-visual-studio-code) per modificare la documentazione.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="e6b7e-196">Aggiunta di immagini</span><span class="sxs-lookup"><span data-stu-id="e6b7e-196">Adding images</span></span>

<span data-ttu-id="e6b7e-197">È necessario caricare le immagini nella cartella "mixed-reality-docs/images" nel repo e quindi fare riferimento alle immagini in modo appropriato nell'articolo.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="e6b7e-198">Le immagini verranno visualizzate automaticamente a dimensioni complete, ovvero le immagini di grandi dimensioni riempiranno l'intera larghezza dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="e6b7e-199">È consigliabile pre-ridimensionare le immagini prima di caricarle.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="e6b7e-200">La larghezza consigliata è compresa tra 600 e 700 pixel, anche se è consigliabile ridimensionare rispettivamente se si tratta di uno screenshot denso o di una frazione di uno screenshot.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e6b7e-201">È possibile caricare le immagini solo nel repo con fork prima dell'unione.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="e6b7e-202">Pertanto, se si prevede di aggiungere immagini a un articolo, è necessario usare [Visual Studio Code](#using-visual-studio-code) per aggiungere prima le immagini alla cartella "images" del fork o assicurarsi di aver eseguito le operazioni seguenti in un Web browser:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="e6b7e-203">Fork del repo MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="e6b7e-204">L'articolo è stato modificato nel fork.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="e6b7e-205">Le immagini a cui si fa riferimento nell'articolo sono caricate nella cartella "mixed-reality-docs/images" nel fork.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="e6b7e-206">È stata **creata una richiesta pull** per unire il fork nel ramo MicrosoftDocs/mixed-reality 'master'.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="e6b7e-207">Per informazioni su come configurare il proprio repo con fork, seguire le istruzioni per [la creazione di un nuovo articolo.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="e6b7e-208">Anteprima del lavoro</span><span class="sxs-lookup"><span data-stu-id="e6b7e-208">Previewing your work</span></span>

<span data-ttu-id="e6b7e-209">Durante la modifica in GitHub tramite un Web browser, è possibile selezionare la scheda **Anteprima** nella parte superiore della pagina per visualizzare in anteprima il lavoro prima di eseguire il commit.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="e6b7e-210">La visualizzazione in anteprima delle modifiche review.docs.microsoft.com è disponibile solo per i dipendenti Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6b7e-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="e6b7e-211">Dipendenti Microsoft: dopo aver unito i contributi nel ramo "master", è possibile esaminare il contenuto prima che venga pubblicato all'indirizzo https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="e6b7e-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="e6b7e-212">Trovare l'articolo usando il sommario nella colonna sinistra.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="e6b7e-213">Modifica nel browser e modifica con un client desktop</span><span class="sxs-lookup"><span data-stu-id="e6b7e-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="e6b7e-214">La modifica nel browser è il modo più semplice per apportare modifiche rapide, ma esistono alcuni svantaggi:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="e6b7e-215">Il controllo ortografico non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-215">You don't get spell-check.</span></span>
- <span data-ttu-id="e6b7e-216">Non si ottiene alcun collegamento intelligente ad altri articoli (è necessario digitare manualmente il nome file dell'articolo).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="e6b7e-217">Può essere un'insidola per caricare e fare riferimento alle immagini.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="e6b7e-218">Se si preferisce non gestire questi problemi, usare un client desktop come [Visual Studio Code](https://code.visualstudio.com/) con un paio [di estensioni utili](#useful-extensions) per contribuire.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="e6b7e-219">Uso di Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e6b7e-219">Using Visual Studio Code</span></span>

<span data-ttu-id="e6b7e-220">Per i motivi [elencati in](#editing-in-the-browser-vs-editing-with-a-desktop-client)precedenza, è preferibile usare un client desktop per modificare la documentazione anziché un Web browser.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="e6b7e-221">È consigliabile usare [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="e6b7e-222">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e6b7e-222">Setup</span></span>

<span data-ttu-id="e6b7e-223">Seguire questa procedura per configurare Visual Studio Code per l'utilizzo di questo repo:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="e6b7e-224">In un Web browser:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-224">In a web browser:</span></span>
    1. <span data-ttu-id="e6b7e-225">Installare [Git per il PC.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="e6b7e-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="e6b7e-226">Installare [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="e6b7e-227">[Creare una fork di MicrosoftDocs/realtà mista,](#creating-a-new-article) se non è già stato fatto.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="e6b7e-228">Nel fork selezionare **Clona o scarica e** copiare l'URL.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="e6b7e-229">Creare un clone locale del fork in Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="e6b7e-230">Scegliere **Riquadro comandi** dal menu **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="e6b7e-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="e6b7e-231">Digitare "Git: Clone".</span><span class="sxs-lookup"><span data-stu-id="e6b7e-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="e6b7e-232">Incollare l'URL copiato.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="e6b7e-233">Scegliere dove salvare il clone nel PC.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="e6b7e-234">Selezionare **Apri il repo** nel popup.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="e6b7e-235">Documentazione di modifica</span><span class="sxs-lookup"><span data-stu-id="e6b7e-235">Editing documentation</span></span>

<span data-ttu-id="e6b7e-236">Usare il flusso di lavoro seguente per apportare modifiche alla documentazione con Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="e6b7e-237">Tutte le linee [](#creating-a-new-article) guida per [la modifica](#editing-an-existing-article) e la creazione di articoli e le nozioni di base sulla modifica di [Markdown](#markdown-basics)da sopra si applicano anche quando si usa Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="e6b7e-238">Assicurarsi che il fork clonato sia aggiornato con il repo ufficiale.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="e6b7e-239">In un Web browser creare una richiesta pull per sincronizzare le modifiche recenti da altri collaboratori in MicrosoftDocs/mixed-reality 'master' al fork (assicurarsi che la freccia sia rivolta nel modo giusto).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Sincronizzare le modifiche da MicrosoftDocs/mixed-reality al fork](images/sync-repos.png)
      
   2. <span data-ttu-id="e6b7e-241">In Visual Studio Code selezionare il pulsante sincronizza per sincronizzare il fork appena aggiornato con il clone locale.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Fare clic sull'immagine del pulsante di sincronizzazione](images/sync-clone.png)
      
2. <span data-ttu-id="e6b7e-243">Creare o modificare articoli nel repo clonato usando Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="e6b7e-244">Modificare uno o più articoli (aggiungere immagini alla cartella "images", se necessario).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="e6b7e-245">**Salvare** le modifiche in **Esplora risorse**.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-245">**Save** changes in **Explorer**.</span></span>
      
      ![Scegliere "Salva tutto" in Esplora risorse](images/explorer-save.png)
      
   3. <span data-ttu-id="e6b7e-247">**Eseguire il commit di** tutte **le modifiche nel** controllo del codice sorgente (scrivere un messaggio di commit quando richiesto).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Scegliere "Commit all" nel controllo del codice sorgente](images/source-control-commit.png)
      
   4. <span data-ttu-id="e6b7e-249">Selezionare il **pulsante sincronizza** per sincronizzare le modifiche all'origine (fork in GitHub).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Fare clic sul pulsante di sincronizzazione](images/sync-back.png)
      
3. <span data-ttu-id="e6b7e-251">In un Web browser creare una richiesta pull per sincronizzare le nuove modifiche nel fork con MicrosoftDocs/mixed-reality 'master' (assicurarsi che la freccia sia rivolta nel modo corretto).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Creare una richiesta pull dal fork in MicrosoftDocs/realtà mista](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="e6b7e-253">Estensioni utili</span><span class="sxs-lookup"><span data-stu-id="e6b7e-253">Useful extensions</span></span>

<span data-ttu-id="e6b7e-254">Le estensioni Visual Studio Code seguenti sono utili quando si modifica la documentazione:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="e6b7e-255">[Estensione Docs Markdown per Visual Studio Code:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) usare **ALT+M** per visualizzare un menu di opzioni di creazione di documenti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e6b7e-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="e6b7e-256">Cercare e fare riferimento alle immagini caricate.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="e6b7e-257">Aggiungere formattazione come elenchi, tabelle e call-out specifici della documentazione, ad esempio `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="e6b7e-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="e6b7e-258">Cercare e fare riferimento a collegamenti e segnalibri interni (collegamenti a sezioni specifiche all'interno di una pagina).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="e6b7e-259">Gli errori di formattazione sono evidenziati (passare il puntatore del mouse sull'errore per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="e6b7e-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="e6b7e-260">[Controllo ortografico del codice:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) le parole con errori di ortografia verranno sottolineate; Fare clic con il pulsante destro del mouse su una parola con errori di ortografia per modificarla o salvarla nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="e6b7e-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
