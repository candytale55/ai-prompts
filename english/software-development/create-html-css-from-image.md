# Convert Image to Semantic HTML & CSS

## Description

This prompt converts a provided image into **clean, semantic, and maintainable HTML and CSS**. Two versions are included: a robust one for full projects and documentation, and a minimalist one for quick prototyping.

---

## Prompts

### 🔹 Robust Version

**Case of use:** when you need production-quality output with accessibility, responsive design, and clear structure (recommended for documentation or portfolio work).

````md
Convert the image I provide into **clean, semantic, maintainable HTML and CSS**.  

### Output
- Provide two separate files in code blocks:  
  - `index.html` wrapped in ```html  
  - `styles.css` wrapped in ```css  
- Do not include inline styles.  
- If any content is unclear from the image, add a comment explaining the assumption instead of inventing details.  

### HTML Rules
* Use **semantic HTML tags** whenever possible (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`, `<ul>`, `<li>`, `<figure>`, `<figcaption>`, `<button>`, `<form>`, `<label>`, `<input>`, `<h1>`–`<h6>`, `<p>`, `<a>`, etc.).  
* Use `<div>` **only for containers/wrappers**.  
* Use **descriptive, consistent class names** (e.g., `btn-primary`, `card-header`).  
* All links to **external files** (CSS, JS, images, fonts) and **between pages** must use the `./` prefix.  
* Image, logo, and icon paths must be **placeholders** in `./images/` with descriptive names and `alt` attributes (e.g., `./images/logo-placeholder.png`, alt="Company logo").  
* Ensure correct **heading hierarchy** and add ARIA roles when appropriate.  

### CSS Rules
* Use only an **external stylesheet** (`./styles.css`).  
* Define **CSS variables** in `:root` for recurring values (colors, font sizes, spacing) with descriptive names.  
  - Example: `:root {--primary-color: #123456;}`  
* **Unit conversions:**  
  * `px → rem` for typography, buttons, UI elements. Add comment with original px value.  
  * `px → em` for padding/margins inside components.  
  * Use `%`, `vh`, or `vw` for responsive layouts.  
* Use **Flexbox or Grid** for layouts.  
* Add at least one **@media query** to demonstrate responsiveness.  
* Keep selectors **simple and consistent**, avoid unnecessary nesting.  
````

---

### 🔹 Minimalist Version

**Case of use:** when speed matters, or for quick prototyping without full documentation overhead.

````md
Convert the image I provide into semantic, maintainable HTML and CSS.  

### Output
- Two code blocks:  
  - `index.html` in ```html  
  - `styles.css` in ```css  

### HTML
- Use semantic tags (`header`, `main`, `section`, `article`, `footer`, `nav`, etc.).  
- `<div>` only as wrappers.  
- Descriptive, consistent class names.  
- File paths must use `./`.  
- Images/icons/logos → `./images/[placeholder-name].png` with alt text.  
- Keep heading hierarchy correct.  

### CSS
- No inline styles, only `./styles.css`.  
- Use CSS variables in `:root`.  
- px → rem for text/UI, px → em for spacing. Add px value in comment.  
- Use Flexbox/Grid for layout.  
- Include at least one media query.  
````
---
PREVIOUS VERSION



# Extract Design into HTML + CSS

```md
Convert the image that I'm going to give you into **clean, semantic, maintainable HTML and CSS**.

### HTML Rules

* Use **semantic HTML tags** whenever possible (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`, `<ul>`, `<li>`, `<figure>`, `<figcaption>`, `<button>`, `<form>`, `<label>`, `<input>`, `<h1>`–`<h6>`, `<p>`, `<a>`, etc.).
* Use `<div>` **only for containers/wrappers**.
* Use **descriptive, consistent class names**.
* All links to **external files** (CSS, JS, images, fonts) and **between pages** must use the `./` prefix.
* Image, logo, and icon paths must be **placeholders with descriptive names** and an alt description whenever possible.

### CSS Rules
* No inline styles. Always assume an **external stylesheet** (`./styles.css`).
* Use **CSS variables** for recurring values (colors, font sizes, spacing) with **descriptive names**. Example: `:root {--primary-color: #123456;}`

* Unit conversions:
  * **px → rem** for typography, buttons, UI elements. Example: `:root {--font-size-base: 1rem;} /* 16px */`
  * **px → em** for padding/margins inside components.
  * Use `%`, `vh`, or `vw` for responsive layouts.
  * Always add a **comment with the original px value** after conversion.
  * Keep **selectors simple** and avoid unnecessary nesting unless it follows CSS conventions.
  * Maintain **consistency** in class naming

```
