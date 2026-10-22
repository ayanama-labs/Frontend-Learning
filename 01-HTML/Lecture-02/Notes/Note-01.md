# 9. HTML5 Fundamentals

## 9.1 What is HTML5?

**HTML5** is the modern version of HTML used to structure web pages and web applications.

It introduced:

- Semantic elements
- Native audio/video
- Canvas and SVG support
- Better forms
- Improved APIs
- Simpler document structure
- Better accessibility and SEO

---

## 9.2 New HTML5 Doctype

### Old HTML4

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN">
```

### HTML5

```html
<!DOCTYPE html>
```

### Important

`<!DOCTYPE html>`:

- Tells the browser to use **standards mode**
- Is **not an HTML element**
- Is a declaration, not a tag
- Is case-insensitive, but lowercase is conventional
- Does not specify an HTML version explicitly

Typical HTML5 document:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Page</title>
  </head>
  <body></body>
</html>
```

---

## 9.3 Semantic Elements Overview

HTML5 introduced elements that describe the **meaning/purpose** of their content.

Instead of:

```html
<div id="header">...</div>
<div id="nav">...</div>
<div id="content">...</div>
```

Use:

```html
<header>...</header>
<nav>...</nav>
<main>...</main>
```

### Why semantic HTML?

Semantic elements improve:

- **Accessibility** → screen readers understand page structure
- **SEO** → search engines can better understand content
- **Maintainability** → code communicates its purpose
- **Readability** → easier for developers to understand

> Semantic HTML describes **what content means**, not how it looks.

---

## 9.4 Browser Compatibility

HTML5 features are implemented by modern browsers such as:

- Chrome
- Firefox
- Edge
- Safari

However, browser support can differ for newer/less-common APIs.

### Important principle

**HTML elements generally degrade gracefully**, but individual HTML/CSS/JS features may have different levels of browser support.

You can check compatibility using resources such as **MDN** and **Can I Use**.

For older browsers, techniques may include:

- Polyfills
- Feature detection
- Progressive enhancement
- Fallback content

### Feature detection

Don't assume a feature exists; test for it when necessary.

```js
if ("geolocation" in navigator) {
  // use geolocation
}
```

---

# 10. Semantic HTML

Semantic HTML means choosing an HTML element based on the **meaning of the content**.

### Non-semantic

```html
<div class="header"></div>
<div class="content"></div>
<div class="footer"></div>
```

### Semantic

```html
<header></header>
<main></main>
<footer></footer>
```

---

# 10.1 `<header>`

Represents introductory content for:

- A page
- A section
- An article

Common contents:

- Logo
- Heading
- Introduction
- Navigation

```html
<header>
  <h1>My Website</h1>
  <nav>...</nav>
</header>
```

**Important:** `<header>` does not necessarily mean "top of the entire page." A section/article can also have its own header.

---

# 10.2 `<footer>`

Represents footer information for a page or section.

Common contents:

- Copyright
- Author information
- Related links
- Contact information

```html
<footer>
  <p>© 2026 My Website</p>
</footer>
```

A document or individual `<article>`/`<section>` can have its own footer.

---

# 10.3 `<nav>`

Represents a **major navigation section**.

```html
<nav>
  <a href="/">Home</a>
  <a href="/about">About</a>
  <a href="/contact">Contact</a>
</nav>
```

### Important

Don't wrap every collection of links in `<nav>`.

Use it for significant navigation such as:

- Main navigation
- Table of contents
- Pagination navigation
- Major site sections

---

# 10.4 `<main>`

Represents the **primary content** of the document.

```html
<main>
  <h1>HTML Tutorial</h1>
  <p>Learn HTML...</p>
</main>
```

### Important rules

Normally:

- One `<main>` per document
- Should contain the central content
- Should not contain repeated site-wide content such as the main navigation or footer

Typical structure:

```html
<body>
  <header>...</header>

  <nav>...</nav>

  <main>...</main>

  <footer>...</footer>
</body>
```

---

# 10.5 `<article>`

Represents **self-contained content** that could stand on its own or potentially be distributed independently.

Examples:

- Blog post
- News article
- Forum post
- Product review
- Comment

```html
<article>
  <h2>What is HTML?</h2>
  <p>HTML is a markup language...</p>
</article>
```

### Test

Ask:

> "Could this content make sense independently?"

If yes, `<article>` may be appropriate.

---

# 10.6 `<section>`

Represents a **thematic grouping of content**.

```html
<section>
  <h2>HTML Basics</h2>
  <p>...</p>
</section>
```

A section usually has a heading.

### Difference

**`article`** → independently distributable/self-contained content.

**`section`** → thematic grouping within a document.

Example:

```html
<article>
  <h1>Learn HTML</h1>

  <section>
    <h2>HTML Elements</h2>
    ...
  </section>

  <section>
    <h2>HTML Attributes</h2>
    ...
  </section>
</article>
```

An `<article>` can contain multiple `<section>` elements.

---

# 10.7 `<aside>`

Represents content that is **indirectly related** to the surrounding content.

Examples:

- Sidebar
- Related articles
- Author bio
- Advertisements
- Supporting information

```html
<aside>
  <h2>Related Articles</h2>
  <a href="#">Learn CSS</a>
</aside>
```

Think:

> **Main content + supplementary content → `<aside>`**

---

# 10.8 `<figure>`

Represents **self-contained content**, commonly an illustration, diagram, image, chart, or code example.

```html
<figure>
  <img src="diagram.png" alt="HTML document structure" />
</figure>
```

