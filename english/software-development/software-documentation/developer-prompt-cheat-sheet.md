
# 📝 Developer Prompt Cheat Sheet

Reusable prompts for automating common tasks (commit messages, PR summaries, READMEs, pseudocode, etc.).

---

## 🔹 Code Maintenance & Git

### 1. Commit Messages

```md
Create a clear commit message using conventional commits (feat, fix, chore, refactor, etc.).  
Keep it concise but understandable by non-devs.  
Input: [short description of what I did].  
```
```md
👉 Example Input: *“added isGameOver state and useEffect for game end condition”*
👉 Example Output: `feat: add game-over state and effect to detect when all cards matched`
```
---

### 2. Pull Request Summaries

```
Summarize these commits into a clean PR summary using markdown.  
- Use bullet points, no bold.  
Input: [list of commit messages].  
```

---

## 🔹 Documentation

### 3. README.md

```
Generate a GitHub-ready README.md for this project.  
Sections:  
- Description (1–2 paragraphs)  
- Technologies  
- Live Demo  
- Status  
- Screenshots (table)  
- Project Structure  
- TODO  
- Notes to Future Self  
- References  

Input: [project details].  
```

---

### 4. Pseudocode Guides

```
Write a step-by-step pseudocode guide in markdown.  
Format: single-line comments (// for JS, <!-- for HTML, /* for CSS */).  
Goal: user can copy-paste into their editor and use it as scaffolding.  
Input: [project type/goal].  
```

---

## 🔹 Code Comments & Navigation

### 5. Add Inline Comments

```
Add concise inline comments to this codebase.  
- Separate major sections with headers.  
- Only explain functionality where needed (don’t state the obvious).  
- Keep style consistent.  
Input: [paste code].  
```

---

### 6. Accessibility Enhancements

```
Improve accessibility in this HTML by adding attributes only (aria-labels, alt text, roles).  
Don’t change structure or add new elements.  
Input: [paste code].  
```

---

## 🔹 Learning Aids

### 7. Concept Summaries

```
Summarize this CSS/JS concept into a practical cheat sheet.  
- Keep it concise but practical.  
- Use bullet points or numbered steps.  
- Include do/don’t guidance if relevant.  
Input: [transcription or notes].  
```

---

### 8. Notes to Future Self

```
Turn this explanation into “Notes to Future Self”:  
- Informal tone.  
- Direct, clear reminders.  
Input: [explanation].  
```

---

## 🔹 Styling Experiments

### 9. CSS Playground Values

```
Add all possible values for [property] as commented-out rules in the CSS.  
Goal: user can uncomment to experiment.  
Input: [CSS snippet].  
```