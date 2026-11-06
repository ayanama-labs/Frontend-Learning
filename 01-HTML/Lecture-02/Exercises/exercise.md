Boss, since you've completed the theory portion of Intermediate HTML, I recommend moving into a practice-first learning phase.

The objective shouldn't simply be to remember HTML tags. You should be able to:

1. Explain why an HTML feature exists.
2. Decide which HTML element or attribute is appropriate for a particular situation.
3. Write valid HTML without constantly referring to documentation.
4. Identify accessibility, semantic, and structural mistakes.
5. Understand how browsers interpret your markup.
6. Build complete pages using these concepts together.

I've designed this as an Intermediate HTML Practice Workbook. It progresses from conceptual understanding to code writing, debugging, and complete projects.

Don't rush through it. Try answering conceptual questions without documentation, and write the actual HTML for practical exercises.

# Intermediate HTML — Practice Workbook

# Your practice syllabus

# 8

Topic modules

# 100+

Questions and tasks

# 5

Mini projects

# 1

Final integrated project

Topics covered

1. HTML5 Fundamentals
2. Semantic HTML
3. Advanced Forms
4. Advanced Tables
5. Media Elements
6. Embedded Content
7. Metadata
8. HTML Entities and Special Characters

## Module 1 — HTML5 Fundamentals

Objective: Understand modern HTML, its document structure, and browser compatibility.

### A. Conceptual understanding

1. What does HTML5 actually mean? Is it a completely different language from earlier HTML versions?
2. Why was the HTML5 doctype simplified to `<!DOCTYPE html>`?
3. What would happen if you removed the DOCTYPE declaration from an HTML document?
4. What is the difference between standards mode and quirks mode?
5. Why do browsers sometimes render invalid HTML instead of throwing an error?
6. What is the difference between an HTML element and an HTML5 element?
7. Are semantic elements like `<article>` fundamentally different from `<div>` in terms of how browsers process them?
8. Can an older browser understand an HTML5 document?
9. What is the purpose of the HTML Living Standard?
10. Why is HTML generally described as a markup language rather than a programming language?

### B. Predict the output / identify problems

11\. What rendering mode will the browser use?

```
<html>
<head>
    <title>My Website</title>
</head>
<body>
    <h1>Hello World</h1>
</body>
</html>
```

12\. Will the following document work? Explain why or why not.

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN">
<html>
<body>
    <main>
        <h1>Welcome</h1>
    </main>
</body>
</html>
```

13\. Identify the problems, if any:

```
<!DOCTYPE html>
<html>
<head>
    <title>My Website</title>
</head>
<body>
    <header>
        <h1>My Website</h1>
    </header>

    <article>
        <h2>First Article</h2>
    </article>

    <article>
        <h2>Second Article</h2>
    </article>
</body>
</html>
```

14\. Is this valid HTML? What does the browser do?

```
<!DOCTYPE html>
<html>
<body>
    <h1>First heading</h1>
    <p>First paragraph

    <h2>Second heading</h2>
    <p>Second paragraph
