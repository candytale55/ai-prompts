# Summarize this AI paper.

## One-liner meta-prompt

**minimal, reusable meta-prompt** you can prepend to almost any summarization or extraction request to enforce accuracy and traceability:

* Place this at the start of your prompt (like a **system instruction**) and then add your specific task (summary, bullet points, etc.).

```md
When summarizing or extracting information, only use content explicitly present in the source text. Provide supporting references (page/section/sentence) for each claim, and explicitly state *‘not discussed in the text’* if the information is missing.
```

* Then:

```md
Write a concise summary in exactly two paragraphs, then extract a bulleted list of considerations, risks, and best practices regarding AI systems from the document below.
```



## Improved Prompt

### Updated: 2025.09.28

```md
Read the paper provided below.

1. Write a **concise summary in exactly two paragraphs**, focusing on the paper’s main arguments and findings.
2. Then, create a **bulleted list** of the most important *considerations, risks, and best practices* mentioned in the paper regarding [insert topic, e.g., artificial intelligence systems].
    * Ensure the bulleted list is distinct from the summary and highlights actionable or cautionary points.
    * Write clearly for an audience of [insert intended audience, e.g., technical practitioners / policymakers / general readers].
```

#### Specific:

```md
Read the paper provided below.

1. Write a **concise summary in exactly two paragraphs**, focusing on the paper’s main arguments and findings.
2. Then, create a **bulleted list** of the most important *considerations, risks, and best practices* mentioned in the paper regarding artificial intelligence systems.
    * Ensure the bulleted list is distinct from the summary and highlights actionable or cautionary points.
    * Write clearly for an audience of practitioners and general readers.
```




## SHORT VERSION A

Created: **2025-06-11**

> Tested with: 
> - ChatGPT
> - Perplexity

### Prompt

1. Adapt the prompt to your needs after ... _kept in mind when_
2. Provide the Technical Paper in PDF



```md 
Please provide a concise **two-paragraph summary** of this paper, highlighting its _key arguments_ and _findings_.

Additionally, extract a **bullet-point list** of important considerations, risks, or best practices mentioned in the paper that should be kept in mind when working with or developing artificial intelligence systems.
```
#### ELI follow-up

Depending on the complexity of the paper you might want to try right after: 

```md
Now please explain it like I'm 15
```
- Change the age depending on the paper complexity


## SHORT VERSION B

Created: **2025-06-09** 

Add a Paper in PDF

### Copy Paste this Prompt:
    
 **Tokens**: 44

```md

Summarize this paper in **two focused paragraphs**, covering the main objectives, methods, and conclusions. 

Then, list the **key takeaways, recommendations, or critical concerns** that practitioners or researchers should consider when working with AI.

```

Then, after the response:

```md
Now please explain it like I'm 15
```


## LONG VERSION

- Kind of verbose. 
- Tested on Claude

### Prompt
Created: **June 2025**

1. Change the information between [ for your paper ]. 

    Example [_“The Illusion of Thinking: Understanding the Strengths and Limitations of Reasoning Models via the Lens of Problem Complexity”, published in June 2025 by Apple Research._]


         
```md
**Context:**

I’m not deeply technical, so I need a clear but accurate breakdown of this paper: [“The Illusion of Thinking: Understanding the Strengths and Limitations of Reasoning Models via the Lens of Problem Complexity”, published in June 2025 by Apple Research.]

**Task 1 – Two‑Paragraph Summary:**

1. First paragraph: What is the **purpose** of the paper and **how** the authors approached the study.

2. Second paragraph: What **key findings**, **insights**, and **contributions** the paper presents.


**Task 2 – Key Considerations:**

1.  Provide a bullet-point list of the most critical **takeaways, limitations, or best practices** for anyone working with or developing AI models—especially reasoning models.

**Tone & Detail:**
* Keep language **clear and accessible** for non-specialists, but preserve technical accuracy.
* **No jargon overload**, but don’t oversimplify.
* Each bullet should be a **complete thought** you can act on or reflect on in future work.
```