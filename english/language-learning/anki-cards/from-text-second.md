# From Text

Compare with the others. 

### Date: 2025

````md

# P.00.1 (Draft) Vocabulary Prompt - From Text

## Purpose
Analyze sentences containing specified vocabulary words and create a comprehensive vocabulary learning resource in tab-separated format for easy import into spreadsheets.

## Task Overview
You will receive a text. Your task is to:
1. Understand the main topic(s) and context of the sentences
2. Find vocabulary words and phrases C1 and above, including idioms, idiomatic expressions, collocations or slang words.
2. Create a tab-separated list with vocabulary analysis that helps students learn these words in context

## Output Format
Create a tab-separated list with these columns in exact order:
**[Vocabulary Word] [Grammatical Type] [Definition] [Example Sentences] [Tags]**

*Note: Use `<br>` for line breaks within cells to ensure proper spreadsheet formatting.*

---

## Column Specifications

### 1. Vocabulary Word
**Standard Format**: Use the exact form from the sentence

**Special Cases**:
- **Conjugated verbs/idioms**: Include sentence form, then dictionary form in parentheses
  - Example: "cut him loose (cut someone loose)"
  - Example: "pulled through (pull through)"
- **Regional spelling differences**: Include both variants only for common words
  - Example: "flavor (AM) / flavour (UK)"

### 2. Grammatical Type
Use standard abbreviations:
- **n** = noun
- **v** = verb  
- **adj** = adjective
- **adv** = adverb
- **prep** = preposition
- **conj** = conjunction
- **interj** = interjection

**For complex forms**, add specifications:
- **v (passive)** = passive voice
- **v (phrasal)** = phrasal verb
- **n (compound)** = compound noun

You are not limited to these.

### 3. Definition
**Length**: 8-20 words maximum

**Requirements**:
- Must reflect the word's meaning in the given context only
- Avoid definitions that make the word obvious to guess
- For conjugated verbs: Include tense in brackets, don't mention infinitive
  - Good: "[past] to encounter or find unexpectedly"
  - Bad: "past tense of come across"

**Quality Check**: Definition should help students understand usage without giving away the word.

### 4. Example Sentences
**Structure**:
1. **First sentence**: Original sentence or meaningful fragment (if over 20 words)
2. **Additional sentences**: Add 1-2 more if original doesn't clearly show meaning/usage

**Blanking System**:
- Show only first letter + underscores for remaining letters
- Each word in the vocabulary item gets this treatment
- Example: "unsociable" becomes "u________"
- Example: "been pursued" becomes "b___ p_______"

**Quality Requirements**:
- All examples must reflect the same meaning as used in the original context
- Avoid examples that could represent different meanings of the word

### 5. Tags
**Format**: Lowercase, space-separated (no commas, no tabs)
**Content**: 3-6 tags including:
- Topic/theme of the text
- Semantic field of the word
- Usage context

**Special Rules**:
- Use hyphens for compound concepts: "human-nature"
- Capitalize proper nouns/adjectives: "German"
- Focus on learning relevance

---

## Example


### Output:
```
roving	adj	constantly moving from place to place; wandering	...attract unwanted attention from the r______ bands of cannibals.<br>He joined a group of r______ mercenaries who never stayed in one town for long.	movement travel danger survival
cannibals	n	people who eat human flesh	...attract unwanted attention from... bands of c________.<br>Sailors feared landing on islands inhabited by c________.	survival violence underground danger
tendrils	n	thread-like growths or extensions; often used metaphorically	...snaking like broken t________ of spiderwebs.<br>The ivy stretched its t________ across the cracked stone wall.	nature underground description imagery
roaming	v	[present participle] moving about without a fixed destination	...cannibalistic people r______ the darkest parts of the underground tunnels.<br>She spent the afternoon r______ through the empty streets.	movement danger exploration survival
been pursued (pursue)	v (passive)	[past participle] to have been persistently followed or chased	Usually, survivors had only b___ p_______ and were getting the hell away...<br>The fugitive had b___ p_______ across two provinces by bounty hunters.	danger survival threat chase
```

---

## Quality Checklist
- [ ] All vocabulary words properly formatted with correct blanking
- [ ] Definitions are contextually accurate and appropriately challenging
- [ ] Example sentences demonstrate the same meaning as original context
- [ ] Tags are relevant and properly formatted
- [ ] Tab-separated format maintained throughout
- [ ] Line breaks coded as `<br>` where needed

## Edge Cases
- **Multiple meanings**: Use only the meaning from the given context
- **Proper nouns**: Treat as regular vocabulary with appropriate grammatical type
- **Technical terms**: Provide accessible definitions suitable for general learners
- **Archaic/rare words**: Include modern equivalent in definition if helpful

I will give you the text in the next prompt
````

```
[TEXT TO CONVERT]
```

