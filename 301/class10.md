

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
    

