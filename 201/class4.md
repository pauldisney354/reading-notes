## HTML Links

### 1. To create a basic link, we wrap text or other content inside what element?

We wrap text or content inside the `<a>` (anchor) element to create a hyperlink. For example:

`<a href="https://www.example.com">Visit Example</a>` 

### 2. The `href` attribute contains what information?

The `href` attribute contains the URL (Uniform Resource Locator) to which the link points. It specifies the destination of the link. For example:

`<a href="https://www.example.com">Link to Example</a>` 

### 3. What are some ways we can ensure links on our pages are accessible to all readers?

To ensure accessibility:

- Use descriptive link text that clearly indicates the link's purpose (avoid generic text like "click here").
- Provide a title attribute that offers additional information when a user hovers over the link.
- Ensure sufficient color contrast between link text and the background.
- Use ARIA (Accessible Rich Internet Applications) roles and properties where appropriate.
- Implement keyboard navigation and focus styles to help users who rely on keyboards or assistive technologies.

## CSS Layout

### 4. What is meant by “normal flow”?

“Normal flow” refers to the default layout behavior of elements on a webpage, where block-level elements stack vertically, and inline elements flow horizontally. This means that block elements like `<div>` and `<p>` create a new line after them, while inline elements like `<span>` do not.

### 5. What are a few differences between block-level and inline elements?

**Block-level elements:**

- Take up the full width available.
- Start on a new line.
- Examples include `<div>`, `<h1>`, `<p>`, and `<section>`.

**Inline elements:**

- Only take up as much width as necessary.
- Do not start on a new line.
- Examples include `<span>`, `<a>`, and `<img>`.

### 6. ___ positioning is the default for every HTML element.

**Static** positioning is the default for every HTML element. Static elements are positioned according to the normal flow of the document.

### 7. Name a few advantages to using absolute positioning on an element.

Advantages of absolute positioning include:

- Precise control over the element’s placement on the page.
- Freedom from the normal document flow, allowing elements to overlap others.
- Ability to position elements relative to their nearest positioned ancestor (non-static).

### 8. What is a key difference between fixed positioning and absolute positioning?

The key difference is that **fixed positioning** keeps an element in a fixed position relative to the viewport (browser window) regardless of scrolling, while **absolute positioning** places an element relative to its nearest positioned ancestor. Fixed elements remain in the same place even when the user scrolls the page.

## Learn JS

### 9. Describe the difference between a function declaration and a function invocation.

A **function declaration** defines a function and establishes its name, parameters, and code block. For example:

`function sayHello() {
    console.log("Hello, world!");
}` 

A **function invocation** (or call) executes the function defined by the declaration. For example:

`sayHello(); // This will output "Hello, world!" to the console.` 

### 10. What is the difference between a parameter and an argument?

A **parameter** is a variable in the function declaration that receives a value when the function is called. An **argument** is the actual value passed to the function when it is invoked. For example:

`function greet(name) { // 'name' is a parameter
    console.log("Hello, " + name);
}
greet("Alice"); // "Alice" is the argument` 

## Miscellaneous

### 11. Pick 2 benefits to pair programming and reflect on how these benefits could help you on your coding journey.

- **Increased Code Quality**: With two developers working together, code is reviewed in real-time, leading to fewer errors and improved overall quality. This is beneficial as it encourages better coding practices and immediate feedback.
- **Enhanced Learning and Knowledge Sharing**: Pair programming fosters collaboration and allows for knowledge transfer. Working alongside someone more experienced can accelerate learning and expose you to new techniques and best practices, helping you grow as a developer.