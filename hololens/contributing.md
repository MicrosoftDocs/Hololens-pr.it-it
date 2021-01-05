---
title: Istruzioni per il contributo
description: Informazioni su come contribuire alla documentazione di HoloLens nella piattaforma docs.microsoft.com usando GitHub-Flavored Markdown.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.openlocfilehash: d17d9e30ca3699a7bd6c69b75043c6974a2bde1f
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253655"
---
# <span data-ttu-id="faf99-103">Contribuire alla documentazione di HoloLens</span><span class="sxs-lookup"><span data-stu-id="faf99-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="faf99-104">Benvenuti nella [documentazione di HoloLens](https://github.com/MicrosoftDocs/Hololens).</span><span class="sxs-lookup"><span data-stu-id="faf99-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="faf99-105">Tutti gli articoli creati o modificati in questo repo **saranno visibili al pubblico.**</span><span class="sxs-lookup"><span data-stu-id="faf99-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="faf99-106">I documenti di HoloLens vengono visualizzati nella piattaforma docs.microsoft.com, che usa GitHub-Flavored Markdown con le caratteristiche di Markdig.</span><span class="sxs-lookup"><span data-stu-id="faf99-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="faf99-107">Il contenuto modificato in questo repo viene formattato in pagine stilizzate visualizzate https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="faf99-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="faf99-108">Questa pagina illustra i passaggi e le linee guida di base per il contributo e i collegamenti alle nozioni fondamentali su Markdown.</span><span class="sxs-lookup"><span data-stu-id="faf99-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="faf99-109">Grazie per il tuo contributo!</span><span class="sxs-lookup"><span data-stu-id="faf99-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="faf99-110">Pronti per le disponibilità</span><span class="sxs-lookup"><span data-stu-id="faf99-110">Available repos</span></span>