</body>
</html>
```

15\. What is the difference between an HTML validation error and a browser rendering error?

### C. Practical exercises

Exercise 1: Modern HTML document

Create a complete HTML5 document containing:

- Correct DOCTYPE.
- Language declaration.
- Character encoding.
- Viewport metadata.
- Page title.
- Header, main, and footer.
- At least two paragraphs.
- One heading hierarchy.

Exercise 2: Compatibility investigation

Create a page using:

- `<header>`
- `<main>`
- `<footer>`
- `<article>`
- `<section>`

Validate the document and investigate how browsers handle these elements.

Exercise 3: Validation challenge

Write a deliberately malformed HTML document containing at least 10 different mistakes. Run it through the W3C Validator and document every error and its correction.

## Module 2 — Semantic HTML

Objective: Understand how to structure meaningful documents instead of simply arranging elements on a page.

[10 semantic HTML tags to better structure your website](https://images.openai.com/static-rsc-4/GIZn7T9W70aIdrF4rAn9Dd30Up2X31B_1iH8ssUvFsmAsd43bwioDwhSZ823bmny3LtVpLz_XUdXqsji9ErMxsP2gSqKfnqw6PudrXLZO0i1KZxrRcXRSp_50MjggJmoUMdGLO_IiPp4GZ8zPfoOagkgWEEANIWneU3RtQ57eNA?purpose=inline)

[코딩의 시작, TCP School](https://images.openai.com/static-rsc-4/Uli-AyNxN_H3-MJW_bfrIlEK8E-kulVzoBjLLcHHFByv4csmkTxIVMiKtGzhs5f8mUfRR5d5gYBifnkRYl4IDAHdJ8h0aNN7WqVKfI10InaJ3f2ZDfhL38hnAXMbfiaY-4Ou1m2f6zN3x1b_3W4TfQtD09csPIpmtGTFx5rfK0Y?purpose=inline)

[Semantic HTML Tutorial | HTML & CSS Is Hard](https://images.openai.com/static-rsc-4/i1ZxAfNVfeap2C-MMm04AcpP57Bm7q0TPgXhthKqm_hfdt-vKCp5Eh7UqORjEm8Dm_3Ixd-CKebhxZV08UCuZsgu39p72b8AGpqK9unDSSrJ7LWnoMResaxSWw_GlOrQzqJNRFDKJ81Q8hKLlJ52rjAop1wCoDOY3Cw2i8ubNhU?purpose=inline)

7

### A. Conceptual understanding

16. What is semantic HTML? Why does it matter?
17. What is the difference between `<div>` and `<section>`?
18. When should you use `<article>` instead of `<section>`?
19. Can an `<article>` contain multiple `<section>` elements?
20. Can a `<section>` contain multiple `<article>` elements?
21. What makes content independently distributable?
22. What is the purpose of the `<main>` element? Can a page have multiple main elements?
23. What is the difference between `<header>` and `<head>`?
24. Can an `<article>` have its own `<header>` and `<footer>`?
25. What is the purpose of `<aside>`? Does it always have to appear on the right side of a webpage?
26. What is the difference between `<figure>` and `<img>`?
27. Why does `<figcaption>` belong inside `<figure>`?
28. When would you use `<time>` instead of an ordinary `<span>`?
29. What is the purpose of the `datetime` attribute in `<time>`?
30. Why is using semantic HTML generally better than creating everything with `<div>` elements?
31. Can semantic HTML improve accessibility without using ARIA?
32. What is the difference between visual hierarchy and document hierarchy?

### B. Choose the correct semantic element

For each situation, identify the most appropriate element and explain your decision.

33. A website's primary navigation menu.
34. An independently publishable news article.
35. A collection of related blog posts.
36. A sidebar containing related articles.
37. The main content of a webpage.
38. The copyright information at the bottom of a page.
39. An image with an accompanying caption.
40. A publication date.
41. A standalone product review.
42. A group of related navigation links.
43. A website logo and introductory content.
44. An introductory section within a blog article.

### C. Code-writing exercises

Exercise 1: Semantic blog article

Create a blog article containing:

- A website header.
- Navigation with at least four links.
- A main content area.
- An article title.
- Author information.
- Publication date using `<time>`.
- Three sections within the article.
- One figure with a caption.
- One aside containing related articles.
- A footer.

Exercise 2: Convert non-semantic HTML

Convert the following document into an appropriate semantic structure.

```
<div class="header">
    <div class="logo">Tech Journal</div>
    <div class="navigation">
        <div>Home</div>
        <div>Articles</div>
        <div>About</div>
    </div>
</div>

<div class="content">
    <div class="title">Understanding Databases</div>

    <div class="article">
        <div class="paragraph">
            Databases store and organize information.
        </div>
    </div>

    <div class="sidebar">
        Related Articles
    </div>
</div>

<div class="footer">
    Copyright 2026
