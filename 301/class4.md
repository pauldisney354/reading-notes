
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

### **Definitions & Descriptions**

1.  **Event** – An event is any interaction that occurs in a web application, such as a user clicking a button, typing in an input field, or submitting a form. Events allow for dynamic interactivity in a web application.
    
2.  **Forms** – Forms are HTML elements (`<form>`) that allow users to input and submit data. In React, forms are commonly controlled using component state to handle input values dynamically.
    
3.  **Event Listeners** – An event listener is a function that "listens" for a specific event to occur on an element (e.g., `click`, `change`, `submit`). In JavaScript and React, event listeners are typically added using methods like `addEventListener` or through JSX props such as `onClick` or `onChange`.
    
4.  **Event Handlers** – An event handler is the function that is called when an event occurs. It is the actual function that executes the desired logic when an event listener detects an event.
    
5.  **event.target** – The `event.target` property refers to the element that triggered the event. For example, in an input field, `event.target.value` gives the current value of the input.
    
6.  **Execute** – In the context of event handling, execution refers to running a function when an event occurs. React automatically re-renders components as state changes when an event handler modifies state.
    

### **Understanding Forms in a React Application**

-   Forms in React are often controlled components, meaning their values are stored in the component’s state and updated using event handlers.
    
-   Example of a controlled form in React:
    
    ```jsx
    function MyForm() {
      const [inputValue, setInputValue] = React.useState("");
    
      const handleChange = (event) => {
        setInputValue(event.target.value);
      };
    
      return (
        <form>
          <input type="text" value={inputValue} onChange={handleChange} />
          <p>You typed: {inputValue}</p>
        </form>
      );
    }
    
    ```
    

### **Passing Form Data to a Child Component**

-   Data collected from a form in a parent component can be passed to a child component via props.
    
    ```jsx
    function ParentComponent() {
      const [formData, setFormData] = React.useState("");
    
      const handleInputChange = (event) => {
        setFormData(event.target.value);
      };
    
      return (
        <div>
          <FormComponent formData={formData} onInputChange={handleInputChange} />
        </div>
      );
    }
    
    function FormComponent({ formData, onInputChange }) {
      return (
        <form>
          <input type="text" value={formData} onChange={onInputChange} />
          <p>Form Data: {formData}</p>
        </form>
      );
    }
    
    ```
    

### **Notes & Key Questions**

#### **Difference between an event listener and an event handler?**

-   **Event Listener:** Listens for an event and triggers a function when it occurs.
-   **Event Handler:** The function that is executed when the event listener detects an event.

#### **How do I access the value that the user is typing in an input field when listening for an `onChange` event?**

-   Use `event.target.value` inside the event handler function.
    
    ```jsx
    const handleChange = (event) => {
      console.log(event.target.value);
    };
    
    ```
    

#### **How do I send the information collected from a child form component up to a parent component?**

-   Pass a function as a prop from the parent to the child. The child calls this function with the new value when the input changes.
    
    ```jsx
    function ParentComponent() {
      const [formData, setFormData] = React.useState("");
    
      const handleDataFromChild = (data) => {
        setFormData(data);
      };
    
      return <ChildForm onDataChange={handleDataFromChild} />;
    }
    
    function ChildForm({ onDataChange }) {
      return (
        <input
          type="text"
          onChange={(event) => onDataChange(event.target.value)}
        />
      );
    }
    
    ```