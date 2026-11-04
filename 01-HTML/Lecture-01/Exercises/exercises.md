The objective is not simply to test whether you remember HTML syntax. It is to make you capable of:

1. Writing HTML without looking at documentation.
2. Choosing the right HTML element for a particular situation.
3. Understanding why HTML behaves the way it does.
4. Identifying and correcting poorly written HTML.
5. Applying concepts to real-world interfaces.
6. Explaining the underlying concepts rather than memorising definitions.

I've divided the exercises into 8 modules corresponding exactly to your Beginner Level roadmap.

# HTML Beginner — Practice Workbook

Your practice objectives

Beginner

# 8

Modules

# 64

Exercises

# 5

Exercise categories

# 8

Practical challenges

Categories covered

- Conceptual understanding
- Syntax and implementation
- Debugging and error identification
- Real-world application
- Deep reasoning and edge cases

## Module 1 — HTML Basics ✅

Topics: HTML, document structure, DOCTYPE, HTML, HEAD and BODY.

### A. Conceptual understanding ✅

1. What problem does HTML solve? Why can't we simply write plain text and expect the browser to understand the structure of a webpage?
2. Explain the difference between HTML, CSS and JavaScript using an analogy of constructing a building.
3. What happens when a browser receives an HTML document? Explain the process at a high level.
4. Why do we write `<!DOCTYPE html>` at the beginning of an HTML document? What might happen if we omit it?
5. Is `<!DOCTYPE html>` an HTML element? Explain your answer.
6. What is the difference between an HTML element and an HTML tag?

### B. Implementation ✅

7. Write a complete HTML document containing:
   - A document title: My First Webpage.
   - A heading: Welcome to HTML.
   - A paragraph introducing yourself.
   - A second paragraph explaining why you are learning HTML.
8. Create a webpage containing:
   - Your name as the heading.
   - Your profession as a paragraph.
   - Your three favourite technologies.
   - A title displayed in the browser tab.

### C. Debugging ✅

9\. Identify and correct all the errors:

```
<!DOCTYPE>
<html>
<head>
    <title>My Website</title>
</head>

<body>
    <h1>Welcome
    <p>This is my website.</p>
</body>
</html>
```

10\. Is the following HTML valid? Explain why or why not.

```
<html>
<body>
    <h1>Hello World</h1>
</body>
</html>
```

11\. What is wrong with this document?

```
<!DOCTYPE html>
<head>
    <title>My Website</title>
</head>
<body>
    <p>Hello</p>
</body>
```

### D. Deep reasoning ✅

12. Why is the `<head>` element called the head if its contents are generally not displayed on the webpage?
13. Can an HTML document contain multiple `<body>` elements? What would the browser do?
14. Is HTML case-sensitive? Would `<HTML>`, `<html>` and `<Html>` work identically?

## Module 2 — Text Fundamentals ✅

Topics: Headings, paragraphs, text formatting and comments.

### A. Conceptual understanding ✅

15. Why does HTML provide six heading levels instead of allowing us to use paragraphs with different font sizes?
16. Explain the difference between `<strong>` and `<b>`. Are they interchangeable?
17. Explain the difference between `<em>` and `<i>`.
18. What is the difference between visual formatting and semantic formatting?
19. Why shouldn't we use heading elements merely to make text bigger?
20. Can we use an `<h3>` directly after an `<h1>`? Is it invalid? Discuss the semantic implications.

### B. Implementation ✅

21\. Create a blog article containing:

- One main heading.
- Three subheadings.
- At least two paragraphs under each subheading.
- Important phrases using `<strong>`.
- Emphasised phrases using `<em>`.

22\. Create a book review containing:

- Book title.
- Author.
- Publication year.
- Your review.
- A quoted sentence using the appropriate HTML element.

23\. Create a document demonstrating:

- Deleted text.
- Inserted text.
- Highlighted text.
- Subscript.
- Superscript.
- Small print.

### C. Debugging ✅

24\. Identify the semantic problems:

```
<h1>My Blog</h1>
<h4>Introduction</h4>
<h2>My Journey</h2>
<h5>Conclusion</h5>
```

25\. Correct this HTML based on the intended meaning:

```
<p>
    This product is <b>extremely important</b>
    and you <i>must read</i> the instructions.
</p>
```

26\. Is the following appropriate HTML?

```
<p>
    <h2>About Me</h2>
    I am a web developer.
</p>
```

