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