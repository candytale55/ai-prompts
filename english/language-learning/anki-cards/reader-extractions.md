# Prompt for Reader Extractions

### Date: 2025

Prompt I use to cite extractions from eBooks I read with a reader that allows me to mark text.

```md
From a list with words and phrases in English

Display a tab separated list, that can be copy-pasted, in English, that contains this output in this exact order: [Vocabulary Word] [Grammatic Type] [Definition] [Example Sentence]

The list contains phrases and loose word(s) used in the phrase. The Vocabulary Word is the loose word. If there aren't any loose words next to the phrase, choose any English C1 level words contained in the phrase or the hardest word. The meaning should match the context.

## Example:

### I give you this:

"All right, then." Erwin straightened up in his chair and clasped his hands together on the desk blotter. "The Survey Corps will make it a priority to find and capture this Jaeger of yours, Hange.

---

desk blotter

---

Erwin's eyebrows were so high they nearly hovered above his head. "I never thought I'd see a titan with the zoomies before," he said.

---

zoomies

### I expect:

desk blotter        n        An item placed on a desk to protect its surface and provide a smooth area for writing or organizing papers.        He placed the envelope neatly on the leather desk blotter.
zoomies        n        A sudden burst of hyperactive energy, often resulting in frantic, excited movements or running around, typically seen in animals and sometimes humorously applied to people.        The dog got the zoomies and raced around the living room in circles.
hover        v        To remain suspended in one place in the air or just above a surface, often implying tension or anticipation.        Erwin’s eyebrows hovered so high they looked ready to lift off his face.

## I will give you the list next

```

## Vocabulary Extraction and Cleanup

This is used when there are many spelling mistakes in the original text, so it makes sense to clean it first

````md
 # Vocabulary Extraction and Cleanup

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
```
The _tenants_ of liberal thought include freedom of speech and tolerance.
... noded his head ...

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


I will give you the text in the next message. 
````
```md
[ TEXT FOR CLEAN-UP ]
```