Explain the issue.

### D. Deep reasoning ✅

27. If CSS can make any text look like a heading, why do we still need `<h1>` through `<h6>`?
28. Do HTML comments affect the rendered webpage? Can users inspect them?

## Module 3 — HTML Elements ✅

Topics: Block vs inline elements, div, span, line breaks and horizontal rules.

### A. Conceptual understanding

29. What fundamentally distinguishes block-level and inline elements?
30. Why do `<div>` and `<span>` exist? What problems do they solve?
31. Why is `<div>` considered a generic container?
32. Is it correct to say that block elements always occupy the entire available width? Explain.
33. Can CSS change the default display behaviour of an HTML element?
34. Why should we avoid using `<br>` repeatedly to create vertical spacing?

### B. Implementation

35\. Create a profile card using only:

- `<div>`
- `<span>`
- `<p>`
- `<h2>`

Include a name, profession, location and status.

36\. Create a paragraph in which:

- One word is highlighted using `<span>`.
- One phrase is bold.
- One phrase is emphasised.

37\. Create a webpage with three distinct content sections separated by horizontal rules.

### C. Debugging

38\. What's wrong with this HTML?

```
<p>
    This is a paragraph.
    <div>This is another section.</div>
    This is still the paragraph.
</p>
```

39\. Identify the problem:

```
<span>
    <div>Hello World</div>
</span>
```

40\. Should the following code be used to create spacing between paragraphs?

```
<p>First paragraph</p>
<br><br><br>
<p>Second paragraph</p>
```

Why?

### D. Deep reasoning

41. Why can an inline element appear inside a paragraph, but a `<div>` cannot?
42. What happens when you place a block element inside an inline element? Discuss HTML parsing and browser behaviour.

## Module 4 — Links and Navigation ✅

Topics: Anchor tags, relative and absolute URLs, email links and link targets.

### A. Conceptual understanding

43. What is a hyperlink? Why is it one of the fundamental concepts behind the World Wide Web?
44. Explain the difference between absolute and relative URLs.
45. What is the difference between `/about` and `about` in a relative URL?
46. What is the purpose of the `href` attribute?
47. What is the difference between `target="_blank"` and `target="_self"`?
48. Why should we use `rel="noopener noreferrer"` in certain links opened using a new tab?

### B. Implementation

49\. Create a navigation menu containing:

- Home
- About
- Services
- Contact

50\. Create a webpage containing links to:

- Google.
- GitHub.
- Your own About page.
- An email address.
- A telephone number.

51. Create a book recommendation page with five books. Each book should link to its corresponding information page.
52. Create a page with a table of contents. Clicking each item should take the user to its corresponding section further down the page.
53. Create an external link that opens in a new tab with appropriate security attributes.

### C. Debugging

54\. Identify the problems:

```
<a>Visit Google</a>

<a href="">About</a>

<a href="https://google.com">
    <p>Google</p>
</a>
```

55\. Why is the following link problematic?

```
<a href="javascript:void(0)">Click here</a>
```

56\. Identify the issue with this link:

```
<a href="https://example.com" target="_blank">
    Visit website
</a>
```

### D. Deep reasoning

57. Why do search engines use links to discover and understand websites?
58. What is the difference between an anchor used for navigation and a button used for an action?
59. When should you use a relative URL instead of an absolute URL?

## Module 5 — Lists ✅

Topics: Ordered lists, unordered lists, description lists and nested lists.

### A. Conceptual understanding

60. What is the semantic difference between `<ol>` and `<ul>`?
61. Why does HTML provide `<dl>`, `<dt>` and `<dd>`?
62. Can an ordered list start from 5 instead of 1? How?
63. What is the difference between the `start`, `reversed` and `type` attributes of `<ol>`?

### B. Implementation

64. Create a shopping list using an unordered list.
65. Create a programming learning roadmap using an ordered list with at least five items.
66. Create a nested list representing the following structure:

- Frontend
  - HTML
  - CSS
  - JavaScript
- Backend
  - Node.js
  - Express
  - MongoDB

67. Create a glossary using a description list containing at least five technical terms and their definitions.
68. Create a restaurant menu using nested lists. Include categories, dishes and their descriptions.

### C. Debugging

69\. Correct this code:

```
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <ol>
        <li>JavaScript</li>
        <li>TypeScript</li>
    </ol>
</ul>
```

70\. Is the following valid?

