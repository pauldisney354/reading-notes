### **Thinking in React**

1.  **Single Responsibility Principle & Components**
    
    -   The **Single Responsibility Principle (SRP)** states that each component should have **one reason to change** (i.e., it should only handle one piece of functionality).
    -   In React, this means **breaking down the UI into small, reusable components**, each responsible for **one job** (e.g., a `Button` component should only render a button, not handle form submission logic).
2.  **Building a Static Version of an Application**
    
    -   A **static version** of a React app is built by creating components that render UI **without interactivity (state or event handlers)**.
    -   This step **focuses purely on structure and styling** using props to pass down data.
3.  **What to Add After the Static Version**
    
    -   Once the UI structure is complete, **stateful logic and interactivity** are introduced.
    -   This means adding **state management, event handling, and user interaction**.
4.  **Three Questions to Determine State**
    
    -   Ask yourself:
        1.  **Does this data change over time?** (If no, it’s not state.)
        2.  **Is it passed down from a parent via props?** (If yes, it probably isn’t state.)
        3.  **Can it be computed from existing state or props?** (If yes, avoid storing it as state.)
5.  **Identifying Where State Lives**
    
    -   Follow these steps:
        -   Identify every component that needs the state.
        -   Find the closest common ancestor of those components.
        -   Put the state in that ancestor (lifting state up if needed).

----------

### **Higher-Order Functions**

1.  **Definition of a Higher-Order Function**
    
    -   A **higher-order function (HOF)** is a function that either:
        -   **Takes another function as an argument**
        -   **Returns a function as a result**
    -   Examples: `map()`, `filter()`, `reduce()`, `forEach()`.
2.  **Understanding the `greaterThan` Function**
    
    ```js
    function greaterThan(n) {
      return m => m > n;
    }
    let greaterThan10 = greaterThan(10);
    console.log(greaterThan10(11)); // → true
    
    ```
    
    -   **Line 2 (`return m => m > n;`)** returns a new function that takes `m` and checks if it's greater than `n`.
    -   This makes `greaterThan(10)` return a function that checks if numbers are greater than `10`.
3.  **How `map()` Works with Higher-Order Functions**
    
    ```js
    const numbers = [1, 2, 3, 4];
    const doubled = numbers.map(num => num * 2);
    console.log(doubled); // → [2, 4, 6, 8]
    
    ```
    
    -   `map()` **takes a function as an argument** and applies it to each element in an array.
    -   It **returns a new array** with transformed elements.

    ### **Conditional Rendering in React**  
Conditional rendering in React refers to rendering different components or elements based on a condition. This helps create dynamic UI updates based on state or props.

### **What is Browser Router?**  
`BrowserRouter` is a component from `react-router-dom` that enables client-side routing in a React application. It listens to the browser's URL changes and renders components accordingly without needing a full page reload.

### **Ternary Operator for Conditional Rendering**  
A ternary operator is a concise way to write an `if/else` condition:

```js
// Regular if/else conditional
if(conditionIsTrue){
  return 'it is true';
} else {
  return 'it is false';
}

// Equivalent ternary statement
return conditionIsTrue ? 'it is true' : 'it is false';
```

### **Conditionally Rendering a Component in React**  
Using a ternary operator:
```jsx
class Parent extends React.Component {
  constructor(props){
    super(props);
    this.state = {
      displayChild: false
    };
  }

  render() {
    return (
      <div>
        {this.state.displayChild ? <Child /> : ''}
      </div>
    );
  }
}
```
A better way to write this is by using the `&&` operator:
```jsx
class Parent extends React.Component {
  constructor(props){
    super(props);
    this.state = {
      displayChild: false
    };
  }

  render() {
    return (
      <div>
        {this.state.displayChild && <Child />}
      </div>
    );
  }
}
```
This works because in JavaScript, `false && <Component />` evaluates to `false`, while `true && <Component />` evaluates to `<Component />`.