</div>
```

Exercise 3: Semantic decision-making

Build a news homepage with:

- Three independent news articles.
- Two categories of news.
- A featured story.
- Related stories.
- Publication dates.
- A website navigation menu.

Use semantic elements appropriately. Avoid using `<div>` unless a generic container is genuinely needed.

## Module 3 — Advanced Forms

Objective: Become comfortable designing real-world forms and understanding how browsers process user input.

### A. Conceptual understanding

45. What is the difference between `type="text"` and `type="email"`?
46. What happens when a user submits an invalid email address?
47. What is the difference between `required` and `pattern`?
48. What is the purpose of `min`, `max`, and `step`?
49. What is the difference between `minlength` and `maxlength`?
50. What is the purpose of the `multiple` attribute?
51. What is the difference between `readonly` and `disabled`?
52. What is the purpose of the `autocomplete` attribute?
53. How does the `datalist` element differ from a `<select>` element?
54. Can a user enter a value that isn't included in a datalist?
55. What is the purpose of `<fieldset>`?
56. Why should `<legend>` generally be used with `<fieldset>`?
57. What is the difference between a checkbox and a radio button?
58. Why must radio buttons belonging to the same group share a `name`?
59. What is the difference between the `name` and `id` attributes?
60. What happens if an input has no `name` attribute?
61. What is the purpose of `novalidate` on a form?
62. What is the difference between `action` and `method`?
63. What is the difference between GET and POST when submitting forms?
64. Why shouldn't HTML validation be treated as backend security?

### B. Practical form-building exercises

Exercise 1: Registration form

Build a registration form containing:

- Full name.
- Username.
- Email.
- Password.
- Confirm password.
- Date of birth.
- Gender selection.
- Country selection.
- Terms and conditions checkbox.
- Submit and reset buttons.

Requirements:

- Use appropriate input types.
- Use labels for every input.
- Make necessary fields required.
- Apply `minlength` and `maxlength`.
- Use appropriate autocomplete values.
- Group related inputs using fieldset and legend.

Note: Password matching requires JavaScript; HTML alone cannot reliably enforce that two separate password fields have identical values.

Exercise 2: Job application form

Create a job application form containing:

- Applicant name.
- Email.
- Phone number.
- Position applied for.
- Years of experience.
- Expected salary.
- Available joining date.
- Resume upload.
- Skills selection.
- Cover letter.

Use suitable validation attributes and input types.

Exercise 3: Product search form

Create a search form with:

- Search query.
- Category selection.
- Minimum price.
- Maximum price.
- Sort order.
- Availability checkbox.

Use GET as the submission method and explain what happens to the form values when submitted.

Exercise 4: Datalist challenge

Create a city input with suggested cities:

- London
- New York
- Toronto
- Sydney
- Berlin

Allow users to enter a city that isn't in the suggestions.

Exercise 5: Validation challenge

Create a form with:

- Username: 5–15 characters.
- Email: valid email format.
- Age: 18–100.
- Password: minimum 8 characters.
- Website: URL input.
- Phone: pattern-based validation.

Test valid and invalid submissions.

### C. Debugging questions

65\. Why doesn't this input submit its value?

```
<input type="text" id="username">
```

66\. Why does this radio group allow multiple selections?

```
<input type="radio" name="gender1" value="male">
<input type="radio" name="gender2" value="female">
```

67\. What is wrong with this form?

```
<form action="/register" method="get">
    <input type="email" placeholder="Email" required>
    <button>Register</button>
</form>
```

68. Why can a disabled input's value be missing from submitted form data?
69. What happens if you put `required` on a hidden input?

## Module 4 — Advanced Tables

Objective: Build structured, accessible tables and understand how complex tabular data is represented.

### A. Conceptual understanding

70. What is the difference between `<thead>`, `<tbody>`, and `<tfoot>`?
71. Can a table contain multiple `<tbody>` elements?
72. What is the purpose of `<caption>`?
73. Why is `<th>` different from `<td>`?
74. What is the purpose of the `scope` attribute?
75. What is the difference between `scope="row"` and `scope="col"`?
76. What is the purpose of `colspan`?
77. What is the purpose of `rowspan`?
78. What happens when a cell spans multiple rows or columns?
79. What is the purpose of the `headers` attribute?
80. When would you use `headers` instead of `scope`?
81. Why shouldn't tables be used to create general webpage layouts?
82. How do screen readers interpret table headers?
83. Why is a table caption useful for accessibility?

### B. Practical exercises

Exercise 1: Student results table

Create a student results table with these columns:

- Student name.
- Mathematics.
- Physics.
- Chemistry.
- Total.
- Percentage.
- Grade.

Requirements:

- Use `<thead>`, `<tbody>`, and `<tfoot>`.
- Add a caption.
- Use appropriate header cells.
- Use `scope` correctly.
- Include at least five students.

Exercise 2: Employee attendance table

Create a table with:

- Employee name.
- Monday.
- Tuesday.
- Wednesday.
- Thursday.
- Friday.
- Total working days.

Use `colspan` and `rowspan` to create a multi-level header.

Exercise 3: Product comparison table

Create a comparison table for three laptops.

Include:

- Brand.
- Model.
- Processor.
- RAM.
- Storage.
- Display.
- Price.

Use grouped column headings where appropriate.

Exercise 4: Complex timetable

Create a weekly college timetable with:

- Days as rows.
- Time slots as columns.
- Different subjects.
- Lunch break.
- At least one class spanning two consecutive time slots.

Use `rowspan` or `colspan` where appropriate.

### C. Debugging challenges

84\. Identify the structural problems:

```
<table>
    <tr>
        <td>Name</td>
        <th>Age</th>
    </tr>

    <thead>
        <tr>
            <th>City</th>
        </tr>
    </thead>
