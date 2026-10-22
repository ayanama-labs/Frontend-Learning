# 🟢 Level 1 — HTML5 & Semantic HTML

### Exercise 1 — Personal Profile

Build a page containing:

- `<header>`
- `<nav>`
- `<main>`
- `<section>`
- `<article>`
- `<aside>`
- `<footer>`

Content:

```text
Your Name
About | Projects | Contact

About Me
A short introduction.

Projects
Project 1
Project 2
Project 3

Latest Article
Title
Article content...

Related Links
Link 1
Link 2

Copyright information
```

**Rules:**

- Don't use `<div>` unless you genuinely need it.
- Use the most appropriate semantic element for each piece of content.

---

### Exercise 2 — Convert Non-Semantic HTML

You are given:

```html
<div class="header">
  <div class="logo">My Website</div>

  <div class="navigation">
    <div>Home</div>
    <div>About</div>
    <div>Contact</div>
  </div>
</div>

<div class="content">
  <div class="article">
    <h1>My Article</h1>
    <p>...</p>
  </div>

  <div class="sidebar">
    <p>Related links</p>
  </div>
</div>

<div class="footer">Copyright 2026</div>
```

Rewrite it using **semantic HTML5 elements**.

---

# 🟢 Level 2 — Semantic HTML Reasoning

### Exercise 3 — Choose the Correct Element

For each situation, decide which element you would use:

1. Website navigation
2. Main content of the page
3. Independent blog post
4. Sidebar containing related information
5. A standalone image with a caption
6. Copyright information
7. A group of related content
8. Page header
9. Page footer
10. Publication date
11. A quotation
12. A list of search results

Don't just write the answer. **Explain why your chosen element is appropriate.**

---

### Exercise 4 — Blog Article

Create:

```text
Blog
│
├── Header
│   ├── Logo
│   └── Navigation
│
├── Main
│   └── Article
│       ├── Title
│       ├── Author
│       ├── Published date
│       ├── Introduction
│       ├── Image + caption
│       ├── Several sections
│       └── Conclusion
│
├── Aside
│   ├── Related articles
│   └── Categories
│
└── Footer
```

Use semantic HTML only.

---

# 🟡 Level 3 — Advanced Forms

### Exercise 5 — Registration Form

Build a registration form containing:

- Full name
- Username
- Email
- Password
- Confirm password
- Date of birth
- Gender
- Country
- Phone number
- Profile picture
- Bio
- Terms & conditions checkbox
- Submit button
- Reset button

Use appropriate:

- `type`
- `name`
- `id`
- `placeholder`
- `required`
- `minlength`
- `maxlength`
- `pattern`
- `autocomplete`

**Challenge:** Don't use JavaScript.

Make HTML's native validation do as much work as possible.

---

### Exercise 6 — Job Application Form

Create a job application form for a software developer.

Fields:

```text
Full Name
Email
Phone
Resume
Years of Experience
Expected Salary
Job Role
Skills
Portfolio URL
GitHub URL
Available Start Date
Work Preference
Cover Letter
Agree to Terms
Submit
```

Use appropriate HTML input types.

For example, don't automatically use:

```html
<input type="text" />
```

for everything.

---

### Exercise 7 — Datalist

Create a search field where users can select or type a programming language.

Suggestions:

```text
JavaScript
TypeScript
Python
Java
C++
C#
Go
Rust
PHP
Ruby
```

Use `<datalist>`.

Then create another datalist for selecting a country.

---

### Exercise 8 — Fieldset & Legend

Build a checkout form divided into:

```text
Personal Information
--------------------
Name
Email
Phone

Shipping Address
----------------
Address
City
State
Postal Code

Payment Information
-------------------
Card Number
Expiry
CVV

Order Options
-------------
Gift wrapping
Delivery instructions
```

Use `<fieldset>` and `<legend>` appropriately.

---

# 🟡 Level 4 — Advanced Tables

### Exercise 9 — Employee Table

Create:

| Employee | Department  | Position         | Salary    |
| -------- | ----------- | ---------------- | --------- |
| A        | Engineering | Developer        | ₹80,000   |
| B        | Design      | Designer         | ₹65,000   |
| C        | Engineering | Senior Developer | ₹1,20,000 |