The figure can be moved elsewhere without destroying the main flow of the document.

---

# 10.9 `<figcaption>`

Provides a caption/description for a `<figure>`.

```html
<figure>
  <img src="diagram.png" alt="HTML structure" />
  <figcaption>Basic structure of an HTML document.</figcaption>
</figure>
```

### Relationship

```text
<figure>
    ├── content
    └── <figcaption>
```

`<figcaption>` must be associated with its `<figure>`.

---

# 10.10 `<time>`

Represents a **specific date, time, or duration** in a machine-readable way.

```html
<time datetime="2026-10-04">October 4, 2026</time>
```

Date and time:

```html
<time datetime="2026-10-04T18:30">October 4 at 6:30 PM</time>
```

Duration:

```html
<time datetime="PT2H">2 hours</time>
```

### Why `datetime`?

Humans see:

```text
October 4, 2026
```

Machines can reliably understand:

```text
2026-10-04
```

---

# 10.11 Putting Everything Together

A typical semantic page:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Blog</title>
  </head>

  <body>
    <header>
      <h1>My Blog</h1>

      <nav>
        <a href="/">Home</a>
        <a href="/blog">Blog</a>
      </nav>
    </header>

    <main>
      <article>
        <header>
          <h2>Learning HTML</h2>
          <p>
            Published
            <time datetime="2026-10-04">October 4, 2026</time>
          </p>
        </header>

        <section>
          <h3>Semantic HTML</h3>
          <p>Semantic HTML gives content meaningful structure.</p>
        </section>

        <figure>
          <img src="html.png" alt="HTML structure" />
          <figcaption>Basic HTML document structure.</figcaption>
        </figure>

        <footer>
          <p>Written by Ayan</p>
        </footer>
      </article>

      <aside>
        <h2>Related Posts</h2>
        <a href="#">Learn CSS</a>
      </aside>
    </main>

    <footer>
      <p>© 2026 My Blog</p>
    </footer>
  </body>
</html>
```

## Quick Revision Table

| Element        | Purpose                              |
| -------------- | ------------------------------------ |
| `<header>`     | Introductory/header content          |
| `<footer>`     | Footer information                   |
| `<nav>`        | Major navigation                     |
| `<main>`       | Primary page content                 |
| `<article>`    | Self-contained/distributable content |
| `<section>`    | Thematic grouping                    |
| `<aside>`      | Related/supplementary content        |
| `<figure>`     | Self-contained visual/content        |
| `<figcaption>` | Caption for figure                   |
| `<time>`       | Machine-readable date/time/duration  |

### The key distinction to remember

```text
<header>   → introductory content
<nav>      → navigation
<main>     → primary content
<article>  → standalone content
<section>  → thematic grouping
<aside>    → supplementary content
<footer>   → footer information
<figure>   → self-contained media/content
<figcaption> → figure caption
<time>     → date/time/duration
```

## **Core idea:** Semantic HTML is primarily about giving the document a meaningful structure that browsers, assistive technologies, search engines, and developers can understand.

## 🔥 Advanced HTML Forms

### 1. New Input Types

Give browsers context + built-in UI.

- `email` → must be valid email.
- `url` → must be valid URL.
- `number` → numeric input with min/max/step.
- `date`, `time`, `datetime-local` → pickers.
- `range` → slider.
- `color` → color picker.
- `tel`, `search` → optimized keyboards on mobile.

---

### 2. Validation Attributes

Built-in checks, no JS needed.

- `required` → field can’t be empty.
- `pattern` → regex rule.
- `min`, `max`, `step` → numeric/date limits.
- `maxlength`, `minlength` → text length control.

---

### 3. Datalist

Autocomplete suggestions.

```html
<input list="browsers" />
<datalist id="browsers">
  <option value="Chrome"></option>
  <option value="Firefox"></option>
</datalist>
```

---

### 4. Fieldset & Legend

For grouping + accessibility.

```html
<fieldset>
  <legend>Personal Info</legend>
  <input type="text" name="name" />
</fieldset>
```

---

#### 🗝️ Core Idea

- **Input types** = better semantics & UI.
- **Validation** = safer forms without JS.
- **Datalist** = smart suggestions.
- **Fieldset/Legend** = structure + clarity.

---

## ⚡ Advanced Tables – Quick Revision

### 1. Table Sections

- `<thead>` → header rows (titles).
- `<tbody>` → main data.
- `<tfoot>` → summary/footer.

```html
<table>
  <thead>
    <tr>
      <th>Item</th>
      <th>Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Apple</td>
      <td>$5</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total</td>
      <td>$5</td>
    </tr>
  </tfoot>
</table>
```

---

### 2. Column & Row Spanning

- `colspan="n"` → span across columns.
- `rowspan="n"` → span across rows.

```html
<tr>
  <th rowspan="2">Name</th>
  <th colspan="2">Scores</th>
</tr>
```

---

### 3. Caption

Table title, improves clarity + accessibility.

```html
<caption>
  Student Marks
</caption>
```

---

### 4. Accessibility

- `scope="col"` / `scope="row"` in `<th>`.
- `headers` attribute for complex tables.
- Always use `<caption>` for context.

```html
<th scope="col">Month</th>
<th scope="row">January</th>
```

---

#### 🗝️ Takeaway

- **thead/tbody/tfoot** = structure.
- **rowspan/colspan** = merge cells.
- **caption** = title.
- **scope/headers** = screen reader friendly.

---
