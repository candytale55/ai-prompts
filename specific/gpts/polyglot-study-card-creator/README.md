## Modes

* **Mode: Cleanup** → Input: raw messy text.
  **Output:**

  ```
  Sentence: <Cleaned sentence>
  Vocabulary: <word>
  Vocabulary: <phrase>
  ```

* **Mode: Extraction** → Input: clean text/excerpts.
  **Output (TSV mini-list):**

  ```
  Word [tab] Type [tab] Definition [tab] Example Sentence
  ```

* **Mode: Cards** → Input: your word list (or text with target words marked).
  **Output (full TSV row per word):**

  ```
  ID [tab] pt_example [tab] pt_ipa_PT ... [tab] Tags
  ```

  (fills spreadsheet schema; one example sentence per word, cloze blanked).

### Flowchart: Which Mode to Use?

```mermaid

flowchart TD

  A[Do you already have a list of words?] -->|YES| B[Mode: Cards<br/>Build full Anki TSV entries]
  A -->|NO| C[Do you want GPT to pick vocabulary from text?]

  C --> D{Text is messy?<br/>typos, fanfic, non-native errors}
  D -->|YES| E[Mode: Cleanup<br/>then Mode: Extraction<br/>Fix text → Extract words]
  D -->|NO| F[Mode: Extraction<br/>Extract C1–C2 words with defs + examples]

  F --> G[(Optional) Mode: Cards<br/>Turn extracted list into full TSV cards]

```


Do you already have a list of words?  
        │
        ├── YES → Mode: Cards  
        │       (Build full Anki TSV entries for these words)  
        │
        └── NO → Do you want GPT to pick vocabulary from text?  
                │
                ├── Text is messy, with typos/fanfic/non-native errors?  
                │        │
                │        ├── YES → Mode: Cleanup → then Mode: Extraction  
                │        │       (Fix text → Extract words)  
                │        │
                │        └── NO → Mode: Extraction  
                │               (Extract C1–C2 words with defs + examples)  
                │
                └── (Optional) After Extraction → Mode: Cards  
                        (Turn extracted list into full TSV cards)  
```

---


## Suggested Conversation Starters


* **Extraction** → Give text, GPT chooses vocabulary.
* **Cards** → Give words, GPT builds full TSV Anki cards.
* **Cleanup (English only)** → Use if text has typos/fanfic errors.


### Extraction Mode

* **EN:** *“Extract C1–C2 vocabulary words from this text and show me definitions and examples.”*
* **PT:** *“Extrai palavras de vocabulário de nível B1 deste texto e mostra definições e exemplos.”*

### Cards Mode

* **EN:** *“Build full Anki cards in TSV format for this list of words.”*
* **PT:** *“Cria cartões completos em formato TSV para esta lista de palavras em português.”*

### Cleanup Mode

* **EN:** *“Clean this messy fanfiction text and extract the advanced vocabulary words.”*


### Optional Add-on Starters

* **Cross-language:** *“Generate TSV cards for these English words with Portuguese translations and articles.”*
* **All-languages:** *“Generate TSV cards for these basic words across all available languages.”*


### Table of Starters

| Language                      | Mode       | Conversation Starter                                                                                 |
| ----------------------------- | ---------- | ---------------------------------------------------------------------------------------------------- |
| **English (EN)**              | Extraction | *“Extract C1–C2 vocabulary words from this text and show me definitions and examples.”*              |
|                               | Cards      | *“Build full Anki cards in TSV format for this list of words.”*                                      |
|                               | Cleanup    | *“Clean this messy fanfiction text and extract the advanced vocabulary words.”*                      |
| **Portuguese (PT)**           | Extraction | *“Extrai palavras de vocabulário de nível B1 deste texto e mostra definições e exemplos.”*           |
|                               | Cards      | *“Cria cartões completos em formato TSV para esta lista de palavras em português.”*                  |
| **French (FR)**               | Extraction | *« Extrait du vocabulaire de niveau B1-B2 de ce texte et affiche définitions et exemples. »*         |
|                               | Cards      | *« Crée des cartes complètes au format TSV pour cette liste de mots en français. »*                  |
| **German (DE)**               | Extraction | *„Extrahiere B1-B2-Vokabeln aus diesem Text und gib Definitionen und Beispielsätze an.“*             |
|                               | Cards      | *„Erstelle vollständige TSV-Karten für diese deutsche Wortliste.“*                                   |
| **Spanish (ES)**              | Extraction | *« Extrae vocabulario raro, técnico o poco común de este texto y muestra definiciones y ejemplos. »* |
|                               | Cards      | *« Crea tarjetas completas en formato TSV para esta lista de palabras en español. »*                 |
| **Italian (IT)**              | Extraction | *« Estrai il vocabolario di livello B1-B2 da questo testo e mostra definizioni ed esempi. »*         |
|                               | Cards      | *« Crea schede complete in formato TSV per questa lista di parole in italiano. »*                    |
| **Catalan / Valencian (VAL)** | Extraction | *« Extreu vocabulari de nivell B1-B2 d’aquest text i mostra definicions i exemples. »*               |
|                               | Cards      | *« Crea targetes completes en format TSV per aquesta llista de paraules en valencià/català. »*       |

---

