
### **1. How to Use Forms in React**

Forms in React work differently than in vanilla HTML because React uses **state** to handle form data. There are two primary ways to handle form inputs:

-   **Controlled Components** (Recommended)
-   **Uncontrolled Components**

### **2. What is a ‘Controlled Component’?**

A **controlled component** is a form element (like `<input>`, `<textarea>`, `<select>`) that is controlled by React state. The component’s value is managed by `useState`, meaning the input updates the state as the user types.

Example of a controlled input:

```jsx
import { useState } from 'react';

function ControlledForm() {
  const [name, setName] = useState('');

  return (
    <form>
      <input 
        type="text" 
        value={name} 
        onChange={(e) => setName(e.target.value)}
      />
      <p>Your Name: {name}</p>
    </form>
  );
}

```

### **3. When Should We Update State?**

We should update the state **as the user types** rather than waiting for form submission. This provides:

-   Real-time validation
-   Instant feedback
-   A better user experience

### **4. Targeting User Input in an Event Handler**

To get the input value inside an event handler, use `event.target.value`.

Example:

```jsx
const handleChange = (event) => {
  console.log(event.target.value);
};

```

### **5. The Conditional (Ternary) Operator**

The **ternary operator** is a shorthand for `if...else` statements.  
**Syntax:**

```jsx
condition ? expressionIfTrue : expressionIfFalse;

```

### **6. Rewriting the `if...else` Statement as a Ternary**

Given:

```js
if(x === y){
  console.log(true);
} else {
  console.log(false);
}

```

Using a ternary:

```js
console.log(x === y ? true : false);

```

or even shorter:

```js
console.log(x === y);

```

### **7. Resources to Bookmark & Review:**

-   [React Bootstrap - Forms](https://react-bootstrap.github.io/forms/)
-   [React Docs - Conditional Rendering](https://react.dev/learn/conditional-rendering)