| <span data-ttu-id="faf99-111">Nome del repository</span><span class="sxs-lookup"><span data-stu-id="faf99-111">Repository name</span></span> | <span data-ttu-id="faf99-112">URL</span><span class="sxs-lookup"><span data-stu-id="faf99-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="faf99-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="faf99-113">HoloLens</span></span> | [<span data-ttu-id="faf99-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="faf99-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="faf99-115">Realtà mista</span><span class="sxs-lookup"><span data-stu-id="faf99-115">Mixed Reality</span></span> | [<span data-ttu-id="faf99-116">MicrosoftDocs/mixed-realtà</span><span class="sxs-lookup"><span data-stu-id="faf99-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="faf99-117">Guida per gli appassionati di VR</span><span class="sxs-lookup"><span data-stu-id="faf99-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="faf99-118">MicrosoftDocs/Mixed-Reality/appassionato-Guida</span><span class="sxs-lookup"><span data-stu-id="faf99-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="faf99-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="faf99-119">Before you start</span></span>

<span data-ttu-id="faf99-120">Se non è già disponibile, è necessario [creare un account github](https://github.com/join).</span><span class="sxs-lookup"><span data-stu-id="faf99-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="faf99-121">Se si è un dipendente Microsoft, collegare l'account di GitHub al proprio alias Microsoft nel [portale Open source Microsoft](https://repos.opensource.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="faf99-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="faf99-122">Partecipare alle organizzazioni " **Microsoft"** e **"MicrosoftDocs"** .</span><span class="sxs-lookup"><span data-stu-id="faf99-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="faf99-123">Quando si configura l'account di GitHub, è consigliabile attenersi alle seguenti precauzioni per la sicurezza:</span><span class="sxs-lookup"><span data-stu-id="faf99-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="faf99-124">Creare una [password complessa per l'account di GitHub](https://github.com/settings/admin).</span><span class="sxs-lookup"><span data-stu-id="faf99-124">Create a [strong password for your Github account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="faf99-125">Abilitare [l'autenticazione a due fattori](https://github.com/settings/two_factor_authentication/configure).</span><span class="sxs-lookup"><span data-stu-id="faf99-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="faf99-126">Salvare i [codici di ripristino](https://github.com/settings/auth/recovery-codes) in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="faf99-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="faf99-127">Aggiornare le [impostazioni del profilo pubblico](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="faf99-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="faf99-128">Impostare il proprio nome e valutare la possibilità di impostare il messaggio di posta *elettronica pubblico* su *non mostrare l'indirizzo di posta elettronica*.</span><span class="sxs-lookup"><span data-stu-id="faf99-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="faf99-129">Ti consigliamo di caricare un'immagine del profilo perché viene visualizzata un'anteprima nelle pagine di documenti a cui Contribuisci.</span><span class="sxs-lookup"><span data-stu-id="faf99-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="faf99-130">Se si prevede di usare la riga di comando, valutare la possibilità [di configurare git Credential Manager per Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="faf99-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="faf99-131">In questo modo, non dovrai immettere la password ogni volta che apporti un contributo.</span><span class="sxs-lookup"><span data-stu-id="faf99-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="faf99-132">Il sistema editoriale è collegato a GitHub, quindi questi passaggi sono importanti.</span><span class="sxs-lookup"><span data-stu-id="faf99-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="faf99-133">Verrà elencato come autore o collaboratore di ogni articolo usando l'alias GitHub.</span><span class="sxs-lookup"><span data-stu-id="faf99-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="faf99-134">Modifica di un articolo esistente</span><span class="sxs-lookup"><span data-stu-id="faf99-134">Editing an existing article</span></span>

<span data-ttu-id="faf99-135">Usare il flusso di lavoro seguente per apportare aggiornamenti a *un articolo esistente* tramite GitHub in un Web browser:</span><span class="sxs-lookup"><span data-stu-id="faf99-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="faf99-136">Passare all'articolo che si vuole modificare nella cartella "Mixed-Reality-docs".</span><span class="sxs-lookup"><span data-stu-id="faf99-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>
2. <span data-ttu-id="faf99-137">Selezionare il pulsante modifica (icona a forma di matita) nell'angolo in alto a destra, che si biforca automaticamente in un ramo monouso dal ramo "Master".</span><span class="sxs-lookup"><span data-stu-id="faf99-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Modificare un articolo.](images/editpage.png)
3. <span data-ttu-id="faf99-139">Modificare il contenuto dell'articolo in base alle ["Nozioni di base su Markdown"](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="faf99-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>
4. <span data-ttu-id="faf99-140">Aggiornare i metadati nella parte superiore di ogni articolo:</span><span class="sxs-lookup"><span data-stu-id="faf99-140">Update metadata at the top of each article:</span></span>
   * <span data-ttu-id="faf99-141">**titolo**: titolo della pagina visualizzato nella scheda del browser quando l'articolo viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="faf99-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="faf99-142">I titoli di pagina vengono usati per SEO e indicizzazione, quindi non modificare il titolo se non necessario (anche se è meno importante prima che la documentazione venga pubblica).</span><span class="sxs-lookup"><span data-stu-id="faf99-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="faf99-143">**Descrizione**: scrivere una breve descrizione del contenuto dell'articolo, che aumenta la SEO e l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="faf99-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="faf99-144">**autore**: se si è il proprietario principale della pagina, aggiungere qui il proprio alias github.</span><span class="sxs-lookup"><span data-stu-id="faf99-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="faf99-145">**ms. Author**: se si è il proprietario principale della pagina, aggiungere il proprio alias Microsoft qui (non è necessario @microsoft. com, solo l'alias).</span><span class="sxs-lookup"><span data-stu-id="faf99-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="faf99-146">**ms. Data**: consente di aggiornare la data se si sta aggiungendo contenuto principale alla pagina, ma non per le correzioni, ad esempio per chiarimenti, formattazione, grammatica o ortografia.</span><span class="sxs-lookup"><span data-stu-id="faf99-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="faf99-147">**parole chiave**: assistenza per le parole chiave in SEO (Search Engine Optimization).</span><span class="sxs-lookup"><span data-stu-id="faf99-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="faf99-148">Aggiungere parole chiave, separate da una virgola e uno spazio, specifiche per l'articolo, ma senza punteggiatura dopo l'ultima parola chiave nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="faf99-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="faf99-149">Non è necessario aggiungere parole chiave globali che si applicano a tutti gli articoli, perché sono gestite altrove.</span><span class="sxs-lookup"><span data-stu-id="faf99-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
5. <span data-ttu-id="faf99-150">Dopo aver completato le modifiche dell'articolo, scorrere verso il basso e selezionare **Proponi modifica file**.</span><span class="sxs-lookup"><span data-stu-id="faf99-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>
6. <span data-ttu-id="faf99-151">Nella pagina successiva selezionare **Crea richiesta di pull** per unire la filiale creata automaticamente in "Master".</span><span class="sxs-lookup"><span data-stu-id="faf99-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>
7. <span data-ttu-id="faf99-152">Ripetere i passaggi descritti sopra per l'articolo successivo che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="faf99-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="faf99-153">Ridenominazione o eliminazione di un articolo esistente</span><span class="sxs-lookup"><span data-stu-id="faf99-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="faf99-154">Se la modifica rinominerà o eliminerà un articolo esistente, assicurarsi di aggiungere un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="faf99-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="faf99-155">In questo modo, tutti gli utenti con un collegamento all'articolo esistente finiranno ancora nel posto giusto.</span><span class="sxs-lookup"><span data-stu-id="faf99-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="faf99-156">I redirect vengono gestiti dall'.openpublishing.redirection.jssu file nella radice del repo.</span><span class="sxs-lookup"><span data-stu-id="faf99-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="faf99-157">Per aggiungere un reindirizzamento a .openpublishing.redirection.js, aggiungere una voce alla `redirections` matrice:</span><span class="sxs-lookup"><span data-stu-id="faf99-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="faf99-158">Il `source_path` percorso del repository relativo al vecchio articolo che si sta rimuovendo.</span><span class="sxs-lookup"><span data-stu-id="faf99-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="faf99-159">Assicurarsi che il percorso inizi con `mixed-reality-docs` e termina con `.md` .</span><span class="sxs-lookup"><span data-stu-id="faf99-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>
- <span data-ttu-id="faf99-160">`redirect_url`È l'URL pubblico relativo del vecchio articolo del nuovo articolo.</span><span class="sxs-lookup"><span data-stu-id="faf99-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="faf99-161">Assicurarsi che l'URL **non** contenga `mixed-reality-docs` o `.md` , poiché fa riferimento all'URL pubblico e non al percorso del repository.</span><span class="sxs-lookup"><span data-stu-id="faf99-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="faf99-162">Il collegamento a una sezione all'interno del nuovo articolo in uso `#section` è consentito.</span><span class="sxs-lookup"><span data-stu-id="faf99-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="faf99-163">È anche possibile usare un percorso assoluto per un altro sito, se necessario.</span><span class="sxs-lookup"><span data-stu-id="faf99-163">You can also use an absolute path to another site here, if necessary.</span></span>
- `redirect_document_id` <span data-ttu-id="faf99-164">indica se si vuole conservare l'ID documento dal file precedente.</span><span class="sxs-lookup"><span data-stu-id="faf99-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="faf99-165">Il valore predefinito è `false` .</span><span class="sxs-lookup"><span data-stu-id="faf99-165">The default is `false`.</span></span> <span data-ttu-id="faf99-166">Usare `true` se si vuole mantenere il `ms.documentid` valore dell'attributo dall'articolo reindirizzato.</span><span class="sxs-lookup"><span data-stu-id="faf99-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="faf99-167">Se si mantiene l'ID documento, i dati, ad esempio le visualizzazioni di pagina e le classifiche, verranno trasferiti nell'articolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="faf99-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="faf99-168">Eseguire questa operazione se il reindirizzamento è principalmente una ridenominazione e non un puntatore a un articolo diverso che copre solo alcuno dello stesso contenuto.</span><span class="sxs-lookup"><span data-stu-id="faf99-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="faf99-169">Se si aggiunge un reindirizzamento, assicurarsi di eliminare anche il vecchio file.</span><span class="sxs-lookup"><span data-stu-id="faf99-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="faf99-170">Creazione di un nuovo articolo</span><span class="sxs-lookup"><span data-stu-id="faf99-170">Creating a new article</span></span>

<span data-ttu-id="faf99-171">Usare il flusso di lavoro seguente per *creare nuovi articoli* nel repository della documentazione tramite GitHub in un Web browser:</span><span class="sxs-lookup"><span data-stu-id="faf99-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="faf99-172">Crea una forchetta al di fuori del ramo "Master" di MicrosoftDocs/Mixed-Reality (usando il pulsante della **forcella** in alto a destra).</span><span class="sxs-lookup"><span data-stu-id="faf99-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Fork del ramo master.](images/forkbranch.png)
2. <span data-ttu-id="faf99-174">Nella cartella "Mixed-Reality-docs" selezionare **Crea nuovo file** in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="faf99-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>
3. <span data-ttu-id="faf99-175">Creare un nome di pagina per l'articolo (usare i trattini invece degli spazi e non usare segni di punteggiatura o apostrofi) e aggiungere ". MD"</span><span class="sxs-lookup"><span data-stu-id="faf99-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Assegnare un nome alla nuova pagina.](images/newpagetitle.PNG)
   
   >[!IMPORTANT]
   ><span data-ttu-id="faf99-177">Assicurati di creare il nuovo articolo nella cartella "Mixed-Reality-docs".</span><span class="sxs-lookup"><span data-stu-id="faf99-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="faf99-178">È possibile confermare questa operazione selezionando "/Mixed-Reality-docs/" nella nuova riga nome file.</span><span class="sxs-lookup"><span data-stu-id="faf99-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="faf99-179">Nella parte superiore della nuova pagina aggiungere il blocco di metadati seguente:</span><span class="sxs-lookup"><span data-stu-id="faf99-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="faf99-180">Compilare i campi relativi ai metadati per le istruzioni nella [sezione precedente](#editing-an-existing-article).</span><span class="sxs-lookup"><span data-stu-id="faf99-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>
6. <span data-ttu-id="faf99-181">Scrivere contenuto articolo usando le [nozioni di base di Markdown](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="faf99-181">Write article content using [Markdown basics](#markdown-basics).</span></span>
7. <span data-ttu-id="faf99-182">Aggiungere una `## See also` sezione nella parte inferiore dell'articolo con collegamenti ad altri articoli rilevanti.</span><span class="sxs-lookup"><span data-stu-id="faf99-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>
8. <span data-ttu-id="faf99-183">Al termine, selezionare **Salva nuovo file**.</span><span class="sxs-lookup"><span data-stu-id="faf99-183">When finished, select **Commit new file**.</span></span>
9. <span data-ttu-id="faf99-184">Selezionare **nuova richiesta di pull** e unire il ramo "Master" della forcella in MicrosoftDocs/Mixed-Reality ' Master ' (verificare che la freccia indichi il modo corretto).</span><span class="sxs-lookup"><span data-stu-id="faf99-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Creare una richiesta di pull dalla forcella in MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

## <span data-ttu-id="faf99-186">Nozioni di base su Markdown</span><span class="sxs-lookup"><span data-stu-id="faf99-186">Markdown basics</span></span>

<span data-ttu-id="faf99-187">Le risorse seguenti ti aiuteranno a scoprire come modificare la documentazione usando la lingua markdown:</span><span class="sxs-lookup"><span data-stu-id="faf99-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="faf99-188">Nozioni di base su Markdown</span><span class="sxs-lookup"><span data-stu-id="faf99-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="faf99-189">Poster di riferimento Markdown-at-a-Glant</span><span class="sxs-lookup"><span data-stu-id="faf99-189">Markdown-at-a-glance reference poster</span></span>](images/MarkdownPoster.pdf)
- [<span data-ttu-id="faf99-190">Risorse aggiuntive per la scrittura di Markdown per docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="faf99-190">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="faf99-191">Aggiunta di tabelle</span><span class="sxs-lookup"><span data-stu-id="faf99-191">Adding tables</span></span>

<span data-ttu-id="faf99-192">A causa del modo in cui le tabelle stili di docs.microsoft.com, non hanno bordi o stili personalizzati, anche se si prova CSS inline.</span><span class="sxs-lookup"><span data-stu-id="faf99-192">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="faf99-193">Sembrerà funzionare per un breve periodo di tempo, ma alla fine la piattaforma striscerà lo stile fuori dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="faf99-193">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="faf99-194">Pianificare in anticipo e semplificare le tabelle.</span><span class="sxs-lookup"><span data-stu-id="faf99-194">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="faf99-195">[Ecco un sito che semplifica le tabelle di Markdown](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="faf99-195">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="faf99-196">L' [estensione docs Markdown per il codice di Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) rende anche la generazione di tabelle semplice se si usa il [codice di Visual Studio (vedere di seguito)](#using-visual-studio-code) per modificare la documentazione.</span><span class="sxs-lookup"><span data-stu-id="faf99-196">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="faf99-197">Aggiunta di immagini</span><span class="sxs-lookup"><span data-stu-id="faf99-197">Adding images</span></span>

<span data-ttu-id="faf99-198">Dovrai caricare le tue immagini nella cartella "Mixed-Reality-docs/images" nel repo e quindi fare riferimento a loro in modo appropriato nell'articolo.</span><span class="sxs-lookup"><span data-stu-id="faf99-198">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="faf99-199">Le immagini verranno visualizzate automaticamente in formato completo, in modo che le immagini di grandi dimensioni riempiano l'intera larghezza dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="faf99-199">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="faf99-200">Ti consigliamo di pre-dimensionare le immagini prima di caricarle.</span><span class="sxs-lookup"><span data-stu-id="faf99-200">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="faf99-201">La larghezza consigliata è compresa tra 600 e 700 pixel, anche se è necessario ridimensionare o ridurre le dimensioni se si tratta di uno screenshot denso o di una frazione rispettivamente di uno screenshot.</span><span class="sxs-lookup"><span data-stu-id="faf99-201">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="faf99-202">È possibile caricare le immagini solo nel repo a forcella prima di unirle.</span><span class="sxs-lookup"><span data-stu-id="faf99-202">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="faf99-203">Quindi, se si prevede di aggiungere immagini a un articolo, è necessario usare il [codice di Visual Studio](#using-visual-studio-code) per aggiungere prima le immagini alla cartella "immagini" della forcella oppure verificare di aver eseguito le operazioni seguenti in un Web browser:</span><span class="sxs-lookup"><span data-stu-id="faf99-203">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="faf99-204">Forked il repo di MicrosoftDocs/Mixed-Reality.</span><span class="sxs-lookup"><span data-stu-id="faf99-204">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="faf99-205">Modifica dell'articolo nella tua forcella.</span><span class="sxs-lookup"><span data-stu-id="faf99-205">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="faf99-206">Sono state caricate le immagini a cui si fa riferimento nell'articolo nella cartella "Mixed-Reality-docs/images" nella forcella.</span><span class="sxs-lookup"><span data-stu-id="faf99-206">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="faf99-207">È stata creata una **richiesta di pull** per unire la forcella alla filiale "Master" di MicrosoftDocs/Mixed-Reality.</span><span class="sxs-lookup"><span data-stu-id="faf99-207">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="faf99-208">Per informazioni su come configurare il proprio repo a forcella, seguire le istruzioni per la [creazione di un nuovo articolo](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="faf99-208">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="faf99-209">Visualizzazione in anteprima del lavoro</span><span class="sxs-lookup"><span data-stu-id="faf99-209">Previewing your work</span></span>

<span data-ttu-id="faf99-210">Durante la modifica in GitHub tramite un Web browser, è possibile selezionare la scheda **Anteprima** nella parte superiore della pagina per visualizzare in anteprima il lavoro prima di eseguire il commit.</span><span class="sxs-lookup"><span data-stu-id="faf99-210">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="faf99-211">La visualizzazione in anteprima delle modifiche apportate review.docs.microsoft.com è disponibile solo per i dipendenti Microsoft</span><span class="sxs-lookup"><span data-stu-id="faf99-211">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="faf99-212">Dipendenti Microsoft: una volta che i contributi sono Stati Uniti nella filiale "Master", è possibile esaminare il contenuto prima che venga eseguito pubblicamente https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="faf99-212">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="faf99-213">Trovare l'articolo usando il sommario nella colonna sinistra.</span><span class="sxs-lookup"><span data-stu-id="faf99-213">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="faf99-214">Modifica nel browser e modifica con un client desktop</span><span class="sxs-lookup"><span data-stu-id="faf99-214">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="faf99-215">La modifica nel browser è il modo più semplice per apportare modifiche rapide, ma ci sono alcuni svantaggi:</span><span class="sxs-lookup"><span data-stu-id="faf99-215">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="faf99-216">Non si ottiene il controllo ortografico.</span><span class="sxs-lookup"><span data-stu-id="faf99-216">You don't get spell-check.</span></span>
- <span data-ttu-id="faf99-217">Non è possibile ottenere un collegamento intelligente ad altri articoli (è necessario digitare manualmente il nome del file dell'articolo).</span><span class="sxs-lookup"><span data-stu-id="faf99-217">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="faf99-218">Può essere un problema per caricare e fare riferimento alle immagini.</span><span class="sxs-lookup"><span data-stu-id="faf99-218">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="faf99-219">Se si preferisce non risolvere questi problemi, usare un client desktop come il [codice di Visual Studio](https://code.visualstudio.com/) con un paio di [utili estensioni](#useful-extensions) quando contribuiscono.</span><span class="sxs-lookup"><span data-stu-id="faf99-219">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="faf99-220">Uso del codice di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="faf99-220">Using Visual Studio Code</span></span>

<span data-ttu-id="faf99-221">Per i motivi elencati [sopra](#editing-in-the-browser-vs-editing-with-a-desktop-client), potrebbe essere preferibile usare un client desktop per modificare la documentazione invece di un Web browser.</span><span class="sxs-lookup"><span data-stu-id="faf99-221">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="faf99-222">È consigliabile usare il [codice di Visual Studio](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="faf99-222">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="faf99-223">Installazione</span><span class="sxs-lookup"><span data-stu-id="faf99-223">Setup</span></span>

<span data-ttu-id="faf99-224">Seguire questa procedura per configurare il codice di Visual Studio per l'utilizzo di questo repo:</span><span class="sxs-lookup"><span data-stu-id="faf99-224">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="faf99-225">In un Web browser:</span><span class="sxs-lookup"><span data-stu-id="faf99-225">In a web browser:</span></span>
    1. <span data-ttu-id="faf99-226">Installare [git per il PC](https://git-scm.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="faf99-226">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="faf99-227">Installare il [codice di Visual Studio](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="faf99-227">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="faf99-228">[Fork MicrosoftDocs/Mixed-Reality](#creating-a-new-article) se non è già stato fatto.</span><span class="sxs-lookup"><span data-stu-id="faf99-228">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="faf99-229">Nella tua forcella seleziona **clona o Scarica** e copia l'URL.</span><span class="sxs-lookup"><span data-stu-id="faf99-229">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="faf99-230">Creare un clone locale della forcella nel codice di Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="faf99-230">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="faf99-231">Nel menu **Visualizza** selezionare **tavolozza dei comandi**.</span><span class="sxs-lookup"><span data-stu-id="faf99-231">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="faf99-232">Digitare "git: clone".</span><span class="sxs-lookup"><span data-stu-id="faf99-232">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="faf99-233">Incollare l'URL copiato.</span><span class="sxs-lookup"><span data-stu-id="faf99-233">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="faf99-234">Scegliere la posizione in cui salvare il clone nel PC.</span><span class="sxs-lookup"><span data-stu-id="faf99-234">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="faf99-235">Selezionare **Apri repo** nella finestra popup.</span><span class="sxs-lookup"><span data-stu-id="faf99-235">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="faf99-236">Modifica della documentazione</span><span class="sxs-lookup"><span data-stu-id="faf99-236">Editing documentation</span></span>

<span data-ttu-id="faf99-237">Usare il flusso di lavoro seguente per apportare modifiche alla documentazione con il codice di Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="faf99-237">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="faf99-238">Tutte le linee guida per la [modifica](#editing-an-existing-article) e la [creazione](#creating-a-new-article) di articoli e le [nozioni di base per la modifica di Markdown](#markdown-basics), si applicano anche quando si usa il codice di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="faf99-238">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="faf99-239">Verificare che la forcella clonata sia aggiornata con il repo ufficiale.</span><span class="sxs-lookup"><span data-stu-id="faf99-239">Make sure your cloned fork is up to date with the official repo.</span></span>
   1. <span data-ttu-id="faf99-240">In un Web browser, creare una richiesta di pull per sincronizzare le recenti modifiche da altri collaboratori in MicrosoftDocs/Mixed-Reality ' Master ' alla forcella (verificare che la freccia sia rivolta nel modo giusto).</span><span class="sxs-lookup"><span data-stu-id="faf99-240">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Sincronizzare le modifiche da MicrosoftDocs/Mixed-Reality alla tua forcella](images/sync_repos.PNG)
   2. <span data-ttu-id="faf99-242">Nel codice di Visual Studio selezionare il pulsante Sincronizza per sincronizzare il fork appena aggiornato con il clone locale.</span><span class="sxs-lookup"><span data-stu-id="faf99-242">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Fare clic sull'immagine del pulsante di sincronizzazione](images/sync_clone.png)
2. <span data-ttu-id="faf99-244">Creare o modificare articoli nel repo clonato usando il codice di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="faf99-244">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>
   1. <span data-ttu-id="faf99-245">Modificare uno o più articoli (se necessario, aggiungere immagini alla cartella "immagini").</span><span class="sxs-lookup"><span data-stu-id="faf99-245">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   2. <span data-ttu-id="faf99-246">**Salvare** le modifiche in **Esplora risorse**.</span><span class="sxs-lookup"><span data-stu-id="faf99-246">**Save** changes in **Explorer**.</span></span>
      
      ![Scegliere "Salva tutto" in Esplora risorse](images/explorer_save.png)
   3. <span data-ttu-id="faf99-248">Eseguire il **commit di tutte** le modifiche nel **controllo del codice sorgente** (messaggio di scrittura commit quando richiesto).</span><span class="sxs-lookup"><span data-stu-id="faf99-248">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
      
      ![Scegliere "Commit all" nel controllo del codice sorgente](images/source_control_commit.png)
   4. <span data-ttu-id="faf99-250">Selezionare il pulsante **Sincronizza** per sincronizzare di nuovo le modifiche all'origine (la forcella su GitHub).</span><span class="sxs-lookup"><span data-stu-id="faf99-250">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Fare clic sul pulsante Sincronizza](images/sync_back.png)
3. <span data-ttu-id="faf99-252">In un Web browser, crea una richiesta di pull per sincronizzare le nuove modifiche nella tua forcella in MicrosoftDocs/Mixed-Reality "Master" (assicurati che la freccia indichi il modo corretto).</span><span class="sxs-lookup"><span data-stu-id="faf99-252">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Creare una richiesta di pull dalla forcella in MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

### <span data-ttu-id="faf99-254">Estensioni utili</span><span class="sxs-lookup"><span data-stu-id="faf99-254">Useful extensions</span></span>

<span data-ttu-id="faf99-255">Le estensioni di codice di Visual Studio seguenti sono utili quando si modifica la documentazione:</span><span class="sxs-lookup"><span data-stu-id="faf99-255">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="faf99-256">[Estensione docs Markdown per il codice di Visual Studio](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) : usare **ALT + M** per visualizzare un menu di opzioni per la creazione di documenti, ad esempio</span><span class="sxs-lookup"><span data-stu-id="faf99-256">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="faf99-257">Cercare e fare riferimento alle immagini caricate.</span><span class="sxs-lookup"><span data-stu-id="faf99-257">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="faf99-258">Aggiungere la formattazione, ad esempio elenchi, tabelle e chiamate specifiche per documenti `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="faf99-258">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="faf99-259">Cercare e fare riferimento a collegamenti interni e segnalibri (collegamenti a sezioni specifiche all'interno di una pagina).</span><span class="sxs-lookup"><span data-stu-id="faf99-259">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="faf99-260">Gli errori di formattazione vengono evidenziati (posizionare il puntatore del mouse sull'errore per saperne di più).</span><span class="sxs-lookup"><span data-stu-id="faf99-260">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="faf99-261">[Controllo ortografia codice](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) : le parole con errori di ortografia verranno sottolineate; fare clic con il pulsante destro del mouse su una parola con errori di ortografia per modificarla o salvarla nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="faf99-261">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
