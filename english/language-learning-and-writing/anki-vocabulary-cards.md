# Prompts to create ANKI cards in English

### Created: ~2024 

## Prompt for Reader Extractions

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

## Cards with example sentences and tags

````md
From a text or a list with words and phrases in English

Display a tab separated list, that can be easily copy-pasted, in English, that contains this output in this exact order: [Vocabulary Word] [Grammatical Type (abbreviation)] [Definition] [Example Sentence] [Tags]

- The Vocabulary Word can be a single word, a compound word, idiomatic expression or phrase.
- If there's a loose word before or after a sentence, the sentence is given as context for the meaning. 
- If there aren't any loose words next to a sentence e that is using it, choose any English above C1-level words found in the text, or the most difficult ones.
- The meaning of the Vocabulary Word should match the context.
- The Definition of the word should include nuances and usage clarifications if applicble.
- If the Vocabulary Word is a conjugated verb, do not mention the infinitive in the Definition, and use the verb tense found in the text as the Verb Word but add the nfinitive between parenthesis next to it.
- The Example Sentence must show only the first letter of each word(s) in the vocabulary item followed by a line, so the user can guess the word. If the word is a compound word, add the second word initial too. 
- The Example Sentence should be long enough to show context. 
- The Tags should be few and concise and related to the context. Separate tags with tabs or spaces (do not use commas).
- For compound words in Tags, use hyphens.
- If the Vocabulary Word has a clear difference in spelling or usage between American and British English, include both versions, indicating the locale as (AM) or (UK) next to each one. Do this only for commonly used words.


## Example:

### I give you this:

```
And then, like he realized something, he immediately yanked the glasses off and shoved them into the pocket of his jacket.

*****

yanked

*****

I noticed how he didn’t put the glasses back on—even though he had to squint hard at the fine print now.

*****

You look like some hotshot librarian who could kill a man with a book spine and I’m trying very hard not to get arrested right now,

*****

Blade handed over the finished stack of paperwork with a sheepish huff,

*****

sheepish

*****

you know how you and Erwin love dragging those out for hours.”

*****

dragging

*****

It was worth every bit of dragging him by the scruff of the neck toward basic self-care.

*****

scruff

*****

I thought back to earlier. Levi had leaned in, voice low and gruff and far too steady:"You look like some hotshot librarian who could kill a man with a book spine

*****

gruff

*****

I couldn’t help the smug flicker of pride in my chest

*****

flicker

*****

Like a storm in human form. I wasn’t even aware I was full-on staring until Eren elbowed me in the ribs. “Gross,”

*****

full-on

*****

You can ogle me all you want, but do it while walking. I’m getting water. You’re coming with me.

*****

ogle

*****

“You were ogling.” “I mean,” I shrugged, lips twitching. “You looked really good.

*****

ogling
```


### I expect:

```
yanked (yank)	v	[past] Pulled suddenly and forcefully.	He immediately y_______ the glasses off.	force sudden
sheepish	adj	Showing embarrassment from shame or a lack of self-confidence.	Blade handed over the stack with a s_______ huff.	emotion embarrassment
dragging (drag)	v	[gerund] Prolonging or extending something unnecessarily.	You and Erwin love d_______ those out.	time frustration
scruff	n	The back of the neck, especially when referring to being grabbed or led by it.	Dragging him by the s_______ of the neck.	physical body-handling
gruff	adj	Rough or abrupt in manner or voice.	Levi had leaned in, voice low and g______.	tone personality
flicker	n	A brief or subtle movement or feeling.	I couldn’t help the smug f_______ of pride.	emotion subtlety
full-on	adj	Complete or intense to the maximum degree.	I wasn’t even aware I was f___-o__ staring.	intensity behavior
ogle	v	To look at someone with obvious sexual or romantic interest.	You can o_______ me all you want, I know I look good.	gaze attraction
ogling (ogle)	v	[gerund] Looking at someone in a way that shows strong attraction.	“You were o_______.” “Well, you looked really good.”	gaze attraction
```

I will give you the list in the next prompt
```` 

Please help me create the GPT for this purpose. 