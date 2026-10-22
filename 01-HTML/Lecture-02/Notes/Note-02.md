# 11. Advanced Forms

HTML5 introduced new input types and attributes that provide **better validation, user experience, and semantic meaning**.

---

## 11.1 New `<input>` Types

### `email`

For email addresses.

```html
<input type="email" name="email" />
```

Browser can validate that the value resembles an email address.

---

### `url`

For URLs.

```html
<input type="url" name="website" />
```

---

### `tel`

For telephone numbers.

```html
<input type="tel" name="phone" />
```

**Note:** `tel` does not perform strong phone-number validation because phone formats vary by country.

---

### `number`

For numerical values.

```html
<input type="number" min="1" max="100" step="1" />
```

Useful attributes:

- `min` → minimum value
- `max` → maximum value
- `step` → allowed increment

---

### `range`

Creates a slider.

```html
<input type="range" min="0" max="100" value="50" />
```

---

### `date`

Allows the user to select a date.

```html
<input type="date" />
```

Other date/time types:

```html
<input type="month" />
<input type="week" />
<input type="time" />
<input type="datetime-local" />
```

---

### `color`

Color picker.

```html
<input type="color" />
```

---

### `search`

For search queries.

```html
<input type="search" name="q" />
```

Semantically tells the browser that this input is intended for searching.

---

### `hidden`

Stores a value that isn't displayed to the user.

```html
<input type="hidden" name="userId" value="123" />
```

**Important:** Hidden does **not** mean secure. Users can inspect and modify it.

---

## 11.2 Form Validation Attributes

HTML5 provides built-in client-side validation.

### `required`

Value must be provided.

```html
<input type="text" required />
```

---

### `minlength` / `maxlength`

Controls text length.

```html
<input type="password" minlength="8" maxlength="20" />
```

---

### `min` / `max`

Controls numerical/date ranges.

```html
<input type="number" min="18" max="60" />
```

---

### `step`

Controls valid increments.

```html
<input type="number" min="0" max="100" step="5" />
```

Possible values:

```text
0, 5, 10, 15, ...
```

---

### `pattern`

Requires the value to match a regular expression.

```html
<input type="text" pattern="[A-Za-z]+" />
```

This allows letters only.

**Important:** `pattern` applies to the entire value.

---

### `placeholder`

Displays a hint/example.

```html
<input type="email" placeholder="you@example.com" />
```

**Important:** `placeholder` is **not** a replacement for `<label>`.

---

### `autocomplete`

Tells the browser what kind of information is expected and allows autofill.

```html
<input type="email" autocomplete="email" />
```

Examples:

```html
autocomplete="name" autocomplete="email" autocomplete="tel"
autocomplete="street-address"
```

---

### `readonly`

User cannot edit the value, but the value can still be submitted.

```html
<input value="Ayan" readonly />
```

---

### `disabled`

Input is disabled.

```html
<input value="Ayan" disabled />
```

**Important difference:**

| Attribute  | Editable? | Submitted? |
| ---------- | --------: | ---------: |
| `readonly` |        ❌ |         ✅ |
| `disabled` |        ❌ |         ❌ |

---

## 11.3 `novalidate`

Disables the browser's built-in validation for a form.

```html
<form novalidate></form>
```

Useful when validation is handled entirely through JavaScript/server-side logic.

---

## 11.4 `datalist`

`<datalist>` provides **suggested options** for an input.

```html
<label for="browser">Browser:</label>

<input list="browsers" id="browser" />

<datalist id="browsers">
  <option value="Chrome"></option>
  <option value="Firefox"></option>
  <option value="Edge"></option>
  <option value="Safari"></option>
</datalist>
```

The user can:

- Select a suggestion
- Usually type a different value

### `datalist` vs `<select>`

**`<select>`** → user generally chooses from predefined options.

**`<datalist>`** → provides suggestions, but the user can enter another value.

```text
<select>
    → controlled choices

<datalist>
    → suggestions + free input
```

---

# 11.5 `<fieldset>`

Groups related form controls.

```html
<fieldset>
  <input type="text" />
  <input type="email" />
</fieldset>
```

Useful for organizing large forms.

---

# 11.6 `<legend>`

Provides a caption/title for a `<fieldset>`.

```html
<fieldset>
  <legend>Personal Information</legend>

  <label>Name:</label>
  <input type="text" />

  <label>Email:</label>
  <input type="email" />
</fieldset>
```

### Relationship

```text
<fieldset>
    ├── <legend> → describes the group
    └── form controls
```

`fieldset` + `legend` is particularly useful for **accessibility**, because assistive technologies can understand that the controls belong to the same group.

---

# 11.7 Important Form Structure

A good semantic form:

```html
<form>
  <fieldset>
    <legend>Account Information</legend>

    <label for="email">Email</label>
    <input id="email" name="email" type="email" required autocomplete="email" />

    <label for="password">Password</label>
    <input
      id="password"
      name="password"
      type="password"
      minlength="8"
      required
    />
  </fieldset>

  <button type="submit">Register</button>
</form>
```

### Key principle

**HTML validation improves UX, but server-side validation is still mandatory.**

Never trust client-side validation for security.

---

# 12. Advanced Tables

HTML tables represent **tabular data** — information organized into rows and columns.

---