</table>
```

85\. Explain the problem with this markup:

```
<table>
    <tr>
        <th colspan="3">Student Details</th>
    </tr>

    <tr>
        <td>Name</td>
        <td>Age</td>
    </tr>
</table>
```

86. What happens if `rowspan` extends beyond the available rows?
87. Why is this table potentially inaccessible?

```
<table>
    <tr>
        <td>Product</td>
        <td>Price</td>
    </tr>
    <tr>
        <td>Laptop</td>
        <td>50000</td>
    </tr>
</table>
```

## Module 5 — Media Elements

Objective: Learn how to embed audio and video content properly, including multiple media sources and captions.

[HTML audio tag explained | sebhastian](https://images.openai.com/static-rsc-4/rnMnGpUXJHL7Y1LNgL74wZaxRklzkw1J3w_SeKvPshbJPuXpivxz7OnlmIYOKO7a0CNQBToIswOk2nbJOV7N0wGUzzVJ9BfBN6u__EowoP1ntpqqPI-xg-HYxHYw9NcQsNzeLmZLKQX3Z-OUJvmaNrCOxhb-58N1DDkNhFshk9s?purpose=inline)

[How to Add Captions & Subtitles to HTML5 Videos | Rev](https://images.openai.com/static-rsc-4/2XbDH0ZGK9HHvCQpKCZU_ouR5kmdaKPrDmL7-3W1m4EeeOUpWAVBE2gOrRmRmLpiOrSpC0cousA2Yqjlv7SJ8O7JJYC8kPDUS4aHtm-qAOUkN4JVHvONOdlSv0Esp34LP0IMsaxIWSQKTvdn2_34j4PAlMLkDiniaaY-o9rxNI8?purpose=inline)

[HTML Video | Learn computer coding, Coding tutorials, Learn web development](https://images.openai.com/static-rsc-4/2CDWgFMtxfKMJBUPOndZFcmkC7nsOiW-iAXyk44HqDt8TeVJr54ZPWhtrwmetyvCD8sP9wyTnSMPShzUsR0_j7HKg8dNYLswfwEm056JfYKy5HmevCkoeMIa2iZ1wnuLQxUxxJs1QUQdyTlQ2YNp_EpnmcvxLLUyt_ympTtzphg?purpose=inline)

7

### A. Conceptual understanding

88. What is the purpose of the `<audio>` element?
89. What is the purpose of the `<video>` element?
90. Why would you use `<source>` instead of directly specifying `src`?
91. Can an audio element contain multiple source elements?
92. How does the browser decide which source to play?
93. What happens if the browser cannot play any of the supplied media formats?
94. What is the purpose of the `controls` attribute?
95. What is the difference between `autoplay`, `loop`, and `muted`?
96. Why do browsers often restrict autoplay?
97. What is the purpose of `preload`?
98. What is the difference between `preload="none"`, `metadata`, and `auto`?
99. What is the purpose of `poster` in a video element?
100.  What is the difference between a video subtitle and a caption?
101.  What is WebVTT?
102.  What is the purpose of the `<track>` element?
103.  What is the difference between `kind="subtitles"` and `kind="captions"`?
104.  Why is providing captions important for accessibility?
105.  Can an HTML video have multiple subtitle tracks?

### B. Practical exercises

Exercise 1: Audio player

Create a webpage containing three audio files.

Requirements:

- Display the title of each audio track.
- Provide playback controls.
- Support multiple audio formats where available.
- Provide fallback text.
- Use appropriate preload values.

Exercise 2: Video player

Create a video player with:

- Video controls.
- Width and height.
- Poster image.
- Multiple source formats.
- Fallback text.
- Appropriate preload behavior.

Exercise 3: Subtitles and captions

Add two subtitle tracks to a video:

- English.
- Hindi.

Use the `<track>` element and appropriate language attributes.

Exercise 4: Media gallery

Create a media gallery containing:

- Two audio players.
- Three video players.
- Captions or subtitles for at least one video.
- A heading and description for every media item.

### C. Debugging questions

106\. Why might this video fail to play?

```
<video controls>
    <source src="movie.mp4" type="video/webm">
