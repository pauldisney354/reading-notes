### Component-Based Architecture

-   **What is a "component"?**
    
    -   A component is a self-contained, reusable block of code that defines how a user interface (UI) element should appear and behave in React. It can represent anything from a button to a complex UI section.
-   **Characteristics of a component:**
    
    -   **Encapsulation**: Each component manages its own state and logic, ensuring that one component doesn't interfere with another.
    -   **Reusability**: Components can be reused across multiple parts of the application, which promotes maintainability and scalability.
    -   **Composition**: Components can be composed of other components, allowing for a hierarchy or structure.
    -   **Declarative**: Components declare what the UI should look like based on the current state, rather than imperatively managing changes.
-   **Advantages of using component-based architecture:**
    
    -   **Separation of concerns**: Breaking the UI into smaller components simplifies the development process.
    -   **Reusability**: Components can be reused in different places, reducing code duplication.
    -   **Maintainability**: Smaller, focused components are easier to maintain and update.
    -   **Scalability**: As applications grow, component-based architecture helps manage complexity by organizing code into smaller, manageable pieces.

### What is Props and How to Use it in React

-   **What is “props” short for?**
    
    -   “Props” is short for “properties”. They are inputs to a React component, used to pass data and behavior from a parent component to a child component.
-   **How are props used in React?**
    
    -   Props are passed from a parent component to a child component as attributes, much like HTML attributes. The child component receives props as an object and can use them to render dynamic content or trigger actions.
-   **What is the flow of props?**
    
    -   **One-way data flow**: Props follow a unidirectional (top-down) data flow from parent to child components. The parent passes props to its child, and the child component cannot modify the props—it can only read or use them.