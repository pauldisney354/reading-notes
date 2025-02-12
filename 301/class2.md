### React Lifecycle and Props

#### 1. **What happens first, the ‘render’ or the ‘componentDidMount’?**

-   **Render** happens first. The `render()` method is responsible for returning the React element (JSX), and it runs before `componentDidMount`. The `componentDidMount` is triggered after the component has been rendered to the DOM, meaning it happens after the initial render.

#### 2. **What is the very first thing to happen in the lifecycle of React?**

-   The **constructor** is the first thing to happen in the lifecycle of a React component. It is called when the component is created, allowing for initializations like setting state and binding methods.

#### 3. **Put the following things in the order that they happen: `componentDidMount`, `render`, `constructor`, `componentWillUnmount`, React Updates.**

-   **Correct order**:
    1.  **Constructor** (Initial setup)
    2.  **Render** (Returns JSX to be displayed)
    3.  **ComponentDidMount** (Runs after render, usually for API calls or setting up listeners)
    4.  **React Updates** (Triggered when props or state changes)
    5.  **ComponentWillUnmount** (Runs before the component is removed from the DOM, typically for cleanup)

#### 4. **What does `componentDidMount` do?**

-   `componentDidMount` is a lifecycle method in React that is invoked immediately after a component is mounted (i.e., inserted into the tree). It’s often used for making API calls, setting up subscriptions, or performing any setup that requires the component to be present in the DOM.

----------

### React State vs Props

#### 1. **What types of things can you pass in the props?**

-   Props are used to pass data from a parent component to a child component. You can pass various types of data, including:
    -   **Strings**
    -   **Numbers**
    -   **Arrays**
    -   **Objects**
    -   **Functions**
    -   **React elements**
    -   **Booleans**

#### 2. **What is the big difference between props and state?**

-   **Props**:
    -   Immutable (read-only) and passed down from a parent component.
    -   Used to pass data and event handlers to child components.
-   **State**:
    -   Mutable and managed within the component itself.
    -   Can be changed within the component and triggers re-renders when modified.

#### 3. **When do we re-render our application?**

-   React re-renders the component when there are **changes in state** or **props**. Any change in either will trigger a re-render to ensure the UI is in sync with the underlying data.

#### 4. **What are some examples of things that we could store in state?**

-   Some common things you might store in state include:
    -   **User input** (e.g., form fields, search queries)
    -   **Flags for showing/hiding components** (e.g., modal visibility)
    -   **API data** (e.g., fetched data from a backend)
    -   **Component-specific UI states** (e.g., active tabs, selected items)