Requirements:

- `<caption>`
- `<thead>`
- `<tbody>`
- `<tfoot>`
- Proper `<th>`
- `scope`

The footer should contain:

```text
Total Employees: 3
```

---

### Exercise 10 — Complex Table

Create a class timetable:

| Time  | Monday | Tuesday | Wednesday | Thursday | Friday |
| ----- | ------ | ------- | --------- | -------- | ------ |
| 9–10  | HTML   | CSS     | JS        | React    | Git    |
| 10–11 | CSS    | JS      | React     | Git      | HTML   |
| 11–12 | Break  | Break   | Break     | Break    | Break  |

Use `colspan` where appropriate.

---

### Exercise 11 — Rowspan Challenge

Create:

```text
Department | Employee | Role
Engineering | Ayan | Developer
             | Rahul | DevOps
             | Sarah | Backend
Design       | John | UI Designer
             | Mike | UX Designer
```

Use `rowspan` so that "Engineering" appears once and spans all three employees.

---

# 🟡 Level 5 — Audio & Video

### Exercise 12 — Video Player

Create a video element with:

- Controls
- Poster image
- Width
- Multiple `<source>` elements
- Caption track
- Fallback text

Example conceptual structure:

```text
Video
 ├── MP4 source
 ├── WebM source
 ├── captions
 └── fallback message
```

---

### Exercise 13 — Accessible Audio

Create a podcast player containing:

- `<audio>`
- Controls
- Multiple formats
- Description of the episode
- Transcript link

Think about what a user who **cannot hear the audio** needs.

---

# 🟡 Level 6 — Embedded Content

### Exercise 14 — YouTube Embed

Create an iframe embedding a YouTube video.

Then answer:

- What does `width` do?
- What does `height` do?
- What does `allow` do?
- What does `allowfullscreen` do?
- What does `loading="lazy"` do?
- What does `title` do?

---

### Exercise 15 — Google Maps

Create an iframe-based location section:

```text
Our Office

[Google Maps]

Address
Phone
Email
```

Make the iframe accessible.

---

# 🟠 Level 7 — Metadata & SEO

### Exercise 16 — SEO Head

Create the `<head>` for a fictional product page:

```text
Product: Samsung Galaxy S26
Website: Tech Tally
```

Include:

- Character encoding
- Viewport
- Description
- Author
- Favicon
- Open Graph title
- Open Graph description
- Open Graph image
- Open Graph URL
- Twitter/X card metadata
- Canonical URL

---

### Exercise 17 — Identify the Problem

What's wrong with this?

```html
<head>
  <title>Phone</title>

  <meta name="description" content="Phones" />

  <meta name="viewport" content="width=device-width" />

  <meta name="keywords" content="phone, mobile, smartphone" />

  <meta property="og:title" content="Phone" />

  <meta property="og:image" content="image.jpg" />
</head>
```

Find **at least 5 improvements**.

---

# 🔴 Level 8 — HTML Debugging

This is extremely important.

### Exercise 18 — Find the Errors

```html
<!DOCTYPE html>

<html>
<head>
    <title>My Website<title>
    <meta charset="UTF-8">
</head>

<body>

    <h1>Welcome</h2>

    <p>This is my website.

    <strong>Important text</em>

    <a href="about.html">About

    <img src="profile.jpg">

    <ul>
        <li>HTML
        <li>CSS
        <li>JavaScript
    </ol>

</body>
</html>
```

Find **every HTML error**.

Don't immediately use a validator.

First fix it yourself.

Then run it through the W3C validator and compare your results.

---

# 🔴 Level 9 — Build Without Looking at Notes

This is where your learning becomes strong.

## Exercise 19 — Build a Product Page

Create a complete product page for:

**Samsung Galaxy S26**

Structure:

```text
Header
 ├── Logo
 └── Navigation

Main
 ├── Product section
 │   ├── Product image
 │   ├── Product name
 │   ├── Description
 │   ├── Price
 │   └── Specifications
 │
 ├── Reviews
 │
 └── Related products

Aside
 └── Buying information

Footer
```

