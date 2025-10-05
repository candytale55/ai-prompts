# AGENTS.md Files

## First Try

```md
# agents.md

**Purpose:**
Defines conventions, coding standards, and collaboration rules for AI-assisted development (e.g., Codex, Copilot) and human contributors.
Ensures consistent structure, readability, accessibility, and responsive behavior across all projects.

---

## 0. Agent Behavior

* Never code an entire project from scratch in one step, even if the prompt is vague or broad.
* Follow an **iterative, real-life development workflow**:

  1. Clarify requirements.
  2. Plan structure and tasks.
  3. Implement incrementally.
  4. Request or wait for feedback before continuing.
* When uncertain about the scope or intent, **ask for clarification** instead of making assumptions.
* Always align outputs with the conventions defined in this document before generating or editing code.

---

## 1. HTML Standards

* Always include essential document structure and meta tags:

  <!DOCTYPE html>  

  <html lang="en">  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Page Title</title>  
* Use **semantic HTML** (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`).
* Include **accessibility features**:

  * Use `aria-label`, `role`, and relevant attributes where needed.
  * Always add `alt=""` to images (leave empty only if decorative).
* For empty or temporary links, use `href="#"` (never leave `href` empty).
* Keep HTML minimal — only add extra `<div>`s when required for layout (Flexbox or Grid).
* Use **classes** for styling; **IDs** only for unique or interactive elements.

---

## 2. Naming & Structure

* File and folder names: **kebab-case**, all lowercase.
* Class names: **kebab-case**, descriptive (e.g., `.main-header`, `.blog-card`).
* IDs: only for unique, functional anchors or JS targets.
* Mapping between HTML & JS:

  * `.class-name` → `className` (camelCase in JavaScript).
* Add a short comment at the top of each file describing its purpose.
* Reference files in the same folder with relative paths (`./`).

---

## 3. CSS & Styling

* Begin each stylesheet with a reset:
  *, *::before, *::after { box-sizing: border-box; }
  body { margin: 0; }
* Use **CSS variables** with descriptive names:

  * Simple pages → `--dark-red`, `--light-gray`
  * Complex sites → group by function: `--accent-color`, `--header-bg`, `--font-primary`
* Use `.container` for layout wrappers (or semantic tag with `.container` when simple).
* Prefer **mobile-first** styling; scale up with `min-width` media queries.

---

## 4. Units & Responsive Design

* Design mobile-first, then enhance for larger screens with media queries.
* Preferred units:

  * `rem` → typography (root-relative)
  * `em` → spacing within components
  * `%`, `vw`, `vh` → fluid layouts
  * `px` → small borders or fine adjustments
* Limit text width for readability (e.g., `max-width: 60ch`).
* Test designs at 320px, 768px, and 1024px+ viewports.

---

## 5. JavaScript Guidelines

* Use **vanilla JS (ES6+)** unless otherwise requested.
* Keep functions modular and descriptive.
* Use **camelCase** for variable and function names.
* Load scripts with `defer` or place before the closing `</body>` tag.
* Use clear DOM references:
  const menuButton = document.getElementById("menu-btn")
  const navLinks = document.querySelector(".nav")

---

## 6. Version Control & Documentation

* Each commit represents one **logical, self-contained step**.
* **Commit message format:**
  type(scope): short summary
  Examples:

  * feat(nav): add responsive toggle
  * fix(css): correct header spacing
  * docs(readme): update setup instructions
* **Pull request summary:**
  short description: concise overview
  summary:

  * key actions in bullet points
* Update `README.md` when structure, setup, or purpose changes.

---

## 7. Basic Testing

**Goal:** Ensure core functionality, accessibility, and responsiveness before merging.

Run these quick checks:

* ✅ Validate HTML and CSS using online or IDE validators.
* ✅ Confirm all links are valid (no empty `href` attributes).
* ✅ All images include `alt` text (blank if decorative).
* ✅ Navigation is usable with keyboard (Tab, Enter).
* ✅ Text contrast passes WCAG AA standards.
* ✅ Layout adjusts correctly for mobile (320px), tablet (768px), and desktop (1024px+).
* ✅ Console has no JS errors or undefined variables.

---

## 8. SEO & Metadata

* Add SEO tags after layout and content are finalized.
* Each page should include:

  * `<title>` and `<meta name="description">`
  * Open Graph and Twitter meta tags if relevant.
```

✅ **Tip:**
If new contributors or AI agents join, they must read and follow this document before editing or generating code.
