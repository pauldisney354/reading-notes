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