</video>
```

107\. What is wrong with this markup?

```
<video src="movie.mp4" autoplay>
    <track src="captions.vtt" kind="captions">
</video>
```

108. Why might autoplay work on one browser but fail on another?
109. What happens when you remove `controls`?
110. What happens when you provide a subtitle track but the VTT file contains invalid formatting?

## Module 6 — Embedded Content

Objective: Understand how external documents, interactive graphics, and other resources are incorporated into HTML.

[Knowledge Base for DX 7 : Show Google Map in a Form](https://images.openai.com/static-rsc-4/nUTPoueX63ibzjjcpjZCEIbLCGHswFisCwfTb52jK_kreqfbfiwXwyekPeUu5zJLihWUa_4VA_hfQlg7pWtCfpwg9QzWs5d0UKAdbhXqhUu5Zatmo5qpOY2LUpURdpkMCtb3qAYEYzd-ftkF3vYMOu-05LDvH4ju3_CrDEHNOnE?purpose=inline)

[Draw A Circle Javascript Canvas at Thomas Gabaldon blog](https://images.openai.com/static-rsc-4/A_6Y8zuMakCoQHqsTEkjoZFCmzREPeq3HlNGO__tUYMuzq8dH8W-ZLnH_z0s8apMekT3TSLud-eOGyodnDWqSqAj1xBnmK3M2StV3tZvdUCRY8O8bC_G7gLFgqThv4M6Te-Vxe7U7hXtSyFh9KirLy7AvzVVY_L2TcxGgIQcBHs?purpose=inline)

[SVG, 일러스트레이터와 잉크스케이프로 벡터그림을 웹에 적용하세요](https://images.openai.com/static-rsc-4/mVk4Fr72L0dUiwGCub2J5s_ynQvODHACL-0u6s0B-yjir78pxoCuVU8aWaZ_90jzorTKqOIOkjNEXJeWawC9BiPT373oavHdIR348orvZKATPoau44-EHnFKedNHmLEG61zqJTsrfPE-rwjKvbTFuO8pf4ZAz7eZyBfeHNOws-8?purpose=inline)

7

### A. Conceptual understanding

111. What is an iframe?
112. What is the difference between an iframe and an ordinary hyperlink?
113. Why might a website prevent itself from being embedded in an iframe?
114. What is the purpose of the `title` attribute on an iframe?
115. What is the purpose of the `sandbox` attribute?
116. What happens when you use an empty sandbox attribute?
117. What is the difference between `allow` and `sandbox`?
118. What is the purpose of `loading="lazy"` on an iframe?
119. What are the `<object>` and `<embed>` elements used for?
120. What is the difference between inline SVG and an SVG image referenced through `<img>`?
121. What is SVG? How does it differ from raster image formats?
122. What is the purpose of the SVG `viewBox` attribute?
123. What is the `<canvas>` element?
124. Why does canvas require JavaScript to draw graphics?
125. What is the difference between SVG and Canvas?
126. Why is canvas generally less suitable than SVG for individually accessible graphical elements?
127. Can canvas provide fallback content?
128. Why might an SVG have an accessibility title?

### B. Practical exercises

Exercise 1: Embedded map

Create a contact page containing an embedded map.

Requirements:

- Use an iframe.
- Give it a descriptive title.
- Specify width and height.
- Use lazy loading where appropriate.
- Provide a link to open the map independently.

Exercise 2: Embedded video

Embed a YouTube video using an iframe.

Investigate:

- How the iframe URL differs from the normal YouTube URL.
- What happens when the `allow` attribute changes.
- How sandbox restrictions affect embedded content.

Exercise 3: SVG illustration

Create an inline SVG containing:

- A rectangle.
- A circle.
- A line.
- A polygon.
- A text element.

Use:

- `viewBox`.
- Width and height.
- Appropriate SVG elements.
- A title or accessible description.

Exercise 4: Canvas introduction

Create an HTML canvas and use JavaScript to draw:

- A rectangle.
- A circle.
- A straight line.
- A simple house.

Exercise 5: Embedded content page

Build a webpage containing:

- An embedded map.
- An embedded video.
- An inline SVG illustration.
- A canvas illustration.

Explain the purpose of each technology.

### C. Debugging questions

129\. Why might this iframe not load?

```
<iframe src="https://example.com"></iframe>
```

130\. What accessibility problem exists here?

```
<iframe src="https://www.youtube.com/embed/example"></iframe>
```

131\. What is wrong with this SVG?

```
<svg>
    <circle cx="50" cy="50" r="40">
