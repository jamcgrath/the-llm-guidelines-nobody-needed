# Markdown Best Practices

Here are some best practices that you can follow when using Markdown for technical writing:

- **Don't use too many levels of heading**: Use headings to break down your content into sections, but don't use too many headings. Too many headings can make your document look cluttered. Stick to using two or three levels of headings.
- **Use lists**: Use lists to break down complex information into smaller, more manageable pieces.
- **Add a table of contents**: Add a table of contents to your document to make it easier for readers to navigate your content.
- **Do not use text decorators**: ex. `**` _Italic_ `**Bold**` `***Bold and Italic***`
- **Ignore external links**
- There should be a single blank between Markdown blocks of different types -- for example, between a paragraph and a list or header.
- Don't use more than one blank line. Multiple blank lines render as a single blank line in HTML, therefore the extra blank lines are unnecessary.
- Within a code block, consecutive blank lines break the code block.
- Remove extra spaces at the end of lines. Trailing spaces can change how Markdown renders.
- There must be a single space between the `#` and the first letter of the heading
- Headings should be surrounded by a single blank line
- Only one H1 per document
- Header levels should increment by one -- don't skip levels
- Limit depth to H3 or H4
- Avoid using bold or other markup in headers

* Declare the language in code blocks

  ````
   ```HTML
   code
   ```

  ````

* Simplify Heading Levels: : Use fewer `#` symbols for headings to create a flatter hierarchy.

* Remove Text Decorations Eliminate markdown styles such as bold (`**`), italics (`*`), and others.

* Condense Code Blocks: Streamline code sections to use fewer tokens without losing essential information.

* Streamline Lists and Descriptions: Use concise bullet points and combine related items to avoid repetition.

* Eliminate Redundant Lines and Separators:: Remove unnecessary horizontal rules (`---`) and extra lines that do not contribute to content clarity.

* Use Inline Elements When Possible: Replace block elements with inline elements if it doesn't compromise the document's readability.

* Remove Excess Whitespace: Eliminate unnecessary spaces and empty lines that do not enhance readability.

* Optimize List Formatting: Use inline list formatting where appropriate to save tokens.

* Consolidate Summary Points: Combine related optimization points into summarized statements.

---

## Markdown Document Example

```
# Document Title

Short introduction.

[TOC]

## Topic

Content.

```



Apologies for the formatting errors in my previous response. Here is the corrected **Code Blocks** section of your **Markdown Best Practices**, focusing on minimizing token usage by avoiding unnecessary indentation within code blocks. I've ensured the formatting is correct and that only the code examples are within code blocks.

------

## 3. Code Blocks

### Best Practices

- **Use Fenced Code Blocks**: Utilize triple backticks (```) to define code blocks instead of indenting with spaces or tabs. This method reduces token usage and maintains clarity for LLM processing.

  **Incorrect (Indented Code Block):**

  ```markdown
  .test{
  	color:red;
  }
  ```

  **Correct (Fenced Code Block):**

  ~~~markdown
  ```css
  .test{
  color:red;
  }
  ```
  ~~~

- **Declare the Language**: Specify the programming language immediately after the opening backticks to enable syntax highlighting. This helps the LLM understand the context of the code without adding significant token overhead.

  ~~~markdown
  ```javascript
  function greet(name){
  console.log("Hello, " + name + "!");
  }
  ```
  ~~~

- **Avoid Unnecessary Indentation**: Do not add extra spaces or tabs to indent code within fenced code blocks. Each line should start left-justified unless the language's syntax requires indentation (e.g., Python).

  - **For Languages Like CSS, JavaScript, HTML, etc.:**

    ~~~markdown
    ```html
    <div class="container">
    <h1>Welcome</h1>
    <p>This is a sample paragraph.</p>
    </div>
    ```
    ~~~

  - **For Python (Requires Indentation):**

    ~~~markdown
    ```python
    def greet(name):
        print("Hello, " + name + "!")
    ```
    ~~~

- **Condense Code Blocks**: Keep code snippets concise by removing unnecessary lines and comments. Focus on including only essential code to effectively convey the example, which reduces the overall token count.

- **Avoid Consecutive Blank Lines**: Within a code block, avoid consecutive blank lines. Maintain single spacing between lines to ensure the code renders correctly and remains token-efficient.

### Examples

Below are examples of well-formatted code blocks adhering to the best practices:

**CSS Example :**

```css
.test{
color:red;
}
```

**JavaScript Example :**

```javascript
function greet(name){
console.log("Hello, " + name + "!");
}
```

**HTML Example :**

```html
<div class="container">
<h1>Welcome</h1>
<p>This is a sample paragraph.</p>
</div>
```

**Python Example (With Required Indentation):**

```python
def greet(name):
    print("Hello, " + name + "!")
```

