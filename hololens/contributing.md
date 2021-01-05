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
# Contribuire alla documentazione di HoloLens

Benvenuti nella [documentazione di HoloLens](https://github.com/MicrosoftDocs/Hololens). Tutti gli articoli creati o modificati in questo repo **saranno visibili al pubblico.** 

I documenti di HoloLens vengono visualizzati nella piattaforma docs.microsoft.com, che usa GitHub-Flavored Markdown con le caratteristiche di Markdig. Il contenuto modificato in questo repo viene formattato in pagine stilizzate visualizzate https://docs.microsoft.com/hololens . 

Questa pagina illustra i passaggi e le linee guida di base per il contributo e i collegamenti alle nozioni fondamentali su Markdown. Grazie per il tuo contributo!

## Pronti per le disponibilità

| Nome del repository | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Realtà mista | [MicrosoftDocs/mixed-realtà](https://docs.microsoft.com/windows/mixed-reality) |
| Guida per gli appassionati di VR | [MicrosoftDocs/Mixed-Reality/appassionato-Guida](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## Prima di iniziare

Se non è già disponibile, è necessario [creare un account github](https://github.com/join).

>[!NOTE]
>Se si è un dipendente Microsoft, collegare l'account di GitHub al proprio alias Microsoft nel [portale Open source Microsoft](https://repos.opensource.microsoft.com/). Partecipare alle organizzazioni " **Microsoft"** e **"MicrosoftDocs"** .

Quando si configura l'account di GitHub, è consigliabile attenersi alle seguenti precauzioni per la sicurezza:
- Creare una [password complessa per l'account di GitHub](https://github.com/settings/admin).
- Abilitare [l'autenticazione a due fattori](https://github.com/settings/two_factor_authentication/configure).
- Salvare i [codici di ripristino](https://github.com/settings/auth/recovery-codes) in una posizione sicura.
- Aggiornare le [impostazioni del profilo pubblico](https://github.com/settings/profile).
   - Impostare il proprio nome e valutare la possibilità di impostare il messaggio di posta *elettronica pubblico* su *non mostrare l'indirizzo di posta elettronica*.
   - Ti consigliamo di caricare un'immagine del profilo perché viene visualizzata un'anteprima nelle pagine di documenti a cui Contribuisci.
- Se si prevede di usare la riga di comando, valutare la possibilità [di configurare git Credential Manager per Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). In questo modo, non dovrai immettere la password ogni volta che apporti un contributo.

Il sistema editoriale è collegato a GitHub, quindi questi passaggi sono importanti. Verrà elencato come autore o collaboratore di ogni articolo usando l'alias GitHub.

## Modifica di un articolo esistente

Usare il flusso di lavoro seguente per apportare aggiornamenti a *un articolo esistente* tramite GitHub in un Web browser:

1. Passare all'articolo che si vuole modificare nella cartella "Mixed-Reality-docs".
2. Selezionare il pulsante modifica (icona a forma di matita) nell'angolo in alto a destra, che si biforca automaticamente in un ramo monouso dal ramo "Master".

   ![Modificare un articolo.](images/editpage.png)
3. Modificare il contenuto dell'articolo in base alle ["Nozioni di base su Markdown"](#markdown-basics).
4. Aggiornare i metadati nella parte superiore di ogni articolo:
   * **titolo**: titolo della pagina visualizzato nella scheda del browser quando l'articolo viene visualizzato. I titoli di pagina vengono usati per SEO e indicizzazione, quindi non modificare il titolo se non necessario (anche se è meno importante prima che la documentazione venga pubblica).
   * **Descrizione**: scrivere una breve descrizione del contenuto dell'articolo, che aumenta la SEO e l'individuazione.
   * **autore**: se si è il proprietario principale della pagina, aggiungere qui il proprio alias github.
   * **ms. Author**: se si è il proprietario principale della pagina, aggiungere il proprio alias Microsoft qui (non è necessario @microsoft. com, solo l'alias).
   * **ms. Data**: consente di aggiornare la data se si sta aggiungendo contenuto principale alla pagina, ma non per le correzioni, ad esempio per chiarimenti, formattazione, grammatica o ortografia.
   * **parole chiave**: assistenza per le parole chiave in SEO (Search Engine Optimization). Aggiungere parole chiave, separate da una virgola e uno spazio, specifiche per l'articolo, ma senza punteggiatura dopo l'ultima parola chiave nell'elenco. Non è necessario aggiungere parole chiave globali che si applicano a tutti gli articoli, perché sono gestite altrove. 
5. Dopo aver completato le modifiche dell'articolo, scorrere verso il basso e selezionare **Proponi modifica file**.
6. Nella pagina successiva selezionare **Crea richiesta di pull** per unire la filiale creata automaticamente in "Master".
7. Ripetere i passaggi descritti sopra per l'articolo successivo che si vuole modificare.

## Ridenominazione o eliminazione di un articolo esistente

Se la modifica rinominerà o eliminerà un articolo esistente, assicurarsi di aggiungere un reindirizzamento. In questo modo, tutti gli utenti con un collegamento all'articolo esistente finiranno ancora nel posto giusto. I redirect vengono gestiti dall'.openpublishing.redirection.jssu file nella radice del repo.

Per aggiungere un reindirizzamento a .openpublishing.redirection.js, aggiungere una voce alla `redirections` matrice:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- Il `source_path` percorso del repository relativo al vecchio articolo che si sta rimuovendo. Assicurarsi che il percorso inizi con `mixed-reality-docs` e termina con `.md` .
- `redirect_url`È l'URL pubblico relativo del vecchio articolo del nuovo articolo. Assicurarsi che l'URL **non** contenga `mixed-reality-docs` o `.md` , poiché fa riferimento all'URL pubblico e non al percorso del repository. Il collegamento a una sezione all'interno del nuovo articolo in uso `#section` è consentito. È anche possibile usare un percorso assoluto per un altro sito, se necessario.
- `redirect_document_id` indica se si vuole conservare l'ID documento dal file precedente. Il valore predefinito è `false` . Usare `true` se si vuole mantenere il `ms.documentid` valore dell'attributo dall'articolo reindirizzato. Se si mantiene l'ID documento, i dati, ad esempio le visualizzazioni di pagina e le classifiche, verranno trasferiti nell'articolo di destinazione. Eseguire questa operazione se il reindirizzamento è principalmente una ridenominazione e non un puntatore a un articolo diverso che copre solo alcuno dello stesso contenuto.

Se si aggiunge un reindirizzamento, assicurarsi di eliminare anche il vecchio file.

## Creazione di un nuovo articolo

Usare il flusso di lavoro seguente per *creare nuovi articoli* nel repository della documentazione tramite GitHub in un Web browser:

1. Crea una forchetta al di fuori del ramo "Master" di MicrosoftDocs/Mixed-Reality (usando il pulsante della **forcella** in alto a destra).

   ![Fork del ramo master.](images/forkbranch.png)
2. Nella cartella "Mixed-Reality-docs" selezionare **Crea nuovo file** in alto a destra.
3. Creare un nome di pagina per l'articolo (usare i trattini invece degli spazi e non usare segni di punteggiatura o apostrofi) e aggiungere ". MD"

   ![Assegnare un nome alla nuova pagina.](images/newpagetitle.PNG)
   
   >[!IMPORTANT]
   >Assicurati di creare il nuovo articolo nella cartella "Mixed-Reality-docs". È possibile confermare questa operazione selezionando "/Mixed-Reality-docs/" nella nuova riga nome file.

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

5. Compilare i campi relativi ai metadati per le istruzioni nella [sezione precedente](#editing-an-existing-article).
6. Scrivere contenuto articolo usando le [nozioni di base di Markdown](#markdown-basics).
7. Aggiungere una `## See also` sezione nella parte inferiore dell'articolo con collegamenti ad altri articoli rilevanti.
8. Al termine, selezionare **Salva nuovo file**.
9. Selezionare **nuova richiesta di pull** e unire il ramo "Master" della forcella in MicrosoftDocs/Mixed-Reality ' Master ' (verificare che la freccia indichi il modo corretto).

   ![Creare una richiesta di pull dalla forcella in MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

## Nozioni di base su Markdown

Le risorse seguenti ti aiuteranno a scoprire come modificare la documentazione usando la lingua markdown:

- [Nozioni di base su Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Poster di riferimento Markdown-at-a-Glant](images/MarkdownPoster.pdf)
- [Risorse aggiuntive per la scrittura di Markdown per docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### Aggiunta di tabelle

A causa del modo in cui le tabelle stili di docs.microsoft.com, non hanno bordi o stili personalizzati, anche se si prova CSS inline. Sembrerà funzionare per un breve periodo di tempo, ma alla fine la piattaforma striscerà lo stile fuori dalla tabella. Pianificare in anticipo e semplificare le tabelle. [Ecco un sito che semplifica le tabelle di Markdown](https://www.tablesgenerator.com/markdown_tables).

L' [estensione docs Markdown per il codice di Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) rende anche la generazione di tabelle semplice se si usa il [codice di Visual Studio (vedere di seguito)](#using-visual-studio-code) per modificare la documentazione.

### Aggiunta di immagini

Dovrai caricare le tue immagini nella cartella "Mixed-Reality-docs/images" nel repo e quindi fare riferimento a loro in modo appropriato nell'articolo. Le immagini verranno visualizzate automaticamente in formato completo, in modo che le immagini di grandi dimensioni riempiano l'intera larghezza dell'articolo. Ti consigliamo di pre-dimensionare le immagini prima di caricarle. La larghezza consigliata è compresa tra 600 e 700 pixel, anche se è necessario ridimensionare o ridurre le dimensioni se si tratta di uno screenshot denso o di una frazione rispettivamente di uno screenshot.

>[!IMPORTANT]
>È possibile caricare le immagini solo nel repo a forcella prima di unirle. Quindi, se si prevede di aggiungere immagini a un articolo, è necessario usare il [codice di Visual Studio](#using-visual-studio-code) per aggiungere prima le immagini alla cartella "immagini" della forcella oppure verificare di aver eseguito le operazioni seguenti in un Web browser:
>
>1. Forked il repo di MicrosoftDocs/Mixed-Reality.
>2. Modifica dell'articolo nella tua forcella.
>3. Sono state caricate le immagini a cui si fa riferimento nell'articolo nella cartella "Mixed-Reality-docs/images" nella forcella.
>4. È stata creata una **richiesta di pull** per unire la forcella alla filiale "Master" di MicrosoftDocs/Mixed-Reality.
>
>Per informazioni su come configurare il proprio repo a forcella, seguire le istruzioni per la [creazione di un nuovo articolo](#creating-a-new-article).

## Visualizzazione in anteprima del lavoro

Durante la modifica in GitHub tramite un Web browser, è possibile selezionare la scheda **Anteprima** nella parte superiore della pagina per visualizzare in anteprima il lavoro prima di eseguire il commit. 

>[!NOTE]
>La visualizzazione in anteprima delle modifiche apportate review.docs.microsoft.com è disponibile solo per i dipendenti Microsoft

Dipendenti Microsoft: una volta che i contributi sono Stati Uniti nella filiale "Master", è possibile esaminare il contenuto prima che venga eseguito pubblicamente https://review.docs.microsoft.com/hololens?branch=master . Trovare l'articolo usando il sommario nella colonna sinistra.

## Modifica nel browser e modifica con un client desktop

La modifica nel browser è il modo più semplice per apportare modifiche rapide, ma ci sono alcuni svantaggi:

- Non si ottiene il controllo ortografico.
- Non è possibile ottenere un collegamento intelligente ad altri articoli (è necessario digitare manualmente il nome del file dell'articolo).
- Può essere un problema per caricare e fare riferimento alle immagini.

Se si preferisce non risolvere questi problemi, usare un client desktop come il [codice di Visual Studio](https://code.visualstudio.com/) con un paio di [utili estensioni](#useful-extensions) quando contribuiscono.

## Uso del codice di Visual Studio

Per i motivi elencati [sopra](#editing-in-the-browser-vs-editing-with-a-desktop-client), potrebbe essere preferibile usare un client desktop per modificare la documentazione invece di un Web browser. È consigliabile usare il [codice di Visual Studio](https://code.visualstudio.com/).

### Installazione

Seguire questa procedura per configurare il codice di Visual Studio per l'utilizzo di questo repo:

1. In un Web browser:
    1. Installare [git per il PC](https://git-scm.com/downloads).
    2. Installare il [codice di Visual Studio](https://code.visualstudio.com/).
    3. [Fork MicrosoftDocs/Mixed-Reality](#creating-a-new-article) se non è già stato fatto.
    4. Nella tua forcella seleziona **clona o Scarica** e copia l'URL.
2. Creare un clone locale della forcella nel codice di Visual Studio:
    1. Nel menu **Visualizza** selezionare **tavolozza dei comandi**.
    2. Digitare "git: clone".
    3. Incollare l'URL copiato.
    4. Scegliere la posizione in cui salvare il clone nel PC.
    5. Selezionare **Apri repo** nella finestra popup.

### Modifica della documentazione

Usare il flusso di lavoro seguente per apportare modifiche alla documentazione con il codice di Visual Studio:

>[!NOTE]
>Tutte le linee guida per la [modifica](#editing-an-existing-article) e la [creazione](#creating-a-new-article) di articoli e le [nozioni di base per la modifica di Markdown](#markdown-basics), si applicano anche quando si usa il codice di Visual Studio.

1. Verificare che la forcella clonata sia aggiornata con il repo ufficiale.
   1. In un Web browser, creare una richiesta di pull per sincronizzare le recenti modifiche da altri collaboratori in MicrosoftDocs/Mixed-Reality ' Master ' alla forcella (verificare che la freccia sia rivolta nel modo giusto).
      
      ![Sincronizzare le modifiche da MicrosoftDocs/Mixed-Reality alla tua forcella](images/sync_repos.PNG)
   2. Nel codice di Visual Studio selezionare il pulsante Sincronizza per sincronizzare il fork appena aggiornato con il clone locale.
      
      ![Fare clic sull'immagine del pulsante di sincronizzazione](images/sync_clone.png)
2. Creare o modificare articoli nel repo clonato usando il codice di Visual Studio.
   1. Modificare uno o più articoli (se necessario, aggiungere immagini alla cartella "immagini").
   2. **Salvare** le modifiche in **Esplora risorse**.
      
      ![Scegliere "Salva tutto" in Esplora risorse](images/explorer_save.png)
   3. Eseguire il **commit di tutte** le modifiche nel **controllo del codice sorgente** (messaggio di scrittura commit quando richiesto).
      
      ![Scegliere "Commit all" nel controllo del codice sorgente](images/source_control_commit.png)
   4. Selezionare il pulsante **Sincronizza** per sincronizzare di nuovo le modifiche all'origine (la forcella su GitHub).
      
      ![Fare clic sul pulsante Sincronizza](images/sync_back.png)
3. In un Web browser, crea una richiesta di pull per sincronizzare le nuove modifiche nella tua forcella in MicrosoftDocs/Mixed-Reality "Master" (assicurati che la freccia indichi il modo corretto).

   ![Creare una richiesta di pull dalla forcella in MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

### Estensioni utili

Le estensioni di codice di Visual Studio seguenti sono utili quando si modifica la documentazione:

- [Estensione docs Markdown per il codice di Visual Studio](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) : usare **ALT + M** per visualizzare un menu di opzioni per la creazione di documenti, ad esempio
   - Cercare e fare riferimento alle immagini caricate.
   - Aggiungere la formattazione, ad esempio elenchi, tabelle e chiamate specifiche per documenti `>[!NOTE]` .
   - Cercare e fare riferimento a collegamenti interni e segnalibri (collegamenti a sezioni specifiche all'interno di una pagina).
   - Gli errori di formattazione vengono evidenziati (posizionare il puntatore del mouse sull'errore per saperne di più).
- [Controllo ortografia codice](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) : le parole con errori di ortografia verranno sottolineate; fare clic con il pulsante destro del mouse su una parola con errori di ortografia per modificarla o salvarla nel dizionario.
