## HTML

### Unordered Lists
- **When to Use**: Use an unordered list when the list items don't follow a specific sequence or priority, like a list of features or items to pack.
- **Changing Bullet Style**: You can change the bullet style of an unordered list by using the `list-style-type` property in CSS. Options include `disc`, `circle`, `square`, or `none`.
- **Ordered vs. Unordered List**: An ordered list is best when the sequence or order of the items matters, such as a set of instructions. An unordered list is better when the order is irrelevant.

### Ordered Lists
- **Changing Numbers on Ordered List Items**:
  - Using the `start` attribute in HTML to begin counting from a specific number.
  - Using CSS `list-style-type` to change numbering to Roman numerals, letters, etc.

## CSS

### The Box Model Story: "The Box Model"
In “The Box Model,” **Margin** and **Padding** are characters who ensure balance and space around **Content**. 
- **Margin** creates space around the element's border, pushing it away from other elements, like a buffer.
- **Padding** adds space inside the border and around the content, keeping content comfortable and spaced from the boundary.

### Four Parts of the HTML Element Box Model
1. **Content**: The area where text or images appear.
2. **Padding**: Space between the content and the border, inside the element.
3. **Border**: Surrounds the padding and content, acting as a visible boundary.
4. **Margin**: The space outside the border, creating separation from other elements.

## JavaScript

### Arrays
- **Data Types Stored**: Arrays in JavaScript can store any data type, including numbers, strings, objects, functions, and even other arrays (nested arrays).

- **Accessing `people` Array**: Yes, it is a valid JavaScript array. You can access values using bracket notation, like `people[0][0]` for "pete" or `people[1][3]` for "fishing:hiking:rock_climbing".

### JavaScript Shorthand Operators
1. `+=`: Adds and assigns, e.g., `x += 2` is shorthand for `x = x + 2`.
2. `-=`: Subtracts and assigns, e.g., `y -= 3` is shorthand for `y = y - 3`.
3. `*=`: Multiplies and assigns, e.g., `z *= 4` is shorthand for `z = z * 4`.
4. `/=`: Divides and assigns, e.g., `w /= 2` is shorthand for `w = w / 2`.
5. `++`: Increments by 1, e.g., `a++` is shorthand for `a = a + 1`.

### Code Evaluation
For this code snippet:
```javascript
let a = 10;
let b = 'dog';
let c = false;

// Evaluate this
(a + c) + b;

Result: "10dog".

Explanation: a + c evaluates to 10 + 0 (since false converts to 0), which is 10. Then, 10 + b results in "10dog" due to JavaScript's type coercion, converting 10 to a string when concatenated with "dog".

Conditional Statements

Example: A conditional statement can check if a user is logged in to a site. If logged in, display their profile; if not, show a login prompt.

Loops in JavaScript

Example: A loop is useful for iterating through an array of user comments to display each one on a webpage.
