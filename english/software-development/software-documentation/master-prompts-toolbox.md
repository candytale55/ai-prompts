# 🧰 Master Prompts Toolbox

These are designed in **`Goal:` / `Input:`** style and ready for copy-paste.

### Created: 2025-09-19 

---

###  Commenting HTML/CSS/JS

```md
Goal:  
Add descriptive inline comments to code so it’s easier to navigate, revisit, and understand.  
- Use section headers for major parts.  
- Only explain code that’s not obvious.  
- If HTML is missing DOCTYPE, lang, charset, or viewport → add them.  
- Add accessibility improvements (aria-labels, alt, etc.) without changing structure.  
- Keep a consistent commenting style.  

Input:  
```
```
[Paste HTML, CSS, or JS here]
```

---

## Commit Message Generator

```md
Goal:  
Generate a clear commit message in markdown format.  
- Always start with a conventional prefix (feat:, fix:, refactor:, chore:, docs:, etc.).  
- Make it understandable even for non-developers.  
- Use bullet points for changes if multiple.  

Input:
```
```  
[Paste description of changes or code snippet]
```

---

### Quick & Dirty README Builder

```md
Goal:  
Create a concise README.md draft (Quick & Dirty version) with these sections:  
- **Description** (max 2 paragraphs)  
- **Technologies** (list all used)  
- **Status** (WIP or Completed + date)  
- **Live Demo** (CodePen/Netlify links if given)  
- **Screenshots** (table format, placeholders ok if no images yet)  
- **Project Structure** (copy-paste file tree if provided)  
- **TODO** (list provided or add “none yet”)  
- **Notes to Future Self** (copy my notes if included)  
- **References** (tutorials, Scrimba, etc.)  

Input:
```
```  
[Provide project info, file tree, notes, etc.]
```
---

### Final README Formatter

```md
Goal:  
Take my Quick & Dirty README plus project notes and polish it into a professional README.md ready for GitHub.  
- Keep sections: Description, Technologies, Live Demo, Status, Screenshots, Project Structure, TODO, Notes to Future Self, References.  
- Improve readability and flow.  
- Format cleanly in markdown.  
- Be concise but clear.  

Input:  
```
```
[Paste Quick & Dirty README with data filled out]
```

### Pseudocode Generator

```md
Goal:  
Convert a finished project into pseudocode comments that can be pasted into an editor as a starting point.  
- Use only comments (`//` for JS, `/* */` for CSS, `<!-- -->` for HTML).  
- Write step-by-step instructions for rebuilding the project.  
- Focus on logic and structure, not full code.  
- Mention gotchas or best practices (like avoiding compounding ems, toggling all themed elements, etc.).  

Input:
```
```  
[Paste the final code here]
```

---

### End-of-Project Packager

```md
Goal:  
Deliver a project “wrap-up” pack:  
- Commented code (HTML, CSS, JS)  
- Final README.md (professional version)  
- Commit message summarizing wrap-up  
- Optional pseudocode (if requested)  

Input:
```
```  
[Paste the final code and notes]
```