Requirements:

- Semantic HTML
- Table for specifications
- Figure + figcaption
- Review articles
- Links
- Metadata
- Accessible images
- Proper headings

**Don't worry about CSS yet.**

---

# 🔴 Level 10 — Build an Entire Website

### Exercise 20 — News Website

Build:

```text
┌───────────────────────────────┐
│ Header                        │
│ Logo | Home | Politics | Tech │
└───────────────────────────────┘

┌───────────────────────────────┐
│ Breaking News                 │
└───────────────────────────────┘

┌─────────────────────┬─────────┐
│ Main Articles       │ Aside   │
│                     │         │
│ Article             │ Trending│
│ Article             │         │
│ Article             │ Latest  │
└─────────────────────┴─────────┘

Footer
```

Every article should contain:

- Title
- Author
- Publication date
- Image
- Caption
- Content
- Related links

Use semantic HTML correctly.

---

# 🧠 Level 11 — Constraint Challenges

These are particularly valuable because they test **understanding rather than memorization**.

### Exercise 21

Create a navigation menu **without using `<div>`**.

---

### Exercise 22

Create a blog post **without using `<div>` anywhere**.

---

### Exercise 23

Create a contact form **without JavaScript** that validates:

- Required name
- Valid email
- 10-digit phone number
- Minimum 20-character message

---

### Exercise 24

Create a product specification table that is accessible to screen readers.

Use:

- `<caption>`
- `<th>`
- `scope`
- `<thead>`
- `<tbody>`

---

### Exercise 25

Create an image gallery where every image has:

- meaningful `alt`
- width/height
- `<figure>`
- `<figcaption>`

---

# 🧠 Level 12 — "Why?" Exercises

These will take you from **HTML user → HTML developer**.

For each question, write your answer before looking anything up.

### 26.

Why is this better?

```html
<nav>
  <a href="/">Home</a>
  <a href="/about">About</a>
</nav>
```

than:

```html
<div class="nav">
  <div onclick="...">Home</div>
  <div onclick="...">About</div>
</div>
```

---

### 27.

Why should `<label>` be associated with an `<input>`?

---

### 28.

What's the difference between:

```html
<section></section>
```

and

```html
<div></div>
```

?

---

### 29.

What's the difference between:

```html
<article></article>
```

and:

```html
<section></section>
```

?

---

### 30.

Why shouldn't you use headings simply because they look visually bigger?

---

### 31.

Why is this:

```html
<img src="photo.jpg" alt="" />
```

sometimes correct?

And why can this be incorrect?

```html
<img src="photo.jpg" alt="photo" />
```

---

# 🏆 Final Project — Intermediate HTML Challenge

Once you've completed the exercises above, build this **without looking at your notes**:

## Tech Tally — Smartphone Product Page

Since you're already interested in phone-specification websites, make this realistic.

### Page structure

```text
HTML
│
├── HEAD
│   ├── SEO metadata
│   ├── Open Graph
│   ├── favicon
│   └── viewport
│
└── BODY
    │
    ├── HEADER
    │   ├── Logo
    │   └── Navigation
    │
    ├── MAIN
    │   │
    │   ├── Breadcrumb navigation
    │   │
    │   ├── PRODUCT
    │   │   ├── Image
    │   │   ├── Name
    │   │   ├── Description
    │   │   ├── Price
    │   │   └── Links
    │   │
    │   ├── SPECIFICATIONS
    │   │   └── Accessible table
    │   │
    │   ├── REVIEWS
    │   │   └── Article × 3
    │   │
    │   └── FAQ
    │       └── details/summary
    │
    ├── ASIDE
    │   ├── Related phones
    │   └── Latest articles
    │
    └── FOOTER
```

### Restrictions

For the first attempt:

- ❌ No CSS
- ❌ No JavaScript
- ❌ No React
- ❌ No Tailwind
- ❌ No Bootstrap
- ❌ No copying from tutorials
- ✅ HTML only

Then inspect your HTML with:

1. Browser DevTools
2. W3C Validator
3. Lighthouse
4. Accessibility checker

---
