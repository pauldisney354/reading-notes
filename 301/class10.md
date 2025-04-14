

## 🧠 JavaScript Call Stack & Errors – Reading Notes

**📌 Why this topic matters**  
As a web developer, understanding the **JavaScript call stack** is fundamental to how code executes, how to trace bugs, and how to write efficient, non-blocking logic. This knowledge enables me to debug better, anticipate stack overflows, and identify types of JavaScript errors—critical to mastering both synchronous behavior and debugging tools in modern front-end development.

----------

### 📚 Reading Assignment: Questions & Answers

#### ✅ What is a ‘call’?

A “call” is when a function is **invoked** and placed on the **call stack**, creating a new execution context. This could be something like `myFunction()` in code, or a callback triggered by a DOM event or another function.

#### ✅ How many ‘calls’ can happen at once?

Only **one call at a time**. JavaScript is single-threaded, so the **call stack** handles one operation at a time. Functions are stacked and executed one-by-one in a **synchronous** order unless asynchronous patterns are used.

#### ✅ What does LIFO mean?

LIFO = **Last In, First Out**. The last function pushed onto the stack is the first to finish and get popped off. The stack is like a stack of plates: you can only remove the top one.

#### ✅ Draw an example of a call stack and the functions that would need to be invoked

Example Code:

```js
function one() {
  two();
}
function two() {
  three();
}
function three() {
  console.log("End");
}
one();

```

**Call Stack at peak execution:**

```
| three() |
| two()   |
| one()   |
| global  |

```

#### ✅ What causes a Stack Overflow?

A **stack overflow** happens when function calls go too deep without terminating—usually due to infinite recursion.

Example:

```js
function loop() {
  loop(); // stack grows infinitely
}
loop(); // ❌ Stack Overflow

```

----------

### ⚠️ JavaScript Error Messages

#### ✅ What is a ReferenceError?

Thrown when referencing a variable that hasn’t been declared:

```js
console.log(myVar); // ❌ ReferenceError

```

#### ✅ What is a SyntaxError?

Occurs when code breaks JavaScript's grammar rules.

```js
let x = ; // ❌ SyntaxError

```

#### ✅ What is a RangeError?

Happens when a number is outside its allowable range.

```js
let arr = new Array(-5); // ❌ RangeError

```

#### ✅ What is a TypeError?

Thrown when a value is not of the expected type:

```js
null.f(); // ❌ TypeError: null has no method `f`

```

----------

### 🛠️ Debugging Tools

#### ✅ What is a breakpoint?

A **breakpoint** is a developer-defined pause in the browser’s code execution, allowing inspection of values and flow. It’s set in the **DevTools → Sources tab**.

#### ✅ What does the word ‘debugger’ do in your code?

The `debugger;` statement pauses script execution just like a breakpoint. It's useful for manually stopping execution to examine context and variables.

----------

## 📎 Cited Resources

-   "Understanding the JavaScript Call Stack" – Code Fellows Reading
    
-   MDN Web Docs: [JavaScript Errors Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors)
    

----------

## 🌱 Things I Want to Know More About

-   How does the **call stack** interact with the **event loop** and **callback queue**?
    
-   What’s the real difference between `ReferenceError` and `TypeError` in asynchronous code?
    
-   Can we simulate a “multi-threaded” effect in JS without Web Workers?
    
-   Is there a way to **trace a stack overflow** to its origin automatically?
    
Here's a structured set of notes for your reading assignment based on the new material. It's ready to add as a new page and link in your course's Table of Contents.

----------

## 🧠 Caching & Debugging – Reading Notes

**📌 Why this topic matters**  
As a developer, understanding **caching** and **debugging** helps optimize performance and streamline error resolution. Caching improves efficiency by avoiding redundant data retrievals, while debugging techniques help isolate and fix issues. Mastering both is essential for building scalable, fast, and bug-resistant applications.

----------

### 📚 Reading Assignment: Questions & Answers

#### ✅ What is a cache?

A **cache** is a temporary storage location that holds frequently accessed data so it can be quickly retrieved without having to re-fetch it from the original source (e.g., API, database).

#### ✅ What does a cache hit mean? What does a cache miss mean?

-   **Cache hit**: The requested data is **already in the cache**, so it's retrieved quickly.
    
-   **Cache miss**: The requested data is **not in the cache**, so the app must fetch it from the original source, and then optionally store it in the cache for future use.
    

#### ✅ What does the word `debugger` do in your code?

The `debugger;` statement **pauses execution** of JavaScript at that point, as if a manual breakpoint was placed. This lets the developer inspect variables, call stack, and application state at that moment.

```js
function test() {
  let x = 10;
  debugger;
  console.log(x);
}

```

#### ✅ What is a breakpoint?

A **breakpoint** is a pause in code execution triggered within developer tools (like Chrome DevTools). It lets you step through code line by line to inspect variables and control flow.

----------

### 🛠️ 5 Different Debugging Tools

1.  **Chrome DevTools** – Built-in suite in Chrome for inspecting and debugging web apps.
    
2.  **VS Code Debugger** – Integrated debugger in the editor with breakpoints and variable watchers.
    
3.  **Linting Tools (ESLint)** – Highlight syntax and logic issues before code runs.
    
4.  **Console Logging (`console.log`)** – Old-school, quick way to print and inspect values.
    
5.  **Postman** – Helps debug and test API calls, responses, and headers.
    

----------

### 💾 Code Example: Adding to the Cache

```js
if (inMemoryDB[ingredient] !== undefined) {
  // Cache hit – return cached data
  return inMemoryDB[ingredient];
} else {
  // Cache miss – fetch from API, then cache it
  inMemoryDB[ingredient] = recipeArr;
}

```

----------

### 🧭 Tracking Cache Age with Timestamps

```js
function Recipe(obj) {
  // Add timestamp when data is stored
  this.dateAdded = Date.now();
}

```

To check if the data is **fresh or stale**:

```js
if (cache[key] && (Date.now() - cache[key].dateAdded < 50000)) {
  console.log('Cache hit');
} else {
  // Cache miss – clear and refresh
  console.log('Cache miss or stale');
}

```

This approach avoids using outdated data and ensures performance stays sharp without compromising data accuracy.

----------

## 🌱 Things I Want to Know More About

-   What are some libraries that simplify in-memory caching for React or Node.js?
    
-   Is localStorage ever appropriate for cache purposes?
    
-   How do service workers play a role in caching and offline behavior?
    
-   How can you visualize the call stack in real time with debugging tools?
