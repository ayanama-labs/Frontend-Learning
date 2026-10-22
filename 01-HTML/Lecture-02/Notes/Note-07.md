# 16. HTML Entities & Special Characters

## 1. Character Entities

HTML entities are special sequences used to display characters that have special meaning in HTML or are difficult to type directly.

Two formats are commonly used:

- Named entity: `&name;`
- Numeric entity: `&#number;` or `&#xhex;`

Examples:

```
&lt;       <!-- < -->
&gt;       <!-- > -->
&amp;      <!-- & -->
&copy;     <!-- © -->
&#169;     <!-- © -->
&#xA9;     <!-- © -->
```

## 2. Reserved Characters

Some characters have special meanings in HTML syntax. Entities allow you to display them as ordinary text.

| Character | Entity   | Display |
| --------- | -------- | ------- |
| `<`       | `&lt;`   | <       |
| `>`       | `&gt;`   | >       |
| `&`       | `&amp;`  | &       |
| `"`       | `&quot;` | "       |
| `'`       | `&apos;` | '       |

Example:

```
<p>5 &lt; 10</p>
<p>Tom &amp; Jerry</p>
```

Output:

5 < 10

Tom & Jerry

Note: In ordinary HTML text, `<` and `&` are especially important to escape. Quotes also need escaping in certain attribute contexts.

## 3. Symbols and Icons

HTML entities can display symbols without requiring you to type the actual character.

| Symbol | Entity     | Meaning              |
| ------ | ---------- | -------------------- |
| ©      | `&copy;`   | Copyright            |
| ®      | `&reg;`    | Registered trademark |
| ™      | `&trade;`  | Trademark            |
| €      | `&euro;`   | Euro                 |
| ₹      | `&#8377;`  | Indian rupee         |
| →      | `&rarr;`   | Right arrow          |
| ✓      | `&#10003;` | Check mark           |
| ♥      | `&hearts;` | Heart                |

Example:

```
<p>Copyright &copy; 2026</p>
<p>Price: &#8377;500</p>
<p>Continue &rarr;</p>
```

Note: You can also use many symbols directly in HTML if your document uses UTF-8 encoding.

## 4. Unicode Characters

Unicode is a universal character-encoding standard that assigns a unique code point to characters from different languages, scripts, and symbol sets.

Examples:

| Character | Unicode code point |
| --------- | ------------------ |
| A         | `U+0041`           |
| ₹         | `U+20B9`           |
| ©         | `U+00A9`           |
| 😀        | `U+1F600`          |

Use UTF-8 encoding in HTML:

```
<head>
  <meta charset="UTF-8" />
</head>
```

You can insert Unicode characters using numeric HTML references:

```
<p>&#8377;500</p>
<p>&#128512;</p>
```

Output: ₹500 and 😀

### Important distinction

- Unicode defines character code points.
- UTF-8 is an encoding used to represent Unicode characters as bytes.
- HTML entities are a way to represent characters in HTML source code.

Practical rule: Use UTF-8 for modern HTML documents, write ordinary characters directly when possible, and use entities when you need to represent reserved characters or prefer a readable named reference.