# 12.1 Basic Table Structure

```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>

  <tr>
    <td>Ayan</td>
    <td>23</td>
  </tr>
</table>
```

### Important elements

| Element   | Purpose         |
| --------- | --------------- |
| `<table>` | Table container |
| `<tr>`    | Table row       |
| `<th>`    | Header cell     |
| `<td>`    | Data cell       |

---

# 12.2 `<thead>`

Contains the table's header rows.

```html
<thead>
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>
</thead>
```

---

# 12.3 `<tbody>`

Contains the main data rows.

```html
<tbody>
  <tr>
    <td>Ayan</td>
    <td>23</td>
  </tr>

  <tr>
    <td>Rahul</td>
    <td>25</td>
  </tr>
</tbody>
```

---

# 12.4 `<tfoot>`

Contains summary/footer rows.

```html
<tfoot>
  <tr>
    <td>Total</td>
    <td>48</td>
  </tr>
</tfoot>
```

### Complete structure

```html
<table>
  <caption>
    Student Information
  </caption>

  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Ayan</td>
      <td>23</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td>Total</td>
      <td>1 student</td>
    </tr>
  </tfoot>
</table>
```

Think:

```text
<table>
 ├── <caption>
 ├── <thead>
 ├── <tbody>
 └── <tfoot>
```

---

# 12.5 `colspan`

Makes a cell span **multiple columns**.

```html
<tr>
  <th colspan="2">Personal Information</th>
</tr>
```

Example:

```text
       colspan="2"
    ┌───────────────┐
    │ Personal Info │
    └───────────────┘
```

If `colspan="3"`, the cell occupies three columns.

---

# 12.6 `rowspan`

Makes a cell span **multiple rows**.

```html
<tr>
  <td rowspan="2">India</td>
  <td>Lucknow</td>
</tr>

<tr>
  <td>Mumbai</td>
</tr>
```

Conceptually:

```text
┌────────┬────────┐
│ India  │ Lucknow│
│        ├────────┤
│        │ Mumbai │
└────────┴────────┘
```

### Easy memory trick

```text
colspan → across columns → horizontal

rowspan → across rows    → vertical
```

---

# 12.7 `<caption>`

Provides a title/description for the table.

```html
<table>
  <caption>
    Employee Salaries
  </caption>
  ...
</table>
```

The `<caption>` should describe what the table represents.

### Accessibility benefit

Screen readers can use the caption to help users understand the table's purpose.

---

# 12.8 Accessibility: `<th>`

Use `<th>` for **header cells**, not `<td>` with bold styling.

Bad:

```html
<td><strong>Name</strong></td>
```

Good:

```html
<th>Name</th>
```

`<th>` communicates that the cell is a **header**, not merely visually bold text.

---

# 12.9 `scope`

`scope` tells assistive technologies what a header describes.

### Column header

```html
<th scope="col">Name</th>
<th scope="col">Age</th>
```

### Row header

```html
<th scope="row">Ayan</th>
```

Common values:

```text
scope="col" → header describes a column
scope="row" → header describes a row
```

This is especially useful for making tables understandable to screen-reader users.

---

# 12.10 Accessible Table Example

```html
<table>
  <caption>
    Student Marks
  </caption>

  <thead>
    <tr>
      <th scope="col">Student</th>
      <th scope="col">Math</th>
      <th scope="col">English</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <th scope="row">Ayan</th>
      <td>90</td>
      <td>85</td>
    </tr>

    <tr>
      <th scope="row">Rahul</th>
      <td>80</td>
      <td>88</td>
    </tr>
  </tbody>
</table>
```

Notice that **Ayan** and **Rahul** are row headers, so `<th scope="row">` is appropriate.

---

# Quick Revision

## Forms

| Feature               | Purpose                      |
| --------------------- | ---------------------------- |
| `type="email"`        | Email input                  |
| `type="url"`          | URL input                    |
| `type="number"`       | Numeric input                |
| `type="date"`         | Date picker                  |
| `type="range"`        | Slider                       |
| `type="color"`        | Color picker                 |
| `required`            | Value required               |
| `min/max`             | Value boundaries             |
| `minlength/maxlength` | Text length                  |
| `step`                | Numeric increment            |
| `pattern`             | Regex-based validation       |
| `autocomplete`        | Browser autofill             |
| `readonly`            | Cannot edit, still submitted |
| `disabled`            | Cannot edit, not submitted   |
| `<datalist>`          | Input suggestions            |
| `<fieldset>`          | Groups controls              |
| `<legend>`            | Names a fieldset             |

## Tables

| Feature       | Purpose                 |
| ------------- | ----------------------- |
| `<thead>`     | Header rows             |
| `<tbody>`     | Main data               |
| `<tfoot>`     | Summary/footer rows     |
| `colspan`     | Cell spans columns      |
| `rowspan`     | Cell spans rows         |
| `<caption>`   | Table title/description |
| `<th>`        | Header cell             |
| `scope="col"` | Column header           |
| `scope="row"` | Row header              |

### The 4 distinctions worth memorizing

```text
readonly  → user can't edit → submitted
disabled  → user can't edit → NOT submitted

datalist  → suggestions + user can type
select    → predefined choices

colspan   → spans columns → horizontal
rowspan   → spans rows    → vertical
```