</svg>
```

132\. Why does this canvas display nothing?

```
<canvas id="myCanvas" width="300" height="200">
    Your browser does not support canvas.
</canvas>
```

133\. Why is it incorrect to assume that an iframe sandbox is always safer when arbitrary permissions are added to it?

## Module 7 — Metadata

Objective: Understand how HTML documents communicate information to browsers, search engines, and social media platforms.

### A. Conceptual understanding

134. What is metadata?
135. Why is metadata generally placed inside `<head>`?
136. What is the purpose of `<meta charset="UTF-8">`?
137. What happens if a webpage uses the wrong character encoding?
138. What is the purpose of the viewport meta tag?
139. Why is `width=device-width` important for responsive websites?
140. What does `initial-scale=1.0` mean?
141. What is the purpose of the description meta tag?
142. Does the meta description directly determine Google search rankings?
143. What is the purpose of the robots meta tag?
144. What is the difference between `index` and `noindex`?
145. What is the difference between `follow` and `nofollow`?
146. What is the Open Graph protocol?
147. Why was Open Graph introduced?
148. What is the purpose of `og:title`?
149. What is the purpose of `og:description`?
150. What is the purpose of `og:image`?
151. What are Twitter Cards (now commonly referred to as X Cards)?
152. What is the purpose of a favicon?
153. What is the difference between a favicon and an ordinary webpage image?
154. Can a webpage have multiple favicon formats?
155. What is the purpose of the canonical URL?
156. Why might two URLs displaying identical content create SEO problems?

### B. Practical exercises

Exercise 1: SEO metadata

Create a webpage for a fictional technology blog.

Include:

- Character encoding.
- Viewport.
- Page title.
- Meta description.
- Author.
- Robots directive.
- Canonical URL.

Exercise 2: Social media sharing

Add Open Graph metadata:

- `og:title`
- `og:description`
- `og:image`
- `og:url`
- `og:type`
- `og:site_name`

Add appropriate X Card metadata.

Exercise 3: Favicon implementation

Implement:

- PNG favicon.
- SVG favicon.
- Apple touch icon.

Use the appropriate `link` elements.

Exercise 4: Product metadata

Create a product page with:

- SEO title.
- Description.
- Canonical URL.
- Open Graph image.
- Social sharing metadata.

Investigate how the page preview changes when the metadata changes.

### C. Debugging questions

157\. Identify the mistakes:

```
<head>
    <title>My Website</title>

    <meta name="description" content="My website">

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width">
</head>
```

158. Why is the character encoding declaration generally placed near the beginning of the head?
159. What happens if the Open Graph image URL points to a nonexistent image?
160. Can a page have multiple description meta tags? Why is that undesirable?
161. What is the difference between canonical metadata and a redirect?
162. Why shouldn't you put important page content only inside metadata?

## Module 8 — HTML Entities and Special Characters

Objective: Understand how HTML represents reserved characters, symbols, and Unicode text.

### A. Conceptual understanding

163. Why do HTML entities exist?
164. Why can't you directly write certain characters in HTML markup?
165. What is the purpose of `&lt;`?
166. What is the purpose of `&gt;`?
167. What is the purpose of `&amp;`?
168. What is the difference between a named entity and a numeric character reference?
169. What is the difference between decimal and hexadecimal character references?
170. What is Unicode?
171. What is the difference between Unicode and UTF-8?
172. Can UTF-8 represent characters from multiple languages?
173. Why might some characters appear as replacement symbols or boxes?
174. What is the purpose of the non-breaking space (`&nbsp;`)?
175. How is a non-breaking space different from an ordinary space?
176. What is the difference between HTML entities and CSS pseudo-elements?
177. When should you use a Unicode character directly instead of an HTML entity?

### B. Practical exercises

Exercise 1: Reserved characters

Create a webpage that displays these characters as text rather than interpreting them as HTML:

```
<div>
<p>
<h1>
&amp;
```

Use appropriate character entities.

Exercise 2: Special symbols

Create a reference page displaying:

- Copyright symbol.
- Registered trademark.
- Trademark.
- Euro symbol.
- Pound symbol.
- Yen symbol.
- Degree symbol.
- Multiplication symbol.
- Division symbol.
- Em dash.
- En dash.

Exercise 3: Mathematical expressions

Create a webpage displaying:

- `x² + y² = z²`
- `a × b = c`
- `10 ÷ 2 = 5`
- `5 ≥ 3`
- `2 ≤ 4`
- `∞`

Use Unicode characters or suitable entities.

Exercise 4: International characters

Create a multilingual page containing:

- English.
- Hindi.
- French.
- German.
- Japanese.
- Arabic.

Ensure the character encoding is correct and investigate how right-to-left text is represented.

### C. Debugging questions

178\. Why doesn't this display the intended text?

```
<p>5 & 10 are values.</p>
```

179\. What will the browser display?

```
<p>&amp;lt;</p>
```

180\. What is the difference between these?

```
<p>©</p>
<p>&copy;</p>
<p>&#169;</p>
<p>&#xA9;</p>
```

# Final Practice — Integrated Mini Projects

These projects are important because knowing individual HTML elements doesn't necessarily mean you can combine them correctly in a real webpage.

Complete them without copying existing implementations.

## Project 1 — Semantic Blog Post

Beginner–Intermediate

[incyber.consulteer.com](https://incyber.consulteer.com/de/insights/incyber-ai-and-apis?utm_source=chatgpt.com)

Build a complete blog article page.

Requirements:

- Semantic header and navigation.
- Main article with author information.
- Publication date using `<time>`.
- At least four article sections.
- Images with appropriate alternative text.
- Figure and figcaption.
- Related articles in an aside.
- Footer with copyright information.
- SEO metadata and Open Graph metadata.

Challenge: Make the document meaningful even if all CSS is removed.

## Project 2 — Comprehensive Contact Form

Intermediate

[Avenix — E-Commerce Inner Pages UI Design by WhiteFrame Creative on Muzli](https://images.openai.com/static-rsc-4/bwRfOl0qIG6U-0d3i39y4xEwhPun35pqtHpp4NZDHWislopMzRKTPMyoH04mLQKTBEE6_y0xZKZijHKeBqpWmas4aRypn14vvG384bPKKXRWl4I97C3KrEf1rSX5Rs0hWuD25MBABABK0Gli9rvkgs7iNfMHAv-dIg4oDT6u5_c?purpose=inline)

[me.muz.li](https://me.muz.li/whiteframe/avenix-e-commerce-inner-pages-ui-design-3?utm_source=chatgpt.com)

Build a professional contact form.

Requirements:

- Personal information.
- Contact information.
- Subject selection.
- Message textarea.
- Preferred contact method.
- File attachment.
- Appropriate validation.
- Fieldsets and legends.
- Proper labels.
- GET or POST submission configuration.

Challenge: Explain what data gets submitted and why each input needs a `name`.

## Project 3 — Accessible FAQ Page

[Simple expanded FAQ example - Tailwind CSS Example](https://images.openai.com/static-rsc-4/pXMBYqHT6xrfyhXRteoNPUDUUOKShXzQ9Ee1ZAGibsqHfcizlduIDuI03uK3sm3DYA23WBFdVYsIoktvI70ODclbM71d0z3EpZw1TdxpRv20RrUgSpniNPZIIpAxoNPf0s8NC7IwQ3LqCwC4k7xfVF7HXBFXXyR3Z1WwnLgoiH0?purpose=inline)

[tailwindflex.com](https://tailwindflex.com/%40orson-kincaid/simple-expanded-faq-example?utm_source=chatgpt.com)

Build an FAQ page using:

- `<details>`
- `<summary>`
- Semantic headings.
- At least 10 questions.
- Proper document structure.
- Accessible labels and meaningful text.

Challenge: Make the entire FAQ usable without JavaScript.

## Project 4 — SEO-Optimized Product Listing

[E-commerce Marketplace Web design by Ronas IT | UI/UX Team on Dribbble](https://images.openai.com/static-rsc-4/9BHhwaGz3ghUjIUsI2y44hBCnUuYdTy6WTJrkOXv_siOBC6y_jQWAJGvOc1Ld8iy4zPZ9j0rU0BkcZ21fOHNR8sYXhCyQSYMBC3h_Z98eT1VhBNIVxnROPQjjpi6k5_2Gr1NPRS-1z__90xVeOcwejSZEgFEmGr3JlS4dW6fIJ8?purpose=inline)

[dribbble.com](https://dribbble.com/shots/26899972-E-commerce-Marketplace-Web-design?utm_source=chatgpt.com)

Build a product listing page for an imaginary electronics store.

Requirements:

- Semantic page structure.
- At least six products.
- Product images and alternative text.
- Product names and descriptions.
- Product comparison table.
- Search form.
- Category filtering form.
- SEO metadata.
- Open Graph metadata.
- Favicon.

Challenge: Use structured data with JSON-LD to describe a product. This also introduces a little material from your next level.

## Project 5 — Media and Embedded Content Library

[AI-Powered Media Search - Find Any Asset Instantly | Flo](https://images.openai.com/static-rsc-4/UZIjriJZvrFJkyjb7HUV522KwG7gheI1702ZFFydLyX6GaPWTi6Z4MKm66ambUVCkK2bBmlc4eXtCZqEhiIudxPnOAjlhGO3PC-6mS-0M5lq7xVHQCxcLnWAYsPLASxdwA1bha1YgQPmeW0RsZMFesc_LsolGCqPdfe8ibltSKo?purpose=inline)

[flomenco.com](https://flomenco.com/discover?utm_source=chatgpt.com)

Build a media library containing:

- Three audio tracks.
- Two videos.
- English subtitles.
- Hindi subtitles.
- An embedded map.
- One inline SVG illustration.
- One canvas drawing.

Challenge: Make sure the media has appropriate fallback behavior and accessibility support.

# How to evaluate your understanding

I don't want you to complete 180 questions mechanically. The important thing is whether you can reason about the concepts.

Use this evaluation system after every module.

Module mastery checklist

Rate yourself from 0 to 2 for each criterion. 0 = Not understood, 1 = Partially understood, 2 = Can do independently.

1\. Conceptual understanding

Can explain what the element does and why it exists.

012

2\. Element selection

Can choose the appropriate element for a given situation.

012

3\. Code implementation

Can write valid markup without referring to examples.

012

4\. Debugging

Can identify structural, semantic and accessibility mistakes.

012

5\. Integration

Can combine the concepts in a complete webpage.

012

Your score

# 0/10

Revisit the module's theory and repeat its exercises.

Reset assessment

# Recommended execution strategy

I suggest completing this workbook in three passes.

| Pass | What you do                  | Objective                    |
| ---- | ---------------------------- | ---------------------------- |
| 1    | Conceptual questions         | Develop understanding        |
| 2    | Code exercises and debugging | Build implementation skills  |
| 3    | Mini projects                | Develop practical competence |

A few rules:

1. Don't look up the solution immediately. Spend at least 5–10 minutes attempting a problem.
2. If you get stuck, consult documentation, understand the answer, and then close the documentation and reproduce it.
3. Validate your HTML using the [W3C HTML Validator](https://validator.w3.org/?utm_source=chatgpt.com).
4. Inspect the resulting DOM using Chrome DevTools.
5. Test keyboard navigation and use an accessibility checker such as [WAVE](https://wave.webaim.org/?utm_source=chatgpt.com).

One important distinction: HTML is not just about producing something that looks correct in a browser. A good implementation must also be structurally valid, semantically meaningful, accessible, and understandable to other developers.

## How I recommend we work through this

Rather than answering all 180 questions at once, work module by module.

Start with Module 1. Send me your answers to questions 1–15 and your three practical exercises.

I'll evaluate them on:

- Technical correctness.
- Depth of conceptual understanding.
- Quality of HTML implementation.
- Industry-standard practices.
- Mistakes and misconceptions.

I'll explain corrections rather than simply giving you the right answers.

After that, we'll move to Module 2.

The target is independent implementation, not merely finishing the workbook.

I can also send you a fresh mixed HTML revision challenge tomorrow to reinforce what you've studied.

📚Daily HTML revision challengeTap to set up