```
<ol>
    <p>My first item</p>
    <li>My second item</li>
</ol>
```

Explain.

### D. Deep reasoning

71. Why should we use lists for navigation menus instead of simply writing multiple anchor elements?
72. Would using an ordered list for a list of unordered product features be semantically correct? Why?

## Module 6 — Images ✅

Topics: Image syntax, attributes, alt text, dimensions and image formats.

### A. Conceptual understanding

73. Why does the `<img>` element not require a closing tag?
74. What is the purpose of the `alt` attribute? Is it always necessary to provide descriptive text?
75. What is the difference between an image's intrinsic dimensions and its rendered dimensions?
76. Why should we specify image dimensions in HTML?
77. Explain the differences between JPEG, PNG, SVG, WebP and AVIF.
78. What happens when an image fails to load? How does the browser handle the `alt` attribute?

### B. Implementation

79. Create an author profile containing an image, name and biography.
80. Create a product card containing:

- Product image.
- Product name.
- Product price.
- Appropriate alternative text.
- Image width and height.

81. Create a gallery containing six images. Each image must have appropriate alternative text.
82. Add a decorative image to a webpage. Explain what its alt attribute should contain.

### C. Debugging

83\. Identify the problems:

```
<img src="profile.jpg">

<img src="product.jpg" alt="image">

<img href="logo.png" alt="Company Logo">
```

84\. Is this implementation correct?

```
<img
    src="product.jpg"
    alt="A red running shoe"
    width="300"
    height="300"
>
```

Assume the actual image has a 600 × 400 aspect ratio. Explain the potential problem.

85\. A webpage contains an image of a decorative background pattern. Should its alt text describe the pattern? Explain.

### D. Deep reasoning

86. Why is `alt="Click here"` generally a poor choice for an image that links to another page?
87. Why is an image's file size important for webpage performance?
88. When would you prefer SVG over PNG?

## Module 7 — Basic Tables ✅

Topics: Table structure, headers, data cells and basic styling.

### A. Conceptual understanding

89. Why were HTML tables originally introduced?
90. What is the difference between `<th>` and `<td>`?
91. Why should tables not be used to create general webpage layouts?
92. What is the purpose of the `scope` attribute in table headers?

### B. Implementation

93\. Create a student marksheet containing:

| Subject     | Maximum Marks | Obtained Marks |
| ----------- | ------------- | -------------- |
| Mathematics | 100           | 85             |
| Science     | 100           | 90             |
| English     | 100           | 78             |

94. Create an employee directory with columns for employee ID, name, department and designation.
95. Create a product comparison table containing three smartphones and their specifications.
96. Create a monthly expense table containing category, estimated expenditure and actual expenditure.

### C. Debugging

97\. Identify the errors:

```
<table>
    <tr>
        <td>Name</th>
        <th>Age</td>
    </tr>
    <tr>
        <td>John</td>
        <td>25</td>
    </tr>
</table>
```

98\. What is wrong with this table?

```
<table>
    <tr>
        <th>Name</th>
        <th>Age</th>
    </tr>

    <td>John</td>
    <td>25</td>
</table>
```

### D. Deep reasoning

99. Why is it important to distinguish between header cells and data cells?
100. Imagine a table containing 100 rows and 20 columns. What accessibility and usability problems might arise if you use only `<td>` elements?

## Module 8 — Simple Forms ✅

Topics: Form structure, input types, labels and submit buttons.

### A. Conceptual understanding

101. What is the purpose of the `<form>` element?
102. Explain the difference between `name`, `id`, `value` and `placeholder` attributes.
103. Why should every form input have an associated label?
104. What happens when a form is submitted? Explain the role of `action` and `method`.
105. What is the difference between GET and POST?
106. Why is the `name` attribute important when submitting form data?
107. What is the difference between a submit button and a normal button?

### B. Implementation

108\. Create a login form containing:

- Email input.
- Password input.
- Remember me checkbox.
- Submit button.

109\. Create a registration form containing:

- Full name.
- Email.
- Password.
- Date of birth.
- Gender selection.
- Terms and conditions checkbox.

110\. Create a contact form containing:

- Name.
- Email.
- Subject.
- Message.
- Submit button.

111\. Create a search form that submits a search query using GET.

### C. Debugging

112\. Identify the problems:

```
<form>
    <input type="text" placeholder="Enter your name">
    <button>Submit</button>
</form>
```

113\. Why is the following form potentially problematic?

