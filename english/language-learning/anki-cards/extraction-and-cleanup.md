# Vocabulary Extraction and Cleanup

### Date: 2025

````md
You will be provided with a text that includes sentences, sentence fragments, or groups of words. Some segments will include vocabulary terms explicitly listed or marked (e.g., *after the sentence, with asterisks or on separate lines*), while others will not. Your task is to clean up and extract the appropriate vocabulary based on context.

---

## What You Need to Do

### Clean up the text:

* **Fix spelling errors** *only if they are unintended*. If slang, dialect, or stylized misspellings are intentional (e.g. "goin’", "fuckin’"), **do not correct them**.
* **Correct truly misspelled words** that are inconsistent with standard language use (e.g., *“tenants”* instead of *“tenets”*).
* **Correct commonly confused words** when the incorrect one was used in context (e.g., *“advice”* → *“advise”*).
* Do **not complete** sentences that are incomplete or intentionally cut off — preserve ellipses or truncations.

---

### Remove duplicates:

* If the same word or phrase appears multiple times in similar contexts, only return the **most illustrative version**.
* Consider meaning and clarity when choosing which version to keep.

---

###  Extract the correct vocabulary word(s):

* Vocabulary may be a **single word**, **phrasal verb**, **idiom**, or **collocation**. Return the complete phrase if that is what is implied.
* If words are **fragmented** or **incomplete**, reconstruct the full vocabulary expression from the context (e.g., “above his damned station” → *“above someone's station”*).

---

###  Handle missing or unlabeled vocabulary:

* If no vocabulary is explicitly marked, extract the **most advanced vocabulary word(s)** (CEFR level **C1–C2**).
* If all vocabulary is simple (B1 or lower), ignore the sentence.

---

## Output Format:

Each sentence must be followed by its vocabulary word(s), each on its own line using the following exact format:


```
Sentence: <Cleaned sentence or fragment>
Vocabulary: <word or phrase 1>
Vocabulary: <word or phrase 2>
...
```

⚠️ Do not include explanations or notes — only the cleaned sentence and extracted vocabulary.


---

###  Examples

```
Nah, it weren’t you. You were upfront from the get-go. It’s the fuckin’ Company I can’t trust.
be upfront
from the get-go

No one has the time or energy to be grindin’ fuckin’ flour down here you twat.
twat

The Silent community held a lot of sway, especially in areas where the mines were involved.
sway

[...] display of knives, swords, gauntlets, and other fine metalwork.
gauntlets
metalwork
```


Examples with mistakes in the original sentences :

The _tenants_ of liberal thought include freedom of speech and tolerance.
... noded his head ...

```
It is a basic tenets of democracy that power should remain as close as possible to the people.
tenets

The boy nodded his head vigorously. His eyes were guileless, and his smile bright and gap-toothed.
guileless

Sentence: Having a notched or battlemented top, like that of a fortress or a crenellated wall.
notched
battlemented
crenellated
```

---

### Notes

* Use sentence context to **disambiguate** meaning.
* If no vocabulary is listed, look for **unfamiliar or technical words**.
* **Do not repeat entries** unless they appear in distinctly different contexts.

I will paste the text in the next prompt: 
````

```
[ TEXT FOR CLEAN-UP ]
```

