
# ChatGPT + Google Sheets Integration Guide

*Created on* **2025-09-15**

---

## Overview:

Explains how to connect **ChatGPT** with **Google Sheets** for task automation, content generation, and dataset creation.

**Intended Use Case:**

* Educators, content creators, and professionals who want to quickly generate structured content (tables, prompts, examples) inside Google Sheets.

**Compatibility:**

* **OpenAI API** (GPT-4o, GPT-4o-mini, GPT-4.1)**.
* Google Sheets via **Workspace Add-on** or **Apps Script**.

---

## Example Workflow:

1. Decide your connection method:

   * **Extension** (faster, no code)
   * **Apps Script** (more control, safer for API keys)

2. Prepare your sheet:

   * Column A: topics or hacks.
   * Column B+: formulas calling GPT (example generation, IA steps, final prompts).

3. Drag formulas down to expand into multiple rows/datasets.

4. Export results into **Google Docs / Canva** for final formatting and publication.

---

## Options to Connect:

### Option 1 - Third-party Extension

* Install: [GPT for Sheets and Docs](https://workspace.google.com/marketplace/app/gpt_for_sheets_and_docs/677318054654)
* Set API Key via **Extensions → GPT for Sheets and Docs → Set API Key**
* Functions available:

  * `=GPT("...")` → single output
  * `=GPT_LIST("...")` → bullet list
  * `=GPT_TABLE("...")` → table expanded across cells

---

### Option 2 - Direct API Integration with Apps Script

1. Open **Extensions → App Script** in your Google Sheet.
2. Save your API Key in **Script Properties** (`OPENAI_API_KEY`).
3. Add this function:

```javascript
function GPT(prompt) {
  var apiKey = PropertiesService.getScriptProperties().getProperty("OPENAI_API_KEY");
  var url = "https://api.openai.com/v1/chat/completions";
  var payload = {
    "model": "gpt-4o-mini",
    "messages": [{"role": "user", "content": prompt}],
    "max_tokens": 500
  };
  var options = {
    "method": "post",
    "headers": {
      "Authorization": "Bearer " + apiKey,
      "Content-Type": "application/json"
    },
    "payload": JSON.stringify(payload)
  };
  var response = UrlFetchApp.fetch(url, options);
  var json = JSON.parse(response.getContentText());
  return json.choices[0].message.content.trim();
}
```

4. Back in your sheet, call GPT:

```excel
=GPT("Escríbeme un chiste corto sobre programadores")
```

---

## PROMPTS:

### Prompt 1 - Generate Topics (Column A)

```markdown
Give me 20 hacks that people can implement immediately using GPT Plus and Google Sheets to automate tasks in less than 15 minutes. Return only the hack names in a clean list.
```

### Prompt 2 - Example Implementation (Column C)

```markdown
Provide a concise example (max 4 steps, no extra titles) of how to implement the hack in less than 15 minutes and with minimal cost: [HACK_NAME].
```

### Prompt 3 - IA Assistant Actions (Column D)

```markdown
From the listed steps, extract ONLY those that must be executed by the AI assistant. Return them as bullet points.
```

### Prompt 4 - Final User Prompt (Column E)

````markdown
Based on the AI actions, generate the exact prompt a user should copy and paste into ChatGPT. 
Output must be inside a markdown code block (```markdown … ```), without explanations or extra text.
````

---

## Suggestions:

1. Use **constraints** like “max 4 steps” or “max 80 words” to avoid verbose answers.
2. **Test with one row first**, then drag formulas down.
3. For publication-ready material, export to **Docs** or **Canva** after generating in Sheets.

Perfecto 🙌. Te armo un **documento inicial en markdown** siguiendo la misma estructura que tu ejemplo, pero aplicado a **“Cómo usar ChatGPT con Google Sheets”**, con lo que hemos visto:

* Opción con extensión de terceros (GPT for Sheets and Docs).
* Opción con API Key propia en Apps Script.
* Ejemplo de función.
* Prompt inicial para generar temas/instrucciones/prompts en una hoja de cálculo.

---

# ChatGPT + Google Sheets Integration Guide

*Created on* **2025-09-15**

---

## Overview:

**Purpose / Description:**
Explains how to connect **ChatGPT** with **Google Sheets** for task automation, content generation, and dataset creation.
Covers both **third-party extension setup** and **direct API integration via Apps Script**.

**Intended Use Case:**

* Educators, content creators, and professionals who want to quickly generate structured content (tables, prompts, examples) inside Google Sheets.
* Learners practicing **prompt engineering** and automation.

**Compatibility:**

* Works with **OpenAI API (GPT-4o, GPT-4o-mini, GPT-4.1)**.
* Google Sheets via **Workspace Add-on** or **Apps Script**.

---

## Example Workflow:

1. Decide your connection method:

   * **Extension (faster, no code)**
   * **Apps Script (more control, safer for API keys)**

2. Prepare your sheet:

   * Column A: topics or hacks.
   * Column B+: formulas calling GPT (example generation, IA steps, final prompts).

3. Drag formulas down to expand into multiple rows/datasets.

4. Export results into **Google Docs / Canva** for final formatting and publication.

---

## Options to Connect:

### Option 1 - Third-party Extension

* Install: [GPT for Sheets and Docs](https://workspace.google.com/marketplace/app/gpt_for_sheets_and_docs/677318054654)
* Set API Key via **Extensions → GPT for Sheets and Docs → Set API Key**
* Functions available:

  * `=GPT("...")` → single output
  * `=GPT_LIST("...")` → bullet list
  * `=GPT_TABLE("...")` → table expanded across cells

---

### Option 2 - Direct API Integration with Apps Script

1. Open **Extensions → App Script** in your Google Sheet.
2. Save your API Key in **Script Properties** (`OPENAI_API_KEY`).
3. Add this function:

```javascript
function GPT(prompt) {
  var apiKey = PropertiesService.getScriptProperties().getProperty("OPENAI_API_KEY");
  var url = "https://api.openai.com/v1/chat/completions";
  var payload = {
    "model": "gpt-4o-mini",
    "messages": [{"role": "user", "content": prompt}],
    "max_tokens": 500
  };
  var options = {
    "method": "post",
    "headers": {
      "Authorization": "Bearer " + apiKey,
      "Content-Type": "application/json"
    },
    "payload": JSON.stringify(payload)
  };
  var response = UrlFetchApp.fetch(url, options);
  var json = JSON.parse(response.getContentText());
  return json.choices[0].message.content.trim();
}
```

4. Back in your sheet, call GPT:

```excel
=GPT("Escríbeme un chiste corto sobre programadores")
```

---

## PROMPTS:

### Prompt 1 - Generate Topics (Column A)

```markdown
Give me 20 hacks that people can implement immediately using GPT Plus and Google Sheets to automate tasks in less than 15 minutes. Return only the hack names in a clean list.
```

### Prompt 2 - Example Implementation (Column C)

```markdown
Provide a concise example (max 4 steps, no extra titles) of how to implement the hack in less than 15 minutes and with minimal cost: [HACK_NAME].
```

### Prompt 3 - IA Assistant Actions (Column D)

```markdown
From the listed steps, extract ONLY those that must be executed by the AI assistant. Return them as bullet points.
```

### Prompt 4 - Final User Prompt (Column E)

````markdown
Based on the AI actions, generate the exact prompt a user should copy and paste into ChatGPT. 
Output must be inside a markdown code block (```markdown … ```), without explanations or extra text.
````

---

## Suggestions:

1. Use **constraints** like “max 4 steps” or “max 80 words” to avoid verbose answers.
2. **Test with one row first**, then drag formulas down.
3. For publication-ready material, export to **Docs** or **Canva** after generating in Sheets.

