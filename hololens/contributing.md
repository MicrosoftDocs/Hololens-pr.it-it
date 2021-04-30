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
# <a name="contributing-to-the-hololens-documentation"></a>Contribuire alla documentazione di HoloLens

Benvenuti nella documentazione [di HoloLens](https://github.com/MicrosoftDocs/Hololens). Tutti gli articoli creati o modificati in questo repo **saranno visibili al pubblico.** 

I documenti di HoloLens vengono visualizzati nella piattaforma docs.microsoft.com, che usa Markdown basato su GitHub con le funzionalità markdig. Il contenuto modificato in questo repo viene formattato in pagine stilizzate che vengono mostrate in https://docs.microsoft.com/hololens . 

Questa pagina illustra i passaggi di base e le linee guida per contribuire e i collegamenti alle nozioni di base di Markdown. Grazie per il tuo contributo.

## <a name="available-repos"></a>Repository disponibili

| Nome del repository | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Realtà mista | [MicrosoftDocs/mixed-reality](https://docs.microsoft.com/windows/mixed-reality) |
| Guida per gli appassionati di VR | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Prima di iniziare

Se non è già presente, è necessario creare [un account GitHub.](https://github.com/join)

>[!NOTE]
>Se si è un dipendente Microsoft, collegare l'account GitHub all'alias Microsoft nel portale [Microsoft Open Source.](https://repos.opensource.microsoft.com/) Partecipare alle **organizzazioni "Microsoft"** **e "MicrosoftDocs".**

Quando si configura l'account GitHub, è consigliabile adottare anche queste precauzioni di sicurezza:
- Creare una [password complessa per l'account GitHub.](https://github.com/settings/admin)
- Abilitare [l'autenticazione a due fattori.](https://github.com/settings/two_factor_authentication/configure)
- Salvare i [codici di ripristino](https://github.com/settings/auth/recovery-codes) in un luogo sicuro.
- Aggiornare le [impostazioni del profilo pubblico](https://github.com/settings/profile).
   - Impostare il nome e provare a impostare Indirizzo di posta *elettronica pubblico* su Non *visualizzare l'indirizzo di posta elettronica.*
   - È consigliabile caricare un'immagine del profilo perché viene visualizzata un'anteprima nelle pagine della documentazione a cui si contribuisce.
- Se si prevede di usare la riga di comando, è consigliabile [configurare Git Gestione credenziali per Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) In questo modo, non sarà necessario immettere la password ogni volta che si apporta un contributo.

Il sistema di pubblicazione è associato a GitHub, quindi questi passaggi sono importanti. L'utente verrà elencato come autore o collaboratore per ogni articolo usando l'alias GitHub.

## <a name="editing-an-existing-article"></a>Modifica di un articolo esistente

Usare il flusso di lavoro seguente per apportare aggiornamenti *a un articolo* esistente tramite GitHub in un Web browser:

1. Passare all'articolo che si vuole modificare nella cartella "mixed-reality-docs".

2. Selezionare il pulsante di modifica (icona a forma di matita) in alto a destra, che crea automaticamente una copia di un ramo eliminabile dal ramo "master".

   ![Modificare un articolo.](images/editpage.png)
   
3. Modificare il contenuto dell'articolo in base alle ["nozioni di base su Markdown".](#markdown-basics)

4. Aggiornare i metadati all'inizio di ogni articolo:

   * **title:** titolo della pagina visualizzato nella scheda del browser quando viene visualizzato l'articolo. I titoli di pagina vengono usati per seO e indicizzazione, quindi non modificare il titolo a meno che non sia necessario (anche se questo è meno importante prima che la documentazione venga pubblicata).
   * **description:** scrivere una breve descrizione del contenuto dell'articolo, che migliora seO e individuazione.
   * **author:** se si è il proprietario primario della pagina, aggiungere qui l'alias GitHub.
   * **ms.author:** se si è il proprietario primario della pagina, aggiungere qui l'alias Microsoft (non è necessario , ma @microsoft.com solo l'alias).
   * **ms.date:** aggiornare la data se si aggiunge contenuto principale alla pagina, ma non per correzioni come chiarimenti, formattazione, grammatica o ortografia.
   * **keywords:** le parole chiave sono di aiuto in SEO (ottimizzazione del motore di ricerca). Aggiungere parole chiave, separate da una virgola e uno spazio, specifiche per l'articolo, ma senza punteggiatura dopo l'ultima parola chiave nell'elenco. Non è necessario aggiungere parole chiave globali che si applicano a tutti gli articoli, perché vengono gestite altrove. 
   
5. Dopo aver completato le modifiche all'articolo, scorrere verso il basso e selezionare **Proponi modifica file**.

6. Nella pagina successiva selezionare Crea **richiesta pull per** unire il ramo creato automaticamente in "master".

7. Ripetere i passaggi precedenti per l'articolo successivo da modificare.

## <a name="renaming-or-deleting-an-existing-article"></a>Ridenominazione o eliminazione di un articolo esistente

Se la modifica rinomina o elimina un articolo esistente, assicurarsi di aggiungere un reindirizzamento. In questo modo, chiunque abbia un collegamento all'articolo esistente finirà comunque nel posto giusto. I reindirizzamenti vengono gestiti dal .openpublishing.redirection.jsfile nella radice del repo.

Per aggiungere un reindirizzamento .openpublishing.redirection.js, aggiungere una voce alla `redirections` matrice:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- è `source_path` il percorso del repository relativo all'articolo precedente che si sta rimuovendo. Assicurarsi che il percorso inizi con `mixed-reality-docs` e termini con `.md` .

- è `redirect_url` l'URL pubblico relativo dall'articolo precedente al nuovo articolo. Assicurarsi che questo URL non contenga o , perché fa riferimento **all'URL** pubblico `mixed-reality-docs` e non al percorso del `.md` repository. È consentito il collegamento a una sezione all'interno del nuovo articolo `#section` tramite . Se necessario, è anche possibile usare un percorso assoluto per un altro sito.

- `redirect_document_id` indica se si vuole mantenere l'ID documento dal file precedente. Il valore predefinito è `false`. Usare `true` se si vuole mantenere il valore `ms.documentid` dell'attributo dall'articolo reindirizzato. Se si mantiene l'ID documento, i dati, ad esempio le visualizzazioni pagina e le classificazioni, verranno trasferiti all'articolo di destinazione. Eseguire questa operazione se il reindirizzamento è principalmente una ridenominazione e non un puntatore a un articolo diverso che copre solo parte dello stesso contenuto.

Se si aggiunge un reindirizzamento, assicurarsi di eliminare anche il file precedente.

## <a name="creating-a-new-article"></a>Creazione di un nuovo articolo

Usare il flusso di lavoro *seguente per creare nuovi* articoli nel repository della documentazione tramite GitHub in un Web browser:

1. Creare un fork dal ramo "master" Di MicrosoftDocs/realtà mista (usando il pulsante **Fork** in alto a destra).

   ![Creare una copia con fork del ramo master.](images/forkbranch.png)
   
2. Nella cartella "mixed-reality-docs" selezionare **Crea nuovo file** in alto a destra.

3. Creare un nome di pagina per l'articolo (usare trattini anziché spazi e non usare segni di punteggiatura o apostrofi) e aggiungere ".md"

   ![Assegnare un nome alla nuova pagina.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Assicurarsi di creare il nuovo articolo dalla cartella "mixed-reality-docs". È possibile verificarlo controllando "/mixed-reality-docs/" nella nuova riga del nome file.

4. Nella parte superiore della nuova pagina aggiungere il blocco di metadati seguente:

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

5. Compilare i campi dei metadati pertinenti in base alle istruzioni nella [sezione precedente.](#editing-an-existing-article)

6. Scrivere il contenuto dell'articolo [usando le nozioni di base di Markdown.](#markdown-basics)

7. Aggiungere una `## See also` sezione nella parte inferiore dell'articolo con collegamenti ad altri articoli pertinenti.

8. Al termine, selezionare **Commit new file (Esegui commit nuovo file).**

9. Selezionare **Nuova richiesta pull** e unire il ramo 'master' del fork in MicrosoftDocs/mixed-reality 'master' (assicurarsi che la freccia sia rivolta nel modo corretto).

   ![Creare una richiesta pull dal fork in MicrosoftDocs/realtà mista](images/pr-to-master.png)

## <a name="markdown-basics"></a>Nozioni di base su Markdown

Le risorse seguenti consentono di imparare a modificare la documentazione usando il linguaggio Markdown:

- [Informazioni di base su Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Risorse aggiuntive per la scrittura di Markdown per docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Aggiunta di tabelle

A causa del modo in cui docs.microsoft.com stili, non hanno bordi o stili personalizzati, anche se si prova css inline. Sembra funzionare per un breve periodo di tempo, ma alla fine la piattaforma rimuoverà lo stile dalla tabella. Pianificare in anticipo e mantenere le tabelle semplici. [Ecco un sito che semplifica le tabelle Markdown.](https://www.tablesgenerator.com/markdown_tables)

[L'estensione Docs Markdown per Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) semplifica anche la generazione di tabelle se si usa Visual Studio Code (vedere di [seguito)](#using-visual-studio-code) per modificare la documentazione.

### <a name="adding-images"></a>Aggiunta di immagini

È necessario caricare le immagini nella cartella "mixed-reality-docs/images" nel repo e quindi fare riferimento alle immagini in modo appropriato nell'articolo. Le immagini verranno visualizzate automaticamente a dimensioni complete, ovvero le immagini di grandi dimensioni riempiranno l'intera larghezza dell'articolo. È consigliabile pre-ridimensionare le immagini prima di caricarle. La larghezza consigliata è compresa tra 600 e 700 pixel, anche se è consigliabile ridimensionare rispettivamente se si tratta di uno screenshot denso o di una frazione di uno screenshot.

>[!IMPORTANT]
>È possibile caricare le immagini solo nel repo con fork prima dell'unione. Pertanto, se si prevede di aggiungere immagini a un articolo, è necessario usare [Visual Studio Code](#using-visual-studio-code) per aggiungere prima le immagini alla cartella "images" del fork o assicurarsi di aver eseguito le operazioni seguenti in un Web browser:
>
>1. Fork del repo MicrosoftDocs/mixed-reality.
>2. L'articolo è stato modificato nel fork.
>3. Le immagini a cui si fa riferimento nell'articolo sono caricate nella cartella "mixed-reality-docs/images" nel fork.
>4. È stata **creata una richiesta pull** per unire il fork nel ramo MicrosoftDocs/mixed-reality 'master'.
>
>Per informazioni su come configurare il proprio repo con fork, seguire le istruzioni per [la creazione di un nuovo articolo.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Anteprima del lavoro

Durante la modifica in GitHub tramite un Web browser, è possibile selezionare la scheda **Anteprima** nella parte superiore della pagina per visualizzare in anteprima il lavoro prima di eseguire il commit. 

>[!NOTE]
>La visualizzazione in anteprima delle modifiche review.docs.microsoft.com è disponibile solo per i dipendenti Microsoft

Dipendenti Microsoft: dopo aver unito i contributi nel ramo "master", è possibile esaminare il contenuto prima che venga pubblicato all'indirizzo https://review.docs.microsoft.com/hololens?branch=master . Trovare l'articolo usando il sommario nella colonna sinistra.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Modifica nel browser e modifica con un client desktop

La modifica nel browser è il modo più semplice per apportare modifiche rapide, ma esistono alcuni svantaggi:

- Il controllo ortografico non viene visualizzato.
- Non si ottiene alcun collegamento intelligente ad altri articoli (è necessario digitare manualmente il nome file dell'articolo).
- Può essere un'insidola per caricare e fare riferimento alle immagini.

Se si preferisce non gestire questi problemi, usare un client desktop come [Visual Studio Code](https://code.visualstudio.com/) con un paio [di estensioni utili](#useful-extensions) per contribuire.

## <a name="using-visual-studio-code"></a>Uso di Visual Studio Code

Per i motivi [elencati in](#editing-in-the-browser-vs-editing-with-a-desktop-client)precedenza, è preferibile usare un client desktop per modificare la documentazione anziché un Web browser. È consigliabile usare [Visual Studio Code](https://code.visualstudio.com/).

### <a name="setup"></a>Configurazione

Seguire questa procedura per configurare Visual Studio Code per l'utilizzo di questo repo:

1. In un Web browser:
    1. Installare [Git per il PC.](https://git-scm.com/downloads)
    2. Installare [Visual Studio Code](https://code.visualstudio.com/).
    3. [Creare una fork di MicrosoftDocs/realtà mista,](#creating-a-new-article) se non è già stato fatto.
    4. Nel fork selezionare **Clona o scarica e** copiare l'URL.
2. Creare un clone locale del fork in Visual Studio Code:
    1. Scegliere **Riquadro comandi** dal menu **Visualizza.**
    2. Digitare "Git: Clone".
    3. Incollare l'URL copiato.
    4. Scegliere dove salvare il clone nel PC.
    5. Selezionare **Apri il repo** nel popup.

### <a name="editing-documentation"></a>Documentazione di modifica

Usare il flusso di lavoro seguente per apportare modifiche alla documentazione con Visual Studio Code:

>[!NOTE]
>Tutte le linee [](#creating-a-new-article) guida per [la modifica](#editing-an-existing-article) e la creazione di articoli e le nozioni di base sulla modifica di [Markdown](#markdown-basics)da sopra si applicano anche quando si usa Visual Studio Code.

1. Assicurarsi che il fork clonato sia aggiornato con il repo ufficiale.

   1. In un Web browser creare una richiesta pull per sincronizzare le modifiche recenti da altri collaboratori in MicrosoftDocs/mixed-reality 'master' al fork (assicurarsi che la freccia sia rivolta nel modo giusto).
      
      ![Sincronizzare le modifiche da MicrosoftDocs/mixed-reality al fork](images/sync-repos.png)
      
   2. In Visual Studio Code selezionare il pulsante sincronizza per sincronizzare il fork appena aggiornato con il clone locale.
      
      ![Fare clic sull'immagine del pulsante di sincronizzazione](images/sync-clone.png)
      
2. Creare o modificare articoli nel repo clonato usando Visual Studio Code.

   1. Modificare uno o più articoli (aggiungere immagini alla cartella "images", se necessario).
   
   2. **Salvare** le modifiche in **Esplora risorse**.
      
      ![Scegliere "Salva tutto" in Esplora risorse](images/explorer-save.png)
      
   3. **Eseguire il commit di** tutte **le modifiche nel** controllo del codice sorgente (scrivere un messaggio di commit quando richiesto).
   
      ![Scegliere "Commit all" nel controllo del codice sorgente](images/source-control-commit.png)
      
   4. Selezionare il **pulsante sincronizza** per sincronizzare le modifiche all'origine (fork in GitHub).
      
      ![Fare clic sul pulsante di sincronizzazione](images/sync-back.png)
      
3. In un Web browser creare una richiesta pull per sincronizzare le nuove modifiche nel fork con MicrosoftDocs/mixed-reality 'master' (assicurarsi che la freccia sia rivolta nel modo corretto).

   ![Creare una richiesta pull dal fork in MicrosoftDocs/realtà mista](images/pr-to-master.png)

### <a name="useful-extensions"></a>Estensioni utili

Le estensioni Visual Studio Code seguenti sono utili quando si modifica la documentazione:

- [Estensione Docs Markdown per Visual Studio Code:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) usare **ALT+M** per visualizzare un menu di opzioni di creazione di documenti, ad esempio:
   - Cercare e fare riferimento alle immagini caricate.
   - Aggiungere formattazione come elenchi, tabelle e call-out specifici della documentazione, ad esempio `>[!NOTE]` .
   - Cercare e fare riferimento a collegamenti e segnalibri interni (collegamenti a sezioni specifiche all'interno di una pagina).
   - Gli errori di formattazione sono evidenziati (passare il puntatore del mouse sull'errore per altre informazioni).
- [Controllo ortografico del codice:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) le parole con errori di ortografia verranno sottolineate; Fare clic con il pulsante destro del mouse su una parola con errori di ortografia per modificarla o salvarla nel dizionario.
