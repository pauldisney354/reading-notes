**Passing Functions as Props** in React:

---

### **Reading: Lists and Keys**
1. **What does `.map()` return?**  
   - The `.map()` method returns a **new array** with the results of calling a provided function on every element in the original array.

2. **Looping through an array to display values in JSX**  
   - You can use `.map()` inside JSX to generate a list of components dynamically. Example:

     ```jsx
     const items = ['Apple', 'Banana', 'Cherry'];
     return (
       <ul>
         {items.map((item, index) => (
           <li key={index}>{item}</li>
         ))}
       </ul>
     );
     ```

3. **Each list item needs a unique ____?**  
   - **Key**. The `key` prop helps React identify elements when updating the DOM.

4. **Purpose of a key?**  
   - Keys help React **efficiently update and re-render** components by tracking changes in a list.

---

### **Reading: The Spread Operator**
1. **What is the spread operator (`...`)?**  
   - The spread operator allows you to **expand** arrays or objects into individual elements.

2. **List 4 things the spread operator can do:**  
   - Copy an array  
   - Merge two or more arrays  
   - Copy an object  
   - Merge objects into one  

3. **Example: Combining two arrays**
   ```js
   const arr1 = [1, 2, 3];
   const arr2 = [4, 5, 6];
   const combined = [...arr1, ...arr2];
   console.log(combined); // [1, 2, 3, 4, 5, 6]
   ```

4. **Example: Adding a new item to an array**
   ```js
   const fruits = ['Apple', 'Banana'];
   const newFruits = [...fruits, 'Cherry'];
   console.log(newFruits); // ['Apple', 'Banana', 'Cherry']
   ```

5. **Example: Combining two objects**
   ```js
   const obj1 = { name: 'Alice' };
   const obj2 = { age: 25 };
   const merged = { ...obj1, ...obj2 };
   console.log(merged); // { name: 'Alice', age: 25 }
   ```

---

### **Videos: How to Pass Functions Between Components**
1. **First step to pass functions between components?**  
   - The developer **defines the function** inside the parent component.

2. **What does `handleClick` do?**  
   - `handleClick` is a function that performs an action (e.g., updating state) when an event occurs.

3. **How to pass a method from parent to child?**  
   - Pass it as a prop:

     ```jsx
     <ChildComponent handleClick={this.handleClick} />
     ```

4. **How does the child component invoke the method?**  
   - By calling it inside an event handler:

     ```jsx
     function ChildComponent({ handleClick }) {
       return <button onClick={handleClick}>Click Me</button>;
     }
     ```

---


### 1. How can a child component update the state of a parent component?

In React, a child component can update the state of a parent component by receiving a function as a prop from the parent. The parent defines a state and a function to update that state, then passes the function down to the child. The child calls that function when needed.

#### Example:

```jsx
import { useState } from "react";

function Parent() {
  const [message, setMessage] = useState("Hello from Parent");

  const updateMessage = (newMessage) => {
    setMessage(newMessage);
  };

  return (
    <div>
      <h2>{message}</h2>
      <Child updateMessage={updateMessage} />
    </div>
  );
}

function Child({ updateMessage }) {
  return (
    <button onClick={() => updateMessage("Updated by Child")}>
      Click to Update Parent State
    </button>
  );
}

```

Here, `updateMessage` is passed as a prop to `Child`, which calls it to update the parent's state.

----------

### 2. How does a parent component send a function into a child component?

A parent component sends a function into a child component by passing it as a prop.

#### Example:

```jsx
function Parent() {
  const handleClick = () => {
    alert("Function called from child!");
  };

  return <Child handleClick={handleClick} />;
}

function Child({ handleClick }) {
  return <button onClick={handleClick}>Click Me</button>;
}

```

Here, `handleClick` is a function defined in the parent, passed as a prop to `Child`, and invoked when the button is clicked.

----------

### 3. Using React-Bootstrap, how do you determine if a modal is open or closed?

In React-Bootstrap, a modal’s visibility is controlled by the `show` prop. To determine if it's open or closed, check the state variable linked to `show`.

#### Example:

```jsx
import { useState } from "react";
import { Modal, Button } from "react-bootstrap";

function MyComponent() {
  const [show, setShow] = useState(false);

  return (
    <div>
      <Button onClick={() => setShow(true)}>Open Modal</Button>
      <Modal show={show} onHide={() => setShow(false)}>
        <Modal.Header closeButton>
          <Modal.Title>My Modal</Modal.Title>
        </Modal.Header>
        <Modal.Body>Modal is {show ? "Open" : "Closed"}</Modal.Body>
        <Modal.Footer>
          <Button onClick={() => setShow(false)}>Close</Button>
        </Modal.Footer>
      </Modal>
    </div>
  );
}

```

-   If `show === true`, the modal is open.
-   If `show === false`, the modal is closed.  
    The `onHide` function ensures that clicking the close button updates the state correctly.