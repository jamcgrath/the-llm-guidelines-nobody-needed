### **Comprehensive Semantic HTML Guideline**

Semantic HTML enhances clarity, accessibility, and maintainability by using elements that convey the meaning and structure of content. Follow these principles to write clean, structured, and semantic HTML.

[TOC]

---

### **1. Use Appropriate Semantic Elements**

Choose HTML elements that accurately represent the content's purpose. Avoid using generic `<div>` and `<span>` elements when a semantic alternative exists.

**Example**:

```html
<header>
  <h1>Welcome to My Website</h1>
  <nav>
    <ul>
      <li><a href="/about">About</a></li>
      <li><a href="/contact">Contact</a></li>
    </ul>
  </nav>
</header>
<main>
  <article>
    <h2>Latest Blog Post</h2>
    <p>This is a self-contained piece of content.</p>
  </article>
  <aside>
    <h3>Related Links</h3>
    <ul>
      <li><a href="/resources">Resources</a></li>
    </ul>
  </aside>
</main>
<footer>
  <p>© 2024 My Website</p>
</footer>
```

---

### **2. Structure Content with Headings**

Use `<h1>` to `<h6>` to define a clear hierarchy for your content. Always use `<h1>` as the main title, followed by `<h2>`, `<h3>`, etc., for subsections.

**Example**:

```html
<h1>Cooking Recipes</h1>
<section>
  <h2>Breakfast</h2>
  <p>Delicious ideas to start your day.</p>
</section>
<section>
  <h2>Dinner</h2>
  <p>Recipes for a hearty meal.</p>
</section>
```

---

### **3. Write Proper Paragraphs**

Use `<p>` for blocks of text. Avoid misusing `<span>` as a block element by styling it with CSS.

**Bad Example**:

```html
<span style="display: block;"
  >This is a paragraph, but a span is being misused here.</span
>
```

**Good Example**:

```html
<p>This is a properly defined paragraph.</p>
```

Use `<span>` only for inline typographic styling when necessary.

**Example**:

```html
<p>
  This text contains <span style="color: red;">important inline styling</span>.
</p>
```

---

### **4. Use Lists for Related Items**

Group related items with `<ul>` (unordered), `<ol>` (ordered), or `<dl>` (description lists).

**Example**:

```html
<ul>
  <li>Apples</li>
  <li>Bananas</li>
  <li>Cherries</li>
</ul>
<ol>
  <li>Preheat oven to 350°F.</li>
  <li>Mix ingredients in a bowl.</li>
  <li>Bake for 30 minutes.</li>
</ol>
<dl>
  <dt>HTML</dt>
  <dd>A markup language for web pages.</dd>
  <dt>CSS</dt>
  <dd>A style sheet language for styling web pages.</dd>
</dl>
```

---

### **5. Mark Up Text for Emphasis and Importance**

Use `<em>` for emphasis and `<strong>` for importance.

**Example**:

```html
<p><strong>Warning:</strong> This action is irreversible.</p>
<p>To highlight an important step, <em>pay attention to this example.</em></p>
```

---

### **6. Label Interactive Elements Properly**

Ensure that links, buttons, and form controls are appropriately labeled and use semantic elements.

**Example**:

```html
<a href="/home" title="Go to homepage">Home</a>
<button type="submit">Submit</button>
<form>
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" />
</form>
```

If a link is to an external site add `target=_blank` and `rel=noopener`

**Example**

```html
<a href="https://www.google.com" target="_blank" rel="noopener">Google.com</a>
```

---

### **7. Use Forms Correctly**

Forms should be accessible and use semantic elements.

- Wrap controls in a `<form>`.
- Use `<label>` to describe inputs.
- Group related inputs with `<fieldset>` and `<legend>`.

**Example**:

```html
<form action="/submit" method="POST">
  <fieldset>
    <legend>Personal Information</legend>
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required />
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required />
  </fieldset>
  <button type="submit">Submit</button>
</form>
```

---

### **8. Use Tables for Tabular Data**

Use `<table>` elements to present tabular data.

**Example**:

```html
<table>
  <thead>
    <tr>
      <th>Product</th>
      <th>Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Apple</td>
      <td>$1.00</td>
    </tr>
    <tr>
      <td>Banana</td>
      <td>$0.50</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total</td>
      <td>$1.50</td>
    </tr>
  </tfoot>
</table>
```

---

### **9. Provide Text Alternatives for Media**

Include `alt` attributes for images and captions for audio or video.

**Example**:

```html
<img src="logo.png" alt="Company Logo" />
<video controls>
  <source src="video.mp4" type="video/mp4" />
  <track src="captions.vtt" kind="subtitles" srclang="en" label="English" />
  Your browser does not support the video tag.
</video>
```

---

### **10. Avoid Non-Semantic Elements for Styling**

Avoid using `<div>` or `<span>` for styling when semantic elements exist.

**Bad Example**:

```html
<div class="header">Welcome to My Site</div>
```

**Good Example**:

```html
<header>Welcome to My Site</header>
```

Use CSS for styling and reserve `<div>` for structural grouping and `<span>` for inline text styling.

---

### **11. Ensure Keyboard Accessibility**

Use semantic elements to ensure built-in keyboard support.

**Example**:

```html
<button onclick="alert('Clicked!')">Click Me</button>
<a href="/profile" role="button">Visit Profile</a>
```

---

### **12. Validate HTML for Semantic Accuracy**

Validate your HTML regularly to catch errors and ensure semantic accuracy.

**Bad Example**:

```html
<div>Click Here</div>
```

**Good Example**:

```html
<button>Click Here</button>
```

---

### **13. Common Semantic HTML Elements**

Here is a list of common semantic elements and their purposes:

- **Structural Elements**: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`.
- **Text Content**: `<h1>` to `<h6>`, `<p>`, `<blockquote>`, `<q>`, `<strong>`, `<em>`, `<mark>`, `<time>`.
- **Lists**: `<ul>`, `<ol>`, `<li>`, `<dl>`, `<dt>`, `<dd>`.
- **Media**: `<img>`, `<figure>`, `<figcaption>`, `<video>`, `<audio>`, `<source>`.
- **Forms**: `<form>`, `<label>`, `<input>`, `<textarea>`, `<button>`, `<select>`, `<option>`, `<fieldset>`, `<legend>`.
- **Tables**: `<table>`, `<thead>`, `<tbody>`, `<tfoot>`, `<tr>`, `<th>`, `<td>`.
- **Interactive Elements**: `<a>`, `<button>`, `<details>`, `<summary>`, `<dialog>`.