```
<form action="/login" method="get">
    <label>Email</label>
    <input type="email" name="email">

    <label>Password</label>
    <input type="password" name="password">

    <button>Login</button>
</form>
```

114\. Identify the issue:

```
<form>
    <input type="text" id="username">
    <label for="user">Username</label>
</form>
```

115\. What happens when two form controls have the same `name` attribute?

### D. Deep reasoning

116. Why does a placeholder not replace a label?
117. Why shouldn't sensitive information such as passwords be submitted through GET?
118. What is the difference between client-side and server-side form validation?
119. If an input has an `id` but no `name`, can its value be submitted with the form?
120. Why is HTML form validation not sufficient for securing a backend application?

# Final Practical Challenges

These are slightly larger exercises. They combine multiple concepts from the beginner curriculum.

Challenge 1 — Personal Portfolio

Easy

[Simple website clone - v0 by Vercel](https://images.openai.com/static-rsc-4/8bF4fMJgXMdHHpa9wSPcVqiK-p40hQGspVXU4Khdc40jGf-4KZkutu9CuhBpHciEqGrJCyGJPQQbaxOXXWTKFnTAoyO5gYRpM1fSS1rsqZUeYuQAdmYI65ps0jsI0YGvkab4gWpFqvV5ibFRJq5OHD-2FqNqrQ9fGcEIyDCbr2Y?purpose=inline)

[v0.app](https://v0.app/templates/simple-website-clone-pGTjSVLX8PQ?utm_source=chatgpt.com)

Build a personal portfolio containing:

- Introduction and profile image.
- About section.
- Skills using lists.
- Project links.
- Contact information.
- Proper document structure and title.

Challenge 2 — Book Review Page

Easy

[Seeking one’s place among hogs with “The Emperor of Gladness”](https://images.openai.com/static-rsc-4/5Glsxe4zQuo_KyU4wnj-VNZlwkdEsVNwRGRKlHyKGU97QtMpGnuIet_hw_LaR31b9yapAeghh4fe-QpKh-J_cdF2CPg3Kg5M8aBFY3UZHXa42zXtO0-GLeZwbjzH8Ycdtqu3onRaDbfmSVhskZ8q0tv1NITu9O4yzPqoxvQRyOQ?purpose=inline)

[horizonsmemento.thebenildean.org](https://horizonsmemento.thebenildean.org/2025/12/seeking-ones-place-among-hogs-with-the-emperor-of-gladness?utm_source=chatgpt.com)

Build a book review page containing:

- Book cover.
- Author information.
- Book description.
- Review with headings and paragraphs.
- Related book recommendations.

Challenge 3 — Product Listing

Intermediate

[E-Commerce Shop - Product Listing & Filter UI by Abdur Rahim on Dribbble](https://images.openai.com/static-rsc-4/0WdslUyI2Ma-WlZbnk06jgcbEtjdGTNXlTUSaY-OCqHQjv5b9Nwq9GN_rqgMsnhKQy-VQWLGkIutTEW5g2WI4CgtjEveeOkMLAXKcv3NlC0hUpHDBD4u_pOO79Mm1DRbK0r53IyRzyVUQzWTRIqw7Fu2f5vHdpwGENSaqLoUPU0?purpose=inline)

[dribbble.com](https://dribbble.com/shots/27157497-E-Commerce-Shop-Product-Listing-Filter-UI?utm_source=chatgpt.com)

Build a smartphone listing page containing:

- Product images.
- Product names and prices.
- Product descriptions.
- Navigation links.
- Comparison table.

Challenge 4 — Student Registration

Intermediate

[School Management website and Student Portal UI Kit by \~ EpicPxls](https://images.openai.com/static-rsc-4/kykYpbayg-1TJ_gc_6__3Fnt6yZHqX7ZRROaavO0_7GUvz0lCelZsFcY9iA8eQ_7Wx3J3yQpLurMLcCZv18c9J3jX-DXTlFvCDkU_WW3LsdnF0sOMNKewQkLD1w2DsmGzDDfnL2I-dCGANw2DE76ZOLdRNqz5RLXVi63E0E7rz4?purpose=inline)

[epicpxls.com](https://www.epicpxls.com/items/school-management-website-and-student-portal-ui-kit?utm_source=chatgpt.com)

Build a registration page containing:

- Personal information.
- Contact details.
- Course selection.
- Gender selection.
- Terms and conditions.
- Submit button.
