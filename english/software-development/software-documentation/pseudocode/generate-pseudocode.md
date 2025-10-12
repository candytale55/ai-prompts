
# Pseudocode Prompts

### 📅 Date: 2025-10-12

⚠️**Untested**


````markdown
# Instruction

Write pseudocode as if it were a **recipe** for recreating this project from scratch.  
Do it iteratively and in the **natural order a real developer might follow**,  
from setup to structure, styling, responsiveness, accessibility, and testing.  

Keep the process **flexible** — don’t assume a single workflow.  
The goal is to show a **realistic, high-level flow** that could apply to different types of projects.  

At each major stage, include brief **developer checks or tests** (functional, visual, or accessibility).

---

## Style and Detail

The pseudocode should read like a **recipe** —  
not overly detailed, but clear enough that someone could:  
- follow it to build the structure, or  
- hand it off to a coding assistant to implement efficiently.  

---

## Comment Syntax by Language

Each step must be in its **own comment block**, using the correct syntax and set between nested backticks:

- **HTML:** `<!-- -->`  
- **CSS:** `/* */`  
- **JavaScript:** `//`  

---

## Formatting Requirements

1. Use **Markdown suitable for GitHub**.  
2. Use **nested code blocks** properly:
   - Tabs with **triple backticks (` ``` `)** for code sections inside Markdown.  
   - Ensure code samples render correctly and are distinguishable from the outer Markdown block.  
3. Avoid emojis unless it’s a **warning or important note**.  
4. Keep the output **concise and professional**.  
5. Include **links or references** if provided.  

---

## Example Outputs

### HTML

```html
<!-- Doctype and <html> tag with lang attribute -->
<!-- <head>: include meta charset, viewport, title, and stylesheet link -->
<!-- Body: main container with header, hero, and footer -->
<!-- Placeholder content and linked script -->
```

**Test:**
✅ Open in browser — ensure layout renders, links load, and console has no errors.

---

### CSS

```css
/* Reset or base styles */
/* Apply universal box-sizing and margin reset */

/* Body styling */
/* Set background color, font, and centered flex layout */

/* Header and Hero sections */
/* Define spacing, typography, and responsive grid */

/* Responsive adjustments */
/* Use media queries to adapt layout for tablets/desktops */
```

**Tests:**
✅ Check that text is legible on mobile (min 375px).  
✅ Resize browser → confirm layout adjusts without overflow.  
✅ Verify color contrast ratio ≥ 4.5:1.

---

### JavaScript

```js
// Select main interactive elements
// Add event listeners for user actions (e.g., click, resize)
// Create helper functions for dynamic behavior
// Handle state updates and re-renders
// Integrate basic accessibility (e.g., aria attributes, focus management)
```

**Tests:**
✅ All buttons respond as expected.  
✅ Resize window → interactive elements reposition correctly.  
✅ Screen reader reads labels accurately.

---

### Example Combined Stage (HTML + JS + CSS)

```html
<!-- Add main button -->
<button id="roll-btn">Roll</button>
```

```css
/* Style roll button */
#roll-btn {
  background: #5035FF;
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 6px;
}
#roll-btn:focus {
  outline: 2px solid #fff;
  outline-offset: 3px;
}
```

```js
// Test button behavior
const btn = document.getElementById("roll-btn");
btn.addEventListener("click", () => console.log("Button works!"));

// Test accessibility
btn.focus();
```

**Tests:**
✅ Button click logs output in console.  
✅ Focus ring visible for keyboard navigation.  
✅ Passes Lighthouse accessibility audit for buttons.

---

### Output Goal

Produce clearly formatted pseudocode blocks for HTML, CSS, and JavaScript —  
each reflecting **recipe-style iterative development** and the **Markdown formatting rules** above,  
with **test examples** included at key stages (functional, visual, accessibility).

````
